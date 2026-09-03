# Opportunity Pool — Consolidated (Phase 3)

> 15 consolidated capabilities after deduplication of 38 raw proposals (9+9+9+11) + removal of 3 tails/fixes. Each opportunity is a single build unit; category lenses are phases, not separate opportunities. Confidence: evidence-backed per `cross-review.md`.

---

## OPP-01 — Delivery & Serviceability Estimator (Pincode-First Landed Cost)

- **Category:** FEATURE, ECOMMERCE STANDARD — **Source:** FEA-01 (+ PER-07 + ECS-05) — Cluster C1
- **User Problem:** PDP forces "Enable your Location" before revealing fee/SLA/timeline; users cannot answer "can this 600L fridge be delivered to my area, at what cost, with free install?" before price commitment.
- **Affected Journey:** Journeys B/C/E (all TV/AC/Fridge/Washer considered purchases); pre-cart placement on PDP → Cart summary propagation
- **Current State Ref:** `01-current-state/page-analysis.md:125` PDP Options gated; `01-current-state/ecommerce-capabilities.md:42-44` delivery preview gated; `01-current-state/personalization-current-state.md:7` PARTIALLY OBSERVED gate only
- **Related Phase 2 Issue:** PDP-02 P1 HIGH (delivery gating), CHECKOUT-02, PDP-03 install fee
- **Description:** Single pincode/area text input on PDP (no location permission gate) returning: serviceability yes/no, delivery SLA, delivery fee, free-install flag + fee if paid, nearest store-pickup alternative + distance. Result propagates to Cart Order Summary and persists across session (personalization layer: remember pincode). Pre-checks pincode before Add To Cart; prevents address-validation failure at checkout.
- **User Value:** Immediate delivery confidence at the exact moment of price exposure; fewer abandoned carts due to delivery uncertainty; informed store-pickup alternative.
- **Business Value:** Unblocks all high-ticket (Tk 50k–1.5L) conversion; reduces checkout pincode-mismatch drop-off; lifts delivered-order rate; enables store-pickup upsell.
- **Complexity:** High — pincode/area master + zone/SLA matrix + install fee table + store inventory feed + session persistence.
- **Dependencies:** Logistics zone/SLA feed, install fee per SKU table, store inventory/district mapping, Cart price-breakdown wiring.
- **Confidence:** HIGH — gate failure is HIGH-confidence P1; estimator pattern has precedent (Amazon/Daraz pincode check).

---

## OPP-02 — Browse Resumption: Recently Viewed & Continue Shopping

- **Category:** PERSONALIZATION, ECOMMERCE STANDARD — **Source:** PER-01 + PER-02 + ECS-09 — Cluster C2
- **User Problem:** No trail to resume interrupted research; returning or back-navigating users must rebuild hierarchy from root, re-find last filtered PLP/search.
- **Affected Journey:** Journey F (returning), Journeys B/C (multi-session research), empty-cart recovery
- **Current State Ref:** `01-current-state/personalization-current-state.md:9-10` Recently Viewed & Continue Shopping NOT OBSERVED; `01-current-state/page-analysis.md:159-164` empty cart/wishlist show no history; `01-current-state/ecommerce-capabilities.md:55` NOT OBSERVED
- **Related Phase 2 Issue:** DISC-02 P1 HIGH (Journey F unserved)
- **Description:** Anonymous → authenticated browse memory: item rail (last 8 viewed PDPs + price/stock badge) on homepage, PLP sidebar, and PDP; context deep-link "Continue where you left off — Smart TV: Samsung 55\"+, 1–2L" that reopens last filtered PLP/search with filters reapplied. Stored as `localStorage viewHistory + lastPlpUrl + compareQueue`, migrated to account on login. Shown on empty cart/wishlist as recovery path.
- **User Value:** Resume research in one tap; no re-navigation; sticks to user-chosen facet state.
- **Business Value:** Recaptures returning high-intent buyers; reduces browse-to-PDP search cost; lifts repeat-visit conversion and shortens time-to-shortlist.
- **Complexity:** Low-Med — localStorage schema + 2 small rails + deep-link builder; auth migration phase 2.
- **Dependencies:** Event instrumentation (PDP view, PLP filter apply), homepage/PLP/empty-cart UI rails, auth handoff.
- **Confidence:** HIGH — cheapest lift; pattern proven; zero existing conflict.

---

## OPP-03 — Smart Compare Workspace (Persistent, Auto-Populated, Decisive-Attribute & Total-Cost Aware)

- **Category:** FEATURE, DECISION SUPPORT — **Source:** FEA-08 (+ PER-03 + EDS-08) — Cluster C3
- **User Problem:** `/compare` requires 3 hand-typed "Model name or part of product details" searches; Journey D (compare 3 Smart TVs/Fridges) is high-friction recall task; no total-cost or decisive-attribute tinting.
- **Affected Journey:** Journey D (compare several), Journey B (shortlist 2–3)
- **Current State Ref:** `01-current-state/page-analysis.md:173-178` empty 3-slot with `Highlight differences` checkbox + 3 search inputs; `01-current-state/page-analysis.md:129` Compare entry on every PDP; `01-current-state/ecommerce-capabilities.md:23-25` Compare interface empty
- **Related Phase 2 Issue:** INTERACTION-01 P1 HIGH (Journey D), PDP-08 variant mismatch
- **Description:** Persistent compare system: sticky compare bar accumulates PDP `Compare` taps (session + auth persisted); `/compare` auto-populated, total-cost pin row (Price + 1yr Energy + Install + EMI/month from OPP-09), category-tuned decisive rows tinted + verdict strip ("Best value: …"), diff-highlight by checkbox, remove/share URL. No manual model typing needed; search remains as add-more only.
- **User Value:** Build shortlist without recall; see total cost + decisive attributes side-by-side; share/compare with family.
- **Business Value:** Fixes core high-consideration decision friction; lifts consideration-to-cart for big ticket; share URLs drive referral.
- **Complexity:** Medium — compare store (session+auth), spec normalization per category, delivery/EMI/energy feeds from OPP-01/09, permalink generation.
- **Dependencies:** Event `Compare add`, spec schema per category, OPP-01/09 data for total-cost row, responsive comparison table.
- **Confidence:** HIGH — Journey D P1 is sharpest high-ticket gap.

---

## OPP-04 — Guided Selling Framework (Requirement-Led Finders → Filtered PLP → PDP Verdict)

- **Category:** DECISION SUPPORT, FEATURE — **Source:** FEA-02 (+ EDS-01,02,03calc,04,09 + ECS-11) — Cluster C4
- **User Problem:** AC/Fridge/TV/Washer shoppers must translate life need (room size, family size, viewing distance, household load, water TDS) into specs (tonnage/EER, litres/door, size/resolution, kg, wattage/filter) themselves; SEO wall (`IA-03`) is generic text, not interactive helper.
- **Affected Journey:** Journeys B/C (primary), Journey A entry via finder
- **Current State Ref:** `01-current-state/page-analysis.md:90-91` SEO guides push grid below fold (IA-03); `01-current-state/product-discovery.md:74-83` frontspecific facets exist but no wizard maps need→filter; `01-current-state/product-page-variations.md:55-61` tone/size ambiguity
- **Related Phase 2 Issue:** IA-03 P1, PDP-03 P1 (room-fit buried), DISC-01 homepage overload
- **Description:** Single 3-step wizard framework `Need → Constraints → Budget/Preference` that outputs a filtered PLP + PDP verdict chip ("Right for your 120 sq ft room — 1.5 Ton"). Shippable category lenses: AC Finder (sq ft × height/top-floor/EER→ tonnage→ filtered inverter-ac), Fridge Validator (family size → litres + door + doorway guard), TV Advisor (distance → size → resolution/panel type), Washer Advisor (household size kg→ front/top), Kitchen/Purifier (cook family/wattage/jars, TDS→RO/UV). Lenses share wizard UI + PLP filter mapping.
- **User Value:** Answers "which spec is right for me?" before spec table hunting; filters are pre-applied to relevant results; PDP verdict confirms fit post-click.
- **Business Value:** Converts problem-aware traffic to filtered shortlist; reduces wrong-size returns; each lens is independently shippable (AC first = largest ticket).
- **Complexity:** Medium — rule tables per category validated against brand specs + PLP filter mapping + PDP verdict chip; no ML required.
- **Dependencies:** Rule table governance per category (sq ft→ton, litres→family etc.) validated by brand spec tables (`product-detail-experience.md:12`); PDP verdict wiring; CMS for wizard copy.
- **Confidence:** HIGH for AC/Fridge/TV/Washer lenses (abundant spec); MED for Kitchen/Purifier lens (thin evidence 7 PDPs).

---

## OPP-05 — Complete-the-Setup: FBT / Bundles & Consumable Attach

- **Category:** FEATURE, ECOMMERCE STANDARD — **Source:** FEA-09 (+ PER-08 + ECS-08) — Cluster C5
- **User Problem:** PDP sells isolated unit (TV without mount, AC without stabilizer, washer without stand/detergent, purifier without cartridge); total cost of ownership invisible until separate trip; existing Related Products is thin single cross-sell (`product-page-variations.md:65-66` NOT OBSERVED FBT).
- **Affected Journey:** Journey E cart-attach moment; post-add confidence (Journey B)
- **Current State Ref:** `01-current-state/ecommerce-capabilities.md:56` FBT/Bundles NOT OBSERVED; `01-current-state/product-page-variations.md:66-67` no accessories/bundles; `01-current-state/personalization-current-state.md:12` Cart-Based Recs NOT OBSERVED
- **Related Phase 2 Issue:** PDP-10 implied (total-cost) + TRUST pre-cart completeness
- **Description:** Complement rule engine per family (AC→ stabilizer/wall bracket/copper wire, TV→ soundbar/wall mount/HDMI, fridge→ stabilizer, washer→ stand/detergent, purifier→ replacement cartridge cadence). Two surfaces: PDP bundle row with toggleable bundle price before add, and Cart post-add rail "Complete your setup" with grouped-line pricing. Suppressed for low-ticket (trimmer/mixer) where attach is generic.
- **User Value:** See full ownership cost before commitment; one-trip purchase; consumable cadence reminder for purifiers.
- **Business Value:** Attach rate + AOV; reduces post-delivery "need extra part" dissatisfaction; re-engages consumables on interval.
- **Complexity:** Medium — complement affinity table per family + bundle CMS + cart grouped-line handling + suppressed low-ticket guard.
- **Dependencies:** Family→attach mapping, bundle price delta logic, inventory/availability per bundle SKU, cart grouping.
- **Confidence:** HIGH for AC/TV/Fridge/Washer/purifier attach; MED suppressed tail for low-ticket.

---

## OPP-06 — Price-Drop & Back-in-Stock Notifications with Timeline (Wishlist Intelligence)

- **Category:** FEATURE, PERSONALIZATION — **Source:** FEA-07 (+ PER-09 head + ECS-10) — Cluster C6
- **User Problem:** Wishlist is inert as guest (empty at `01-current-state/page-analysis.md:167-171` + `ecommerce-capabilities.md:38` AUTH required) and has no price-watch; out-of-stock PDP shows "Get Stock Alert" with no ETA (`issue-register.md:43` FEEDBACK-02), so users submit without expectation.
- **Affected Journey:** Wishlist journey (auth), Journey F resumption, out-of-stock research (Dell outlier)
- **Current State Ref:** `01-current-state/page-analysis.md:113` Get Stock Alert on Currently Unavailable; `01-current-state/ecommerce-capabilities.md:49,54` stock button VERIFIED but Price Alerts NOT OBSERVED; `01-current-state/personalization-current-state.md:13,9` persistence/auth lifecycle gaps
- **Related Phase 2 Issue:** FEEDBACK-02 P2, PDP-07 lifecycle, AUTH-02
- **Description:** Authenticated wishlist becomes monitored: price-drop (savedPrice vs current, %/Tk badge), back-in-stock with ETA/status ("Restocking in 2–3 weeks — notify at arrival or show similar in-stock alternatives"), and on-site banner + email/SMS per consent. Price history sparkline optional phase 2. Timeline promise is explicit; not perpetual waitlist.
- **User Value:** High-ticket consideration becomes watchable without daily checking; restock has finite expectation; alternatives avoid dead-end.
- **Business Value:** Captures high-intent demand that would otherwise go to competitor; reactivates dormant wishlist; measurable CTR to PDP.
- **Complexity:** Medium-High — authenticated wishlist + price history + stock ETA feed + consent + messaging templating.
- **Dependencies:** Wishlist persistence (auth), price history table, stock ETA feed per SKU, messaging consent/orchestration.
- **Confidence:** HIGH — explicit gap (no price watch, no ETA) validated as NOT OBSERVED.

---

## OPP-07 — Intelligent Search: Autocomplete, Recent Searches & Personalized Ranking (Staged)

- **Category:** ECOMMERCE STANDARD, PERSONALIZATION — **Source:** ECS-03 (+ PER-06) — Cluster C7
- **User Problem:** Header input VERIFIED but suggestions NOT FULLY VERIFIED; Journey A (know exactly: `FTKL12TV16WD`) has no fast-path; placeholder "Search Here" gives no scent; recent searches not recalled.
- **Affected Journey:** Journey A primary; Journey B/C entry
- **Current State Ref:** `01-current-state/ecommerce-capabilities.md:12-13` search input VERIFIED, suggestions NOT FULLY VERIFIED; `01-current-state/product-discovery.md:40-43` type attempted but dropdown not captured; `02-ux-audit/issue-register.md:17-19` SEARCH-01 P1 + SEARCH-03 P2
- **Related Phase 2 Issue:** SEARCH-01 P1 MEDIUM, SEARCH-02 P3, SEARCH-03 P2
- **Description:** Two-stage search. Stage 1 (foundational, P0): debounced autocomplete dropdown with product (title+price+stock badge), brand, category, SKU syntax detection for alphanumeric exact match, + Recent Searches chip row. Stage 2 (personalization, after OPP-02): affinity-biased ranking (viewer viewed Samsung 55" → Samsung suggestions ranked up). Zero-result recovery (OPP-08) is separate page, not part of dropdown.
- **User Value:** Type `ftkl` → see exact Daikin 1 Ton at top; recent typed terms one tap; no full-code memorization.
- **Business Value:** Shortest path for model-aware buyers (direct intent) → highest conversion intent; reduces zero-result volume.
- **Complexity:** Med Stage1 (index + debounced UI + recent store) / Med-High Stage2 (affinity scoring)
- **Dependencies:** Suggestion index (title/SKU/brand/category), search event stream, OPP-02 viewHistory for stage 2, mobile keyboard handling.
- **Confidence:** HIGH Stage1 (hygiene), MED Stage2 (requires affinity data volume).

---

## OPP-08 — Zero-Result Recovery & Typo Tolerance (Did-You-Mean + Facet Relaxation)

- **Category:** ECOMMERCE STANDARD — **Source:** ECS-04 alone
- **User Problem:** Typos for alphanumeric codes (`FTKL` vs `FTLK`) or Bangla-English mixed queries produce silent zero-result page; no handling observed in Phase 1 (no trigger test).
- **Affected Journey:** Journey A failure path; Journey B overly narrow filter combination
- **Current State Ref:** `01-current-state/ecommerce-capabilities.md:15` zero-result NOT TESTED; `01-current-state/product-discovery.md:40-43` brand-filtered search is only indexed pattern; `02-ux-audit/issue-register.md:19` SEARCH-03 P2 MED
- **Related Phase 2 Issue:** SEARCH-03 P2 (dead-end without recovery)
- **Description:** Fuzzy index (edit distance 1–2) + brand/category synonym table + Did-you-mean prompt + "No exact match but 18 close" fallback. On zero-result page: relaxed-facet suggestions ("Remove Brand filter → 12 results"), related searches, and advisor CTA ("Not sure? Try AC Finder").
- **User Value:** Typo does not equal dead-end; shortest recovery without re-typing from scratch.
- **Business Value:** Recaptures high-intent misspelled queries (alphanumeric codes are typo-prone); reduces bounced searches.
- **Complexity:** Medium — fuzzy index + zero-result template + facet-relax hints + analytics on zero-result queries.
- **Dependencies:** Search index with fuzzy, query log for top zero-result terms, advisor deep-links.
- **Confidence:** HIGH — classic hygiene gap; zero-result already flagged as not handled.

---

## OPP-09 — True Cost & EMI Planner (Ownership + Energy + Install + Financing in One Row)

- **Category:** DECISION SUPPORT, FEATURE — **Source:** FEA-05 + EDS-06 — Cluster C9
- **User Problem:** Sticker price illusion: EMI eligibility inconsistent (`product-page-variations.md:55` Haier fridge no EMI vs others); energy cost hidden in Spec tab (EER 3.15 → kWh/month); install fee gated until PDP-02; ownership sum unknown.
- **Affected Journey:** Journeys B/C/E at PDP decision + Cart total hesitation
- **Current State Ref:** `01-current-state/page-analysis.md:114-117` EMI badges/text present but inconsistent; `01-current-state/product-page-variations.md:55` EMI absence on fridge; `cross-review.md:138` cluster; `02-ux-audit/issue-register.md:31` PDP-06 P2
- **Related Phase 2 Issue:** PDP-06 P2 MED, PDP-03, PDP-02
- **Description:** PDP ownership row: `Upfront × + Install fee + Energy ~Tk/m (1yr/~5yr) → EMI from Tk/month for Y months @ Bank`. Interactive controls: tenure/bank picker + tariff selector + running-hours slider. Cart inherits row as price breakdown. Eligibility verdict where EMI unavailable ("EMI not available for this SKU → see EMI Bank List" rather than silence). Phaseable: energy math + EMI eligibility first, full planner interactive after.
- **User Value:** Compare appliances on total ownership, not sticker; validate if Tk 1.38L fridge is affordable monthly; hidden energy cost transparent.
- **Business Value:** De-risks high-ticket financing decision at the moment price is exposed; lifts apply for EMI clicks; trust via explicit "not available" verdict.
- **Complexity:** Medium — EMI rule table × bank/tenure + tariff × EER + consumable cadence + eligibility matrix.
- **Dependencies:** EMI bank/tenure master + tariff table + EER per SKU + install fee table (shares OPP-01), PLP/Cart price breakdown wiring.
- **Confidence:** HIGH — EMI inconsistency + energy tab-burial are both HIGH/med P1 gaps.

---

## OPP-10 — Rich Media Suite: Zoom, Pinch, Video & Dimension Overlay

- **Category:** FEATURE, DECISION SUPPORT — **Source:** FEA-03 + ECS-02 — Cluster C8
- **User Problem:** PDP gallery is generic placeholders (`01-current-state/page-analysis.md:134-135` 4+ generics, `01-current-state/product-page-variations.md:49-50` 68 DOM images but no player); TV bezel depth, fridge door swing, AC outdoor wall, washer drum inspection unsupported — high-consideration goods look like commodity listings.
- **Affected Journey:** PDP research (all AC/TV/Fridge/Washer)
- **Current State Ref:** `01-current-state/ecommerce-capabilities.md:30` Video NOT OBSERVED; `01-current-state/product-page-variations.md:49-51` NOT OBSERVED galleries; `01-current-state/ecommerce-capabilities.md:29` specs heading only
- **Related Phase 2 Issue:** PDP-01 P1 HIGH (video/zoom absent)
- **Description:** Gallery viewer upgraded: hover-zoom (desktop) / pinch-zoom (mobile) first, short feature video per category template second (AC install, TV panel demo, wash drum), 360° where asset exists, and dimension overlay on hero image (W×H×D + ventilation gap) drawn from structured spec. Phased: zoom → video → dimension.
- **User Value:** Inspect fit/finish/features without visiting store; validate wall/size/drum before ordering.
- **Business Value:** Reduces pre-purchase anxiety → reduces wrong-size returns/service burden; video lifts considered-PDP dwell.
- **Complexity:** Medium — viewer component + brand asset pipeline + spec dimension normalization; asset production scales by category.
- **Dependencies:** Brand image/video/360 assets, spec W×H×D normalized per SKU, gallery CMS.
- **Confidence:** HIGH — inspection gap is HIGH P1; zoom is low-risk first phase.

---

## OPP-11 — Spec Jargon Decoder & Energy Label Explainer

- **Category:** DECISION SUPPORT — **Source:** EDS-05 alone (+ EDS-03 glossary half) — keep distinct per cross-review
- **User Problem:** Spec tab reveals EER/R32/HQLED/Dolby Vision/Twin inverter/Coanda without explainer; warranty legend `Service-12M / Parts-12M / Special 60M` opaque (`issue-register.md:30` PDP-05).
- **Affected Journey:** All PDP research moments; unlocks OPP-04 finders by making finder outputs explainable
- **Current State Ref:** BrowserOS click on Daikin `Specification` revealed rows `Refrigerant R32 / EER 3.15 / Applicable For 120 sq ft` but no glossary; `01-current-state/product-page-variations.md:57-61` inconsistent tab headings + warranty keys
- **Related Phase 2 Issue:** PDP-04 P2 (hierarchy), PDP-05 P2 (warranty), EDS-05 literacy
- **Description:** Inline glossary: tap any spec term → drawer/ tooltip "EER 3.15 = ~1.1 kW draw at full load → ~Tk Y/month at 8 hrs/day" — same for R32 (refrigerant class), HQLED, Dolby, Twin inverter. Energy label visual + running-cost formula. Warranty legend row: "Special Component = Compressor/Panel/Motor per category". Content-only, no ML.
- **User Value:** Decode without leaving PDP; compare on meaning (energy Tk/month) not token (EER 3.15).
- **Business Value:** Literacy is prerequisite for finders/Cost calculator; reduces Q&A load; trust via transparent legend.
- **Complexity:** Low — glossary CMS (25–40 terms, category-scoped) + formula + legend copy; no backend.
- **Dependencies:** Term bank authoring, tariff input for cost formula, warranty mapping table.
- **Confidence:** HIGH — content-only, immediate, unblocks all electronics decisions.

---

## OPP-12 — Installation Feasibility & Slot Booking (Checker → Bookable Appointment)

- **Category:** FEATURE — **Source:** EDS-07 + FEA-06 — Cluster C9 (sequential layers)
- **User Problem:** No feasibility signal (outdoor wall/bracket, drain, socket, ventilation gap, floor strength) before ordering; no bookable install slot means scheduling is opaque post-purchase (`page-analysis.md:126-128` no install line; PDP-03).
- **Affected Journey:** AC/Fridge/Washer post-add pre-fulfilment (PDP → Cart → post-purchase)
- **Current State Ref:** `01-current-state/product-page-variations.md:60` install line NOT OBSERVED; `01-current-state/ecommerce-capabilities.md:45` install referenced only via footer/trust bar `Free Installation Selective Items`
- **Related Phase 2 Issue:** PDP-03 P1 (install absent), TRUST-01, M-03/M-06 flagged gaps
- **Description:** Two-gate install capability. Gate 1 Checker (content, ships first): per-SKU feasibility checklist (AC: outdoor wall + bracket + drain; Fridge: ventilation gap + floor + door swing; Washer: inlet/drain + floor) with pass/fail verdict before Add. Gate 2 Booking (ops, after confirmation): calendar slot picker by district/zone, prerequisites tick, fee if any, reschedule, order ↔ service-order linkage, push notification. Preresolution prevents booking on undeliverable sites.
- **User Value:** Avoid ordering AC that cannot be walled; know install prerequisites + fee + slot before commitment.
- **Business Value:** Eliminates failed-install waste; converts AC/Washer buyers who fear post-purchase surprise; differentiates vs Daraz/Pickaboo for large appliances.
- **Complexity:** Med (checker) / High (booking) — checklist CMS first, slot capacity + order↔service linkage after ops confirms feed.
- **Dependencies:** SKU install table (free/paid + fee) + checklist per appliance; slot inventory feed by district/installer team; order↔service linkage.
- **Confidence:** HIGH for checker (content), MED gating for booking (needs ops confirmation per `cross-review.md:175`).

---

## OPP-13 — Variant & Family Navigator (Sibling PDP Chips with Delta & Stock)

- **Category:** FEATURE, ECOMMERCE STANDARD — **Source:** FEA-04 alone — uniquely proposed
- **User Problem:** TVs filtered by Display Size on PLP but 55" PDP has no way to jump to 65" sibling; fridges/washers have no size/carbon switcher despite family existing; PLP discovery vs PDP navigation disconnected (`issue-register.md:33` PDP-08 P2).
- **Affected Journey:** PDP variant exploration (all families)
- **Current State Ref:** `01-current-state/product-page-variations.md:52` only AC shows `Choose Ton 1 / 1.5`; others show zero variants; `01-current-state/page-analysis.md:86` PLP display size facets hint family exists
- **Related Phase 2 Issue:** PDP-08 P2 (variant inconsistency)
- **Description:** Product family graph (model root → variants by tonnage/litres/display size/capacity) rendered as sibling chips on PDP with price delta + stock badge ("65\" + Tk 18k, In stock" vs "75\" Currently Unavailable"). Click navigates to sibling PDP; filters stay scoped. Not variant property inside PDP tab — navigable family.
- **User Value:** Explore sibling vault without returning to PLP; validate delta cost/availability instantly.
- **Business Value:** Capitalizes on existing SKU families without new SKUs; lifts sibling cross-sell; connects PLP taxonomy to PDP navigation.
- **Complexity:** Medium — family graph (model root → variants) + dimension mapping + price/availability feed; CMS wiring.
- **Dependencies:** Catalog family graph modeling; variant dimension table; price/stock feed.
- **Confidence:** HIGH — pattern verified by AC ton switcher + PLP size facets; only missing graph.

---

## OPP-14 — Social Proof: Ratings, Review Count & Return-to-Shelf Badges

- **Category:** ECOMMERCE STANDARD, DECISION SUPPORT — **Source:** ECS-01 alone — uniquely proposed
- **User Problem:** Review/Q&A tabs exist (`01-current-state/page-analysis.md:131-133`) but no aggregate stars, count, or sample review visible in reads; Customer Review facet is empty (`issue-register.md:21` FILTER-02 P2); PLP has no rating badge to bias shortlist — high-consideration research lacks social proof.
- **Affected Journey:** Journeys B/C shortlist (PLP), PDP confidence (PDP-07), repeat consideration
- **Current State Ref:** `01-current-state/ecommerce-capabilities.md:31-33` Reviews Ratings Q&A headings exist as tabs/buckets but Content NOT OBSERVED/NOT TESTED; `01-current-state/product-page-variations.md:62` Review tab present but no stars/count captured
- **Related Phase 2 Issue:** PDP-07 P1 HIGH (social proof absent), FILTER-02 P2
- **Description:** Foundational trust pipeline: review submission/moderation → aggregate rating + count badge above fold near price + on-card PLP badge (e.g., "4.6★ 212") → Customer Review facets populated → empty-state "Be first to review — Q&A prompt" + verified-purchase marker. Facet and PDP badge are suppressed until feed has data; no fake counts.
- **User Value:** Shortlist by peer validation, not price alone; see ownership-verified sentiment before committing Tk 80k+.
- **Business Value:** Proven conversion lift for electronics; populates Customer Review filter (currently empty) turning it into a real decision facet; seeds Q&A to reduce support load.
- **Complexity:** High — submission/moderation + aggregation + PLP badge wiring + facet feed; seeded empty-state governance.
- **Dependencies:** Review collection + moderation queue + aggregation service + PLP/PDP badge UI + facet indexing; verified-purchase check.
- **Confidence:** HIGH — explicitly NOT OBSERVED + P1 pain point + pattern is foundational baseline.

---

## OPP-15 — Category-Affinity Homepage & PLP Prioritization (Returner Reorder)

- **Category:** PERSONALIZATION — **Source:** PER-05 alone (with ECS-09 implicit)
- **User Problem:** Homepage serves identical 7+ mini-grids (Electric Kettles, Microwave, Washer, AC, TV …) to first-timer and to returner who spent 3 sessions viewing Samsung TVs and ACs; PLP order is identical regardless of affinity — no distinction between first-time orientation and returner deepening.
- **Affected Journey:** Journey F (returning) + Journey B PLP multi-visit; homepage as re-entry point
- **Current State Ref:** `01-current-state/page-analysis.md:48-54` 7+ serial grids (DISC-01 overload P1); `01-current-state/product-discovery.md:98-107` Latest/Best Deals are generic not affinity-scoped; `01-current-state/personalization-current-state.md:6` Personalized Homepage NOT OBSERVED
- **Related Phase 2 Issue:** DISC-01 P1 (heavy homepage), PERSONALIZATION gap, MOBILE-01 load concern
- **Description:** Returner-aware homepage/PLP module assignment: returning affinity (viewed Samsung TV + AC 1.5 Ton) surfaces "Picked up where you left off" rail + hero reweighted to affinity category; first-timer keeps orientation layout (Shop By Category + single curated hero). Governance: pins respect campaign merch slots; suppressed when affinity confidence low; PLP affinity chips (e.g., "Your size: 55\"+") rank within category. Implemented as modular CMS reorder + scorer, not hard-coded grid.
- **User Value:** Returner sees continuity without scanning generic grids; first-timer keeps uncluttered orientation.
- **Business Value:** Lifts returning-visitor conversion (highest intent) without harming first-time discovery; prepares for broader lifecycle personalization.
- **Complexity:** Medium-High — homepage CMS modularity + affinity scorer + A/B framework + governance vs campaign pins.
- **Dependencies:** CMS modularization audit, affinity scorer (viewHistory/category affinity), A/B infrastructure, governance rules.
- **Confidence:** MED — valid but weakest evidence + highest CMS dependency; keep as P2 experiment, require A/B proof per cross-review §6.

---

## Exclusions Explicitly Not in Pool

- **Remediation backlog (fixes, not opportunities):** ECS-07 Active Filter/Sort Feedback (FILTER-01/SORT-01 P1) and ECS-06 Populated Cart hygiene (CART-02) — moved to `02-ux-audit` follow-through per `cross-review.md:199-208`.
- **Generic seasonal broadcast tail of PER-09** — campaign segmentation, fails True Personalization test, removed.
- **Missing high-value gaps flagged for future triage (not opportunities in this pool):** M-01 checkout discoverability, M-02 IA flat-URL/SEO wall/undefined, M-03 trust propagation + warranty legend, M-04 mobile performance, M-05 auth OTP continuity, M-06 Track Order/Service post-purchase, M-07 brand vs search canonical, M-08 Exchange trade-in — noted in `cross-review.md:234-243`, not elaborated here to avoid re-proposing fixes as opportunities.

---
*Total consolidated: **15 opportunities**. Each is a single build unit; lenses/phases are implementation stages, not separate opportunities. All traceable to `03-opportunities/agents/*` IDs and `cross-review.md:32-73` Fate table + `cross-review.md:256-272` Consolidated Set C1–C15.*
