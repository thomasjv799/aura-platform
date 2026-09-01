# Aura — Build Plan: PoC → MVP → Product

**Status:** pre-code. This plan supersedes the timeline in the July 2026 pitch.
Written 1 September 2026. Evidence for every claim: [RESEARCH.md](RESEARCH.md).

---

## What changed from the pitch, and why

Seven premises in the initial pitch do not survive research. They are corrected
here before they anchor a plan or a fundraise.

| Pitch premise | Reality | Consequence |
|---|---|---|
| "MVP in 8–12 weeks" | The four-pillar MVP is **45–85 person-weeks**. 8–12 weeks buys 15–35% of it for two people. | Timeline rebuilt as five gated phases, **~21 weeks P50 / ~30 weeks P80** |
| Catalogue access is the hard part | **Shopify's Global Catalog MCP is free, unauthenticated and live.** 443 Indian haldi-kurta results in INR, with sizes, stock and deep links. Approval was removed 17 Jun 2026. | Catalogue is a **one-day task**. It has been deleted from the roadmap as a milestone |
| Affiliate commission monetises the catalogue | Of 69 Indian D2C sellers sampled from that catalogue, **2 (2.9%)** had an affiliate programme; 8 (11%) on the most generous test. | **Affiliate coverage replaces catalogue as the Phase 1 gate** |
| "4–10% commission" | Cuelinks' real Myntra rate is **7.5% new / 3.75% existing**. Aura's users are *by definition* existing Myntra customers. | Blended net rate modelled at **5.0%**, not 8% |
| Proactive WhatsApp alerts are the retention hook | 100 templates cost ₹109 and return **₹4.70–₹21.30**. Break-even needs an EPC of ₹10.90 — **23× the base case**. | **WhatsApp broadcast is dead.** Push is free and has better retention evidence |
| Amazon PA-API qualification is a milestone | PA-API 5.0 was **retired 15 May 2026**; its replacement needs ~10 qualified sales in a rolling 30 days — *traffic before access*. | Amazon removed from the critical path |
| We are first to this wedge | **Daydream** ($50M, 8,500 brands) reached ~1.5M uniques in a year, then went B2B. **Alle** — India-first, ex-Meesho, Elevation-backed — shut down Jan 2026 after six pivots. | The plan opens with both, in falsifiable terms |

---

## The central tension

> **Supply and monetisation are two disjoint sets, and the free one is the wrong
> one.**

The route that makes Aura demoable — Shopify's free Global Catalog, which already
ships occasion metadata (*"Suitable for haldi, mehendi, and other traditional
events"* came back verbatim in a live probe) — is the route where **~90–97% of
sellers have no affiliate programme at all**.

The merchants that *do* pay — Myntra, Ajio, Amazon.in — publish no product feed,
force sub-network access, run **1-day cookies** against a **10-day** median
click-to-sale, pay commission only on **delivered** GMV (~30% evaporates to
returns and RTO), settle cash **4–5.5 months** later, and apply the
**existing-customer tier** to an audience that already has their apps installed.

Every incentive in the build — the free API, the good demo, the pretty long-tail
brands, the haldi tags already written for you — pulls the team toward the
unmonetisable half.

**So the ordering principle for this entire plan is inverted.** Do not start from
*"what catalogue can I get?"* — the answer is "almost all of it, free, today."
Start from **"which merchants will actually pay me?"** That list defines the
business. Anything that widens catalogue without widening affiliate coverage is
negative-value work.

---

## How to read this timeline

Ranges with stated confidence, not dates. Grounded in three findings:

- **Cone of Uncertainty.** At "Initial Concept" the defensible range is
  **0.25×–4×**. It narrows as *decisions close options*, not as weeks pass. That
  is what the gates are for.
- **The planning fallacy is worse than intuition suggests.** In the canonical
  study, subjects' *worst-case* estimates (48.6 days) still fell short of actual
  (55.5). **Plan around the P80.**
- **IT overruns are fat-tailed** — 27% average, one in six at 200%. Padding cannot
  cover that. The fix is **structural de-scoping and kill gates**.

Every phase states: duration (P50/P80) · **Entry** · **Gate** · **Signal**
(falsifiable, with a threshold and a named measurer) · **Must/Won't** · **Kill**.

**Fix the date, float the scope. Never both.**

### Capacity

Two people, counting *effective* engineering time — a founder also doing
partnerships, support and fundraising supplies ~3.0–3.5 focused days a week.

| Team | PoC start → MVP gate |
|---|---|
| 1 person | 26–40 weeks |
| **2 people (planned)** | **17–26 weeks (P50), ~30 weeks (P80)** |
| 3 people | 14–22 weeks, with a coordination tax |

AI assistance is modelled at **0–20% on code-typing and ~0% on judgement-heavy
work** — ontology design, relevance tuning, feed reconciliation — which is most of
this build. Published evidence brackets the effect between −19% (METR) and +21%
(Google), and DORA 2025 found AI raises throughput *and* instability, so rework
capacity is budgeted rather than netted against zero.

---

## Phase 0 — Foundation, dependency ignition, and falsification

**2–3 weeks elapsed · ~0 engineering · runs in parallel with everything else**

### 0a. Start five external clocks by day 14

None can be compressed by working harder.

| Clock | Elapsed | Gates |
|---|---|---|
| SPICe+ incorporation | 10–15 working days | Affiliate payouts |
| GST registration | 3–5 working days (30 if physical verification) | Invoicing networks |
| **Affiliate network signup + per-merchant campaign approval** | **2–8 weeks** | **Everything** |
| Google Play **organisation** account | Avoids the hard 12-testers-for-14-continuous-days wall on personal accounts | Phase 4 |
| Apple Developer Program | ~24h review once enrolled | Phase 4 |

Sign up to **all six** sub-networks, not three: Cuelinks, EarnKaro, ExtraPe,
Admitad India, vCommission, INRDeals.

*Meta Business Verification has been removed from this list — see Phase 3.*

**Gate: CLOCK STARTED.** All submitted with dated reference numbers by day 14.
**Kill:** none — pure option value.

### 0b. Falsify the thesis before building anything

Four experiments. Each can kill or sharpen the company in under two weeks.

**1. Enumerate the monetisable catalogue.** Open publisher accounts on Cuelinks +
Admitad India + INRDeals and list *every* India fashion advertiser with an active
programme. **That list — call it N — is the real total addressable catalogue.**
Not the 47,000 Indian fashion Shopify stores. Not the Global Catalog. N.

> This is now the **single most important unknown in the project**. Admitad
> India's feed page renders "Advertisers found: 200", but how many are Indian
> *and* fashion cannot be determined without an account.

**2. Twenty occasion queries against every incumbent.** Run the same twenty real
prompts ("cousin's haldi, not yellow, under ₹3,000, size M") against Myntra Maya,
Flipkart SLAP, Amazon Rufus India, Meesho Vaani and Glance AI. Record and grade
every output.

> This remains the load-bearing claim of the thesis, and it is now **harder**:
> Shopify already ships occasion tags as free metadata. The question is no longer
> "does anyone do occasion reasoning" but "is Aura's occasion reasoning better
> than a free field plus a good retriever." If it isn't, there is no product.

**3. Get a real rate card in writing.** Confirm from inside a logged-in dashboard:
whether Cuelinks' displayed rates are gross or net of the 75:25 revshare (a 25%
swing), apparel category caps, new-vs-repeat tiers, and — critically — **whether
network terms permit an AI agent to ingest and re-present merchant catalogue data
at all.** No public policy exists either way. It is binary.

**4. Call the founders of Alle.** Reachable ex-Meesho operators in Bengaluru who
ran this exact play with $3M and shut it down after six pivots. One conversation
is worth more than every hour of desk research behind this document.

**Gate: THESIS SURVIVES.** N ≥ 20 monetisable fashion merchants · occasion gap
confirmed by hands-on comparison · written net rate ≥4% · no terms prohibiting
agent use.
**Kill:** any one fails → **stop and re-scope before writing code.**

---

## Phase 1 — PoC: can we recommend things we get paid for?

**4–6 weeks (P50 5, P80 7)**

One occasion vertical (wedding-guest womenswear), **hybrid search behind a CLI**.
No chat UI. No app. No alerts. No persona editor.

**Catalogue strategy — inverted from the pitch.** Three routes, used for three
different jobs:

| Route | Job | Why |
|---|---|---|
| **Affiliate network feeds** (route 3) | **Defines the business** | The only route where a SKU arrives with a way to get paid for it |
| **Per-store `/products.json`** (route 2) | The working index | Free, full depth, own refresh cadence, `available` per variant, robots.txt-permitted — **but only for merchants from route 3** |
| **Shopify Global Catalog MCP** (route 1) | Breadth and demos only | Free and instant, but ~97% unmonetisable — **instrument separately, never mix into a demo metric** |

For **Myntra, Ajio and Amazon.in** — programmes but no feed — do *not* build a
catalogue. Use them as **link targets only**, resolved at conversation time from
stated intent via search deep links wrapped in an affiliate link.

**Dropped entirely:** ONDC (₹5–25 lakh, 3–5 months, orders falling 6.5M→4.6M/month,
and buyer apps earn a seller-side finder fee — which would make Aura a
marketplace, contradicting the thesis). Scraping Myntra/Ajio (~$3,000 per 1M-SKU
refresh, 0.3–0.5 FTE forever, and **OLX v. Padawan** saw the Delhi High Court grant
a permanent injunction against exactly this). Commercial vendors (42Signals caps
at 200 SKUs; Bright Data is ₹2.2 lakh per 1M against a free alternative).

**Entry:** Phase 0 gates passed · **a 100-query golden set written by a human
stylist exists.** Non-negotiable — relevance tuning has an unbounded tail without
one.

**Gate: COVERAGE + RELEVANCE.** Both, or neither counts.

**Signal:**
- **≥20 merchants with a live programme and a confirmed ₹1 test payout** —
  end-to-end, money actually received, not just a link generated
- **≥40% of recommendations shown carry a live affiliate link** *(track this as a
  first-class metric from day one; below 40% the product is a hobby)*
- Top-5 contains a human-judged *"would actually wear to this"* item for **≥60%**
  of held-out golden queries, scored by a rater who did not write the retrieval code
- Precision@5 **≥0.4**; enrichment agreement ≥80% occasion, ≥85% category

**Must:** ingestion + normalisation · category-gated attribute enrichment · hybrid
BM25+vector with RRF · hard filters · occasion ontology v1 as structured data ·
offline eval harness · **affiliate link generation and click logging**.
**Won't:** chat, persona editor, alerts, boards, mobile, auth.

**Kill:** fewer than 20 monetisable merchants by week 6 → the affiliate model is
disconfirmed and the business needs a different revenue line. Or top-5 hit rate
<40% → the retrieval thesis is wrong; re-scope to curation-led.

---

## Phase 2 — Pilot: does anyone want this, and will they buy today?

**3–5 weeks (P50 4, P80 6)**

The pitch's "Step 0 manual pilot", kept and strengthened. 20–40 hand-recruited
users, mobile web only.

Chat and the editable persona are real. Affiliate links are real and tracked.
**Proactive contact is sent by a human**, using the scoring model only as a
suggestion — the point is to falsify the retention hook **before** building a
notification platform.

### The 1-day cookie problem is a product problem, and this is where it surfaces

All three major merchants run **1-day cookies**. Industry median click-to-sale is
**10 days**. Occasion-wear at ₹3,000–₹20,000 involves browsing, comparison and
family consultation.

> **Aura only gets paid on same-day conversions.** Anything that makes it a
> thoughtful advisor rather than an impulse trigger destroys its own revenue — and
> "save it and decide later" is the *natural* shape of occasion shopping. This may
> be structurally incompatible with affiliate monetisation, and Phase 2 is where
> that gets measured rather than assumed.

### The retention reframe worth testing

Trend alerts are a commodity. **The occasion calendar is not.** Indian fashion
demand is calendar-driven and forward-dated: a user mentions a cousin's wedding in
November, and that is a legitimate reason to make contact in September, October
and November. Event-triggered rather than budget-triggered, and relevance comes
from the user's own calendar rather than a messaging allowance.

**Instrument: do users volunteer future occasions unprompted?** That single
behaviour separates a search tool from an agent.

**Entry:** Coverage + relevance gate passed · consent copy written.

**Gate: DESIRE.**

**Signal:**
- **≥8% retailer click-through** on hand-sent, persona-matched contact
- **≥30% of users edit their persona** unprompted at least once
- **≥40% volunteer a future occasion** unprompted *(the calendar hypothesis)*
- **≥1 conversion verified end-to-end in the network's own reporting** — proves
  the money pipe, not just the click
- **Same-day conversion share measured and reported** *(no threshold — this is the
  number that tells us whether the cookie window is survivable)*

**Kill:** CTR <3% after four weeks and two content iterations → the proactive
pillar is falsified; Aura is a search tool and this plan is rewritten. Or **zero
conversions reconcile after 200+ clicks** → attribution or the cookie window makes
the model unviable regardless of product quality.

> Thresholds borrowed from general messaging benchmarks, not from a comparable
> Indian fashion product. Recalibrate before treating them as kill criteria.

---

## Phase 3 — Private beta: automate what the human did

**6–9 weeks (P50 7, P80 10)** · 150–500 users

**Must:** relevance-gated alert scoring · frequency caps · quiet hours ·
cross-week dedup · **consent ledger** · unsubscribe · boards · managed phone-OTP
auth · admin and curation console · **eval harness wired into CI as a merge gate**.

### The channel decision is already made: push, not WhatsApp

At **₹1.09 all-in** per delivered marketing template, against a modelled
**EPC of ₹0.47** (base) to ₹1.42 (optimistic):

```
Per 100 marketing templates sent:
  cost                          100 × ₹1.09  = ₹109.00
  revenue @ 10% CTR, base       10 × ₹0.47   =   ₹4.70   →  4.3% recovered
  revenue @ 15% CTR, optimistic 15 × ₹1.42   =  ₹21.30   → 19.5% recovered
```

**Aura loses 80–96% on every WhatsApp broadcast.** Break-even at 10% CTR needs an
EPC of **₹10.90 — 23× base, 7.7× optimistic.** No combination of India fashion AOV
and commission rate reaches it.

**Push notifications are free.** Personalised push shows ~4× open-rate lift, and
lifecycle-triggered push is credited with up to +190% 90-day retention. WhatsApp
is defensible only for **service-window messages or a paying cohort** — never for
recommendation broadcasts to the general base. This is why Meta verification was
cut from Phase 0.

**Entry:** Desire gate passed · Play closed test already running if Android is in
scope.

**Gate: RETENTION.**

**Signal:** ≥25% of the cohort still opening at least one notification in week 4 ·
≥1.5 sessions/user/week · unsubscribe <5%/month · automated link-health probe
≥97% deep-link validity, ≤1 catalogue incident/week.

**Kill:** week-4 retention <12%, or unsubscribe >12%/month, or link validity <90%.
The last matters more than it looks — **no amount of model quality compensates for
sending users to dead or out-of-stock links.**

---

## Phase 4 — MVP: public launch

**4–6 weeks (P50 5, P80 7)**

App-store submission · catalogue scaled across all N monetisable merchants ·
onboarding · support flow · DPDP consent and deletion · cost controls · on-call.

**Entry:** Retention gate passed · app-store lead time burned down · all merchant
approvals in hand.

**Gate: UNIT ECONOMICS.**

**Signal:** attributed GMV per active user per month **≥3× fully-loaded inference +
messaging cost**, computed on **reconciled commission receipts — not projections**
— with **≥100 reconciled conversions**.

**Kill:** commission per active user below cost after six weeks → cut alert
frequency and re-gate rather than scaling a negative-margin loop.

### What the numbers actually say

| | Base | Optimistic |
|---|---:|---:|
| EPC | ₹0.47 | ₹1.42 |
| Revenue / MAU / month | **₹0.21** | **₹1.42** |
| Revenue per converting user | ₹90 (range ₹68–₹187) | — |
| **Break-even MAU, founders unpaid** (₹40k/mo burn) | **190,000** | **28,000** |
| Break-even MAU, ₹1L salaries (₹2.5L/mo) | 1,190,000 | 176,000 |

Global average affiliate EPC is ~₹40. **Aura's modelled EPC is ~1% of that** — not
an error; the global figure is dominated by finance, travel and SaaS.

At ~2% day-30 retention, *holding* 190,000 MAU implies acquiring on the order of
**9.5 million installs**. Even the most favourable cell needs **28,000 monthly
actives** — 12–24 months of organic growth, self-financed, with cash arriving
**4–6 months in arrears**.

**Set the first revenue gate at ₹1,000 ≈ 11–15 delivered, attributed orders.** Not
a hard number. Time-box it: **if 20 monetisable merchants and 90 days of real
usage do not produce 15 paid orders, the affiliate model is disconfirmed** and the
business needs a different revenue line — merchant SaaS, sponsored placement, or
lead-gen.

---

## Phase 5 — Product: find a channel that repeats

**Open-ended · first review at 8–12 weeks**

**Distribution is the primary risk, not product quality.** Meesho reached 1.5M
users in one month with an in-app feature. Daydream reached 1.5M in a year with
$50M and a good product. Paid acquisition is impossible here — not merely
expensive: revenue lands 4–6 months after the click, so every acquisition rupee is
financed out of pocket for half a year.

**Organic or nothing.** Candidates, to be tested with real CAC:

- **Occasion-adjacent partnerships** — wedding invitation platforms, planners,
  bridal creators. The user has already declared the occasion; highest-intent
  moment in the funnel.
- **Screenshot-to-shop sharing** — architecturally free, inherently shareable.
- **SEO on occasion queries** — "what to wear to a haldi" is durable and
  under-served.
- **WhatsApp *organic* forwarding** — free, unlike broadcast. Forwarding a look to
  a friend is native Indian behaviour.

**Exit:** a repeatable channel with **CAC payback under 6 months**.
**Kill:** no such channel after 12 weeks.

---

## Timeline summary

| Phase | P50 | P80 | Gate | Kill trigger |
|---|---:|---:|---|---|
| 0 · Foundation + falsification | 2–3 wk | 3 wk | Clocks started; thesis survives | N < 20 merchants, occasion gap absent, net rate <4%, or terms prohibit agents |
| 1 · PoC | 5 wk | 7 wk | Coverage + relevance | <20 monetisable merchants, or top-5 hit <40% |
| 2 · Pilot | 4 wk | 6 wk | Desire | CTR <3%, or 0 conversions in 200+ clicks |
| 3 · Private beta | 7 wk | 10 wk | Retention | Wk-4 retention <12%, unsub >12%/mo, link validity <90% |
| 4 · MVP | 5 wk | 7 wk | Unit economics | <15 paid orders in 90 days at 20 merchants |
| **PoC start → MVP gate** | **~21 wk** | **~30 wk** | | |
| 5 · Product | open | | Repeatable CAC | No channel with <6mo payback in 12 wk |

**Indicative calendar** (two people, Phase 0 from September 2026): MVP gate lands
**February 2027 at P50, April 2027 at P80** — uncomfortably close to **13 May 2027,
the DPDP full compliance deadline.** That is why the consent ledger is a Phase 3
*Must* and a day-one schema decision.

---

## Scope discipline

Cut lines are agreed **before** each phase starts. Flyvbjerg's finding is that
per-task padding cannot cover a fat-tailed distribution and Parkinson's Law
consumes it anyway; only structural cuts work.

**Never building:** checkout · payments · inventory · logistics · virtual try-on ·
a social network · order tracking.

This is no longer a compromise. **OpenAI retired in-chat Instant Checkout on
24 March 2026** after Walmart measured it converting ~3× *worse* than
click-through. And Shopify's 2026 default `robots.txt` — which explicitly permits
catalogue crawling — forbids exactly one thing: *"Checkouts are for humans. Do NOT
complete checkout, payment, or order placement automatically."* **Aura is, by
construction, inside the permitted envelope.**

**Not building yet:** screenshot-to-shop (Phase 5) · outfit completion · gifting
and budget modes · weekly digest · multi-vertical expansion · ACP/UCP integration
(neither has reached India; monitor monthly).

---

## The escape hatch, designed in from day one

Both prior attempts exited sideways: **The Yes** to a technology/team acquisition
($87.6M), **Daydream** to white-label search for brands. Neither was a consumer
outcome.

If the **occasion-intelligence corpus is built as a clean, separable service** —
versioned structured data with provenance, not prompt logic buried in the app —
the same corpus is licensable to Myntra, Ajio, Tata CLiQ or Nykaa for their
festive and wedding seasons.

**It costs nothing extra if the architecture is right from the start.** Build it
that way. Do not build *for* it.

---

## What would make this plan wrong

1. **The occasion gap may not exist — and the bar just rose.** Shopify already
   ships occasion tags as free metadata. Aura must beat "free field + good
   retriever", not "nothing".
2. **Affiliate terms may prohibit agent use outright.** No public policy either
   way. Binary, and unresolved.
3. **The 50% attribution-survival estimate has no published India source** and
   swings revenue 2×. Only measurable by pushing ~1,000 real clicks through a
   network and reconciling.
4. **"Save it and decide later" may be incompatible with 1-day cookies.** A
   product-form question, and possibly existential.
5. **Break-even may be out of reach.** 28,000 MAU is the optimistic floor; 190,000
   is the base case. Neither is obviously achievable organically.
6. **Shopify could meter the Global Catalog**, or ship promoted placements that
   collapse routes 1 and 3 into one. The second would change these economics
   fundamentally, in Aura's favour — **the highest-leverage external event to
   monitor.**
