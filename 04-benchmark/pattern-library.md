# Pattern Library — Transcom Digital (Phase 4)

> **Source:** `04-benchmark/agents/global-commerce.md` (12 patterns) + `electronics-commerce.md` (11 patterns) + `regional-commerce.md` (10 findings) · `03-opportunities/opportunity-pool.md` (15) · `02-ux-audit/issue-register.md` (32)
> **Purpose:** Reusable, problem-centered library. Not a competitor dump. Each problem groups 2–4 interchangeable pattern variations observed across benchmarks with example platforms, why they work, and maturity.
> **Usage:** Pick a PROBLEM → choose a variation by maturity/effort → wire to Transcom gap listed. Patterns are modular: same install-fee table feeds delivery, EMI, and compare cost-pin; same dimension spec feeds inspection and install.

---

## Maturity Legend

| Tag | Meaning |
|-----|---------|
| **STANDARD** | Expected baseline in vertical/region. Absence is a hygiene gap. |
| **EMERGING** | Adopted by 2–3 leaders; becoming expectation in 2025–26. |
| **DIFFERENTIATOR** | Done well by 1–2; clear competitive edge if executed. |
| **EXPERIMENTAL** | Novel, unproven at scale; use as bet only. |

> Regional note: a pattern STANDARD globally (e.g., pincode check) can be EMERGING in Bangladesh and therefore a window.

---

### 1. PROBLEM: Users cannot confirm delivery, cost, or timeline before committing to a high-ticket purchase

*Transcom gaps:* PDP-02 P1 HIGH (`page-analysis.md:125` `Enable your Location` gate), CHECKOUT-02, PDP-03 install fee, `ecommerce-capabilities.md:42-44` delivery gated, `opportunity-pool.md:5-20` OPP-01. Buyer asks "can this 600L fridge / 1 Ton AC reach Rajshahi, when, at what fee, with free install?" and gets a permission prompt.

| # | Pattern | Description | Why It Works | Example Platforms | Maturity |
|---|---------|-------------|--------------|-------------------|----------|
| 1A | **Pincode / Area-First Serviceability Input** | Single text field `Enter pincode / district / area` + `Check` placed between price block and Add to Cart. No browser geolocation permission. Validates against zone/SLA matrix. Result persists in session. | Moves failure before commitment. Text entry > permission gate in 64-district Bangladesh where pincode literacy is low and location anxiety high. 20% memory, 80% ops data. | Amazon.in, Flipkart (India), Daraz Fast Delivery (BD — Aug 2026, 50k SKUs), Best Buy ZIP estimator (US), AO.com | **STANDARD** (South Asia) / **EMERGING** (BD outside Daraz) |
| 1B | **Landed-Cost Truth Row with Store-Pickup Alternative** | Response card in one line: `✓ Deliverable to 1212 Dhaka — 2–4 days — Delivery Tk 0 — Installation Free (bracket extra) — Nearest pickup: Dhanmondi 1.2km (in stock)` OR `✗ Not deliverable — Nearest pickup: X km`. Propagates to Cart `Subtotal + Delivery + Install → Total` without re-entry. | Answers price-exposure question with money + time + alternative. Cart inheritance prevents checkout pincode-mismatch drop-off. Store alt converts undeliverable into pickup. | Best Buy (estimated arrival by ZIP), Currys (7-day delivery), Daraz Choice (single-warehouse), AO.com | **STANDARD** (IN/EU) / **EMERGING** (BD fee/SLA transparency) |
| 1C | **Fast-Delivery / Serviceability Badge on PLP** | PLP card/filter tag `Fast Delivery` or `Deliverable to your area` earned via proven fulfilment, not bought. Lets users browse only quickly-deliverable items before opening PDP. | Pre-filters consideration for urgency; earned tag signals ops reality vs marketing claim. Mirrors EMI36 badge pattern already on Transcom PLP. | Daraz Fast Delivery tag + filter (BD), Pickaboo 3-Hour Express, Flipkart 100% serviceable pincode (19k) | **EMERGING** (BD) |

---

### 2. PROBLEM: Users must translate a life need (room, family, distance) into a technical spec they don't understand

*Transcom gaps:* IA-03 P1 (SEO wall pushes grid below fold, `page-analysis.md:90-91` 1,500+ words), PDP-03 P1 (room-fit/energy buried), PDP-04/PDP-05 (spec opaque). No bridge between "120 sq ft top-floor room" → "1.5 Ton, EER 3.15, R32".

| # | Pattern | Description | Why It Works | Example Platforms | Maturity |
|---|---------|-------------|--------------|-------------------|----------|
| 2A | **Room-Size → Tonnage / BTU Calculator (AC Finder)** | 3-field wizard: `sq ft × ceiling height × top-floor/sun/occupancy` → tonnage/BTU verdict + `See suitable Inverter ACs` filtered PLP + PDP chip `✓ Fits your 120 sq ft`. Rule table validated against brand spec (e.g., Daikin `Applicable for 120 sq ft`). Formula exposed, not ML. | Deterministic, auditable. Removes wrong-size risk (short-cycle, poor cooling). Top-floor correction tuned to Bangladesh climate. | LG Air Conditioner Calculate (EG/global), LG Home Comfort (CA) `20 BTU/sq ft`, Coolblue advice `choose-your-tv-size` (same mechanic), Crutchfield | **STANDARD** (HVAC calculators) / **EMERGING** (retailer-integrated AC finder) |
| 2B | **Capacity → Family + Shopping-Bag Ladder + Doorway Guard (Fridge Validator)** | Ladder: litres → bags (`AO: 18L = 1 bag`) → family size (`Up to 150L → 1–2 persons / 250–350L → 3–4 / 400L+ → 5+ / American 400–700L`). + 7-step measurement guard: niche H/W/D, doorway/hall, 90° hinge scrape (5cm), 1–2cm ventilation gap, water-line proximity. PDP guard: `Will it fit? Check your space` dimension overlay. | Litres are meaningless; bags/family is instant. Guard prevents most expensive failure — delivery rejected at door. One dimension source feeds inspection (4) and install (10). | AO.com (71–655L bag ladder), Currys `How to measure if fridge freezer will fit` (7 steps) | **STANDARD** (UK) / **DIFFERENTIATOR** (BD — bag translation + guard combined) |
| 2C | **Viewing-Distance → Size Advisor + Panel Explainer (TV)** | Inputs: distance + brightness + use → 2–3 size options with room overlay. RTINGS SMPTE 30° / THX 40° table (32"→4ft, 55"→7ft, 65"→8ft). Embedded row: QLED vs HQLED vs Dolby Vision in tap-to-explain (brightness, angle, energy delta). CTA → pre-filtered PLP. | Size is highest-regret TV decision; distance math is deterministic. Panel explainer decodes `HQLED` without leaving PDP. | Samsung DE `help-me-choose`, MediaMarkt TV-Kaufberater, RTINGS Size-to-Distance tool | **EMERGING** |
| 2D | **Interactive Buying Guide as Layered Wizard (Framework Wrapper)** | Buying guide lives at `/buying-guides/{category}` — wizard `Need → Constraints → Budget` outputs filtered PLP URL. PLP CTA: `Not sure what size? 30-sec guide`. SEO long-form moves below pagination, not above grid. Grid stays above fold. | Preserves SEO equity while removing scroll cost. Respects two intents: "know what I want" (filters/grid) vs "need guidance" (wizard). Wizard → filtered PLP converts higher than raw PLP. | Currys buying-guides hub (oven, fridge, washer, coffee), Coolblue advice → quiz | **STANDARD** (UK/EU) |

---

### 3. PROBLEM: Users struggle to compare technically similar high-ticket products without memory overload

*Transcom gaps:* INTERACTION-01 P1 HIGH (`/compare` 3 empty `Model name or part of product details` inputs, `page-analysis.md:173-178`), PDP-08 variant mismatch, `ecommerce-capabilities.md:23` Compare empty. Journey D is recall task.

| # | Pattern | Description | Why It Works | Example Platforms | Maturity |
|---|---------|-------------|--------------|-------------------|----------|
| 3A | **Persistent Auto-Populated Compare Workspace** | Sticky bar `Compare (2/3)` accumulates PDP `Add to Compare` taps (session + auth). `/compare` auto-populates from bar; no typing. Search remains only as `Add product`. Shareable URL `?ids=a,b,c` survives without login. | Recall → recognition (Nielsen). Survives reload and WhatsApp family share — critical for BD family decision. | Coolblue (up to 4 specs), Best Buy `/site/compare?skus=...`, Samsung TV comparison, Daraz (thin — opportunity) | **STANDARD** (considered electronics) |
| 3B | **Highlight Differences + Decisive-Attribute Tint** | Toggle `Highlight differences` dims identical rows. Category-tuned decisive rows tinted: AC `EER/tonnage/R32/Applicable sq ft`, TV `panel/HDR/zone count`, Fridge `litres/door/inverter`, Washer `kg/drum/motor warranty`. + Verdict strip `Best value for 120 sq ft: Daikin 1.5T — lowest 5-yr cost`. | Collapses 40-row scan to 6–8 decisive rows. Tint + verdict make spec overload scannable without normalizing entire Spec tab. | Best Buy (Show only differences), RTINGS scored lab table (8–12 decisive rows, green winner), Coolblue decisive tint | **STANDARD** (diff toggle) / **DIFFERENTIATOR** (verdict strip) |
| 3C | **Total-Cost Pin Row (Price + Install + Energy + EMI/month)** | Pinned bottom row in compare table: `Product + Delivery + Install + 1yr energy + EMI/month` computed from patterns 1 & 5 feeds. Same row propagates to Cart. | Answers "which is actually cheaper to own?" Energy dominates sticker delta over 5 years; transparency builds trust vs hidden fees. | RTINGS value scoring, Amazon A+ comparison table (8–20% lift claimed), Best Buy total-cost pin | **EMERGING** (BD) / **DIFFERENTIATOR** (energy+install+EMI combined) |

---

### 4. PROBLEM: Users cannot inspect large appliances remotely with enough realism to commit

*Transcom gaps:* PDP-01 P1 HIGH (`page-analysis.md:134-135` 4+ generic image containers, `ecommerce-capabilities.md:29-30` Video NOT OBSERVED, 68 DOM images no player), `product-page-variations.md:49-50`.

| # | Pattern | Description | Why It Works | Example Platforms | Maturity |
|---|---------|-------------|--------------|-------------------|----------|
| 4A | **Hover / Pinch Zoom + Thumbnail Scrub + Count Indicator** | Desktop hover-lens zoom; mobile native pinch; thumbnail strip with `1/7` count and scrub. No asset reshoot — pure viewer upgrade. | Highest anxiety reduction per effort. Validates wall/size/drum before store visit. Lazy-load + muted protects `MOBILE-01` weight. | Apple (iPhone/Mac), Samsung TV bezel video + 360° | **STANDARD** |
| 4B | **Functional Video per Category Template (15–25s)** | Short demo — AC on wall with piping, TV panel/HDR, washer drum spin, fridge door swing — not generic brand film. Reuses existing brand 15s reels. | Education before commitment lifts considered categories >20%. Category template scales without reshoot. | Dyson airflow video, Samsung panel depth video, Coolblue feature reels, Amazon A+ video guidance (85% main image + 6 support images = Very High Impact) | **STANDARD** |
| 4C | **360° + Dimension Overlay + AR Placement** | Where brand asset exists: 360° viewer. Dimension drawn from structured spec onto hero: `600L — 1780×912×645 mm + 50mm ventilation gap + door swing`. Optional AR: `View TV virtually in your room` (app/deep-link). Spec W×H×D is not just a tab row. | Answers "will 65" fit my wall? will 600L clear doorway?" Same dimension source feeds install checker (10). AR is phase 3. | Coolblue `View TV virtually in living room`, Currys/Coolblue `What are dimensions of my fridge?`, Apple dimension diagrams | **STANDARD** (360/overlay) / **EMERGING** (AR) |

---

### 5. PROBLEM: Users see only sticker price and cannot judge true monthly affordability

*Transcom gaps:* PDP-06 P2 (EMI present on AC/TV but silent on Haier 622L fridge, `product-page-variations.md:55`), CONSISTENCY-01 (`EMI36` badge vs `Avail Bank EMI`), PDP-03 energy hidden as `EER 3.15` token, `opportunity-pool.md:139-149` OPP-09.

| # | Pattern | Description | Why It Works | Example Platforms | Maturity |
|---|---------|-------------|--------------|-------------------|----------|
| 5A | **Interactive EMI Tenure + Bank Picker with Monthly Re-calc** | PDP ownership sub-row: `EMI from Tk 2,633/mo ×36m @ Standard Chartered — choose bank/tenure [3/6/12/24/36]`. EMI rule table (SKU → banks × tenures → factor) from finance master; dropdown re-calculates live. | Monthly framing is primary for BD bank-card EMI (32-bank network). Picker at price exposure de-risks financing before paywall. | Pickaboo 0% EMI up to 36m (32 banks, BDT 5k threshold), Daraz EMI (BDT 10k per-product), Amazon.in EMI `From ₹X/mo`, Best Buy financing calculator | **STANDARD** (BD electronics badge) / **EMERGING** (interactive picker) |
| 5B | **Single Ownership Row: Upfront + Delivery + Install + Energy → EMI/month** | One PDP line beneath sale price: `Upfront 1,38,605 | Delivery Tk0 | Energy ~Tk 420/mo (EER 3.15 @8h/day) | EMI from 3,863/mo ×36`. Tariff × EER + running-hours slider → `Tk/mo` and `1yr/5yr`. Cart inherits as grouped breakdown. | Converts abstract `EER` into money — only unit driving trade-off between two models differing by Tk5k upfront but Tk8k/yr in energy. Collapses three scattered truths. | Currys/MediaMarkt energy-label cost + Klarna monthly, Home Depot protection-tier pricing, AO energy `149kWh/yr → £39/yr` translator | **DIFFERENTIATOR** (BD combined row) / **EMERGING** (interactive energy) |
| 5C | **Explicit Eligibility Verdict (Trust Repair)** | When EMI unavailable: `EMI not available for this SKU → see EMI Bank List` with reason (threshold, bank exclusion, Dhaka-only) — not silence. Suppresses planner for low-ticket (trimmer 3k) where irrelevant. | Silent absence reads as bug; verdict reads as policy clarity. Mirrors Pickaboo/Daraz transparency (Daraz: Dhaka-only 0% EMI; 7–10 day form). | Pickaboo tenure-varies-per-product disclosure, Daraz Dhaka-only + reflection timeline, Amazon.in bank-exclusion copy | **EMERGING** (trust repair through explicit "no") |

---

### 6. PROBLEM: Users distrust authenticity, peer proof, or warranty when stakes are Tk 50k–1.5L

*Transcom gaps:* TRUST-01 P2 (`Free Installation / Original Product Guaranteed` claims on homepage `page-analysis.md:34` not echoed on PDP/Cart), PDP-07 P1 HIGH (tabs exist, no aggregate stars/count, `ecommerce-capabilities.md:31-33`), PDP-05 P2 (warranty `Parts-0M / Motor-300M` implausible), FILTER-02 P2 (Customer Review heading empty).

| # | Pattern | Description | Why It Works | Example Platforms | Maturity |
|---|---------|-------------|--------------|-------------------|----------|
| 6A | **Authenticity / Mall / Verified Badging at Price Context** | PDP hero lockup: `✓ Authorized — Official Warranty` + `Authenticity Guarantee — replacement + 3× cash back if fake` + flagship-store/Mall tag + seller identity + warranty detail sheet. Echoes homepage `Original Product Guaranteed` at the decision moment. | Marketplace variance is BD #1 trust barrier (post-Evaly). Authorization proves moat vs Daraz variance. Tied to brand partnerships (13 brands). | DarazMall `Authenticity Guarantee + Mall tag`, Pickaboo `100% genuine 400+ brands + 0 tolerance`, Bikroy `Verified Badge` (NID/Trade License + 6-month tenure), Star Tech `20+ stores + ISO 9001` physical proxy | **STANDARD** (BD marketplace) / **DIFFERENTIATOR** (retailer PDP proof) |
| 6B | **Social Proof Layer: Aggregate Rating on PLP + Review Facet + Verified Q&A** | Pipeline `Collection → Moderation → Aggregation → Badges → Facet`. PDP header `4.6★ 212` above fold near price; every PLP card `4.6★ (212)` (suppressed if n<5 → `Be first to review`); `Customer Review` facet buckets `★★★★ & up (41)` populated by real index; Q&A with `Verified Purchase` marker. | Shortlist by peer validation, not price alone. Verified-purchase matters disproportionately for high trust sensitivity. Populates currently broken Customer Review filter — two gaps, one pipeline. | Amazon (Verified Purchase + Q&A, 2,184 counts), Best Buy (4.6★ 212 on PLP + star facets), Sephora photo reviews, Coolblue own-reviews facet | **STANDARD** |
| 6C | **Spec Jargon Decoder + Energy Label → Tk/month Translator** | Tap any underlined spec term → drawer/tooltip: `EER 3.15 = 1.1kW draw → ~Tk Y/mo @8h/day @Tk Z/kWh`; `R32 = refrigerant class`; `Twin Inverter = 20% lower fluctuation → ~Tk Y/mo saving`; `Special Component = Compressor/Panel/Motor per category` legend. Energy label visual + `Cost = annual kWh × unit rate` formula. Glossary CMS 25–40 terms, category-scoped. | Literacy is prerequisite for finders and cost calculator. Transparent formula > claim. Keeps buyer on PDP instead of Googling. | Energy Saving Trust A–G explainer + QR fiche, Citizens Advice `kWh × rate` formula, Selectra/Ofgem tariff calculators, AO `kWh/yr → £/yr`, Currys inline buying guides | **STANDARD** (EU energy communication) / **EMERGING** (inline BD decoder) |

---

### 7. PROBLEM: Users fail to find an exact model (alphanumeric SKU) or hit a dead-end on typo / narrow filters

*Transcom gaps:* SEARCH-01 P1 (suggestions NOT FULLY VERIFIED, `product-discovery.md:40-43` timed out), SEARCH-02 P3 (`Search Here` generic), SEARCH-03 P2 (zero-result NOT TESTED, `ecommerce-capabilities.md:15`), `opportunity-pool.md:101-132` OPP-07/08.

| # | Pattern | Description | Why It Works | Example Platforms | Maturity |
|---|---------|-------------|--------------|-------------------|----------|
| 7A | **Predictive Autocomplete with SKU-Boost + Recent Searches** | Debounced (150–200ms) typeahead after 2 chars. Rows: `Product (title+price+stock+thumb)` ranked, `Brand (Samsung 14)`, `Category (Smart TV)`, `SKU exact` when query has 3+ alphanumerics (`ftkl` → `Daikin FTKL12TV16WD — 1 Ton — Tk 81k — In stock` ranked first). Header: `Recent: samsung 55" | daikin 1 ton` chips (localStorage 6). Placeholder scent: `Try FTKL12TV16WD or Samsung TV 55"` | SKU substring match wins for electronics where buyers photograph codes in-store. Recent chips recapture interrupted research. Type→tap→PDP shortens funnel vs type→submit→PLP→select. | Amazon (typeahead with count), Flipkart (SKU-aware alphanum), ASOS, John Lewis, Daraz BD (Bangla/English mixed) | **STANDARD** (autocomplete+recent) / **STANDARD** (SKU-boost in electronics) |
| 7B | **Zero-Result Recovery: Did-You-Mean + Typo Tolerance + Facet Relaxation** | Fuzzy index (edit distance 1–2) + brand/synonym table. Zero-result page: `No exact for "FTLK12" — did you mean "FTKL12"? 3 results` + `Try removing: Brand Samsung (→12 results)` with count preview + `Related: daikin 1.5 ton` + advisor CTA `Not sure? Try AC Finder`. Tracks top zero-result queries. | `FTLK → FTKL` is intent, not failure. Facet relaxation answers "am I filtering myself into zero?" — shows brand filter is culprit vs catalog gap. | ASOS `Did you mean…?`, John Lewis & Zalando `Remove Brand → N results`, Wayfair, Amazon related searches | **STANDARD** (typo tolerance) / **EMERGING** (facet-relax count preview) |
| 7C | **Typo-Tolerant Alphanumeric + Bangla-English Symmetry** | QWERTY-adjacent fuzzing (`L↔K`) for model codes; Bangla digit/letter → English mapping; synonym table `inverter = invator`. Recovery not suggestions — brackets both sides of submit. | Catches high-intent buyers who mistyped code or mixed language; recovers 12–18% of zero-result sessions in electronics per Amazon/Flipkart logs. | Flipkart alphanum matching, Daraz Bangla query handling | **EMERGING** |

---

### 8. PROBLEM: Users lose research progress across sessions, devices, or after navigating away

*Transcom gaps:* DISC-02 P1 HIGH (Journey F unserved), `personalization-current-state.md:7-9` Recently Viewed & Continue Shopping NOT OBSERVED, empty cart/wishlist no recovery (`page-analysis.md:159-164`), `opportunity-pool.md:21-36` OPP-02.

| # | Pattern | Description | Why It Works | Example Platforms | Maturity |
|---|---------|-------------|--------------|-------------------|----------|
| 8A | **Recently Viewed Horizontal Rail (Anonymous → Auth)** | Last 8 PDPs with thumbnail + price + `In stock / Currently Unavailable` badge. Appears on homepage below hero, PLP sidebar, PDP footer, and empty cart/wishlist as recovery. `localStorage viewHistory`; merged to account on OTP login via same `0157…`. Swipe on mobile, cap 8, newest first. | Cheapest retention lift — anonymous localStorage + two rails, no backend. Captures highest-intent returners who already invested in finding `Inverter AC 1.5T`. More durable than cookie on mobile. | Amazon `Pick up where you left off`, Zalando/ASOS horizontal rail, eBay Recently viewed, Daraz viewed history strip | **STANDARD** |
| 8B | **"Continue Where You Left Off" Filter-Restore Deep-Link** | Card: `Smart TV: Samsung 55"+, 1–2L (14 results) — Continue` that reopens last filtered PLP/search with query + facets reapplied from `localStorage lastPlpUrl` (title + facet summary). Not a static link. | More powerful than item rail: restores `Brand=SAMSUNG(14) + 55" + Price 0–1L` state, not just one PDP. Pairs with Recent Searches (problem 7) — item-based + intent-based re-entry. | Amazon `Continue shopping`, eBay Watchlist + deep-link, Zalando/ASOS continue strip | **STANDARD** (item trail) / **DIFFERENTIATOR** (BD filter-restore deep-link) |
| 8C | **Empty-Cart / Empty-Wishlist Recovery Injection** | Empty state replaces dead-end with rails + deep-link + `You have not added…` plus `Recently Viewed` and `Continue Shopping`. Cross-sells from affinity when available. | Converts abandonment moment into resumption. Supports CART-01 P1 + AUTH-02 guest save feedback gap. | Amazon empty-cart recommendations, eBay empty watchlist rail, Daraz (partial) | **STANDARD** |

---

### 9. PROBLEM: Users filtered by size/capacity on listing but cannot explore sibling variants on product page

*Transcom gaps:* PDP-08 P2 (only AC shows `Choose Ton 1 / 1.5`, `product-page-variations.md:52`; TVs/Washers/Fridges have no switcher despite `page-analysis.md:86` `Display Size 55"(10) 43"(7) 65"(7)` family), IA-01 flat URL severs hierarchy, `opportunity-pool.md:199-213` OPP-13.

| # | Pattern | Description | Why It Works | Example Platforms | Maturity |
|---|---------|-------------|--------------|-------------------|----------|
| 9A | **Sibling Variant Chips with Price Delta & Stock Badge** | Beneath PDP title or above Add to Cart: chips sorted by dimension — `55" — Tk79,900 — In stock | 65" +Tk18,000 — In stock | 75" — Currently Unavailable` (+ `Get Stock Alert`). Current variant active; siblings show delta + stock. | Price delta + stock prevents surprise; disabled style signals availability before click. | Apple (Storage/Color/Size chips), Samsung TV size chips `43/55/65 +delta`, Sony TV family `X80K 43/50/55/65`, Uniqlo/Decathlon (same data model) | **STANDARD** |
| 9B | **Family Graph Navigation (PDP-to-PDP, Not Tab Toggle)** | Chip click navigates to sibling PDP (new URL) in family graph `model_root → variants by tonnage/litres/display size/kg`. History preserves `?familyRef` so Compare (3) and Recently Viewed (8) capture family context. PLP facets stay scoped on return. | Connects PLP facet taxonomy to PDP exploration — without chips users must hit back to PLP and lose context. Compensates for flat PDP URL (`IA-01` — family gives PDP hierarchy URL lacks). | Apple family nav, Samsung, Sony, Coolblue | **STANDARD** |
| 9C | **Variant Switch Re-validates Delivery / Energy / EMI** | Chips placed above delivery estimator (1) so size change re-checks `Deliverable + Install + EMI/month + Energy` before Add. Suppressed when family <2 variants (safe default). | Size change is not cosmetic — it changes deliverability, running cost, and financing. Wiring prevents stale truth after switch. | Coolblue variant-aware estimator wiring (implicit) | **EMERGING** (integrated wiring) |

---

### 10. PROBLEM: Users fear ordering a large appliance they cannot install, connect, or fit

*Transcom gaps:* PDP-03 P1 HIGH (no feasibility signal, `page-analysis.md:126-128` no install line, `product-page-variations.md:60` NOT OBSERVED), `ecommerce-capabilities.md:45` `Free Installation Selective Items` vague, PDP-05 warranty opaque, `opportunity-pool.md:182-196` OPP-12.

| # | Pattern | Description | Why It Works | Example Platforms | Maturity |
|---|---------|-------------|--------------|-------------------|----------|
| 10A | **Feasibility Checker with Pass/Fail Verdict (Gate 1 — Content Only)** | PDP `Installation` row beneath Warranty, per category: AC `outdoor wall? bracket? drain? socket within 1.5m?`, Fridge `ventilation 1" gap? floor strength? door swing 90° + hinge 5cm?`, Washer `inlet/drain + floor level + shut-off within 4ft`. Toggles → `✓ Feasible — Add to Cart` / `⚠ Requires bracket Tk2,500 — order bundle`. Fee table per SKU (`Free install Yes/No — Fee Tk X`). Ships without calendar. | Eliminates most expensive failure — failed install. De-risks AC/Washer for buyers who need patterns 1 & 5 most. Brand signal for Transcom owned fleet vs marketplace Daraz/Pickaboo. | Coolblue Eigen Plan prerequisite check, Best Buy Geek Squad checklist, Currys/AO 7-step measure guide (feeds checker) | **DIFFERENTIATOR** (BD) / **EMERGING** (checker alone) |
| 10B | **Installation as Priced Basket Line Item (+ Haul-Away)** | Checkbox on PDP: `Add Installation` + `Add Recycling (haul away old appliance)` added as priced line items alongside product. Priced transparently: e.g., washer install Tk X / fridge free/paid / disposal Tk Y / American fridge doors removable surcharge. Scope, price, and `Before You Buy / Before We Deliver` checklist video shown. | Converts vague "installation included?" into purchasable SKU with scope, price, and gate. Prevents split-delivery failure. Suppress for Personal Care where generic. | John Lewis `Home Appliance Installation & Disposal` (£15–£115 install, £25 disposal), AO.com (`unpack, level, connect, remove doors`), Home Depot `hook-up parts required — will not reuse existing` | **STANDARD** (UK/US) / **DIFFERENTIATOR** (BD priced install as SKU) |
| 10C | **Bookable Slot Picker with Prerequisites & Reschedule (Gate 2 — Ops)** | Calendar by district/installer team, prerequisites ticked, fee if any, `order ↔ service-order` link, push notification, reschedule via `Track Your Service`. Post-purchase phase gated behind slot-capacity feed confirmation. | "Transcom will come, on this date, at this price" — date certainty is brand promise. Preresolution prevents booking on undeliverable sites. Tolerates rural 5–8 day window truthfully. | Coolblue Eigen Plan (delivery + installation slot), Best Buy Geek Squad appointment, Home Depot appliance install slots | **DIFFERENTIATOR** (ops-gated; <10% of SA retailers offer verified slots) |

---

### 11. PROBLEM: Users discover total setup cost only after delivery — missing accessories, stabilizers, or consumables

*Transcom gaps:* `product-page-variations.md:66-67` FBT NOT OBSERVED, `ecommerce-capabilities.md:56` FBT/Bundles NOT OBSERVED, `personalization-current-state.md:12` Cart-Based Recs NOT OBSERVED, Related Products thin single card (`page-analysis.md:159-164`), `opportunity-pool.md:72-85` OPP-05.

| # | Pattern | Description | Why It Works | Example Platforms | Maturity |
|---|---------|-------------|--------------|-------------------|----------|
| 11A | **Complete-the-Setup Bundle Row (Pre-Add, Toggleable)** | Rule engine `Family → complements`: AC → stabilizer / wall bracket / copper wire, TV → soundbar / wall mount / HDMI, Fridge → stabilizer, Washer → stand / detergent, Purifier → cartridge. PDP row `Add soundbar + wall mount → Save Tk X bundle price` with toggle before Add. Suppressed for low-ticket trimmer/mixer (generic). | One-trip ownership reduces "need extra part" dissatisfaction and lifts AOV/attach rate. Mandatory hookup-kit model (Home Depot) prevents install failure when tied to pattern 10. | Home Depot mandatory hookup kits (cord, gas flex, duct, water line — must add at point of sale), AO.com bundle row, MediaMarkt/Saturn | **STANDARD** (large appliances) |
| 11B | **Cart Post-Add "Complete Your Setup" Grouped Line** | After Add to Cart, cart rail `Complete your setup — add washer stand + detergent` with grouped-line pricing. Drawer/cart shows bundle as linked items, not loose cross-sell. | Captures attach after commitment without cluttering PDP. Grouped pricing makes add decision easy. | AO.com cart grouping, MediaMarkt cart bundles | **STANDARD** |
| 11C | **Consumable Cadence & Subscribe & Save** | Purifier PDP: `Replacement cartridge every 6 months — Subscribe & save`. Re-engages on interval via wishlist/alert. | Converts one-time appliance sale into recurring revenue; cadence reminder prevents post-purchase neglect. | AO/Currys purifier cartridge proximity check, Amazon Subscribe & Save (adapted) | **EMERGING** |

---

### 12. PROBLEM: Users need payment choice and human reassurance at the exact price/decision moment

*Transcom gaps:* CHECKOUT-01 P1 (checkout undiscoverable from empty cart, `user-journeys.md:126-131`), TRUST-01, AUTH-01 split OTP field P2, CART-01 P1 empty-cart dead-end, PDP-02 `TRUST-01`, `opportunity-pool.md:21-36` OPP-02; `regional-commerce.md:66-110` Findings 4/7/9.

| # | Pattern | Description | Why It Works | Example Platforms | Maturity |
|---|---------|-------------|--------------|-------------------|----------|
| 12A | **Plural Payment Row (COD + bKash/Nagad + Card-on-Delivery + Online/EMI)** | PDP beneath EMI row + Cart Order Summary shows co-equal choices: `◉ Cash on Delivery ✓ | ◉ Card on Delivery (Swipe) ✓ | ◉ bKash/Nagad ✓ | ◉ Online Card (EMI eligible) ✓` with district-aware `Delivery to Rajshahi: COD available` from same zone matrix as pattern 1. | COD is 75–90% of BD transactions (Levree 2026); bKash/wallet is second rail. EMI alone excludes most buyers. Choice itself is trust — like Pickaboo "various methods for your best convenience". | Daraz, Pickaboo (`Free Shipping, bKash, Card on Delivery, COD, Countrywide`), ChalDal, Rokomari, Levree COD 75–90% benchmark | **STANDARD** (BD) |
| 12B | **Open-Box Delivery + OTP Verification at Doorstep** | Opt-in for electronics >Tk20k on Order Summary: rider opens outer + brand packing in front of customer, checks damage/correct item/IMEI/accessories, customer shares OTP only after satisfaction, photographed + reference logged. Badge on PDP: `Eligible for Open Box Delivery at your pincode ✓`. | Solves "what if wrong/damaged at door?" — highest anxiety for 600L/TV 65"/AC 1T. Documentation burden shifts from buyer (self-unbox → return fight) to logistics. Proves `Original Product Guaranteed`. | Flipkart Open Box Delivery (both packings open + OTP + photo), India Post COD parcel integration (1.6L offices), vs Amazon India no-OBD burden | **STANDARD** (India electronics) / **EMERGING** (BD) |
| 12C | **Hotline-Sticky + Conversational Care (Human WhatsApp/Messenger)** | Elevate `16212 9AM–9PM` from footer to sticky call bar on PDP/Cart. `Need help? Click Here` (`page-analysis.md:14`) resolves to WhatsApp/Messenger PDP deep-link `Share via WhatsApp — Ask agent about this fridge` + hotline fallback. Optional premium manager for >Tk50k: `Get personal manager — message on WhatsApp` (agent handles order, tracks delivery, resolves post-delivery). | Bangladesh trust is human — phone + Messenger before site. Social influence β=0.13 and WOM drive purchase (BJMS 2025). Human manager converts Tier-2/3 where self-serve fails. | ChalDal 16710 phone-order + Premium Care WhatsApp agent, Facebook Commerce (thousands BD sellers), Rokomari chat, Transcom `Track Order Status / Track Your Service` header pattern, Daraz 16492 EMI conversion call | **STANDARD** (hotline in funnel, BD) / **EMERGING** (human WhatsApp manager) |
| 12D | **Cart Drawer & Checkout Transparency (Mini-Cart + Landed-Cost Stepper)** | Slide-in mini-cart on Add confirmation; Cart Order Summary `Subtotal + Delivery + Install → Total` with explicit `Free Installation` vs `Tk X`; progress stepper `Cart → Delivery → Payment → Confirm` with trust micro-copy. Feedback toast on every add/wishlist/compare to fix `FEEDBACK-01 P1`. | Visibility of system status + landed-cost truth before paywall. Stepper reduces `CHECKOUT-01` opacity; toast fixes "did it save?" uncertainty. | Apple, ASOS, Best Buy, Zalando cart drawer + stepper, Daraz Control Tower status wiring (65 hubs) | **STANDARD** |

---

## Cross-Cutting Wiring (Reuse, Not Repeat)

| Shared Data / Component | Feeds Patterns |
|-------------------------|----------------|
| Pincode / District → Zone/SLA + Delivery Fee + Install Fee + Store Inventory table | 1A, 1B, 1C, 5B, 8B, 9C, 12A/B |
| Dimension normalization (W×H×D + gap + swing + bracket) | 4C, 10A |
| EMI Bank/Tenure rule table + threshold | 5A, 5B, 5C, 12A |
| Tariff × EER → Tk/month formula | 5B, 6C, 10A |
| Family graph (model root → variants by dimension) | 3A, 9A, 9B, 11A |
| Glossary CMS (25–40 terms, category-scoped) | 2A–2D, 6C, 10A |
| `localStorage viewHistory + lastPlpUrl + compareQueue + searchHistory` + auth migration | 7A, 8A, 8B, 3A |
| Review aggregation + verified-purchase check | 6B |
| Store Locator feed (already `/store-locator` VERIFIED) | 1B, 10C, 12C (Schedule Visit linkage) |

---

## How to Apply

1. Start with hygiene STANDARD: 1A+1B, 5A+5C, 6A+6B, 7A, 8A, 9A, 11A, 12A+12D. Absence is conspicuous.
2. Layer EMERGING pre-consideration: 2A→2B→2C→2D (one wizard UI + lenses), 3B, 4A, 7B, 8B.
3. Differentiate where owned ops allow: 10A first (content-only), 10B/10C after slot feed, 11C, 12B, 3C/5B (True Cost row), 6C (decoder).
4. Suppress intelligently for low-ticket Personal Care (Tk3k trimmer, 5k mixer): suppress 1C, 5A/B, 10A/C, 11A for these per `cross-review.md:168` and regional EMI threshold BDT 5k.

---

*Library compiled from 33 benchmark patterns/findings without competitor-first grouping. Each row cites observed mechanic, not fame. For build sequencing see `03-opportunities/opportunity-pool.md:5-20` (P0/P1/P2) and `cross-review.md:234-243` M-gaps.*
