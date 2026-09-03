# Electronics & Appliance Commerce Benchmark — Agent B

> **Agent:** B — Electronics & Appliance Benchmark | **Phase:** 4 | **Date:** 2026-09-03
> **Scope:** High-consideration electronics & home appliance — AC (1/1.5 Ton), fridge (245L–600L), TV (32"–100"), washer (8KG), kitchen/small appliances
> **Knowledge base reviewed:** `00-input/sitemap-analysis.md`, `01-current-state/site-inventory.md`, `01-current-state/page-analysis.md`, `01-current-state/product-discovery.md`, `01-current-state/product-page-variations.md`, `01-current-state/user-journeys.md`, `01-current-state/ecommerce-capabilities.md`, `01-current-state/personalization-current-state.md`, `02-ux-audit/issue-register.md`, `02-ux-audit/executive-summary.md`, `03-opportunities/opportunity-pool.md`, `03-opportunities/cross-review.md`
> **Transcom Phase 2 gaps in scope:** PDP-03 (install/energy/room-fit buried in tabs/SEO), PDP-05 (warranty nomenclature inconsistent: Parts-0M / Motor-300M), no capacity calculators, no spec explainer, INTERACTION-01 compare friction, PDP-02 location-gated delivery, PDP-06 EMI inconsistency
> **Research method:** Verified live patterns via websearch (Best Buy, Currys, AO.com, John Lewis, LG/Home Comfort, Home Depot, RTINGS, MediaMarkt/Samsung DE, Energy Saving Trust) + cross-checked against `04-benchmark` market inventory. All patterns are problem-solving, not generic feature lists.

---

## How to Read This Document

Each pattern answers: *what decision does the customer fail without this, how does the leader solve it mechanically, and what would it mean for Transcom's Tk 50k–1.5L considered purchase?* Classification:

- **INDUSTRY STANDARD** — expected by most buyers; absence is a hygiene failure.
- **EMERGING** — adopted by 2–3 leaders; becoming expectation in 2025–26.
- **DIFFERENTIATOR** — done well by 1–2; clear competitive edge if executed.

---

### Pattern 1 — Persistent, Auto-Populated Compare with Highlight Differences

- **Company:** Best Buy (US/Canada) + RTINGS.com (reference standard)
- **Product Category:** TV, major appliances (fridge, washer), computing
- **Customer Decision Problem:** Shopper shortlists 3 Smart TVs (55" vs 65", QLED vs HQLED) or 3 side-by-side fridges (415L vs 600L) but spec differences are scattered across tabs. Memory fails; re-opening PDPs to compare EER, panel warranty, or drum size is high-friction. Transcom's `/compare` today requires typing "Model name or part of product details" into 3 empty search boxes (`page-analysis.md:173-178`, `issue-register.md:41` INTERACTION-01 P1).
- **Pattern:** Sticky compare bar + auto-populated comparison table + "Highlight differences" toggle + decisive-attribute verdict.
- **How It Works:**
  - Every PDP has an `Add to Compare` that accumulates to a persistent bottom bar (session + authenticated persistence). No typing.
  - `/compare` (Best Buy: `/site/compare?skus=...`) auto-populates from that bar. RTINGS extends this to a scored lab table (`/tv/tools/compare`) with 8–12 decisive rows (Picture Quality, Brightness, Viewing Angle, Energy) and a green-tinted winner row.
  - Checkbox `Highlight differences` suppresses identical rows, leaving only deltas (e.g., Compressor Warranty 60M vs 120M, Panel Warranty 48M, EER 3.15 vs 3.65).
  - Shareable URL (`?skus=6501301,6500517`) lets a family member open the same comparison.
- **Why It Works:** Converts recall task (remember model codes) into recognition; diff-highlight reduces 40-row scan to 6–8 decisive rows; total-cost pin (see Pattern 9) answers "which is actually cheaper to own?" Social proof (review count) is pinned above the fold. Verified live: Best Buy compare page shows 4-product columns with faceted spec sections + Reviews & Ratings row; RTINGS tool shows side-by-side scoring used by 10M+ buyers.
- **Potential Application (Transcom):** Direct fix for OPP-03 / C3 Smart Compare Workspace. Replace 3 search inputs with sticky bar fed by PDP `Compare` (already VERIFIED on every PDP at `page-analysis.md:129`). Add category-tuned decisive rows: AC → Tonnage / EER / Applicable sq ft / Refrigerant; Fridge → Litres + Door Type + Compressor Warranty; TV → Panel Type / Resolution / HDR / Panel Warranty. Add total-cost pin from OPP-09. Keep `Highlight differences` — already exists but empty.
- **Complexity:** Medium — compare store (session+auth), spec normalization per category, responsive table, permalink. Low if row data already structured.
- **Maturity:** **INDUSTRY STANDARD** for electronics (Best Buy, Currys, AO all offer). RTINGS verdict layer is **DIFFERENTIATOR**.

---

### Pattern 2 — Room-Size → Tonnage/BTU Calculator (AC Finder)

- **Company:** LG Electronics (global) — `lg.com/eg_en/products/air-conditioners/calculate`, LG Ductless Learning Center via ACDirect, LG Home Comfort (Canada)
- **Product Category:** Air Conditioner — residential split / inverter AC (directly maps to Transcom `air-conditioner/residential/inverter-ac`)
- **Customer Decision Problem:** Buyer knows room is "about 120 sq ft, top floor, west-facing" but not whether 1 Ton or 1.5 Ton is correct. Wrong choice = poor cooling or short-cycling + wasted energy. Transcom PDP shows `Applicable For 120 sq ft` only after opening Specification tab (`cross-review.md:296`), and SEO guide pushes grid below fold (IA-03). No interactive translation.
- **Pattern:** 3-field room input → tonnage/BTU verdict → filtered PLP.
- **How It Works:**
  - Inputs: Room Length × Width (or sq ft), ceiling height, exposure (top-floor, sun-facing, insulation), and adjustment factor (LG slider 0.70–1.50 for conditioned vs attic space).
  - Formula exposed: LG Home Comfort publishes `20 BTU per sq ft` baseline (Energy Star variant: 25 BTU/sq ft for humid climates), then adjustment. Example table: 100–150 sq ft → 5,000 BTU; 550–700 sq ft → 15,000 BTU; 1,000–1,300 → 22,000 BTU. LG INVERTER note explains oversizing tolerance due to variable capacity.
  - Output: "Your room needs ~12,000 BTU (1 Ton) — suitable for 100–150 sq ft with Econo mode" + CTA `See suitable Inverter ACs` that lands on filtered PLP (`/air-conditioner/residential/inverter-ac?tonnage=1Ton`).
  - Top-floor correction explicitly shown (×0.7 if room below conditioned space).
- **Why It Works:** Answers the single-question blocking AC purchase at entry, before spec hunting. Reduces wrong-size returns and post-purchase complaints. Calculator is content-only (no ML), validated against brand spec tables.
- **Potential Application (Transcom):** Anchor lens for OPP-04 / C4 Guided Selling Framework — AC Finder ships first (largest ticket, highest return risk). Inputs tuned to Bangladesh context: sq ft × height × top-floor flag × occupancy. Maps directly to existing tonnage variant chips (Daikin PDP `Choose Ton 1 / 1.5 Ton` at `product-page-variations.md:52` — only PDP with variant control). PDP verdict chip: "Right for your 120 sq ft room — 1 Ton" closes the loop.
- **Complexity:** Medium — rule table (sq ft→ton/BTU validated against Daikin/Haier specs) + PLP filter mapping + PDP verdict wiring. No backend.
- **Maturity:** **INDUSTRY STANDARD** for HVAC (LG, Daikin, Energy Star all publish tables). Interactive finder on retailer PLP is **EMERGING** (Currys/AO do it for washers/TVs; AC is less common).

---

### Pattern 3 — Fridge Capacity Translated to Family Size + Shopping Bags + Doorway Guard

- **Company:** AO.com (UK) + Currys (UK)
- **Product Category:** Refrigerator / Fridge Freezer — freestanding, integrated, American style (maps to Transcom `refrigerators/no-frost/side-by-side`, `multi-door`, 245L–600L range)
- **Customer Decision Problem:** "Is 415L enough for a family of 4? Will a 600L side-by-side fit through my doorway and kitchen gap?" Litres alone are meaningless; door swing, ventilation, and corridor clearance are discovered after delivery fails. Transcom PDP shows litres in title but no family mapping; installation line is NOT OBSERVED (`product-page-variations.md:60`).
- **Pattern:** Capacity ladder in human units + 7-step measurement guard.
- **How It Works (AO.com verified):**
  - Capacity ladder: "Total capacity 71L–655L — we’ve worked out how many shopping bags fit in each" (AO rule: `18 litres = 1 bag of shopping`; 150L = 8 bags, 350L = 19 bags). American models: 400–700L range labeled. Displayed on every product card and buying guide.
  - Family mapping: `Up to 150L → 1–2 persons / 250–350L → 3–4 persons / 400L+ → 5+ / American` (AO: "Up to 350L ideal for medium households").
  - Measurement guide (Currys `How to measure if a new fridge freezer will fit` — 7 steps): Height/Width/Depth of niche + repeat at different spots for uneven floors; measure doorways/hallways/corners; check 90° door opening + hinge scrape (leave 5cm on hinge side, 2cm behind/top for breathing/energy); confirm plumbing proximity for water dispenser (within 5m of source); confirm pull-out space for cleaning.
  - Split explainer (integrated): 50/50 vs 70/30 split must match housing unit (60W×60D standard; 177cm most common height).
  - PDP guard: Before Add To Cart, "Will it fit? Check your space" with dimension overlay + doorway warning for American models (doors removable — but not in rain).
- **Why It Works:** Litres → bags → family size is an instant mental model; 7-step guard prevents the most expensive failure (delivery rejected, door removed, floor scratched). Reduces customer service load.
- **Potential Application (Transcom):** Second lens for OPP-04 (Fridge Validator) + feeds OPP-12 Installation Checker. For Bangladesh: add `Litres → family size + Eid stock-up scenario` (Transcom SEO already uses family sizing), plus doorway/lift/stair guard for Dhaka apartments. Integrate with pincode delivery estimator (Pattern 6) so "fits your space + deliverable to your area" is one verdict.
- **Complexity:** Low-Med — content tables (litres→bags→family) + 7-step checklist CMS + PDP dimension overlay (requires W×H×D normalized per SKU). No logistics feed for guard phase.
- **Maturity:** **INDUSTRY STANDARD** in UK (Currys, AO identical). Shopping-bag conversion is **DIFFERENTIATOR** — materially reduces comprehension cost.

---

### Pattern 4 — TV Size–Distance–Resolution Advisor with Panel Explainer

- **Company:** Samsung DE TV Finder (`samsung.com/de/tvs/help-me-choose`), MediaMarkt TV-Kaufberater, RTINGS Size-to-Distance tool, Crutchfield (US)
- **Product Category:** Television — QLED / Smart TV / UHD (32"–100", maps to Transcom `tv-av/television/smart-tv`, `qled-tv`)
- **Customer Decision Problem:** Buyer knows viewing distance (e.g., 2.5m) but not whether 55", 65", or 75" is right, nor whether UHD vs QLED matters at that distance. Transcom filters offer Display Size buckets (`55"(10) 43"(7) 65"(7)` at `page-analysis.md:80`) but no distance guidance; PDP bullets mention HQLED/Dolby Vision without explainer.
- **Pattern:** Distance input → size recommendation → resolution/panel type explainer → filtered PLP.
- **How It Works:**
  - Inputs: Viewing distance + room brightness + primary use (movies/gaming/sport) + budget.
  - Samsung DE Finder: "Welche Fernsehergröße passt am besten zu deinem Raum?" → outputs 2–3 size options with visual room overlay.
  - RTINGS Size-to-Distance table: mathematically maps 32"→ 4 ft / 55"→ 7 ft / 65"→ 8 ft / 77"→ 9.5 ft + angle-of-view sweet spot (SMPTE 30° / THX 40°).
  - Panel explainer embedded: QLED vs OLED vs HQLED vs Dolby Vision in one tap-to-explain row (brightness, viewing angle, energy delta).
  - CTA: `See recommended Smart TVs` → PLP pre-filtered by recommended size ±1 step, with PDP verdict "Ideal for 2.5m — THX 40°".
- **Why It Works:** Size is the highest-regret TV decision; distance math is non-obvious but deterministic. Advisor short-circuits hours of research into 30 seconds. MediaMarkt reports this as top-converting finder.
- **Potential Application (Transcom):** Third lens for OPP-04. Leverages existing Display Size facet taxonomy (already category-specific at `product-discovery.md:79`) and brand breadth (Samsung/Haier/ROWA 32–100"). Also powers OPP-11 glossary: tap HQLED → "High Quantum LED — brighter than LED, 20% higher consumption than OLED at same size".
- **Complexity:** Medium — distance→size lookup table (SMPTE/THX) + room-brightness adjustment + PLP filter mapping. Content-only.
- **Maturity:** **EMERGING** — Samsung/LG brand sites have it; retailer PLP integration (AO/Currys) is still rolling out. Expected to become standard in 12–18 months.

---

### Pattern 5 — Installation & Recycling as Priced Basket Add-Ons with Pre-Condition Checklist (Before You Buy / Before We Deliver)

- **Company:** John Lewis & Partners (UK) + AO.com — `johnlewis.com/our-services/home-appliance-installation-and-disposal`, `ao.com/help-and-advice/delivery-and-services/installation`
- **Product Category:** All large appliances — washing machine, fridge/freezer, dishwasher, TV (maps to Transcom AC/Fridge/Washer/TV where PDP-03 install gap lives)
- **Customer Decision Problem:** Buyer reaches checkout and discovers installation is ambiguous ("Free Installation Selective Items" on homepage trust bar vs NOT OBSERVED on PDP at `ecommerce-capabilities.md:45`). Will fitter connect water/drain? Is haul-away included? Are prerequisites (shut-off valve within 4–6 ft, 3-pin socket within 1m, 1" ventilation gap) met? Transcom PDP shows only `Home Delivery Enable your Location` with no install truth.
- **Pattern:** Installation and haul-away are explicit SKUs added to basket alongside the product, with priced transparency and gate checklist.
- **How It Works (John Lewis verified live):**
  - Product page offers two checkboxes: `Add Installation` + `Add Recycling (haul away old appliance)` — added as line items.
  - Priced transparently: Washing machine installation £115 (freestanding) / £110 integrated dishwasher / £30 freestanding; Disposal £25; Fridge/freezer installation from £15 (AO freestanding) / £30 American. Delivery itself £19.95 standard / next-day where eligible.
  - **Before You Buy / Before We Deliver** gate: short video + checklist — e.g., for washer: transit straps removed, feet levelled, floor strength (suspended floor → blockboard), hot/cold valves corrosion-free with shut-off within 4 ft on same floor, 110V socket within reach, hoses not reused. For fridge: 3-pin socket within 1m, level space, 4-hour stand before switch-on, water valve within 6 ft for plumbed models, 1" gap on all sides. For dishwasher: water line with shut-off under sink, side brackets for solid surfaces.
  - Exception handling: Supplier-direct delivery = installation not bookable online (must phone 0345 604 8835). American fridge freezer recycling excluded for supplier-direct. Postcode exclusions table (remote/highland) shown before purchase.
  - AO adds: "We’ll unpack, level, connect water if needed, remove doors to fit American models, remove packaging — you must unplug old appliance and clear space before arrival."
- **Why It Works:** Converts vague "installation included?" into a purchasable line item with scope, price, and pass/fail checklist. Prevents failed installs (largest cost centre for large appliances) and builds trust by refusing to sell installation where prerequisites fail.
- **Potential Application (Transcom):** Core of OPP-12 / C12 Installation Checker → Slot Booking. Transcom trust bar `Free Installation Selective Items` becomes per-SKU truth: `Free install: Yes/No — Fee: Tk X — Prerequisites: outdoor wall + drain (AC), ventilation 1" gap (fridge), inlet/drain + floor (washer)` as Gate 1 (content). Gate 2 adds slot picker by district/zone after ops confirms feed (per `cross-review.md:175` gating). Cart line-item model mirrors John Lewis — prerequisite check propagates to checkout.
- **Complexity:** Med (checker — checklist CMS + per-SKU free/paid table) / High (booking — slot capacity + order↔service linkage + district exclusions).
- **Maturity:** **INDUSTRY STANDARD** in UK/EU (John Lewis, AO, Currys, MediaMarkt all sell installation as line item). Bangladesh execution is **DIFFERENTIATOR** vs Daraz/Pickaboo.

---

### Pattern 6 — Pincode/Area Delivery Estimator with Landed-Cost Truth (Serviceability + Fee + SLA + Store-Pickup Alt)

- **Company:** AO.com + Currys + Home Depot (US) — checkout pincode check / flexible delivery 7 days a week / store inventory feed
- **Product Category:** All large appliances (fridge 600L, AC outdoor unit, washer 8KG)
- **Customer Decision Problem:** "Can this 600L fridge be delivered to Rajshahi, what does it cost, and when?" Transcom gates this behind `Enable your Location` permission (`page-analysis.md:125` P1 PDP-02), then hides fee/SLA until checkout — the highest drop-off point for Tk 80k+ purchases (`opportunity-pool.md:OPP-01`).
- **Pattern:** Single pincode/area input on PDP that returns complete landed-cost truth without permission gate.
- **How It Works:**
  - Input: pincode / area / district text field (not geolocation permission) on PDP near price, with `Check` button. AO: "Add product to basket → enter postcode → see available dates" — 7-day delivery, installation priced separately.
  - Output block (all in one row): `✓ Deliverable to 1207 (Dhanmondi) — Delivery Tk 500 — Installation Free — SLA 2–3 days — Nearest store pickup: Elephanta 3.2km (in stock)` OR `✗ Not deliverable to this pincode — Nearest serviceable area: ... — Store pickup alt: ...`
  - Persists in session (`localStorage` pincode) and propagates to Cart Order Summary (delivery fee + install fee + total). Triggers pre-cart guard: `Add To Cart` disabled with inline reason if not serviceable.
  - Backend: pincode/area master × zone/SLA matrix × install fee table × store inventory by district.
- **Why It Works:** Answers delivery confidence at the exact moment of price exposure (Nielsen: visibility of system status). Pre-empts address-validation failure at checkout — the gap `cross-review.md:234` M-01 flags as missing from 38 proposals.
- **Potential Application (Transcom):** OPP-01 / C1 — highest-priority foundational capability per `opportunity-pool.md`. Replaces `Enable your Location` gate. Unblocks all high-ticket conversion and enables store-pickup upsell via Store Locator (`/store-locator` already VERIFIED with List/Map at `page-analysis.md:199-204`). Shares data model with Pattern 5 prerequisites.
- **Complexity:** High — pincode master + zone/SLA + install fee table + store inventory feed + cart wiring + session persistence. Phased: serviceability yes/no first, fee/SLA/pickup second.
- **Maturity:** **INDUSTRY STANDARD** globally (Amazon/Daraz already do pincode check; AO/Currys expose it on PDP). Absence in Bangladesh large-appliance is conversion gap, not innovation.

---

### Pattern 7 — Energy Label → Running-Cost Translator (Tap Any Spec Term for Tk/month)

- **Company:** Energy Saving Trust (UK) + Citizens Advice (UK) + Selectra/Ofgem + AO/Currys energy-label blocks (EU A–G label)
- **Product Category:** Fridge, washer, AC, TV — any EU A–G labelled appliance (maps to Transcom inverter AC EER, washer kWh/100 washes, TV kWh/1000h)
- **Customer Decision Problem:** PDP spec shows `EER 3.15` or `Energy consumption 250 kWh/year` but buyer cannot answer "what does that cost me per month?" Energy cost is hidden in Spec tab until clicked (`cross-review.md:296`). For Tk 50k–1.5L, 5-year energy dwarfs sticker delta but is invisible.
- **Pattern:** Inline glossary + label → Tk/month translator.
- **How It Works (verified sources):**
  - Energy Saving Trust: A–G label explainer (A most efficient) + QR to product fiche + capacity/noise/duration per class (fridge: chilled/frozen capacity + noise dB; washer: kWh/100 Eco 40-60 cycles + water L + spin; TV: SDR/HDR kWh/1000h + diagonal + pixels).
  - Citizens Advice formula: `Cost = annual kWh × unit rate` (UK example: 100 kWh × 24.67p = £24.67/yr; Selectra: 24.67p–26.11p/kWh cap; Purely Energy calculator: watts × hours /1000 = kWh).
  - Retail translation (AO): "Fridge-freezer 149 kWh/yr → £39/yr at 26.11p/kWh. Split AC 750W × 4h/day 7d → 1,092 kWh/yr → £285/yr." Interactive: tariff picker + running-hours slider + year-1/5-year projection.
  - Jargon decoder (Transcom-specific): Tap `EER 3.15` → tooltip "Energy Efficiency Ratio 3.15 = 1.1 kW draw at full load → ~Tk Y/month at 8 hrs/day @ Tk Z/kWh" — same for R32 (refrigerant class), Twin Inverter, HQLED.
- **Why It Works:** Converts abstract token (EER, A-G) into money — the only unit that drives trade-off between two models differing by Tk 5k upfront but Tk 8k/yr in energy. Trust via transparent formula, not claim.
- **Potential Application (Transcom):** OPP-11 / C11 Spec Jargon Decoder + feeds OPP-09 True Cost row. Content-only: glossary CMS of 25–40 terms (category-scoped: AC R32/EER, fridge Twin Inverter, TV HQLED/Dolby, washer Eco 40-60). Blocks all finders — finder output ("1 Ton is right") becomes explainable when EER→Tk/month is tapped.
- **Complexity:** Low — glossary CMS + running-cost formula + tariff table. No backend. Bangladesh tariff (per kWh) replaces UK 24.67p; formula identical.
- **Maturity:** **INDUSTRY STANDARD** for energy communication in EU/UK. Interactive translator is **EMERGING** (AO/Selectra have it; most PDPs still static).

---

### Pattern 8 — True Cost & EMI Planner in One Ownership Row (Price + Energy + Install + EMI/month)

- **Company:** Home Depot (US) Protection + EMI planner pattern + AO / John Lewis EMI context + Transcom EMI heritage (`EMI36`, `EMI From Tk/month`)
- **Product Category:** All high-ticket (AC 81k, fridge 1.38L, washer 57k, TV 79k — Transcom PDP pricing at `product-page-variations.md:54-56`)
- **Customer Decision Problem:** Sticker-price illusion: Transcom PDP shows `EMI From 2633 Tk/month — Avail Bank EMI` on AC but silence (no EMI line) on Haier 622IBG 600L fridge (`product-page-variations.md:55` PDP-06 P2). Buyer cannot validate "can I afford this monthly?" or "what is the total ownership cost vs cheaper model that costs more in energy?"
- **Pattern:** Single PDP row: `Upfront × + Install fee + Energy ~Tk/m (1yr/5yr) → EMI Tk/month × N months @ Bank`, with tenure/bank picker.
- **How It Works:**
  - Inputs: EMI bank/tenure master (e.g., City Bank 3/6/12/24/36 months), tariff × EER (from Pattern 7), install fee (from Pattern 5), running-hours slider.
  - Display: `Ownership: Tk 81,000 + Install Free + Energy ~Tk 850/m (1yr ~Tk 10k) → EMI from Tk 2,633/m for 36m @ City Bank` or explicit eligibility verdict `EMI not available for this SKU — see EMI Bank List`.
  - Interactive: Tenure dropdown (3→36m) re-calculates EMI; tariff selector (residential slab) updates energy; row propagates to Cart and Compare total-cost pin.
  - Home Depot reference: Protection plan priced by appliance price tier (3-yr/5-yr table) + 2-day service guarantee + No Lemon policy — shows how warranty upsell is merchandised alongside financing.
- **Why It Works:** Collapses three scattered truths (price, energy, financing) into one affordability verdict at the decision moment. Explicit "not available" verdict builds trust vs silence.
- **Potential Application (Transcom):** OPP-09 / C9. Feeds compare total-cost pin (Pattern 1). Directly fixes PDP-06 + PDP-03 + PDP-02 in one row. Phased: energy math + EMI eligibility first, full interactive planner after. Eligibility matrix shared with finance team.
- **Complexity:** Medium — EMI rule table × bank/tenure + tariff × EER + cart propagation. Cross-team: finance + catalog + PDP front-end.
- **Maturity:** **INDUSTRY STANDARD** expectation for EMI markets (India/Bangladesh BD EMI culture). Single-row ownership math is **DIFFERENTIATOR** — few Bangladeshi retailers combine energy + install + EMI.

---

### Pattern 9 — Spec Jargon Decoder as Cross-Category Glossary (Not Just AC/TV)

- **Company:** Currys interactive buying guides + AO capacity explainer + RTINGS glossary
- **Product Category:** Cross-category — AC (R32/EER/Applicable sq ft), fridge (Twin Inverter/DEO Fresh), TV (HQLED/Dolby Vision/Atmos), washer (Inverter Motor / 525mm Super Big Drum)
- **Customer Decision Problem:** Spec tab lists tokens (`Refrigerant R32`, `EER 3.15`, `Applicable For 120 sq ft`, `Twin inverter`, `HQLED`) with no explainer; warranty legend `Service-12M / Parts-12M / Special 60M` opaque (`issue-register.md:30` PDP-05). Buyer leaves PDP to Google and does not return. Transcom bullets are short but not decoded (`page-analysis.md:119` 4 bullets typical).
- **Pattern:** Tap-any-term → drawer/tooltip with plain-language definition + cost/behaviour translation + warranty legend.
- **How It Works:**
  - Trigger: Underlined spec terms in Specification tab + key-features bullets are tappable. E.g., tap `Twin inverter` → "Two compressors alternate load → 20% lower fluctuation vs single inverter → ~Tk Y/m saving at 8h/day". Tap `Special Component` warranty → "Special Component = Compressor (AC/Fridge) / Panel (TV) / Motor (Washer) per category — see table."
  - Currys pattern: Buying guides are not SEO walls; they are interactive layers with "How to measure" and "What capacity do you need?" per product line (oven, fridge, tumble dryer, coffee machine) linked from PLP.
  - Structure: 25–40 terms, category-scoped, authored once, rendered inline. Energy label visual + running-cost formula reused from Pattern 7.
- **Why It Works:** Literacy is prerequisite for finders/Cost calculator; reducing Q&A load and spec-hunting time directly lifts conversion for considered goods. Keeps buyer on PDP.
- **Potential Application (Transcom):** OPP-11 / C11 — content-only, immediate, unblocks all electronics decisions. Fixes PDP-04/pDP-05/pDP-03 burying. Shares glossary CMS with advisor outputs.
- **Complexity:** Low — glossary CMS + tooltip/drawer component + warranty mapping table. No backend.
- **Maturity:** **EMERGING** — few retailers do inline spec decode; most still externalise to blog. First-mover advantage in BD.

---

### Pattern 10 — Interactive Buying Guides as Layered PLP Entry (Not SEO Wall)

- **Company:** Currys (UK) — `currys.co.uk/buying-guides` (interactive built-in oven, washing machine, refrigeration, coffee machine guides)
- **Product Category:** Kitchen + refrigeration + laundry (maps to Transcom `home-kitchen/home-appliances`, `washing-machine`, `refrigerators` L1 where SEO guide buries grid at `issue-register.md:10` IA-03)
- **How It Works:**
  - Currys hub: Dedicated `/buying-guides/{category}` with interactive wizard (not long-form text above product grid). Each guide has its own URL, shareable, with steps: measure → capacity → split type → features → energy.
  - Trigger: PLP has subtle `Need help choosing? Take the 30-second guide` CTA that opens the wizard without pushing grid below fold. Wizard outputs a filtered PLP URL (e.g., AO/Currys append `?capacity=350-400L&split=70-30`).
  - Result: Product grid remains above the fold; SEO long-form moves below pagination or to `/buying-guides` — fixes IA-03 without losing SEO. Category-specific facets remain (Currys: Brand/Capacity/Split/Energy for fridge; Price/Brand/Display Size for TV — same taxonomy Transcom already has at `page-analysis.md:75-81`).
- **Why It Works:** Respects two intents: "I know what I want" (straight to filters/grid) vs "I need guidance" (wizard). Preserves SEO equity while removing scroll cost. Measurable: guide → filtered PLP has higher conversion than raw PLP.
- **Potential Application (Transcom):** Feeds OPP-04 / C4 as the wrapper for all finders. Unblocks IA-03 P1 (SEO wall). First move is architectural: move `refrigerators` L1 SEO block (1,500+ words verified at `site-inventory.md:70`) below grid and add `Not sure what size? Check fridge capacity guide` link → guided selling framework. Low-content, high-impact.
- **Complexity:** Low-Med — buying-guide CMS page per lens + CTA on PLP + filtered URL mapping. No new data model.
- **Maturity:** **INDUSTRY STANDARD** in UK/EU (Currys, AO, John Lewis all separate buying guides from PLP). Transcom currently conflates them — fixing IA alone is P1 hygiene.

---

### Pattern 11 — Complete-the-Setup Bundles & Consumable Cadence (FBT Done Right)

- **Company:** Home Depot (US) + AO.com + MediaMarkt/Saturn
- **Product Category:** AC, TV, fridge, washer, purifier (maps to Transcom AC→ stabilizer/wall bracket/copper wire, TV→ soundbar/wall mount/HDMI, fridge→ stabilizer, washer→ stand/detergent, purifier→ cartridge)
- **Customer Decision Problem:** PDP sells isolated unit; total cost of ownership discovered on second trip (buy TV, then hunt mount) or post-delivery (need stabilizer, wall bracket, extra copper). Consumable purifier cartridge cadence is invisible. Transcom PDP shows no bundle rail (`product-page-variations.md:66-67` FBT NOT OBSERVED; Related Products is single-card thin).
- **Pattern:** Complement rule engine rendered as toggleable bundle row on PDP + post-add Cart rail "Complete your setup".
- **How It Works:**
  - Rule engine: Family→attach mapping per appliance. Verified mandatory pattern at Home Depot: `New connection/hook-up parts are required for Depot Direct deliveries — Depot Direct will not use existing parts` (electric cords, gas flex lines, dryer duct, dishwasher connection kits, water lines). Must add waterline kit, supply hoses (4 ft), gas flex + dryer duct at point of sale.
  - AO/MediaMarkt: PDP bundle row shows `Add soundbar + wall mount → Save Tk X bundle price` with toggle before Add To Cart. Cart post-add rail shows grouped-line pricing ("Complete your setup — add washer stand + detergent").
  - Consumable cadence: Purifier PDP shows `Replacement cartridge every 6 months — Subscribe & save` (AO/Currys water dispenser proximity check).
  - Guard: Suppressed for low-ticket (trimmer/mixer at Tk 2k–5k) where attach is generic — matches `cross-review.md:168` scope-narrow guidance.
- **Why It Works:** One-trip total ownership reduces "need extra part" dissatisfaction and lifts AOV/attach rate. Mandatory hookup kit model prevents install failure (ties to Pattern 5).
- **Potential Application (Transcom):** OPP-05 / C5. Attach logic is merchandising-owned (not personalization). Phased: bundle row on PDP first, cart grouping + consumable cadence second. Aligns with PDP `Related Products` rail already VERIFIED — upgraded from single generic cross-sell to rule-driven complement.
- **Complexity:** Medium — complement affinity table per family + bundle CMS + cart grouped-line handling + suppressed low-ticket guard. Requires inventory feed for bundle SKUs.
- **Maturity:** **INDUSTRY STANDARD** for large appliances (Home Depot mandatory kit, AO bundle row). Consumable cadence is **EMERGING** (purifier/cartridge).

---

## Cross-Pattern Summary

| # | Pattern | Primary Transcom Gap | Opportunity Link | Maturity | Complexity |
|---|---------|----------------------|------------------|----------|------------|
| 1 | Persistent Compare with Diff Highlight | INTERACTION-01 P1 (compare needs typing) | OPP-03 / C3 | Industry Standard (+ Diff. verdict) | Medium |
| 2 | BTU/Tonnage Room Calculator | PDP-03 (room-fit buried) + IA-03 | OPP-04 AC lens / C4 | Industry Standard | Medium |
| 3 | Fridge Capacity → Bags/Family + Doorway Guard | PDP-03 + Install NOT OBSERVED | OPP-04 Fridge lens / C4 + C12 | Industry Standard (+ Diff. bag) | Low-Med |
| 4 | TV Distance→Size Advisor + Panel Explainer | PDP-03 + PDP-04 spec buried | OPP-04 TV lens / C4 | Emerging | Medium |
| 5 | Installation + Haul-Away as Priced Basket Line Items + Checklist | PDP-03 TRUST-01 (install vague) | OPP-12 / C12 | Industry Standard | Med → High |
| 6 | Pincode Delivery Estimator (fee/SLA/pickup) | PDP-02 P1 (location gate) | OPP-01 / C1 | Industry Standard | High |
| 7 | Energy Label → Tk/month Translator | PDP-03 + glossary gap | OPP-11 / C11 | Industry Standard (+ Emerging interactive) | Low |
| 8 | True Cost & EMI Planner Ownership Row | PDP-06 (EMI inconsistency) | OPP-09 / C9 | Differentiator (BD) | Medium |
| 9 | Inline Spec Jargon Decoder (EER/R32/Twin) | PDP-05 warranty + spec literacy | OPP-11 / C11 | Emerging | Low |
| 10 | Layered Buying Guides (wizard off PLP) | IA-03 (SEO wall buries grid) | OPP-04 wrapper / C4 | Industry Standard | Low-Med |
| 11 | Complete-the-Setup Bundles + Consumable | FBT NOT OBSERVED + Related thin | OPP-05 / C5 | Industry Standard (+ Emerging cadence) | Medium |

---

## Sequencing Recommendation (for Transcom)

1. **Immediate P0 (unblocks conversion):** Pattern 6 (Pincode Estimator) + Pattern 10 (move SEO wall below grid + add guide CTA) + Pattern 7 (energy translator) — fixes hygiene that every other pattern depends on.
2. **Next P1 (decision support):** Pattern 2 (AC Finder) + Pattern 3 (Fridge validator) + Pattern 1 (Compare workspace) + Pattern 8 (True Cost row) — the considered-purchase core for Tk 80k–1.5L.
3. **Differentiator (after core):** Pattern 4 (TV advisor), Pattern 5 (Checker), Pattern 11 (Bundles), Pattern 9 (glossary scale-up). Pattern 5 Gate 2 (bookable slot) gated behind ops slot-capacity feed per `cross-review.md:175`.
4. **Do not build:** Seasonal generic broadcast, low-ticket bundle creep, homepage affinity reorder before P0 hygiene — per `cross-review.md:234-243` M-01–M-08 gaps need remediation before personalization.

---

## Evidence Index (Traceability to Transcom State)

| Claim | Transcom Source:Line | External Verification |
|-------|----------------------|----------------------|
| `/compare` 3 search inputs, Highlight differences empty | `page-analysis.md:173-178`, `ecommerce-capabilities.md:23-25` | Best Buy `/site/compare`, RTINGS `/tv/tools/compare` (websearch 2026-09-03) |
| `Choose Ton 1/1.5` only on AC PDP | `product-page-variations.md:52` | LG AC calculate + Home Comfort BTU chart + ACDirect sizing calculator (websearch) |
| Litres in title, no family/bag mapping, install NOT OBSERVED | `page-analysis.md:119-125`, `product-page-variations.md:60` | AO fridge freezer buying guide (71–655L, 18L=1 bag) + AO measurement guide 7 steps (websearch) |
| Display Size facets but no distance guidance | `page-analysis.md:80`, `product-discovery.md:79` | Samsung DE TV Finder + RTINGS Size-to-Distance (websearch) |
| `Free Installation Selective Items` vs PDP no install line | `page-analysis.md:34`, `ecommerce-capabilities.md:45` | John Lewis installation & disposal services + pricing (£15–£115) + Before You Buy/Before We Deliver checklist (websearch) |
| `Enable your Location` gate blocks delivery truth | `page-analysis.md:125`, `issue-register.md:27` PDP-02 P1 | AO flexible delivery 7 days + Home Depot delivery checklist (websearch) |
| EER/R32/HQLED buried, warranty `Parts-0M/Motor-300M` | `issue-register.md:30-31` PDP-05/06, `cross-review.md:286-290` | Energy Saving Trust A–G label + Citizens Advice kWh×rate formula + Selectra running cost (websearch) |
| EMI present on AC/TV, absent on fridge without verdict | `product-page-variations.md:55` | Home Depot protection plan tiered pricing + EMI planner pattern (websearch) |
| SEO wall pushes grid below fold (1,500+ words) | `site-inventory.md:70`, `issue-register.md:10` IA-03 P1 | Currys buying-guides hub (interactive guides separated from PLP) |
| Related single card, FBT NOT OBSERVED | `product-discovery.md:106`, `ecommerce-capabilities.md:56` | Home Depot mandatory hookup kits + AO bundle row (websearch) |
| 167 URLs flat PDP namespace, `/undefined` broken | `sitemap-analysis.md:22-27,131`, `site-inventory.md:92` | — |
| 38→15 opportunity dedup, C1–C15 | `cross-review.md:32-73`, `opportunity-pool.md:C1–C15` | — |

---

*Output requested: `F:\My Code\Transcom\04-benchmark\agents\electronics-commerce.md`. Patterns are problem-solving, company-anchored, and verified where websearch allowed. No generic lists. All Potential Application rows map to a specific Transcom gap and opportunity ID.*
