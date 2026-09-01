# Aura — Evidence Base

Every load-bearing claim in [README.md](../README.md), [ROADMAP.md](ROADMAP.md)
and [ARCHITECTURE.md](ARCHITECTURE.md) traces to something here. Research
current to **31 August 2026**.

**How to read the confidence tags:**

| Tag | Meaning |
|---|---|
| `VERIFIED` | Confirmed against a primary or near-primary source |
| `LIKELY` | Multiple secondary sources agree; no primary found |
| `UNCERTAIN` | Single source, vendor-published, or derived estimate |
| `CONTRADICTED` | The original pitch claim is wrong as stated |
| `ESTIMATE` | Our own arithmetic, not a published figure |

> Figures sourced from affiliate networks, BSPs and martech vendors are
> **marketing numbers**. They are flagged as such throughout and should be
> re-verified against a real rate card before they enter a financial model or an
> investor deck.

---

## 1. The two closest precedents both failed

This is the most important section in this document. Aura's exact wedge has been
run twice in public, by better-resourced teams, and neither worked.

### Daydream — the Western analogue

`VERIFIED` Raised **$50M seed, June 2024**, co-led by Forerunner and Index, with
GV, True Ventures and Karlie Kloss. Founded by Julie Bornstein — 25+ years in
e-commerce (Stitch Fix COO, Sephora, Nordstrom, Urban Outfitters), founder of
The Yes. Founding team from Google, Microsoft, Amazon, Nordstrom, Farfetch. No
later round found as of Aug 2026; still operating on seed money 26 months on.

`VERIFIED` Publicly launched in the US on **25 June 2025** with 2M+ products from
~8,500 brands. Across its **entire first year the consumer product drew ~1.5M
unique visitors** to website and app combined. Roughly 13 months after launch it
announced **"Powered by Daydream"** — white-label natural-language search
embedded on brands' *own* sites, with STAUD, Alice + Olivia, Couper, Cult Mia
and Hampden Clothing live and 25+ more signed.

Bornstein: *"This is not a pivot."* Also Bornstein: *"We're really committed to
the consumer business, and, as hard as it is, we really believe in it."* Puck ran
a piece titled "Requiem for Daydream."

`VERIFIED` Daydream's business model is **exactly Aura's** — commission on
purchases completed at partner retailers, no inventory, no payments, no
advertising. Aura therefore cannot claim the model is untested. It has been
tested at scale and has not yet produced a consumer breakout.

`LIKELY` The documented failure mode is precisely the one Aura's occasion
intelligence must solve: hands-on reviews record misses on **negative and
compound constraints** ("no sheer", "no tighter dresses"), with the system
described as struggling to weigh multiple attributes in complex searches.

> Sources: [PR Newswire, Jun 2024](https://www.prnewswire.com/news-releases/daydream-secures-50-million-in-seed-funding-to-launch-new-ai-powered-search-and-discovery-shopping-platform-302177481.html) ·
> [Fortune, 25 Jun 2025](https://fortune.com/2025/06/25/daydream-fashion-ai-shopping-agent-marketplace-julie-bornstein/) ·
> [The Aisle / Jason Del Rey, Aug 2026](https://www.readtheaisle.com/p/powered-by-day-dream-fashion-conversational-ai-search) ·
> [Puck, Mar 2026](https://puck.news/does-anyone-actually-want-ai-to-help-them-shop/) (paywalled)

### Alle — the India analogue, already dead

`VERIFIED` Founded 2023 in Bengaluru by **three ex-Meesho executives** (Prateek
Agarwal, Harshit Madan, Pavan Patil). Raised **$3M seed, Dec 2023**, from
Elevation Capital (a Meesho backer), Bharat Founders Fund and The Singhal
Children. Product: a conversational "AI stylist" over **1,000+ curated brands**
on one platform.

Shutdown decided **October 2025**, announced **January 2026** — the first Indian
startup shutdown announced that year. Co-founder Prateek Agarwal:

> *"Over the 2.5 years we spent building Alle, we pivoted six times, each time
> believing we were getting closer to a large enough opportunity. Eventually, we
> had to accept that the opportunity cost of everyone's time outweighed another
> uncertain pivot."*

**The stated cause was not execution or capital. It was the wedge.**

> Sources: [Inc42](https://inc42.com/buzz/elevation-capital-backed-ai-startup-alle-shuts-shop/) ·
> [YourStory, Jan 2026](https://yourstory.com/2026/01/elevation-capital-backed-ai-stylist-alle-shuts-shop)

`LIKELY` Also shut down: **NeuroPixel.AI**, a Flipkart-backed Indian AI fashion
startup. Tier-1 and strategic backing has not been sufficient in this category
in India. ([Inc42](https://inc42.com/buzz/flipkart-backed-neuropixel-ai-shuts-down/))

### The graveyard, and what it repeats

`LIKELY` Across **Polyvore, The Yes, LimeRoad, Wooplr, Alle** and Daydream's
consumer arm, five causes repeat with almost no variation:

1. **Discovery without transaction control.** Every one had good engagement and
   bad conversion. LimeRoad: 15M users, 50M "scrapbooks", **~1.5% conversion**.
   Polyvore: 17M monthly uniques, no checkout. Daydream: 1.5M uniques on $50M.
   Owning taste does not mean owning the transaction, and whoever owns the
   transaction owns the margin *and* the data.
2. **Taste is not a retention loop.** Fashion purchase frequency is low; a
   stylist is consulted a few times a year, and the app is deleted in between.
3. **Catalogue is a treadmill, not an asset.** Alle curated 1,000+ brands,
   Daydream 8,500 — both found it was table stakes that decayed daily.
4. **The aggregator is disintermediated by its own suppliers.** Retailers watch
   which queries convert, then build the same assistant first-party. Salesforce
   measured retailers with their own branded shopper agents growing holiday
   sales **59% faster** (6.2% vs 3.9% YoY) — they are strongly incentivised to.
5. **The wedge is too narrow to be a company.** Alle's stated cause, verbatim.

`VERIFIED` The two observed **exits** are also instructive, and neither is a
consumer outcome: acquihire for team/technology (The Yes → Pinterest, **$87.6M**,
June 2022, app sunset within months) or a B2B pivot (Daydream).

---

## 2. Competitive landscape

### The pitch's competitor table omits the four most dangerous entities

`VERIFIED` **Flipkart SLAP** ("Shop Like a Pro"), January 2026 — a **standalone**
conversational AI shopping app, not an in-app widget, replacing Flippi. It
explicitly supports DM-ing **Instagram Reel product links** to find the exact
item or the best alternative. Still in gated early-access beta as of mid-2026.
Built by **Myntra's parent**, with India's deepest fashion catalogue and
behavioural data behind it. This is the most Aura-shaped product in the market.
*(The pitch cites Flippi, which Flipkart replaced in Jan 2026 — a dated citation
an informed investor will catch.)*

`VERIFIED` **Meesho Vaani**, February 2026 — Gen-AI voice shopping assistant,
English and Hindi at launch. **1.5M users in the first phase**, conversion **+22%**
vs regular browsing, with lower returns and cancellations. Targets an estimated
500M Indians for whom typing and filters are unintuitive.

> Meesho reached in **one month** the user count Daydream reached in **a year**
> with $50M. That is the distribution asymmetry Aura is up against.

`VERIFIED` **Glance AI** — an AI shopping experience distributed on the **lock
screens** of Xiaomi, Realme and Samsung phones across India; a distribution moat
Aura cannot buy. FY25 revenue **$97.6M (+33.5%)** against a pre-tax loss of
**$105.9M**. Read that carefully: free distribution to hundreds of millions of
Indian devices, and it still lost more than its entire revenue.

`LIKELY` **Meta "Hatch"** — an Instagram shopping agent targeting launch before
Q4 2026, designed around purchasing items seen in Reels. In India, Instagram is
where fashion discovery actually happens. Note the convergence: Flipkart SLAP
already ships Reel-link ingestion. Both giants have found the same funnel.

### Incumbents already shipping

| Player | Status | Relevance to Aura |
|---|---|---|
| **Myntra Maya** | Live since 2023. Users **3× more likely to purchase**, adding from 16% more categories. 85% of users with history get AI size/fit. | Owns the fashion catalogue Aura wants to recommend from |
| **Amazon Rufus** | All-India rollout late 2025; **10M+ Indian customers**. Renamed "Alexa for Shopping" in the US, 13 May 2026. 365-day price history live in India May 2026. | India is in Amazon's *first* tier for price-history features |
| **Walmart Sparky** | Users spend **40% more per order**; users **+70% YoY**. Ads now inside Sparky. | Proof first-party retailer agents work |
| **Nykaa** | FY26 revenue ₹10,022 crore (+26%), crossing $1B. Building "Ask Nykaa", virtual closet. | Hard play into fashion |
| **Pinterest** | "Ask Pinterest" experimental AI shopping app, 17 Jun 2026. | **Already owns The Yes's technology and Bornstein's former team** |

### Direct threat to the alerts pillar

`VERIFIED` Amazon's Alexa for Shopping **already ships** proactive price-drop
alerts, automatic purchase at a target price, and **Scheduled Actions** for
recurring personalised shopping tasks. Aura's "proactive alerts" hook is not a
new capability — it is a shipped Amazon feature, backed in India by 365 days of
price history.

### Western startups in the same wedge, funded far above Aura

`VERIFIED` **Phia** (Phoebe Gates, Sophia Kianni) — $8M seed, then **$35.5M
Series A led by Kleiner Perkins, 27 Jan 2026**. Notably, Phia's traction is built
on a concrete verifiable utility (is this the best price, new or used?), **not on
taste** — which may be exactly why it raised where taste-first products struggled.

`LIKELY` **Alta** — $11M seed; AI personal stylist with a wardrobe layer, very
close to Aura's pillars 1 and 2. **Doji** — ~$14–15M for avatar-based try-on.
Neither is India-first. Aggregate investment in AI styling apps: **$2.3B+**.

`LIKELY` Most Indian "AI fashion" names are **B2B, not competitors**: Stylumia,
Streamoid, Fynd and Mad Street Den all sell *to* retailers. Aura's real India
competitors are the platforms, not these vendors.

`LIKELY` **Stylz** (Hyderabad, March 2026) pairs AI with **human stylist
validation**, giving VIP members direct access to a human. A live read on whether
pure-AI styling clears India's trust bar.

### Verdict on defensibility

`LIKELY` **The "India-first + proactive alerts" wedge is not defensible as
stated.** Decomposed:

- **India-first** buys *nothing* against Flipkart, Myntra, Meesho, Nykaa, Amazon
  India or Glance — all India-first by construction, with catalogue, transaction
  data, payment rails and free distribution. It buys **real time** against
  Daydream, Phia, Alta, Pinterest and Google agentic checkout, none of which
  serve India today. That is a head start measured in **quarters, not a moat**.
- **Proactive alerts** are a shipped Amazon feature and a one-sprint clone for
  anyone else. The 2–3/week cap is a taste choice, not a barrier. It also fights
  itself: 2–3 alerts/week against ~2% day-30 retention is probably too little
  contact to hold a user, and more would burn trust.
- **The persona engine** is the closest thing to an asset — but Myntra, Meesho
  and Amazon derive equivalent personas from **actual purchase history**, which
  is strictly better data than self-reported taste, and they get it free.

The honest position: Aura's defensibility is **execution speed plus a specific
cultural-reasoning corpus**, not structure. The pitch should say that rather than
claim a moat.

`UNCERTAIN` **Occasion intelligence is the one genuinely unserved
differentiator** — and even it is a head start, not a moat. Desk research found
no evidence that Myntra Maya, Flipkart SLAP or Rufus India reason *structurally*
about Indian occasions (ritual → dress code → fabric → colour taboo → region →
time of day → budget); they treat occasion as campaign merchandising. **But
absence of press coverage is not absence of capability.** This is the
load-bearing claim of the entire thesis and it is the least verified. It must be
settled by hands-on testing, not desk research — see [ROADMAP.md](ROADMAP.md)
Phase 0.

---

## 3. Market data — what survives checking

### Verified

`VERIFIED` **Adobe: AI-referred traffic converted 42% better** than non-AI
traffic in March 2026 — having converted **38% *worse*** twelve months earlier.
AI-referred visits also spent 45% more time on site with 33% lower bounce.
*(A +54% figure for May 2026 also circulates; use +42% as the citable primary
and be ready for the discrepancy.)*

`VERIFIED` **Salesforce: $262B** AI/agent-influenced holiday spend, **~20% of
global online holiday spend**, from 1.5B shoppers across 89 countries. The
under-cited corollary is dangerous for Aura: **retailers with their own branded
agents grew holiday sales 59% faster.**

`VERIFIED` **OpenAI retired in-chat Instant Checkout on 24 March 2026** after
Walmart measured in-ChatGPT checkout converting **~3× worse** than click-through
to walmart.com. Stated causes: limited selection, stale item information,
merchant onboarding difficulty, no multi-item carts, no loyalty connection, and a
4% ACP transaction fee. The market consolidated on **"discover in AI, buy on
site."**

> This is **affirmative evidence for Aura's architecture.** Excluding checkout,
> payments, inventory and logistics is now the industry-validated design, not a
> scoping compromise.

`LIKELY` **India is the world's most receptive market** for AI shopping agents
— 62% of Indian consumers actively use GenAI (vs 42% US); 64% use it to research
products mid-purchase; 60% want a personal AI agent (highest in APAC); ChatGPT
India grew ~4.5× in 2025 to **160M+ MAU**, OpenAI's second-largest market. But:
**76% want interactions to feel human rather than robotic**, and clear AI
labelling is the top reassurance factor.
([First Resort, citing BCG 2025 and Adobe 2026](https://www.firstresort.in/blogs/research/ai-fashion-shopping-india-2026))

### Corrected

`CONTRADICTED` **Morgan Stanley's $190–385B is US e-commerce, not global.**
Morgan Stanley Research projects agentic shoppers reaching $190–385B in **US**
spending by 2030 — ~10% of US online retail base case, up to 20% optimistic,
based on an AlphaWise survey finding ~23% of Americans made an AI-assisted
purchase in the past month. The pitch's "10–20% of e-commerce" is right; the
geography is not.
([Morgan Stanley](https://www.morganstanley.com/insights/articles/agentic-commerce-market-impact-outlook))

`VERIFIED` **McKinsey's $3–5T is global and correct**, but it measures
*orchestrated* commerce — commerce an agent influences or routes, not agent
revenue. US alone is ~$1T of it. Do not present it as an addressable market.
([Digital Commerce 360](https://www.digitalcommerce360.com/2025/10/20/mckinsey-forecast-5-trillion-agentic-commerce-sales-2030/))

`CONTRADICTED` **"Amazon blocks AI crawlers and sued Perplexity" is materially
out of date — in Aura's favour.** Amazon won a preliminary injunction against
Perplexity's Comet agent in March 2026; on **4 August 2026 the Ninth Circuit
vacated it**, holding Amazon unlikely to succeed on its CFAA claim because when a
user directs an assistant to act on Amazon.com, it is **the user, not the vendor**,
accessing Amazon's computers. The underlying suit continues. This cuts both ways:
it weakens the "incumbents lock everyone out" moat narrative while leaving
retailer *terms-of-service* enforcement an open risk for any scraping strategy.
([Engadget](https://www.engadget.com/2230471/perplexity-has-successfully-overturned-amazon-injunction-on-its-ai-shopping-bot/))

### Retention reality

`VERIFIED` **Median day-30 retention for shopping apps is ~2%** — among the
lowest of any category, with 94.4% churn by day 30. **72% of customers have
downloaded a retail app for a one-time purchase and then deleted it.** Top
uninstall reasons: no longer needed (64%), storage (43%), lack of ongoing
relevance (43%).

The one counter-signal in Aura's favour: *returning* shoppers engage with
conversational concierges **more** than first-time visitors — once users
understand how it helps, they come back and use it more deeply.
([Adobe, via Ecommerce Times](https://www.ecommercetimes.com/story/adobe-finds-most-retail-apps-are-one-and-done-178651.html))

---

## 4. Protocols and distribution

`VERIFIED` **UCP (Universal Commerce Protocol)** — Google, with Shopify, Etsy,
Wayfair, Target and Walmart; 20+ partners. Major update March 2026; **live with
real US retailer checkout at Google Marketing Live, 20 May 2026**. Free,
open-source. Powers Google AI Mode and Gemini.

`VERIFIED` **ACP (Agentic Commerce Protocol)** — Stripe and OpenAI; live in
production since late 2025 with PayPal and Worldpay. Powers ChatGPT.

`LIKELY` **Neither has reached India.** UCP checkout rollout is US → Canada,
Australia → UK. No India signal found. Google's India search dominance means an
India launch would compress Aura's window sharply — **worth monitoring monthly.**

Both protocols are fundamentally **merchant-side checkout standards**. Since Aura
deliberately does no checkout, they are a **Phase 3+ distribution consideration**
(getting Aura's reasoning onto AI surfaces), not a Phase 1 dependency.

`LIKELY` **Perplexity's merchant programme is free** (no listing fees, no
commissions) with "Buy with Pro" zero-fee checkout — but is **US-shipping-gated**,
so not a competitor in India today.

`LIKELY` **ONDC** is a real but unproven catalogue route: ~37 network
participants, 260,000+ merchants, and it is described as an emerging discovery
channel for **regional, ethnic and D2C fashion** — which is precisely Aura's
segment. Buyer-app participation requires network certification. Evaluated
further in the supply analysis below.

---

## 5. Delivery reality — what "8–12 weeks to MVP" actually buys

### The productivity evidence does not support an AI speedup

`VERIFIED` **METR RCT: experienced developers were 19% *slower*** with
early-2025 AI tools — and could not perceive it. 16 developers, 246 issues, on
mature repos (22k+ stars, 1M+ LOC) where they had years of experience. They
forecast a 24% speedup beforehand and still estimated a 20% speedup *afterwards*
— a ~39-point perception gap against a measured +19% completion time.
([METR, 10 Jul 2025](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/) · arXiv:2507.09089)

`VERIFIED` **A Google internal RCT found the opposite sign — ~21% faster** (96
engineers, three AI features, summer 2024), with authors noting *"our confidence
interval is large."* ([arXiv:2410.12944](https://arxiv.org/abs/2410.12944))

**So the honest bracket is roughly −19% to +21%, depending on context.** Plan for
**0–20% on code-typing tasks and ~0% on judgement-heavy work** — taxonomy design,
relevance tuning, alert calibration, feed reconciliation — which is most of this
build.

`LIKELY` **DORA 2025**: AI adoption now correlates positively with throughput but
*continues* to correlate with **higher delivery instability** — more change
failures, more rework. Root cause is structural: without strong automated
testing and fast feedback, more change volume produces instability. For a 1–3
person team with no test infrastructure, that effect lands fully. **Budget
explicit rework capacity.**

`LIKELY` **Stack Overflow 2025**: 84% use or plan to use AI tools, but only 29%
trust output accuracy and **3% report high trust**. Top frustration: *"AI
solutions that are almost right, but not quite"* (66%); second, longer debugging
(45%).

### Estimation discipline

`LIKELY` **The planning fallacy is severe enough that a team's self-declared
worst case is still optimistic.** Buehler, Griffin & Ross (1994): students
estimated 33.9 days average, 27.4 best case, **48.6 worst case** — and actually
took **55.5 days**, exceeding even the worst case. Only ~30% estimated accurately.

`LIKELY` **IT overruns are fat-tailed.** Flyvbjerg & Budzier, 1,471 IT projects:
average cost overrun 27%, but **one in six is a "black swan"** at 200% cost and
70% schedule overrun. Flyvbjerg's own prescription is that padding cannot cover
this — the fix is **structural de-scoping and kill gates**.

`LIKELY` **Cone of Uncertainty**: at Initial Concept — where Aura sits — the
defensible range is **0.25× to 4×**, a 16× spread. Critically: *"the only way to
reduce the variability in the estimate is to reduce the variability in the
project itself."* **The cone narrows with decisions made, not weeks elapsed.**
That is the entire justification for phase gates.

`VERIFIED` **Gartner predicts >40% of agentic AI projects will be cancelled by
end of 2027** — escalating costs, unclear business value, inadequate risk
controls — noting most current projects are "early stage experiments or proofs of
concept mostly driven by hype and often misapplied."

`LIKELY` **MIT Project NANDA**: 95% of enterprise GenAI pilots produced no
measurable P&L impact, cause given as a workflow gap — *"tools that never entered
the workflow they were bought to change."* Enterprise-focused and methodologically
criticised, so treat as directional — but it argues for gates measured by
**behaviour change in the user's real routine**, not demo quality.

### External clocks that cannot be compressed

`CONTRADICTED` **"Amazon PA-API qualification" is obsolete.** PA-API 5.0 was
deprecated 30 April 2026 and **retired 15 May 2026** (calls now return HTTP 403).
The replacement **Creators API** uses OAuth 2.0 client-credentials.

`LIKELY` **The Creators API gate is chicken-and-egg**: it requires an Associates
account with *final* acceptance **plus ~10 qualified sales in a rolling trailing
30 days** on that marketplace — maintained, or access is suspended. **You need
converting traffic before you get catalogue access.** Never let a plan depend on
an input that requires the plan to have already succeeded.

`LIKELY` **Meta Business Verification + WhatsApp API onboarding: 2–6 weeks.**
Verification typically 2–5 business days with clean documents, up to 10 in policy
windows; full WABA onboarding 3–10 business days clean, 2–4 weeks with document
rework, 4–8 weeks for enterprise review. Assume **1–2 template rejection rounds**
for a novel proactive-alert use case. Unverified portfolios are capped at 250
messages/24h.

`VERIFIED` **Google Play imposes a hard 14-day wall.** Personal developer
accounts created after 13 Nov 2023 must run a closed test with **12 testers
continuously opted in for at least 14 days** before they can even *apply* for
production access — and completing it does not publish the app; Google then
evaluates how actively testers used it. *(Apple: ~90% of submissions reviewed in
under 24 hours.)* **Use an organisation account.**

`LIKELY` **India company + tax setup is a 3–8 week clock that gates revenue**
(affiliate payouts need PAN/GST): DSC 1–2 days, SPICe+ name reservation 1–3 days,
incorporation 7–10 working days; GST 3–5 working days with Aadhaar e-KYC, up to
30 if physical verification triggers; plus 1–3 weeks for bank and payment gateway.

`LIKELY` **Brand-partnership revenue cannot sit in a 12-month base case.**
Forrester: average enterprise sales cycle rose from 6.4 months (2015) to **9.3
months (2023)**; major deals 6–18 months. Warm partnership routes move ~4× faster
than outbound. Budget **3–9 months** from first conversation to first rupee.

### Effort decomposition

`ESTIMATE` The four-pillar MVP is **45–85 person-weeks of pure build**, excluding
discovery, design, user research, recruiting, partnership meetings, support and
fundraising — all of which consume the same founder-hours.

| Component | To MVP (person-weeks) | Note |
|---|---:|---|
| Catalogue ingestion + normalisation | 5–9 | Largest and most underestimated; each new merchant costs 0.5–1.5 pw that **does not amortise** |
| Attribute enrichment | 4.5–8 | Risk is the ontology and gold set, not the model code |
| Hybrid search | 5–9 | Tuning tail is **unbounded without a golden query set** |
| Chat / agent orchestration | 6–11 | Only 1–2 of that is the demo |
| Persona store + editor | 3–6 | Editable + provenance roughly doubles a naive profile store |
| Alert scoring + delivery | 5–9 | It is a notification **platform**, not a cron job |
| Saves / boards | 1.5–3 | |
| Affiliate deep-linking + tracking | 2–4 via aggregator | 4–7 integrating networks directly |
| Analytics + eval harness | 4–7 | The eval half is the most-cut, most-costly-to-cut item |
| Auth | 1–2 managed | 3–5 hand-rolled, for zero differentiation |
| Admin / curation tools | 3–6 | Always cut, then rebuilt under crisis |
| Cross-cutting (frontend, CI/CD, DPDP, security) | 8–17 | |

`ESTIMATE` **Against effective capacity, 8–12 weeks buys 8–15% of that scope for
1 person, 15–35% for 2, and 25–55% for 3.** A solo founder also doing
partnerships, support and fundraising supplies ~6–7 *effective* engineering
person-weeks in 10 calendar weeks; two people ~12–16; three ~20–26 with a
coordination tax.

**None of these is GA.** The pitch's "8–12 weeks to MVP" is not achievable for
the four-pillar product at any of these team sizes.

### The highest-leverage de-risking move

`VERIFIED` **Cuelinks ships a developer API and an MCP server** that collapses
affiliate deep-linking and click tracking from 4–7 person-weeks to ~1.5–3: 33
endpoints covering URL→tracked-link conversion with 5-dimension sub-ID
attribution, EPC-sortable campaign search across 100+ networks and 10,000+
campaigns, real-time conversions and reporting, and programmatic
missing-transaction claims. Free read-only Starter tier. It also solves the
Myntra/Ajio problem — neither has a self-serve programme, so a sub-network is the
only route in regardless.
([developers.cuelinks.com](https://developers.cuelinks.com/), fetched 31 Aug 2026)

---

## 6. Compliance

`LIKELY` **DPDP Rules notified 14 November 2025.** 2026 is the "build and test"
year under soft enforcement (guidance and warnings). The Consent Manager
framework is expected to be operationalised mid-to-late 2026; **November 2026** is
widely expected to end the soft-enforcement phase; **13 May 2027 is the full
compliance deadline** for all Data Fiduciaries. Penalties reach **₹250 crore**
for security failures and ₹200 crore for other breaches.

Aura is unambiguously a Data Fiduciary — it stores style-preference and
behavioural data and sends proactive marketing. Consent capture, purpose
limitation, deletion rights and grievance redressal all fall **inside this
roadmap's horizon**, which is why the consent ledger is a day-one schema
requirement rather than a later retrofit.

> Sources: [India Briefing](https://www.india-briefing.com/news/india-dpdp-compliance-timeline-enforcement-2026-27-44740.html/) ·
> [Fisher Phillips](https://www.fisherphillips.com/en/insights/insights/indias-new-data-privacy-rules-are-here)

---

## 7. Messaging economics

`VERIFIED` **WhatsApp India 2026 rate card** (per delivered message, Meta's own
rates effective 1 July 2026): **marketing ₹0.8631**, utility ₹0.1150,
authentication ₹0.1150. **Plus 18% GST** (₹0.8631 → ₹1.0185) **plus BSP markup**
— AiSensy charges ₹1.09 for a marketing template; MyOperator ~₹0.95.

Two changes that matter:

- Since **1 July 2025** Meta charges **per delivered message**, not per 24-hour
  conversation window.
- From **1 October 2026**, service and utility messages inside an open 24-hour
  window — previously free — **become chargeable**.

`ESTIMATE` **Persona-matched trend, drop and price alerts are marketing-category,
not utility.** They will not qualify for the ₹0.115 tier. At 3 alerts/week:

```
3 × 52 = 156 delivered marketing templates/user/year
156 × ₹0.8631            = ₹134.6
+ 18% GST                = ₹158.8
+ BSP markup (₹0.05–0.15/msg) = ₹167–182/user/year
```

Break-even attributed GMV at 7% blended commission ≈ **₹2,270/user/year** —
roughly **one ₹2,300 order per user per year, attributed and reconciled**, before
any inference, infrastructure or acquisition cost, and ignoring that only a
fraction of users stay opted in for a full year.

**At 10k MAU this is ~₹1.6M/year — an order of magnitude above the entire
infrastructure bill.** Messaging, not compute, is the dominant variable cost of
this product.

`LIKELY` Counterweight: WhatsApp is reported as 2026's highest-performing channel
for alert delivery, and with ~2% day-30 app retention in this category, a
WhatsApp surface plausibly beats an in-app push surface outright. *(Source is a
vendor blog — treat as directional.)*

**The unresolved question that decides pillar 3:** will Meta approve a recurring
persona-matched product-recommendation template, and under which category? If any
variant qualifies as utility, the economics improve **~7×**. This must be tested
with a real template submission in Phase 0, not assumed.

---

## 8. Returns and clawback

`LIKELY` **Indian fashion return rates run 25–40%** (some sources 30–35% for
fashion and footwear, against a ~17% all-category average).

`LIKELY` **RTO**: national average **~23.18%** across 180M+ shoppers, rising
toward 40% by state and pin code. **COD RTO ~26% vs <2% prepaid.** Indian D2C
brands collectively lose **₹8,000+ crore a year** to RTO.

`ESTIMATE` **Any commission model must be net of returns.** A 7% headline rate at
a 30% return rate is ~4.9% realised, before attribution leakage. The pitch's
"4–10%" range should be read as gross, and modelled at the bottom of it.

> Sources: [First Resort — Returns & RTO in Indian fashion, 2026](https://www.firstresort.in/blogs/research/fashion-ecommerce-returns-rto-india-2026) ·
> [TrackVid / GoKwik data](https://trackvid.in/blogs/rto-in-ecommerce-india.html)

---

## 9. Supply and unit economics

> **Status: in progress.** Catalogue-source ranking, real affiliate rate cards,
> attribution leakage, payout terms and the full revenue-per-MAU model are being
> researched separately and will be appended here.

Established so far:

- Affiliate networks in India supply **link conversion and reporting, not
  catalogues**. Cuelinks: 33 endpoints, no SKU feed.
- **Myntra and Ajio have no self-serve affiliate programme.** Access is only via
  sub-networks (Cuelinks, EarnKaro, ExtraPe), adding an approval hop.
- Headline rates — Myntra 7.5–10%, Flipkart 1–15% by category, Amazon India
  fashion 4–9% — are **affiliate-network marketing numbers**, not net rates for a
  new publisher. `UNCERTAIN`, and it is the single most important unverified
  number in the model.
- Amazon cookie window: 24 hours (90 days if added to cart within 24h).
- **An "AI agent" publisher type is a category these networks have no precedent
  for.** Expect questions and at least one rejection.

---

## 10. Open questions that should be closed by conversation, not search

Ranked by how much the answer would change the plan:

1. **What is the actual net affiliate rate** for Myntra/Ajio/Flipkart/Nykaa
   apparel after category caps, new-vs-repeat tiers and network revenue share?
   If it is 3–4% rather than 4–10%, the unit economics section of the pitch is
   wrong.
2. **Do Indian affiliate network terms permit an AI agent** to ingest,
   restructure and re-present retailer catalogue data? Aggregators have been
   tolerated as coupon/cashback sites; an LLM re-ranking a retailer's catalogue
   inside a third-party conversational surface is a different proposition.
3. **How good are Myntra Maya, Flipkart SLAP and Rufus India at real occasion
   queries?** Twenty prompts, graded. This is the thesis.
4. **Why exactly did Alle pivot six times?** The founders are reachable ex-Meesho
   operators in Bengaluru. One conversation with Prateek Agarwal is worth more
   than all of this desk research.
5. **Will Meta classify a persona-matched recommendation template as marketing or
   utility?** A ~7× swing in the cost of pillar 3.
6. **Is there any published evidence that persona-matched *recommendation* alerts
   drive retention** in fashion — as opposed to price-drop alerts on a known
   wishlist item? These are psychologically different products ("the thing I want
   got cheaper" vs "you will like this"). No data found for the second, which is
   the one Aura is betting on.
7. **Does a pure-AI stylist clear India's trust bar at all**, given 76% want
   interactions to feel human and Stylz deliberately pairs AI with human stylists?
8. **What are Google's India plans for UCP and AI Mode agentic shopping?** An
   India launch would compress the window sharply.
