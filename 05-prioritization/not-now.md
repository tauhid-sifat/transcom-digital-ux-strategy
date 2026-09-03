# Not Now — Deferred, Parked & Removed Initiatives

> Strategic "what NOT to do" is as important as what to build. Each entry explains decision, why not now, and conditions that would trigger reconsideration.

## Parked — Too Complex for Current Maturity / Needs Validation

| Idea | Source | Decision | Why Not Now | Conditions for Reconsideration |
|---|---|---|---|---|
| **Hierarchical PDP URL migration** (`/refrigerators/no-frost/side-by-side/ro...` replacing flat `/{brand}-{product}` ) | INV-C01 IA-01 `sitemap-analysis.md:27` 101 PDPs flat P1 `issue-register.md:8` | **PARKED** | Very high engineering (301 map 101 PDPs, SEO risk, internal links, sitemap `00-input/sitemap-analysis.md:131` trailing-hyphen cleanup entangled). Low-cost canonical + hyphen + orphan fixes deliver 80% with LOW effort. | Reconsider when canonical fixes proven + SEO crawl shows flat→hierarchical uplift hypothesis validated via 10-URL pilot + 301 log clean. |
| **Category-Affinity Homepage & PLP Prioritization (full returner reorder)** | INV-06 / PER-05 `applicability-review.md:128-135` QUESTIONED `issue-register.md:13` DISC-01 P1 | **PARKED — P2 experiment only** | Requires modular CMS + affinity scorer + A/B + campaign-pin governance; no global/electronics pattern validates full homepage rewrite before P0 hygiene. Cheaper INV-22 Recently Viewed rail + INV-C03 Recent Searches (localStorage only) achieve 80% returner value. | Ship INV-22/INV-C03 first; when returner conversion with rail proven, run A/B `Rail only vs Rail+hero reweight` with modular CMS audit passing. |
| **Install Booking Gate2 — Bookable Calendar Slot (ops-gated)** | INV-16 Gate2 FEA-06 `cross-review.md:175` | **PARKED — Gate1 ships now** | Gate2 needs slot-capacity feed per district/installer + order↔service linkage + reschedule via `Track Your Service` `page-analysis.md:7`; ops feed not yet confirmed; building UI without feed is worse than no booking. | Ops confirms slot inventory feed + capacity by district; Gate1 checker proves demand (feasibility pass rate). |
| **Full Ratings pipeline at scale** | INV-20 `applicability-review.md` + `ecommerce-capabilities.md:31-33` NOT OBSERVED | **DEFERRED to piloted scope** | VERY HIGH (collection/moderation/aggregation) while current review supply is zero `personalization-current-state.md:12-14` NOT OBSERVED; badge wiring without pipeline would be fake counts. | Pilot post-delivery SMS for 1 cat (AC/TV) proves n≥5 supply consistently; then extend. |
| **Rich Media 360°/AR (beyond zoom)** | INV-12 `applicability-review.md` | **PARKED beyond zoom** | Asset pipeline for 360°/AR not yet structured; zoom/pinch + count delivers highest anxiety reduction per effort for P0. | After zoom proven + dimension overlay from structured spec (W×H×D) + brand 360 assets validated for top 10 SKUs per cat. |

## Removed — Different Solution Better / Overlap

| Idea | Source | Decision | Why Not Now | Conditions |
|---|---|---|---|---|
| **Kitchen & Purifier Requirement Finder lens (wattage→task, TDS→filter)** | EDS-09 `sitemap-analysis.md:43` 7 PDPs Purifier / Kitchen long-tail `opportunity-pool.md:67` MED | **REMOVED** (within INV-24) | Thin evidence 7 PDPs vs fridge/AC/TV high-ticket 8–12 each; thin ticket attach generic per `duplicates-and-overlaps.md:168` suppress rule. Guided Selling AC/Fridge/TV/Washer lenses keep differentiator; kitchen lens dilutes governance. | Reconsider when purifier catalog ≥20 PDPs with validated TDS/wattage rule tables and `W×H×D` enrichment passes. |
| **Price-Drop & Back-in-Stock as N=3 pipelines — Seasonal broadcast tail** | PER-09 tail `personalization.md:356` `cross-review.md:169` | **REMOVED tail only** — head (wishlist price/stock with ETA) kept as INV-33 P2 | Seasonal "Prepare for summer: Inverter ACs in your viewed range" is campaign segmentation (calendar + broad affinity), no behavioral trigger, fails True Personalization test `personalization.md:30-33`; no benchmark validates as personalization standard. | Campaign team can schedule without product capability; revisit as `NEW CAPABILITY` only with signal-driven price/stock history feed, not calendar. |
| **Populated Cart quantity/coupon as standalone opportunity** | ECS-06 `duplicates-and-overlaps.md:144` `ecommerce-capabilities.md:39-42` NOT TESTED populated | **REMOVED as opportunity — reclassified as hygiene fix** | Empty shell VERIFIED; quantity stepper/coupon/breakdown are baseline cart hygiene per `cross-review.md:201-208` (string/ARIA restoration = fix). Cross-sell part belongs to INV-25 bundles (C5). | Track as remediation inside INV-C06 Cart Drawer, not separate opportunity. |
| **Active Filter/Sort Feedback as standalone opportunity** | ECS-07 `issue-register.md:20-25` | **REMOVED — remediation** | Filter/sort shells VERIFIED `ecommerce-capabilities.md:16-22`; gap is missing chip row + empty `sortOptions: []` — restoring expected PLP feedback is fix, not differentiator. | Track as P0 fix inside INV-C02. |

## Deferred — High Value but Gated by Dependency Proof

| Idea | Source | Decision | Why Not Now | Conditions |
|---|---|---|---|---|
| **Fridge/TV/Washer Finder lenses (litres→family + guard, distance→size)** | INV-24 P2 | **DEFERRED after AC lens** | AC lens fewest SKUs + `Choose Ton` proof validates pattern; fridge bag ladder + 7-step measure guard + TV distance need W×H×D enrichment not yet proven at scale `value-analysis.md`. | AC finder ships; next lenses ship when rule tables governed + `W×H×D+gap+swing` normalisation sampled 10 PDPs passes. |
| **Open-Box OTP Doorstep Verification (full protocol)** | INV-28 / NEW-02 `regional-commerce.md:41-50` | **P2** | Badge eligibility by pincode LOW ships now; full rider OTP+photo log HIGH and ops-gated (Wishmaster fleet protocol, COD 75–90% `Levree`). | INV-13 zone truth proven + fleet protocol confirms photo/log overhead vs dispute ROI. |
| **Complete-the-Setup Bundles full catalog** | INV-25 | **P2 pilot only** | Curated attach for AC/TV/Fridge/Washer/purifier valid; expanding to low-ticket (trimmer) dilutes per `cross-review.md:168` BDT5k threshold. | Curated pilot demonstrates attach rule table; expand after Family Graph `model_root` covers top 30 roots 70% `page-analysis.md:86`. |
| **Cross-Category AI Diagnostics (Exchange)** | INV-33 `regional-commerce.md:113-122` Flipkart ReCommerce 26 cats 10-step AI | **LATER** | VERY HIGH — after static 14-day badge + `up to Tk12k → inspection → OTP` truth proves demand vs ops cost. | Static `up to` valuation proves trade-in intent; AI diagnostics feasible per ops. |

## Low Value / Narrow Reach — Intentionally P2/Continuous

| Idea | Source | Decision | Why Not Now | Conditions |
|---|---|---|---|---|
| **Full WCAG audit as sprint** | INV-34 `accessibility-observations.md` | **P2 continuous, not sprint** | Value analysis rates LOW on reach (narrowest) but morality HIGH; feasibility LOW means ships incrementally with each touchpoint fix (icon labels `//` `page-analysis.md:129`, focus order per `accessibility-observations.md:32-40`) rather than blocking P0. | Ship with every P0/P1 initiative: `aria-label`, focus, colour contrast audit (`WCAG AA`) per component, not as separate P0. |

## Blocked Traction Traps — Solved by Simpler UX Change

| Idea | Simpler Fix Chosen | Why Simpler Wins |
|---|---|---|
| Dose search need fuzzy + affinity + recent all at once? | Ship typeahead + Recent 6 (INV-C03 Stage1) before fuzzy/affinity `decision-log.md` | 150ms debounced + Recent covers `FTKL…` exact-code job; fuzzy edit 1–2 adds 60% complexity for incremental zero-result volume (MEDIUM applicability `applicability-review.md:88-92`). |
| Does EMI need full slider on day one? | Static `EMI from Tk/mo × bank/tenure + eligibility verdict + 5–10d truth` ships; slider deferred `decision-log.md` | Static row answers "can I afford monthly?" for 80% (tenure picker 3/6/12/24/36 suffices); tariff slider adds HIGH complexity for marginal precision. |
| Does PDP need second Add To Cart button removed as initiative? | Duplicate `Add To Cart` handled as visual hygiene inside INV-C06 drawer + INV-12 media scrub `decision-log.md` | No separate initiative — redundant button is visual noise, fixed by drawer/sticky bar. |

---
*Every "Not Now" is traceable to `value-analysis.md` (reach/value), `feasibility-dependencies.md` (VERY HIGH / ops feed gates), and `strategic-critique.md` approvals/simplifications/deferrals. Conditions above are measurable exits, not vague "later".*
