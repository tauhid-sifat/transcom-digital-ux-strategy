# Phase 5 Summary — Prioritized UX Strategy Scope

> Decision-making phase consolidating 34 raw initiatives → 25 after dedup → 10 P0 + 11 P1 + 4 P2 + PARKED/LATER per unified scope `unified-ux-scope.md`. Evidence spans `01-current-state`, `02-ux-audit`, `03-opportunities`, `04-benchmark`.

## 1. Total Raw Findings from Previous Phases

| Source | Raw count | Reference |
|---|---|---|
| Phase 2 UX Issues | **32** (40 rows collapsed → 32 registered `02-ux-audit/issue-register.md:7-46` — P0 1 / P1 13 / P2 14 / P3 4) | 535 lines deep dives in `usability-issues.md` etc. |
| Phase 3 Opportunities | **15** consolidated OPP-01–15 `03-opportunities/opportunity-pool.md` (38→15 after cross-review dedup per `03-opportunities/duplicates-and-overlaps.md:6-19`, 6 duplicate clusters C1–C9) | 9 PER + 9 FEA + 9 EDS (layers) + 11 ECS (classified FOUNDATIONAL/ENHANCEMENT/DIFFERENTIATOR) → 8 NEW via benchmarking not counted here |
| Phase 4 New Opportunities | **8** NEW-01–08 `04-benchmark/new-opportunities.md:22-102` + `competitive-opportunity-map.md` 15+8 rows | Trust/OBD/plural payment/WhatsApp/hotline/cart drawer/14-day/phygital threshold |
| Phase 4 Benchmark Patterns | **33** raw patterns → 12 problem groups × 38 reusable variations `04-benchmark/pattern-library.md` (validated 8, enhanced 5, questioned 2 per `applicability-review.md`) | 21 platforms (Amazon.in/Flipkart/Daraz, Coolblue, Best Buy, AO, Currys, etc.) |

Raw findings are many-to-many; Phase 5 normalizes them.

## 2. Total Initiatives After Normalization

| Step | Count | File |
|---|---|---|
| Master Initiative Inventory (normalized, no priority) | **34** INVs (13 FIX / 6 IMPROVEMENT / 15 NEW CAPABILITY, 1 HYBRID) | `master-initiative-inventory.md:1-535` |
| After initiative-merging dedup | **25** INV-C* consolidated (6 merges 15→6 + 19 kept distinct) | `initiative-merging.md:15-23` |

## 3. Duplicates Merged

| Merge cluster | Raw members | Consolidated | Type | Source trace |
|---|---|---|---|---|
| INV-02+03+05 → INV-C01 | 3 | IA & Discoverability Hygiene | Exact duplicate (flat PDP + orphan + canonical) | `sitemap-analysis.md:27`, `issue-register.md:8-12,16`, `duplicates-and-overlaps.md:144` |
| INV-09+10+11 → INV-C02 | 3 | PLP Browse Controls | Same root PLP cannot narrow/sort | `issue-register.md:20-25`, `page-analysis.md:75-87` |
| INV-07+08 → INV-C03 | 2 → with ZERO-RESULT | Intelligent Search & Recovery | Parent/child pre/post-submit `pattern-library.md:96-104` | Search hygiene |
| INV-15+18 → INV-C04 | 2 | Spec Literacy & Warranty Truth | Exact warranty legend duplicate `product-page-variations.md:61` `master-initiative-inventory.md:259` | Spec decoder |
| INV-29+30 → INV-C05 | 2 | Human Support Spine | Different solutions same reassurance `page-analysis.md:14,18-19,199-204` 12C | Human trust |
| INV-27+31+19 → INV-C06 | 3 | Cart Drawer & Feedback | Overlapping FEEDBACK-01 `page-analysis.md:126-128,159-164` | Purchase confidence |

*Before → After: 34 → 25 (−9, 26.5%). FIX 13→8, IMPROVEMENT 6→2, NEW 15→14 (+1 HYBRID INV-C06). Parent/child wiring for C01/C02/C03/C04/C05/C06 plus sibling shared tables (Fulfillment Platform INV-13/14/26/28, Trust Stack C04/20/21, Resumption Store) kept distinct despite shared data per `applicability-review.md:158-169`.*

## 4. Initiatives Removed (Parked/Deleted Scope — Not Counted as Initiatives After)

| Category | Count | Detail |
|---|---|---|
| Lenses removed within initiative | **1 lens** | INV-24 Kitchen/Purifier Requirement Finder (7 PDPs `sitemap-analysis.md:43` thin `opportunity-pool.md:67` MED + `strategic-critique.md` REMOVE) |
| Tails removed | **2 tails** | PER-09 seasonal broadcast tail (generic `personalization.md:356` fails True Personalization test `cross-review.md:169`) + Populated Cart hygiene reclassification (ECS-06) + Filter/Sort feedback reclassification (ECS-07) — moved to remediation inside INV-C06/INV-C02 |
| Hierarchical PDP migration fully parked | **1 initiative slice** | INV-C01 hierarchical URL migration VERY HIGH → PARKED, while canonical/hyphen/tile fixes ship now `decision-log.md` |
| *Total fully removed would-be initiatives* | **~3** plus lens/tail slices | Documented in `not-now.md:44-68` |

## 5. Initiatives Deferred (Not Removed — P2/LATER/EXPERIMENT)

| Category | Count | Detail |
|---|---|---|
| P2 important (after foundations) | **4** | INV-06 Curated Prioritization (affinity reorder P2 A/B), INV-25 Bundles pilot, INV-28 OBD OTP protocol, INV-33 Exchange AI + full pipeline |
| LATER ops/content gated | **3** | INV-20 full Ratings pipeline (after post-delivery pilot proves supply `ecommerce-capabilities.md:31-33` zero), INV-24 Fridge/TV/Washer lenses after AC, INV-16 Gate2 bookable slot |
| EXPERIMENT (A/B gate) | **1** | INV-06 affinity homepage reorder `Rail only vs Rail+hero` requiring modular CMS+scorer |

## 6. P0 Initiatives — Critical (Must address) — 10 items

| P0 | Initiative | Type | Why P0 |
|---|---|---|---|
| P0 | INV-01 Fix /undefined | FIX | Browse dead-end P0 blocks every path `issue-register.md:7` LOW fix |
| P0 | INV-C02 PLP Browse Controls | FIX | No chips/sort `Select Sort Option` placeholder `sortOptions:[]` `issue-register.md:20-25` P1 cluster, LOW restore |
| P0 | INV-13 Delivery & Serviceability Estimator | NEW | Unblocks all Tk50k–1.5L; single table wires 7 |
| P0 | INV-C06 Cart Drawer & Feedback | FIX+NEW | FEEDBACK-01/CART-01/CHECKOUT-01 P1 cluster + landed-cost truth |
| P0 | INV-21 Authenticity Badging | NEW | Post-Evaly #1 trust `sitemap-analysis.md:26` 13 brands; no backend |
| P0 | INV-22 Browse Resumption | NEW | Journey F wholly unserved DISC-02 P1; cheapest retention localStorage |
| P0 | INV-26 Plural Payment Row | NEW | 75–90% COD+ bKash `regional-commerce.md:65-74` Levree; card-first excludes majority |
| P0 | INV-C04 warranty half | FIX | `Parts-0M / Motor-300M` P2 `product-page-variations.md:61` `issue-register.md:30` |
| P0 | INV-C03 Stage1 Search | NEW | Journey A fast-path `FTKL12TV16WD` `page-analysis.md:111` debounced + Recent 6 |
| P0 | INV-14 True Cost Static Row | NEW | Sticker→EMI/mo + verdict + offline 5–10d truth (Pickaboo/Daraz `regional-commerce.md:52-64`) |

*P0 is "critical journey blocker / serious trust / major conversion friction" per Step 7. All P0 are VERY HIGH value + LOW or essential HIGH complexity (INV-13).*

## 7. P1 Initiatives — High Priority — 11 items

INV-C01 IA Hygiene (canonical fixes), INV-04 SEO Re-layer, INV-23 Smart Compare (sticky→auto-populate), INV-24 AC Finder (P1 lens), INV-C04 decoder full glossary, INV-12 Rich Media zoom (P0 slice) + video pilot P1, INV-17 Variant Navigator, INV-16 Gate1 checker (content), INV-C05 WhatsApp deep-link + sticky hotline, INV-32 Auth UX split-field + guest toast, INV-C03 Zero-Result Recovery.

## 8. P2 Initiatives — Important — 4 items

INV-06 Homepage budget cull, INV-25 Bundles pilot AC/TV only, INV-33 14-day static badge, INV-34 Accessibility incremental (WCAG per touchpoint `accessibility-observations.md`).

## 9. P3 Initiatives — Future Opportunity — 2+ items

INV-24 Fridge/TV/Washer additional lenses, INV-12 Video/360/AR beyond zoom (per `executive-priority-view.md` P3 table).

## 10. Parked Initiatives — 7 items

INV-C01 hierarchical migration, INV-06 Affinity reorder (full), INV-16 Gate2 booking, INV-20 full pipeline at scale, INV-24 Kitchen/Purifier lens, INV-33 AI diagnostics, INV-34 full WCAG audit as sprint (continuous instead).

## 11. Key Foundational Initiatives (Enable ≥3 others — per dependency-map.md)

| Foundational | Enables | Why |
|---|---|---|
| **INV-01 /undefined fix** | All browse/discovery INV-04/22/23/24/INV-C02 | No path completes with broken See All |
| **INV-13 District→Zone/SLA + fee + install + store inventory table** | INV-14, INV-16, INV-26, INV-28, INV-C05, INV-C06, NEW-08 Fast filter (7 consumers) | Single table built once |
| **INV-C04 Glossary (8–10 terms) + Warranty Truth** | INV-14 True Cost EMI row, INV-24 Guided Selling verdict, INV-16 checklist | Literacy prerequisite |
| **INV-22 localStorage viewHistory+lastPlpUrl+compareQueue** | INV-23 Compare, INV-C03 Recent Searches, INV-32 auth migration | Same store `viewHistory/compareQueue/searchHistory` |
| **EMI Master (bank×tenure×threshold 5k/10k + form latency)** | INV-14, INV-23 total-cost pin, INV-26, INV-C06 | Finance truth table |
| **Family Graph (model_root → variants)** | INV-17, INV-23, INV-25, INV-10 re-validation | Top 30 roots 70% high-ticket |
| **W×H×D + ventilation gap normalisation** | INV-10 dimension overlay, INV-16 checker, INV-24 Fridge guard | One spec enrichment |

## 12. Major Dependencies

| Initiative | Depends On | Strength |
|---|---|---|
| INV-14 True Cost | INV-13 delivery table + INV-C04 glossary + EMI master | HARD |
| INV-16 Checker → Booking | INV-13 + INV-C04 + W×H×D + slot-capacity feed (VERY HIGH, parked Gate2) | HARD / VERY HIGH Gate2 |
| INV-23 Smart Compare | INV-22 store + INV-13/14 feeds + Family Graph | HARD store; SOFT feeds |
| INV-24 Guided Selling AC→Fridge/TV | INV-C04 glossary + rule tables per lens | HARD glossary |
| INV-06 Affinity Reorder | INV-22 rail + INV-C03 Recent + CMS modularity + scorer + A/B | HARD cms (deferred) |
| INV-20 Ratings full pipeline | Post-delivery pilot proving n≥5 supply `ecommerce-capabilities.md:31-33` zero | HIGH (deferred) |
| INV-22 resumption auth migration | INV-32 auth | SOFT auth |
| INV-06 budget subtraction | None beyond culled grids | None |

Critical path per `dependency-map.md:55-64`: **0–2 Foundations (INV-01 + INV-C02 + INV-C04 warranty + INV-22 + start INV-13 table) → 2–4 Trust Row (INV-13→INV-14 static+INV-26+INV-21+INV-C06 drawer+INV-C03 Stage1+INV-11 decoder) → Next (INV-04 re-layer, INV-23 compare, INV-24 AC finder, INV-12 zoom, INV-17 chips) → Later ops/content gated (Gate2 booking, AI diagnostics, bundle scale, review pipeline).**

## 13. Top Strategic Themes

| Theme | Constituent | Strategic lens |
|---|---|---|
| **1. Fulfillment Confidence at Decision Moment** | OPP-01 Estimator + INV-12 checker + OPP-09 True Cost ownership + NEW-02/03 + INV-13 table | Delivery + install + landed cost are one row not three pages; district/area text > GPS gate `page-analysis.md:125` PDP-02 P1; location permission is anti-pattern in BD `regional-commerce.md:77-86` |
| **2. Considered-Purchase Research (Guide, Explain, Verify)** | INV-24 Guided Selling + INV-C04 decoder + INV-C03 recovery | IA-03 SEO wall forces self-translation; Spec tab hides EER/panel data; typos for `FTKL…` codes dead-end — wizard+glossary turn taxonomy into assisted shopping |
| **3. Decision Memory & Resumption** | INV-22 Recently Viewed+Continue + INV-C03 Recent + INV-23 Compare persistence | DISC-02 Journey F unserved + SEARCH-01 Journey A no suggestions + INTERACTION-01 hand-type all attack same memory gap |
| **4. Confidence & Value Transparency** | INV-14 True Cost EMI + INV-C04 decoder + INV-10 Rich Media + INV-17 Variant Navigator + INV-20/21 trust-stack | PDP content-present but confidence-thin (PDP-01 zoom `page-analysis.md:134-135` 68 images generic, PDP-07 no reviews, PDP-08 no sibling, PDP-06 EMI silence) |
| **5. Attach & Lifecycle Monetization** | INV-25 bundles + INV-33 14-day/exchange + post-delivery retention | Thin Related single cross-sell `product-page-variations.md:65-66` FBT NOT OBSERVED `ecommerce-capabilities.md:56`; lifecycle turned on via consumable cadence |
| **6. Trust Mechanics (not branding)** | INV-21 authenticity + NEW-02 OBD OTP + NEW-07 14-day + INV-C05 hotline/WhatsApp + INV-26 plural payment | Post-Evaly BD trust = mechanics proof at handover, not homepage bar `page-analysis.md:34` `TRUST-01 P2` `applicability-review.md:175` |

## 14. Important Trade-offs (What Was Decided NOT to Do, and Why)

| Trade-off | Chosen | Not Chosen | Why |
|---|---|---|---|
| Homepage overload DISC-01 P1 `page-analysis.md:48-54` 7+ grids | Budget-only cull (subtraction) now | Full affinity reorder personalization `cross-review.md:168` BDT5k-like scorer | Reorder QUESTIONED `applicability-review.md:128-135` — needs modular CMS+scorer for unproven lift; cheaper INV-22 rail + Recent achieves 80% with localStorage |
| Installation | Gate1 checklist + priced basket SKU `Add Installation` (John Lewis £115) now | Gate2 bookable calendar slot immediately | Gate2 VERY HIGH `feasibility-dependencies.md` slot-capacity feed + order↔service linkage not confirmed `cross-review.md:175`; UI without feed is worse than no booking |
| True Cost EMI | Static `EMI from Tk/mo × bank/tenure + eligibility verdict + 5–10d truth` now | Full tariff slider + bank picker interactive on day one | Static row answers "can I afford monthly?" for 80% (tenure 3/6/12/24/36); slider adds HIGH complexity for marginal precision |
| Ratings Pipeline | PDP header badge + PLP card 4.6★(212) depends on pipeline | Full pipeline at scale now | VERY HIGH collection/moderation while current supply zero `ecommerce-capabilities.md:31-33` + empty `Customer Review` facet P2; pilot post-delivery SMS for 1 cat to prove n≥5 first |
| Search | Typeahead + Recent 6 + synonym table now | Full fuzzy/affinity personalized ranking | Fuzzy edit 1–2 + affinity scoring are HIGH/MEDIUM with marginal volume beyond typeahead+Recent; staged after INV-22 volume |
| PDP Media | Zoom/pinch + count + scrub now; video pilot 1 cat | 360°/AR for all categories now | Zoom is STANDARD hygiene; video/AR asset production scales by category; reuses Samsung/Haier reels not yet audited |

---
*Validated: 34 normalized → 25 consolidated (6 merges per `initiative-merging.md:15-23`, 19 kept distinct §5) → 10 P0 + 11 P1 + 4 P2 + PARKED/LATER per `unified-ux-scope.md` + `executive-priority-view.md` (NOW/NEXT/LATER/EXPERIMENT horizons, not dates; dependency strength HARD/SOFT per `dependency-map.md`). No UI/wireframes/tickets/hours estimated per brief. STOP AFTER PHASE 5 — Phase 6 will render final roadmap deliverable.*
