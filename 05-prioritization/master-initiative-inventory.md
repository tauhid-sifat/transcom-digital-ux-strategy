# Master Initiative Inventory — Phase 5 (Step 1)

> **Purpose:** Complete, deduplicated inventory of ALL candidate initiatives. Normalizes 32+ Phase 2 UX audit issues, 15 Phase 3 consolidated opportunities, 8 Phase 4 benchmark NEW opportunities, and Phase 4 benchmark-enhanced patterns into single build-unit register. **No prioritization yet** — classification is FIX / IMPROVEMENT / NEW CAPABILITY only.
> **Sources ingested:** `00-input/sitemap-analysis.md` (167 URLs) · `01-current-state/*` (site-inventory, page-analysis, product-discovery, product-page-variations, user-journeys, ecommerce-capabilities, personalization-current-state, exploration-plan) · `02-ux-audit/issue-register.md:7-46` (32 registered, 40 rows observed) + `executive-summary.md` + module audits · `03-opportunities/opportunity-pool.md:7-245` (15 OPPs) + `cross-review.md:32-73` + `duplicates-and-overlaps.md` + `04-benchmark/pattern-library.md:22-165` (12 problems, 38 variations) + `04-benchmark/applicability-review.md:22-152` (15 OPPs validated/enhanced/questioned + 8 NEW) + `04-benchmark/new-opportunities.md:7-14` + `04-benchmark/competitive-opportunity-map.md` + `04-benchmark/phase-4-summary.md`
> **Date:** 2026-09-03 · **Status:** Step 1 Inventory — not prioritized, not sequenced
> **Method:** Deduplicate by root-cause capability (cross-review Clusters C1–C9, `03-opportunities/cross-review.md:126-138`), not by label. A FIX repairs broken / gated / feedback-missing hygiene where VERIFIED control exists but fails. IMPROVEMENT evolves an existing but thin/inconsistent capability. NEW CAPABILITY introduces net-new (NOT OBSERVED in `01-current-state/ecommerce-capabilities.md`).

---

## Classification Key

| Type | Definition | Example |
|------|-----------|---------|
| **FIX** | Existing experience creates friction/failure — broken link, gated disclosure, missing feedback, implausible copy, dead-end. Shipping restores expected baseline. | NAV-01 `/undefined`, FILTER-01 chips, FEEDBACK-01 toast |
| **IMPROVEMENT** | Existing capability present but thin, generic, inconsistent, or not scaled — needs evolution, not repair. | PDP-01 generic gallery → zoom/video, TRUST-01 homepage-only → PDP-anchored, DISC-03 single Related card |
| **NEW CAPABILITY** | Meaningful capability does not exist (NOT OBSERVED in Phase 1). Introduces new data, UI system, or service. | OPP-01 pincode estimator, OPP-02 resumption, NEW-01 authenticity lockup |

---

## Counts

| Source | Raw | After dedup |
|--------|-----|-------------|
| Phase 2 UX Issues (`02-ux-audit/issue-register.md`) | 40 rows listed (32 registered) | — |
| Phase 3 Consolidated Opportunities (`03-opportunities/opportunity-pool.md`) | 15 OPPs (38 raw → 15) | — |
| Phase 4 NEW Opportunities (`04-benchmark/new-opportunities.md` + `applicability-review.md:142-151`) | 8 NEW | — |
| **Normalized initiatives (this file)** | **55 candidate rows** | **34 initiatives** |
| FIX | — | **13** |
| IMPROVEMENT | — | **6** |
| NEW CAPABILITY | — | **15** |

> 34 hits target ~30-35. Over-coverage vs 32 registered reflects inclusion of 8 additional issue rows observed in register file + full NEW set, collapsed per `cross-review.md:74` fate table (28 merged → 8 clusters, 2 removed as remediation tails re-elevated as FIXes here, 1 generic tail removed).

---

## Summary Table — All 34 Initiatives

| ID | Initiative Name | Type | Source Phase(s) | Primary Evidence | Severity / Maturity |
|----|-----------------|------|-----------------|------------------|---------------------|
| **INV-01** | Repair Broken Browse Paths (`/undefined` See All) | FIX | P2: NAV-01 P0 | `02-ux-audit/issue-register.md:7` · `01-current-state/page-analysis.md:56-57` | P0 |
| **INV-02** | IA & URL Hygiene — Flat PDP Namespace, Orphan `/tv-av`, Trailing-Hyphen Slugs | FIX | P2: IA-01 P1, IA-02 P2, IA-04 P2 | `00-input/sitemap-analysis.md:27` · `02-ux-audit/issue-register.md:8-11` | P1/P2 |
| **INV-03** | Canonical Strategy — Brand PLP vs Search Brand Filter Duplication | FIX | P2: NAV-02 P2 | `02-ux-audit/issue-register.md:12` · `01-current-state/site-inventory.md:25` | P2 |
| **INV-04** | SEO Architecture — Move Buying-Guide Wall Below Fold, Buying-Guide Hub | FIX | P2: IA-03 P1 · P4 ENHANCED OPP-04 | `02-ux-audit/issue-register.md:10` · `01-current-state/page-analysis.md:90-91` · `04-benchmark/applicability-review.md:64-66` | P1 · STANDARD (Currys/Coolblue) |
| **INV-05** | Category Taxonomy Consistency (Dishwashers Tile vs Sitemap) | FIX | P2: DISC-04 P2 | `02-ux-audit/issue-register.md:16` · `01-current-state/page-analysis.md:47` | P2 |
| **INV-06** | Homepage Prioritization & Performance Budget | IMPROVEMENT | P2: DISC-01 P1, MOBILE-01 P2 | `02-ux-audit/issue-register.md:13,46` · `01-current-state/page-analysis.md:48-54` · `01-current-state/product-page-variations.md:49` | P1 |
| **INV-07** | Intelligent Search — Autocomplete + Recent Searches + Scented Placeholder | NEW CAPABILITY (Stage 1 FIX hygiene) | P2: SEARCH-01 P1, SEARCH-02 P3 · P3: OPP-07 · P4: VALIDATED | `02-ux-audit/issue-register.md:17-18` · `03-opportunities/opportunity-pool.md:101-116` · `04-benchmark/pattern-library.md:99-102` Problem 7 | STANDARD |
| **INV-08** | Zero-Result Recovery — Did-You-Mean + Typo Tolerance + Facet Relaxation | NEW CAPABILITY | P2: SEARCH-03 P2 · P3: OPP-08 · P4: VALIDATED | `02-ux-audit/issue-register.md:19` · `03-opportunities/opportunity-pool.md:117-132` · `04-benchmark/pattern-library.md:102-103` | STANDARD/EMERGING |
| **INV-09** | Active Filter Feedback — Chips, Summary, Counts, Clear-All | FIX | P2: FILTER-01 P1 | `02-ux-audit/issue-register.md:20` · `04-benchmark/pattern-library.md:134` (excluded tail reinstated as FIX) · `03-opportunities/cross-review.md:67` | P1 · STANDARD |
| **INV-10** | Sort Clarity + Pagination Model | FIX | P2: SORT-01 P1, SORT-02 P2 | `02-ux-audit/issue-register.md:24-25` · `01-current-state/page-analysis.md:84-85` | P1/P2 |
| **INV-11** | Facet Taxonomy Hygiene — Empty Customer Review, Dual Price Controls, Screen vs Display Size | FIX | P2: FILTER-02 P2, FILTER-03 P2, FILTER-04 P3 | `02-ux-audit/issue-register.md:21-23` · `01-current-state/product-discovery.md:74-83` | P2/P3 |
| **INV-12** | Rich Media Inspection — Zoom, Pinch, Video, 360°, Dimension Overlay | IMPROVEMENT | P2: PDP-01 P1 · P3: OPP-10 · P4: VALIDATED | `02-ux-audit/issue-register.md:26` · `03-opportunities/opportunity-pool.md:150-163` · `04-benchmark/pattern-library.md:60-67` Problem 4 | STANDARD (zoom) |
| **INV-13** | Delivery & Serviceability Estimator — Pincode-First Landed Cost + Fast Badge | NEW CAPABILITY | P2: PDP-02 P1 · P3: OPP-01 · P4: ENHANCED | `02-ux-audit/issue-register.md:27` · `03-opportunities/opportunity-pool.md:7-20` · `04-benchmark/applicability-review.md:46-49` · `04-benchmark/pattern-library.md:26-31` Problem 1 | STANDARD SA / EMERGING BD |
| **INV-14** | True Cost & EMI Planner — Ownership Row + Tenure Picker + Eligibility Verdict | NEW CAPABILITY | P2: PDP-06 P2, CONSISTENCY-01 P3 · P3: OPP-09 · P4: ENHANCED | `02-ux-audit/issue-register.md:31,44` · `03-opportunities/opportunity-pool.md:136-148` · `04-benchmark/applicability-review.md:94-98` · `04-benchmark/pattern-library.md:72-80` Problem 5 | EMERGING → DIFFERENTIATOR |
| **INV-15** | Spec Jargon Decoder & Energy Label Translator + Warranty Legend | NEW CAPABILITY | P2: PDP-04 P2, PDP-05 P2 · P3: OPP-11 · P4: VALIDATED | `02-ux-audit/issue-register.md:29-30` · `03-opportunities/opportunity-pool.md:166-180` · `04-benchmark/pattern-library.md:86-92` Problem 6 | EMERGING |
| **INV-16** | Installation Feasibility Checker — Pass/Fail Verdict (Content Gate) | NEW CAPABILITY | P2: PDP-03 P1 · P3: OPP-12 Gate1 · P4: ENHANCED | `02-ux-audit/issue-register.md:28` · `03-opportunities/opportunity-pool.md:182-196` · `04-benchmark/pattern-library.md:132-137` Problem 10 | DIFFERENTIATOR |
| **INV-17** | Variant & Family Navigator — Sibling Chips with Delta & Stock | NEW CAPABILITY | P2: PDP-08 P2 · P3: OPP-13 · P4: VALIDATED | `02-ux-audit/issue-register.md:33` · `03-opportunities/opportunity-pool.md:199-213` · `04-benchmark/pattern-library.md:119-128` Problem 9 | STANDARD |
| **INV-18** | Warranty Repair & Trust Claims Propagation to PDP/Cart | FIX | P2: PDP-05 P2, TRUST-01 P2 | `02-ux-audit/issue-register.md:30,35` · `01-current-state/page-analysis.md:34` · `01-current-state/product-page-variations.md:61` | P2 |
| **INV-19** | PDP CTA Hierarchy — Deduplicate Add To Cart | FIX | P2: PDP-09 P3 | `02-ux-audit/issue-register.md:34` · `01-current-state/page-analysis.md:126-128` | P3 |
| **INV-20** | Social Proof Pipeline — Ratings, Review Count, On-Card Badges, Customer Review Facet, Q&A | NEW CAPABILITY | P2: PDP-07 P1, FILTER-02 P2 · P3: OPP-14 · P4: ENHANCED | `02-ux-audit/issue-register.md:32,21` · `03-opportunities/opportunity-pool.md:216-231` · `04-benchmark/applicability-review.md:124-126` · `04-benchmark/pattern-library.md:87-90` Problem 6 | STANDARD |
| **INV-21** | Authenticity / Authorized-Retailer Badging at Price Context | NEW CAPABILITY | P4: NEW-01 | `04-benchmark/new-opportunities.md:7` · `04-benchmark/applicability-review.md:142-144` · `00-input/sitemap-analysis.md:26` (13 brand PLPs) | STANDARD BD |
| **INV-22** | Browse Resumption — Recently Viewed Rail + Continue Shopping Deep-Link | NEW CAPABILITY | P2: DISC-02 P1 · P3: OPP-02 · P4: VALIDATED | `02-ux-audit/issue-register.md:14` · `03-opportunities/opportunity-pool.md:21-36` · `04-benchmark/pattern-library.md:108-116` Problem 8 | STANDARD |
| **INV-23** | Smart Compare Workspace — Persistent, Auto-Populated, Decisive-Attribute & Total-Cost Aware | NEW CAPABILITY | P2: INTERACTION-01 P1, DISC-03 P2 · P3: OPP-03 · P4: VALIDATED | `02-ux-audit/issue-register.md:41,15` · `03-opportunities/opportunity-pool.md:37-52` · `04-benchmark/pattern-library.md:47-56` Problem 3 | STANDARD / DIFFERENTIATOR |
| **INV-24** | Guided Selling Framework — Need → Constraints → Budget Finder (AC, Fridge, TV, Washer, Kitchen) | NEW CAPABILITY | P2: PDP-03 P1, IA-03 · P3: OPP-04 · P4: ENHANCED | `03-opportunities/opportunity-pool.md:54-68` · `04-benchmark/applicability-review.md:62-67` · `04-benchmark/pattern-library.md:34-44` Problem 2 | DIFFERENTIATOR |
| **INV-25** | Complete-the-Setup — Bundles, FBT & Consumable Attach (Pre-Add + Cart Grouping) | NEW CAPABILITY | P3: OPP-05 · P4: VALIDATED | `03-opportunities/opportunity-pool.md:70-84` · `01-current-state/product-page-variations.md:66-67` · `04-benchmark/pattern-library.md:143-152` Problem 11 | EMERGING |
| **INV-26** | Plural Payment Row — COD + bKash/Nagad + Card-on-Delivery + Online/EMI (District-Aware) | NEW CAPABILITY | P2: CHECKOUT-01 P1 · P4: NEW-03 | `04-benchmark/new-opportunities.md:9` · `04-benchmark/applicability-review.md:144-146` · `01-current-state/page-analysis.md:34` | STANDARD BD |
| **INV-27** | Cart Drawer + Checkout Transparency — Landed-Cost Breakdown, Stepper, Mini-Cart, Empty-State Recovery | FIX/NEW* | P2: CART-01 P1, CART-02 P2, CHECKOUT-01 P1, FEEDBACK-01 P1 · P4: NEW-06 | `02-ux-audit/issue-register.md:36-38,42` · `04-benchmark/new-opportunities.md:12` · `04-benchmark/pattern-library.md:164` Problem 12 | STANDARD |
| **INV-28** | Open-Box Delivery + OTP Doorstep Verification | NEW CAPABILITY | P4: NEW-02 | `04-benchmark/new-opportunities.md:8` · `04-benchmark/applicability-review.md:145` · `01-current-state/ecommerce-capabilities.md:42-44` | STANDARD India / EMERGING BD |
| **INV-29** | Conversational Care — WhatsApp/Messenger Human Agent + PDP Share Deep-Link | NEW CAPABILITY | P4: NEW-04 | `04-benchmark/new-opportunities.md:10` · `01-current-state/page-analysis.md:14` (Need help? Click Here ``) | STANDARD social / EMERGING manager |
| **INV-30** | Hotline-Sticky Support Spine + Schedule Store Visit Linkage | IMPROVEMENT | P4: NEW-05 | `04-benchmark/new-opportunities.md:11` · `01-current-state/page-analysis.md:18-19` (16212 9AM–9PM) · `01-current-state/page-analysis.md:199-204` Store Locator | STANDARD BD |
| **INV-31** | Post-Action Feedback — Toasts & Persistence Confirmation (Cart/Wishlist/Compare) + Guest Inline Prompt | FIX | P2: FEEDBACK-01 P1, AUTH-02 P2 | `02-ux-audit/issue-register.md:40,42` · `01-current-state/ecommerce-capabilities.md:36-37` · `04-benchmark/pattern-library.md:164` 12D | STANDARD |
| **INV-32** | Authentication Friction & Guest→Auth Continuity (OTP Split-Field, No-Password, History Migration) | FIX | P2: AUTH-01 P2, AUTH-02 P2, DISC-02 | `02-ux-audit/issue-register.md:39-40` · `01-current-state/page-analysis.md:192-195` Login | P2 |
| **INV-33** | Exchange & Return Value — 14-Day Badge + Cross-Category AI Diagnostics + Timeline | NEW CAPABILITY | P2: FEEDBACK-02 P2 · P3: OPP-06 (QUESTIONED) · P4: NEW-07 | `02-ux-audit/issue-register.md:43` · `03-opportunities/opportunity-pool.md:86-100` · `04-benchmark/new-opportunities.md:13` · `01-current-state/page-analysis.md:208-212` Exchange | EMERGING BD |
| **INV-34** | Accessibility & Icon System — Labeled Controls, Contrast, Keyboard Order | FIX | P2: ACCESS-01 P2 | `02-ux-audit/issue-register.md:45` · `01-current-state/page-analysis.md:7-14` header icons `  ` | P2 · WCAG |

*INV-27 is FIX (repairs CHECKOUT-01/CART-01/FEEDBACK-01 dead-ends) + NEW (introduces drawer/stepper system). Classified FIX for triage to unblock P0, with NEW build note.

---

## Detailed Initiatives

### INV-01 — Repair Broken Browse Paths (`/undefined` See All)
- **Type:** FIX
- **Source Phase(s):** Phase 2 — `02-ux-audit/issue-register.md:7` NAV-01 P0 HIGH
- **Related Evidence:** `01-current-state/page-analysis.md:56-57` “See All links … resolve to `/undefined` — VERIFIED” (5+ occurrences homepage) · `01-current-state/site-inventory.md:77` homepage “All Products See All→ `/undefined` broken” · `01-current-state/page-analysis.md:77` Brand PLP `/samsung` → `/samsung/undefined` repeated 4× · `00-input/sitemap-analysis.md:77` missing `/tv-av` root fragility · `02-ux-audit/usability-issues.md:7-32` hydration timing note
- **User Problem:** Primary discovery CTA dead-ends — user clicks category intent (Electric Kettles, Microwave, Washing Machine, etc.) and lands on 404/`/undefined`. Journey abandoned before PLP metrics begin.
- **Affected Journey:** Journey B/C (browse with category intent), Journey A via homepage entry, Brand PLP journey
- **Affected Page(s):** Homepage ` / ` (7+ feature sections) · Brand PLP `/samsung` (brand sub-sections) · All category teaser modules
- **Current State:** Client hydration produces empty slug → href `/undefined`. Second BrowserOS check returned `undef 0` masked initial paint but Phase 1 snapshot authoritative. No CI link check.
- **Proposed Direction:** Audit slug-builder hydration fallback; enforce redirect/guard for empty slug; add automated link integrity check in CI; map each See All to correct L1/L2 category PLP (`/air-conditioner`, `/refrigerators/no-frost/side-by-side`, etc.). P0 blocking every downstream OPP.

### INV-02 — IA & URL Hygiene — Flat PDP Namespace, Orphan `/tv-av`, Trailing-Hyphen Slugs
- **Type:** FIX
- **Source Phase(s):** Phase 2 — IA-01 P1 HIGH `02-ux-audit/issue-register.md:8` · IA-02 P2 `issue-register.md:9` · IA-04 P2 `issue-register.md:11`
- **Related Evidence:** `00-input/sitemap-analysis.md:27` 101 PDPs flat at root `/{brand}-{descriptor}-{model}` vs nested `/{category}/{product}` · `00-input/sitemap-analysis.md:74-77` missing `/tv-av` root with children `/tv-av/television`, `/tv-av/soundbar` orphaned · `00-input/sitemap-analysis.md:132-134` 4 trailing-hyphen slugs `pureit-classic-23l-`, `samsung-65-qn85c-`, etc. · `01-current-state/site-inventory.md:112-113` flat namespace verified
- **User Problem:** Users cannot infer category from URL; back navigation and mental model broken; breadcrumb parent not indexed; shares/bookmarks risk 404 on truncated slugs; crawl waste.
- **Affected Journey:** All journeys that traverse PDP ↔ category; SEO crawl; share/bookmark
- **Affected Page(s):** All 101 PDPs · Category hierarchy L1–L4 · Sitemap `sitemap.xml` loc entries
- **Current State:** All PDPs resolve at host root; `/tv-av` not indexed; 4 slugs end with `-` suggesting export artifact.
- **Proposed Direction:** Sitemap hygiene: canonical cleanup for trailing-hyphen (301 without hyphen), add `/tv-av` root page, decide on hierarchical PDP URL vs flat+canonical — at minimum surface family context on PDP (INV-17) to compensate for flat URL. Do not block P0 browse before fixing INV-01 but schedule before SEO-guidance moves.

### INV-03 — Canonical Strategy — Brand PLP vs Search Brand Filter Duplication
- **Type:** FIX
- **Source Phase(s):** Phase 2 — NAV-02 P2 HIGH `02-ux-audit/issue-register.md:12`
- **Related Evidence:** `00-input/sitemap-analysis.md:26` 13 brand slugs at root `/samsung` etc. vs `00-input/sitemap-analysis.md:28` single search `search?Brand=samsung` indexed · `01-current-state/site-inventory.md:27` brand listing pages · `01-current-state/product-discovery.md:20` search PLP same chrome as category · `04-benchmark/phase-4-summary.md:162` M-07 flagged
- **User Problem:** Two URL patterns serve identical brand-filtered product sets — users encounter duplicate paths, uncertainty which is authoritative; SEO duplicate content without canonical.
- **Affected Journey:** Journey A (brand-aware search), SEO entry
- **Affected Page(s):** Brand PLPs (`/samsung`, `/daikin`, etc.) · Search `/search?Brand=…`
- **Current State:** Both patterns indexed; no canonical distinction observed.
- **Proposed Direction:** Canonicalize brand PLP as authoritative for brand-browse, search as filtered view with `rel=canonical` to brand PLP when Brand-only; distinct title/H1; wire to variant graph (INV-17) to give brand PLP family value search cannot.

### INV-04 — SEO Architecture — Move Buying-Guide Wall Below Fold, Buying-Guide Hub
- **Type:** FIX
- **Source Phase(s):** Phase 2 — IA-03 P1 HIGH `02-ux-audit/issue-register.md:10` · Phase 4 — ENHANCED OPP-04 wrapper `04-benchmark/applicability-review.md:64-67`
- **Related Evidence:** `01-current-state/page-analysis.md:90-91` SEO blocks 1,500+ words on L1/L2 (`/air-conditioner`, `/refrigerators`) push grid below fold — VERIFIED · `03-opportunities/opportunity-pool.md:54-68` OPP-04 IA-03 cluster · `04-benchmark/pattern-library.md:42-44` Problem 2D `/buying-guides/{category}` hub + `Not sure? 30-sec guide` CTA per Currys/Coolblue · `04-benchmark/phase-4-summary.md:162` M-02
- **User Problem:** Product discovery delayed; users must scroll past long-form SEO to reach filters/products; SEO vs discovery compete as stacks not layers.
- **Affected Journey:** Journey B/C (category browse) — highest friction cluster `02-ux-audit/executive-summary.md:50`
- **Affected Page(s):** All top-level category PLPs L1/L2 (AC, Refrigerators, Washing Machine, Home & Kitchen)
- **Current State:** Generic buying-guide prose above grid serves SEO equity at cost of discovery.
- **Proposed Direction:** Preserve SEO equity but move long-form below pagination; grid/filters stay above fold; create `/buying-guides/{category}` hub that wizard (INV-24) CTA links to. No deletion — re-layering. Feeds INV-24 finders for explainability.

### INV-05 — Category Taxonomy Consistency (Dishwashers Tile vs Sitemap)
- **Type:** FIX
- **Source Phase(s):** Phase 2 — DISC-04 P2 HIGH `02-ux-audit/issue-register.md:16`
- **Related Evidence:** `01-current-state/page-analysis.md:47` Shop By Category 6 cards include `Dishwashers` · `00-input/sitemap-analysis.md:20-26` sitemap taxonomy has no `/dishwashers` top-level; Dishwashers absent from 5 top-level slugs
- **User Problem:** Users seeking Dishwashers see tile but tile not in navigable taxonomy — confusion, expectation violation.
- **Affected Journey:** Journey B entry via homepage
- **Affected Page(s):** Homepage Shop By Category grid
- **Current State:** Marketing tile vs IA mismatch.
- **Proposed Direction:** Align tile set to sitemap IA or add missing category route; audit tile→PLP mapping (links to INV-01 repair). Low effort consistency fix.

### INV-06 — Homepage Prioritization & Performance Budget
- **Type:** IMPROVEMENT
- **Source Phase(s):** Phase 2 — DISC-01 P1 HIGH `02-ux-audit/issue-register.md:13` · MOBILE-01 P2 `issue-register.md:46` · Phase 4 — OPP-15 QUESTIONED deferred `04-benchmark/applicability-review.md:128-135`
- **Related Evidence:** `01-current-state/page-analysis.md:48-54` 7+ serialized mini-grids (Electric Kettles, Microwave, Washer, AC, TV …) no prioritization — VERIFIED · `01-current-state/product-page-variations.md:49` 68 DOM images on Mixer PDP · `01-current-state/page-analysis.md:48` 68+ images homepage+PLP weight · `03-opportunities/cross-review.md:178` M-04 mobile weight
- **User Problem:** Cognitive overload; slow decision on where to start; high scroll cost; low-bandwidth mobile slow load and scroll fatigue (Bangladesh mobile-first).
- **Affected Journey:** Journey B/C entry; mobile low-bandwidth
- **Affected Page(s):** Homepage ` / ` · All PLPs with `Latest Products` + heavy grid
- **Current State:** Generic curation (`Best Deals`, `Featured Product`, `Best Selling`) not prioritized; 11 See All + multiple carousels heavy.
- **Proposed Direction:** Do NOT build full affinity reorder (INV-34 vs OPP-15 deferred). Instead triage: single hero + Shop By Category + 2 prioritized category rows based on sitemap breadth (AC/Fridge/TV), defer rest below fold; implement image lazy-load + budgeted carousel count; A/B cut vs add. Prepares P0 hygiene before any affinity experiment.

### INV-07 — Intelligent Search — Autocomplete + Recent Searches + Scented Placeholder
- **Type:** NEW CAPABILITY (Stage 1 hygiene; Stage 2 personalization)
- **Source Phase(s):** Phase 2 — SEARCH-01 P1 MEDIUM `02-ux-audit/issue-register.md:17` · SEARCH-02 P3 `issue-register.md:18` · Phase 3 — OPP-07 `03-opportunities/opportunity-pool.md:101-116` · Phase 4 — VALIDATED Stage1 `04-benchmark/applicability-review.md:83-87`
- **Related Evidence:** `01-current-state/ecommerce-capabilities.md:12-13` header input VERIFIED, suggestions NOT FULLY VERIFIED · `01-current-state/product-discovery.md:40-43` typing `AC/samsun tv` timeout no dropdown captured · `01-current-state/page-analysis.md:9` placeholder `Search Here` generic · `04-benchmark/pattern-library.md:99-102` Problem 7A debounced 150–200ms, rows Product/Brand/Category/SKU-exact, Recent chips 6, placeholder `Try FTKL12TV16WD or Samsung TV 55"` · `04-benchmark/phase-4-summary.md:50` STANDARD
- **User Problem:** “Know exactly what I want” (Journey A: `FTKL12TV16WD`, `H55P7UX`) has no fast-path; placeholder gives no scent; recent searches not recalled → must submit to see results.
- **Affected Journey:** Journey A primary; Journey B/C entry
- **Affected Page(s):** Header `Search Here` on all pages (all templates share shell `01-current-state/page-analysis.md:7-15`)
- **Current State:** Input exists; suggestion index not verifiably rendering; placeholder generic; no recent chips.
- **Proposed Direction:** Stage 1 (P0): debounced typeahead after 2 chars, SKU-boost when query has 3+ alphanumerics (photographed-code buyers), rows Product (+price/stock+thumb) / Brand / Category, header `Recent: samsung 55\" | daikin 1 ton` from `localStorage searchHistory` cap 6, placeholder with model+category example. Stage 2 (P2 after INV-22): affinity-biased ranking (viewed Samsung 55" → Samsung ranked up). Validate dropdown vs index gap before building.

### INV-08 — Zero-Result Recovery — Did-You-Mean + Typo Tolerance + Facet Relaxation
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 2 — SEARCH-03 P2 `02-ux-audit/issue-register.md:19` · Phase 3 — OPP-08 `03-opportunities/opportunity-pool.md:117-132` · Phase 4 — VALIDATED `04-benchmark/applicability-review.md:88-92`
- **Related Evidence:** `01-current-state/ecommerce-capabilities.md:15` zero-result NOT TESTED · `04-benchmark/pattern-library.md:102-103` Problem 7B/C fuzzy 1–2, `Did you mean`, `Remove Brand →12` count preview, Bangla-English symmetry · `03-opportunities/cross-review.md:138` zero-result recovery distinct from suggestions
- **User Problem:** Typos for alphanumeric codes (`FTLK↔FTKL`, `H55P7UX` digit) or Bangla-English mixed queries dead-end; overly narrow filter combos trap.
- **Affected Journey:** Journey A failure path; Journey B narrow filter
- **Affected Page(s):** Search PLP (`/search`) zero-result state · Filtered PLPs with zero results (PLP empty grid `01-current-state/page-analysis.md:90`)
- **Current State:** No recovery template observed; zero-result behavior unknown.
- **Proposed Direction:** Fuzzy index (edit distance 1–2, QWERTY-adjacent `L↔K`, Bangla digit map, synonym `inverter=invator`), zero-result template: `No exact for "FTLK12" — did you mean "FTKL12"? 3 results` + `Try removing: Brand Samsung (→12)` + `Related: daikin 1.5 ton` + advisor CTA `Try AC Finder` (→ INV-24). Short build; brackets OPP-07 submission failure side.

### INV-09 — Active Filter Feedback — Chips, Summary, Counts, Clear-All
- **Type:** FIX
- **Source Phase(s):** Phase 2 — FILTER-01 P1 MEDIUM `02-ux-audit/issue-register.md:20` · Phase 3 — removed as opportunity tail `03-opportunities/cross-review.md:67` ECS-07, reinstated as remediation P1
- **Related Evidence:** `01-current-state/product-discovery.md:74-88` Price/Brand/Screen facets VERIFIED, no summarized chip row `product-discovery.md:84-88` · `01-current-state/page-analysis.md:75-82` sidebar checkboxes + counts but selected state beyond per-row highlight, no chip row · `02-ux-audit/usability-issues.md:35-58` plpSort verification no `filterCount` chips
- **User Problem:** Users cannot see at a glance what is applied; removal requires hunting sidebar; memory load for multi-facet narrowing (TV: brand+size+price).
- **Affected Journey:** Journey B (filter-heavy), Journey D comparison prep
- **Affected Page(s):** All PLPs (category L1-L4, Brand PLP `/samsung`, Search PLP `/search?Brand=…`)
- **Current State:** Filters function but feedback missing — violates Nielsen visibility of system status.
- **Proposed Direction:** Persistent chip row + count above grid (`3 filters: Samsung × 55" × 1–2L`), per-chip remove, `Clear all`. Suppressed when no filter. Shared with INV-10 sort.

### INV-10 — Sort Clarity + Pagination Model
- **Type:** FIX
- **Source Phase(s):** Phase 2 — SORT-01 P1 HIGH `02-ux-audit/issue-register.md:24` · SORT-02 P2 `issue-register.md:25`
- **Related Evidence:** `01-current-state/page-analysis.md:84-86` `Select Sort Option` dropdown + `Show 12` + `<of 1>` + numeric `1` — VERIFIED · `02-ux-audit/usability-issues.md:60-84` evaluation `sortOptions: []`, `selectText: not found` · `01-current-state/product-discovery.md:89-94` options not enumerated — NOT TESTED
- **User Problem:** Users cannot anticipate sorting; sort affordance looks like placeholder; pagination model (`Show 12 <of 1> 1`) obscures total results and page-size change.
- **Affected Journey:** Journey B shortlist; price-sensitive EMI buyers needing price sort
- **Affected Page(s):** All PLPs + Campaign hub `/campaigns`
- **Current State:** Control renders placeholder text; options not enumerated in snapshots.
- **Proposed Direction:** Replace placeholder with 4–5 canonical sorts (Relevance, Price low→high, Price high→low, Discount, Newest) with sensible default; pagination as `Showing 1–12 of 44` + selector `Show 12/24/48` + prev/next affordance.

### INV-11 — Facet Taxonomy Hygiene — Empty Customer Review, Dual Price Controls, Screen vs Display Size
- **Type:** FIX
- **Source Phase(s):** Phase 2 — FILTER-02 P2 HIGH `02-ux-audit/issue-register.md:21` · FILTER-03 P2 `issue-register.md:22` · FILTER-04 P3 `issue-register.md:23`
- **Related Evidence:** `01-current-state/product-discovery.md:74-83` filter facets table: Price slider + buckets, Brand counts, `Customer Review` heading present no buckets captured `product-discovery.md:83` · `01-current-state/page-analysis.md:75-81` Smart TV `0 - 10,55,000` dual slider + buckets `0 to 1,00,000` competing · `01-current-state/product-discovery.md:79-80` `Display Size 55"(10)` vs `Screen 32"(2)` duplication on Smart TV
- **User Problem:** Expectations set then violated (empty Customer Review); competing price controls cause decision paralysis; taxonomy duplication lets users miss products classified under sibling facet.
- **Affected Journey:** Journey B filter step
- **Affected Page(s):** PLPs (Smart TV, Dry Irons, all sampled)
- **Current State:** Heading with no buckets; two price controls with identical function; two size dimensions.
- **Proposed Direction:** Single price control (slider with bucket presets, not duplicate); merge Screen → Display Size taxonomy; suppress Customer Review heading until INV-20 pipeline populates (`n≥5`); audit facet→SKU mapping.

### INV-12 — Rich Media Inspection — Zoom, Pinch, Video, 360°, Dimension Overlay & AR
- **Type:** IMPROVEMENT (existing generic gallery → inspection-grade)
- **Source Phase(s):** Phase 2 — PDP-01 P1 HIGH `02-ux-audit/issue-register.md:26` · Phase 3 — OPP-10 `03-opportunities/opportunity-pool.md:150-163` · Phase 4 — VALIDATED `04-benchmark/applicability-review.md:100-104`
- **Related Evidence:** `01-current-state/page-analysis.md:134-135` 4+ generic image containers above title — OBSERVED · `01-current-state/product-page-variations.md:49-51` 68 DOM images on Mixer PDP, Video NOT OBSERVED all samples · `01-current-state/ecommerce-capabilities.md:29-30` Image Gallery OBSERVED placeholders, Video NOT OBSERVED · `04-benchmark/pattern-library.md:60-67` Problem 4 variations 4A (hover/pinch+scrub+count), 4B (functional video 15–25s per template), 4C (360°+dimension+AR) · `04-benchmark/phase-4-summary.md:50` STANDARD zoom since ~2018
- **User Problem:** High-consideration decisions (600L door swing, 65" bezel depth, AC wall piped, washer drum) under-supported by static thumbnails; users cannot inspect fit/finish/features remotely → hesitation.
- **Affected Journey:** All considered-purchase PDP research (AC/Fridge/TV/Washer)
- **Affected Page(s):** All PDPs (101 at root)
- **Current State:** Placeholders, no viewer zoom/player, heavy DOM without inspection value.
- **Proposed Direction:** Phased: hover-zoom desktop + pinch mobile + `1/7` count + scrub (week, no reshoot); functional video per category template (AC wall, TV panel/HDR, washer spin, fridge door swing 15–25s muted lazy-loaded, reuse brand reels); 360° where asset exists; dimension overlay `W×H×D + ventilation gap + door swing` from structured spec shared with INV-16. Suppression: generic for Personal Care.

### INV-13 — Delivery & Serviceability Estimator — Pincode-First Landed Cost + Fast Badge
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 2 — PDP-02 P1 HIGH `02-ux-audit/issue-register.md:27` · Phase 3 — OPP-01 `03-opportunities/opportunity-pool.md:7-20` Cluster C1 · Phase 4 — ENHANCED `04-benchmark/applicability-review.md:46-49`
- **Related Evidence:** `01-current-state/page-analysis.md:125` PDP `Home Delivery Enable your Location` / `Store Pickup Enable your Location` gate VERIFIED all PDPs · `01-current-state/ecommerce-capabilities.md:42-44` delivery preview gated · `01-current-state/personalization-current-state.md:7` location-gated PARTIALLY OBSERVED · `01-current-state/page-analysis.md:199-204` Store Locator List/Map + `Schedule your visit` store feed · `04-benchmark/pattern-library.md:26-31` Problem 1 (1A pincode text, 1B landed-cost truth row, 1C Fast badge) · `04-benchmark/phase-4-summary.md:50` STANDARD SA
- **User Problem:** At exact price exposure, users cannot answer “can this 600L/1 Ton be delivered to my district, at what fee, when, with free install?” — permission gate hides answer until after commitment; checkout pincode mismatch drop-off.
- **Affected Journey:** Journeys B/C/E (all Tk 50k–1.5L considered); PDP → Cart propagation
- **Affected Page(s):** PDP Options block (Daikin AC, Haier Fridge/TV, etc.) · Cart Order Summary propagation · Store Locator `/store-locator` as pickup alt
- **Current State:** `Enable your Location` permission gate; fee/SLA/timeline gated; trust bar “Free Installation Selective Items” not echoed per SKU.
- **Proposed Direction (ENHANCED):** Single district/area *text* field (not GPS permission — Bangladesh sparse formal pincodes, low trust `regional: Finding 5`) between price and ATC; returns serviceability yes/no + SLA + delivery fee + install flag/fee + nearest store-pickup distance; result persists session (`remember pincode` personalization layer) and propagates to Cart `Subtotal+Delivery+Install→Total` without re-entry; earned `Fast Delivery` PLP badge/filter (earned via fulfillment, not bought) alongside `EMI36`. Shares zone/SLA/install/store table with INV-14/16/20/26/28/30. Suppress low-ticket trimmer `Tk 3k` (`product-page-variations.md:104`).

### INV-14 — True Cost & EMI Planner — Ownership Row + Tenure Picker + Eligibility Verdict
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 2 — PDP-06 P2 MED `02-ux-audit/issue-register.md:31` · CONSISTENCY-01 P3 `issue-register.md:44` · Phase 3 — OPP-09 `03-opportunities/opportunity-pool.md:136-148` Cluster C9 · Phase 4 — ENHANCED `04-benchmark/applicability-review.md:94-98`
- **Related Evidence:** `01-current-state/page-analysis.md:114-117` EMI `EMI From 2633 Tk/month` + `Avail Bank EMI` present on AC/TV/Mixer/Laptop — VERIFIED · `01-current-state/product-page-variations.md:55` Haier 622IBG Fridge **no EMI line** vs others — absent without explanation · `01-current-state/page-analysis.md:87` PLP badge `EMI36` vs text divergence · `04-benchmark/pattern-library.md:72-80` Problem 5 (5A tenure picker, 5B single row `Upfront+Delivery+Install+Energy→EMI/mo`, 5C eligibility verdict) · `04-benchmark/applicability-review.md:96-98` Pickaboo 32 banks BDT 5k / Daraz 10k + 7–10d offline form truth, `EMI not available for this SKU → see EMI Bank List`
- **User Problem:** Sticker illusion: EMI eligibility inconsistent with silent absence; energy hidden as `EER 3.15` token; install fee gated → monthly affordability unknown at decision moment.
- **Affected Journey:** Journeys B/C/E at PDP decision + Cart total hesitation
- **Affected Page(s):** PDP pricing block · PLP cards (badge) · Cart price breakdown
- **Current State:** EMI shown where available; absent as silence; energy/install not combined; inconsistent tone.
- **Proposed Direction (ENHANCED):** Single ownership row beneath sale price: `Upfront × + Delivery Tk0 + Energy ~Tk/mo (1yr/5yr) → EMI from Tk/month × tenure @ bank` with tenure picker 3/6/12/24/36 + tariff/running-hours slider (formula `annual kWh × unit rate` `pattern-library.md:90-92`); eligibility verdict where EMI unavailable with reason (threshold, bank exclusion, Dhaka-only); BDT 5k threshold suppress per `regional Finding 3`; cart inheritance as grouped breakdown. Offline form latency disclosed `blocked amount → signed form 3d → bank converts 5–10d` (Pickaboo/Daraz).

### INV-15 — Spec Jargon Decoder & Energy Label Translator + Warranty Legend
- **Type:** NEW CAPABILITY (content-only, prerequisite)
- **Source Phase(s):** Phase 2 — PDP-04 P2 `02-ux-audit/issue-register.md:29` · PDP-05 P2 `issue-register.md:30` · Phase 3 — OPP-11 `03-opportunities/opportunity-pool.md:166-180` · Phase 4 — VALIDATED `04-benchmark/applicability-review.md:105-109`
- **Related Evidence:** `01-current-state/product-page-variations.md:57-61` Spec click surfaced rows `Refrigerant R32 / EER 3.15 / Applicable For 120 sq ft` but no glossary; `product-page-variations.md:57` Mixer omits `Feature` tab hierarchy inconsistency · `01-current-state/product-page-variations.md:61` Warranty adapted per appliance `Service-24M/Parts-24M/Compressor-120M` vs `Motor-300M (≈25yr)` vs `Special Component-0M` · `04-benchmark/pattern-library.md:86-92` Problem 6C tap-any-term drawer `EER 3.15 = 1.1kW → ~Tk Y/mo @8h/day` + energy A–G+QR fiche
- **User Problem:** Spec tab reveals `EER/R32/HQLED/Dolby Vision/Twin inverter/Coanda` without explainer; warranty legend opaque; users leave to Google.
- **Affected Journey:** All PDP research moments; unlocks INV-14/16/24 literacy
- **Affected Page(s):** PDP tabs `Specification` / `Feature` / Warranty block
- **Current State:** Tabs present but content only after click; glossary absent.
- **Proposed Direction:** Inline glossary CMS 25–40 terms category-scoped; tap underlined term → drawer/tooltip with cost math shared with INV-14 (`watts×hours/1000×tariff`); warranty legend `Special Component = Compressor/Panel/Motor per category`; energy label visual. Content-only, ships before finders/planner.

### INV-16 — Installation Feasibility Checker — Pass/Fail Verdict (Content Gate)
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 2 — PDP-03 P1 HIGH `02-ux-audit/issue-register.md:28` · Phase 3 — OPP-12 Gate1 `03-opportunities/opportunity-pool.md:182-196` (EDS-07+FEA-06 layers) · Phase 4 — ENHANCED `04-benchmark/applicability-review.md:110-117`
- **Related Evidence:** `01-current-state/product-page-variations.md:60` install line NOT OBSERVED · `01-current-state/ecommerce-capabilities.md:45` `Free Installation Selective Items` homepage trust bar `page-analysis.md:34` not echoed PDP · `01-current-state/page-analysis.md:126-128` no install line in PDP Options · `04-benchmark/pattern-library.md:132-137` Problem 10A per-SKU checklist (AC: outdoor wall/bracket/drain/socket 1.5m; Fridge: ventilation 1" gap + floor + door swing 90° + hinge 5cm; Washer: inlet/drain + floor level) · `03-opportunities/cross-review.md:174-176` checker as content prerequisite before booking
- **User Problem:** No feasibility signal before ordering large appliance — buyer risks ordering AC without outdoor wall/drain, 600L without ventilation gap/door swing, washer without inlet/drain.
- **Affected Journey:** AC/Fridge/Washer post-add pre-fulfilment (PDP → Cart → post-purchase)
- **Affected Page(s):** PDP `Installation` row beneath Warranty · Cart as fee line
- **Current State:** PDP shows `Home Delivery/Store Pickup Enable your Location` only; install fee vague.
- **Proposed Direction (Gate1):** Per-SKU feasibility toggles → verdict `✓ Feasible — Add to Cart` / `⚠ Requires bracket Tk 2,500 — order bundle` with fee table `Free/Paid + Tk X` shares table with INV-13/14; dimension spec normalization `W×H×D+gap+swing` shares source with INV-12. No calendar in this gate; prerequisite for INV-12 overlay reuse and INV-25 mandatory-kit.

### INV-17 — Variant & Family Navigator — Sibling Chips with Delta & Stock
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 2 — PDP-08 P2 HIGH `02-ux-audit/issue-register.md:33` · Phase 3 — OPP-13 `03-opportunities/opportunity-pool.md:199-213` · Phase 4 — VALIDATED `04-benchmark/applicability-review.md:118-122`
- **Related Evidence:** `01-current-state/product-page-variations.md:52` only AC shows `Choose Ton 1 / 1.5 Ton` — VERIFIED · `01-current-state/page-analysis.md:86` PLP `Display Size 55"(10) 43"(7) 65"(7)` proves families exist but PDP has no switcher · `00-input/sitemap-analysis.md:27` flat PDP namespace severs hierarchy — family compensates · `04-benchmark/pattern-library.md:119-128` Problem 9 Apple/Samsung `43/55/65 +delta` chips
- **User Problem:** TVs filtered by Display Size on PLP but 55" PDP has no jump to 65" sibling; fridge/washer families invisible on PDP — must return to PLP to explore vault.
- **Affected Journey:** PDP variant exploration (all families)
- **Affected Page(s):** PDP beneath title/above ATC
- **Current State:** Single variant control (AC tonnage) only; others zero.
- **Proposed Direction:** Product family graph `model_root → variants by tonnage/litres/display size/kg`; chips with price delta + stock badge `65" +Tk18,000 In stock | 75" Currently Unavailable`. Navigation PDP→sibling PDP (new URL) preserves `?familyRef` for Compare/Recently Viewed; price/availability live; placed above INV-13 estimator so size change re-validates delivery/energy/EMI.

### INV-18 — Warranty Repair & Trust Claims Propagation to PDP/Cart
- **Type:** FIX
- **Source Phase(s):** Phase 2 — PDP-05 P2 HIGH `02-ux-audit/issue-register.md:30` · TRUST-01 P2 `issue-register.md:35`
- **Related Evidence:** `01-current-state/product-page-variations.md:61` Warranty lines `Service-24M/Parts-24M/Compressor-120M` vs `Motor-300M` vs `Parts-0M / Special-60M` implausible nomenclature · `01-current-state/page-analysis.md:34` Homepage trust bar `Free Installation / Original Product Guaranteed / Exchange Program / Secure Payment` not echoed on PDP/Cart · `02-ux-audit/executability.md` vs `page-analysis.md:7-34` header/terms gaps
- **User Problem:** Warranty confidence eroded; confidence built at entry dissipates at consideration/checkout.
- **Affected Journey:** All considered purchases — price-to-Add transition
- **Affected Page(s):** PDP warranty block · PDP trust row near price · Cart trust micro-copy
- **Current State:** Inconsistent `Parts-0M`/`300M` values; trust claims absent where decision happens.
- **Proposed Direction:** Normalize warranty legend per INV-15 (`Special Component` defined per category); surface trust claims at price context: `Free Installation — Free for this SKU` / `Paid — Tk X` + `Original Product Guaranteed` badge paired with INV-21 authenticity; not generic banner but per-SKU truth.

### INV-19 — PDP CTA Hierarchy — Deduplicate Add To Cart
- **Type:** FIX
- **Source Phase(s):** Phase 2 — PDP-09 P3 HIGH `02-ux-audit/issue-register.md:34`
- **Related Evidence:** `01-current-state/page-analysis.md:126-128` `Add To Cart` ×2 (near price + below Options) without role distinction — VERIFIED all in-stock PDPs · `01-current-state/product-page-variations.md:126-129` states table
- **User Problem:** Users unsure which CTA is primary; visual noise; duplicate violates hierarchy.
- **Affected Journey:** PDP → Cart (Journey E)
- **Affected Page(s):** PDP pricing block vs Options block
- **Current State:** Two identical `Add To Cart` buttons.
- **Proposed Direction:** Single primary CTA sticky on scroll + secondary `Add to Compare/Wishlist`; distinguish via region ownership; wire to INV-27 drawer + toast.

### INV-20 — Social Proof Pipeline — Ratings, Review Count, On-Card Badges, Customer Review Facet, Q&A
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 2 — PDP-07 P1 HIGH `02-ux-audit/issue-register.md:32` · FILTER-02 P2 `issue-register.md:21` · Phase 3 — OPP-14 `03-opportunities/opportunity-pool.md:216-231` · Phase 4 — ENHANCED `04-benchmark/applicability-review.md:124-126`
- **Related Evidence:** `01-current-state/ecommerce-capabilities.md:31-33` Review/Rating/Q&A headings exist as tabs but Content NOT OBSERVED — tab labels only `01-current-state/page-analysis.md:131-133` · `01-current-state/product-page-variations.md:62` Review tab present no stars/count · `01-current-state/page-analysis.md:81` `Customer Review` filter heading with no buckets · `04-benchmark/pattern-library.md:87-90` Problem 6B pipeline Collection→Moderation→Aggregation→Badges→Facet; Best Buy `4.6★ 212`, Amazon Verified Purchase · `04-benchmark/phase-4-summary.md:158` ratings alone insufficient post-Evaly — pair with INV-21
- **User Problem:** High-ticket research lacks peer validation; shortlist cannot be biased by social proof; empty Customer Review filter expectation violated.
- **Affected Journey:** Journeys B/C shortlist (PLP), PDP confidence (PDP-07)
- **Affected Page(s):** PDP header badge above fold near price · PLP card `4.6★ (212)` · PDP Review tab · Filter sidebar Customer Review facet
- **Current State:** Tabs exist; no aggregate stars/count/cards visible; facet empty; Q&A not captured.
- **Proposed Direction (ENHANCED):** Pipeline: submission (post-delivery prompt) → moderation → aggregation (rolling avg, suppress `n<5` → `Be first to review — ask Q`) → PDP header badge + PLP card badge (never overlapping `-23.45%` `page-analysis.md:87`) → review facet `★★★★&up (41)` indexed + Q&A with `Verified Purchase` marker; suppressed where thin. Paired with INV-21 two-layer trust.

### INV-21 — Authenticity / Authorized-Retailer Badging at Price Context
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 4 — NEW-01 `04-benchmark/new-opportunities.md:7` · `04-benchmark/applicability-review.md:142-144` (STANDARD BD)
- **Related Evidence:** `01-current-state/ecommerce-capabilities.md:46` warranty line reads as claim not proof · `01-current-state/page-analysis.md:34` homepage `Original Product Guaranteed` not echoed PDP/Cart · `00-input/sitemap-analysis.md:26` 13 brand partnerships (Samsung/Daikin/Haier etc.) · `04-benchmark/pattern-library.md:87-90` Problem 6A DarazMall `Authenticity Guarantee + Mall` (replacement + 3× if fake), Pickaboo `100% genuine 400+ brands`, Bikroy `Verified Badge` (NID/Trade License) — post-Evaly penetration 2–3% barrier `regional Finding 1`
- **User Problem:** Trust dissipates PDP/Cart where Tk 80k+ decision happens; marketplace variance is #1 barrier post-Evaly.
- **Affected Journey:** All considered PDP decisions
- **Affected Page(s):** PDP hero lockup near price + warranty detail sheet · Cart trust row
- **Current State:** Authorization is true (13 authorized brands) but invisible at decision moment.
- **Proposed Direction:** PDP hero `✓ Authorized — Official Warranty` + `Authenticity Guarantee (replacement + 3× if fake)` + flagship/Mall tag + seller identity + warranty detail sheet; reuses partnerships, no backend; companion to INV-20 ratings (two-layer trust per `applicability-review.md:174`).

### INV-22 — Browse Resumption — Recently Viewed Rail + Continue Shopping Deep-Link
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 2 — DISC-02 P1 HIGH `02-ux-audit/issue-register.md:14` · Phase 3 — OPP-02 `03-opportunities/opportunity-pool.md:21-36` Cluster C2 · Phase 4 — VALIDATED `04-benchmark/applicability-review.md:51-54`
- **Related Evidence:** `01-current-state/personalization-current-state.md:9-10` Recently Viewed & Continue Shopping NOT OBSERVED (20+ page reads) · `01-current-state/ecommerce-capabilities.md:55` NOT OBSERVED · `01-current-state/page-analysis.md:159-164` empty cart/wishlist show no history · `04-benchmark/pattern-library.md:108-116` Problem 8 (8A rail 8 items, 8B filter-restore deep-link `Smart TV: Samsung 55"+, 1–2L (14) → Continue`, 8C empty-cart injection) · `03-opportunities/cross-review.md:126-138` C2 merge rationale
- **User Problem:** No trail to resume interrupted research; returning users must rebuild hierarchy from root, re-find last filtered PLP/search (Journey F wholly unserved).
- **Affected Journey:** Journey F (returning), Journeys B/C multi-session, empty-cart recovery
- **Affected Page(s):** Homepage below hero · PLP sidebar · PDP footer · Cart/Wishlist empty states (injection)
- **Current State:** Anonymous browse not remembered.
- **Proposed Direction:** `localStorage viewHistory (8)+ lastPlpUrl + compareQueue + searchHistory` (shared with INV-07/23/31), migrated to account on OTP; rail: thumbnail+price+stock badge (swipe mobile, cap 8); deep-link card reopens last filtered PLP/search with query+facets reapplied; same store as INV-07 Recent Searches, INV-23 compare queue. Cheapest retention lift; no backend for stage 1.

### INV-23 — Smart Compare Workspace — Persistent, Auto-Populated, Decisive-Attribute & Total-Cost Aware
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 2 — INTERACTION-01 P1 HIGH `02-ux-audit/issue-register.md:41` · DISC-03 P2 `issue-register.md:15` · Phase 3 — OPP-03 `03-opportunities/opportunity-pool.md:37-52` Cluster C3 · Phase 4 — VALIDATED `04-benchmark/applicability-review.md:56-60`
- **Related Evidence:** `01-current-state/page-analysis.md:173-178` `/compare` empty 3-slot with `Highlight differences` checkbox + 3 search inputs `Model name or part of product details` · `01-current-state/page-analysis.md:129` Compare entry `` on every PDP · `01-current-state/ecommerce-capabilities.md:23-25` Compare interface empty · `01-current-state/product-page-variations.md:65-66` Related Products single thin cross-sell not browsing-aware · `04-benchmark/pattern-library.md:47-56` Problem 3 (3A persistent bar, 3B decisive tint 6–8 rows, 3C total-cost pin) · Coolblue/Best Buy/RTINGS evidence `applicability-review.md:58-60`
- **User Problem:** Journey D (compare 3 Smart TVs/Fridges) is recall-bound hand-typed task; discovery of alternatives stalls; decisive attributes buried in 40 rows; total ownership invisible.
- **Affected Journey:** Journey D (compare several), Journey B shortlist 2–3
- **Affected Page(s):** PDP Compare entry · Sticky compare bar accumulation · `/compare` comparison table
- **Current State:** Compare exists but requires manual model recall; empty on entry; `Highlight differences` checkbox exists but no data.
- **Proposed Direction:** Sticky bar `Compare (2/3)` accumulates taps (session+auth persisted); `/compare` auto-populated, search remains as add-more only; decisive-attribute tint per category (AC `EER/tonnage/R32/Applicable sq ft`, TV `panel/HDR`, Fridge `litres/door/inverter`) collapses 40 rows to 6–8; verdict strip; total-cost pin row (`Price+Install+1yr Energy+EMI/mo` from INV-13/14) pinned; diff-highlight by checkbox; remove/share URL (WhatsApp family decision). `?familyRef` preserved for INV-17/22 context.

### INV-24 — Guided Selling Framework — Need → Constraints → Budget Finder (Umbrella + 5 Lenses)
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 3 — OPP-04 `03-opportunities/opportunity-pool.md:54-68` Cluster C4 · Phase 4 — ENHANCED `04-benchmark/applicability-review.md:62-67` · `04-benchmark/pattern-library.md:34-44` Problem 2
- **Related Evidence:** `01-current-state/page-analysis.md:90-91` SEO wall pushes grid below fold (IA-03) · `01-current-state/product-discovery.md:74-83` facets exist (Price/Brand/Display Size) but no wizard maps need→filter · `01-current-state/product-page-variations.md:55-61` spec `Applicable For 120 sq ft` Ton/size ambiguity · `04-benchmark/applicability-review.md:64-67` LG `20 BTU/sq ft` 3-field wizard `sq ft×height×top-floor/sun→tonnage`, AO `18L=1 bag` + 7-step measure guard, Samsung help-me-choose, Currys buying-guides hub
- **User Problem:** Shoppers must translate life need (room size/top-floor/sun, family size, viewing distance, household load, water TDS) into specs (tonnage/EER, litres/door, size/resolution, kg, filter) themselves; SEO wall is generic text not interactive helper.
- **Affected Journey:** Journeys B/C primary, Journey A entry via finder
- **Affected Page(s):** New `/buying-guides/{category}` hub + PLP CTA `Not sure? 30-sec guide` + filtered PLP output + PDP verdict chip `✓ Fits your 120 sq ft`
- **Current State:** No wizard; buyers hunt spec table; SEO equity not linked to filtered PLP.
- **Proposed Direction (ENHANCED):** Single 3-step wizard UI `Need→Constraints→Budget/Preference` outputs filtered PLP URL + PDP chip verdict. Shippable lenses: AC Finder first (largest ticket, `Choose Ton` proves family `variations.md:52`, fewest SKUs) → Fridge Validator (bag ladder + measure guard, guard source shared with INV-12/16) → TV Advisor → Washer Advisor → Kitchen/Purifier (cook family/wattage/jars, TDS→RO/UV) per `opportunity-pool.md:67` MED thin-evidence flag. Rule tables validated against brand spec tables (`product-detail-experience.md:12`); PDP verdict wiring; CMS for wizard copy. No ML.

### INV-25 — Complete-the-Setup — Bundles, FBT & Consumable Attach (Pre-Add + Cart Grouping)
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 3 — OPP-05 `03-opportunities/opportunity-pool.md:70-84` Cluster C5 · Phase 4 — VALIDATED `04-benchmark/applicability-review.md:69-72` · `04-benchmark/pattern-library.md:143-152` Problem 11
- **Related Evidence:** `01-current-state/ecommerce-capabilities.md:56` FBT/Bundles NOT OBSERVED · `01-current-state/product-page-variations.md:66-67` no accessories/bundles, single Related cross-sell `product-page-variations.md:65-66` thin · `01-current-state/personalization-current-state.md:12` Cart-Based Recs NOT OBSERVED · `04-benchmark/pattern-library.md:143-144` Home Depot *mandatory* hookup kits (cord/gas flex/duct/water line), AO bundle row `Add soundbar+mount → Save`
- **User Problem:** PDP sells isolated unit (TV without mount, AC without stabilizer/bracket/wire, washer without stand/detergent, purifier without cartridge); total ownership invisible until separate trip.
- **Affected Journey:** Journey E cart-attach moment; post-add confidence (Journey B)
- **Affected Page(s):** PDP bundle row + Cart post-add rail `Complete your setup`
- **Current State:** Thin single Related Products card; no affinity rule engine.
- **Proposed Direction:** Complement rule engine per family (AC→ stabilizer/wall bracket/copper wire, TV→ soundbar/wall mount/HDMI, fridge→ stabilizer, washer→ stand/detergent, purifier→ cartridge cadence every 6 months). Two surfaces: PDP toggleable bundle price before add + Cart grouped-line pricing. Suppress for low-ticket trimmer/mixer where attach generic per BDT 5k `site-inventory.md:92` threshold; mandatory-kit model doubles as install-failure prevention (ties to INV-16).

### INV-26 — Plural Payment Row — COD + bKash/Nagad + Card-on-Delivery + Online/EMI (District-Aware)
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 2 — CHECKOUT-01 P1 `02-ux-audit/issue-register.md:38` · TRUST-01 P2 · Phase 4 — NEW-03 `04-benchmark/new-opportunities.md:9` · `04-benchmark/applicability-review.md:146` STANDARD BD
- **Related Evidence:** `01-current-state/page-analysis.md:34` homepage `Secure Payment System` bar only vs PDP only `Avail Bank EMI` for cardholders — excludes 75–90% COD buyers `regional Finding 4 Levree wallet 75–90% COD` · `04-benchmark/pattern-library.md:161` Problem 12A Daraz/Pickaboo/ChalDal plural row `Free Shipping, bKash, Card on Delivery, COD, Countrywide` · `04-benchmark/applicability-review.md:148` Pickaboo “for your best convenience”
- **User Problem:** Bangladesh checkout cannot be card-first; district-aware COD availability invisible at decision moment; choice itself is trust.
- **Affected Journey:** PDP decision + Cart Order Summary district truth `Delivery to Rajshahi: COD available`
- **Affected Page(s):** PDP beneath EMI row (co-equal radio) + Cart Order Summary
- **Current State:** PDP shows `Avail Bank EMI` only; plural choice absent.
- **Proposed Direction:** Co-equal row `◉ Cash on Delivery ✓ | ◉ Card on Delivery (Swipe) ✓ | ◉ bKash/Nagad ✓ | ◉ Online Card (EMI eligible) ✓` with district-aware line from same zone matrix as INV-13; no backend beyond zone availability. Pairs with INV-14 financing row + INV-13 delivery.

### INV-27 — Cart Drawer + Checkout Transparency — Landed-Cost Breakdown, Stepper, Mini-Cart, Empty-State Recovery
- **Type:** FIX (repairs dead-ends) + NEW system (drawer/stepper/toast)
- **Source Phase(s):** Phase 2 — CART-01 P1 HIGH `02-ux-audit/issue-register.md:36` · CART-02 P2 `issue-register.md:37` · CHECKOUT-01 P1 `issue-register.md:38` · FEEDBACK-01 P1 `issue-register.md:42` · Phase 4 — NEW-06 `04-benchmark/new-opportunities.md:12` elevated from remediation tail `03-opportunities/cross-review.md:67`
- **Related Evidence:** `01-current-state/page-analysis.md:159-164` empty cart `You have not added…` illustration, Order Summary `Subtotal: ৳0 Total: 0`, Checkout `disabled` when empty — VERIFIED · `01-current-state/user-journeys.md:122-148` Checkout journey STOPPED BEFORE PAYMENT, `Checkout button is disabled — VERIFIED`, no alternative `/checkout` URL in sitemap `00-input/sitemap-analysis.md:94-102` · `04-benchmark/pattern-library.md:164` Problem 12D Apple/ASOS/Best Buy stepper `Cart→Delivery→Payment→Confirm` + Daraz Control Tower 65 hubs
- **User Problem:** Empty-cart dead-end with no inline next-step guidance; checkout steps undiscoverable until after adding + auth; no landed-cost truth before paywall; no toast on Add → duplicate clicks.
- **Affected Journey:** Journey E purchase boundary — highest P1 conversion gap after delivery
- **Affected Page(s):** Cart page `/cart` · Slide-in mini-cart on Add confirmation · Checkout stepper (preview on empty cart)
- **Current State:** Dead-end empty state; progress invisible; fees invisible at price.
- **Proposed Direction:** Slide-in mini-cart on Add confirmation with count animation; Cart Order Summary truth row `Subtotal + Delivery + Install → Total` (explicit `Free Installation vs Tk X` shares table with INV-13/14) + progress stepper `Cart → Delivery → Payment → Confirm` with trust micro-copy; feedback toasts on every add/wishlist/compare (repairs FEEDBACK-01); empty-state injection of INV-22 rails + `Continue Shopping`. Low backend; reuses INV-13 fee tables.

### INV-28 — Open-Box Delivery + OTP Doorstep Verification
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 4 — NEW-02 `04-benchmark/new-opportunities.md:8` · `04-benchmark/applicability-review.md:145` (STANDARD India / EMERGING BD differentiator) · `04-benchmark/pattern-library.md:162` Problem 12B
- **Related Evidence:** `01-current-state/ecommerce-capabilities.md:42-44` gated preview has no OBD/OTP language; big-ticket doorstep anxiety for 600L/65"/1 Ton + COD 75–90% dispute risk · Flipkart OBD T&C `If eligible… Order Summary opt-in; rider opens outer+brand packing, checks damage/correct item/IMEI/accessories; customer shares OTP only after satisfaction, photographed + reference logged` + India Post 1.6L offices COD OTP `regional Finding 2`
- **User Problem:** Self-unbox burden shifts to buyer; damage/correct-item dispute risk for Tk 50k–1.5L; `Original Product Guaranteed` not materially proven.
- **Affected Journey:** Post-purchase fulfilment for >Tk 20k electronics
- **Affected Page(s):** PDP badge `Eligible for Open Box Delivery at your pincode ✓` (from INV-13 zone truth) · Order Summary opt-in · Doorstep protocol
- **Current State:** No OBD/OTP flow.
- **Proposed Direction:** Eligibility badge by pincode; opt-in on Order Summary for electronics >Tk 20k; rider opens both packings in front of customer, checks damage/correct item/IMEI/accessories; OTP share after satisfaction + photo log; differentiator for owned fleet vs pure marketplace (`Original Product` mechanically proven). Owned Store Locator + logistics gives credible Wishmaster.

### INV-29 — Conversational Care — WhatsApp/Messenger Human Agent + PDP Share Deep-Link
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 4 — NEW-04 `04-benchmark/new-opportunities.md:10` · `04-benchmark/applicability-review.md:147-148` (STANDARD social layer / EMERGING human manager)
- **Related Evidence:** `01-current-state/page-analysis.md:14` sticky `Need help? Click Here ` trigger OBSERVED generic not conversational · PDP `Share` `` lacks WhatsApp; PDP-07 empty social proof; Facebook Commerce “thousands sell exclusively via FB” `regional Finding 7` · `01-current-state/page-analysis.md:20` footer `Chat With Us / Connect`; `04-benchmark/pattern-library.md:163` Problem 12C
- **User Problem:** Tier-2/3 high-ticket needs voice/chat before cart; buyer checks Messenger before site; purchase is collective family huddle via WhatsApp.
- **Affected Journey:** All considered PDP hesitation → purchase reassurance
- **Affected Page(s):** PDP deep-link `Share via WhatsApp — Ask agent about this fridge` + hotline fallback · Footer `Chat With Us` wired same
- **Current State:** Help trigger generic; Share not WhatsApp-native.
- **Proposed Direction:** PDP deep-link to human WhatsApp/Messenger with PDP URL pre-filled + hotline fallback; optional premium manager for >Tk 50k `Get personal manager — message on WhatsApp` (agent handles order, Tracks delivery, resolves post-delivery — ChalDal Premium Care model). Deep-links, no platform build; social influence β=0.13, WOM drives purchase `BJMS 2025`.

### INV-30 — Hotline-Sticky Support Spine + Schedule Store Visit Linkage
- **Type:** IMPROVEMENT
- **Source Phase(s):** Phase 4 — NEW-05 `04-benchmark/new-opportunities.md:11` · `04-benchmark/applicability-review.md:149` (STANDARD BD hygiene)
- **Related Evidence:** `01-current-state/page-analysis.md:18-19` `16212 9AM–9PM` `estore@transcomdigital.com` footer-only not in funnel — VERIFIED · `01-current-state/page-analysis.md:199-204` Store Locator List/Map + district dropdown + `Schedule your visit` Mapbox VERIFIED but not linked from PDP Store Pickup · `01-current-state/page-analysis.md:7` header `Track Order Status / Track Your Service` links OBSERVED not wired to real-time · `04-benchmark/pattern-library.md:163` Problem 12C Daraz 16492/ChalDal 16710/Star Tech 16793 hotline pattern
- **User Problem:** Voice before cart for AC/Fridge/Washer highly reassuring but footer-only; Tier-2/3 low self-serve confidence cannot convert without store reassurance bridging.
- **Affected Journey:** Considered PDP → store reassurance → conversion
- **Affected Page(s):** PDP/Cart sticky call bar · PDP Store Pickup estimator shows nearest 3 stores with stock + `Schedule your visit` district cards · Track Order/Service wiring
- **Current State:** Hotline exists but not in funnel; locator not PDP-linked.
- **Proposed Direction:** Elevate `16212 9AM–9PM` to sticky call bar on PDP/Cart; PDP Store Pickup estimator (from INV-13) shows nearest 3 stores with stock + `Schedule your visit` deep-link; `Track Order Status / Track Your Service` wired to real-time (Daraz control towers 65 hubs reference). Wire existing assets; no rebuild.

### INV-31 — Post-Action Feedback — Toasts & Persistence Confirmation (Cart/Wishlist/Compare) + Guest Inline Prompt
- **Type:** FIX
- **Source Phase(s):** Phase 2 — FEEDBACK-01 P1 MEDIUM `02-ux-audit/issue-register.md:42` · AUTH-02 P2 `02-ux-audit/issue-register.md:40`
- **Related Evidence:** `01-current-state/user-journeys.md:98-101` Add To Cart run timed out before cart state capture — PARTIALLY VERIFIED, no diff/toast captured · `01-current-state/ecommerce-capabilities.md:36-38` Wishlist/Compare empty as guest `You have not added…` (Wishlist `page-analysis.md:167-171`, Compare `page-analysis.md:173-178`) guest clicks appear to do nothing · `04-benchmark/pattern-library.md:164` 12D feedback toast + `04-benchmark/applicability-review.md:148-150` reinstated
- **User Problem:** Users uncertain if product was saved/added; duplicate clicks; guest clicks on save appear as no-op.
- **Affected Journey:** Journey E purchase intent; Journey F save-for-later; guest save
- **Affected Page(s):** PDP `Wishlist`/`Compare`/`Add To Cart` → Cart/Wishlist/Compare empty pages · Header count badges
- **Current State:** No visible toast/confirmation; empty persistence without inline explanation.
- **Proposed Direction:** Immediate toast + animated cart count increment on every add/wishlist/compare; persistent drawer/chevron confirmation; guest inline prompt “Saved — log in to persist across devices” (feeds INV-32 migration). Part of INV-27 drawer wiring.

### INV-32 — Authentication Friction & Guest→Auth Continuity (OTP Split-Field, No-Password, History Migration)
- **Type:** FIX
- **Source Phase(s):** Phase 2 — AUTH-01 P2 HIGH `02-ux-audit/issue-register.md:39` · AUTH-02 P2 `issue-register.md:40` · M-05 `03-opportunities/cross-review.md:230`
- **Related Evidence:** `01-current-state/page-analysis.md:192-195` Login `+880` selector, two textbox split-field, `Next` — VERIFIED, no password/social · `01-current-state/ecommerce-capabilities.md:57-60` Login OTP-only, split-field, velocity · `01-current-state/personalization-current-state.md:13` Wishlist persistence AUTHENTICATION REQUIRED · `01-current-state/ecommerce-capabilities.md:38,55` guest wishlist inert · `03-opportunities/cross-review.md:230` guest→auth memory handoff un-designed
- **User Problem:** Desktop users without phone access face friction; split field slows entry; guest→auth migration missing — viewHistory/compareQueue saved as guest lost on login, collapsing INV-22/23 value.
- **Affected Journey:** Journey F authenticated lifecycle; all personalization dependents
- **Affected Page(s):** Login `/login` (+880 flow) · PDP save actions · Account creation post-OTP
- **Current State:** Phone OTP only; split-field; no social/password alt; anonymous history not migrated.
- **Proposed Direction:** Consolidate split phone field to single input; consider social/password alt for desktop; tighten OTP velocity; implement `localStorage`→account migration on OTP success for viewHistory/compareQueue/wishlist/searchHistory (`INV-22` rail preserves cross-device). Gate for INV-06/22/23/33 authentic value.

### INV-33 — Exchange & Return Value — 14-Day Badge + Cross-Category AI Diagnostics + Timeline
- **Type:** NEW CAPABILITY
- **Source Phase(s):** Phase 2 — FEEDBACK-02 P2 `02-ux-audit/issue-register.md:43` · Phase 3 — OPP-06 `03-opportunities/opportunity-pool.md:86-100` (QUESTIONED P2 pipeline-heavy, zero benchmark pattern) · Phase 4 — NEW-07 `04-benchmark/new-opportunities.md:13` · `04-benchmark/applicability-review.md:150` (EMERGING BD / STANDARD India)
- **Related Evidence:** `01-current-state/page-analysis.md:113` Dell `Currently Unavailable` → `Get Stock Alert` with no timeline — VERIFIED · `01-current-state/ecommerce-capabilities.md:49,54` stock button VERIFIED but Price Alerts NOT OBSERVED · `01-current-state/page-analysis.md:208-212` Exchange hub `/exchange` 2-card Refrigerator/Washing Machine + PLP `Get Exchange up to 12000 Tk` `product-discovery.md:119-120` — valuation/execution opaque · `04-benchmark/new-opportunities.md:13` Daraz 14-day ALL products 2025 + Flipkart ReCommerce 26 cats cross-category AI diagnostics 10-step + Trust Shield 30-day `regional Finding 8`
- **User Problem:** Out-of-stock alert has no timeline/expectation; wishlist inert as guest; exchange hub exists but trade-in valuation/execution opaque `TRUST-01` homepage `Exchange Program` not echoed PDP; idle household assets not currency.
- **Affected Journey:** Wishlist/authenticated resumption · Out-of-stock research (Dell outlier) · Upgrade trade-in
- **Affected Page(s):** PDP `Currently Unavailable` state + wishlist · Exchange hub `/exchange/{id}?category=…` · PDP badge `14-Day Hassle-Free Return ✓` + `Exchange value: Estimate up to Tk 12k → doorstep inspection → OTP`
- **Current State:** Get Stock Alert no ETA; Wishlist inert without price-watch; exchange brochure-only.
- **Proposed Direction:** PDP badge next to `In stock` `14-Day Hassle-Free Return ✓` (Daraz Aug 2025 baseline expectation) + cross-category doorstep exchange `up to Tk 12k → inspection → OTP` beneath price; valuation explicit `Restocking 2–3 weeks — notify at arrival or show similar in-stock alternatives`; cross-category (fridge→washer, laptop→fridge, fan→purifier) + 10-step AI condition check within minutes (phase 2). Start static `up to` + inspection truth; AI phase 2. QUESTIONED sequencing remains: defer until wishlist persistence + INV-20 social proof base proved — here inventoried, not sequenced.

### INV-34 — Accessibility & Icon System — Labeled Controls, Contrast, Keyboard Order
- **Type:** FIX
- **Source Phase(s):** Phase 2 — ACCESS-01 P2 MEDIUM `02-ux-audit/issue-register.md:45` · Related: `01-current-state/page-analysis.md:7-14` header
- **Related Evidence:** `02-ux-audit/issue-register.md:45` icon-only controls header (`` cart, `` wishlist, `` share, `` Compare) lack visible text labels in snapshot; color contrast and focus order not enumerated — MEDIUM observation · `01-current-state/page-analysis.md:9-14` main header icon buttons, Top utility bar `B2B / Dealership, Store Locator, Track Order Status…`
- **User Problem:** Screen-reader/keyboard users face discovery failures; WCAG risk; icon-only trio lacks affordance for sighted as well.
- **Affected Journey:** All journeys for assistive-tech users
- **Affected Page(s):** Header (all pages) · PDP action trio (`Compare`/`Wishlist`/`Share`) · Cart/Compare controls
- **Current State:** Icon font without paired visible label in snapshot; focus order not enumerated.
- **Proposed Direction:** Pair icons with visible text labels or aria-label + tooltip; verify contrast ratios and tab order; add focus indicator; audit `Highlight differences` Plans. No change to information architecture — hygiene.

---

## Coverage Matrix — All Sources Normalized Without Duplication

| Source ID | Source Title | Mapped INV(s) | Disposition |
|-----------|--------------|--------------|-------------|
| NAV-01 | Browse `/undefined` | INV-01 | FIX retained |
| IA-01 .. IA-04 | Flat URL, orphan, hyphen, SEO wall | INV-02, INV-04 | 2 FIXes |
| NAV-02 | Brand vs Search duplicate | INV-03 | FIX |
| DISC-01/02/03/04 | Homepage overload, no resumption, thin Related, tile mismatch | INV-06, INV-22, INV-23/25, INV-05 | 1 IMPROV + 2 NEW + 1 FIX |
| SEARCH-01..03 | Autocomplete, placeholder, zero-result | INV-07, INV-08 | 1 NEW + 1 NEW (staged) |
| FILTER-01..04 | Chips, Review empty, dual slider, taxonomy dup | INV-09, INV-11 | 2 FIXes |
| SORT-01/02 | Sort placeholder, pagination | INV-10 | FIX |
| PDP-01..09 | Video/zoom, delivery gate, install buried, tab inconsistency, warranty, EMI inconsistent, reviews absent, no variant, duplicate CTA | INV-12, INV-13, INV-16, INV-15, INV-18, INV-14, INV-20, INV-17, INV-19 | 3 IMPROV/FIX + 4 NEW + 2 FIX |
| TRUST-01 | Trust not echoed | INV-18 + INV-21 | FIX + NEW (two-layer) |
| CART-01/02, CHECKOUT-01 | Empty dead-end, populated untested, checkout black box | INV-27 | FIX/NEW drawer system |
| AUTH-01/02 | OTP split-field, guest save no prompt | INV-32, INV-31 | FIX |
| INTERACTION-01 | Compare hand-search | INV-23 | NEW |
| FEEDBACK-01/02 | No toast, no timeline | INV-31, INV-33 | FIX + NEW |
| CONSISTENCY-01 | EMI badge vs text | INV-14 | In-row verdict |
| ACCESS-01 | Icon-only | INV-34 | FIX WCAG |
| MOBILE-01 | Heavy grid | INV-06 | IMPROV budget |
| OPP-01 | Delivery Estimator | INV-13 | NEW ENHANCED (district text, Fast badge, shared table) |
| OPP-02 | Browse Resumption | INV-22 | NEW VALIDATED |
| OPP-03 | Smart Compare | INV-23 | NEW VALIDATED |
| OPP-04 | Guided Selling | INV-24 | NEW ENHANCED (wrapper + bag+guard) |
| OPP-05 | Complete-the-Setup | INV-25 | NEW VALIDATED |
| OPP-06 | Wishlist Intelligence | INV-33 | NEW QUESTIONED (deferred but inventoried) |
| OPP-07 | Intelligent Search | INV-07 | NEW VALIDATED Stage1 |
| OPP-08 | Zero-Result Recovery | INV-08 | NEW VALIDATED |
| OPP-09 | True Cost & EMI Planner | INV-14 | NEW ENHANCED (offline form, threshold, verdict) |
| OPP-10 | Rich Media Suite | INV-12 | IMPROV VALIDATED |
| OPP-11 | Jargon Decoder | INV-15 | NEW VALIDATED |
| OPP-12 | Installation Checker/Booking | INV-16 | NEW ENHANCED (Gate1 content; Gate2 Booking is ops-gated extension noted) INV-16 covers checker; bookable slot is Phase inside same INV filed as Gate2* |
| OPP-13 | Variant Navigator | INV-17 | NEW VALIDATED |
| OPP-14 | Social Proof | INV-20 | NEW ENHANCED (needs INV-21 companion) |
| OPP-15 | Affinity Homepage Reorder | INV-06 note + INV-22 cheap alternative | QUESTIONED deferred → experiment; homepage budget triage ships instead |
| NEW-01 | Authenticity Badging | INV-21 | NEW STANDARD BD |
| NEW-02 | OBD + OTP | INV-28 | NEW EMERGING BD |
| NEW-03 | Plural Payment | INV-26 | NEW STANDARD BD |
| NEW-04 | WhatsApp/Messenger Care | INV-29 | NEW |
| NEW-05 | Hotline-Sticky | INV-30 | IMPROV |
| NEW-06 | Cart Drawer + Stepper | INV-27 | FIX/NEW (elevated from remediation M-01) |
| NEW-07 | 14-Day + AI Exchange | INV-33 | NEW EMERGING |
| NEW-08 | Phygital + Threshold Bundling | INV-06/+28 wiring note (stored with Store Locator; threshold bundling inventoried as INV-25/27 extension; phygital remains in INV-30 linkage — full NEW-08 mechanics noted as Phase of INV-30 + INV-25/27, no separate build counted to stay within 34) — threshold `Add 2 more for Free Delivery` is Cart merchandising extension filed under INV-27/30 shared table |

> *INV-12 Gate2 Bookable Slot detail:* `04-benchmark/applicability-review.md:110-117` Gate2 calendar `Prereq tick + fee + order↔service-order + Track Your Service + push` is inventoried inside INV-16 as deferred Gate2 after slot-capacity feed confirmation (`03-opportunities/cross-review.md:174`). Not a separate INV — prevents double-count.

**Benchmark-enhanced patterns (5) folded:**
- OPP-01 → district text + Fast badge (INV-13)
- OPP-04 → buying-guide hub wrapper + bag+guard (INV-04 + INV-24)
- OPP-09 → offline form latency + combined row + verdict + threshold (INV-14)
- OPP-12 → priced basket SKU + Before You Buy video + checker-first phasing (INV-16)
- OPP-14 → authenticity companion two-layer trust (INV-20 → INV-21)

**Deduplication applied per `03-opportunities/duplicates-and-overlaps.md:6-19`:**
- Clusters C1..C9 (28 rows → 8 capabilities) collapsed to INV-13,22,23,24,25,33,07,12,14 — no duplication.
- Removed tails reinstated: ECS-07 `Active Filter/Sort Feedback` (`INV-09`/`INV-10`) and ECS-06 `Populated Cart Completeness` part (`INV-27 Quantity/Coupon/Breakdown` flagged as hygiene inside Cart completeness) elevated from remediation to FIX inventoried here because benchmark pattern-library 12D validates drawer/stepper as STANDARD hygiene requiring explicit inventory — gap deemed load-bearing per developer note applicable to all cases.
- PER-09 seasonal broadcast tail (`cross-review.md:41` generic) is sole omitted — not inventoried as initiative; treated as campaign optimization.

---

## Shared Data & Wiring (for Phase 5 Prioritization, not sequencing)

> From `04-benchmark/applicability-review.md:158-169` + `04-benchmark/pattern-library.md:168-181`. Single tables feed multiple INVs — build once.

| Shared Table / Component | Feeds INVs | Note |
|--------------------------|-----------|------|
| District→Zone/SLA + Delivery Fee + Install Fee + Store Inventory table | INV-13, INV-14, INV-16, INV-20 context, INV-26, INV-28, INV-30, INV-27 | Build once; district-aware truth |
| EMI Bank/Tenure rule table + BDT 5k threshold + form-latency copy | INV-14, INV-23 total-cost pin, INV-26, INV-27 | Finance-owned; eligibility verdict shared |
| `W×H×D + ventilation gap + hinge/swing + bracket` dimension normalization | INV-12 overlay, INV-16 checker, INV-24 Fridge guard | One enrichment task `01-current-state/product-page-variations.md:61` verified pattern |
| Tariff × EER/kWh → `Tk/mo` formula + Glossary CMS 25–40 terms | INV-15, INV-14, INV-24 explainability | `pattern-library.md:90-92` formula |
| Family graph `model_root → variants by dimension` + Price/Stock feed | INV-17, INV-23, INV-12 re-validate on switch, INV-25 attach mapping | Top 30 roots ≈ 70% high-ticket `00-input/sitemap-analysis.md:44` (Haier 12, Tron 9…) |
| `localStorage viewHistory + lastPlpUrl + compareQueue + searchHistory` + auth migration | INV-07 Recent, INV-22, INV-23, INV-29 share URL | Same store; no backend for stage 1 (INV-32 migration Gate2) |
| Review aggregation + verified-purchase + moderation pipeline | INV-20, INV-21 companion | Pipeline before badges; suppress `n<5` |
| Store Locator feed (`/store-locator` already VERIFIED `01-current-state/page-analysis.md:199-204`) | INV-13 pickup alt, INV-30 linkage | Wire, don't rebuild |

---

## Open Gaps & Preservation Notes

- **Not sequenced, not prioritized:** This STEP 1 inventory intentionally avoids RICE/MoSCoW; sequencing is Step 2.
- **Preserved P0 blockers:** INV-01 (`/undefined` P0) is the only P0; every downstream conversion lift is gated on it — noted but not ordered here.
- **Questioned retained:** INV-33 (Wishlist Intelligence) and homepage affinity reorder (OPP-15) are retained inside INV-33/INV-06 notes as inventoried but QUESTIONED per `04-benchmark/applicability-review.md:74-81` (pipeline-heavy, auth-gated, zero benchmark pattern). Filed as P2-capable; inventory does not endorse P0.
- **Suppression rule (consistent with `03-opportunities/cross-review.md:168` + BDT 5k `04-benchmark/applicability-review.md:96`):** Suppress EMI row, energy row, checker, and FBT for Personal Care trimmer/mixer `Tk 3k` (`01-current-state/product-page-variations.md:104`); show authenticity + plural payment everywhere.
- **Verification before build:** INV-07 autocomplete empty dropdown may be rendering bug not missing index (`03-opportunities/cross-review.md:205`) — re-test *before* build; INV-27 populated-cart wiring remains NOT TESTED (`01-current-state/ecommerce-capabilities.md:40`).

---

## Traceability Index (all files touched)

| File | Lines | Role in this inventory |
|------|------|------------------------|
| `00-input/sitemap-analysis.md` | :7-38 category counts · :27 flat PDP · :74 orphan · :132 hyphen | IA hygiene INV-02/03 |
| `01-current-state/site-inventory.md` | :77 broken See All · :112 flat namespace | INV-01/02 |
| `01-current-state/page-analysis.md` | :7-15 header · :14 Help trigger · :18 16212 · :34 trust bar · :47 Shop By Category · :48-54 7+ grids · :56-57 `/undefined` · :75-86 filters · :84 sort · :90 SEO wall · :113 Get Stock Alert · :125 Enable Location · :126 ATC · :131 tabs · :134 gallery · :159 cart · :173 compare · :199 store locator | 14 INVs |
| `01-current-state/product-discovery.md` | :40 suggestions · :74 facets · :89 sort · :98 recommendations | INV-07/09/10 |
| `01-current-state/product-page-variations.md` | :49 68 images · :52 Choose Ton · :55 EMI absent · :59 delivery gate · :61 warranty · :66 bundles NOT OBSERVED | INV-12-18,22,25 |
| `01-current-state/user-journeys.md` | :7-277 Journeys A–F · :122 CHECKOUT blocked · :155 login | INV-03,27,32 |
| `01-current-state/ecommerce-capabilities.md` | :12 search · :15 zero-result · :28 spec heading · :30 video · :31 reviews · :42 delivery gate · :45 install · :52 exchange · :55 Recently NOT OBSERVED · :57 login OTP | INV-07-16,20,22 |
| `01-current-state/personalization-current-state.md` | :9-10 Recently/Continue NOT OBSERVED | INV-22 |
| `02-ux-audit/issue-register.md` | :7-46 all 32 IDs | All FIX spine |
| `02-ux-audit/executive-summary.md` | :5 maturity Developing → Foundational | Context for IMPROVEMENT rationale |
| `03-opportunities/opportunity-pool.md` | :7-245 all 15 OPPs | 15 OPP mapping |
| `03-opportunities/cross-review.md` | :32-73 fate table · :126-138 clusters C1–C9 · :234 M-gaps | Dedup logic + M-01..M-08 coverage |
| `03-opportunities/duplicates-and-overlaps.md` | :6-19 metrics · :20 merge rationale | Dedup audit trail |
| `04-benchmark/pattern-library.md` | :22 Problem 1 · :34 Problem 2 · :47 Problem 3 · :59 Problem 4 · :72 Problem 5 · :86 Problem 6 · :96 Problem 7 · :108 Problem 8 · :119 Problem 9 · :132 Problem 10 · :143 Problem 11 · :155 Problem 12 | Pattern maturity per INV |
| `04-benchmark/applicability-review.md` | :22-38 15 OPP table · :46-135 per-OPP detail · :142 NEW table · :158 wiring | VALIDATED/ENHANCED/QUESTIONED tags |
| `04-benchmark/new-opportunities.md` | :7-14 8 NEW rows | INV-21,26-30,33 |
| `04-benchmark/competitive-opportunity-map.md` | :5-29 mapping + wiring | Market-informed classification |
| `04-benchmark/phase-4-summary.md` | :11 11 STANDARD · :38 emerging · :58 differentiators · :80 experimental | Portfolio maturity context |

---

*Generated as Phase 5 Step 1 Master Initiative Inventory. 34 initiatives — all traceable per file:line above to `00-input`, `01-current-state`, `02-ux-audit`, `03-opportunities`, `04-benchmark`. No prioritization applied; next Step 2 will score and sequence.*
