# Aura

**A shopper-side AI agent for India's occasion-driven fashion market.**

Aura learns a persistent, editable style persona — colours, fits, brands, budget
bands, per-brand sizing — and understands what an Indian occasion actually
implies. Ask it for something to wear to your cousin's haldi and it reasons about
daytime, festive, photo-heavy, turmeric-friendly, and the fact that everyone else
will be in yellow. Then it hands you off to the retailer's own site to buy.

🧭 **Occasion intelligence, not keyword search** • 🇮🇳 **India-first** •
✏️ **A persona you can see and edit** • 🔗 **Affiliate handoff — no checkout, no inventory**

> **Status: pre-code.** This repository currently holds the plan, the evidence
> behind it, and the architecture it implies. Nothing is built yet. That is
> deliberate — [four experiments](docs/ROADMAP.md#0b-falsify-the-thesis-before-building-anything)
> could still kill this thesis, and they cost two weeks instead of two quarters.

---

## Start here

| Document | What it is |
|---|---|
| **[docs/ROADMAP.md](docs/ROADMAP.md)** | The build plan — five gated phases from PoC to product, with durations, falsifiable success signals and explicit kill criteria |
| **[docs/RESEARCH.md](docs/RESEARCH.md)** | The evidence base. Every load-bearing claim, with confidence tags and sources |
| **[docs/ARCHITECTURE.md](docs/ARCHITECTURE.md)** | The recommended stack, priced, with the measurable trigger to change each choice |

---

## The thesis

Online shopping is a search problem pretending to be a personal one. Shoppers
think in occasions and moods — *"something for my cousin's haldi, not yellow,
under ₹3,000"* — but stores understand categories and keywords. Preferences don't
travel: Amazon knows one slice of you, Myntra another, a D2C brand nothing at all.

Consumer behaviour has already moved. **AI-referred retail traffic converted 42%
better than non-AI traffic in March 2026** — a channel that converted *38% worse*
twelve months earlier. **India is the world's most receptive market** for this:
62% of Indian consumers actively use GenAI versus 42% in the US, and 60% say they
want a personal AI agent, the highest in Asia-Pacific.

The interface war is being fought by giants. **The occasion-reasoning layer is
not.**

---

## The honest position

Two companies have run close to this exact play. Both failed. A plan that doesn't
open with that isn't a plan.

**Daydream** — $50M seed, 8,500 brands, founded by the former COO of Stitch Fix —
launched June 2025 and drew roughly **1.5 million unique visitors in its entire
first year**. Thirteen months in, it launched a B2B white-label product for
brands. Its business model was identical to this one.

**Alle** — India-first conversational AI stylist, 1,000+ curated brands, founded
by three ex-Meesho executives, backed by Elevation Capital — **shut down in
January 2026** after six pivots. The founder's stated reason was not execution or
capital; it was that they could never find a large enough opportunity.

Meanwhile the incumbents are not asleep. Flipkart shipped **SLAP**, a standalone
conversational shopping app that ingests Instagram Reel links, in January 2026.
Meesho's **Vaani** reached **1.5M users in its first month** with 22% higher
conversion — the number Daydream took a year and $50M to reach. Amazon's shopping
assistant already ships proactive price-drop alerts and target-price auto-buy,
and has 10M+ Indian users.

**So what is actually defensible here?**

Not "India-first" — Flipkart, Myntra, Meesho, Nykaa and Amazon India are all
India-first by construction, with catalogue, transaction data and free
distribution. India-first buys real time against *Western* entrants, and that is a
head start measured in quarters.

Not "proactive alerts" — Amazon ships them already, and anyone can clone a
frequency cap in a sprint.

**Occasion intelligence is the one thing research supports as genuinely
unserved.** No Western agent reasons about haldi, sangeet or mehndi. Indian
incumbents treat occasion as seasonal merchandising, not as a reasoning layer.
Built properly — as a structured, versioned corpus mapping *ritual → dress code →
fabric → colour norms and taboos → region → time of day → budget band* — it is
the only asset in this product a competitor cannot clone in a sprint.

That claim is also **the least verified thing in this document**, which is why
testing it against every incumbent is the first task in the plan, before any code.
And the bar just rose: Shopify's free catalogue API already returns
*"Suitable for haldi, mehendi, and other traditional events"* as vendor metadata.
Aura has to beat a free field plus a good retriever — not nothing.

---

## The central tension

> **Supply and monetisation are two disjoint sets, and the free one is the wrong
> one.**

Getting product data turned out to be trivial. Shopify's Global Catalog MCP is
open and unauthenticated — a live probe returned 443 Indian haldi-appropriate
kurta sets in INR with sizes, stock and deep links, no API key, no approval, no
fee. Integration is under a developer-day.

But of 69 Indian D2C sellers sampled from that catalogue, **2 had an affiliate
programme.** Eight on the most generous test. Meanwhile the merchants that *do*
pay — Myntra, Ajio, Amazon.in — publish no product feed at all.

So the failure mode isn't technical and isn't legal. **It's that Aura will
recommend, beautifully and correctly, from a catalogue it has no affiliate link
for** — and every incentive in the build pulls that way, because the free API is
also the fun one with the pretty long-tail brands and the occasion tags already
written for you.

This is why the plan inverts the usual order. Not *"what catalogue can I get?"* —
the answer is "almost all of it, free, today." Instead: **"which merchants will
actually pay me?"** That list is the business. Everything else is index.

---

## What we're building

Four pillars, reordered by what the evidence says actually matters.

**1 · Occasion intelligence — the product.** A structured cultural corpus, not
prompt text. Ritual, dress code, fabric norms, colour taboos, regional variation,
formality, time of day, budget band. Testable, reviewable by a human stylist, and
separable from the app.

**2 · The persona engine — the switching cost.** A visible, editable style
profile built from three signal sources: explicit (a short onboarding quiz),
conversational (every message refines it), and behavioural (saves, dismissals,
click-throughs). Users can see and correct it — which builds trust, improves the
data, and makes the system legible in a way a learned policy never is.

**3 · Conversational discovery with grounded answers.** Natural language across
the catalogue, one-tap refinements, and an explicit *"why this?"* on every
recommendation. The model never sees a price — it emits a product ID and prose,
and the client renders price and stock from the feed row. It is
[structurally incapable](docs/ARCHITECTURE.md#4-grounding-the-llm-must-be-structurally-unable-to-state-a-price)
of inventing a discount.

**4 · Saved boards and affiliate handoff.** Collections that double as the
monetisation surface. Purchase completes on the retailer's own site.

### The retention question, reframed

The pitch made proactive trend alerts the retention hook. The evidence doesn't
support it: shopping apps have **~2% day-30 retention**, 72% of shoppers delete a
retail app after one purchase, and Amazon already ships the feature.

The better mechanic is the **occasion calendar**. Indian fashion demand is
calendar-driven and forward-dated. When a user mentions a wedding in November,
that is a legitimate, welcome reason to make contact in September, October and
November — event-triggered rather than budget-triggered. It inverts the whole
notification-fatigue problem: relevance comes from the user's own calendar
instead of from a messaging allowance.

Whether users volunteer future occasions unprompted is
[a measured Phase 2 gate](docs/ROADMAP.md#phase-2--pilot-does-anyone-want-this-and-will-they-buy-today).

---

## What we're deliberately not building

Checkout · payments · inventory · logistics · virtual try-on · a social network ·
order tracking and store support.

This is no longer a scoping compromise. **OpenAI retired in-chat Instant Checkout
on 24 March 2026** after Walmart measured checkout inside ChatGPT converting
**~3× worse** than a click-through to walmart.com. The market consolidated on
*"discover in AI, buy on site."* Aura's architecture is the one the industry
converged on.

---

## Architecture at a glance

```
merchant feeds ──► normalise ──► enrich (category-gated VLM) ──► index
                                                                   │
  persona (editable, consent-ledgered) ──┐                         │
                                          ▼                        ▼
              occasion ontology ──► retrieval: BM25 + vector, RRF fusion
                                          │
                                          ▼
                          rank ──► reason ──► render (price from feed, never from the model)
                                          │
                                          ▼
                              affiliate deep link ──► retailer's own site
```

The whole design is constrained by one number: **at ₹2,000 AOV and 6% net
commission, a conversation grosses about 4.5 US cents.** A frontier model on the
hot path costs more than the commission it earns. That is an arithmetic
constraint on the architecture, not a preference — so models are tiered, and the
catalogue-side AI (which is nearly free) does the heavy lifting offline.

| Layer | Choice |
|---|---|
| Catalogue | `/products.json` for merchants that pay; Shopify Global Catalog MCP for breadth |
| Store | Postgres + pgvector |
| Retrieval | Hybrid BM25 + vector, RRF fusion |
| Embeddings | Marqo-FashionSigLIP, self-hosted (~20 pts over generic CLIP on LookBench) |
| Hot-path LLM | Smallest model that passes eval |
| Persona | Deterministic weighted scoring — not bandits, until the feedback volume justifies them |
| Alert transport | Push. **Never WhatsApp broadcast** — it loses 80–96% per send |

Infrastructure runs ~$59/month at 100 MAU and ~$1,132 at 10k — which is not the
binding cost. **Reach is.** At ₹1.09 per WhatsApp marketing template against a
modelled EPC of ₹0.47, 100 sends cost ₹109 and return ₹4.70. Push is free.

Full detail and every price: [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md).

---

## Roadmap at a glance

| Phase | P50 | Gate | Kills it |
|---|---:|---|---|
| **0 · Foundation + falsification** | 2–3 wk | Clocks started; thesis survives | Fewer than 20 monetisable merchants, incumbents already handle occasions, net commission <4%, or affiliate terms prohibit AI agents |
| **1 · PoC** | 5 wk | Coverage + relevance — ≥20 merchants with a confirmed ₹1 test payout, ≥40% of results carrying a live affiliate link, top-5 hit ≥60% | <20 monetisable merchants, or top-5 hit <40% |
| **2 · Pilot** | 4 wk | Desire — ≥8% CTR on hand-sent contact, ≥1 reconciled conversion | CTR <3%, or 0 conversions in 200+ clicks |
| **3 · Private beta** | 7 wk | Retention — ≥25% still opening notifications at week 4 | Week-4 retention <12%, or link validity <90% |
| **4 · MVP** | 5 wk | Unit economics — attributed GMV ≥3× inference + messaging cost, on reconciled receipts | <15 paid orders in 90 days across 20 merchants |
| **5 · Product** | open | A repeatable channel with CAC payback <6 months | No such channel in 12 weeks |

**PoC start → MVP gate: ~21 weeks at P50, ~30 at P80, for two people.**

Not 8–12 weeks. The four-pillar MVP is 45–85 person-weeks of build, and 8–12
weeks buys 15–35% of it at this team size. The published evidence on AI-assisted
development brackets the speedup between −19% and +21% depending on context, so
this plan models **0–20% on code-typing and ~0% on the judgement-heavy work** that
dominates the build.

Every phase has a named gate, a falsifiable signal with a threshold and a
measurer, and a kill trigger. That structure is the point:
[Gartner expects >40% of agentic AI projects to be cancelled by end-2027](docs/RESEARCH.md#5-delivery-reality--what-812-weeks-to-mvp-actually-buys),
and Alle's failure was not running out of money — it was six pivots without a
falsifiable gate.

Full plan: [docs/ROADMAP.md](docs/ROADMAP.md).

---

## Business model — and the hardest number in this repo

Affiliate commission. Asset-light, the same model Daydream validated, and the same
one that has not yet produced a consumer breakout.

The economics are worse than the pitch assumed, in four compounding ways:

| | |
|---|---|
| **Rate** | Cuelinks' real Myntra rate is **7.5% new / 3.75% existing**. Aura's user is *by definition* an existing Myntra customer. Blended net: **5.0%** |
| **Cookie** | **1 day** on Myntra, Ajio and Amazon.in — against a **10-day** median click-to-sale |
| **Returns** | Commission is paid on **delivered**, not ordered, GMV. At 25–40% fashion returns and 23% RTO, **~30% evaporates** |
| **Cash** | Lands **4–5.5 months** after the sale |

Which produces:

```
EPC                       ₹0.47 (base)  →  ₹1.42 (optimistic)
Revenue / MAU / month     ₹0.21         →  ₹1.42
Break-even, founders unpaid   190,000 MAU  →  28,000 MAU
```

Global average affiliate EPC is ~₹40. **Aura's is about 1% of that** — not an
error; the global figure is dominated by finance, travel and SaaS. India fashion
at ₹1,800 AOV cannot produce a dollar-scale EPC.

**First revenue gate: ₹1,000 ≈ 11–15 delivered, attributed orders.** Time-boxed —
if 20 monetisable merchants and 90 days of real usage don't produce 15 paid
orders, the affiliate model is disconfirmed and the revenue line has to change.

**North-star metric:** percentage of weekly active users who engage with a
proactive, persona-matched contact and click through to a retailer.

**Guardrail metric, tracked from day one:** *percentage of recommendations shown
that carry a live affiliate link.* Below 40%, this is a hobby.

---

## Repository layout

```
aura-platform/
├── README.md              you are here
└── docs/
    ├── ROADMAP.md         PoC → MVP → Product, gates and kill criteria
    ├── RESEARCH.md        evidence base, confidence-tagged and sourced
    └── ARCHITECTURE.md    stack, costs, and change triggers
```

---

## Open questions

The things that would most change this plan, ranked. None can be settled by more
desk research — each needs a conversation or an experiment.

1. **How many Indian fashion merchants actually run an affiliate programme?**
   Admitad India's feed page says "Advertisers found: 200" — how many are Indian
   *and* fashion is invisible without a publisher account. **This number sizes the
   business.**
2. **Do affiliate network terms permit an AI agent** to ingest and re-present
   merchant catalogue data? No public policy exists either way. It is binary.
3. **Does GoAffPro or UpPromote expose a publisher-side discovery API?** If one
   integration could enumerate and join hundreds of small Indian D2C programmes,
   affiliate coverage of the free catalogue goes from ~3% to something viable.
   **This would be the highest-value engineering task in the project.**
4. **What fraction of Indian affiliate clicks survive app-to-web attribution?**
   No public data exists. The 50% estimate in the model swings revenue 2×.
5. **How good are Myntra Maya, Flipkart SLAP and Rufus India at real occasion
   queries?** Twenty prompts, graded. Still the thesis.
6. **Is "save it and decide later" compatible with a 1-day cookie at all?** That
   is the natural shape of occasion shopping, and it may be structurally
   incompatible with getting paid.
7. **Why did Alle pivot six times?** The founders are reachable.
8. **When do Shopify "promoted placements" ship, and what do they pay?** Announced
   17 Jun 2026 as a *future* path for developers to earn on catalogue-driven
   sales. If it lands, it collapses the tension above — the single
   highest-leverage external event to watch.

---

<sub>Research current to 31 August 2026. Figures sourced from affiliate networks,
BSPs and martech vendors are marketing numbers and are flagged as such in
[docs/RESEARCH.md](docs/RESEARCH.md); re-verify against a real rate card before
using any of them in a financial model or an investor deck.</sub>
