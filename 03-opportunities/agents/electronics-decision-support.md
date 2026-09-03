# Electronics Decision Support Opportunities — Transcom Digital (Phase 3 — Agent C)

> Agent C — Electronics Commerce UX Specialist | Phase 3
> Source knowledge base: `00-input/sitemap-analysis.md`, `01-current-state/site-inventory.md`, `01-current-state/page-analysis.md`, `01-current-state/product-discovery.md`, `01-current-state/product-page-variations.md`, `01-current-state/user-journeys.md`, `01-current-state/ecommerce-capabilities.md`, `01-current-state/personalization-current-state.md`, `01-current-state/exploration-plan.md`, `02-ux-audit/issue-register.md`, `02-ux-audit/executive-summary.md`, `02-ux-audit/product-detail-experience.md`, `02-ux-audit/navigation-information-architecture.md`, `02-ux-audit/user-journey-friction.md`
> Date: 2026-09-03 | Verified via BrowserOS Neo 2026-09-03
> Mission: **High-consideration electronics/appliance decision support only** — buying guides, finders, spec explainers, calculators, compatibility, installation, ecosystem. Not generic e-commerce polish.
> PDP evidence anchors: Daikin FTKL12TV16WD 1 Ton (Warranty 12/12/60, EER 3.15 + Applicable For 120 sq ft — visible only after `Specification` tab click), Haier HRF-622IBG 600L side-by-side, Haier H55P7UX 55" 4K Google TV, Haier HW80-BP12929A 8kg front-load, Philips HL7757 750W mixer, Hitachi CV-SE230V 2300W vacuum, Philips BT1235 trimmer, Dell Inspiron 15 3501 (Currently Unavailable).

---

## 0. Method & Scope Guardrails

**What qualifies:** A decision-support capability that reduces *spec-literacy + fit + total-cost uncertainty* for a specific appliance family (AC, refrigerator, TV, washing machine, kitchen/small appliance, laptop/smartphone). It must be **requirement-led** (human inputs → product recommendation) or **spec-explanatory** (jargon → outcome), not a shell fix.

**What is deliberately excluded (Phase 2 fixes, not opportunities):**
- Repairing `See All → /undefined` (NAV-01 `issue-register.md:7`), adding active-filter chips (FILTER-01), enumerating `Select Sort Option` (SORT-01), adding toasts after Add to Cart (FEEDBACK-01), normalising warranty `Parts-0 M / Motor-300 M` strings (PDP-05 `issue-register.md:30`), fixing flat PDP URLs (IA-01) — all acknowledged as required remediation but **not recast** as decision support.
- Generic compare/persistence mechanics are owned by FEA-08 / PER-03; electronics-specific *decision lenses* inside comparison are in scope here (EDS-08).

**Verification rule:** Every EDS below was checked against `01-current-state/ecommerce-capabilities.md` (36 VERIFIED entries) — none duplicates an existing capability. `NOT OBSERVED` gaps plus tab-hidden evidence (`product-detail-experience.md:12-13`) are the opportunity space. **No AI is proposed** — all are rule-based, spec-driven, and content-governed. AI would only add opacity where deterministic tables (sq ft→tonnage, litres→family size, watts→use case) are authoritative and auditable.

**Decision difficulty scale used:** `Low` = preference/comfort, `Medium` = multi-attribute trade-off with moderate cost of error, `High` = wrong choice causes return, re-installation, or 5–10 year regret (tonnage, litres, panel, installation feasibility).

---

## 1. Baseline — Why Electronics Needs Its Own Decision Layer

Transcom's catalogue is structurally complete (39 category PLPs + 13 brand PLPs at `sitemap-analysis.md:22-27`, taxonomy-aware facets at `page-analysis.md:75-81`, warranty line adapted per appliance at `product-page-variations.md:61`) but **decision-thin**:

- **Buying guidance is SEO wall, not a finder:** L1/L2 category pages (`/air-conditioner`, `/refrigerators` at `page-analysis.md:90-91`, `issue-register.md: IA-03`) render 800–1,500 words of generic prose *above* the product grid that still cannot answer "is 1 Ton enough for my 130 sq ft west-facing room?"
- **Fit data is tab-hidden:** Daikin AC `Applicable For 120 Square Feet ; Height - 10 feet`, `EER 3.15`, `Refrigerant R32` only appear after clicking `Specification` (`product-detail-experience.md:12`). Journey C ("I need an AC for my room" at `user-journey-friction.md:53-73`) must hunt tabs to validate tonnage suitability.
- **No calculators, no requirement mapping:** Price slider + `Display Size 55"(10)`, `Color Green(1)`, `Power 1000W(1)` facets (`product-discovery.md:77-83`) expose *what* to filter, never *why* to choose. No room calculator, no capacity calculator, no energy explainer was `OBSERVED` in any PLP/PDP sample.
- **Installation/compatibility is a claim, not a plan:** Homepage trust bar `Free Installation Selective Items` (`page-analysis.md:34`) and footer `Installation` link exist, but PDP Options block shows only `Home Delivery Enable your Location / Store Pickup Enable your Location` with a permission gate (`product-page-variations.md:59-60`, `issue-register.md: PDP-02/03`).

For Tk 50k–1.45L purchases (AC 1–1.5 Ton, 600L fridge, 55–65" TV, 8kg washer at `product-page-variations.md:48-56`) this is a **high-cost-of-error** gap: undersized AC, too-small fridge, wrong-gamut TV, or non-installable appliance drives returns and service calls.

---

## 2. Opportunity Register — 9 Electronics Decision-Support Capabilities

> Each entry: Customer problem → Product category → Decision difficulty → Proposed capability → Example user scenario → User value → Business value → Complexity. Data + interaction + traceability included.

---

### EDS-01 — AC Room-Size & Thermal Load Finder (Tonnage Calculator)

- **Customer problem:** Buyer cannot translate room dimensions, floor, sun exposure, and room type into the correct tonnage (1 / 1.5 / 2 Ton) and inverter vs non-inverter choice. The only fit signal on the Daikin 1 Ton PDP — `Applicable For  120 sq ft ; Height - 10 ft` — is buried inside `Specification` after a tab click (`product-detail-experience.md:12`), and the `EER 3.15` energy rating has no plain-language meaning. Wrong tonnage = chronic under-cooling or energy waste for 10+ years. No interactive guide exists on `/air-conditioner` or `/air-conditioner/residential/inverter-ac` (`site-inventory.md:64-67`, `product-discovery.md:59`).
- **Product category:** Air Conditioners — Residential Split AC, Inverter & Non-Inverter (Daikin, Haier, Hitachi, Transtec families).
- **Decision difficulty:** **High** — sizing error is irreversible without replacement; inverter premium payback depends on usage hours.
- **Proposed capability:** **Room-Fit Finder: 3-step rule-based advisor + on-PDP fit verdict.** Inputs: room size (sq ft, with visual floor-plan selector), floor (ground/mid/top), sun exposure (shaded/sunny west), room type (bedroom/living). Output: (a) recommended tonnage with confidence band, (b) inverter vs non-inverter nudge based on daily hours, (c) EER/energy label explained as `Tk / year at 8h/day`, (d) direct action `See 1 Ton ACs (18) — [See 1.5 Ton if top-floor]` that auto-applies PLP filters (`Choose Ton` taxonomy already exists on AC PDP at `page-analysis.md:121`). From any AC PDP, compact verdict `✔ This 1 Ton fits 100–130 sq ft → Your room 140 sq ft ⚠ Consider 1.5 Ton` with link to sibling variant (ties to family navigator).
- **Example user scenario:** *Nadia, 28, Dhaka, renting 135 sq ft top-floor bedroom, west-facing, 10h/day usage.* She lands on `/air-conditioner` (currently SEO wall + grid at `page-analysis.md:48-54`), taps `Find the right AC for my room` above filters. Wizard returns: `For 135 sq ft top-floor sunny, 1.5 Ton Inverter recommended — EER 3.6 saves ~Tk 4,200/year vs 3.15 at your usage.` She lands on filtered `inverter-ac` PLP with 1.5 Ton pre-filtered. On Daikin 1 Ton PDP she sees the warning to step up, taps to Daikin 1.5 Ton sibling without returning to PLP.
- **User value:** One-tap translation of human context (room + heat load) → correct tonnage and energy tier; avoids undersizing regret and clarifies inverter payback in Tk terms, not jargon.
- **Business value:** Prevents most costly AC returns/complaints ("AC not cooling"); lifts conversion on correctly-sized (often higher-ticket) variants; generates structured demand signal (sq ft buckets) for merchandising and inventory; differentiates from price-only competitors.
- **Complexity:** **Medium** — Content: tonnage→sq ft rule table validated against Daikin/Haier/Hitachi spec sheets; Logic: rule engine (no ML) + PLP filter mapping (tonnage/inverter query params); UI: 3-step wizard + PDP verdict chip. No new fulfillment system.
- **Dependencies & traceability:** Spec extraction `Applicable For 120 sq ft` / `Height - 10 ft` / `EER 3.15` (`product-detail-experience.md:12`); variant buttons `Choose Ton 1 / 1.5` (`product-page-variations.md:52`); energy label source (BEE/brand). Evidence anchors `sitemap-analysis.md:22` AC hierarchy, `issue-register.md: PDP-03`.

---

### EDS-02 — Refrigerator Capacity & Kitchen Space Validator

- **Customer problem:** Capacity language is opaque: litres (245L vs 415L vs 600L side-by-side at `product-page-variations.md:48-56`) map poorly to family size and cooking habits. No PDP signals whether a 600L side-by-side will physically fit through a 30" apartment door or alcove, or whether frost/no-frost matters for this household. Category L1 `/refrigerators` SEO block mentions `Capacity… Space… Compressor` generically (`site-inventory.md:72`) but offers no personal mapping.
- **Product category:** Refrigerators — Frost / No-Frost, Top-Mount / Side-by-Side / Multi-Door (Haier 622IBG 600L, Samsung 415L/700L, Hitachi Made-in-Japan lines).
- **Decision difficulty:** **High** — 10-year appliance; wrong capacity or door type = daily friction; spatial misfit = failed delivery.
- **Proposed capability:** **Fridge Fit Validator: family→litres advisor + dimension guard.** Step 1: `Household size (2/4/6) + cooking frequency (daily/weekly bulk) + current fridge pain (space / freshness)` → recommended litres bucket (e.g., `320–420L for family of 4 with bulk cooking` vs `Up to 280L for 2-person`) + door-type rationale (`Side-by-side for wide-item storage vs Top-mount for compact kitchen`). Step 2: `Kitchen gap: Width × Depth × Height + Door width` → verdict `✔ Fits — needs 2" ventilation` or `⚠ Depth 28" exceeds your 26" alcove — consider slim model X`. Outputs a filtered PLP link by litres + door type (leveraging existing facets at `product-discovery.md:60`). On PDP, `Will this fit my family & space?` compact check pre-filled with SKU's litres + W×H×D from spec table.
- **Example user scenario:** *Rahman family of 4, bulk cooks twice weekly, kitchen alcove 36" wide × 28" deep, doorway 30".* They use the validator on `/refrigerators`. Result: `420–550L Side-by-side or Multi-door recommended — 600L Haier 622IBG fits your alcove (W 36" / D 27.5") but check doorway tilt delivery.` They filter to side-by-side PLP and on the 600L PDP see `✔ Capacity fit for 4 with bulk cooking — ⚠ Door swing needs 130° clearance — see diagram.` They avoid ordering a 245L that would soon overflow.
- **User value:** Turns litres into household reality; prevents spatial delivery failures before Add to Cart; validates door-type trade-off with plain language.
- **Business value:** Reduces "too small / won't fit" returns on highest-ticket, bulkiest SKUs; steers demand to correct capacity tier (often higher AOV); lowers failed-delivery rate (door/alcove guard); collects family-size intent for demand planning.
- **Complexity:** **Medium** — Litres→family rule table + dimension database (W×H×D per SKU from spec tables at `product-page-variations.md:61`); door-swing overlay diagram; PLP litres/door-type filter mapping. No logistics integration beyond dimension truth.
- **Traceability:** PDP samples `haier-no-frost-refrigerator-hrf-622ibg-600-liters` (`product-page-variations.md:6`), facets at `product-discovery.md:60`, issue `PDP-03`/`DISC-03`.

---

### EDS-03 — TV Size–Distance–Resolution Advisor + Panel Technology Explainer

- **Customer problem:** Screen size (32" / 43" / 55" / 65") and resolution (FHD / 4K / QLED / HQLED) choices are presented as filter values (`Display Size 55"(10) 43"(7) 65"(7)` at `product-discovery.md:79`) with no guidance on viewing distance (8 ft vs 12 ft), and panel jargon (`HQLED`, `QLED`, `Dolby Vision`, `Dolby Atmos` bullets on Haier H55P7UX at `product-page-variations.md:62`) is untranslated. Buyers oscillate between overbuying 65" for a small room or underbuying 43" they regret at 10 ft.
- **Product category:** Televisions — Smart TV / QLED / UHD + Soundbar adjacency (`tv-av/television/smart-tv` at `site-inventory.md:64`).
- **Decision difficulty:** **Medium–High** — size regret is common and visible daily; panel-tier premium is hard to justify without explainer.
- **Proposed capability:** **TV Decision Pair: (A) Distance→Size Calculator + (B) Panel Explainer.** (A) Slider `Viewing distance: 6–14 ft` + toggle `Wall mount vs Stand` + primary use (`Movies / Gaming / Mixed`) → `At 8 ft, 55" is sweet spot · 65" is immersive but needs 9 ft+` with live `visual angle` diagram and PLP pre-filter to `55" + 4K`. (B) On PDP, every spec bullet/acronym gets a tap-to-explain plain-language card: `HQLED = High-brightness QLED — punchier in bright rooms vs standard QLED` / `Dolby Vision = HDR format — brighter highlights in supported content` / `Panel-48 M` warranty explained as `Panel itself 48 months` (countering `issue-register.md: PDP-05` opacity). Video/gaming implications (120Hz, HDMI 2.1) flagged when present in spec table.
- **Example user scenario:** *Arif, viewing distance 7.5 ft in bedroom, wall-mounted, primary use Netflix + PS5.* He opens the advisor on `/tv-av/television/smart-tv` (currently 44+ products across 4 pages at `user-journeys.md:13`). Result: `55" 4K QLED is ideal at 7.5 ft; 65" will dominate the wall — [See 55" QLEDs (12)] [See 65" if you move sofa back]` + `For PS5, prefer 100/120Hz + HDMI 2.1 — filter now?` He lands on the Haier H55P7UX PDP and taps `HQLED` to read `Better bright-room performance; Dolby Vision films shine; panel warranty 48M covers display, not stand.` Confidence replaces spec anxiety.
- **User value:** Converts distance into size certainty with a visual proof; translates panel jargon into viewing outcome; validates constellation before purchase.
- **Business value:** Increases attach of correct size tier (55"→65" step-up when distance allows → AOV); reduces post-purchase size regret/return; positions Transcom as advisor, not spec list.
- **Complexity:** **Low–Medium** — Distance→size table (SMPTE/THX-derived, simplified) + jargon glossary CMS linked to spec bullets; PLP Display Size + resolution filter mapping. No new backend.
- **Traceability:** Facets `Display Size / Screen` at `product-discovery.md:79-80` (noting duplication `FILTER-04` at `issue-register.md:23`); TV PDP H55P7UX bullets + `Panel-48 M` warranty (`product-page-variations.md:55-61`).

---

### EDS-04 — Washing Machine Capacity & Household Load Advisor

- **Customer problem:** Kg capacity (6kg / 8kg / 9kg) and load type (front vs top load) are listed but not mapped to household reality: a family of 5 washing 4×/week needs a different drum than a couple washing 2×/week, and "8KG Front-Load HW80-BP12929A Super Big Drum 525mm" bullet at `product-page-variations.md:89` means nothing without context. `Motor-300 M` warranty (≈25 years at `product-page-variations.md:61`) adds confusion rather than confidence. No washer guide is observable beyond generic SEO.
- **Product category:** Washing Machines (incl. Dryers where cataloged) — Haier HW80-BP12929A 8KG verified sample; `washing-machine` L1 at `site-inventory.md:64`.
- **Decision difficulty:** **Medium** — capacity mismatch creates weekly pain; load-type error affects space/plumbing.
- **Proposed capability:** **Washer Load Advisor: Household → Kg + Load-type.** Inputs: household headcount + wash frequency (2× / 4× / daily) + space constraint (narrow balcony vs utility room) + water pressure note. Output: `For 4 members × 4 loads/week → 8kg front-load ideal; 6kg will need extra cycles; top-load needs top clearance 40" — [See 8kg front-loads (7)]`. Each recommendation card shows `Drum 525mm` translated as `Fits king-size bedsheet flat` and warranty card `Motor warranty 10 years (120M actual)` with humanised correction where `Motor-300 M` appears. Load-type explainer: `Front-load: better water efficiency, needs plumbing slope; Top-load: easier loading, smaller footprint.`
- **Example user scenario:** *Single mother of 3, washes 4×/week, balcony space 24" deep.* She uses the advisor on `/washing-machine`. Result: `8kg Front-load recommended; 6kg would cost you ~1 extra cycle/week; your 24" depth fits standard 8kg (D 23.6") — check door swing.` She filters to 8kg front-load, views HW80 PDP where `525mm Super Big Drum` now reads `Large drum — washes a king duvet in one cycle`.
- **User value:** Validates kg choice against actual laundry rhythm; prevents "too small drum" weekly friction; clarifies plumbing/space trade-offs before delivery.
- **Business value:** Steers buyers to correctly-capacity (often higher) washer; reduces capacity-related service complaints; humanises warranty (`Motor-300 M` → `10-year motor` with source) rebuilding trust.
- **Complexity:** **Low–Medium** — Kg→household rule table + drum-use translation + load-type explainer glossary + `Motor-300 M` normalisation; PLP `washing-machine` filter mapping. No new integration.
- **Traceability:** Washer PDP HW80 bullets + warranty `Motor-300 M` (`product-page-variations.md:61`/`89`); empty `Exchange` trade-in context at `site-inventory.md:58` informing upgrade nudge.

---

### EDS-05 — Spec Jargon Decoder & Energy Label Explainer (Cross-Category)

- **Customer problem:** The most decision-critical specs are also the most jargon-dense and behaviourally invisible: `EER 3.15` (Daikin AC), `Refrigerant R32`, `Inverter`, `Twin inverter` (Haier fridge at `product-page-variations.md:62`), `HQLED / QLED / Dolby Vision / Dolby Atmos` (TV), `525mm Super Big Drum / Inverter Motor` (washer), `2300W Cylinder-Cyclone / Nano Titanium Filter` (Hitachi vacuum at `product-page-variations.md:96-97`). Current PDP renders them as 4-bullet shorthand (`page-analysis.md:119`) and hides the explanatory spec table behind tabs (`product-detail-experience.md:12-13`). No legend explains `Service-12 M / Parts-12 M / Compressor-60 M` vs `Panel-48 M` vs `Special Component-60 M` (`product-page-variations.md:61`).
- **Product category:** **Cross-category** — AC, Refrigerator, TV, Washing Machine, Small/Home Appliances (vacuum, purifier, mixer with `HL7757 750W`).
- **Decision difficulty:** **Medium** — jargon opacity directly blocks energy/cost and quality judgement.
- **Proposed capability:** **In-context glossary + Energy outcome translator.** Every spec bullet, badge, and warranty token becomes a tap-to-explain: underline-dotted terms (`EER`, `Inverter`, `HQLED`, `Twin inverter`, `R32`) open a 2-line plain-language card with outcome, not definition: `EER 3.15 — Cooling per watt. Higher = lower electricity bill. At 8h/day, this AC costs ~Tk 2,100/month to run.` + `R32 — Modern refrigerant, more efficient, lower environmental impact vs R410A — doesn't affect cooling, affects footprint.` Energy label gets a `Running Cost` translation per SKU using `EER + wattage`. Warranty decoder normalises `Service / Parts / Compressor|Panel|Motor` with icons and humanised durations, fixing `Parts-0 M` / `Special 0M` opacity (`issue-register.md: PDP-05`).
- **Example user scenario:** *First-time AC buyer comparing two 1 Ton units: Daikin EER 3.15 vs Haier EER 3.6 (both listed in Specification tabs).* He taps `EER` on the Daikin PDP: card shows `EER 3.15 → ~Tk 1,950/month at 8h/day; Haier 3.6 → ~Tk 1,700/month — you save ~Tk 3,000/year with 3.6 — [Compare running costs]`. He taps `Twin inverter` on the fridge PDP: `Twin inverter = compressor + fan both variable — quieter, steadier temperature, lower bill vs single inverter.` He taps `Panel-48 M`: `Panel warranty 4 years — covers display, not remote/stand.` Jargon becomes budget.
- **User value:** Converts alphabet soup into money, comfort, and longevity outcomes — in situ, without leaving the PDP research flow.
- **Business value:** Increases preference for correctly-matched efficiency tiers (supports premium inverter/HQLED/QLED upsell on outcome, not badge); rebuilds trust in warranty `Motor-300 M`/`Special 0M` copy; reduces spec-mismatch complaints and support Q&A volume.
- **Complexity:** **Low** — Glossary CMS (25–40 terms) with category scoping + running-cost formula (EER×wattage×tariff×hours) + warranty legend component. Pure content + front-end, no AI.
- **Traceability:** Key bullets per PDP (`product-page-variations.md:48-56`); spec-tab hiding (`product-detail-experience.md:12-13`); warranty inconsistency matrix (`product-page-variations.md:61`; `page-analysis.md:123-124`).

---

### EDS-06 — True Cost & Energy Consumption Calculator

- **Customer problem:** Sticker price is not total cost. AC electricity (EER 3.15 vs 3.6), fridge 24/7 running (`Twin inverter` vs non-inverter), washer water/energy, purifier filter cartridge cadence, and EMI financing (`EMI From 2633 Tk/month` on AC but **absent on 1.38L Haier fridge** at `product-page-variations.md:55`, `issue-register.md: PDP-06`) create a *true-cost* gap users cannot compute. Current PDP shows `Save 7,000 -7.95%` but never `Own for 1 year costs X including electricity + filter`.
- **Product category:** **AC + Refrigerator + Washing Machine + Water Purifier (Pureit)** — plus EMI attach for any high-ticket PDP.
- **Decision difficulty:** **Medium–High** — energy and consumable cost compounds for 5–10 years; EMI eligibility confusion causes cart avoidance.
- **Proposed capability:** **Ownership Calculator: Sticker + Energy + Consumable + EMI.** On PDP (and cart-basket level): (a) **Energy row:** inputs `Hours/day (AC) or 24/7 (fridge) × Tariff` prefilled, showing `Estimated monthly running: Tk X · Year 1 total incl. purchase: Tk Y` with comparison toggle `Add second model to compare running cost`. (b) **Consumable row (purifier/washer):** `Filter replacement: every 6 months × Tk 1,500` or `Detergent/softener` nudged. (c) **Financing row:** `Or Tk X/month × 12 via EMI (bank list at `page-analysis.md:22-26` footer)` with eligibility verdict where EMI is currently silent (`EMI not offered for this SKU — why? [EMI Bank List]`). Result is shareable and persists to cart.
- **Example user scenario:** *Couple choosing between Haier 600L fridge (no EMI line, Twin inverter) and Samsung 415L (EMI eligible).* Calculator on each PDP shows `Haier 600L: ~Tk 850/month electricity (twin inverter) · Year 1 total Tk 1,48,800 · No EMI — Cash/Card only` vs `Samsung 415L: ~Tk 720/month · Year 1 total Tk 1,03,900 · EMI Tk 3,900/mo × 12`. They realise the 600L's 5-year energy saving (~Tk 7,800) doesn't offset the EMI gap for their budget and choose Samsung — confidently, without later financing surprise.
- **User value:** Replaces sticker-price illusion with 1-year and 5-year ownership math; resolves EMI silence into an explicit `not eligible` + reason before cart; enables rational inverter/premium choice on energy saving, not badge.
- **Business value:** Increases conversion among price-sensitive EMI intenders by removing PDP-06 ambiguity; justifies premium efficiency tiers via quantified saving; reduces checkout abandonment at payment step (financing surprise).
- **Complexity:** **Medium** — Energy formula per category + tariff table + consumable cadence DB + EMI eligibility matrix (price threshold × bank). Front-end calculator + PLP-aware comparison toggle. No payment gateway change.
- **Traceability:** EMI inconsistency documented (`product-detail-experience.md:25` PDP-06); energy EER evidence (`product-detail-experience.md:12`); purifier consumable context (`site-inventory.md:64` water-purifier hierarchy).

---

### EDS-07 — Installation & Site Compatibility Checker

- **Customer problem:** Users reach PDP price before knowing if the product can be installed in their space. AC needs outdoor-unit wall/bracket, drain point, 10A socket; washer needs water inlet/drain slope; TV 65" needs wall strength for mount; refrigerator side-by-side needs door-swing and floor level. Today PDP shows no install line (`product-page-variations.md:60` NOT OBSERVED), only `Home Delivery Enable your Location` gate (`issue-register.md: PDP-02`). Homepage `Free Installation Selective Items` trust bar (`page-analysis.md:34`) never maps to the SKU being viewed (`issue-register.md: TRUST-01`). Failed installs waste Tk 3–8k and a day.
- **Product category:** **Installation-sensitive:** AC (outdoor unit) · Refrigerator (ventilation/level) · Washing Machine (plumbing) · TV 55–65" (wall mount) · Water Purifier (wall/pressure).
- **Decision difficulty:** **High** for AC/Washer/Purifier (physical feasibility), **Medium** for TV/Fridge (space/ventilation).
- **Proposed capability:** **Site-Check: 4-question install feasibility + cost explainer.** Directly under PDP delivery/warranty block: `Check installation fit — 1 min` with appliance-specific questions:
  - *AC:* `Outdoor wall available? / Floor (high-rise bracket?) / Dedicated 10A socket? / Drain point?` → verdict `✔ Installable at your site — Free installation (bracket Tk 1,200 if needed)` vs `⚠ No drain point — hose routing adds Tk 800` + link `Prerequisites (Service Pre-Requisite at `page-analysis.md:23`)`.
  - *Washer:* `Water inlet within 1.5m? / Floor drain? / Level floor?` → verdict + `Stand/cover` suggestion.
  - *TV:* `Wall type (concrete/drywall) — Mount requires anchor type; Stand alternative fits?`
  - *Fridge:* `Ventilation gap 2" + floor level?` + door-swing arc diagram.
  Cost is SKU-bound (free vs paid per `Free Installation Selective Items` → now SKU-explicit), not generic.
- **Example user scenario:** *Family ordering Daikin 1 Ton for 5th-floor apartment with enclosed balcony.* Site-Check asks `Outdoor wall? — Enclosed balcony (needs stand, not bracket)` → verdict `✔ Installable — outdoor on balcony stand, drain to balcony, free install covers labour; stand Tk 1,500 extra.` They order with correct expectation and installer arrives with the right kit. Without this, installer reschedules and trust drops.
- **User value:** Pre-purchase certainty that the product is physically installable at their site, with an honest cost before payment — not a post-delivery surprise.
- **Business value:** Reduces failed-install visits and `Track Your Service` complaints (`ecommerce-capabilities.md:61`); converts SKU-bound trust claim into quantified promise; lifts confidence on high-ticket install-sensitive SKUs where competitors also stay vague.
- **Complexity:** **Medium** — Appliance-specific checklists (4–6 qs) + SKU install table (free/paid + fee) + verdict copy + diagram assets. Ties to FEA-01 delivery estimator for unified `Deliver + Install` card but shippable independently.
- **Traceability:** Install NOT OBSERVED on PDP (`product-page-variations.md:60`); trust bar isolation (`issue-register.md: TRUST-01`); footer `Installation / Service Pre-Requisite` (`page-analysis.md:22-26`).

---

### EDS-08 — Electronics Comparison with Decisive-Attribute Lens

- **Customer problem:** Current `/compare` (`page-analysis.md:173-178`) is a 3-empty-slot hand-type table (`Model name or part of product details` ×3) with `Highlight differences` — generic row parity. Electronics comparison is not about row parity; it's about *decisive attributes*: for TVs it's panel type / brightness / refresh; for AC it's tonnage + EER + refrigerant; for fridges it's litres + door type + inverter + compressor; for washers it's kg + load type + drum + motor warranty. Today PDP `Compare` exists on every PDP (`page-analysis.md:129`) but accumulation is unverified and diff logic is spec-table-generic (`user-journey-friction.md:75-96`, `issue-register.md: INTERACTION-01` P1).
- **Product category:** **TV · Refrigerator · AC · Washing Machine** comparison cohorts (brand-family and cross-brand within same size/capacity band).
- **Decision difficulty:** **High** — this is the purchase bottleneck for Journey D ("compare 3 Smart TVs 55–65"" at `user-journey-friction.md:75`).
- **Proposed capability:** **Decisive-Attribute Comparison: category-tuned lens + verdict row.** Same `/compare` shell but with:
  - (a) **Category lens tabs** atop diff view: `AC lens: Tonnage · EER · Refrigerant · Warranty (Compressor) · Running cost/mo` vs `TV lens: Size · Panel (HQLED/QLED) · HDR (Dolby Vision) · Refresh · Panel warranty · Mount/bundle` — lens reorders and tints decisive rows, greys accessory rows.
  - (b) **Total-cost pin row** (uses EDS-06 energy + FEA-05 EMI + EDS-07 install fee) so comparison is on `Price + Year-1 ownership`, not sticker.
  - (c) **Fit tags:** for AC `Fits 120 sq ft ✓`, for TV `Ideal at 8 ft ✓`, for fridge `Fits family of 4 ✓` drawn from EDS-01–04.
  - (d) **Verdict strip:** plain-language tie-breaker `Best efficiency → Model A (saves Tk 3k/yr) · Best bright-room → Model B (HQLED) · Best value → Model C` — no AI ranking, just decisive-attribute flags.
- **Example user scenario:** *Shopper shortlisted Haier H55P7UX 55" + ROWA 65" + Samsung 65" QN85C (the trailing-hyphen slug at `sitemap-analysis.md:131`).* Lens shows TV-decisive rows first: `Panel: HQLED vs QLED-Neo vs QLED` with decoder tooltip, `Refresh: 60 vs 120`, `Running: Tk 42/mo vs 48 vs 55`, `Install: Stand vs wall mount +Tk 2,000`. He sees at a glance that the 65" Neo QLED costs more yearly and needs a stronger wall, but wins bright-room — the tie-breaker is legible without parsing 40 spec rows.
- **User value:** Cuts comparison hunting cost by surfacing the 6–8 decisive rows per category first, with fit + true-cost context — a decision, not a table.
- **Business value:** Raises compare completion → purchase rate on high-ticket (Journey D is P1 precisely for this friction); reduces "bought on sticker, returned on total-cost" churn; drives step-up via justified premium (efficiency/panel) lens.
- **Complexity:** **Medium** — Spec normalization per category (canonical decisive rows) + lens tab UI + pin row integration (energy/EMI/install feeds); generic 3-slot storage remains (can reuse FEA-08/PER-03 persistence).
- **Traceability:** Empty compare empty-state + 3 search inputs (`page-analysis.md:173-178`), PDP Compare presence (`page-analysis.md:129`), category facets showing comparison axes (`product-discovery.md:79-83`), bullying spec-tab hide (`product-detail-experience.md:12`).

---

### EDS-09 — Kitchen & Water Purifier Requirement Finder (Wattage, Use-Case, Filter Logic)

- **Customer problem:** Kitchen and home-appliance choice is use-case-driven but presented as SKU-list: `Philips HL7757 750W 3-jar` (`product-page-variations.md:48-56`) with no guidance on watts needed for daily grinding vs occasional chutney; `Miyako Electric Kettle MJK-805 1.8L` vs larger; `Microwave Convection/Solo` (`sitemap-analysis.md:67`) with no use-case mapping; water purifiers (Pureit RO/UV/Mineral — 7 PDPs at `sitemap-analysis.md:44`) require RO vs RO+UV vs mineral vs storage (23L) logic that depends on source water and family consumption. Today selection is filter-only (`Brand: Ocean/Philips(2)` on dry-irons at `product-discovery.md:79`), not requirement-led.
- **Product category:** **Kitchen & Small/Home Appliances** — Mixer-Grinder / Blender-Juicer / Microwave Oven (Convection/Solo) / Electric Kettle / Vacuum (Hitachi 2300W Cylinder-Cyclone) / Water Purifier (Pureit Classic 23L etc.).
- **Decision difficulty:** **Medium** (mixer/microwave: task→capacity), **High** for purifier (health + consumable cost over years).
- **Proposed capability:** **Use-Case Finder per subfamily:**
  - *Mixer-Grinder:* `Tasks (daily flour / masala / juice) + Household size + Frequency` → `750W 3-jar recommended — 1000W only if daily hard grinding` + overload/jar explainer (existing `overload protector, jar lock guide` bullet at `product-page-variations.md:95` now decoded).
  - *Microwave:* `Cooking needs (reheat only vs grill/bake)` → `Solo if reheat; Convection if baking — size 20L for 2, 30L for 4`.
  - *Water Purifier:* `Source (city/well), TDS, Household size, Storage need` → `RO+UV+Mineral 23L if TDS >500 + family of 4; RO+MF if TDS <300` + `Cartridge: 6-month cycle × Tk X` running-cost disclosure (feeds EDS-06). Each finder outputs a filtered PLP link and a PDP `Fits your use-case ✓` verdict.
- **Example user scenario:** *Newly married couple, daily 2–3 masala grinds, small kitchen, budget-constrained.* Mixer finder returns `750W 3-jar HL7757 fits — 1000W saves little for your load; extra jar useful — [See 750W (4)]`. On the HL7757 PDP, `Warranty Special Component-60 M` is decoded as `Motor/jar coupler 5 years` and `Power 750W` reads `Handles daily hard spices; overload protection prevents burn-out — good for your frequency.` They avoid overpaying for 1000W and understand the warranty.
- **User value:** Maps daily kitchen tasks and water reality to the right wattage/capacity/filter — not to branded buzzwords — with consumable cost disclosed upfront (purifier).
- **Business value:** Reduces category returns/swap ("too weak for my grind" / "wrong purifier for my water"); increases correct-capacity upsell; for purifiers, transparency on cartridge cadence builds long-term consumable trust.
- **Complexity:** **Low–Medium** — Small rule tables per subfamily + wattage/use-case mapping + purifier TDS→filter decision tree + glossary cards. Pure front-end + content; no new inventory truth.
- **Traceability:** Kitchen PLP facets (`mixer-grinders`, `microwave-oven/convection/solo` at `sitemap-analysis.md:22-25`); mixer 68-image DOM + `Applicance` bullets (`product-page-variations.md:49-57`); vacuum `2300W` descriptor (`product-page-variations.md:6`); purifier brand count 7 at `sitemap-analysis.md:44` + trailing-hyphen slug hygiene at `sitemap-analysis.md:131`.

---

> **Notes on smartphones & laptops:** No smartphone PDP exists in the 101-product sitemap (`product-page-variations.md:8` — none observed) and only one laptop outlier (Dell Inspiron 15 3501, Currently Unavailable at `product-page-variations.md:6`) was sampled. For these, the decision layer is deferred to **finder templates** ready to activate: `Use-case → RAM/Storage/Processor` (laptop: gaming/battery vs business/portability; smartphone: camera/battery/gaming/budget) with battery/chipset explainers, without new PDP sampling. The nine EDS above cover the verified high-consideration core; smartphone/laptop will inherit EDS-05/08/06 (Jargon Decoder + Decisive Comparison + True Cost) when catalogue expands.

---

## 3. Cross-Opportunity Coverage

| Appliance family | Finders / Calculators | Explainers | Fit / Compatibility | Comparison & Cost |
|---|---|---|---|---|
| **Air Conditioner** | EDS-01 room→tonnage | EDS-05 EER/R32/Inverter | EDS-07 outdoor/drain/socket | EDS-06 energy + EDS-08 AC lens |
| **Refrigerator** | EDS-02 family→litres | EDS-05 Twin inverter / frost type | EDS-07 ventilation/door-swing + EDS-02 doorway guard | EDS-06 (24/7 fridge) + EDS-08 fridge lens |
| **Television** | EDS-03 distance→size | EDS-05 HQLED/QLED/Dolby | EDS-07 wall/stand | EDS-08 TV lens + EDS-06 |
| **Washing Machine** | EDS-04 household→kg | EDS-05 Inverter Motor / Drum size | EDS-07 plumbing/level/space | EDS-08 washer lens |
| **Kitchen / Small / Purifier** | EDS-09 use-case→wattage/litres/filter | EDS-05 wattage/overload/filter tech | EDS-07 purifier wall/pressure | EDS-06 consumable cost |
| **Generic electronics literacy** | — | **EDS-05** (shared glossary) + EDS-03/04 | — | **EDS-06** + **EDS-08** (shared) |

**Jobs-to-be-done addressed:** "Will this fit my home/family?" (EDS-01/02/03/04/07), "What does this spec actually do for me?" (EDS-05), "What will it really cost me to own?" (EDS-06), "Which of these shortlisted is decisive for my need?" (EDS-08), "What should I buy for my daily task/water?" (EDS-09).

---

## 4. What This Is Not — Explicit Non-Proposals

| Already-covered as Phase 2 fix (not proposed as EDS) | Why excluded | Where fix lives |
|---|---|---|
| PDP warranty `Parts-0 M` / `Motor-300 M` copy fix, inconsistent EMI badge silence, tab-set normalisation (`Product-Page-Variations.md:57/61`), `See All → /undefined` hydration (`site-inventory.md:92`) | Single-line markup/data correction, no new capability | `02-ux-audit/issue-register.md: PDP-04/05/06, NAV-01` |
| Active-filter chips, `Select Sort Option` enumeration, toasts, `Customer Review` bucket empty state | Feedback restoration of existing interaction | `issue-register.md: FILTER-01, SORT-01, FEEDBACK-01/02` |
| Persistent Wishlist/Compare storage, pincode delivery API as generic shell | Ownership is FEA-01/FEA-08 + PER-01/03; electronics-specific decisive lenses remain here (EDS-06/08) | `03-opportunities/agents/features.md`, `03-opportunities/agents/personalization.md` |

No opportunity above requires AI ranking, chat, or generative search. Each is a **deterministic, auditable table + glossary + calculator** with merchandising governance.

---

## 5. Suggested Sequencing (by conversion leverage, not effort order)

1. **EDS-01 (AC) + EDS-05 (Glossary/Energy)** — highest regret cost + most jargon; EDS-05 unblocks every other EDS's explainers. Ship together as "AC decision pack".
2. **EDS-03 (TV) + EDS-08 (Decisive Comparison)** — biggest shortlist bottleneck (Journey D P1) and most visual-category purchase.
3. **EDS-02 (Fridge) + EDS-07 (Site Check)** — bulky spatial + install failure directly causes failed deliveries.
4. **EDS-06 (True Cost)** — layers on energy data from EDS-01–05 to convert sticker comparisons to ownership math (especially where EMI silence at PDP-06).
5. **EDS-04 (Washer) + EDS-09 (Kitchen/Purifier)** — high-frequency weekly friction and consumable transparency as retention trust.

All EDS are A/B-testable on PDP and PLP entry points without re-platforming; each finder is URL-shareable for family decisioning (`?room=135&floor=top&tonnage=1.5` etc.).

---

## 6. Evidence Index

| EDS | Primary evidence (file:line / verified state) | Gap signal |
|---|---|---|
| EDS-01 | `product-detail-experience.md:12` AC Applicable For 120 sq ft + EER 3.15 tab-hidden; `product-page-variations.md:52` Choose Ton only on AC; `site-inventory.md:72` SEO wall not interactive; `user-journey-friction.md:53-73` Journey C | Fit data tab-hidden; no calculator `NOT OBSERVED` |
| EDS-02 | `product-page-variations.md:6` Haier 600L / Samsung 415L/700L litres; `product-discovery.md:60` fridge frost taxonomy; `page-analysis.md:34` trust bar vs PDP `issue-register.md: TRUST-01` | Litres≠family size mapping `NOT OBSERVED`; dimension guard `NOT OBSERVED` |
| EDS-03 | `product-discovery.md:79` Display Size buckets; `product-page-variations.md:62` HQLED/Dolby bullets; `product-page-variations.md:55-61` Panel warranty; `site-inventory.md:64` tv-av hierarchy | Distance→size `NOT OBSERVED`; panel jargon unexplained |
| EDS-04 | `product-page-variations.md:89` 525mm Super Big Drum / Inverter Motor; `product-page-variations.md:61` Motor-300 M warranty | Kg→household `NOT OBSERVED`; drum translated `NOT OBSERVED` |
| EDS-05 | `product-page-variations.md:62` Twin inverter etc.; `page-analysis.md:119` 4 bullets; `product-detail-experience.md:12-13` spec hidden; `issue-register.md: PDP-03/05` | Jargon decoder `NOT OBSERVED`; warranty legend `NOT OBSERVED` |
| EDS-06 | `product-page-variations.md:55` Haier fridge no EMI vs AC EMI; `product-detail-experience.md:25` PDP-06 EMI silence; `sitemap-analysis.md:44` Pureit 7 PDPs | Running cost + true cost `NOT OBSERVED`; EMI availability rule `NOT VERIFIED` |
| EDS-07 | `product-page-variations.md:60` install NOT OBSERVED; `page-analysis.md:34` trust bar selective; `page-analysis.md:22-26` Service Pre-Requisite | Install line `NOT OBSERVED`; site check `NOT OBSERVED` |
| EDS-08 | `page-analysis.md:173-178` /compare hand-type 3 slots; `page-analysis.md:129` PDP Compare; `user-journey-friction.md:75-96` Journey D | Decisive-attribute lens `NOT OBSERVED`; category lens `NOT OBSERVED` |
| EDS-09 | `product-page-variations.md:48-56` HL7757 750W / 68 images; `sitemap-analysis.md:22-25` kitchen/purifier hierarchy; `product-page-variations.md:96` Hitachi 2300W | Use-case→wattage/filter `NOT OBSERVED`; consumable cadence `NOT OBSERVED` |

---

*Author: Agent C — Electronics Commerce UX Specialist. Phase 3 output. 9 electronics decision-support opportunities (EDS-01–EDS-09), each with category-specific problem, decision difficulty, requirement-led capability, scenario, user + business value, and traceability. Complement to `03-opportunities/agents/features.md` (product features) and `03-opportunities/agents/personalization.md` (behavioral personalization); this doc owns **electronics fit, literacy, and true-cost decision support** with no AI, no generic polish recast.*
