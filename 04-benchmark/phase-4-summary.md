# Phase 4 Summary — Benchmarking & Applicability Review

> 3 benchmark agents → 1 pattern library → 1 applicability review → opportunity map → new opportunities. All counts traceable per file:line.

## 1. Competitors / Platforms Researched

| Agent | Platforms / Hosts spot-checked (websearch) | Count |
|---|---|---|
| **A Global Commerce** | Amazon.in, Flipkart, Daraz BD, Best Buy, Coolblue, Apple, Dyson, Samsung, ASOS, John Lewis, Wayfair, Zalando | **12 distinct** |
| **B Electronics & Appliance** | Best Buy, RTINGS, LG, Currys, AO.com, Samsung/Mediamarkt, Home Depot, John Lewis, Energy Saving Trust/Citizens Advice/Selectra, Dyson | **11** |
| **C Regional & Contextual (BD/South Asia)** | Daraz BD, Pickaboo, Bikroy, Flipkart IN, ChalDal, Rokomari, Star Tech, Lever / India Post | **10 findings anchored to BD platforms** |
| **Deduplicated platform set** | Amazon (.in/.com), Flipkart, Daraz, Best Buy, Coolblue, Apple, Samsung, AO, Currys, LG, Home Depot, John Lewis, Wayfair, ASOS, Zalando, Star Tech, Pickaboo, Bikroy, ChalDal, Dyson, RTINGS | **21 unique platforms** |

Verification: `global-commerce.md:12 patterns [WS]`, `electronics-commerce.md:8 websearch passes`, `regional-commerce.md:7 HIGH applicability validated on BD hosts`.

---

## 2. Total Patterns Discovered

| Source | Raw patterns/findings | Variation count after extraction |
|---|---|---|
| Agent A Global Commerce | 12 patterns (Company/Journey/Pattern/How/Why/Lesson/Applicability) | — |
| Agent B Electronics Commerce | 11 patterns (Company/Category/Decision/How/Why/Application/Complexity) | — |
| Agent C Regional Commerce | 10 findings (Market Context/Problem/Why Relevant) | — |
| **Total raw benchmark patterns** | **33** (12+11+10) | — |
| Pattern Library (problem-centered) | 12 problem groups × 2–4 variations | **38 reusable pattern variations** |

Raw → library is many-to-many: e.g., Amazon pincode appears in both A and B; Daraz authenticity appears in C and pattern library Problem 6.

---

## 3. Industry Standard Patterns

| Pattern (library problem) | Maturity | Evidence (illustrative) | Relevance to Transcom |
|---|---|---|---|
| Pincode/District Serviceability Estimator (1A) | **STANDARD** (South Asia) / Daraz EMERGING BD Aug 2026 | Amazon.in/Flipkart 19k pincodes, Daraz Fast Delivery 50k SKUs, Best Buy ZIP, AO | Pincode-first landed cost — Tk50k–1.5L hygiene |
| Recently Viewed + Continue Shopping (8A/8B) | **STANDARD** | Amazon Pick up where you left off, eBay Watchlist, Zalando | Multi-session AC/TV research resumption |
| Persistent Compare Workspace (3A) | **STANDARD** | Coolblue up to 4, Best Buy Diffs, Samsung TV chart | Journey D hygiene |
| Rich Media Zoom/Scrub (4A) | **STANDARD** since ~2018 | Apple hover/dimension, Samsung 360° | PDP inspection anxiety |
| Autocomplete + Recent Searches (7A) | **STANDARD** | Amazon typeahead, Flipkart SKU-aware alphanum, ASOS/John Lewis recent | `FTKL12TV16WD` fast-path |
| Variant Family Chips (9A) | **STANDARD** since ~2018 | Apple Storage/Color, Samsung 43/55/65+delta | Family graph nav |
| Social Proof PLP+PDP badges + facets (6B) | **STANDARD** since ~2016 | Amazon Verified Purchase 2,184, Best Buy 4.6★ 212 | Tk80k+ trust |
| Cart Drawer + Stepper (12D) | **STANDARD** | Apple/ASOS/Best Buy | Landed-cost visibility |
| Authenticity / Mall badging (6A regional) | **STANDARD** BD marketplace | DarazMall guarantee+Mall, Pickaboo 100% genuine, Bikroy Verified | Post-Evaly trust |
| Plural Payment COD+bKash (12A regional) | **STANDARD** BD | Daraz/Pickaboo/ChalDal Levree 75–90% COD | No card-first checkout |
| Hotline-sticky support spine (12C regional) | **STANDARD** BD | Transcom 16212, Daraz 16492, ChalDal 16710 | Voice before cart |
| **Total STANDARD** | **11 pattern variations** | — |  |

---

## 4. Emerging Patterns

| Pattern | Maturity | Evidence | Why emerging (BD window) |
|---|---|---|---|
| True Cost & EMI Tenure Picker + Eligibility Verdict (5B) | **EMERGING** (combined row differentiator in BD) | Pickaboo EMI36 32 banks/BDT 5k + offline 7–10d form, Currys energy label, AO £/yr | Interactive planner emerging even in BD; offline form truth is BD-specific adaptation |
| Energy Label Translator kWh→Tk/mo (6C) | **EMERGING** BD | Energy Saving Trust A–G+QR, Citizens Advice 24.67p, AO translator | Literacy layer before regulation |
| Zero-Result Typo Recovery + Facet Relaxation count preview (7C) | **EMERGING** (facet-relax) | ASOS Did you mean + John Lewis `Remove Brand →12` | Fuzzy for alphanum codes `FTLK↔FTKL` |
| Cross-Category Doorstep Exchange + 14-day (8) | **EMERGING** BD | Daraz 14-day ALL 2025 + Flipkart 26-cat 10-step AI | Daraz Aug 2025 baseline shift |
| Open-Box + OTP (12B) | **STANDARD** India / **EMERGING** BD differentiator | Flipkart OBD + India Post OTP | Owned fleet vs marketplace moat |
| Complementary Bundles — Consumable Cadence (11C) | **EMERGING** electronics | Home Depot mandatory kits → MediaMarkt attach → purifier cadence | FBT in electronics not yet standard in BD |

*Standard globally can be Emerging in Bangladesh — therefore a competitive window (Daraz Fast Delivery Aug 2026 is STANDARD globally but was EMERGING in BD just months ago).*

---

## 5. Differentiators

| Differentiator | Why it differentiates vs Daraz/Pickaboo marketplace | Source |
|---|---|---|
| Guided Selling Wizard: Need→Filter→Verdict (Problem 2) | Daraz/Pickaboo cannot render brand-validated tonnage/litres rule tables + verdict chip at scale with P0 hygiene — requires catalog + rule governance (Coolblue-grade) | Global D + Electronics D |
| Installation Checker → Priced Basket SKU → Bookable Slot (Problem 10) | Marketplace cannot credibly prereq-check + slot-book per district with owned fleet; Transcom Store Locator `page-analysis.md:199-204` + trust bar `Free Installation` is owned-asset moat | Global D + Electronics (John Lewis £115, Coolblue Eigen Plan) + Regional NONE |
| True Cost row combined (Price+Delivery+Install+Energy→EMI/mo) with offline form truth | BD standard is EMI badge only; combined row is not same as global standalone energy label or standalone EMI calc | Emerging → Differentiator hybrid (OPP-09 cap) |
| Phygital Assisted/Threshold (Problem 12 wrapped as NEW-08) | Flipkart BuyZone 10k stores 5× growth (8× TV/appliances) + Daraz Choice Free on 3+ single-warehouse — requires store density + single warehouse Choice | Regional D + Global wiring |

*Only 3–4 differentiators called — per instruction not to call everything differentiator.*

---

## 6. Experimental Patterns

| Pattern | Why experimental for Transcom now | Source |
|---|---|---|
| Category-Affinity Homepage & PLP Prioritization (Returner Reorder) | Highest CMS dependency (modular CMS + scorer + A/B + campaign-pin governance); no P0/P1 global pattern validates full homepage rewrite; `electronics-commerce.md:236-241` sequencing explicitly says "Do not build… before P0 hygiene"; cheaper validated retention (OPP-02 rail + OPP-07 recent) gives 80% with localStorage only | Applicability REVIEWED as QUESTIONED OPP-15 |
| Seasonal Lifecycle Broadcast (PER-09 tail, removed) | Generic campaign segmentation with calendar + broad affinity, no behavioral trigger; fails True Personalization test `personalization.md:30-33`; no benchmark validates as personalization standard | Cross-review REMOVE; not counted here as experimental (counted as generic) |
| AR `View TV virtually` in room (subset of Rich Media) | Asset pipeline + device AR penetration uncertain in BD; no BD retail validates at scale | Pattern Library 4C |

*Experimental means unproven or premature without P0/P1 proof, not fanciful — requires A/B gate before commit.*

---

## 7. Phase 3 Opportunities Validated

**8 of 15 OPPs — VALIDATED** (multiple relevant platforms demonstrate same-category problem pattern, HIGH applicability, no reshaping required):

| OPP | Title | Evidence (illustrative) | Maturity |
|---|---|---|---|
| OPP-02 | Browse Resumption | Amazon/eBay/Zalando — Problem 8 | STANDARD |
| OPP-03 | Smart Compare Workspace | Coolblue/Best Buy/Samsung/RTINGS — Problem 3 | STANDARD |
| OPP-05 | Complete-the-Setup Bundles | Home Depot/AO/MediaMarkt — Problem 11 | EMERGING |
| OPP-07 | Intelligent Search Stage1 | Amazon/Flipkart/ASOS — Problem 7 | STANDARD |
| OPP-08 | Zero-Result Recovery | ASOS/John Lewis/Zalando — Problem 7 | STANDARD/EMERGING |
| OPP-10 | Rich Media Suite | Apple/Samsung/Dyson/Coolblue — Problem 4 | STANDARD |
| OPP-11 | Spec Jargon Decoder | Energy Saving Trust/Citizens Advice/AO — Problem 6 | EMERGING |
| OPP-13 | Variant & Family Navigator | Apple/Samsung/Sony — Problem 9 | STANDARD |

*All 8 are hygiene proven as Industry Standard before personalization — direct P0/P1 build candidates.*

---

## 8. Phase 3 Opportunities Enhanced

**5 of 15 OPPs — ENHANCED** (validated PLUS benchmarking revealed materially stronger implementation that should reshape scope):

| OPP | Title | Enhancement from Benchmarking | Source |
|---|---|---|---|
| OPP-01 | Delivery & Serviceability Estimator | District/area text > pincode alone (sparse BD pincodes, low GPS trust) + earned `Fast Delivery` PLP badge/filter alongside `EMI36` (1C) + install-fee truth shares table with OPP-09/12 | Global 1 + Regional 5 + Pattern Library 1 |
| OPP-04 | Guided Selling Framework | Wrapper fix for IA-03 (buying-guide at `/buying-guides/{cat}` + PLP CTA `30-sec guide`, SEO moves below pagination per Currys) + Fridge bag ladder `18L=1 bag` + 7-step measure guard (`W×H×D+gap+swing`) that also feeds OPP-10/12 | Electronics 2/3/4 + Global 2 + Pattern Library 2 |
| OPP-09 | True Cost & EMI Planner | BD offline form truth Pickaboo/Daraz disclosed (blocked amount → signed form 3d → bank converts 5–10d) + combined `Upfront+Delivery+Install+Energy→EMI/mo` single row + BDT 5k threshold suppress + ineligibility verdict | Regional 3 + Pattern Library 5 |
| OPP-12 | Installation Feasibility & Slot Booking | Gate1 checker content → priced basket SKU `Add Installation + Recycling` (£115 model John Lewis) + `Before You Buy/Before We Deliver` checklist video (10A); Gate2 booking ops-gated, order↔service link | Global 11 + Pattern Library 10 |
| OPP-14 | Social Proof | Ratings pipeline + PDP header + PLP badges must be paired with Authenticity proof (NEW-01 `DarazMall`) — Verified Purchase alone insufficient post-Evaly; `Mall/Flagship + Authenticity Guarantee + warranty sheet` is the companion | Global 9 + Regional 1 + Pattern Library 6 |

---

## 9. Phase 3 Opportunities Questioned

**2 of 15 OPPs — QUESTIONED** (limited relevance / sequence risk now, not invalid):

| OPP | Title | Why Questioned | Conditional Next Step |
|---|---|---|---|
| OPP-06 | Price-Drop & Back-in-Stock Notifications (Wishlist Intelligence) | Pipeline-heavy (auth-gated wishlist persistence + price history + stock ETA feed + consent + messaging templating) with auth friction (`AUTH-01 P2` split-field OTP `issue-register.md:39`, phone-only `01-current-state/ecommerce-capabilities.md:57-58`, guest wishlist inert `issue-register.md:40`) + **zero dedicated benchmark pattern** in 33 (vs EMI/delivery/ratings validated). Regional demand capture via *14-day return + exchange + EMI row* captures dormant demand at decision moment with higher immediate ROI. | **Defer to P2** after Wishlist persistence + PDP-07 social proof + OPP-02 resumption prove auth value; if built, explicit ETA `Restocking 2–3 weeks — or show in-stock alternatives` + on-site + email/SMS |
| OPP-15 | Category-Affinity Homepage & PLP Prioritization (Returner Reorder) | No P0/P1 global/electronics pattern validates full homepage reorder as hygiene; benchmark sequencing `electronics-commerce.md:236-241` "Do not build… before P0 hygiene" + `cross-review.md:234-243` M-gaps (NAV-01 P0 `/undefined` `issue-register.md:7`, IA-01 flat URLs, FILTER-01/SORT-01) remain unremediated; highest CMS dependency (modular CMS + scorer + A/B + campaign governance) with `DISC-01 P1` homepage already overloaded `page-analysis.md:48-54` + `MOBILE-01 P2`; today's returner problem (Journey F wholly unserved) is cheaper-solved by OPP-02 rail + continue deep-link + OPP-07 recent searches with `localStorage` only (validated STANDARD 8/12). | **Defer to P2 experiment:** ship OPP-02/07 first → A/B `Rail only` vs `Rail + hero reweight`; require proof before committing affinity scorer; ship PLP-internal affinity chips (`Your size: 55"`) earlier as low-cost tweak |

*Neither is NOT VALIDATED — both have behavioral logic, but benchmarking flags sequencing risk: building them before P0/P1 proven wastes the cheapest retention (localStorage) and the hardest pipeline (auth wishlist) on unproven lift.*

---

## 10. New Opportunities Discovered (Not in Phase 3 Pool)

**8 distinct NEW opportunities** elevated from 33 patterns + 8 missing gaps M-01–M-08 (`cross-review.md:234-243`), each absent from 15 OPPs or remediated tails:

| NEW | Title | Pattern Type | Applicability | Why Distinct |
|---|---|---|---|---|
| NEW-01 | Authenticity / Authorized-Retailer Badging at Price Context | **STANDARD** BD marketplace | **HIGH** | Post-Evaly #1 barrier; reuses 13 brand authorizations (`sitemap-analysis.md:26`) as moat vs Daraz variance; not same as ratings (OPP-14 needs this companion) |
| NEW-02 | Open-Box Delivery + OTP Doorstep Verification | **STANDARD** India / **EMERGING** BD | **HIGH** 50k–1.5L | Owned fleet vs pure marketplace moat; eligible badge by pincode |
| NEW-03 | Plural Payment Row (COD+bKash/Nagad+Card-on-Delivery+Online/EMI) | **STANDARD** BD | **HIGH** | 75–90% COD (`Levree` `regional-commerce.md:65-74`); PDP was card-first, excludes majority; district-aware COD truth |
| NEW-04 | WhatsApp/Messenger Human Agent + Share | **STANDARD** social layer / **EMERGING** human manager | **HIGH** | Human trust for Tk80k+; Facebook Commerce thousands BD sellers exclusively FB; collective purchase |
| NEW-05 | Hotline-Sticky Support Spine + Schedule Store Visit | **STANDARD** BD hygiene | **HIGH** | Voice before cart for AC/Fridge/Washer; Mapbox Store Locator `page-analysis.md:199-204` wire, not rebuild |
| NEW-06 | Cart Drawer + Checkout Transparency (Mini-Cart, Landed-Cost Breakdown, Stepper & Toast) | **STANDARD** | **HIGH** | Elevates M-01 remediation (CHECKOUT-01 P1 `issue-register.md:38`) to build unit — highest ROI for paywall surprise; low backend, fixes FEEDBACK-01/CART-01/CHECKOUT-01 |
| NEW-07 | 14-Day Hassle-Free Return Badge + Cross-Category Doorstep Exchange with AI Diagnostics | **EMERGING** BD (Daraz Aug 2025 ALL) | **MEDIUM** | Exchange hub `/exchange` existing but opaque `ecommerce-capabilities.md:52`; AI diagnostics lowers inspection cost; idle household currency |
| NEW-08 | Assisted/Phygital Store Linkage + Threshold Bundling (Free on 3+) | **DIFFERENTIATOR** electronics / **EMERGING** threshold | **MEDIUM** | Flipkart BuyZone 5× + Daraz Choice single-warehouse; phygital linkage + deal threshold converts Tier-2/3 low self-serve confidence |

All 8 are **HIGH** except two MEDIUM (N=14-day ops feed + phygital network co-growth). Validation column in `new-opportunities.md` shows BD platform evidence per row.

---

## 11. Most Relevant Competitive Insights (What Changes Scope)

1. **Trust is mechanics, not branding.** Homepage bar (`page-analysis.md:34` `Free Installation / Original / Exchange / Secure`) is not surfacing as mechanics at PDP/Cart price context. Bangladesh trust after Evaly = `Authenticity badging (NEW-01) + Open-Box OTP (NEW-02) + 14-day return (NEW-07) + Hotline/WhatsApp human (NEW-04/05) + Plural payment (NEW-03)` — each alone is hygiene, together they are the trust row. OPP-14 stays but **needs NEW-01 companion**; otherwise ratings alone cannot carry Tk80k+.
2. **Financing + delivery + install are one decision row, not three pages.** OPP-09 ENHANCED with Pickaboo/Daraz offline form truth (blocked → signed form 3d → bank converts 5–10d) + PDP-02 pincode text > GPS gate + district-aware COD truth (NEW-03) is the Bangladesh affordability unit: `Upfront + Delivery + Install + Energy → EMI/mo` with ineligibility verdict. Building any one without the other wastes motion (shared EMI/district tables, single wiring table `pattern-library.md:159-168`).
3. **Location permission is the anti-pattern.** `Enable your Location` gate (`page-analysis.md:125`, `issue-register.md:27` PDP-02 P1) fails versus district/area text — that single swap unlocks OPP-01, NEW-03 and NEW-02 eligibility badge with one data change.
4. **Guided selling is the moat vs Daraz/Pickaboo.** Rule tables (LG 20 BTU/sq ft, AO 18L=1 bag, 7-step measure guard) + family graph + verdict chip (Coolblue-grade wizard) is the only pattern pure marketplace cannot credibly copy with governance. Keep AC→Fridge→TV ordering; suppress Kitchen/Purifier until evidence thickens.
5. **Do not build affinity homepage before P0.** Cheaper validated retention (OPP-02 `localStorage` rail + continue deep-link + OPP-07 Recent Searches) delivers 80% of returner value with no scorer/CMS work. OPP-15 is a **P2 experiment** requiring modular CMS + scorer + campaign-pin governance + A/B proof after `NAV-01 /undefined` P0, IA flat-URL/SEO remediation, and hygiene P0 (OPP-01/07/09 row) proven.
6. **Every standard reveals a suppression rule.** EMI, install, FBT, energy-row, and even `Customer Review` facet must be suppressed for low-ticket (trimmer/mixer `Tk3k` `product-page-variations.md:104`) where attach/install is generic and BDT 5k threshold (`regional-commerce.md:52-64` Pickaboo `EMB:5k` / Daraz `EMI:10k`) would misfire.
7. **Thriving platforms add human where automatable trust thins.** ChalDal Premium Care dedicated agent 24h / Facebook Commerce thousands exclusively FB (WOM + social β=0.13, BJMS 2025 `regional-commerce.md:101-110`) + hotline-first 16710 — same logic applies to Tk600L/65": human WhatsApp deep-link + OBD photograph + hotline-sticky is cheaper than product returns.
8. **Speed pattern: Pincode text swallows three tables.** One district→Zone/SLA + delivery fee + install fee + store inventory table wires OPP-01, OPP-09 (energy/EMI row), OPP-10 dimension, NEW-01/02/03/05/08 Fast filter + single-warehouse. Build that table once before touching CMS reorder.

---

## Artefact Map

| File | Patterns / IDs | Role |
|---|---|---|
| `agents/global-commerce.md` | 12 patterns (Company/Journey/Pattern/How/Why/Lesson/Applicability + STANDARD/EMERGING/DIFFERENTIATOR) | Broad e-commerce mechanics |
| `agents/electronics-commerce.md` | 11 patterns (Company/Category/Decision/How/Why/Application/Complexity) | High-consideration complexity reduction |
| `agents/regional-commerce.md` | 10 findings (Market Context/Problem/Why Relevant) | BD trust/COD/EMI/delivery/human adaptations |
| `pattern-library.md` | 12 problem groups × 2–4 variations = 38 reusable variations | Problem-centered reuse, not competitor dump |
| `applicability-review.md` | 15 OPPs classed ENHANCED(5) / VALIDATED(8) / QUESTIONED(2) + 8 NEW + wiring + sequencing P0→P2 | Validation vs fame, BD-context |
| `competitive-opportunity-map.md` | Mapping OPP-01–15+NEW-01–08 × Pattern Type × Applicability × Recommendation | Market-informed build decisions |
| `new-opportunities.md` | 8 NEW (HIGH 6, MEDIUM 2) with evidence + value + complexity | Net-new from benchmarking, not re-proposed Phase 2 fixes |
| `phase-4-summary.md` | This file — 11 metrics + 8 most relevant insights | Roll-up before Phase 5 scope consolidation |

---
*Phase 4 produced 33 raw benchmark patterns → 12 problem-centered groups (38 variations) → 15 OPPs validated/enhanced/questioned (8/5/2) → 8 NEW opportunities. Maturity mix: STANDARD 11, EMERGING 6, DIFFERENTIATOR 4, EXPERIMENTAL 1. Missing gaps M-01–M-08 `cross-review.md:234-243` that remain are architecture/remediation (IA-03 SEO wall, IA-01 flat URLs, NAV-01 undefined, FILTER-01/SORT-01) — not counted as benchmark NEW because they are P1 fixes, not opportunities. Next: Phase 5 consolidates 32 Phase 2 issues + 15 Phase 3 opportunities + 8 NEW + 12 pattern-library problems into one scope + prioritization framework.*

---
*Generated 2026-09-03. Evidence traceable per `file:line` above to `00-input`, `01-current-state`, `02-ux-audit`, `03-opportunities`, `04-benchmark/agents`, `04-benchmark/pattern-library.md`.*
