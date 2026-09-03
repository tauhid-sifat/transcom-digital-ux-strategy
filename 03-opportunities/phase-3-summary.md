# Phase 3 Summary — Opportunity Discovery & Consolidation

> Orchestrated multi-agent discovery (PER/FEA/EDS/ECS) → Cross-Review challenge → Deduplication → Consolidated pool. Do not prioritize yet — Phase 4 will RICE/road-map.

## 1. Total Raw Opportunities Discovered

| Agent | File | IDs | Count | Charter |
|---|---|---|---|---|
| **A Personalization** | `agents/personalization.md` | PER-01 – PER-09 | **9** | First-time vs returning, browsing/search, affinity, resumption, recommendations, lifecycle |
| **B Features** | `agents/features.md` | FEA-01 – FEA-09 | **9** | Net-new capabilities: discovery, research, confidence, delivery/install, financing, post-purchase |
| **C Electronics Decision Support** | `agents/electronics-decision-support.md` | EDS-01 – EDS-09 | **9** | Requirement-led finders, comparison, jargon/energy, compatibility, ecosystem |
| **D Ecom Standards** | `agents/ecommerce-standards.md` | ECS-01 – ECS-11 | **11** | Foundational vs enhancement vs differentiator |
| **Total raw** | — | — | **38** | — |

All 38 cleared verification against `01-current-state/ecommerce-capabilities.md` (none duplicates a VERIFIED complete row) and `01-current-state/personalization-current-state.md` (all 14 NOT OBSERVED except gate-only PARTIAL). Zero hallucinations of already-existing modules per `cross-review.md:182-193`.

---

## 2. Opportunities Removed as Duplicates (Pure Duplication)

| Cluster | Raw rows collapsed | Consolidated survivor |
|---|---|---|
| C1 Delivery Estimator | PER-07 + FEA-01 + ECS-05 (3) | OPP-01 (anchor FEA-01) |
| C2 Browse Resumption | PER-01 + PER-02 + ECS-09 (3) | OPP-02 |
| C3 Smart Compare (duplicate half) | 3 rows share comparison domain | part of OPP-03 (3 layers — counted with overlap) |
| C5 Attach/Bundles | PER-08 + FEA-09 + ECS-08 (3) | OPP-05 |
| C6 Price/Stock Notifications | PER-09 head + FEA-07 + ECS-10 (3) | OPP-06 |
| C8 Rich Media | FEA-03 + ECS-02 (2) | OPP-10 |
| **Total pure-duplicate rows** | **~18 rows** collapsing into **6 capabilities** |  |

Effectively 6 capabilities were triple-proposed under different vocabularies — ~47% of raw list is vocabulary duplication, not distinct invention.

---

## 3. Opportunities Removed Because They Already Exist

| Checked | Result | Note |
|---|---|---|
| Related/Latest/Best Deals generic rails | **0 removed** | All proposals correctly added behavioral/bundle/monetized signal, not re-proposed generic `01-current-state/product-discovery.md:98-107` rails |
| EMI badge Financing | **0 removed** | FEA-05/EDS-06 propose planner/calculator, not badge |
| Stock Alert button | **0 removed** | FEA-07/ECS-10 propose intelligence + price-drop + ETA, not single button |
| Wishlist/Compare empty pages | **0 removed** | PER-03/FEA-08 add persistence + workspace |
| Video/gallery | **0 removed** | FEA-03/ECS-02 propose viewer + dimension pipeline |

**0 of 38 was an already-exists violation** — agent verification discipline was strong (§4.3).

---

## 4. Opportunities Removed as Non-Opportunities (UX-Fix Misclassification)

| ID | Title | Reason | Correct home |
|---|---|---|---|
| **ECS-07** | Active Filter/Sort Feedback (chips, counts, enumerated sort) | Filter/sort shell VERIFIED (`ecommerce-capabilities.md:16-22`); gap is missing feedback, not capability. Maps to FILTER-01 P1/SORT-01 P1 in `02-ux-audit`. Restore expected control = fix. | Remediation backlog P1 |
| **ECS-06** | Populated Cart Completeness (qty/coupon/breakdown) | Empty shell VERIFIED; qty/coupon are baseline hygiene, not opportunity. Maps to CART-02 P2 `NOT TESTED populated`. | Split — hygiene fix + bundle is OPP-05 |
| **PER-09 tail** | Seasonal broadcast "Prepare for summer: Inverter ACs …" | Campaign segmentation with calendar + broad affinity, no behavioral trigger; fails True Personalization test `agents/personalization.md:30-33`; no new signal | Remove — campaign optimisation |
| **Total removed as fix/generic** | **3 rows/tail** | — | — |

Boundary rule applied per `features.md:9-30` — if shippable as string/ARIA/CSS restoration, it is a fix.

---

## 5. Opportunities Merged (Layers of One Capability)

| Merge | Raw members | Consolidated | Type |
|---|---|---|---|
| **C3 Smart Compare** | PER-03 + FEA-08 + EDS-08 (3 layers) | OPP-03 | Persistence + workspace + decisive lens are phases, not 3 builds |
| **C4 Guided Selling** | FEA-02 + EDS-01 + EDS-02 + EDS-03calc + EDS-04 + EDS-09 + ECS-11 (7) | OPP-04 | One wizard framework + 5 category lenses (AC/fridge/TV/washer/kitchen) |
| **C7 Search** | ECS-03 + PER-06 + (ECS-04 adjacent) | OPP-07 vs OPP-08 | Autocomplete Recent (foundational) + personalized ranking (stage 2) — staged, not merged; zero-result stays distinct |
| **C9 True Cost** | FEA-05 + EDS-06 (2) | OPP-09 | EMI planner + energy calculator = one ownership row |
| **C9b Installation** | EDS-07 + FEA-06 (2) | OPP-12 | Checker (content) → Booking (ops) — sequential layers |

**Total merged rows:** **~28 rows** collapsed into **8 consolidated capabilities** (plus 2 moved categories). The 38-item list is ~55% duplication by capability.

---

## 6. Final Consolidated Opportunity Count

| Metric | Count |
|---|---|
| Raw proposals | 38 |
| Pure duplicates collapsed | 18 rows → 6 |
| Layers merged | ~10 rows → 8 (incl. guided selling 7→1) |
| Removed as fix/generic | 3 |
| Distinct keepers proposed once | 7 |
| **Final consolidated opportunities** | **15** (OPP-01 – OPP-15) |
| Consolidation ratio | 38 → 15 = **60% reduction** |

*Counting note:* Final pool is `opportunity-pool.md` — 15 build units. Lenses/phases inside OPP-04 (5 lenses), OPP-07 (2 stages), OPP-12 (checker→booking) are implementation stages, not separate opportunities. Counting each lens as separate would re-inflate to 22+ and reintroduce the breadth overstatement cross-review corrected.

---

## 7. Opportunities by Category

| Category (non-exclusive) | Members | Count | Share |
|---|---|---|---|
| **PERSONALIZATION** | OPP-02, OPP-07 stage 2, OPP-15 (+ 02/03/06 personalization layers) | **3 primary** (+ 3 blended) | 20% primary; blended ~40% with Ecom Standard |
| **FEATURE** | OPP-01, OPP-03, OPP-04, OPP-05, OPP-06, OPP-07, OPP-08, OPP-10, OPP-12, OPP-13 | **10** | 67% — large-ticket commerce building |
| **DECISION SUPPORT** | OPP-04, OPP-09, OPP-11 core (+ OPP-03/10/12/13 decision facets) | **3 primary** (+ 4 blended) | 20% primary; blended ~47% |
| **ECOMMERCE STANDARD** | OPP-02, OPP-07, OPP-08, OPP-10, OPP-14 (+ foundational halves) | **5** | 33% — hygiene with outsized lift |

*If an opportunity belongs to multiple categories, not duplicated — multi-label in `opportunity-pool.md` (e.g., OPP-09 is DECISION SUPPORT + FEATURE, OPP-07 is ECOMMERCE STANDARD + PERSONALIZATION). Percentages not summing to 100 is intended.*

**By classification (within Standards lens):** FOUNDATIONAL 7 (OPP-01,02,03,07,08,10,14), ENHANCEMENT 5 (OPP-05,06,11,13 + 02 layer), DIFFERENTIATOR 3 (OPP-04 guided selling, OPP-12 booking, OPP-15 affinity reorder) — only 3 differentiators per brief ("Do NOT call everything a differentiator").

**By complexity (stage 1):** Low: OPP-11 jargon decoder. Low-Med: OPP-02 resumption. Med: OPP-04 (per lens), OPP-05, OPP-08, OPP-09, OPP-13. Med-High: OPP-03, OPP-06, OPP-15. High: OPP-01 delivery engine, OPP-12 booking, OPP-14 ratings pipeline.

---

## 8. Key Opportunity Themes

| Theme | Constituent opportunities | User job | Why bundled as a theme |
|---|---|---|---|
| **1. Fulfillment Confidence (Delivery + Install at Decision Moment)** | OPP-01 Estimator + OPP-12 Checker/Booking + OPP-09 True Cost ownership row | "Can it be delivered/installed to my place, when, at what total cost?" | AC/Fridge/Washer for Bangladesh scatter; location-gating (PDP-02) blocks price before delivery promise. Single theme spans PDP→Cart→post-purchase; delivers the strongest P1 conversion lift. |
| **2. Considered-Purchase Research (Guide, Explain, Verify)** | OPP-04 Guided Selling + OPP-11 Jargon Decoder + OPP-08 Zero-Result recovery | "Which spec is right for my room/family/distance?" | IA-03 SEO wall forces self-translation; Spec tab hides EER/panel data; typos for `FTKL…` codes dead-end. Together they turn taxonomy (`product-discovery.md:74-83`) into assisted shopping. |
| **3. Decision Memory & Resumption** | OPP-02 Recently Viewed/Continue Shopping + OPP-07 Search Recent/Autocomplete + OPP-03 Smart Compare persistence | "Resume where I left off; compare without re-typing" | DISC-02 Journey F unserved + SEARCH-01 Journey A no suggestions + INTERACTION-01 compare hand-type all attack the same memory gap across entry points. |
| **4. Confidence & Value Transparency** | OPP-09 True Cost/EMI planner + OPP-14 Ratings/Reviews + OPP-10 Rich Media (zoom/video/dimension) + OPP-13 Variant Navigator | "Is this good, does it fit, what will it cost to own?" | PDP is content-present but confidence-thin (PDP-01 zoom, PDP-07 no reviews, PDP-08 no sibling, PDP-06 EMI silence). One row (price→total cost) + media + proof + variant completeness. |
| **5. Attach & Lifecycle Monetization** | OPP-05 Complete-the-Setup + OPP-06 Price/Stock Wishlist Intelligence | "Get everything needed in one trip; watch price until I'm ready" | Existing Related is thin single cross-sell; wishlist is inert as guest; FBT/Bundles NOT OBSERVED. Connects cart attach to interval repurchase (purifier cartridge) and deferred purchase. |
| **6. Discoverability Hygiene (Foundational that unblocks everything)** | OPP-07 Stage1 autocomplete + OPP-08 zero-result are hygiene that lifts all themes | "Type a code and land; typo does not fail" | Stage1 is P0 even before personalization; without it Guided Selling must be built to compensate for broken search — hygiene first. |

*These 6 themes map to the 4 agent charters but are not 1:1 — cross-review deliberately broke charter silos.*

---

## 9. Areas Requiring Validation

| Area | What is unproven | Validation needed | Which opportunity gates on it |
|---|---|---|---|
| **Pincode/area master + zone/SLA matrix** | FEA-01 assumes zone→SLA mapping exists per district/store; no feed sampled (`ecommerce-capabilities.md:42` preview only gate) | Audit logistics zone table + install fee table + store inventory feed; confirm 167 URL districts map to deliverable zones | OPP-01 delivery estimator (unblocks all high-ticket) |
| **Catalog structured dimensions (W×H×D + ventilation gap per SKU)** | `ecommerce-capabilities.md:28` Spec Content NOT TESTED; only 8 PDPs sampled; `product-page-variations.md:49-50` 68 DOM images but no dimensions field validated | Sample 10 large-appliance PDPs for spec table dimension rows; assess normalisation cost | OPP-10 dimension overlay, OPP-12 checker, EDS-02 doorway guard (sub-lens of OPP-04) |
| **EMI bank × tenure × price-threshold matrix** | `product-page-variations.md:55` Haier fridge EMI absence unexplained; `cross-review.md:175` bank rule table effort unclear | Pull EMI eligibility rules per bank/tenure/price from finance team; verify per-SKU eligibility flag exists | OPP-09 True Cost & EMI eligibility row |
| **Review volume & moderation capacity** | `ecommerce-capabilities.md:31-33` Reviews facet NOT OBSERVED; no submission flow observed | Assess willingness to seed reviews (incentive, verified-purchase marker) + moderation ops + empty-state "Be first" governance | OPP-14 Social Proof (otherwise PLP badge empty, Customer Review facet stays dead) |
| **Homepage CMS modularity** | PER-05 assumes modular grid reorder is low-cost; `page-analysis.md:48-54` shows 7+ serial grids but no CMS proof | CMS audit: can homepage grids be hidden/reordered per persona without deploy? | OPP-15 affinity reorder (keep as P2 experiment, not P0) |
| **Search index freshness + volume** | ECS-03 assumes suggestion index on title/SKU/brand; no search volume sampled | Pull top-200 query log; measure zero-result rate for alphanumeric codes `FTKL…` + typo distance | OPP-07 Stage1, OPP-08 recovery |
| **Specification rule tables governance (sq ft→ton, litres→family etc.)** | EDS-01–04 finders assume governed tables validated per brand spec | Source rule tables from product/MKT, audit against spec tabs (`page-analysis.md:138` Related/Options vs spec), set owner & refresh cadence | OPP-04 guided selling lenses |
| **Guest→auth continuity event stream** | PER-01/02/06 assume viewHistory/compareQueue migration on login | Engineering spike: can `localStorage` → account memory migrate without duplicate write? Auth continuity design | OPP-02/03/06 lifecycle chain |
| **Slot capacity for install booking** | FEA-06 assumes slot inventory per district/installer; no ops link observed | Confirm ops capacity model + order↔service linkage exists; otherwise checker only | OPP-12 Booking phase |

---

## 10. Cross-Agent Disagreements & How They Were Resolved

| Disagreement | Agents involved | Positions | Cross-Review resolution | Rationale |
|---|---|---|---|---|
| **Filter/Sort chips — opportunity or fix?** | D (ECS-07) vs B/C framing | D proposes Active Feedback as opportunity; B/C silent (treat as fix) | **Fixed as fix** — filter/sort shells are VERIFIED (`ecommerce-capabilities.md:16-22`); chips are status restoration per FILTER-01 P1/SORT-01 P1, not new capability. Moved to remediation backlog. | Boundary rule `features.md:9-30` — string/ARIA fix ≠ opportunity. |
| **Populated cart qty/coupon — opportunity or hygiene?** | D (ECS-06) vs B implicit | D proposes Cart Commerce Completeness; B's FEA set omits cart | **Fixed as hygiene + bundle placement** — empty shell VERIFIED; qty/coupon are baseline. Cross-sell part → OPP-05. | Same boundary rule; CART-02 P2 is remediation. |
| **Search — one or two opportunities?** | A (PER-06 personalized) vs D (ECS-03 autocomplete) | D claims foundational autocomplete; A claims personalized ranking layer | **One capability, two stages** — OPP-07 Stage1 (autocomplete + recent) then Stage2 (affinity ranking). Not two counts. | Autocomplete without personalization still delivers Journey A value; personalization is phase 2. |
| **Guided selling — 6 vs 1** | B (FEA-02 umbrella) vs C (EDS-01–04/09 five lenses) vs D (ECS-11) | B/C/D overlap heavily; C treats each category as separate, B as one pattern | **One framework + phased lenses** — OPP-04. Counting each lens as equal inflates breadth 7×; counting only umbrella hides category specificity. | Matrix §2 overlap audit + C4 rationale. |
| **Pincode estimator ownership — personalization vs fulfillment** | A (PER-07 delivery) vs B (FEA-01) vs D (ECS-05) | A frames as "remember pincode" personalization; B/D as fulfillment engine | **Fulfillment feature** (A's persistence is 20% layer only). Decision rights sit with logistics, not affinity scoring. | §6 Category Moves. |
| **Attach/bundles — 3 surfaces, 1 rule engine or 3?** | A (PER-08 cart), B (FEA-09 bundles), D (ECS-08 FBT) | Three surfaces (PDP bundle row vs cart rail vs PLP checkbox) each claims distinct | **One rule engine** — OPP-05. | Placements ≠ capabilities; affinity table is single. |
| **Seasonal lifecycle nudge — personalization or generic?** | A (PER-09 seasonal AC tail) | A proposes "For you — Prepare for summer" as True Personalization | **Generic — removed.** Fails A's own test `personalization.md:30-33` (calendar + broad affinity = campaign segmentation). | Tail removed, head (wishlist price/stock) kept as OPP-06. |
| **Homepage affinity reorder — P1 or P2?** | A (PER-05) vs implied D/C scepticism | A proposes as personalization; no other agent duplicates strongly | **P2 experiment with A/B gate** — unproven lift vs P0 cost + CMS dependency. Keep but deprioritise. | §4.2 Unsupported + CMS audit gate. |
| **True Cost scope — EMI vs energy** | B (FEA-05 financing) vs C (EDS-06 energy/consumable) | Each builds half the ownership row | **One row** — OPP-09. | Each without the other leaves sticker illusion. |
| **Zero-result vs autocomplete — duplicate?** | Implicit: D proposes both 03 & 04 | Two adjacent search hygiene items | **Distinct — keep separate.** | Suggestions are at-type; recovery is post-submit. |

*No disagreement was dismissed as opinion — each resolved by whether control shell is VERIFIED vs NOT OBSERVED, and whether capability adds a net-new data model.*

---

## 11. Final Artefact Map

| File | Role | IDs covered |
|---|---|---|
| `agents/personalization.md` | 9 raw, signal-driven; 4 blended into pool | PER-01–09 |
| `agents/features.md` | 9 raw, net-new only; fix boundary stated upfront | FEA-01–09 |
| `agents/electronics-decision-support.md` | 9 raw, category-scoped rule tables, no AI | EDS-01–09 |
| `agents/ecommerce-standards.md` | 11 raw, classified Foundational/Enhancement/Differentiator | ECS-01–11 |
| `cross-review.md` | Challenge + duplicate/layer/overlap matrix | All 38, adjudicated |
| `duplicates-and-overlaps.md` | Merge/remove/move decisions with rationale | All 38 fates |
| `opportunity-pool.md` | 15 consolidated build units with full fields | OPP-01–OPP-15 |
| `phase-3-summary.md` | This file | Roll-up |

---

*Next: Phase 4 will assess effort, RICE, dependencies and sequence the 15 consolidated opportunities into a roadmap. No prioritisation or UI design is scored in Phase 3 per brief.*

---
*Evidence base: 03 agent outputs (38 IDs) → `cross-review.md` (38 adjudicated, 9 clusters, 8 missing gaps M-01–M-08) → `duplicates-and-overlaps.md` (28 merged, 3 removed, 4 moved, 7 distinct keepers) → `opportunity-pool.md` (15 build units). All counts traceable to file:line as above.*
