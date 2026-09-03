# Feasibility & Dependencies — Phase 5 Step 4

> **Phase:** 5 Step 4 — Feasibility & Dependency Analysis  
> **Date:** 2026-09-03  
> **Status:** Step 4 Complete — complexity & dependency map for sequencing (Step 5)  
> **Input:** `05-prioritization/master-initiative-inventory.md` (34 INVs) → `05-prioritization/initiative-merging.md` (25 consolidated)  
> **Evidence base:** `00-input/sitemap-analysis.md` · `01-current-state/site-inventory.md:1-121` · `01-current-state/page-analysis.md:1-248` · `01-current-state/product-page-variations.md:49-61` · `01-current-state/ecommerce-capabilities.md:12-62` · `01-current-state/personalization-current-state.md:9-13` · `02-ux-audit/issue-register.md:7-46` · `03-opportunities/opportunity-pool.md:7-244` (OPP-01..15 complexity hints) · `03-opportunities/cross-review.md:32-243` · `04-benchmark/pattern-library.md:22-164` (Problems 1–12, STANDARD/EMERGING/DIFFERENTIATOR) · `04-benchmark/applicability-review.md:22-192` (VALIDATED/ENHANCED/QUESTIONED + wiring `:158-169` + sequencing `:182-191`)

**Method:** Relative implementation complexity only — no engineering-hour estimates. Dimensions scored qualitatively: **UI complexity** (templates/components, responsive, states), **Data** (new table/CMS/graph/feed), **Backend** (service/index/pipeline/auth), **Third-party** (gateway/carrier/store platform), **Personalization** (event store, scorer, migration), **Content** (authoring/governance, asset production), **Operational** (ops capacity, agent roster, fleet/process). Classification is comparative across the 25, not absolute.

---

## Classification Key

| Level | Meaning | Typical profile |
|-------|---------|-----------------|
| **LOW** | Single-template fix or content/config change. No new pipeline, no ops dependency, 1 squad, ships in days–2 weeks of focused work. | Hydration guard, copy legend, chip row, badge lockup, aria labels, text input swap |
| **MEDIUM** | New component with bounded data (rule table, localStorage, or asset pipeline reuse). 1–2 surfaces, limited backend, content authoring required. | Finder lens, drawer/stepper reusing fee table, localStorage rail, accessory affinity row, WhatsApp deep-link + store wiring |
| **HIGH** | Multi-surface system with shared data table or catalog modeling. Requires feed build + multi-template wiring + moderation or normalization; cross-squad coordination. | Zone/SLA estimator, EMI planner with bank matrix, family graph, compare workspace, guided-selling framework (5 lenses), media pipeline with dimension overlay |
| **VERY HIGH** | Pipeline-heavy and/or ops-gated. Moderation + aggregation + feed generation + auth migration or fleet/rider process change; failure mode is worse than not shipping. | Ratings pipeline with verified-purchase + facet indexing, AI diagnostics exchange with cross-category valuation, slot-booking calendar with order↔service linkage |

> Content-only ≠ automatically LOW: 25–40 term glossary is LOW; 5-lens rule governance validated against brand sheets is HIGH. Ops-gated gates are flagged separately.

---

## Summary Table — All 25 Consolidated Initiatives

| # | Final ID | Initiative Name | Type | Complexity | One-line rationale | Key dependency / shared table |
|---|----------|-----------------|------|------------|--------------------|-------------------------------|
| 1 | **INV-01** | Repair Broken Browse Paths (`/undefined` See All) | FIX | **LOW** | Hydration slug-builder guard + CI link integrity; zero new data. `master-initiative-inventory.md:82-89` · `page-analysis.md:56-57` | Slug builder; sitemap route table |
| 2 | **INV-C01** | IA & Discoverability Hygiene — Flat PDP, Orphan `/tv-av`, Trailing-Hyphen, Canonical & Tile Alignment | FIX | **LOW** | Sitemap/redirect/canonical config + 1 orphan page; no personalization/backend. `sitemap-analysis.md:27,74-77,132` | Redirect table (301 without hyphen); canonical strategy; tile→taxonomy map |
| 3 | **INV-04** | SEO Architecture — Move Buying-Guide Wall Below Fold, Buying-Guide Hub | FIX | **LOW** | Template re-layer (grid above fold, 1,500-word block below pagination) + `/buying-guides/{category}` hub; preserves equity. `page-analysis.md:90-91` | CMS hub + INV-24 finder CTAs |
| 4 | **INV-C02** | PLP Browse Controls Hygiene — Chips, Sort, Pagination, Facet Repair | FIX | **LOW** | Persistent chip row + `Showing 1–12 of N` + single price control + `Screen→Display Size` merge; suppress empty Review until n≥5. `page-analysis.md:75-86` | Facet taxonomy audit; suppress rule shared with INV-20 |
| 5 | **INV-06** | Homepage Prioritization & Performance Budget | IMPROVEMENT | **MEDIUM** | Cut 7+ grids/68 images `page-analysis.md:48-54` + `product-page-variations.md:49` + lazy-load + budgeted carousel count; A/B cut vs add. `opportunity-pool.md:233-244` | Image CDN/lazy-load; homepage CMS triage |
| 6 | **INV-C03** | Intelligent Search & Recovery — Autocomplete + Recent + Recovery | NEW (gated) | **HIGH** | Debounced typeahead (150–200 ms, SKU-boost) + recent chips (6) + scented placeholder + fuzzy edit 1–2/QWERTY/Bangla + facet-relax. `pattern-library.md:99-103` Prob 7 | Suggestion index (title/SKU/brand/category) + synonym table; zero-result template; `localStorage searchHistory` (shares INV-22 store) |
| 7 | **INV-12** | Rich Media Inspection — Zoom, Pinch, Video, 360°, Dimension Overlay & AR | IMPROVEMENT | **HIGH** *(phased: MEDIUM → HIGH)* | Gate1 zoom/pinch+scrub (week, no reshoot) = MEDIUM; Gate2 functional video 15–25 s per template + 360°/dimension/AR = HIGH (asset pipeline). `pattern-library.md:60-67` Prob 4 | Brand reels + `W×H×D+gap+swing` dimension normalization (shares INV-16/24) |
| 8 | **INV-13** | Delivery & Serviceability Estimator — Pincode-First Landed Cost + Fast Badge | NEW | **HIGH** | District/area text → serviceability + SLA + fee + install flag + nearest store-pickup distance; persists session → Cart truth. `opportunity-pool.md:7-20` Cluster C1 · `applicability-review.md:46-49` ENHANCED | District→Zone/SLA + delivery fee + install fee + store inventory table (shared: INV-14/16/26/28/C05/C06) |
| 9 | **INV-14** | True Cost & EMI Planner — Ownership Row + Tenure Picker + Eligibility Verdict | NEW | **HIGH** | Ownership row `Upfront+Delivery+Energy→EMI/mo` + 3/6/12/24/36 picker + tariff/hours slider (`kWh×rate` `pattern-library.md:90-92`) + BDT 5k threshold + offline 7–10 d form latency. `applicability-review.md:94-98` ENHANCED | EMI bank/tenure master (32 banks) + tariff table + EER per SKU + install fee table (shares INV-13) |
| 10 | **INV-C04** | Spec Literacy & Warranty Truth — Jargon Decoder + Energy Translator + Warranty Legend | FIX | **LOW** | Tap-any-term drawer 25–40 terms + `Special Component = Compressor/Panel/Motor` legend + energy A–G; content-only. `product-page-variations.md:57-61` | Glossary CMS + tariff formula (feeds INV-14/24); warranty mapping table |
| 11 | **INV-16** | Installation Feasibility Checker — Pass/Fail Verdict + Priced Basket (Gate2 Slot Booking ops-gated) | NEW | **MEDIUM** *(Gate1)* → **VERY HIGH** *(Gate2 Booking)* | Gate1 content toggles per appliance (AC wall/bracket/drain) + fee `Free/Paid Tk X` = MEDIUM; Gate2 calendar + order↔service linkage + reschedule = VERY HIGH ops-gated. `pattern-library.md:132-137` | Install checklist per SKU; `W×H×D+gap+swing` (shares INV-12); slot-capacity feed (gating) |
| 12 | **INV-17** | Variant & Family Navigator — Sibling Chips with Delta & Stock | NEW | **HIGH** | Family graph `model_root→variants` (tonnage/litres/display size/kg) + price delta + stock badge `65" +Tk18k In stock`. `applicability-review.md:118-122` | Family graph (top 30 roots ≈70% high-ticket `sitemap-analysis.md:44`) + live price/stock feed |
| 13 | **INV-20** | Social Proof Pipeline — Ratings, Review Count, Badges, Customer Review Facet, Q&A | NEW | **VERY HIGH** | Collection→moderation→aggregation (suppress n<5)→ PDP header badge + PLP `4.6★ (212)` + facet `★★★★&up (41)` + verified-purchase + Q&A. `pattern-library.md:87-90` | Review submission/moderation/aggregation service + facet indexing (wiring partner INV-21) |
| 14 | **INV-21** | Authenticity / Authorized-Retailer Badging at Price Context | NEW | **LOW** | Hero lockup `✓ Authorized — Official Warranty + replacement + 3× if fake` + Mall/flagship tag; reuses 13 brand PLPs `sitemap-analysis.md:26`. `applicability-review.md:142-144` | Brand authorization proof + warranty detail sheet (no backend; companion to INV-20 two-layer trust) |
| 15 | **INV-22** | Browse Resumption — Recently Viewed Rail + Continue Shopping Deep-Link | NEW | **LOW** | `localStorage viewHistory (8)+lastPlpUrl+compareQueue+searchHistory` → rails + `Smart TV: Samsung 55"+,1–2L (14)→Continue`. `personalization-current-state.md:9-10` NOT OBSERVED | viewHistory store (shares INV-C03/23/C05) + auth migration via INV-32 (stage 2) |
| 16 | **INV-23** | Smart Compare Workspace — Persistent, Auto-Populated, Decisive-Attribute & Total-Cost Aware | NEW | **HIGH** | Sticky bar `Compare (2/3)` → auto-populated `/compare` + decisive tint 6–8 rows + total-cost pin + diff highlight + share URL. `pattern-library.md:47-56` | Spec normalization per category + delivery/EMI/energy feeds (INV-13/14) + family graph `?familyRef` |
| 17 | **INV-24** | Guided Selling Framework — Need→Constraints→Budget Finder (5 Lenses + Hub) | NEW | **HIGH** | Umbrella wizard + 5 lenses (AC sq ft×height×top-floor/sun→tonnage; Fridge 18L=1 bag+measure guard; TV distance→size; Washer kg; Kitchen TDS). `pattern-library.md:34-44` | Rule tables per category (brand-spec validated) + PLP filter mapping + PDP verdict chip; hub INV-04 as enabler |
| 18 | **INV-25** | Complete-the-Setup — Bundles, FBT & Consumable Attach (Pre-Add + Cart Grouping) | NEW | **MEDIUM** | Complement rule engine (AC→stabilizer/bracket, TV→soundbar/mount) as PDP toggleable bundle + Cart rail grouped-line. `pattern-library.md:143-152` | Family→attach mapping (shares family graph) + bundle CMS + inventory/price delta |
| 19 | **INV-26** | Plural Payment Row — COD + bKash/Nagad + Card-on-Delivery + Online/EMI (District-Aware) | NEW | **LOW** | Co-equal row `◉ COD ✓ | Card on Delivery ✓ | bKash/Nagad ✓ | Online (EMI)` + `Delivery to Rajshahi: COD available` from zone matrix. `applicability-review.md:144-146` | Zone/SLA table (shares INV-13) + EMI master (INV-14) |
| 20 | **INV-C06** | Cart Drawer & Feedback System — Drawer, Stepper, Landed-Cost Truth, Toasts, CTA Hierarchy | FIX/NEW | **MEDIUM** | Slide-in mini-cart + `Subtotal+Delivery+Install→Total` + stepper `Cart→Delivery→Payment→Confirm` + toasts + sticky primary ATC + empty-state recovery. `pattern-library.md:164` 12D | Zone/fee table (INV-13/14) for truth row; `localStorage` wiring (INV-22/32) for empty-state injection |
| 21 | **INV-28** | Open-Box Delivery + OTP Doorstep Verification | NEW | **HIGH** *(operationally VERY HIGH if rolled to all >Tk 20k fleet-wide)* | Eligibility badge by pincode + Order Summary opt-in + rider opens both packings + OTP + photo log. `pattern-library.md:162` · `applicability-review.md:145` | Zone truth (INV-13) + fulfilled-order OTP/photo process + rider training/ops capacity |
| 22 | **INV-C05** | Human Support Spine — WhatsApp/Messenger + Hotline + Store Visit | NEW/IMPROV | **MEDIUM** | PDP deep-link `Share via WhatsApp — Ask agent about this fridge` + hotline 16212 sticky bar + nearest-3-stores + Schedule Visit + Track wiring. `page-analysis.md:14,18-19,199-204` | WhatsApp/Messenger deep-links; store inventory feed (shares INV-13); agent roster |
| 23 | **INV-32** | Authentication Friction & Guest→Auth Continuity | FIX | **MEDIUM** | Consolidate split phone field + OTP velocity + consider password/social alt + `localStorage→account` migration for viewHistory/compareQueue/wishlist/searchHistory. `page-analysis.md:192-195` | Auth service + migration layer (gating INV-22/23/33/C03 personalization) |
| 24 | **INV-33** | Exchange & Return Value — 14-Day Badge + Cross-Category AI Diagnostics + Timeline | NEW | **VERY HIGH** | Static badge `14-Day ✓` = LOW, but cross-category `up to Tk12k→inspection→OTP` + 10-step AI + cross-category (fridge→washer/mobile→laptop) + timeline = VERY HIGH. `applicability-review.md:150` | Valuation feed (AI or static table phase1) + inspection ops + wishlist pipeline (shares INV-32 auth) |
| 25 | **INV-34** | Accessibility & Icon System — Labeled Controls, Contrast, Keyboard Order | FIX | **LOW** | Pair icon-font `  ` with labels/aria+tooltip + contrast + tab order audit. `page-analysis.md:7-14` | ARIA/tooltip component; WCAG audit (no data dependency) |

> **Distribution:** LOW 8 · MEDIUM 6 · HIGH 8 · VERY HIGH 3. Phased initiatives (INV-12, INV-16, INV-33) show range; classification reflects full scope.

---

## Detailed Feasibility — Per Initiative

### INV-01 — Repair Broken Browse Paths (`/undefined` See All) — **LOW**

- **UI:** Minimal — audit hydration fallback for empty slug in teaser modules; guard/guard-redirect for empty href. Same fix applies to Brand PLP sub-sections `/samsung/undefined` (`page-analysis.md:77`).
- **Data:** None new. Reads existing sitemap route table + category taxonomy.
- **Backend:** None. Build-time/link-time check.
- **Third-party:** None.
- **Personalization:** None.
- **Content:** None.
- **Operational:** Add automated link-integrity check in CI; map each See All to correct L1/L2 category PLP (`/air-conditioner`, `/refrigerators/no-frost/side-by-side`).
- **Complexity driver:** Scope is bug, not system — 5+ homepage occurrences `page-analysis.md:56-57` + brand PLP 4× `site-inventory.md:77`.
- **Dependencies:** None. **P0 blocker** — ships before every downstream OPP (notably INV-C01, INV-04, INV-C03 recovery advisor CTA).
- **Risk:** Masked by second BrowserOS check returning `undef 0` but snapshot authoritative — do not de-prioritize.

### INV-C01 — IA & Discoverability Hygiene — **LOW**

- **UI:** Low — at most add `/tv-av` root page shell; trailing-hyphen is redirect, not UI. Canonical is `<link rel=canonical>` + title/H1 differentiation; tile fix is homepage `Shop By Category` grid alignment `page-analysis.md:47`.
- **Data:** Redirect table (4 trailing-hyphen slugs `sitemap-analysis.md:132-134`) + canonical rule (`Brand-only → canonical to brand PLP`). Flat PDP namespace (`101 at root` `sitemap-analysis.md:27`) is a *decision* — at minimum compensate via INV-17 family context if hierarchy not rebuilt.
- **Backend:** Redirect/canonical logic (CDN or app router). Sitemap hygiene `sitemap.xml` loc entries.
- **Third-party:** SEO crawl (Google Search Console validation).
- **Personalization/Content/Operational:** None; copy tweak for brand PLP distinct title.
- **Dependencies:** Depends on **INV-01** shipping first (slug guard is P0). Sibling wiring to INV-C01 children is internal — single IA squad release.
- **Why LOW not MEDIUM:** No feed build, no moderation, no scorer — IA design + redirect QA only. Squads often overestimate canonical work; real cost is decision + verification.

### INV-04 — SEO Architecture — **LOW**

- **UI:** Low — re-layer PLP template: grid/filters stay above fold; 1,500+ word SEO block `page-analysis.md:90-91` moves below pagination. Add `/buying-guides/{category}` hub (Currys/Coolblue pattern `pattern-library.md:42-44`).
- **Data:** CMS hub content (re-wrapped SEO copy, not new research).
- **Backend:** Template order + pagination anchor; preserve SEO equity (no deletion, no 301 churn).
- **Dependencies:** Enabler for **INV-24** (wizard CTA `Not sure? 30-sec guide` links to hub) — but ships independently per `initiative-merging.md:166` `FIX vs NEW parent/child`.
- **Complexity note:** Perceived SEO risk inflates estimates — actual build is CSS/template + CMS page per top category (AC/Refrigerator/Washing Machine/Home & Kitchen).

### INV-C02 — PLP Browse Controls Hygiene — **LOW**

- **UI:** Low–Medium frontend only — persistent chip row + count `3 filters: Samsung × 55" × 1–2L` + per-chip remove + `Clear all` + `Showing 1–12 of 44` + prev/next + enumerated sorts 4–5 (Relevance/Price low→high/high→low/Discount/Newest). Single PLP template header `page-analysis.md:75-86`.
- **Data:** Facet taxonomy hygiene: audit SKU→facet mapping; merge `Display Size 55"(10)` + `Screen 32"(2)` duplication `product-discovery.md:79-80`; collapse dual price `0–10,55,000` slider + buckets `0 to 1,00,000` `page-analysis.md:75-81` to single control with presets.
- **Backend:** None core; suppress `Customer Review` heading until INV-20 pipeline has n≥5 — conditional render, not feed.
- **Dependencies:** Suppression rule shared with INV-20 social proof pipeline; otherwise standalone.
- **Why LOW:** Restores expected PLP feedback (Nielsen visibility of system status) of VERIFIED controls `ecommerce-capabilities.md:16-22` — no new data model, confirmed by `duplicates-and-overlaps.md:144-150` as remediation.

### INV-06 — Homepage Prioritization & Performance Budget — **MEDIUM**

- **UI:** Medium — triage 7+ serialized mini-grids `page-analysis.md:48-54` to `hero + Shop By Category + 2 prioritized rows` (AC/Fridge/TV breadth `sitemap-analysis.md:20-26`); defer rest below fold.
- **Data:** Performance budget (image count/weight) — 68 DOM images on Mixer PDP `product-page-variations.md:49` + 68+ homepage. Implement lazy-load + budgeted carousel count.
- **Backend:** CDN/image optimization; not search/index.
- **Personalization:** Explicitly NOT affinity reorder — OPP-15 QUESTIONED deferred `applicability-review.md:128-135`; do not build scorer here.
- **Content/Operational:** Merch governance for pinned rows; A/B cut vs add.
- **Why MEDIUM not LOW:** Requires perf audit + cross-template image hygiene + CMS triage decision, not just a chip row. Still far below HIGH — no feed, no moderation.

### INV-C03 — Intelligent Search & Recovery — **HIGH**

- **UI:** Medium — debounced (150–200 ms) dropdown with rows Product (+price/stock+thumb)/Brand/Category/SKU-exact, `Recent: samsung 55" | daikin 1 ton` chips (cap 6), scented placeholder `Try FTKL12TV16WD or Samsung TV 55"` replacing `Search Here` `page-analysis.md:9`.
- **Data:** Suggestion index (title/SKU/brand/category) with SKU-boost when query has 3+ alphanumerics (photographed-code buyers `page-analysis.md:111`). Synonym table + zero-result template. `cross-review.md:205` verification gate: empty dropdown may be *rendering bug, not missing index* — re-test before build.
- **Backend:** Search index + debounced typeahead service.
- **Advanced layer:** Fuzzy edit 1–2 + QWERTY-adjacent `L↔K` + Bangla digit map + synonym `inverter=invator` (7B) + facet-relax `Remove Brand →12` with count preview + `Did you mean` + advisor CTA `Try AC Finder` → INV-24 (7C `pattern-library.md`). Bangla-English symmetry is BD-specific.
- **Personalization:** Stage2 affinity-biased ranking after INV-22 volume — MEDIUM-HIGH but filed as Gate2 P2 inside same initiative `initiative-merging.md:78-82`.
- **Third-party/Operational:** Query log for top zero-result terms (merch insight).
- **Dependencies:** Shares `localStorage searchHistory` with INV-22; recovery template feeds INV-24 advisor; facet-relax shares INV-C02 facet taxonomy truth.
- **Why HIGH:** Template + synonyms alone brackets ~40% recovery before fuzzy engine (short build), but full fuzzy + synonym + facet-relax + staged personalization across pre-submit/post-submit is a search-epic with two gates. Bors.

### INV-12 — Rich Media Inspection — **HIGH** *(phased)*

- **UI:** Medium — viewer: hover-zoom desktop + pinch mobile + `1/7` count + scrub (Asos/Amazon pattern `pattern-library.md:60-67` Problem 4A).
- **Content/Asset:** HIGH — functional video 15–25 s per category template (AC wall, TV panel/HDR, washer spin, fridge door swing; muted, lazy-loaded, respects `MOBILE-01 P2` `issue-register.md:46`) reuses brand reels (Samsung/Haier/Daikin) but requires CMS governance + per-category template. 360° where asset exists + AR phase 3.
- **Data:** Dimension normalization `W×H×D + ventilation gap + door swing + bracket` from structured spec — single enrichment task `product-page-variations.md:61` that also feeds INV-16 checker and INV-24 Fridge guard (build once, `applicability-review.md:158-169`).
- **Phasing:** `initiative-merging.md:119` already merged — keep as one viewer pipeline: **Gate1 zoom = MEDIUM** (week, no reshoot) → **Gate2 video/360/dimension overlay = HIGH**.
- **Dependencies:** Brand asset pipeline + spec dimension feed + gallery CMS. Suppress generic for Personal Care trimmer `Tk 3k` `product-page-variations.md:104`.
- **Why HIGH not VERY HIGH:** No moderation, no ops capacity — asset production scales by category but is bounded.

### INV-13 — Delivery & Serviceability Estimator — **HIGH**

- **UI:** Low — single district/area *text* field (not GPS permission — anti-pattern per `regional Finding 5` `applicability-review.md:149`) between price and ATC `page-analysis.md:125` `Home Delivery Enable your Location` gate replacement. Result card.
- **Data:** **The shared table.** District→Zone/SLA + delivery fee + install fee + store inventory mapping `applicability-review.md:158-169` build-once feed. 64-district estimator is hygiene, not personalization. Earned `Fast Delivery` PLP badge/filter alongside existing `EMI36` `page-analysis.md:87`.
- **Backend:** Serviceability service (yes/no + SLA + fee + store alt distance); session persistence `remember pincode` (personalization layer 20%, `opportunity-pool.md:7-20`).
- **Dependencies:** Logistics zone/SLA feed + store inventory/district mapping + cart price-breakdown wiring (`initiative-merging.md:108`). Feeds INV-14, INV-16, INV-26, INV-28, INV-C05, INV-C06.
- **Operational:** Store Locator `/store-locator` VERIFIED `page-analysis.md:199-204` already exists — wire, don't rebuild.
- **Why HIGH:** Zone/SLA matrix + store feed is cross-squad data work; UI is trivial. 80% ops data / 20% memory per `applicability-review.md:49`. Suppress low-ticket `Tk 3k` trimmer.

### INV-14 — True Cost & EMI Planner — **HIGH**

- **UI:** Medium — single ownership row beneath sale price `Upfront × + Delivery Tk0 + Energy ~Tk/mo (1yr/5yr) → EMI from Tk/month × tenure @ bank` + picker 3/6/12/24/36 + tariff/hours slider; eligibility verdict `EMI not available for this SKU → see EMI Bank List` (trust repair 5C `pattern-library.md:72-80`).
- **Data:** EMI bank/tenure master (32 banks, BDT 5k threshold Pickaboo / 10k Daraz `applicability-review.md:94-98`) + tariff table + EER per SKU + install fee table (shares INV-13). Formula `annual kWh × unit rate` `pattern-library.md:90-92`.
- **Backend:** Eligibility matrix + cart inheritance as grouped breakdown.
- **Regional nuance:** Offline form latency must be disclosed `blocked amount → signed form 3d → bank converts 5–10d` (Pickaboo/Daraz) — otherwise BD buyer paywall surprise. District-aware but finance-owned, vs INV-13 ops-owned `initiative-merging.md:170`.
- **Dependencies:** Requires delivery table (INV-13) for combined row; feeds INV-23 total-cost pin and INV-C06 cart truth.
- **Why HIGH not VERY HIGH:** Rule table + calculator, not pipeline/moderation — EMI inconsistency `product-page-variations.md:55` Haier fridge no EMI vs others is HYG gap.

### INV-C04 — Spec Literacy & Warranty Truth — **LOW**

- **UI:** Low — inline underline + tap drawer/tooltip; legend row `Special Component = Compressor/Panel/Motor per category` `product-page-variations.md:61`.
- **Data/Content:** Glossary CMS 25–40 terms category-scoped (`EER 3.15 = 1.1 kW → ~Tk Y/mo @8h/day @Tk Z/kWh`, `R32`, `HQLED`, `Twin inverter`) + energy A–G+QR fiche + running-cost formula `watts×hours/1000×tariff` shared with INV-14 `pattern-library.md:86-92`.
- **Backend/Personalization/Operational:** None. Content-only, ships before finders/planner (prerequisite per `cross-review.md:156` EDS-05 distinct).
- **Why LOW:** Highest leverage-to-effort in portfolio — fixes `Parts-0M / Motor-300M` implausible nomenclature `issue-register.md:30` TRUST-01; propagation to PDP/Cart price context is copy, not service.

### INV-16 — Installation Feasibility Checker — **MEDIUM → VERY HIGH**

- **Gate1 Checker — MEDIUM:** Per-SKU feasibility toggles → verdict `✓ Feasible — Add to Cart` / `⚠ Requires bracket Tk 2,500 — order bundle` with fee table `Free/Paid + Tk X` shares INV-13 fee table; dimension spec normalization `W×H×D+gap+swing` shares source with INV-12. No calendar. `pattern-library.md:132-137` Problem 10A AC outdoor wall/bracket/drain/soc 1.5 m; Fridge 1" gap+door swing 90°+hinge 5 cm; Washer inlet/drain. Content, not scheduling.
- **Gate1b Priced-basket (John Lewis model) — MEDIUM:** `Add Installation` + `Add Recycling (haul away)` as line items (£115 washer / £30 fridge / £25 disposal `applicability-review.md:113-117`) + `Before You Buy / Before We Deliver` checklist video.
- **Gate2 Booking — VERY HIGH (ops-gated, defer):** Calendar slot by district/installer team + prerequisites ticked + fee if any + reschedule + order↔service-order linkage + push via `Track Your Service` `page-analysis.md:7` VERIFIED link. **Gated behind slot-capacity feed confirmation `cross-review.md:175`** — building UI without feed is worse than no booking.
- **Dependencies:** SKU install table + slot inventory feed by district; Store Locator feed `page-analysis.md:199-204`.
- **Sequence note:** Inventory correctly files Gate2 inside same INV as deferred phase `master-initiative-inventory.md:467` — prevents double-count.

### INV-17 — Variant & Family Navigator — **HIGH**

- **UI:** Low — sibling chips with price delta + stock badge `65" +Tk18,000 In stock | 75" Currently Unavailable` placed above ATC so size change re-validates delivery/energy/EMI.
- **Data:** **The catalog modeling task.** Product family graph `model_root → variants by tonnage/litres/display size/kg` rendered per `pattern-library.md:119-128` Problem 9 Apple/Samsung `43/55/65 +delta`. Top 30 roots cover ~70% high-ticket (Haier 12, Tron 9 `sitemap-analysis.md:44`). Flat PDP namespace `sitemap-analysis.md:27` compensation is explicit.
- **Backend:** Graph service + live price/availability feed; navigation PDP→sibling PDP (new URL) preserves `?familyRef` for Compare/Recently Viewed.
- **Dependencies:** Suppressed when family <2. Feeds INV-23 add-to-compare, INV-12 re-validate on switch, INV-25 attach mapping — build once, `applicability-review.md:165`.
- **Why HIGH:** Not a second button (`Choose Ton 1/1.5` AC `page-analysis.md:120-121` is trivial) — *family graph* is net-new; taxonomy exists as PLP facets `page-analysis.md:86` but not as PDP graph.

### INV-20 — Social Proof Pipeline — **VERY HIGH**

- **UI:** Low — PDP header badge above fold near price + PLP card `4.6★ (212)` never overlapping `-23.45%` `page-analysis.md:87` + review facet `★★★★&up (41)` indexed.
- **Data/Backend:** **The pipeline before badges.** `pattern-library.md:87-90` Problem 6B: Collection (post-delivery prompt) → Moderation → Aggregation (rolling avg, suppress n<5 → `Be first to review — ask Q`) → PDP/PLP badge → review facet indexed → Q&A with `Verified Purchase` marker. Seeded empty-state governance — no fake `5.0 (1)`.
- **Evidence:** Tabs exist but content NOT OBSERVED `page-analysis.md:131-133` + `ecommerce-capabilities.md:31-33`; `Customer Review` filter heading with no buckets `page-analysis.md:81` FILTER-02 P2 `issue-register.md:21`.
- **Dependencies:** Paired with INV-21 two-layer trust `applicability-review.md:124-126` ENHANCED — ratings alone insufficient post-Evaly `phase-4-summary.md:158`. Never overlapping discount badge requires template guard.
- **Why VERY HIGH not HIGH:** Moderation queue + verified-purchase check + aggregation service + PLP badge wiring + facet indexing is pipeline, not row. Auth volume (INV-32) gates feed.

### INV-21 — Authenticity / Authorized-Retailer Badging — **LOW**

- **UI:** Low — PDP hero lockup near price `✓ Authorized — Official Warranty` + `Authenticity Guarantee (replacement + 3× if fake)` + Mall/flagship tag + seller identity + warranty detail sheet; Cart trust row `page-analysis.md:34` homepage bar echo.
- **Data/Content:** Reuses 13 brand partnerships (Samsung/Daikin/Haier `sitemap-analysis.md:26`) — proof copy, no feed. DarazMall/Bikroy/Pickaboo pattern `applicability-review.md:142-144` + `regional Finding 1` post-Evaly 2–3% penetration.
- **Why LOW:** No backend; companion to INV-20 two-layer trust `initiative-merging.md:110-112`; highest ROI per effort after INV-01 fix.

### INV-22 — Browse Resumption — **LOW**

- **UI:** Low — rail thumbnail+price+stock badge (swipe mobile, cap 8) on homepage below hero / PLP sidebar / PDP footer + empty-cart injection `page-analysis.md:159-164` + deep-link card `Smart TV: Samsung 55"+, 1–2L (14) → Continue` reopening last filtered PLP/search with query+facets reapplied.
- **Data:** `localStorage viewHistory (8) + lastPlpUrl + compareQueue + searchHistory` (same store as INV-C03 Recent + INV-23 queue + INV-C05 share URL per `initiative-merging.md:114-116`).
- **Backend:** None stage1; migration to account on OTP via INV-32 stage 2.
- **Why LOW:** Cheapest retention lift per `opportunity-pool.md:21-36` — no backend for stage1, rails only. `personalization-current-state.md:9-10` NOT OBSERVED + Journey F wholly unserved `issue-register.md:14`.

### INV-23 — Smart Compare Workspace — **HIGH**

- **UI:** Medium — sticky bar `Compare (2/3)` accumulates taps (session+auth persisted) `page-analysis.md:129` ``; `/compare` auto-populated (search remains add-more only) `page-analysis.md:173-178` empty 3-slot + `Highlight differences` checkbox (already exists, but empty) + remove/share URL (WhatsApp family decision).
- **Data:** Spec normalization per category (decisive-attribute tint 6–8 rows vs 40 — AC `EER/tonnage/R32/Applicable sq ft`, TV `panel/HDR`, Fridge `litres/door/inverter` per `pattern-library.md:47-56` Problem 3B) + verdict strip.
- **Backend:** Compare store (session+auth) + total-cost pin row `Price+Install+1yr Energy+EMI/mo` from INV-13/14 pinned (3C `pattern-library.md`); permalink generation; responsive swipe.
- **Dependencies:** Needs delivery/EMI/energy feeds (INV-13/14) + family graph `?familyRef` (INV-17) for context; diff-highlight by checkbox.
- **Why HIGH:** Already correctly merged `duplicates-and-overlaps.md:46-54` C3 PER-03+FEA-08+EDS-08 as one workspace — Journey D P1 `issue-register.md:41` sharpest high-ticket gap.

### INV-24 — Guided Selling Framework — **HIGH**

- **UI:** Medium — single 3-step wizard `Need → Constraints → Budget/Preference` outputs filtered PLP URL + PDP verdict chip `✓ Fits your 120 sq ft — 1.5 Ton`.
- **Data/Content:** **5 lenses as content packs** + rule tables validated against brand specs `product-detail-experience.md:12` + CMS for wizard copy. No ML. Lenses: AC Finder (sq ft×height×top-floor/sun→tonnage `applicability-review.md:64` LG 20 BTU/sq ft) first → Fridge Validator (`18L=1 bag` + 7-step measure guard Currys niche H/W/D+90° hinge 5 cm+1–2 cm ventilation `applicability-review.md:66`) → TV Advisor (distance→size→resolution/panel) → Washer Advisor (kg→front/top) → Kitchen/Purifier (cook family/wattage/jars, TDS→RO/UV) per `opportunity-pool.md:67` MED thin-evidence flag (thin 7 PDPs `sitemap-analysis.md:43`).
- **Dependencies:** IA hub INV-04 (`/buying-guides/{category}` CTA `Not sure? 30-sec guide` Currys/Coolblue) as enabler; PDP verdict wiring; shares `W×H×D+gap` with INV-12/16 and glossary explainability with INV-C04.
- **Why HIGH:** `duplicates-and-overlaps.md:58-71` C4 already collapsed 7 rows to one framework — umbrella is MEDIUM, but 5 governed lenses + PLP mapping + verdict chip is HIGH total. Shippable per lens (AC first = largest ticket, fewest SKUs).

### INV-25 — Complete-the-Setup — **MEDIUM**

- **UI:** Low — PDP toggleable bundle row + Cart post-add rail `Complete your setup` with grouped-line pricing.
- **Data:** Complement rule engine per family (AC→ stabilizer/wall bracket/copper wire, TV→ soundbar/wall mount/HDMI, fridge→ stabilizer, washer→ stand/detergent, purifier→ replacement cartridge cadence every 6 months). Two surfaces share one affinity table `pattern-library.md:143-152` Problem 11 Home Depot mandatory hookup kits.
- **Backend:** Bundle CMS + cart grouped-line handling + suppressed low-ticket guard (trimmer/mixer generic `cross-review.md:168`).
- **Dependencies:** Family→attach mapping shares family graph (INV-17); mandatory-kit doubles as install-failure prevention (ties to INV-16); single Related card `product-page-variations.md:65-66` NOT OBSERVED FBT `ecommerce-capabilities.md:56`.
- **Why MEDIUM:** Rule table + CMS, not pipeline — `duplicates-and-overlaps.md:74-82` C5 already merged 3 placements; core is merchandising logic.

### INV-26 — Plural Payment Row — **LOW**

- **UI:** Low — co-equal radio row beneath EMI row + Cart Order Summary `◉ Cash on Delivery ✓ | ◉ Card on Delivery (Swipe) ✓ | ◉ bKash/Nagad ✓ | ◉ Online Card (EMI eligible) ✓` with district-aware line `Delivery to Rajshahi: COD available`.
- **Data:** Reads same zone matrix as INV-13; no new table. `regional Finding 4` 75–90% COD (Levree wallet) — choice itself is trust per `applicability-review.md:146` Pickaboo.
- **Backend:** Zone availability check only; pairs with INV-14 financing row + INV-13 delivery in same pride context, but card vs COD polarity requires distinct UI `initiative-merging.md:179`.
- **Why LOW:** Text + zone availability; plural row is STANDARD BD `pattern-library.md:161` 12A.

### INV-C06 — Cart Drawer & Feedback System — **MEDIUM**

- **UI:** Medium — slide-in mini-cart on Add confirmation with count animation; Cart Order Summary truth row `Subtotal + Delivery + Install → Total` explicit `Free vs Tk X` shares INV-13/14 fee tables; progress stepper `Cart → Delivery → Payment → Confirm` with trust micro-copy; feedback toasts on every add/wishlist/compare (repairs `FEEDBACK-01 P1` `issue-register.md:42`); empty-state injection of INV-22 rails + `Continue Shopping`; CTA hierarchy single sticky primary ATC + secondary Compare/Wishlist (deduplicating `Add To Cart ×2` `page-analysis.md:126-128`).
- **Data:** Reuses zone/fee table + `localStorage` wiring with INV-22/32 (no new feed).
- **Backend:** Cart/drawer/stepper + populated-cart hygiene (`ecommerce-capabilities.md:40-41` VERIFIED empty, NOT TESTED populated `page-analysis.md:159-162` `Subtotal: ৳0 Total: 0`).
- **Dependencies:** **Depends on INV-32** auth migration for persistence; shares landed-cost truth with fulfillment platform.
- **Why MEDIUM:** `initiative-merging.md:55-56` M-06 merged INV-27+INV-31+INV-19 because drawer trigger ambiguous without CTA hierarchy and toast without surface — one FEEDBACK-01 system, not three tickets. `pattern-library.md:164` 12D STANDARD Apple/ASOS/Best Buy stepper.

### INV-28 — Open-Box Delivery + OTP — **HIGH**

- **UI:** Low — PDP badge `Eligible for Open Box Delivery at your pincode ✓` (from INV-13 zone truth) + Order Summary opt-in for electronics >Tk 20k.
- **Data:** Eligibility flag per pincode (derived, not new master).
- **Operational:** **The driver.** Rider opens outer + brand packing in front of customer, checks damage/correct item/IMEI/accessories; customer shares OTP only after satisfaction, photographed + reference logged (Flipkart OBD T&C `regional Finding 2` `applicability-review.md:145`). Owned Store Locator `page-analysis.md:199-204` + logistics gives credible Wishmaster vs pure marketplace; self-unbox burden contrast TechEnclave.
- **Why HIGH (ops-gated VERY HIGH at fleet scale):** PDP badge is LOW, but doorstep protocol is rider training/process change + photo log + dispute handling for >Tk 20k ticket + COD 75–90% dispute risk. EMERGING BD differentiator vs STANDARD India.

### INV-C05 — Human Support Spine — **MEDIUM**

- **UI:** Low — WhatsApp/Messenger PDP deep-link `Share via WhatsApp — Ask agent about this fridge` (pre-filled PDP URL) + hotline fallback; premium manager for >Tk 50k `Get personal manager` (ChalDal Premium Care model `regional Finding 7`).
- **Data:** Wire existing assets — `Need help? Click Here ` `page-analysis.md:14` + `16212 9AM–9PM` `page-analysis.md:18-19` footer-only → sticky call bar on PDP/Cart + nearest-3-stores + `Schedule your visit` district cards + Track wiring `page-analysis.md:7` `Track Order Status / Track Your Service` to real-time (Daraz control towers 65 hubs `applicability-review.md:149`).
- **Operational:** Agent roster + phone/WhatsApp handoff; store inventory wiring (shares INV-13 pickup alt).
- **Why MEDIUM:** `initiative-merging.md:54-55` M-05 merged INV-29 NEW + INV-30 IMPROVEMENT because same support surface split across header/footer/locator `04-benchmark/new-opportunities.md:10-11` + `applicability-review.md:147-149` 12C. Deep-links are LOW; sticky bar + store bridge + Track wiring = MEDIUM.

### INV-32 — Authentication Friction & Guest→Auth Continuity — **MEDIUM**

- **UI:** Low–Medium — consolidate split phone field (`+880` selector + two textbox inputs `page-analysis.md:192-195` VERIFIED) to single input; consider social/password alt for desktop; tighten OTP velocity (`ecommerce-capabilities.md:57-60`).
- **Data/Backend:** `localStorage → account` migration on OTP success for `viewHistory + compareQueue + wishlist + searchHistory` (`cross-review.md:230` M-05 un-designed handoff). **Gate for all personalization** — without it INV-22/23/C03 Stage2 lose cross-device value.
- **Dependencies:** None upstream; downstream gate for INV-22/23/C03/33. `personalization-current-state.md:13` wishlist persistence AUTHENTICATION REQUIRED + `issue-register.md:39-40` AUTH-01/02 P2.
- **Why MEDIUM:** Interaction fix + migration layer; not building new auth platform, but migration fidelity matters.

### INV-33 — Exchange & Return Value — **VERY HIGH**

- **UI:** Low — PDP badge next to `In stock` `14-Day Hassle-Free Return ✓` (Daraz 14-day ALL products Aug 2025 baseline `applicability-review.md:150` + `regional Finding 8`) — LOW alone.
- **Value flow — VERY HIGH:** Cross-category `up to Tk 12k → doorstep inspection → OTP` beneath price `product-discovery.md:119-120` + `ecommerce-capabilities.md:52` `/exchange` hub VERIFIED 2-card with parameterized `/exchange/{id}?category=…`; cross-category extension (fridge→washer, mobile→laptop, fan→purifier) + 10-step AI condition check within minutes (Flipkart ReCommerce 26 cats + cross-category + Trust Shield 30-day `applicability-review.md:151`). Valuation explicit `Restocking 2–3 weeks — notify at arrival or show in-stock alternatives`; `Get Stock Alert` on Dell `Currently Unavailable` with no timeline `page-analysis.md:113` `issue-register.md:43` FEEDBACK-02.
- **Data/Backend:** Valuation feed (start static `up to` + inspection truth → AI phase2); ops inspection + doorstep OTP; wishlist intelligence wiring (deferred P2 after auth base per `applicability-review.md:74-81` QUESTIONED sequencing).
- **Why VERY HIGH:** Idle BD households as currency; cross-category AI diagnostics + inspection ops is ops + model.

### INV-34 — Accessibility & Icon System — **LOW**

- **UI:** Low — pair icon-only controls `` cart / `` wishlist / `` share / `` Compare `page-analysis.md:7-14` header + PDP trio + Cart/Compare controls with visible text labels or aria-label + tooltip; verify contrast ratios + tab order + focus indicator; audit `Highlight differences` `page-analysis.md:173-178`.
- **Data/Backend/Operational:** None. WCAG hygiene audit, not feature. Keep distinct from INV-C06 toasts/INV-C02 chips per `initiative-merging.md:183` — audit remediation.
- **Dependencies:** Independent; ship early as hygiene.

---

## Dependency Map — Critical Paths & Shared Build-Once Tables

### Shared tables — build once, surface at many placements (`applicability-review.md:158-169` + `initiative-merging.md:187-201`)

| Shared Table / Component | Built for | Surfaced at | Build owner |
|--------------------------|-----------|-------------|-------------|
| **District→Zone/SLA + delivery fee + install fee + store inventory** | INV-13 anchor | INV-13 estimator · INV-14 energy/install row · INV-16 verdict/basket · INV-26 district payment · INV-28 OBD badge · INV-C06 truth row · INV-C05 store bridge · INV-04/24 guard | Ops/Logistics (single source of truth) |
| **EMI bank/tenure master + BDT 5k threshold + form-latency copy** | INV-14 anchor | INV-14 picker/verdict · INV-23 total-cost pin · INV-26 plural row · INV-C06 cart inheritance | Finance |
| **`W×H×D + ventilation gap + hinge/swing + bracket` dimension normalization** | Catalog enrichment (`product-page-variations.md:61`) | INV-12 dimension overlay · INV-16 checker verdict · INV-24 Fridge Validator guard | Catalog/Content |
| **Tariff × EER/kWh → `Tk/mo` formula + glossary CMS 25–40 terms** | INV-C04 anchor | INV-C04 decoder · INV-14 energy row · INV-24 explainability · INV-12 | Content + Finance (tariff) |
| **Family graph `model_root → variants by dimension` + price/stock feed** | INV-17 anchor | INV-17 chips · INV-23 add-to-compare · INV-12 re-validate on switch · INV-25 attach mapping | Catalog (top 30 roots ≈70% cover) |
| **`localStorage viewHistory(8)+lastPlpUrl+compareQueue+searchHistory` + auth migration** | INV-22 anchor | INV-C03 Recent · INV-22 rail · INV-23 queue · INV-C05 share URL | Frontend + Auth (INV-32 migration) |
| **Review aggregation + verified-purchase + moderation pipeline** | INV-20 anchor | INV-20 badges/facet/Q&A · INV-21 companion two-layer trust | Trust/Moderation |
| **Store Locator feed (`/store-locator` VERIFIED `page-analysis.md:199-204`)** | Existing | INV-13 pickup alt · INV-16 · INV-C05/INV-28 linkage | Wire, don't rebuild |

### Hard dependencies (must ship before / gates build)

```
P0 gate — ship first, no prereq:
  INV-01 (/undefined) ──→ unlocks all browse
  INV-34 (a11y) + INV-C01 (IA) + INV-04 (SEO re-layer) + INV-C02 (PLP controls)
        may ship in same P0 hygiene release as INV-01

Resumption store (no backend stage1):
  INV-32 (auth migration design) ──→ enables cross-device value of ──→ INV-22 / INV-23 / INV-C03 Recent
  BUT stage1 localStorage rails (INV-22, INV-23 queue, INV-C03 autocomplete Recent) ship WITHOUT waiting for migration

Fulfillment confidence platform (single table, distinct surfaces):
  INV-13 (zone/SLA estimator) ──→ builds table ──→ INV-14 / INV-26 / INV-28 / INV-C06 truth / INV-C05 store bridge
  INV-13 district text swap (`Enable your Location` → district/area text) is the unlock for zone truth

Literacy prerequisite:
  INV-C04 (jargon decoder + warranty legend + energy translator) ──→ prerequisite for ──→ INV-14 energy row explainability + INV-24 finder explainability + INV-16 fee transparency

Catalog modeling track (parallel, not blocking P0 trust row):
  INV-17 (family graph) ──→ feeds INV-23 / INV-25 / INV-12
  `W×H×D` normalization ──→ feeds INV-12 overlay + INV-16 checker + INV-24 guard

Trust stack at price context (same PDP hero lockup, no ordering constraint beyond co-location):
  INV-C04 (warranty legend) + INV-20 (ratings pipeline) + INV-21 (authenticity proof) → two-layer trust companion per applicability-review.md:174
  INV-20 pipeline must precede badges/facet; INV-21 has no prereq — ships cheapest

Search sequence:
  INV-C03 Gate1 typeahead + Gate1b zero-result template/synonym (short build, brackets typo)
      ──→ Gate2 affinity ranking (P2, after INV-22 volume)
  Zero-result advisor CTA ──→ INV-24 (finder) deep-link — not blocking

Cart boundary (consumes fulfillment truth):
  INV-C06 (drawer/stepper/toast) consumes INV-13/14 table; depends on INV-32 for persistence; empty-state injects INV-22

Ops-gated deferrals (do NOT block P0/P1):
  INV-16 Gate2 slot booking — gated behind slot-capacity feed (ops confirmation)
  INV-33 AI diagnostics — after wishlist persistence + INV-20 base proves auth volume
  INV-24 Kitchen/Purifier lens — thin evidence 7 PDPs, P2
```

### What does NOT gate what (avoids false sequencing)

| Pair | Relationship | Sequencing rule |
|------|--------------|-----------------|
| INV-13 Delivery vs INV-14 EMI vs INV-26 Plural Row vs INV-28 OBD | Shared table, distinct PDP/Cart/doorstep surfaces | Build table once (INV-13), surface independently — do not serialize as 4 phases of one ticket |
| INV-17 Family graph vs INV-23 Compare | Family graph helps compare, but compare is usable with hand-typed `?familyRef` from PLP taxonomy | Compare ships without waiting for full graph; family chips enhance it |
| INV-12 Rich Media vs INV-16 Checker | Shared `W×H×D` source is wiring, not build — viewer vs verdict | Keep distinct per `initiative-merging.md:168` |
| INV-C04 Glossary vs INV-24 Finder | Glossary is prerequisite for *literacy*, not for wizard *mechanics* | Finder mechanics can ship with glossary stubs; glossary ships first as content |
| INV-22 Resumption vs INV-C03 Search | Same localStorage but resumption (item+PLP context) vs search (recent terms) are different rails | Keep distinct per `initiative-merging.md:175` |

---

## Feasibility Notes & Risks

1. **Do not build affinity homepage before P0 hygiene.** OPP-15 QUESTIONED per `applicability-review.md:128-135` + `cross-review.md:234-243` M-gaps — `NAV-01 /undefined` P0 `issue-register.md:7` + IA + `FILTER-01/SORT-01` remediation must prove lift before scorer + modular CMS + campaign governance.
2. **Search index verification before build.** INV-C03 autocomplete empty dropdown may be rendering bug not missing index `cross-review.md:205` — re-test live typing `AC`/`samsun tv` `product-discovery.md:40-43` before indexing effort.
3. **Populated-cart wiring remains NOT TESTED** `ecommerce-capabilities.md:40` — INV-C06 discovery may need inventory once items are in cart (`user-journeys.md:122-148` STOPPED BEFORE PAYMENT).
4. **Stock ETA feed has no BD-standard UI.** INVEST-33 timeline `Restocking 2–3 weeks — notify at arrival or show similar in-stock` avoids perpetual waitlist but feed is pipeline-heavy — keep as P2 after wishlist persistence `applicability-review.md:74-81`.
5. **Suppression rule (consistent with `cross-review.md:168` + BDT 5k `applicability-review.md:96`):** Suppress EMI row, energy row, checker, and FBT for Personal Care trimmer `Tk 3k` `product-page-variations.md:104` (+ mixer where wattage generic); show authenticity + plural payment everywhere.
6. **Phasing protects ROI.** For every HIGH/VERY HIGH, Gate1 is shippable without Gate2: INV-12 zoom before video; INV-C03 template/synonym before fuzzy; INV-16 checker before booking; INV-33 static `up to` + 14-day badge before AI. `applicability-review.md:182-191` sequencing mirrors this.

---

## Traceability

| Claim | File:Line |
|-------|-----------|
| 25 consolidated from 34 (6 merges, 15→6, net −9) + HYBRID INV-C06 | `initiative-merging.md:15-25` + `:42-57` + `:126-156` |
| 13/6/15 typing + 8 NEW + wiring | `master-initiative-inventory.md:27-31` + `applicability-review.md:142-152` + `:158-169` |
| P0 `/undefined` + IA flat/orhpan/hyphen + canonical + tile | `issue-register.md:7-11` + `sitemap-analysis.md:27,74-77,132` + `site-inventory.md:77,112` |
| SEO wall 1,500 words pushes grid below fold + hub | `page-analysis.md:90-91` + `pattern-library.md:42-44` Problem 2D |
| PLP chips/sort/facet hygiene (dual slider, Screen vs Display Size, empty Review) | `page-analysis.md:75-86` + `product-discovery.md:74-83` + `ecommerce-capabilities.md:16-22` |
| Search input VERIFIED, suggestions NOT FULLY VERIFIED, placeholder `Search Here`, SKU codes `FTKL12TV16WD/H55P7UX` | `ecommerce-capabilities.md:12-13` + `page-analysis.md:9,111` + `product-discovery.md:40-43` |
| PDP delivery gate `Enable your Location` + store locator | `page-analysis.md:125,199-204` + `ecommerce-capabilities.md:42-44` |
| EMI badges + fridge EMI absent + `Parts-0M/Motor-300M` + `68 DOM images` + `Add To Cart ×2` + `16212` footer-only | `page-analysis.md:87,113-117,126-128,18-19` + `product-page-variations.md:49,55,61` |
| Personalization NOT OBSERVED + Recently Viewed/Continue/Compare Queue | `personalization-current-state.md:9-10` + `ecommerce-capabilities.md:55` + `page-analysis.md:159-164,173-178` |
| OPP complexities (High/Med/Low) | `opportunity-pool.md:17,33,49,65,81,97,113,129,145,161,178,193,210,225,242` |
| VALIDATED/ENHANCED/QUESTIONED + 8 NEW + regional BDT 5k/75–90% COD/32 banks/14-day | `applicability-review.md:22-38` + `:52-64` + `:142-152` + `regional Finding 3/4/5/8` |
| 38→15 dedup + fate table + C1–C9 clusters + 8 missing M-gaps | `cross-review.md:32-73` + `:126-138` + `:234-243` |

*Feasibility & Dependencies generated 2026-09-03. Relative complexity LOW/MEDIUM/HIGH/VERY HIGH with dimension breakdown, dependencies, shared-table wiring, and gating — no hour estimates. Ready for Step 5 prioritization.*
