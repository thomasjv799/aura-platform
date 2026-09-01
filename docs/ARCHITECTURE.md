# Aura — Technical Architecture

The recommended stack, phase by phase, with the reason for each choice and the
measurable trigger that should make us change it. Every cost figure is priced
against verified 2026 vendor rates; see [RESEARCH.md](RESEARCH.md) for sources.

> **Design bias:** deliberately boring. The hard problems in this product are
> catalogue supply, relevance and unit economics — not infrastructure. Every
> component below is chosen to be the cheapest thing that cannot become the
> reason we fail.

---

## 0. The constraint that determines everything

**Aura's LLM budget per conversation is about 4.5 US cents, and that is the
gross commission, not the profit.**

Working: ₹2,000 (~$25) AOV × 6% net commission × 3% conversation-to-sale =
$0.045 gross per conversation. An 8-turn conversation costs roughly 14,400
input + 2,240 output tokens.

| Hot-path model | Cost / conversation | % of gross commission |
|---|---:|---:|
| gpt-5-nano | $0.0016 | 3.6% |
| **Gemini 2.5 Flash-Lite** | **$0.0023** | **5.1%** |
| gpt-5-mini | $0.0081 | 18.0% |
| Gemini 2.5 Flash | $0.0099 | 22.0% |
| Claude Haiku 4.5 | $0.0256 | 56.9% |
| Claude Sonnet 5 | $0.0512 | 113.8% |

A frontier model on the hot path costs more than the commission it earns. This
is not a preference for cheap models — it is an arithmetic constraint on the
architecture. **The conversation-to-sale rate (3%) is the load-bearing and
entirely unvalidated assumption**: at 1% conversion, everything above the
nano/lite tier is underwater.

**Consequence:** tier the models.

- **Hot path** (intent parsing, filter extraction, query rewriting) — smallest
  model that passes eval. Start at Gemini 2.5 Flash-Lite.
- **User-visible reasoning** (the "why this?" line on each card) — one tier up,
  and only for the items actually rendered, not the whole candidate set.
- **Offline enrichment** (attribute extraction) — batch API, 50% discount,
  quality over latency.

---

## 1. Catalogue: the gating dependency

Nothing else in this document matters until this is solved. Affiliate networks
in India sell *link conversion and reporting*, not product data — Cuelinks'
developer API has 33 endpoints and **no SKU feed**. Myntra and Ajio have no
self-serve affiliate programme at all. Amazon's PA-API 5.0 was retired on
15 May 2026, and its replacement requires ~10 qualified sales in a rolling
30-day window — you need converting traffic *before* you get catalogue access.

**PoC source of record: Shopify/D2C India fashion brands.** They are the only
clean, legal, structured, free feed a small team can obtain, and brand-direct
commission is materially better than marketplace rates. Marketplace coverage
comes later, through a normalising aggregator or a commercial feed vendor.

```
merchant feed (Shopify / XML / CSV)
        │
        ▼
  ingest + normalise ──► raw_product          (append-only, source-of-truth)
        │
        ▼
  attribute enrichment ──► product            (typed, category-gated schema)
        │
        ▼
  index build ──────────► pgvector + FTS      (hybrid retrieval)
        │
        ▼
  freshness probe ──────► price/stock refresh (fast lane, no re-enrichment)
```

Two loops, deliberately separated:

- **Slow loop** (daily/weekly): new SKUs, attribute enrichment, embeddings.
- **Fast loop** (hourly, or on read): price, stock, deep-link validity. These
  are the fields that destroy trust when stale, and they must never wait on the
  enrichment pipeline.

Every product row carries `fetched_at`. Nothing renders without it.

---

## 2. Retrieval

**Store: Postgres + pgvector.** Not because it is fastest, but because price
and stock live in Postgres anyway — one store means filter-plus-vector is a
single transactional query with no sync lag against a feed that changes hourly.

Sizing: 1M vectors at 768-dim float32 = 3.1 GB; int8-quantised = 0.77 GB. At
5M SKUs int8 that is ~4 GB — fits in RAM on a commodity box, which is the whole
reason this stays cheap. Managed Postgres at this scale runs $20–60/month.

**Migration trigger** (not a matter of taste): move to a dedicated vector store
when p95 filtered-query latency exceeds 300 ms at production filter cardinality,
or when the working set exceeds ~5M vectors. Qdrant self-hosted is the next
step; Turbopuffer is the escape hatch at real scale.

**Method: hybrid lexical + vector with Reciprocal Rank Fusion.** On the WANDS
e-commerce relevance set, tuned hybrid reached 0.7497 NDCG vs 0.6983 for BM25
alone and 0.6953 for pure vector — ~7.4% over either. RRF (`score = Σ 1/(k+rank)`,
k=60) uses only rank positions, so no score normalisation is needed between a
BM25 and an HNSW index.

The mechanism matters specifically for Indian fashion queries, which mix all
three signal types in one sentence:

> "sage green **Anarkali** under **₹3000** for a **haldi**, size M"

- BM25 catches `Anarkali`, `chikankari`, brand names, size labels — literal
  tokens dense vectors reliably miss.
- Vectors catch occasion intent and paraphrase.
- Hard filters catch price, size and availability.

**The filter trap.** Naively bolting filters onto HNSW degrades in a
predictable, documented way. Qdrant's own guidance: pre-filtering "breaks too
many links in the HNSW graph, causing lower accuracy" on large datasets, and
filterable-HNSW adds extra edges *per payload index separately, not for every
combination* — so `size=M AND price<2000 AND in_stock AND occasion=haldi`,
which is exactly Aura's query shape, can still disconnect the graph. Design for
this from the start: keep filter cardinality estimates, and let the planner fall
back to payload-index-only scans when cardinality is low.

**Embeddings: Marqo-FashionSigLIP, self-hosted.** Fashion-tuned embeddings beat
generic ones decisively. On LookBench (arXiv 2601.14706, Jan 2026 — independent
and contamination-aware, ~2,500 queries against 60k images):

| Model | Fine Recall@1 |
|---|---:|
| GR-Pro (proprietary) | 67.4% |
| GR-Lite (proprietary) | 65.7% |
| **Marqo-fashionCLIP** | **63.2%** |
| **Marqo-fashionSigLIP** | **62.8%** |
| Generic CLIP / SigLIP2 / DINOv2 baselines | 30–45% |

~20 points over generic CLIP. Self-hosting costs almost nothing (1M images on a
rented L4 at ~$0.39/hr = 1.9–5.5 GPU-hours ≈ **$0.75–2.20**) and the real reason
to self-host is version control: a hosted embedding model that deprecates forces
a full catalogue re-embed on the vendor's schedule, not yours.

---

## 3. Attribute enrichment

Catalogue AI is nearly free and the instinct to economise here is misdirected —
extraction and embedding together never exceed ~5% of the monthly bill.

Cost to enrich **1M SKUs** (~800 input + 150 output tokens each, batch pricing):

| Model | Cost / 1M SKUs |
|---|---:|
| gpt-5-nano | $50 |
| Gemini 2.5 Flash-Lite | $70 |
| gpt-5-mini | $250 |
| Gemini 2.5 Flash | $308 |
| Claude Haiku 4.5 | $775 |

**The one design rule that matters.** A WACV 2026 study (arXiv 2601.15711, 9 VLMs,
5,000 fashion images, 18 attributes) decomposed the task three ways:

| Tier | Task | Mean score |
|---|---|---:|
| 1 | Full attribute labelling | Gemini 2.5 Pro best at 64.0% macro-F1 |
| 2 | **Knowing an attribute does not apply** | **24.7%** |
| 3 | Classifying, given it applies | 61% (Flash best, 70.8%) |

Models are decent at seeing attributes and terrible at knowing when one is
irrelevant. **So never ask for all attributes on every SKU.** Gate the schema by
category — ask `neckline` only for tops and dresses, `rise` only for bottoms —
so the model is never asked to emit N/A. That single choice converts the 24.7%
failure case into the 61–71% success case.

For reference, the same task on supervised Fashion-CLIP embeddings scores ~21%
F1, so zero-shot VLM extraction is roughly **3× better than a trained baseline**.

### The occasion ontology

This is the one asset in the system that a competitor cannot clone in a sprint,
and it should be built as **structured data, not prompt text**:

```
occasion → ritual → dress code → fabric norms → colour norms & taboos
         → formality → time of day → region / community variation → budget band
```

Encoded as a versioned table with provenance, it is testable, reviewable by a
human stylist, and separable from the app — which also makes it the licensable
asset if the consumer product fails. See [ROADMAP.md](ROADMAP.md) for why that
escape hatch matters.

---

## 4. Grounding: the LLM must be structurally unable to state a price

Hallucination cannot be prompted away, and price and stock are the
fastest-changing fields in the system. A wrong discount in a shopping app is a
consumer-protection exposure, not just a quality bug. So enforce it in the
architecture, not the prompt:

1. **The model never sees the price.** It emits a `product_id` plus prose about
   style, fit and occasion. The client renders price, discount and availability
   from the feed row at display time. The model cannot repeat a stale number it
   was never shown.
2. **Every card carries `fetched_at`** from the feed row.
3. **A claim validator** regex-scans model output for currency symbols,
   digit-plus-`%` patterns and stock language ("in stock", "only 2 left",
   "sale") and rewrites or refuses the turn on a hit. Cheap, deterministic,
   testable in CI.
4. **Empty means empty.** If the retrieval set is empty after filters, the agent
   says so. It must never soften an empty result into a near-match without
   explicitly flagging the substitution.
5. **Price-drop alerts compare two feed snapshots** and state both numbers from
   the feed. The LLM writes only the sentence around them.

Product descriptions from merchant feeds are **untrusted input entering the
context window** — this is a real prompt-injection surface, not a theoretical
one. Treat catalogue text as data at every boundary.

---

## 5. Persona: rules, not ML

Contextual bandits are the theoretically correct answer for cold-start
personalisation and the wrong answer for Aura in 2026. The rate-limiting
resource is feedback events, not algorithm sophistication.

The arithmetic: at 1,000 MAU × 10 conversations/month × ~8 items per turn, a
bandit over even a 50-dimensional persona space sees a few hundred thousand
impressions but only a **few thousand genuine positive signals** per month,
spread across 1M+ SKUs and a long tail of occasion contexts.

Two further reasons rules win here:

- **Exploration is paid for in trust.** A bad recommendation in a style product
  is not a wasted impression; it is evidence the agent does not know you.
- **The persona is directly editable.** A user correcting their own profile is a
  far higher-bandwidth signal than anything inferrable from clicks — and it makes
  the system legible ("you told me you avoid crop tops") in a way a learned
  policy never is.

**Design:** deterministic weighted scoring over explicit persona fields, with
per-field provenance (`explicit` / `conversational` / `behavioural`) and
versioning. Revisit bandits only when a single user segment produces >10k
labelled positive interactions per month.

The persona store also holds the **DPDP consent ledger** — see §7. That is a
day-one schema requirement, not a later retrofit.

---

## 6. Evaluation

**Write the golden query set before the retrieval code.** Relevance tuning has
an unbounded tail without one, and the eval harness is simultaneously the
component most likely to be cut and the one whose absence causes the documented
DORA instability pattern.

- **100-query golden set**, authored by a human stylist, covering each target
  occasion, with graded relevance judgements.
- **Offline harness** in CI, gating merges from private beta onward.
- **LLM-as-judge, calibrated.** GPT-4-class judges reach >80% agreement with
  human preferences, but position bias runs up to **75% preference for whichever
  candidate appears first** — fatal when evaluating ranked lists. Every pairwise
  judgement must be run in both orderings and averaged, or the harness measures
  presentation order rather than relevance. Validate against humans at
  correlation >0.85 / Cohen's κ >0.6 before trusting it, and recalibrate
  periodically: judge scores drift, and a panel of judges can be confidently and
  consistently wrong together.

---

## 7. Compliance, built in

India's DPDP Rules were notified 14 November 2025. Consent Manager provisions
become operative around November 2026 and **full Data Fiduciary compliance is
due 13 May 2027** — inside this roadmap's horizon. 2026 is a soft-enforcement
"build and test" year; that is the window, not a reprieve.

Aura processes behavioural and style-preference data and sends proactive
marketing messages, so it is squarely a Data Fiduciary. Required in the persona
store from day one:

- consent capture with purpose binding and timestamped ledger
- purpose limitation enforced at query time, not by convention
- deletion and correction flows that actually cascade
- grievance redressal contact and process

Retrofitting this later is a multi-week rewrite of the exact component every
other subsystem depends on.

---

## 8. Cost envelope

| | 100 MAU / 300k SKUs | 1k MAU / 1.5M SKUs | 10k MAU / 5M SKUs |
|---|---:|---:|---:|
| Conversation LLM | $6.00 | $60.00 | $600.00 |
| Alert copy | $0.07 | $0.74 | $7.40 |
| Attribute extraction | $3.15 | $15.75 | $52.50 |
| Embeddings | $0.14 | $0.68 | $2.25 |
| Search / vector | $25 | $80 | $250 |
| App DB, storage, jobs | $25 | $70 | $220 |
| **Total / month** | **~$59** | **~$227** | **~$1,132** |
| **Per MAU** | $0.59 | $0.23 | $0.11 |

Two structural observations:

1. Extraction + embeddings never exceed ~5% of the bill. Optimising there is
   wasted effort.
2. At 10k MAU, conversation LLM is 53% of spend. **Hot-path model choice is the
   only cost lever that will ever matter.**

Images: hotlink retailer CDNs where affiliate terms permit; otherwise cache
thumbnails on Cloudflare R2 (zero egress — 5M thumbnails at 30 KB ≈ 150 GB ≈
$2.25/month). Never self-host image serving.

**Note what is missing from this table: WhatsApp.** At India's 2026 marketing
rate (₹0.8631 + 18% GST + BSP markup ≈ ₹1.09/message), 3 alerts/week costs
~₹160/user/year — which at 10k MAU is roughly **₹1.6M/year, an order of
magnitude above all the infrastructure above combined**. Messaging, not compute,
is the dominant variable cost of this product. See [ROADMAP.md](ROADMAP.md) §
Phase 2.

---

## 9. Screenshot-to-shop

Architecturally free: the same Marqo-FashionSigLIP image tower embeds a query
screenshot into the same space as catalogue images. One extra endpoint over the
existing index, no new stack.

The catch is that its hardest case is where open models are weakest — LookBench's
"real street-look" subset (user-shot, cluttered, non-studio imagery, i.e.
precisely what a screenshot is) is the lowest-scoring subset, with the best
proprietary model at 62.4% and open Marqo models around 57%. A **detection/crop
step** — isolate the garment before embedding, as Pinterest's published
architecture does — matters more here than model choice.

Scale evidence that the behaviour is real: Google Lens handles ~20B monthly
queries; Pinterest Lens ~600M visual searches per month.

---

## 10. Stack summary

| Layer | Choice | Change when |
|---|---|---|
| Catalogue source | Shopify/D2C feeds | Marketplace feed access is confirmed in writing |
| Store | Postgres + pgvector | p95 filtered query >300 ms, or >5M vectors |
| Retrieval | BM25 + vector, RRF fusion | Golden-set NDCG plateaus below target |
| Embeddings | Marqo-FashionSigLIP, self-hosted | A fashion-tuned model beats it on LookBench |
| Hot-path LLM | Gemini 2.5 Flash-Lite | Eval regression, or conversion economics change |
| Reasoning LLM | One tier up, rendered items only | — |
| Enrichment | Batch VLM, category-gated schema | — |
| Persona | Deterministic weighted scoring | >10k labelled positives/segment/month |
| Alerts | Rules + hard relevance threshold | — |
| Auth | Managed phone OTP | Never hand-roll |
| Affiliate | Aggregator API (Cuelinks-class) | Direct merchant relationships exist |
