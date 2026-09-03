# Product Detail Experience — Audit

> Electronics & appliance purchase is high-consideration: technical specs, capacity, energy, installation, warranty, financing, and compatibility determine satisfaction. Audit lenses: information hierarchy, decision support, trust, consistency. No design specs — directional guidance only.

## Media & Inspection

### [PDP-01] Inspection unsupported — no video/zoom/360 verified (P1, HIGH) — Type G
**Location:** PDP gallery region above title (generic image containers `page-analysis.md:134-135`) — all 8 PDP samples. **Current:** Phase 1 found 4+ generic image containers and 68 DOM images on Mixer but no player/zoom verified; Phase 2 did not surface a video string in body reads. **Problem:** Users cannot inspect bezel, door swing, outdoor unit dimensions, drum — gaps most painful for TV/AC/Fridge. **Impact:** Purchase hesitation on high-ticket visual goods; returns risk. **Direction:** Introduce hover-zoom (desktop)/pinch (mobile) + short feature video per category template where assets exist; indicate gallery count.

## Information Hierarchy

### [PDP-03] Installation/energy/room-fit buried one click deep (P1, HIGH) — Type D
**Location:** PDP Options block vs hidden `Specification` tab table. **Current:** Phase 2 click on Daikin AC `Specification` tab revealed `Applicable For 120 Square Feet ; Height - 10 feet`, `EER 3.15`, `Refrigerant R32`, `Feature Energy Saving…` — all absent above the fold in pre-click body. No explicit installation fee/energy label inline. **Problem:** Journey C (“I need an AC for my room”) must click tabs to validate tonnage suitability; throw-away if user skips tabs. **Impact:** Wrong-size choice (1 vs 1.5 Ton) → dissatisfaction/service. **Direction:** Surface 3-point fit summary directly under title/price: “Fit for: … | Energy: … | Install: …” with tab as detail; keep spec table lazy-loaded.

### [PDP-04] Specification hierarchy inconsistent across categories (P2, HIGH) — Type C
**Location:** Daikin AC (tabs `Overview|Feature|Specification|Review|Product Policy`) vs Philips Mixer `HL7757` (tabs `Overview|Specification|Review|Product Policy` — `Feature` omitted) — `product-page-variations.md:57`. **Current:** Tab set shifts per category; content of spec table appears only after clicking tab (Phase 2 verification shows post-click body includes table rows `General Features | Refrigerant R32`). **Problem:** Learnability: users who learn spec is under `Specification` on AC find different set on Mixer. **Impact:** Spec hunting cost rises per category. **Direction:** Canonical 4-tab set with disabled-but-visible placeholder + consistent table order (General → Energy → Dimensions → Warranty → Feature).

### [PDP-09] Duplicate “Add To Cart” buttons without role distinction (P3, HIGH) — Type A
**Location:** All in-stock PDPs — one CTA near price and second below Options (`page-analysis.md:126-128`). **Current:** Two isomorphic ` Add To Cart` buttons. **Problem:** Duplication adds noise; users unsure which scroll anchor is primary; screen-reader announcement doubled. **Impact:** Minor visual clutter but scales across PDPs. **Direction:** Keep single sticky CTA bar on scroll; second button becomes anchor or removed.

---

## Price, Financing, Warranty

### [PDP-06] EMI/financing availability inconsistent and unexplained (P2, MEDIUM) — Type C
**Location:** Daikin AC `EMI From 2633` + `Avail Bank EMI` present; Haier 622IBG Fridge **no EMI line** (`product-page-variations.md:55`); Trimmer no EMI. **Current:** Fridge (1.38L) — arguably highest EMI need — shows savings % but no EMI; no “not eligible” message. **Problem:** Eligibility appears arbitrary; price-sensitive users uncertain if high-ticket can be financed. **Impact:** Cart avoidance for fridge segment. **Direction:** Where EMI unavailable show “Pay in EMI not available for this product — see EMI Bank List” with link, else consistent `EMI From…`.

### [PDP-05] Warranty nomenclature inconsistent and values implausible (P2, HIGH) — Type C
**Location:** PDP Options Warranty line — `product-page-variations.md:61` + `page-analysis.md:123-124`. **Current:** `Parts-0 M` (Mixer), `Special 0M` (Trimmer), `Motor-300 M` (Wash ≈25 years). No legend for `Special Component`. **Problem:** 0 months reads as no warranty; 300 months reads as typo — trust eroded. **Impact:** Warranty is post-purchase confidence driver for BD electronics; inconsistency downgrades trust. **Direction:** Normalise keys (`Service | Parts | Compressor/Panel/Motor`) with legend + humanised durations (“5 years”).

### [PDP-05b — sub-case] “Parts-0 M” likely means not applicable but shown as numeric — information design failure
Included under PDP-05 root cause for deduplication.

## Delivery & Trust

### [PDP-02] Delivery confidence gated behind “Enable your Location” (P1, HIGH) — Type E
Detailed in `usability-issues.md`. **Location:** PDP Options `Home Delivery Enable your Location` / `Store Pickup Enable your Location` (`product-page-variations.md:59-60`). **Current:** No pincode/area pre-check field; location permission gate blocks cost/timeline. **Problem:** Delays delivery confirmation to after price exposure; error-prevention for pincode mismatches not handled before cart. **Impact:** High abandonment at PDP; store-pickup benefit hidden. **Direction:** Lightweight pincode/area text input inline with immediate delivery/ install fee result; keep permission as enhancement.

### [TRUST-01] Trust bar isolated to homepage — absent where decision happens (P2, HIGH) — Type C
**Location:** Homepage trust bar `Free Installation Selective Items / Original Product Guaranteed / Exchange Program / Secure Payment` vs PDP/Cart where absent (`page-analysis.md:33-34`). **Current:** No trust reinforcement near price/CTA. **Problem:** Confidence built at browse entry dissipates at consideration/checkout moment — violates consistency. **Impact:** PDP/Cart trust premium untapped, especially where installation after-sales anxiety high. **Direction:** Echo 2–3 most relevant badges inline near CTA (Original + Installation + Secure Payment) with links.

### [PDP-02b] Installation fee not surfaced on PDP (P1, HIGH)
Duplicate partial of PDP-02/03 — consolidated here. **Location:** AC/Fridge/Washer PDPs. **Current:** No explicit “Free/paid installation” line on PDP Options beyond Home Delivery framing; footer `Installation` link exists but decoupled. **Problem:** AC install can cost ~Tk 3–8k; unanticipated cost at checkout heightens abandonment. **Direction:** Surface install fee (if free, say “Free Installation”; if paid, estimate) alongside delivery line.

## Reviews & Social Proof

### [PDP-07] Review/Q&A tabs present but no aggregate rating or sample review visible (P1, HIGH) — Type D
**Location:** All PDP tab strips `Review` (`product-page-variations.md:62`, `page-analysis.md:131-133`). **Current:** No star aggregate near title/price; reads contain no star glyphs. **Problem:** Electronics rely on peer validation; empty tab looks like missing content rather than zero-reviews. **Impact:** Research users lack social proof nudge. **Direction:** Surface aggregate + count above fold; lazy-load samples inside tab; add “Be first to review” + Q&A prompt when empty; expose Customer Review as real filter only when reviews exist (ties to FILTER-02).

## Comparison & Variants

### [PDP-08] Only AC exposes in-PDP variant control; TVs/Wash/Fridge have no variant selector despite filter taxonomy (P2, HIGH) — Type G/C
**Location:** Daikin AC `Choose Ton 1 Ton / 1.5 Ton` vs TV/Wash no variant (`product-page-variations.md:52`). **Current:** TVs filtered by `Display Size` on PLP but PDP for 55" TV shows no size switcher. **Problem:** Users who want 55"→65" adjustment must return to PLP; PLP taxonomy vs PDP controls disconnected. **Impact:** Variant exploration requires back-navigation → funnel breaks. **Direction:** Where product family has size/capacity siblings, show PDP variant chips linking siblings.

### [PDP-10] No accessories/bundles/FBT to contextualise total cost (P2, MEDIUM) — Type G
**Location:** PDP footer beyond Related Products — `product-page-variations.md:66-67` “None observed” across all categories. **Current:** No stabilizer for TVs, stand for AC, detergent for wash — PDP sells isolated unit. **Problem:** Total cost of ownership invisible; cross-sell revenue missed. **Impact:** Users buy TV then discover stabilizer need late → separate purchase friction. **Direction:** Introduce “Frequently bought with” accessory rail per appliance type.

---
*Evidence: `page-analysis.md:107-154`, `product-page-variations.md:23-137`, BrowserOS spec-click verification (`Daikin AC Specification` table rows).*
