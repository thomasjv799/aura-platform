# Aura — Build Plan: PoC → MVP → Product

**Status:** pre-code. This plan supersedes the timeline in the July 2026 pitch.
Written 1 September 2026. Evidence for every claim: [RESEARCH.md](RESEARCH.md).

---

## What changed from the pitch, and why

Six premises in the initial pitch do not survive research. They are corrected
here before they anchor a plan or a fundraise.

| Pitch premise | Reality | Consequence |
|---|---|---|
| "MVP in 8–12 weeks" | The four-pillar MVP is **45–85 person-weeks**. 8–12 weeks buys 15–35% of it for two people. | Timeline rebuilt as five gated phases, **17–26 weeks P50** |
| Proactive alerts are the retention hook | Amazon already ships price-drop alerts, target-price auto-buy and Scheduled Actions. Shopping apps have **~2% day-30 retention**. | Alerts demoted to a supporting feature. The **occasion calendar** becomes the retention mechanic |
| Affiliate networks give us catalogue access | Cuelinks has **33 endpoints and no SKU feed**. Myntra and Ajio have **no self-serve programme**. | Catalogue supply is the **Phase 1 kill criterion**, not an implementation detail |
| Amazon PA-API qualification is a milestone | PA-API 5.0 was **retired 15 May 2026**. Its replacement needs ~10 qualified sales in a rolling 30 days — *traffic before access*. | Amazon removed from the critical path entirely |
| "Amazon blocks AI crawlers and sued Perplexity" | The Ninth Circuit **vacated that injunction on 4 Aug 2026**. | Weakens the "incumbents lock everyone out" narrative; ToS risk remains for scraping |
| We are first to this wedge | **Daydream** ($50M, 8,500 brands) reached ~1.5M uniques in a year and went B2B at month 13. **Alle** (ex-Meesho, Elevation-backed, India-first, 1,000+ brands) shut down Jan 2026 after six pivots. | The plan must state what Aura does differently, in falsifiable terms, in Phase 0 |

**The reframe.** Occasion intelligence is not a feature of this product — it is
the product. It is the only differentiator the evidence supports as genuinely
unserved, and the only asset a competitor cannot clone in a sprint. Everything
else here is scaffolding around proving that one thing is real and that someone
will pay for it.

---

## How to read this timeline

The estimates below are ranges with stated confidence, not dates. That is a
deliberate choice grounded in three findings:

- **Cone of Uncertainty.** At "Initial Concept" — where this project sits — the
  defensible estimate range is **0.25× to 4×**. It narrows as *decisions close
  options*, not as weeks pass. That is what the gates are for.
- **The planning fallacy is worse than intuition suggests.** In the canonical
  study, subjects' *worst-case* estimates (48.6 days) still fell short of actual
  (55.5 days). **Plan around the P80, not the P50.**
- **IT overruns are fat-tailed** — 27% average, but one in six projects runs 200%
  over. Padding cannot cover that distribution. The fix is **structural
  de-scoping and kill gates**, which is why every phase below has both.

Every phase is stated in one format:

> **Phase N — Name.** Duration (P50 / P80). **Entry:** … **Gate:** … **Signal:**
> falsifiable metric, threshold, named measurer. **Must / Should / Won't.**
> **Kill:** trigger and consequence.

**Fix the date, float the scope. Never both.**

### Capacity assumption

Sizing assumes **two people**, and counts *effective* engineering time — a
founder also doing partnerships, support and fundraising supplies ~3.0–3.5
focused engineering days a week, not five.

| Team | PoC start → MVP gate |
|---|---|
| 1 person | 26–40 weeks |
| **2 people (planned)** | **17–26 weeks (P50), ~30 weeks (P80)** |
| 3 people | 14–22 weeks, with a coordination tax |

**AI assistance is modelled at 0–20% on code-typing and ~0% on judgement-heavy
work** — ontology design, relevance tuning, alert calibration, feed
reconciliation — which is most of this build. The published evidence brackets AI
speedup between −19% (METR) and +21% (Google), and DORA 2025 found AI raises
throughput *and* delivery instability, so rework capacity is budgeted explicitly
rather than netted against zero.

---

## Phase 0 — Foundation, dependency ignition, and falsification

**2–3 weeks elapsed · ~0 engineering · runs in parallel with everything else**

Two things happen here, and neither is code.

### 0a. Start six external clocks by day 14

None of these can be compressed by working harder. Every one of them gates a
later phase, and each has burned a startup that started it late.

| Clock | Elapsed time | Gates |
|---|---|---|
| SPICe+ incorporation | 10–15 working days | Affiliate payouts |
| GST registration | 3–5 working days (30 if physical verification) | Invoicing networks |
| Affiliate network signup + **per-merchant campaign approval** | 2–8 weeks | Everything |
| Meta Business Verification + WABA onboarding | 2–6 weeks, assume 1–2 template rejections | Phase 3 alerts |
| Google Play **organisation** account | Avoids the hard 12-testers-for-14-continuous-days wall on personal accounts | Phase 4 launch |
| Apple Developer Program | ~24h review once enrolled | Phase 4 launch |

**Gate: CLOCK STARTED.** All six submitted with dated reference numbers by day 14.
**Kill: none** — this is pure option value.

### 0b. Falsify the thesis before building anything

Three experiments, in priority order. Each can kill or sharpen the company in
under two weeks and costs almost nothing.

**1. Twenty occasion queries against every incumbent.** Run the same twenty real
occasion prompts ("cousin's haldi, not yellow, under ₹3,000, size M") against
Myntra Maya, Flipkart SLAP, Amazon Rufus India, Meesho Vaani and Glance AI.
Record and grade every output.

> This is the load-bearing claim of the entire thesis and it is the least
> verified. Desk research found no evidence these products reason *structurally*
> about Indian occasions — but absence of press coverage is not absence of
> capability. **If they handle it well, the wedge is gone and it is far better to
> learn that in week 1.** If they handle it badly, that comparison is the
> strongest slide the deck can have.

**2. Get a real affiliate rate card in writing.** Not a blog post. The headline
figures (Myntra 7.5–10%, Flipkart 1–15%, Amazon India fashion 4–9%) are
affiliate-network *marketing* numbers. Establish: net rate after revenue share,
apparel category caps, new-vs-repeat tiers, cookie window, app-to-web attribution
behaviour, whether commission is paid on ordered or **delivered** GMV — and
critically, **whether the network's terms permit an AI agent to ingest and
re-present merchant catalogue data at all.** An "AI agent" publisher type is a
category these networks have no precedent for.

**3. Call the founders of Alle.** They are reachable ex-Meesho operators in
Bengaluru who ran this exact play with $3M and shut it down after six pivots.
One conversation is worth more than every hour of desk research behind this
document.

**Gate: THESIS SURVIVES.** Occasion gap confirmed by hands-on comparison, *and* a
written net commission rate ≥4%, *and* no terms prohibiting agent use.
**Kill:** any of the three fails → **stop and re-scope before writing code.**

---

## Phase 1 — PoC: does retrieval actually work?

**4–6 weeks (P50 5, P80 7)**

Deliberately narrow: **one occasion vertical** (wedding-guest womenswear), **one
catalogue source**, 20–50k SKUs, enrichment on a 2,000-item sample, hybrid search
**behind a CLI**. No chat UI. No app. No alerts. No persona editor.

**Catalogue source: Shopify/D2C India fashion brands.** Sign 20–50 whose product
feeds can be pulled legitimately. This is the only clean, legal, structured,
free source a two-person team can obtain — and brand-direct commission is
materially better than marketplace rates. Treat it as **the wedge, not a
compromise**: the pitch's "one conversation across thousands of brands" is the
Phase 3 story, not the Phase 1 one.

**Entry:** Phase 0 gates passed, **and a 100-query golden set written by a human
stylist exists.** This is non-negotiable — relevance tuning has an unbounded tail
without one, and the eval harness is simultaneously the most-cut component and
the one whose absence causes the documented instability pattern.

**Gate: RELEVANCE.**

**Signal**, scored by a rater who did not write the retrieval code:
- Top-5 contains a human-judged *"would actually wear to this"* item for **≥60%**
  of held-out golden queries
- Precision@5 **≥0.4**
- Enrichment agreement with human labels **≥80% on occasion, ≥85% on category**

**Must:** ingestion + normalisation · category-gated attribute enrichment ·
hybrid BM25+vector with RRF · hard filters (size, price, stock) · the occasion
ontology v1 as structured data · offline eval harness.
**Won't:** chat, persona editor, alerts, boards, mobile, auth.

**Kill:** top-5 hit rate <40% at week 6 → the retrieval thesis is wrong; re-scope
to curation-led rather than search-led. Also kill if **no merchant feed is live
by week 6**.

---

## Phase 2 — Pilot: does anyone actually want this?

**3–5 weeks (P50 4, P80 6)**

This is the pitch's "Step 0 manual pilot", kept and strengthened. 20–40
hand-recruited users. Mobile web only, no app.

**Chat and the editable persona are real. Affiliate links are real and tracked.
Alerts are sent *by a human*,** using the scoring model only as a suggestion.

> The point of this phase is to **falsify the retention hook before building the
> notification platform.** Alert delivery is a platform — frequency capping,
> quiet hours, cross-week dedup, consent ledger, unsubscribe, template lifecycle,
> deliverability monitoring — and it is the single most under-scoped item in the
> original plan. Do not build it to discover nobody opens the alerts.

### The retention reframe worth testing here

Trend alerts are a commodity. **The occasion calendar is not.** Indian fashion
demand is calendar-driven and forward-dated: a user mentions a cousin's wedding
in November, and that is a legitimate, welcome reason to make contact in
September, October and November. It is event-triggered rather than
budget-triggered, and it inverts the frequency-cap problem — relevance comes from
the user's own calendar, not from a notification allowance.

**Instrument specifically: do users volunteer future occasions unprompted?**
That single behaviour is the difference between a search tool and an agent.

**Entry:** Relevance gate passed · ≥2 merchants live with tracked links · consent
copy written.

**Gate: DESIRE.**

**Signal:**
- **≥35% open rate** and **≥8% retailer click-through** on manually-sent,
  persona-matched alerts
- **≥30% of users edit their persona** unprompted at least once
- **≥1 conversion verified end-to-end in the network's own reporting** — this
  proves the money pipe, not just the click
- **≥40% of users volunteer a future occasion** unprompted *(the calendar
  hypothesis)*

**Kill:** alert CTR <3% after four weeks and two content iterations → pillar 3 is
falsified; Aura is a search tool, not an agent, and this plan is rewritten. Also
kill if **zero conversions reconcile after 200+ clicks** — that means attribution
or the cookie window makes the model unviable regardless of product quality.

> **Note on thresholds.** The 35%/8% figures come from general messaging
> benchmarks, not from a comparable Indian fashion product. Recalibrate them
> against a real reference class before treating them as kill criteria.

---

## Phase 3 — Private beta: automate what the human did

**6–9 weeks (P50 7, P80 10)**

150–500 users. Automate Phase 2's manual work and add the machinery a real
product needs.

**Must:** alert scoring with a hard relevance threshold · frequency caps · quiet
hours · cross-week dedup · **consent ledger** · unsubscribe · boards · managed
phone-OTP auth · admin and curation console · **eval harness wired into CI as a
merge gate**.

**Entry:** Desire gate passed · WhatsApp verification complete **or** an explicit
decision to launch push-only · Play closed test already running if Android is in
scope.

**Gate: RETENTION.**

**Signal:**
- **≥25%** of the cohort still opening at least one alert in week 4
- **≥1.5 sessions/user/week**
- Alert unsubscribe **<5%/month**
- Automated link-health probe: **≥97% deep-link validity, ≤1 catalogue incident
  per week**

**Kill:** week-4 retention <12%, or unsubscribe >12%/month, or link validity <90%.
The last one matters more than it looks: **no amount of model quality compensates
for sending users to dead or out-of-stock links.**

### The channel decision belongs in this phase

At India's 2026 rates a WhatsApp marketing template costs **₹0.8631 + 18% GST +
BSP markup ≈ ₹1.09**. Three alerts a week is **~₹167–182 per user per year**,
requiring **~₹2,270/user/year in attributed GMV** at 7% commission just to break
even on messaging — before inference, infrastructure or acquisition. At 10k MAU
that is ~₹1.6M/year, **an order of magnitude above the entire infrastructure
bill.**

**Default to in-app push and reserve WhatsApp for high-intent moments.** Make the
crossover a measured Phase 4 criterion, not an assumption.

One classification question decides this outright: **will Meta approve a
recurring persona-matched recommendation template, and as marketing or utility?**
Utility is ~7× cheaper. Submit a real template in Phase 0 and find out.

---

## Phase 4 — MVP: public launch

**4–6 weeks (P50 5, P80 7)**

App-store submission · catalogue scaled to 5–10 merchants · onboarding polish ·
support flow · DPDP consent and deletion flows · cost controls · on-call.

**Entry:** Retention gate passed · app-store lead time already burned down · all
merchant approvals in hand.

**Gate: UNIT ECONOMICS.**

**Signal:** attributed GMV per active user per month **≥3× fully-loaded messaging
+ inference cost** per active user per month, computed on **reconciled commission
receipts — not projections** — with **≥100 reconciled conversions**.

**Kill:** commission per active user below messaging + inference cost after six
weeks → the channel is unviable at that alert frequency. Cut to in-app only and
re-gate rather than scaling a negative-margin loop.

> **Model commission net of returns.** Indian fashion return rates run **25–40%**
> and national RTO ~23% (COD ~26% vs <2% prepaid). A 7% headline rate at a 30%
> return rate realises ~4.9% before attribution leakage. Model at the bottom of
> the range.

---

## Phase 5 — Product: find a channel that repeats

**Open-ended · first review at 8–12 weeks**

**Distribution is the primary risk, not product quality.** Meesho reached 1.5M
users in one month with an in-app feature. Daydream reached 1.5M in a year with
$50M and a genuinely good product. A bootstrapped two-person team has no
distribution answer today, and paid acquisition does not work on affiliate
margins.

Candidate organic loops, to be tested with real CAC numbers:

- **Occasion-adjacent partnerships** — wedding invitation platforms, planners,
  bridal creators. The user has already declared the occasion; that is the
  highest-intent moment in the funnel.
- **Screenshot-to-shop sharing** — architecturally free (§9 of
  [ARCHITECTURE.md](ARCHITECTURE.md)) and inherently shareable.
- **SEO on occasion queries** — "what to wear to a haldi" is a real, durable,
  under-served query class.
- **WhatsApp virality** — forwarding a look to a friend is native behaviour in India.

**Exit:** a repeatable acquisition channel with **CAC payback under 6 months**.
**Kill:** no such channel after 12 weeks of testing.

---

## Timeline summary

| Phase | P50 | P80 | Gate | Kill trigger |
|---|---:|---:|---|---|
| 0 · Foundation + falsification | 2–3 wk | 3 wk | Clocks started; thesis survives | Occasion gap absent, or net rate <4%, or terms prohibit agents |
| 1 · PoC | 5 wk | 7 wk | Relevance | Top-5 hit <40%, or no feed live, at wk 6 |
| 2 · Pilot | 4 wk | 6 wk | Desire | Alert CTR <3%, or 0 conversions in 200+ clicks |
| 3 · Private beta | 7 wk | 10 wk | Retention | Wk-4 retention <12%, unsub >12%/mo, link validity <90% |
| 4 · MVP | 5 wk | 7 wk | Unit economics | Commission/user < messaging + inference cost |
| **PoC start → MVP gate** | **~21 wk** | **~30 wk** | | |
| 5 · Product | open | | Repeatable CAC | No channel with <6mo payback in 12 wk |

**Indicative calendar** (two people, Phase 0 starting September 2026): MVP gate
lands **February 2027 at P50, April 2027 at P80**.

That is uncomfortably close to **13 May 2027 — the DPDP full compliance
deadline.** This is exactly why the consent ledger is a Phase 3 *Must* and a
day-one schema decision, not a launch-week retrofit.

---

## Scope discipline

**Cut lines are agreed before each phase starts, not negotiated mid-phase.**
Flyvbjerg's finding is that per-task padding cannot cover a fat-tailed
distribution and Parkinson's Law consumes it anyway; the only thing that works is
cutting scope structurally.

### Deliberately not building — ever

Checkout · payments · inventory · logistics · virtual try-on · a social network ·
order tracking and store support.

This is no longer a scoping compromise. **OpenAI retired in-chat Instant Checkout
on 24 March 2026** after Walmart measured it converting ~3× *worse* than
click-through to walmart.com, and the market consolidated on "discover in AI, buy
on site." Aura's architecture is the industry-validated one. Say so.

### Not building yet

Screenshot-to-shop (Phase 5 — architecturally free, but a growth feature, not a
core one) · outfit completion · gifting and budget modes · weekly digest ·
multi-vertical expansion · ACP/UCP integration (neither protocol has reached
India; monitor monthly).

---

## The escape hatch, designed in from day one

Both prior attempts at this wedge exited sideways: **The Yes** to a
technology/team acquisition ($87.6M), **Daydream** to white-label search for
brands. Neither was a consumer outcome.

If the **occasion-intelligence corpus is built as a clean, separable service** —
versioned structured data with provenance, not prompt logic buried in the app —
then the same corpus is licensable to Myntra, Ajio, Tata CLiQ or Nykaa for their
festive and wedding seasons.

**That costs nothing extra if the architecture is right from the start, and it is
worth a great deal if the consumer product does not find its loop.** Build it
that way. Do not build *for* it.

---

## What would make this plan wrong

Held honestly, because the gates above are only as good as the assumptions under
them:

1. **The occasion gap may not exist.** Incumbents may already encode this in
   ranking without publicising it. Phase 0 experiment 1 settles it.
2. **Affiliate terms may prohibit agent use outright.** No public policy exists
   either way. This is a binary, and it is unresolved.
3. **The 3% conversation-to-sale assumption is unvalidated** and the entire LLM
   cost model rests on it. At 1%, most model choices go underwater.
4. **The alert thresholds are borrowed**, not observed from a comparable Indian
   product.
5. **Distribution has no answer yet.** Everything above assumes users can be
   reached at a cost the affiliate margin supports. That remains unproven, and it
   is what actually killed the predecessors.
