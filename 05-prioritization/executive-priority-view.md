# Executive Priority View — At-a-Glance

> Concise table per priority. Problem | Why Now column traces to P0 blockers and HIGH value. Dependency column is hard gates only.

## P0 — CRITICAL (Must address — journey blockers / trust failures)

| Initiative | Type | Problem | Why Now | Dependency |
|---|---|---|---|---|
| **INV-01 Fix /undefined** | FIX | 11 See All dead-ends homepage+brand P0 `issue-register.md:7` | Blocks every browse path; LOW fix | None — hotfix |
| **INV-C02 PLP Browse Controls (chips/sort/facets)** | FIX | PLP cannot narrow: no chips, `Select Sort Option` placeholder `sortOptions:[]`, `Customer Review` empty, price slider+buckets compete `issue-register.md:20-25` | Journey B P0 cluster; LOW CSS/ARIA restore; unlocks filtering for guided selling | INV-01 |
| **INV-13 Delivery & Serviceability Estimator** | NEW | PDP gate `Enable your Location` hides fee/SLA `issue-register.md:27` PDP-02 P1 | Unblocks all 50k–1.5L; single table wires 7 initiatives | District→Zone/SLA table — foundation |
| **INV-C06 Cart Drawer & Feedback System** | FIX+NEW | `FEEDBACK-01 P1` no toast, `CART-01 P1` empty dead-end `Subtotal ৳0`, `CHECKOUT-01 P1` black box `issue-register.md:36-42` | Paywall surprise prevention; visibility of system status; medium drawer | INV-13/14 landed-cost feed |
| **INV-21 Authenticity Badging** | NEW | Post-Evaly #1 barrier; `Original Product Guaranteed` homepage-only `page-analysis.md:34` vs PDP generic | Reuses 13 brands — no backend; pairs with ratings; trust at price context | None |
| **INV-22 Browse Resumption (Recently Viewed + Continue)** | NEW | Journey F wholly unserved `personalization-current-state.md:9-10` DISC-02 P1 | Cheapest retention (localStorage), no backend stage1; reuses viewHistory | Event instrumentation only |
| **INV-26 Plural Payment Row (COD+bKash+Nagad+Card)** | NEW | PDP card-first excludes 75–90% COD `regional-commerce.md:65-74` Levree | HIGH 75–90% market; LOW row beneath EMI; district-aware truth from same table | INV-13 zone matrix |
| **INV-C04 (warranty half) Warranty Truth** | FIX | `Parts-0M / Motor-300M` implausible `product-page-variations.md:61` `issue-register.md:30` PDP-05 P2 | P0 content — normalise legend `Service/Parts/Compressor→5 years` | None |
| **INV-C03 Stage1 Intelligent Search** | NEW | `Search Here` placeholder generic `SEARCH-02 P3`, suggestions NOT FULLY VERIFIED `user-journeys.md` | Journey A fast-path; 150ms dropdown + Recent 6; verify empty is missing index not bug | Suggestion index |
| **INV-14 Static True Cost Row (part of True Cost)** | NEW | Sticker illusion; EMI inconsistent `product-page-variations.md:55` Haier 622L no EMI `issue-register.md:31` | Upfront+Delivery+Install+Energy→EMI/mo verdict; ineligibility `→ EMI Bank List`; offline 5–10d truth | INV-13 + INV-C04 + EMI master |

## P1 — HIGH PRIORITY (Strongly recommended)

| Initiative | Type | Problem | Why Now | Dependency |
|---|---|---|---|---|
| **INV-C01 IA Hygiene** | FIX | Flat PDP URLs `sitemap-analysis.md:27` 101 at root, `/tv-av` orphan, trailing-hyphen 4, Brand vs `/search?Brand` duplicate | Canonical fixes LOW now; hierarchical migration DEFERRED per decision-log | INV-01 |
| **INV-04 SEO Wall Re-layer** | IMPROVEMENT | IA-03 1,500-word guide pushes grid below fold `page-analysis.md:90-91` | Grid above fold; guide → below pagination + `30-sec guide` CTA; preserves SEO | INV-C02 |
| **INV-23 Smart Compare Workspace** | NEW | `/compare` 3× hand-typed `Model name or part…` `page-analysis.md:173-178` `issue-register.md:41` INTERACTION-01 P1 | Sticky→auto-populate + Highlight differences (decisive tint/verdict deferred) | INV-22 store + INV-13/14 feeds + Family Graph |
| **INV-24 Guided Selling (AC lens first)** | NEW | Life need→spec translation manual; SEO wall generic `issue-register.md:10,28` | AC fewest SKUs, `Choose Ton` proof, differentiator moat vs Daraz; rule table governed | INV-C04 glossary |
| **INV-C04 Jargon Decoder (full glossary)** | NEW | EER/R32/HQLED opaque `product-page-variations.md:57` | 8–10 terms tap-to-explain + `kWh×rate` Tk/mo; unlocks finders/cost literacy | Term bank |
| **INV-12 Rich Media (zoom)** | NEW | PDP-01 P1 `page-analysis.md:134-135` 68 images generic no video/zoom | Zoom/pinch + count + scrub P0-priority slice; video/dimension next | Asset pipeline; shares W×H×D |
| **INV-17 Variant & Family Navigator** | NEW | TV/Washer PDP no sibling switch despite Display Size facets `page-analysis.md:86` `issue-register.md:33` | Vault exploitation top 30 roots 70%; re-validates delivery/energy on switch | Family graph modeling |
| **INV-16 Gate1 Installation Checker** | NEW | No feasibility before ordering `product-page-variations.md:60` PDP-03 P1 | Per-SKU checklist + verdict `✓ Feasible`; priced `Add Installation` basket SKU | W×H×D + INV-13 |
| **INV-C05 Human Support Spine (WhatsApp deep-link)** | NEW | `Need help? Click Here` not conversational, footer hotline `page-analysis.md:14,18-19` | Sticky 16212 + `Share via WhatsApp` PDP deep-link (human reassurance Tk80k+); low | Store inventory INV-13 for Schedule Visit |
| **INV-32 Auth UX (split-field fix + guest toast)** | FIX | AUTH-01 P2 split two textboxes `page-analysis.md:192-195` + AUTH-02 guest inert `issue-register.md:40` | Single tel + toast `Saved for now — log in` + localStorage→account migration | INV-22 store |
| **INV-C03 Zero-Result Recovery** | NEW | SEARCH-03 P2 `FTLK↔FTKL` typo `ecommerce-capabilities.md:15` NOT TESTED | Short build: synonym table + Did-you-mean + `Remove Brand →12` + advisor CTA | Search index fuzzy |
| **INV-14 Interactive True Cost (slider)** | NEW | Sticker illusion deep solve | Phase2 of TRUE COST — tariff slider + bank picker after static row proves | INV-14 static |

## P2 — IMPORTANT (After foundations stable)

| Initiative | Type | Problem | Why Now | Dependency |
|---|---|---|---|---|
| **INV-06 Homepage Curated Prioritization** | IMPROVEMENT | `DISC-01 P1` 7+ grids overload `page-analysis.md:48-54` + affinity QUESTIONED `applicability-review.md:128-135` | Budget-only cull now; affinity reorder is P2 A/B experiment requiring modular CMS+scorer | CMS modularity audit |
| **INV-25 Bundles Pilot** | NEW | Thin Related `product-page-variations.md:65` FBT NOT OBSERVED | Curated pilot AC/TV/Fridge/Washer only; suppress low-ticket; family→attach mapping | Family Graph |
| **INV-28 OBD badge** | NEW | Doorstep anxiety 50k–1.5L COD 75–90% | Eligible badge by pincode; OTP protocol is P2 ops | INV-13 eligibility |
| **INV-33 Exchange & 14-Day (static badge)** | NEW | Exchange hub opaque `ecommerce-capabilities.md:52` NOT TESTED; Daraz Aug 2025 baseline shift | `14-Day Hassle-Free Return ✓` + `up to Tk12k → inspection → OTP` static | Valuation feed |
| **INV-20 Social Proof Pipeline (full)** | NEW | `ecommerce-capabilities.md:31-33` NOT OBSERVED + PDP-07 P1, `Customer Review` empty P2 | Needs post-delivery pilot proves n≥5 supply; collection/moderation/aggregation VERY HIGH | Review volume pilot |
| **INV-34 Accessibility (WCAG)** | FIX | ACCESS-01 icon-only `//` lacks label `accessibility-observations.md` | Incremental with each touchpoint; suppressed less as P0 hype | Continuous |

## P3 — FUTURE OPPORTUNITY (Requires validation/maturity/infrastructure)

| Initiative | Type | Problem | Why Now | Dependency |
|---|---|---|---|---|
| **INV-24 Fridge/TV/Washer finder lenses** | NEW | Founders valid but need rule table governance per lens | After AC lens proves pattern; validate litres→family etc. | Rule governance |
| **INV-12 Video/360/AR** | NEW | Functional video per template 15–25s muted | After zoom proven; asset reshoot per category | Asset production |

## PARKED (Not now)

| Initiative | Type | Reason Parked |
|---|---|---|
| **INV-C01 hierarchical PDP URL migration** | FIX | Very high engineering (101 PDPs 301), parked as IA Hygiene DEFER per decision-log — canonical/hyphen fixes ship now instead |
| **INV-06 Affinity Homepage Reorder** | NEW | Needs modular CMS + scorer + campaign-pin governance + A/B proof after rails; cheapest retention via INV-22 rail already 80% |
| **INV-16 Gate2 Bookable Slot** | NEW | Ops-gated — slot-capacity feed + order↔service linkage not confirmed `cross-review.md:175` |
| **INV-20 full Ratings pipeline at scale** | NEW | VERY HIGH until pilot proves supply — keep pilot scope only |
| **INV-24 Kitchen/Purifier finder lens (7 PDPs)** | NEW | Thin evidence 7 PDPs `sitemap-analysis.md:43` — fails governance threshold, removed per strategic critique |
| **INV-33 AI Diagnostics cross-category** | NEW | VERY HIGH — after static 14-day/badge + inspection truth proven |
| **INV-34 full WCAG audit** | FIX | Continuous, not parked but incremental |

## LATER / EXPERIMENT Horizons (sequencing logic, not dates)

- **NOW (P0/P0-adjacent):** INV-01, INV-C02, INV-13, INV-C06, INV-21, INV-26, INV-22, INV-C03 Stage1, INV-C04 warranty, INV-14 static row
- **NEXT (P1 high-value after foundations):** INV-C01 canonical, INV-04 re-layer, INV-23 compare, INV-24 AC finder, INV-C04 decoder, INV-12 zoom, INV-17 family chips, INV-16 Gate1 checker, INV-C05 WhatsApp deep-link, INV-32 auth fix, INV-C03 recovery
- **LATER (P2/LATER differentiators ops-gated):** INV-06 budget, INV-25 bundles pilot, INV-28 OBD protocol, INV-33 14-day→AI, INV-20 full pipeline, INV-24 additional lenses, INV-12 video→AR
- **EXPERIMENT (validate before invest):** INV-06 affinity reorder A/B `Rail only vs Rail+hero reweight` (requires modular CMS + scorer)
