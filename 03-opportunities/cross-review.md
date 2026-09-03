# Cross-Review — Phase 3 Opportunities Audit

> **Agent:** Cross-Review (Phase 3) | **Date:** 2026-09-03
> **Inputs audited:** `03-opportunities/agents/personalization.md` (PER-01–09), `features.md` (FEA-01–09), `electronics-decision-support.md` (EDS-01–09), `ecommerce-standards.md` (ECS-01–11) — **38 raw opportunities**
> **Evidence base:** `01-current-state/ecommerce-capabilities.md`, `01-current-state/personalization-current-state.md`, `02-ux-audit/issue-register.md` (32 issues), `02-ux-audit/executive-summary.md`
> **Role:** Challenge weak recommendations. Do not combine lists blindly. Determine duplicates vs distinct layers vs category misplacements. Flag generic / unsupported / already-exists / UX-fix misclassifications. Surface missing high-value gaps none covered.
> **Constraint:** No new opportunities created beyond critique; gaps are flagged only.

---

## 0. Executive Verdict

| Metric | Count |
|---|---|
| Raw opportunities audited | **38** (9 + 9 + 9 + 11) |
| Deduplicated capabilities after merge | **15** |
| Pure duplicates (identical capability, different label) | **~18** rows collapse into 6 clusters |
| Overlapping concepts that are **layers of one capability**, not duplicates | **3 clusters** (Compare, Guided Selling, Installation) |
| UX fixes misclassified as opportunities | **2** (ECS-07, ECS-06) + 1 partial (ECS-03 boundary) |
| Category misplacements (right idea, wrong owner) | **4** |
| Generic / unsupported / already-exists | **3** flagged |
| Missing high-value gaps none of 4 agents covered | **8** |

**Headline:** Agents were individually rigorous — each correctly checked `ecommerce-capabilities.md` VERIFIED vs NOT OBSERVED and avoided re-proposing static generic shelves. **Collectively they triple-proposed the same 6 capabilities** under different vocabularies. The 38-item list is ~55% duplication by capability. The strongest distinct contributions are: **Ratings/Social Proof (ECS-01 alone), Variant Navigator (FEA-04 alone), Spec Jargon Decoder (EDS-05 alone), Zero-Result Recovery (ECS-04 alone)** — each proposed once and never duplicated. The weakest proposals cluster around **seasonal lifecycle broadcast (PER-09 tail), homepage affinity reorder (PER-05), and kit/bundle without catalog proof (FEA-09/ECS-08 for low-ticket skews)**.

---

## 1. Fate of Every Raw Opportunity

> **Fate definitions:** `KEEP` = distinct, net-new, correctly categorised. `MERGE` = duplicate or layer of a larger capability — consolidate. `REMOVE` = generic / unsupported / already-exists / pure UX fix — drop from opportunity register (move to remediation or discard). `MOVE` = valid idea but belongs to another domain — reassign owner.

| ID | Title (short) | Fate | Disposition / Rationale | Consolidated Owner |
|---|---|---|---|---|
| **PER-01** | Recently Viewed Trail | **MERGE** | Identical to ECS-09 half. Layer A (item-level history) of **Browse Resumption** capability. Not distinct from ECS-09. | **Browse Resumption** (Personalization) — merge PER-01 + PER-02 + ECS-09 |
| **PER-02** | Continue Shopping / Resume Journey | **MERGE** | Identical to ECS-09 half. Layer B (last filtered PLP/search context) of same Browse Resumption. PER correctly splits A vs B; ECS bundles them. Merge. | Same as above |
| **PER-03** | Resume Comparison (Persistent Compare) | **MERGE** | Layer 1 (persistence/memory) of **Smart Compare** triad. Overlaps FEA-08 (workspace) + EDS-08 (decisive lens). Not standalone. | **Smart Compare** (Features + Decision Support) — merge PER-03 + FEA-08 + EDS-08 |
| **PER-04** | Behavior-Aware Recommendations | **KEEP** | Distinct behavioral shelf ("Because you viewed / Inspired"). No duplicate — FEA/EDS/ECS do not propose browsing-aware ranking. Survives generic-vs-true test (`personalization.md:27-33`). Keep. | Personalization — Recommendations |
| **PER-05** | Category-Affinity Homepage & PLP Prioritization | **KEEP*** | Distinct but **weakest personalization** — requires CMS modular reorder (`personalization.md:214` Medium-High) for unproven lift vs P0 cost. Keep with caveat: downgrade to P2 experiment, require A/B proof. Valid but low evidence. | Personalization — Homepage |
| **PER-06** | Personalized Search (History-Aware Suggestions) | **MERGE** | Personalization layer atop **Search Autocomplete** foundation (ECS-03). PER-06 adds affinity-biased ranking; ECS-03 is non-personalized base. Merge as two maturity stages. | **Search** — merge PER-06 + ECS-03 (+ ECS-04 related) |
| **PER-07** | Location-Aware Delivery Confidence (Invert Gate) | **MERGE** + **MOVE** | Core is **Delivery Serviceability Estimator** — FEA-01/ECS-05 duplicate. PER framing ("remember pincode") is persistence layer only. Valid but mis-categorised as pure personalization; 80% is fulfillment. | **Delivery Estimator** (Features/Delivery) — merge PER-07 + FEA-01 + ECS-05 |
| **PER-08** | Cart-Based Complementary Suggestions | **MERGE** + **MOVE** | Core is **Attach/Bundles** — FEA-09/ECS-08 duplicate. PER adds cart-contingent trigger. Mis-categorised; merchandising owns accessory affinity, personalization owns cart-state trigger. Merge. | **Complete-the-Setup** (Features/Merch) — merge PER-08 + FEA-09 + ECS-08 |
| **PER-09** | Lifecycle & Post-Purchase (Wishlist Nudges, Seasonal) | **MERGE** (partial) / **REMOVE** (tail) | Head (price-drop / back-in-stock wishlist nudges) = duplicate of FEA-07/ECS-10 — merge. Tail (seasonal AC-summer / fridge-Eid broadcast segmented by affinity) is **generic campaign segmentation** with no price/stock signal; unsupported without CRM/consent feed (`personalization.md:347-348` High complexity). Split: keep wishlist-price/stock as merged, **remove seasonal broadcast** as generic recommendation requiring no new capability. | Head → **Price/Stock Notifications**; Tail → REMOVE (generic) |
| **FEA-01** | Pincode-First Delivery, Installation & Serviceability Estimator | **MERGE** | **Anchor** for Delivery Estimator cluster. Most complete spec (serviceability engine, SLA, install fee, store pickup, session propagation). Merge. | **Delivery Estimator** — anchor (see above) |
| **FEA-02** | Room & Capacity Fit Advisor (Interactive Buying Guide) | **MERGE** | **Umbrella** for Guided Selling parent. Generic wizard pattern; EDS-01–04/09 are category instantiations. ECS-11 is verbatim duplicate at standards framing. Merge. | **Guided Selling** — umbrella (see EDS cluster) |
| **FEA-03** | Rich Media Inspection Suite (Video+Zoom+360+Dimension Overlay) | **MERGE** | Identical to ECS-02. FEA adds dimension-overlay; ECS covers gallery depth/video/zoom. Same media pipeline. Merge. | **Rich Media** — merge FEA-03 + ECS-02 |
| **FEA-04** | Product Family & Variant Navigator | **KEEP** | **Unique.** Only proposal for SKU family graph / sibling PDP chips. PDP-08 (`issue-register.md:33` P2) is the fix symptom; family graph is net-new. No duplicate across 38. Keep. | Features — Catalog |
| **FEA-05** | Interactive EMI & Affordability Planner | **MERGE** | Financing half of **True Cost** cluster. EDS-06 adds energy/consumable + EMI eligibility row. Overlap >60%. Merge. | **True Cost & EMI** — merge FEA-05 + EDS-06 |
| **FEA-06** | Installation & Extended Service Slot Booking | **MERGE** | Booking half of **Installation** cluster. EDS-07 is feasibility checker. Complementary layers, not duplicates, but same scheduling domain. Merge as Checker → Booking sequence. | **Installation** — merge FEA-06 + EDS-07 |
| **FEA-07** | Price Drop, Stock Alert & Wishlist Intelligence | **MERGE** | **Anchor** for Price/Stock Notifications. Most detailed (wishlist intelligence, price delta, restock ETA). Merge. | **Price/Stock Notifications** — anchor |
| **FEA-08** | Smart Compare Workspace (Persistent, Total-Cost Aware) | **MERGE** | **Anchor** for Smart Compare. Most complete (sticky bar, auto-populate, diff-highlight, total-cost pin, share URL). Merge. | **Smart Compare** — anchor |
| **FEA-09** | Complete-the-Setup Bundles & Consumables Attach | **MERGE** | Bundles half of Attach cluster. Adds bundle pricing + consumable cadence. Merge with PER-08/ECS-08. | **Complete-the-Setup** — anchor |
| **EDS-01** | AC Room-Size & Thermal Load Finder | **MERGE** | Category instantiation of Guided Selling (tonnage calculator). Not distinct from FEA-02 pattern — **layer**, not duplicate. Merge. | **Guided Selling** — AC lens |
| **EDS-02** | Refrigerator Capacity & Kitchen Space Validator | **MERGE** | Same pattern — litres→family + doorway guard. Layer, not duplicate. Merge. | **Guided Selling** — Fridge lens |
| **EDS-03** | TV Size–Distance–Resolution Advisor + Panel Explainer | **MERGE** | Same pattern — distance→size + HQLED decoder. Panel explainer half overlaps EDS-05 glossary; calculator half merges. Split: calculator → Guided Selling; glossary → EDS-05. | **Guided Selling** + **Jargon Decoder** |
| **EDS-04** | Washing Machine Capacity & Household Load Advisor | **MERGE** | Same pattern — kg→household. Layer. Merge. | **Guided Selling** — Washer lens |
| **EDS-05** | Spec Jargon Decoder & Energy Label Explainer | **KEEP** | **Unique.** Only cross-category glossary + running-cost translator. No other agent proposes tap-to-explain for EER/R32/HQLED/Twin inverter. Complements all EDS finders. Keep. | Decision Support — Glossary |
| **EDS-06** | True Cost & Energy Consumption Calculator | **MERGE** | Ownership-cost half of True Cost cluster. Adds 1yr/5yr math + purifier consumables. Merge with FEA-05. | **True Cost & EMI** |
| **EDS-07** | Installation & Site Compatibility Checker | **MERGE** | Feasibility half of Installation cluster (outdoor wall/drain/socket). Precursor to FEA-06 booking. Merge. | **Installation** |
| **EDS-08** | Electronics Comparison — Decisive-Attribute Lens | **MERGE** | Lens layer of Smart Compare (category-tuned decisive rows + verdict strip). Not workspace mechanics. Merge. | **Smart Compare** |
| **EDS-09** | Kitchen & Water Purifier Requirement Finder | **MERGE** | Same Guided Selling pattern for long-tail (wattage→use-case, TDS→filter). Layer. Lowest evidence (purifier 7 PDPs at `sitemap-analysis.md:44`) but valid as extension. Merge. | **Guided Selling** — Kitchen/Purifier lens |
| **ECS-01** | Aggregate Ratings, Review Count & On-Card Social Proof | **KEEP** | **Unique.** Only ratings/reviews proposal. Correctly identifies `ecommerce-capabilities.md:31-32` NOT OBSERVED + `issue-register.md:32` PDP-07 P1. Keep. | Standards — Confidence |
| **ECS-02** | Rich Product Media: Video, Zoom, 360° / Gallery Depth | **MERGE** | Duplicate of FEA-03. Merge. | **Rich Media** |
| **ECS-03** | Predictive Search Autocomplete, Suggestions & Recent Searches | **MERGE** | Foundation layer of Search. Duplicates PER-06 suggestion/Recent half but at non-personalized baseline. Merge as stage 1. | **Search** |
| **ECS-04** | Zero-Result Recovery, Typo Tolerance & Did-You-Mean | **KEEP** | **Distinct.** Only zero-result/typo tolerance proposal. No overlap with PER-06/ECS-03 (which are suggestions, not recovery). Addresses SEARCH-03 (`issue-register.md:19` P2) + `ecommerce-capabilities.md:15` NOT TESTED. Keep. | Standards — Search |
| **ECS-05** | Pre-Cart Delivery, Installation & Serviceability Estimator | **MERGE** | Duplicate of FEA-01/PER-07. Standards framing. Merge. | **Delivery Estimator** |
| **ECS-06** | Populated Cart Commerce Completeness (Qty/Coupon/Breakdown) | **REMOVE** | **UX-fix misclassification.** Empty-cart shell exists (`ecommerce-capabilities.md:40-41` VERIFIED empty, NOT TESTED populated). Quantity stepper, coupon field, price breakdown are **expected cart hygiene**, not an opportunity — maps directly to CART-02 (`issue-register.md:37` P2) + CHECKOUT-01 discovery gap. Reclassify to P1 remediation backlog, not opportunity register. | Remove — remediation |
| **ECS-07** | Active Filter/Sort Feedback: Chips, Counts, Clear-All & Sort Options | **REMOVE** | **UX-fix misclassification (clearest).** Filters/sort controls are VERIFIED present (`ecommerce-capabilities.md:16-22` VERIFIED headings); gap is missing feedback. Maps 1:1 to FILTER-01 P1, FILTER-02 P2, SORT-01 P1 (`issue-register.md:20-21,24`). This is restoring expected PLP feedback, not a new capability. Remove from opportunities; retain as P1 fix. | Remove — remediation |
| **ECS-08** | Complementary & Attach Recommendations (FBT/Bundles/Accessories) | **MERGE** | Duplicate of attach cluster (PER-08/FEA-09). Standards framing (catalog-driven FBT vs thin Related). Merge. | **Complete-the-Setup** |
| **ECS-09** | Browse Resumption: Recently Viewed & Continue Shopping | **MERGE** | Duplicate bundle of PER-01+PER-02. Merge. | **Browse Resumption** |
| **ECS-10** | Transparent Stock & Price Notifications with Timeline | **MERGE** | Duplicate of notification cluster (FEA-07/PER-09). Merge (ECS adds timeline promise). | **Price/Stock Notifications** |
| **ECS-11** | Needs-Based Guided Selling / Product Finder | **MERGE** | Verbatim duplicate of FEA-02. Different label, same room→tonnage / family→litres wizard. Merge. | **Guided Selling** |

**Summary fate:** KEEP 7 (PER-04, PER-05*, FEA-04, EDS-05, ECS-01, ECS-04 + 1 conditional), MERGE 28 (into 8 consolidated capabilities), REMOVE 3 (ECS-06, ECS-07, PER-09 tail seasonal).

---

## 2. Duplicate & Overlap Matrix

> Rows/cols are raw IDs. `D` = pure duplicate (same capability, different wording). `L` = layer (same parent, distinct facet — should be one capability with phases). `P` = partial overlap. Empty = no material overlap. Diagonal omitted.

|  | PER-01 | PER-02 | PER-03 | PER-04 | PER-05 | PER-06 | PER-07 | PER-08 | PER-09 | FEA-01 | FEA-02 | FEA-03 | FEA-04 | FEA-05 | FEA-06 | FEA-07 | FEA-08 | FEA-09 | EDS-01 | EDS-02 | EDS-03 | EDS-04 | EDS-05 | EDS-06 | EDS-07 | EDS-08 | EDS-09 | ECS-01 | ECS-02 | ECS-03 | ECS-04 | ECS-05 | ECS-06 | ECS-07 | ECS-08 | ECS-09 | ECS-10 | ECS-11 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **PER-01** | — | L |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | D |  |  |
| **PER-02** | L | — |  |  | P |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | D |  |  |
| **PER-03** |  |  | — |  |  |  |  |  |  |  |  |  |  |  |  |  | L |  |  |  |  |  |  |  |  | L |  |  |  |  |  |  |  |  |  |  |  |  |
| **PER-04** |  |  |  | — | P |  |  |  |  |  |  |  |  |  |  |  |  | P |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | P |  |  |  |
| **PER-05** |  | P |  | P | — |  |  |  | P |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | P | P |  |
| **PER-06** |  |  |  |  |  | — |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | D | P |  |  |  |  |  |  |  |
| **PER-07** |  |  |  |  |  |  | — |  |  | D |  |  |  |  | P |  |  |  |  |  |  |  |  |  | P |  |  |  |  |  |  | D |  |  |  |  |  |  |
| **PER-08** |  |  |  |  |  |  |  | — |  |  |  |  |  |  |  |  |  | D |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | D |  |  |  |
| **PER-09** |  |  |  |  | P |  |  |  | — |  |  |  |  |  |  | D |  | P |  |  |  |  |  | P |  |  |  |  |  |  |  |  |  |  |  | D |  |
| **FEA-01** |  |  |  |  |  |  | D |  |  | — |  |  |  |  | L |  |  |  |  |  |  |  |  |  | L |  |  |  |  |  |  | D |  |  |  |  |  |  |
| **FEA-02** |  |  |  |  |  |  |  |  |  |  | — |  |  |  |  |  |  |  | L | L | L | L | P | P |  |  | L |  |  |  |  |  |  |  |  |  | D |
| **FEA-03** |  |  |  |  |  |  |  |  |  |  |  | — |  |  |  |  |  |  |  |  |  |  |  |  | P |  |  |  | D |  |  |  |  |  |  |  |  |
| **FEA-04** |  |  |  |  |  |  |  |  |  |  |  |  | — |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| **FEA-05** |  |  |  |  |  |  |  |  |  |  |  |  |  | — |  |  | P |  |  |  |  |  |  | D |  | P |  |  |  |  |  |  |  |  |  |  |  |
| **FEA-06** |  |  |  |  |  |  | P |  |  | L |  |  |  |  | — |  |  |  |  |  |  |  |  |  | D |  |  |  |  |  |  | P |  |  |  |  |  |
| **FEA-07** |  |  |  |  |  |  |  |  | D |  |  |  |  |  |  | — |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | D |  |
| **FEA-08** |  |  | L |  |  |  |  |  |  |  |  |  |  | P |  |  | — |  |  |  |  |  |  | P |  | L |  |  |  |  |  |  |  |  |  |  |  |
| **FEA-09** |  |  |  | P |  |  |  | D | P |  |  |  |  |  |  |  |  | — |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | D |  |  |  |
| **EDS-01** |  |  |  |  |  |  |  |  |  |  | L |  |  |  |  |  |  |  | — |  |  |  | P | P |  |  |  |  |  |  |  |  |  |  |  |  | D |
| **EDS-02** |  |  |  |  |  |  |  |  |  |  | L |  |  |  |  |  |  |  |  | — |  |  |  |  | P |  |  |  |  |  |  |  |  |  |  |  | D |
| **EDS-03** |  |  |  |  |  |  |  |  |  |  | L |  |  |  |  |  |  |  |  |  | — |  | P |  |  | P |  |  |  |  |  |  |  |  |  |  | D |
| **EDS-04** |  |  |  |  |  |  |  |  |  |  | L |  |  |  |  |  |  |  |  |  |  | — |  |  |  |  |  |  |  |  |  |  |  |  |  |  | D |
| **EDS-05** |  |  |  |  |  |  |  |  |  |  | P |  |  |  |  |  |  |  | P |  | P |  | — | P | P | P |  |  |  |  |  |  |  |  |  |  |  |
| **EDS-06** |  |  |  |  | P |  |  |  | P |  | P |  |  | D |  |  | P |  | P |  |  |  | P | — |  | P |  |  |  |  |  |  |  |  |  | P |  |
| **EDS-07** |  |  |  |  |  |  | P |  |  | L |  | P |  |  | D |  |  |  |  | P |  |  | P |  | — |  |  |  |  |  |  | P |  |  |  |  |  |
| **EDS-08** |  |  | L |  |  |  |  |  |  |  |  |  |  | P |  |  | L |  |  |  | P |  | P | P |  | — |  |  |  |  |  |  |  |  |  |  |  |
| **EDS-09** |  |  |  |  |  |  |  |  |  |  | L |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | — |  |  |  |  |  |  |  |  |  | D |
| **ECS-01** |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | — |  |  |  |  |  |  |  |  |  |
| **ECS-02** |  |  |  |  |  |  |  |  |  |  |  | D |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | — |  |  |  |  |  |  |  |  |
| **ECS-03** |  |  |  |  |  | D |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | — | P |  |  |  |  |  |  |
| **ECS-04** |  |  |  |  |  | P |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | P | — |  |  |  |  |  |  |
| **ECS-05** |  |  |  |  |  |  | D |  |  | D |  |  |  |  | P |  |  |  |  |  |  |  |  |  | P |  |  |  |  |  |  | — |  |  |  |  |  |
| **ECS-06** |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | — |  |  |  |  |
| **ECS-07** |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | — |  |  |  |
| **ECS-08** |  |  |  | P |  |  |  | D |  |  |  |  |  |  |  |  |  | D |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | — |  |  |
| **ECS-09** | D | D |  |  | P |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  | — |  |
| **ECS-10** |  |  |  |  |  |  |  |  | D |  |  |  |  |  |  | D |  |  |  |  |  |  |  | P |  |  |  |  |  |  |  |  |  |  |  |  | — |  |
| **ECS-11** |  |  |  |  |  |  |  |  |  |  | D |  |  |  |  |  |  |  | D | D | D | D |  |  |  |  | D |  |  |  |  |  |  |  |  |  |  | — |

**Reading note:** `D` at row PER-01 / col ECS-09 means PER-01 duplicates ECS-09. `L` at PER-03 / FEA-08 means layers of one parent — consolidate, don't count twice. `P` is partial conceptual overlap worth noting but not a merge trigger alone.

### Consolidated Duplicate Clusters (the 6 that drive 55% duplication)

| Cluster | Capability | Raw members (n) | Duplicate type | Evidence that it is one capability |
|---|---|---|---|---|
| **C1 Delivery Estimator** | Pincode-first total landed cost (delivery + install + store pickup + timeline, session-persistent, pre-cart) | PER-07 + FEA-01 + ECS-05 (3) | **Pure duplicate** — same inputs (pincode/area/district), same outputs (fee, SLA, free-install flag, store alt), same placement (PDP block → Cart summary). All three cite `page-analysis.md:125` gate + `product-page-variations.md:59-60` + `ecommerce-capabilities.md:42-44`. Only difference is framing (personalization persistence vs fulfillment engine vs standards baseline). | `ecommerce-capabilities.md:42-44` VERIFIED preview-only gate; `issue-register.md:27` PDP-02 P1; `page-analysis.md:34` trust bar selective — single serviceability engine solves all three phrasings. |
| **C2 Browse Resumption** | Recently Viewed + Continue Shopping (anonymous → authenticated, item-level + filtered-PLP context) | PER-01 + PER-02 + ECS-09 (3) | **Duplicate bundle vs split.** PER correctly splits item vs context; ECS bundles them as one capability. They share store (`localStorage` viewHistory/lastPlpUrl) and placement (homepage, PLP, empty cart). | `personalization-current-state.md:9-10` NOT OBSERVED + `issue-register.md:14` DISC-02 P1 + `ecommerce-capabilities.md:55` NOT OBSERVED |
| **C3 Smart Compare** | Persistent, auto-populated, total-cost-aware, decisive-attribute comparison | PER-03 + FEA-08 + EDS-08 (3) | **Layers, not duplicates** — persistence (PER-03) + workspace mechanics + total-cost pin (FEA-08) + category lens + verdict (EDS-08) are phases of one decision board. All cite `page-analysis.md:173-178` empty 3-slot + `page-analysis.md:129` Compare entry + `issue-register.md:41` INTERACTION-01 P1. | Three proposals for one `(/compare)` page; building any one without the other two leaves the journey broken. |
| **C4 Guided Selling** | Requirement-led finders (room→tonnage, family→litres, distance→size, kg→load, wattage→task, TDS→filter) | FEA-02 + EDS-01 + EDS-02 + EDS-03calc + EDS-04 + EDS-09 + ECS-11 (7) | **Umbrella + instantiations.** FEA-02/ECS-11 are the umbrella pattern (3-step wizard → filtered PLP); EDS-01/02/03/04/09 are category-specific instantiations sharing the same PLP filter mapping and PDP verdict pattern. EDS-03 panel explainer half belongs to glossary. | `product-discovery.md:77-83` facets exist, advisor `NOT OBSERVED`; `issue-register.md:10` IA-03 SEO wall; `product-detail-experience.md:12` tab-hidden fit data — one finder framework serves all categories. |
| **C5 Attach / Bundles (Complete-the-Setup)** | Frequently Bought Together / Bundles / Cart-context cross-sell | PER-08 + FEA-09 + ECS-08 (3) | **Pure duplicate.** Same accessory affinity (TV→mount/soundbar, AC→stabilizer/bracket, washer→stand/detergent, purifier→cartridge). All cite `ecommerce-capabilities.md:56` FBT NOT OBSERVED + `product-page-variations.md:66-67` single Related card. Placement differs (cart vs PDP vs PLP) but capability is one bundle rule engine. | One complement-affinity table + PDP/cart bundle UI; proposing it three times inflates perceived breadth. |
| **C6 Price/Stock Notifications** | Wishlist-gated price-drop + back-in-stock alerts with timeline/ETA | PER-09 head + FEA-07 + ECS-10 (3) | **Pure duplicate.** Same wishlist plumbing (authenticated persistence), same triggers (savedPrice vs current, `Currently Unavailable` at `page-analysis.md:113`), same promise (timeline/ETA). PER-09 adds lifecycle seasonal tail which is separate and generic. | `ecommerce-capabilities.md:49` VERIFIED Get Stock Alert button, `ecommerce-capabilities.md:54` Price Alerts NOT OBSERVED, `issue-register.md:43` FEEDBACK-02 — one notification service serves all three. |
| **C7 Search** | Autocomplete / Suggestions / Recent Searches (plus typo-recovery) | PER-06 + ECS-03 (+ ECS-04 adjacent) (2+1) | **Layered duplicate.** PER-06 is personalized ranking layer atop ECS-03 foundational autocomplete. ECS-04 (zero-result recovery) is adjacent but distinct (fuzzy/Did-you-mean vs suggestions). Count as one capability with two maturity stages. | `ecommerce-capabilities.md:12-13` input VERIFIED, suggestions NOT FULLY VERIFIED + `issue-register.md:17-19` SEARCH-01 P1 / SEARCH-03 P2 |
| **C8 Rich Media** | Video, Zoom, 360°, Dimension Overlay | FEA-03 + ECS-02 (2) | **Pure duplicate.** Same asset pipeline (brand images/video/360), same PDP gallery region (`page-analysis.md:134-135` placeholders, `product-page-variations.md:49-50` 68 DOM images, `ecommerce-capabilities.md:30` Video NOT OBSERVED). Dimension overlay is FEA-unique facet but not enough to be separate. | One viewer component; video-dependent vs zoom-only is phasing, not separate opportunities. |
| **C9 True Cost & EMI** | EMI planner + energy/consumable total-cost calculator | FEA-05 + EDS-06 (2) | **Layered overlap.** FEA-05 = bank-aware financing planner (tenure/bank/monthly); EDS-06 = ownership cost (energy + consumable + EMI). Share EMI eligibility matrix and PDP→Cart persistence. Build as one True Cost row. | `page-analysis.md:114-117` EMI badges + `product-page-variations.md:55` Haier fridge EMI absence + `issue-register.md:31` PDP-06 inconsistency |

*Effectively 9 clusters account for 26 of 38 rows. Retiring duplicates collapses to ≤15 deduplicated capabilities (§8).*

---

## 3. Detailed Overlap Adjudication — Duplicate vs Related Distinct vs Layer

| Concept pair | Verdict | Reasoning |
|---|---|---|
| **Personalized Recommendations (PER-04) vs Related Products (existing) vs Behavioral Recs** | **Related distinct — not duplicate.** Existing `Related Products` is VERIFIED generic single-card (laptop→laptop at `product-discovery.md:106`), catalog-driven, not browsing-aware. PER-04 is behavioral re-ranking by viewHistory/categoryAffinity — net-new. Agents correctly distinguished generic vs true personalization (`personalization.md:26-33`). No merge. | Keep PER-04. Do not conflate with ECS-08 FBT. |
| **Recently Viewed (PER-01) vs Continue Shopping (PER-02)** | **Layers of one capability — not two opportunities.** Both are browse-resumption memory using same store and same empty-state placements. Splitting as two inflates count. One Browse Resumption capability with two surfaces (item rail + filtered-PLP deep-link) is correct. | Merge PER-01+PER-02+ECS-09. |
| **Resume Comparison (PER-03) vs Smart Compare (FEA-08) vs Decisive-Attribute Lens (EDS-08)** | **Three layers of one decision board.** PER-03 = "remember my picks", FEA-08 = "populate and pin total-cost", EDS-08 = "tint decisive rows + verdict". None delivers Journey D (`user-journey-friction.md:75-96` P1) alone. Treating as 3 opportunities implies 3 builds; it is one build with three acceptance criteria. | Merge into one Smart Compare. |
| **AC Finder (EDS-01) vs Fridge Validator (EDS-02) vs TV Advisor (EDS-03) vs Washer Advisor (EDS-04) vs Kitchen Finder (EDS-09) vs Room/Capacity Advisor (FEA-02)** | **Umbrella + category lenses — not 6 duplicates.** FEA-02/ECS-11 describe the pattern; EDS-01–04/09 are valid category instantiations. Counting each as equal-weight duplicates is wrong, but counting them as 6 independent opportunities overstates breadth — it is one framework with 5 content packs. Critique: EDS-09 long-tail (trimmer/mixer/purifier) borrows credibility from AC/TV/ fridge but has thinner evidence and lower ticket — de-prioritise. | Merge into one Guided Selling with phased lenses. |
| **EMI Planner (FEA-05) vs True Cost Calculator (EDS-06)** | **Overlap — merge into one True Cost row.** FEA-05 without energy/consumable still leaves sticker-price illusion; EDS-06 without EMI silences PDP-06 ambiguity. The PDP needs a single `Ownership: Price + Energy + Install + EMI/month` row. Two proposals that each rebuild half the row = duplication. | Merge FEA-05+EDS-06. |
| **Pincode Estimator (FEA-01) vs Location-Aware Delivery (PER-07) vs Serviceability Estimator (ECS-05)** | **Pure duplicate — not layers.** All three specify the same pincode input → same serviceability matrix → same PDP→Cart propagation. "Location-aware" without pincode is already proven failed (`issue-register.md:27` PDP-02 gate). Only the pincode-first estimator pattern solves it. | Merge to single estimator; keep FEA-01 as anchor (most complete). |
| **Price/Stock Alerts (PER-09 head) vs Wishlist Intelligence (FEA-07) vs Transparent Notifications (ECS-10)** | **Pure duplicate.** All three wish for wishlist-gated alerting with price delta + restock ETA. The divergence is copy ("transparent timeline" vs "intelligence") not capability. Seasonal nudge tail in PER-09 is unrelated — detach and discard. | Merge three; discard seasonal tail. |
| **Cart Complements (PER-08) vs Setup Bundles (FEA-09) vs FBT (ECS-08)** | **Pure duplicate.** PDP bundle vs cart rail vs FBT checkbox are placements, not capabilities. One affinity rule set (AC↔stabilizer, TV↔mount) drives all. The consumable cadence (purifier cartridge) in FEA-09 is the only distinct extension — keep as phase 2 of same bundle. | Merge. |
| **Rich Media (FEA-03) vs Rich Media (ECS-02)** | **Pure duplicate.** | Merge. |
| **Personalized Search (PER-06) vs Autocomplete (ECS-03)** | **Foundation vs personalization layer — not duplicate but must not be double-counted as two opportunities.** ECS-03 is P0 hygiene (type-ahead + recent); PER-06 is ranking boost by affinity/history. Building ECS-03 suffices for immediate value; PER-06 is phase 2 ranking. Keep as one capability with two stages; do not sum as two. | Merge as Search with staged maturity. |
| **Jargon Decoder (EDS-05) vs Product Finder (FEA-02)** | **Related distinct — keep separate.** EDS-05 is inline glossary + running-cost translator (tap EER→Tk/month); FEA-02 is guided wizard. Both rely on specs but serve different moments: PDP research vs PLP entry. Not duplicate. | Keep EDS-05 distinct. |
| **Installation Checker (EDS-07) vs Slot Booking (FEA-06)** | **Sequential layers — checker before booking.** EDS-07 = feasibility (outdoor wall/drain/socket) prevents failed installs; FEA-06 = scheduling (calendar slot). Different owners (content checklist vs ops scheduling) but same installation domain. Building booking without checker re-creates waste. Merge as one Installation capability with two gates. | Merge as Installation. |

---

## 4. Generic / Unsupported / Already-Exists Analysis

### 4.1 Generic Recommendations (Masquerading as Personalization or Value)

| ID | Claim | Why it is generic / low-signal | Action |
|---|---|---|---|
| **PER-09 seasonal tail** — "For you — Prepare for summer: Inverter ACs in your viewed range" (`personalization.md:356`) | Segment = `affinity == AC && month in [Feb-Apr]` → show AC module. This is **campaign segmentation**, not True Personalization. No behavioral trigger beyond static calendar + broad affinity. Identical to merchandising scheduling with an affinity filter. Fails PER's own True Personalization test (`personalization.md:30-33` requires user-specific signal vs static shelf). | **REMOVE tail** as opportunity; treat as campaign optimisation, not a new capability. Head (wishlist price/stock) remains valid. |
| **PER-08 / FEA-09 / ECS-08 bundle for low-ticket** | Proposing stabilizer/mount attach for TV/AC is valid; extending same bundle logic to trimmers/mixers ("extra jar", "vacuum bags") at Tk 2k–5k (`personalization.md:313` suppression note acknowledges this) is generic attach that existing Related Products already covers. Dilutes bundle credibility. | **SCOPE-NARROW:** bundles only for AC/Fridge/TV/Washer/Purifier (high-ticket attach). Suppress for low-ticket; do not proposal-count. |
| **FEA-02 / ECS-11 generic SEO-to-finder rewrite** | The SEO buying-guide text (`site-inventory.md:70`) is correctly diagnosed as IA-03 burden, but re-presenting it as a 3-step wizard without validated tonnage/litres rule tables is **content re-format, not capability** unless tables are governed. Without brand-spec validation, "generic transformation" claim is unsupported. | Keep but require **rule-table governance** as hard dependency; not generic but at risk of being generic. |

### 4.2 Unsupported (Evidence Gap or Dependency Unproven)

| ID | Unsupported aspect | Evidence gap | Consequence |
|---|---|---|---|
| **FEA-06 Slot Booking** | "Slot capacity by district/installer team" + "order ↔ service order linkage" (`features.md:127`) | No slot inventory feed observed; `ecommerce-capabilities.md:62` Service Tracking is OBSERVED link only; checkout steps NOT ACCESSIBLE (`ecommerce-capabilities.md:42`). FEA correctly tags Complexity High but understates that **no scheduling backend exists**. | Feasibility RISK: building UI without ops capacity = broken promise worse than no booking. Gate behind logistics confirmation; **phase after EDS-07 checker**. |
| **EDS-02 doorway guard / EDS-07 site checks** | Requires W×H×D per SKU normalized + ventilation gap spec for every large-appliance PDP | Current spec table content is `OBSERVED` heading only (`ecommerce-capabilities.md:28` Content NOT TESTED); only 8 PDP samples. No proof field `dimensions` is structured. | Content RISK: dimension overlay / site verdict will be empty until catalog enrichment. Treat as catalog-modeling dependency, not UI-only. |
| **PER-09 price/stock feed** | "Price history / stock ETA feed" (`personalization.md:344-345`) | `ecommerce-capabilities.md:38,54` Wishlist persistence and Price Alerts are AUTHENTICATION REQUIRED / NOT OBSERVED. No feed sampled. | Dependency is real; complexity High is accurate. Do not block on notifications. |
| **PER-05 homepage reorder** | Homepage CMS modularity to support reordering/suppression (`personalization.md:214`) | `page-analysis.md:48-54` shows 7+ serial grids but no evidence CMS is modular. Assumption unvalidated. | Risk of High effort for Medium lift; keep as P2 experiment with CMS audit gate. |

*No opportunity is outright fabricated — all tie to a NOT OBSERVED gap. Unsupported flags are **dependencies**, not hallucinations.*

### 4.3 Already-Exists (Would Duplicate VERIFIED Capability)

| Checked | Result |
|---|---|
| **Related/Latest/Best Deals rails** — generic curation | VERIFIED (`ecommerce-capabilities.md:10-11,34`) — agents correctly **did not re-propose** generic Related as opportunity; all proposals add browsing/behavioral or bundle signal. PASS. |
| **EMI Financing** | VERIFIED badge/text (`ecommerce-capabilities.md:47`, `page-analysis.md:114-117`). FEA-05/EDS-06 propose **interactive planner + calculator**, not a badge — net-new. PASS. |
| **Stock Alert button** | VERIFIED on Dell outlier (`ecommerce-capabilities.md:49`). FEA-07/ECS-10 propose **wishlist intelligence + price-drop + ETA transparency** — net-new. PASS. |
| **Wishlist/Compare entry + empty page** | VERIFIED empty states (`ecommerce-capabilities.md:36-37,23-24`). PER-03/FEA-08 propose **persistence + auto-populate + total-cost** — net-new. PASS. |
| **Video / Gallery** | Video NOT OBSERVED (`ecommerce-capabilities.md:30`), gallery OBSERVED placeholders — FEA-03/ECS-02 propose viewer + video — net-new. PASS. |
| **Delivery gate** | VERIFIED preview gated (`ecommerce-capabilities.md:42-44`) — estimator proposes **pincode calculation** — net-new. PASS. |

**Conclusion:** Zero of 38 proposals duplicate a VERIFIED complete capability. Agents' verification discipline is strong. Only risk is **re-labeling a fix as opportunity** (see §5), not re-proposing existing.

---

## 5. UX-Fix Misclassifications — Opportunities That Are Actually Fixes

> Boundary rule used (from `features.md:9-30`): *If it can be shipped as a string fix, copy change, or CSS/ARIA restoration of an expected control, it is a fix.*

| ID | Title | Why it is a fix, not an opportunity | Correct home | Severity |
|---|---|---|---|---|
| **ECS-07** | Active Filter/Sort Feedback: Chips, Counts, Clear-All & Enumerated Sort | Filter checkboxes, Reset link, and Sort control shell are VERIFIED (`ecommerce-capabilities.md:16-22`). Gap is missing chip row + empty `sortOptions: []` (`issue-register.md:24` SORT-01, `page-analysis.md:75-82`). This is **restoring expected PLP feedback** of existing controls (Nielsen "visibility of system status"). No new data model. | **Remediation backlog — P1** FILTER-01 P1, SORT-01 P1, FILTER-02 P2. Belongs in `02-ux-audit` follow-through, not opportunity register. | **Remove** from opportunities |
| **ECS-06** | Populated Cart Commerce Completeness: Quantity, Coupon, Breakdown, Save-for-Later & Cross-Sell | Empty cart shell is VERIFIED (`ecommerce-capabilities.md:39,41`). Quantity stepper + coupon + breakdown are **baseline cart completeness** expected once populated. `issue-register.md:37` CART-02 explicitly flags this as a P2 risk with `NOT TESTED populated`. The gap is untested wiring, not missing capability. Cross-sell part belongs to C5 bundles — detach. | **Remediation + bundle placement.** Quantity/coupon/breakdown → P1 cart hygiene fix; cross-sell → C5 bundles. Do not count as standalone opportunity. | **Remove** (split) |
| **ECS-03** (boundary case, keep but caveat) | Predictive Search Autocomplete | Input is VERIFIED (`ecommerce-capabilities.md:12`), suggestions NOT VERIFIED. Autocomplete is plausibly foundational hygiene BUT searching on `FTKL12TV16WD` alphanumeric codes (`ecommerce-standards.md:78`) does justify an opportunity lens. Verdict: **keep as opportunity** because dropdown behavior was NOT TESTED live, but flag that empty suggestion list may be a **rendering bug, not missing index**. Requires live re-test before build. | Keep as ECS-03 but gate behind search index verification. | Keep* |

*ECS-07 and ECS-06 together remove 2 of 11 ECS proposals — consistent with Phase 2's warning that 40% of audit findings are P1 hygiene, not opportunities.*

**Not misclassified (often mistaken):**
- `FEA-01` pincode estimator vs `PDP-02` gate fix: gate → pincode field is a fix, but **serviceability engine with SLA/fee/store alt and Cart propagation** is a new fulfillment service — correctly classified as feature.
- `FEA-08` compare auto-populate vs `INTERACTION-01` hand-type: autocomplete is a fix, but **persistent workspace + total-cost pin + share URL** is a new decision system — correctly classified.
- `FEA-04` variant navigator vs `PDP-08` inconsistency: second tonnage button is a fix for AC only; **family graph for all families** is new catalog capability — correctly classified.

---

## 6. Category Misplacements (Right Idea, Wrong Owner)

| ID | Current placement | Correct domain | Why move |
|---|---|---|---|
| **PER-07** | Personalization | **Delivery / Fulfillment (Features)** | Core is pincode serviceability engine (logistics matrix). Personalization only owns "remember pincode in session" — 20% of effort. Decision rights and dependencies sit with logistics/catalog, not affinity scoring. |
| **PER-08** | Personalization | **Merchandising / Features** | Core is complement affinity rules per family (TV→mount, AC→stabilizer). Cart-contingency is trigger logic, but rule definition is merchandising. Personalization framing overstates behavioral need. |
| **ECS-09** | E-commerce Standards | **Personalization (Retention)** | Recently Viewed / Continue Shopping are intrinsically personalization — history-dependent, user-specific. Standards framing as "foundational" is correct for urgency but engineering ownership is personalization store, not platform baseline. Reassign to personalization implementer. |
| **ECS-02 / FEA-03** | Both claim ownership (Standards vs Features) | **PDP Content / Features** | Rich media is not standards differentiation nor a pure feature — it is PDP media pipeline + asset production. Consolidate under PDP/content owner, not two. Single owner. |
| **EDS-06 / FEA-05** | Split: Features vs Decision Support | **Single True Cost owner** | Splitting EMI (finance) and energy (literacy) across two agents created the most obvious overlap. One True Cost owner should hold both rows. |

*Misplacement does not mean the idea is wrong — it means prioritisation and sequencing will fail if implementation stays in the wrong squad.*

---

## 7. Missing High-Value Gaps — None of the 4 Agents Covered

> Each gap is evidenced as P1/P2 in `issue-register.md` or VERIFIED state in `ecommerce-capabilities.md`, but **zero of 38 proposals** addresses it. Flagged only, not elaborated into new opportunities.

| # | Gap | Evidence | Why it matters (Tk 50k–1.5L context) | Why missed* |
|---|---|---|---|---|
| **M-01** | **Checkout discoverability & trust: steps, address/delivery/payment preview** | `issue-register.md:38` CHECKOUT-01 P1 HIGH; `ecommerce-capabilities.md:42` Checkout Steps NOT ACCESSIBLE; `cart-checkout.md:21` journey blocked. No proposal addresses what checkout *is* (progress, payment options, COD assurance). | Journey E stalls at cart → checkout boundary. PDP estimator + EMI planner solve pre-cart confidence but **checkout itself remains a black box** until items are added. Highest P1 conversion gap after delivery is checkout preview. | Agents focused on PDP/PLP discovery, not funnel. |
| **M-02** | **Information architecture: IA-03 SEO wall vs product grid + IA-01 flat PDP URLs + NAV-01 `/undefined`** | `issue-register.md:7-11` NAV-01 P0, IA-01 P1, IA-03 P1, IA-02 P2; `executive-summary.md:5` catalog shell vs decision-thin. No opportunity addresses **content architecture** (layering SEO below fold / tabbed vs grid priority) or **URL hierarchy**. | IA-03 pushes 1,500-word SEO wall above filters on every L1/L2 — advisors are proposed **above filters** but IA remains broken. Advisors built on broken IA inherit scroll cost. | Agents treat IA as Phase 2 fix, not strategic opportunity. |
| **M-03** | **Trust-bar → PDP propagation (TRUST-01) + Warranty nomenclature repair** | `issue-register.md:35` TRUST-01 P2 HIGH (`Free Installation Selective Items` homepage-only), `issue-register.md:30` PDP-05 warranty `Parts-0 M / Motor-300 M`; `page-analysis.md:34` trust bar vs PDP OPTIONS divergence. No proposal unifies trust claims as PDP-bound truth. | Homepage trust is built then dissipated at PDP where it is needed. Estimator fixes install fee for that SKU but not "Original Product Guaranteed / Secure Payment" propagation. | Overlap partially covered by FEA-01/EDS-05 but not as trust system. |
| **M-04** | **Mobile performance & homepage load (MOBILE-01) + PLP density** | `issue-register.md:46` MOBILE-01 P2; `product-page-variations.md:49` 68 images DOM on Mixer PDP; `page-analysis.md:48-54` 7+ mini-grids + 11 See All. Zero proposals address mobile weight, image optimisation, or homepage triage (agents propose *adding* rails). | `DISC-01` P1 overload is cited, but solutions add *more* rails (Recently Viewed, Browsing-aware, finder) without culling weight. On low-bandwidth mobile (Bangladesh), this compounds. | Feature agents default to addition, not subtraction. |
| **M-05** | **Authentication friction (AUTH-01) + AUTH-02 guest-to-auth continuity** | `issue-register.md:39-40` AUTH-01 P2, AUTH-02 P2; `ecommerce-capabilities.md:38,58-60` wishlist/persistence AUTHENTICATION REQUIRED. No proposal addresses OTP split-field friction, no password/social alt, or guest→auth memory migration (viewHistory/compareQueue handoff). | Personalization proposals assume anonymous→authenticated sync "phase 2" but never design it. Without it, PER-01/03/09 lose cross-device value and wishlist intelligence collapses. | Auth treated as out-of-scope; but it is the gate for all lifecycle personalization. |
| **M-06** | **Post-purchase Track Order / Track Service enhancement** | `ecommerce-capabilities.md:61-62` Track Order/Service OBSERVED links, flows NOT TESTED; `features.md:122-125` FEA-06 touches Order History but no standalone order/service tracking modernisation. PDP-heavy proposals dominate; post-purchase is afterthought. | High-ticket buyers track delivery/install obsessively. Existing `Track Order Status` / `Track Your Service` (`page-analysis.md:7-8`) are header links with no evidence of proactive updates. Retention loop incompleteness. | Post-purchase is correctly scoped but under-weighted vs PDP. |
| **M-07** | **Navigation — Brand vs Search canonical duplication (NAV-02) + Category tile mismatch (DISC-04)** | `issue-register.md:12` NAV-02 P2 (`/samsung` vs `/search?Brand=samsung` identical sets), `issue-register.md:16` DISC-04 tile vs taxonomy mismatch. No proposal addresses canonicalisation, sitemap hygiene (`sitemap-analysis.md:131` trailing-hyphen slugs), or brand PLP distinctiveness. | SEO crawl waste + user "which is authoritative?" confusion. Finder pattern exacerbates without canonical PLP distinction. | IA issues assumed as fix, but canonical strategy is opportunity-level (SEO + discovery). |
| **M-08** | **Exchange promotion integration + EMI Bank List distinctiveness** | `ecommerce-capabilities.md:52` Exchange hub VERIFIED (Fridge/WM only), `site-inventory.md:58` exchange context; `page-analysis.md:22-26` EMI Bank List footer; `product-discovery.md:46` campaign-filtered search. No proposal leverages exchange as decision lever (trade-in estimator at PDP) or clarifies EMI vs exchange trade-off at price. | Exchange is a Transcom differentiator vs Daraz/Pickaboo for large appliances — entirely unexploited beyond top-funnel hub. EMI planner proposes bank choice but not exchange-vs-EMI comparison. | Agents focused on net-new finders, not existing promo assets. |

*\* "Why missed" is not blame — it reflects each agent's charter (personalization → behavioral, features → net-new, electronics → spec, standards → baseline). Cross-review's job is to catch what falls between charters.*

**Not flagged as missing (adequately covered or correctly excluded):**
- Video/zoom (covered), ratings (covered), filter/sort chips (already a fix), Recently Viewed (covered), pincode estimator (covered), comparison workspace (covered), EMI/energy (covered), bundles (covered), finders (covered in depth), jargon decoder (covered). No need to re-propose.

---

## 8. Consolidated Deduplicated Capability Set

> Merge of 38 → **15 capabilities**. This is not a new opportunity list — it is the **minimum viable opportunity register** after deduplication, for sequencing reference. Each row cites anchor files:line and required dependencies.

| # | Consolidated Capability | Raw constituents | Classification | Dependencies / Enabler | Phase hint |
|---|---|---|---|---|---|
| **C1** | **Delivery & Serviceability Estimator** (pincode, SLA, fee, free-install flag, store pickup alt, Cart propagation) | PER-07 + FEA-01 + ECS-05 | Foundational (conversion) | Pincode/area master + zone/SLA matrix + install fee table + store inventory feed; session persistence | Phase 1 (P0) — unblocks all high-ticket |
| **C2** | **Browse Resumption** (Recently Viewed rail + Continue Shopping deep-link) | PER-01 + PER-02 + ECS-09 | Foundational (retention) | localStorage schema viewHistory + lastPlpUrl + compareQueue; UI rails (homepage, PLP, empty cart) | Phase 1 (P0) — cheapest lift |
| **C3** | **Smart Compare** (persistent bar, auto-populate, diff-highlight, total-cost pin, decisive-attribute lens, share URL) | PER-03 + FEA-08 + EDS-08 | Foundational → Differentiator | Compare store (session+auth), spec normalization per category, delivery/EMI/energy feeds (C1+C9) | Phase 1–2 (P1) — fixes Journey D P1 |
| **C4** | **Guided Selling Framework** (wizard → filtered PLP → PDP verdict; lenses: AC tonnage, Fridge litres/door, TV size, Washer kg, Kitchen/purifier wattage/filter) | FEA-02 + EDS-01 + EDS-02 + EDS-03calc + EDS-04 + EDS-09 + ECS-11 | Differentiator | Rule tables per category (sq ft→ton, litres→family, distance→size, wattage→task, TDS→filter) validated by brand specs; PLP filter mapping | Phase 2 (content + logic) — shippable per lens (AC first) |
| **C5** | **Complete-the-Setup (FBT / Bundles / Attach)** | PER-08 + FEA-09 + ECS-08 | Enhancement → Differentiator | Complement rule set per family; bundle CMS; cart grouped lines; inventory/price delta; suppress low-ticket | Phase 2 |
| **C6** | **Price/Stock Notifications & Wishlist Intelligence** | PER-09 head + FEA-07 + ECS-10 | Enhancement (retention) | Authenticated wishlist; price history; stock ETA feed; SMS/email consent; on-site banner system | Phase 2–3 (needs auth + feed) |
| **C7** | **Search (Stage 1: Autocomplete + Recent; Stage 2: Personalized ranking)** | ECS-03 + PER-06 | Foundational → Enhancement | Suggestion index (title/SKU/brand/category), debounced UI, searchHistory store, affinity bias (stage 2) | Stage 1 P0, Stage 2 after C2 |
| **C8** | **Zero-Result Recovery & Typo Tolerance (Did-you-mean)** | ECS-04 alone | Foundational (search hygiene) | Fuzzy index (edit distance), zero-result template, facet-relax hints | Phase 1 (short build) |
| **C9** | **True Cost & EMI Planner** (tenure/bank/monthly + energy kWh/month + install fee + Year-1 ownership; eligibility verdict) | FEA-05 + EDS-06 | Foundational (confidence) | EMI rule table × bank/tenure + tariff × EER + consumable cadence + price-threshold matrix | Phase 1–2 (rules + UI) |
| **C10** | **Rich Media Suite** (zoom/pinch, video per template, 360° where asset exists, dimension overlay) | FEA-03 + ECS-02 | Foundational (confidence) | Brand asset pipeline + spec dimensions normalized + gallery viewer; phased zoom → video | Phased (zoom first) |
| **C11** | **Spec Jargon Decoder & Energy Label Explainer** (tap-to-explain EER/R32/HQLED/Twin inverter + warranty legend) | EDS-05 alone (+ EDS-03 glossary half) | Enhancement (literacy) | Glossary CMS (25–40 terms, category-scoped) + running-cost formula + warranty legend | Phase 1 (content-only) — unblocks all finders |
| **C12** | **Installation Checker + Slot Booking** (site feasibility → bookable appointment, prerequisites, reschedule) | EDS-07 + FEA-06 | Differentiator (operations) | SKU install table (free/paid + fee) + checklist per appliance + slot capacity + order↔service linkage | Checker first (content), Booking after ops confirmed |
| **C13** | **Variant & Family Navigator** (sibling PDP chips with price delta + stock badge) | FEA-04 alone | Enhancement | Product family graph (model root → variants); variant dimension mapping; price/availability feed | Phase 1–2 (catalog modeling) |
| **C14** | **Social Proof (Ratings, Review Count, On-Card Badges + Customer Review buckets)** | ECS-01 alone | Foundational (trust) | Review submission/moderation + aggregation + PLP badge + PDP header; seeded "Be first" for thin catalogue | Phase 1 (pipeline) |
| **C15** | **Category-Affinity Homepage & PLP Prioritization** (returner module reorder; first-timer orientation) | PER-05* | Enhancement (growth) | Homepage CMS modularity; affinity scorer; A/B framework; governance vs campaign pins | Phase 3 experiment — deprioritise |

*Plus remediation backlog (not opportunities): Filter/Sort chips (FILTER-01/SORT-01), populated-cart quantity/coupon/breakdown (CART-02), and the 8 missing gaps M-01–M-08 to be triaged separately.*

---

## 9. Evidence Index (Cross-References)

| Claim | File:Line |
|---|---|
| Recently Viewed / Continue Shopping NOT OBSERVED as guest | `personalization-current-state.md:9-10`, `ecommerce-capabilities.md:55` NOT OBSERVED, `page-analysis.md:159-164` empty cart no history link, `issue-register.md:14` DISC-02 P1, `user-journey-friction.md:123-142` Journey F |
| Related Products VERIFIED thin (single HP cross-sell) | `ecommerce-capabilities.md:11` VERIFIED presence, `product-discovery.md:106` Dell→HP, `product-page-variations.md:65` Related single card, `issue-register.md:15` DISC-03 P2 |
| Ratings NOT OBSERVED / Review tab stars NOT VERIFIED | `ecommerce-capabilities.md:31-32` NOT OBSERVED, `page-analysis.md:132` tab label, `product-page-variations.md:57` tab presence, `issue-register.md:32` PDP-07 P1 |
| Video NOT OBSERVED / gallery placeholders / 68 images | `ecommerce-capabilities.md:30` NOT OBSERVED, `page-analysis.md:134-135` placeholders, `product-page-variations.md:49-50` controls NOT TESTED |
| Delivery gated `Enable your Location` | `page-analysis.md:125`, `product-page-variations.md:59-60`, `ecommerce-capabilities.md:42-44` VERIFIED preview-only, `issue-register.md:27` PDP-02 P1 |
| Trust bar selective install | `page-analysis.md:34` `Free Installation Selective Items`, `issue-register.md:35` TRUST-01 P2, `ecommerce-capabilities.md:45` OBSERVED trust bar |
| Installation line NOT OBSERVED | `product-page-variations.md:60` NOT OBSERVED, `ecommerce-capabilities.md:45-46` PDP detail NOT OBSERVED |
| EMI inconsistent (Haier fridge no EMI) | `product-page-variations.md:55` Haier 1.38L no EMI, `page-analysis.md:114-117` EMI badges, `ecommerce-capabilities.md:47` VERIFIED but inconsistent, `issue-register.md:31` PDP-06 P2 |
| Compare entry VERIFIED + empty 3-slot VERIFIED + populated NOT TESTED | `ecommerce-capabilities.md:23-25`, `page-analysis.md:173-178` 3 inputs + Highlight differences, `page-analysis.md:129` PDP Compare, `issue-register.md:41` INTERACTION-01 P1 |
| Wishlist/compare guest empty + auth required | `ecommerce-capabilities.md:36-38,57-58`, `page-analysis.md:168-171` guest empty, `issue-register.md:40` AUTH-02 P2 |
| Filter facets VERIFIED + chips/sort NOT ENUMERATED | `ecommerce-capabilities.md:16-22` VERIFIED headings, `page-analysis.md:75-82` sidebar, `issue-register.md:20-24` FILTER-01 P1, FILTER-02 P2, SORT-01 P1 |
| SEO guide pushes grid below fold | `site-inventory.md:70` long-form guide, `page-analysis.md:90-91`, `issue-register.md:10` IA-03 P1, `navigation-information-architecture.md:15` |
| Flat PDP URLs + `/undefined` + trailing hyphen | `sitemap-analysis.md:22-27` flat namespace, `sitemap-analysis.md:131` trailing hyphens, `site-inventory.md:92` `/undefined` hydration, `issue-register.md:7-11` NAV-01 P0, IA-01 P1 |
| Cart empty VERIFIED + populated NOT TESTED + checkout NOT ACCESSIBLE | `ecommerce-capabilities.md:39-42`, `page-analysis.md:159-164` empty, `user-journeys.md:98-103` populated NOT TESTED |
| Fit data tab-hidden (EER, Applicable sq ft) | `product-detail-experience.md:12-13` specification tab-hidden, `product-page-variations.md:61` warranty/ spec matrix, `issue-register.md:28-30` PDP-03/05 |

---

## 10. Severity & Recommendation Filters Applied

**What was challenged:**
1. **Counting layers as opportunities.** Four agents each applied diligence locally but none reconciled with peers. Result: delivery proposed 3×, browse resumption 3×, compare 3×, guided selling 7× — inflating perceived breadth from 15 to 38.
2. **Fixes dressed as features.** Standards agent correctly surfaced hygiene gaps but mis-filed two classic P1 fixes (filter/sort feedback, cart completeness) as opportunities — a category error that would misroute remediation into product backlog.
3. **Capability creep into adjacent domains.** Personalization extensions into logistics (pincode) and merchandising (bundles) borrow ownership that should sit with fulfillment and merch — sequencing will fail if not moved.
4. **Unsupported tail risk.** Seasonal personalization, slot booking without slot capacity, and dimension guards without structured dims are valid ideas gated by unfunded dependencies — staged, not immediate.

**What survived scrutiny:**
- Agents' **generic-vs-true personalization discipline** (`personalization.md:26-33`) is exemplary — true signal + trigger + labeling required for every PER. No proposal would duplicate an already-personalized module (none exists guest-side).
- **Evidence tier discipline** (only VERIFIED as existing) held across all four — zero proposals duplicate a VERIFIED complete capability (see §4.3).
- **Most distinctive proposals were written once:** variant navigator, jargon decoder, ratings, zero-result recovery, true-cost — these should be protected in prioritisation, not diluted by duplicated clusters.

---

## 11. Housekeeping

- **This document names every raw ID and its fate** — see §1 table (38 rows). No ID omitted.
- **Duplicate/overlap matrix** — see §2 (38×38 sparse matrix + 9-cluster summary). Layer vs duplicate adjudicated in §3.
- **Generic / unsupported / already-exists / UX-fix** — §4–5 with file:line evidence.
- **Missing gaps** — §7 (8 gaps), flagged not elaborated.
- **No new opportunities minted** beyond consolidation references (C1–C15 are merges, not new). New work should address M-01–M-08 via separate remediation/opportunity scoping.

---

*Cross-review authored from 4 specialist outputs + 4 evidence docs. All fate decisions are reversible with new live evidence (e.g., if checkout steps become VERIFIED or dimension fields are structured, dependencies clear). Next step: deduplicated prioritisation (RICE/impact-effort) on C1–C15 plus remediation backlog for ECS-06/07 and M-01–M-08.*
