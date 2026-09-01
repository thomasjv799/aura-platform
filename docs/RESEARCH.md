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

> **This section inverts the plan.** Catalogue supply stopped being the gating
> dependency on 17 June 2026. The gate moved to monetisation, and it moved
> somewhere much worse.

### 9.1 Catalogue is solved, free, and legal

`VERIFIED (live probe, 31 Aug 2026)` **Shopify's Global Catalog MCP is an open,
unauthenticated, cross-merchant India fashion search API.**

```
POST https://catalog.shopify.com/api/ucp/mcp
   → search_catalog, query "yellow kurta set for haldi ceremony"
   → context: { address_country: IN, currency: INR }
   → filters: { available: true, ships_to: IN, ships_from: IN }
```

No auth header. No API key. No account. HTTP 200, `total_count = 443`, returning
Kisah, Bonsoir, KALKI Fashion, Kalpraag at ₹2,999–₹19,499 with **title, image,
price, per-variant stock, size options, product deep link, seller identity and
policy links**.

`VERIFIED` **Approval was removed on 17 June 2026** (Shopify Spring '26 Edition):
*"Building on Shopify's agentic commerce layer used to require approval. That
requirement is gone."* Engineering cost to integrate: `ESTIMATE` **under one
developer-day** — a static JSON agent profile and an HTTP client.

`VERIFIED` **The occasion differentiator is already a free field in the supply
layer.** Verbatim from the Kisah result's `metadata.top_features`:

> *"Suitable for haldi, mehendi, and other traditional events"*

This is the single most uncomfortable finding in this document. Aura's proposed
moat is shipping as vendor metadata, at no cost, to anyone who calls the endpoint.

`VERIFIED` **But it is a search endpoint, not a feed.** Depth probe across eight
queries returned `total_count` clustered at **395–482 every time** — sherwani 482,
lehenga 454, office shirt 441, saree 430, kurti 418, anarkali 412, chinos 395.
That is a **result cap of ~400–500 per query**, not catalogue depth. So: you
cannot mirror the corpus, cannot build offline embeddings over it, cannot compute
"what's new this week" without your own query fan-out, and **your ranking quality
is capped by Shopify's relevance, not yours.**

`UNCERTAIN` No published rate limits, SLA or commercial rate card. Free today ≠
free at 100k MAU. Model a non-zero probability of metering.

### 9.2 Per-store feeds work too, and robots.txt explicitly permits them

`VERIFIED (live probe)` `GET /products.json?limit=250` returned **7 of 10** major
Indian D2C fashion stores unauthenticated — Rare Rabbit, Nicobar, Libas, Suta,
Freakins, Powerlook, Bummer. Full schema: variants with `sku`, `price`,
`compare_at_price`, `available` (boolean per variant), `option1..3` (size,
colour), plus product `tags`, `product_type`, `handle` and 6 CDN images.

**Every attribute the product needs is present.** Missing only quantity-on-hand
and any taxonomy beyond free-text tags. A 5,000-SKU brand refreshes in ~20
seconds at 1 req/s. Cost: ₹0 plus a small VM.

`VERIFIED (live fetch)` **Shopify's 2026 default `robots.txt` invites catalogue
crawling and forbids only automated checkout.** From `suta.in/robots.txt`:

> `# Shopify storefront. Public product, collection, page, blog, policy, cart, and localized HTML is crawlable.`
> `# Agents should use UCP/MCP for catalog, cart, and checkout.`
> `# Checkouts are for humans. Do NOT complete checkout, payment, or order placement automatically…`

Then `User-agent: * / Allow: /`. Zero mentions of `products.json` in any of the
seven stores checked. Disallowed paths are transactional only.

**This is decisive for Aura specifically: the one thing Shopify's robots.txt
forbids is the one thing Aura has already declared out of scope.** Aura is, by
construction, inside the permitted envelope.

`LIKELY` Caveats: robots.txt is a permission signal, not a licence, and does not
override merchant ToS. `suta.in` carried dedicated `GPTBot` and `ClaudeBot`
stanzas — merchants are selectively blocking *named* AI crawlers while allowing
`*`. Ship a named UA and expect a growing blocklist.

`VERIFIED (licence text)` **The consumer `shop` skill route prohibits exactly what
Aura is.** From `shop.app/references/legal.md`: *"This skill is for individual
end-users only. Building commercial services, resale platforms, aggregators, or
anything that provides third parties with programmatic access to Shopify's
catalog… is prohibited."* The same help page names the escape hatch —
`shopify.dev/docs/agents`. **Two licence regimes over nearly the same data. Aura
must be able to state in writing that it is on the developer/UCP route.**

`LIKELY` Market size: **121,624 active Shopify stores in India in Q1 2026**
(+32% YoY), **38.7% in Apparel & Fashion** ≈ **~47,000 Indian fashion Shopify
stores**. (Emerge Digital, 14 May 2026, sourcing StoreLeads Q1 2026.)

### 9.3 The finding that matters: ~97% of that catalogue is unmonetisable

`VERIFIED (live probe), method limitation stated` Pulling 500 products across 10
India fashion queries yielded **192 distinct Indian sellers** — Kisah, Bonsoir,
KALKI, Kalpraag, Varanga, Saundh, Shop Mulmul, Taana Baana, Vastramay, Zinniars,
asaga — a deep long tail of small brands, essentially none on Cuelinks or
Admitad. Probing 70 of those domains for affiliate-programme signals:

| Test | Hits | Rate |
|---|---:|---:|
| Homepage scan (GoAffPro / UpPromote / Refersion / Affiliatly / Social Snowball) | 2 of 69 reachable | **2.9%** |
| Direct path probe (`/pages/affiliate`, `/apps/goaffpro`, …) | 6 of 70 | 8.6% |
| **Generous union** | **8 of 70** | **11%** |

Method limitation: homepage scanning misses footer-only links on non-home
templates; Shopify page-existence probes can return 200 for catch-all templates.
**Treat 3–11% as the band.**

> **Aura's recommendation set and its monetisable set barely intersect.** Every
> beautiful haldi recommendation the demo produces is, 89–97% of the time, an
> unpaid recommendation.

### 9.4 Real affiliate rates — the headline numbers do not apply to Aura's users

`VERIFIED (Cuelinks campaign pages, Aug–Sep 2026)`

| Merchant | Published publisher payout | Note |
|---|---|---|
| **Myntra** | "Upto 9%" → **7.5% new / 3.75% existing** | Excludes wallet credits, gift vouchers, Myntra Credits |
| **Ajio** | **4.50%–10.40%** per sale | Separate new / existing / jewellery / tech tiers; alliance codes pay **0** |
| **Amazon.in** | **"Upto 3.80%"** | Category rates behind login |
| **Flipkart** | "Upto 12%" | Cuelinks only — direct programme discontinued |
| **Levi.in** (vCommission) | up to 17.5% | The only Indian D2C brand with a published rate found |

**The adversarial point.** Aura's target user is someone who already shops for
occasion-wear online. That person is **by definition an existing Myntra/Ajio
customer**, so the applicable rate is **Myntra 3.75%**, not 7.5%, and the
**bottom** of Ajio's band, not the top. Every affiliate-network marketing blog
quotes the new-customer tier. **Modelled blended net rate: 5.0%.**

`LIKELY` Cuelinks states revenue distribution is **75:25 publisher:Cuelinks**. The
Ajio page describes its figures as publisher payout rather than revenue share, so
displayed rates *appear* already net — **unverified; confirm from inside a
logged-in dashboard.** It swings the model 25%.

### 9.5 Three structural killers in the affiliate mechanics

`VERIFIED` **1. Cookie windows are 1 day. Industry click-to-sale is 10 days.**
Myntra 1 day, Ajio 1 day (cut from 2 effective 1 July), Amazon.in 1 day. Fashion
occasion-wear at ₹3,000–₹20,000 is a considered purchase involving browsing,
price comparison and family consultation.

> This is not a tuning problem, it is a design constraint: **Aura only gets paid
> on same-day impulse conversions.** Anything that makes Aura a thoughtful advisor
> rather than an impulse trigger destroys its own revenue. "Save it and decide
> later" — the natural shape of occasion shopping — may be structurally
> incompatible with affiliate monetisation.

`VERIFIED` **2. Commission is paid on delivered, not ordered GMV.** Ajio via
Cuelinks: *"Commission calculated on delivered orders."* EarnKaro T&C: a
qualifying transaction must be *"not returned/refunded/cancelled/rejected."*
Against 25–40% fashion returns and 23% RTO, **~30% of tracked GMV evaporates.**
Modelled survival factor **0.70**, which is generous — it assumes a prepaid-skewed
mix. (Unicommerce FY26: COD festive returns **58%** vs <15% prepaid.)

`VERIFIED` **3. Cash lands 4–5.5 months after the sale.**

| Merchant | Tracking | Validation | Payment | To cash |
|---|---|---|---|---|
| Myntra | 48 h | 60 days from following month | +90 days | **~5.5 months** |
| Ajio | 5 min | 45 days from following month | +60 days | **~4 months** |
| Amazon.in | 48 h | 45 days from following month | +15 days | ~2.5 months |

Cuelinks minimum payout ₹500. **A bootstrapped team books revenue in September and
banks it in February.** This alone rules out any paid-acquisition strategy.

`UNCERTAIN` **App-to-web attribution leakage has no published India figure.** The
search returned none. Cuelinks confirms *"affiliate tracking on all mobile apps is
possible only through deeplink affiliate URLs"* and that *"tracking issues often
stem from app attribution."* Generic non-India sources put combined tracking loss
at 20–40%. **50% attribution survival is used below as an explicit ESTIMATE**,
justified by 1-day cookies + universal-link handoff dropping tracking params +
Safari ITP + India's app-first shopping behaviour. **This single unmeasured
parameter swings revenue 2×.**

### 9.6 The model

`LIKELY` Inputs, each sourced or explicitly flagged:

| Input | Base | Optimistic | Source |
|---|---|---|---|
| AOV | **₹1,800** | ₹1,800 | GoKwik D2C festive ₹1,869 (+11% YoY) |
| Net commission | **5.0%** | 7.5% | Cuelinks rates, existing-user weighted |
| Click→order CVR | **1.5%** | 2.0% | India D2C 1.8% overall / **1.2% mobile** / 3.1% desktop |
| Attribution survival | **0.50** `ESTIMATE` | 0.70 | No public India figure |
| Delivered survival | **0.70** | 0.75 | GoKwik / Unicommerce / Pragma |

```
Per 1,000 outbound clicks (base):
  orders placed     1,000 × 1.5%   =  15.0
  attributed        15.0  × 0.50   =   7.5
  delivered & paid  7.5   × 0.70   =   5.25
  GMV paid on       5.25  × ₹1,800 = ₹9,450
  commission @ 5%                  =   ₹472.50
  EPC                              =   ₹0.47   (≈ $0.0053)

Optimistic: 20 → 14 → 10.5 → ₹18,900 @ 7.5% → EPC ₹1.42
```

**Benchmark check:** global average affiliate EPC is **$0.45 (~₹40)**. Aura's
modelled EPC is **~1% of that.** Not a modelling error — the global figure is
dominated by finance, travel and SaaS. India fashion at ₹1,800 AOV and 3.75–5%
net cannot produce a dollar-scale EPC. Fashion is separately documented as a
low-income affiliate niche (~$2,049/month typical).

**Revenue per MAU per month: ₹0.21 (base) to ₹1.42 (optimistic).**
Revenue per converting user: **₹90** (range ₹68–₹187) — and with 72% of shoppers
deleting after one purchase, that is also the lifetime value of most users.

### 9.7 Break-even

`LIKELY` Indian salary anchors 2026: Bengaluru SWE ₹9.2–10.2 LPA average, 3 years
₹10–18 LPA, strong freshers at Swiggy/CRED/Meesho ₹18–24 LPA; PF/ESI adds
₹8,000–12,000/month per head.

| Scenario | Monthly burn | Break-even @ ₹0.21/MAU | @ ₹1.42/MAU |
|---|---:|---:|---:|
| **Two founders unpaid**, infra + LLM + tooling only | ₹40,000 | **190,000 MAU** | **28,000 MAU** |
| Two founders at ₹1L/month each + ₹50k costs | ₹2,50,000 | 1,190,000 MAU | 176,000 MAU |

**Now apply retention.** At ~2% day-30 retention, *holding* 190,000 MAU implies
acquiring on the order of **9.5 million installs**. Even the most favourable cell
— founders unpaid, optimistic EPC — needs **28,000 monthly actives**, which for a
conversational agent with no distribution is 12–24 months of organic growth,
self-financed, with cash arriving 4–6 months in arrears.

### 9.8 WhatsApp is arithmetically impossible

`VERIFIED arithmetic on sourced inputs` At **₹1.09 all-in** per delivered
marketing template, and India-sourced benchmarks of **65–90% measured read** and
**5–15% healthy broadcast CTR** (not the vendor-marketed 98%):

```
Per 100 marketing templates sent:
  cost                    100 × ₹1.09        = ₹109.00
  clicks @ 10% CTR                           =  10
  revenue (base)          10 × ₹0.47         =   ₹4.70   →  4.3% of cost recovered
  revenue (optimistic, 15% CTR) 15 × ₹1.42   =  ₹21.30   → 19.5% of cost recovered
```

**Aura loses 80–96% on every WhatsApp broadcast.** Break-even at 10% CTR requires
an **EPC of ₹10.90 — 23× the base case and 7.7× the optimistic case.** No
combination of India fashion AOV and commission rate reaches it.

**Push notification is free and WhatsApp is not.** WhatsApp is defensible only for
service-window messages or a paying cohort — never for persona-matched
recommendation broadcasts to the general base.

### 9.9 The other routes, ranked

| Rank | Route | Cost | Time to data | Legal risk | Monetisable? |
|---|---|---|---|---|---|
| 1 | **Shopify Global Catalog MCP** | ₹0 | <1 day | Low (developer route) | **No** |
| 2 | **Per-store `/products.json`** | ₹0 + VM | 2–3 days | Low (robots.txt permits) | Only if brand has a programme |
| 3 | **Affiliate network feeds** (Admitad India, 200 advertisers) | ₹0, revshare | 1–2 weeks | None | **Yes — same object** |
| 4 | Bright Data datasets | $0.0025/record → ~₹2.2L per 1M | Days | Vendor-indemnified | No |
| 5 | Scraping Myntra/Ajio | ~$3,000/1M/refresh + 0.3–0.5 FTE | 2–6 weeks | **High** | No |
| 6 | ONDC buyer app | ₹5–25L + ₹15–50k/mo | 3–5 months | Low | Wrong model |

`LIKELY` **ONDC ranks last and should be dropped.** Build cost ₹5–25 lakh, 3–5
months to MVP, 6–12 to production; requires FQDN, SSL for OCSP validation,
separate BAP/BPP certificates, registrar approval, pre-prod then production
gating. **Demand is falling, not rising** — retail orders peaked at 6.5M/month in
Oct 2024 and fell to 4.6M by Feb 2025 as incentives were cut (monthly incentive
cap ₹3 crore → ~₹30 lakh). And monetisation is structurally wrong: buyer apps earn
a **buyer finder fee charged to the seller** (Paytm charged 3%), which requires
seller-side contracts and makes Aura a marketplace — contradicting the entire
"affiliate only, no checkout" thesis.

`VERIFIED / UNCERTAIN` **Commercial vendors sell the wrong product.** Bright Data
is the only one shaped correctly, at $0.0025/record ($250 minimum) — ~$2,500 per
1M SKUs one-time, ~$10,000/month for weekly refresh at list. **42Signals caps all
plans at 200 SKUs** — off by 3–4 orders of magnitude. DataWeave and Semantics3
publish no per-record rate card; both are price-intelligence tools sold to brands,
not catalogue suppliers to discovery apps.

`LIKELY` **Scraping India has no safe harbour and one bad precedent.** India has
**no scraping statute and no sui generis database right**. The framework is IT Act
2000 **s.43** (compensation for accessing/copying without permission — the
government has stated scrapers of public data "may be in breach"), **s.66**
(criminal only with dishonest intent), and the Copyright Act 1957 (compilations
protected where selection/arrangement shows minimum creativity — *Eastern Book
Company v. D.B. Modak*). **In OLX v. Padawan Ltd. the Delhi High Court granted a
permanent injunction** restraining automated or manual scraping of listings,
accepting that they formed a proprietary database qualifying as an original
literary work. That is the closest Indian analogue to scraping a marketplace
catalogue, **and the platform won.** *ANI v. OpenAI* concerns AI training, not
catalogue copying, and offers no comfort. `VERIFIED` Cost: Apify's Myntra scraper
charges **$0.003/product** — $3,000 per 1M-SKU refresh, ~$12,000/month weekly —
plus an `ESTIMATE` **0.3–0.5 FTE** permanently on anti-bot and schema drift, which
for a two-person team is 15–25% of engineering capacity producing zero
differentiation.

`LIKELY` **Correction to §9's earlier prior:** the sub-network list for
Myntra/Ajio is **six, not three** — Cuelinks, EarnKaro, ExtraPe, Admitad India,
vCommission, INRDeals. Admitad India's product-feed page renders **"Advertisers
found: 200"**, supports CSV/XML/YML/GMC formats, and gives publishers free feed
access on signup — **but size, gender and colour must be passed inside a `param`
tag, so attribute depth depends entirely on what each advertiser uploads.** How
many of the 200 are Indian *and* fashion could not be verified without an account.

### 9.10 The single most likely reason Aura never earns its first ₹1,000

> **Aura will recommend, beautifully and correctly, from a catalogue it has no
> affiliate link for.**

The route that makes Aura demoable — Shopify's free Global Catalog, with occasion
tags already written into the metadata — is the route where **~97% of sellers have
no affiliate programme at all**. The merchants that *do* pay publish no product
feed, force sub-network access, run 1-day cookies against a 10-day consideration
cycle, and pay the **3.75% existing-customer tier** to an audience that already
has their apps installed.

The failure is neither technical nor legal. **Supply and monetisation are two
disjoint sets, and every incentive in the build — the free API, the good demo, the
pretty long-tail brands, the haldi tags already written for you — pulls the team
toward the unmonetisable one.**

Fifteen delivered, attributed orders is not a hard number to hit. It is only hard
to hit if the first six months go into the wrong half of the problem — and right
now the wrong half is the free, easy, fun, fully-solved half.

---

## 10. Open questions that should be closed by conversation, not search

Ranked by how much the answer would change the plan. None of these can be settled
by more desk research.

1. **How many of Admitad India's 200 product-feed advertisers are Indian *and*
   fashion?** This directly sizes the only route where supply and payment are the
   same object — i.e. it sizes the business. Needs a publisher account.
2. **Are Cuelinks' displayed payout percentages gross or net of the 75:25
   revshare?** A logged-in dashboard settles it; it swings the model 25%.
3. **What fraction of Indian affiliate clicks actually attribute when the merchant
   app is installed?** No public data anywhere. The 50% estimate swings revenue
   2×. Only measurable by pushing ~1,000 real clicks through Cuelinks and
   reconciling against merchant-side reporting.
4. **Does GoAffPro or UpPromote expose a publisher-side discovery API?** If one
   integration could enumerate and join hundreds of small Indian D2C programmes,
   it would lift affiliate coverage of the Shopify catalogue from ~3% to something
   viable. **This would be the highest-value engineering task in the entire
   project.** No evidence found either way.
5. **Is there a per-merchant UCP path to affiliate attribution?** The Global
   Catalog's `checkout_url` carries `utm_source=shopify&utm_medium=catalog` and no
   slot for a third-party affiliate ID. Whether a merchant will honour an appended
   affiliate parameter on the `variant.url` deep link is untested — and it is the
   crux of whether route 1 can ever be monetised.
6. **When do Shopify "promoted placements" ship and what do they pay?** Shopify
   has said developers will get *"a **future** path to earn revenue when their
   Catalog-powered experiences drive sales."* Future, not present. If it ships it
   collapses routes 1 and 3 into one and changes Aura's economics fundamentally.
   **The single highest-leverage external event to monitor.**
7. **Will Shopify meter or price the Global Catalog MCP?** No published rate
   limits, SLA or commercial terms.
8. **How good are Myntra Maya, Flipkart SLAP and Rufus India at real occasion
   queries?** Twenty prompts, graded. Still the thesis — and now sharpened by the
   discovery that Shopify already ships occasion tags for free.
9. **Why did Alle pivot six times?** The founders are reachable ex-Meesho
   operators in Bengaluru. One conversation is worth more than all of this.
10. **Is "save it and decide later" compatible with 1-day cookies at all?** This is
    a product-form question, not a research one, and it may be existential.
11. **Does a pure-AI stylist clear India's trust bar**, given 76% of Indian
    consumers want interactions to feel human and Stylz deliberately pairs AI with
    human stylists?
12. **What are Myntra's and Ajio's actual AOVs?** Not published anywhere; every
    public figure is an estimate. ₹1,800 vs ₹1,200 is a 33% revenue swing.
