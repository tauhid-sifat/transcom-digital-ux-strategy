# Value Analysis — Phase 5 Step 3

> **Phase:** 5 Step 3 — Value Analysis (Initiative-Level)
> **Date:** 2026-09-03
> **Status:** Step 3 Complete — classified, not yet sequenced
> **Input:** `05-prioritization/master-initiative-inventory.md` (34 → 25) · `05-prioritization/initiative-merging.md` (25 consolidated) · `02-ux-audit/issue-register.md:7-46` (32 issues, P0=1 P1=13) · `02-ux-audit/user-journey-friction.md` (Journeys A–F) · `03-opportunities/opportunity-pool.md:7-245` (15 OPPs) · `04-benchmark/applicability-review.md:22-152` (15 validated + 8 NEW) · `04-benchmark/pattern-library.md:22-165` (12 problems, 38 variations) · `01-current-state/user-journeys.md` (J1–J9)
> **Method:** Score each of 25 consolidated initiatives on 5 dimensions — no invented revenue. Classification is absolute value, not build order (sequencing is Step 4).

---

## Classification Criteria

| Dimension | Question |
|-----------|----------|
| **USER VALUE** | Does it solve a meaningful, evidenced user problem (not internal hygiene alone)? |
| **JOURNEY IMPACT** | Which journey(s) and moment does it unblock: discovery / decision-making / purchase / post-purchase? |
| **FRICTION REDUCTION** | Does it remove an observed pain (abandonment, distrust, recall burden, dead-end) — `issue-register.md` severity as proxy? |
| **BUSINESS RELEVANCE** | Which lever: conversion / discovery throughput / trust / engagement / retention / AOV? |
| **STRATEGIC RELEVANCE** | Is absence conspicuous for a mature electronics e-commerce (STANDARD vs EMERGING vs DIFFERENTIATOR per `pattern-library.md:9-18`)? |

| Class | Definition |
|-------|------------|
| **VERY HIGH** | Hard blocker or baseline trust failure — user abandons or cannot decide; affects ≥2 high-ticket journeys; STANDARD baseline whose absence is conspicuous; without it maturity claim fails. |
| **HIGH** | Meaningful P1 decision/purchase friction — significantly lifts consideration-to-cart or trust, validated STANDARD/EMERGING, but journey can still limp without it. |
| **MEDIUM** | Valuable for subset, retention/AOV/engagement, or ops-gated differentiator — improves maturity but not core funnel blocker; often phasing-dependent. |
| **LOW** | Hygiene/niche/compliance — necessary but narrow reach, deferred sequencing, or QUESTIONED evidence for now. |

> No revenue math invented. Business relevance is lever-based, not Tk-forecast.

---

## Summary Table — 25 Consolidated Initiatives

| # | Final ID | Initiative Name | Type | Value Class | Primary Lever |
|---|----------|-----------------|------|-------------|---------------|
| 1 | **INV-C01** | IA & Discoverability Hygiene — Flat PDP, Orphan `/tv-av`, Trailing-Hyphen, Canonical & Tile Alignment | FIX | **HIGH** | Discovery / SEO trust |
| 2 | **INV-01** | Repair Broken Browse Paths (`/undefined` See All) | FIX | **VERY HIGH** | Conversion (funnel entry) |
| 3 | **INV-04** | SEO Architecture — Move Buying-Guide Wall Below Fold, Buying-Guide Hub | FIX | **HIGH** | Discovery throughput |
| 4 | **INV-C02** | PLP Browse Controls Hygiene — Chips, Sort, Pagination, Facet Repair | FIX | **VERY HIGH** | Discovery / conversion |
| 5 | **INV-06** | Homepage Prioritization & Performance Budget | IMPROVEMENT | **MEDIUM** | Engagement / performance |
| 6 | **INV-C03** | Intelligent Search & Recovery — Autocomplete + Recent + Recovery | NEW (gated) | **VERY HIGH** | Discovery / conversion |
| 7 | **INV-12** | Rich Media Inspection — Zoom, Pinch, Video, 360°, Dimension Overlay & AR | IMPROVEMENT | **HIGH** | Decision confidence |
| 8 | **INV-13** | Delivery & Serviceability Estimator — Pincode-First Landed Cost + Fast Badge | NEW | **VERY HIGH** | Conversion / trust |
| 9 | **INV-14** | True Cost & EMI Planner — Ownership Row + Tenure Picker + Eligibility Verdict | NEW | **VERY HIGH** | Conversion / trust |
| 10 | **INV-C04** | Spec Literacy & Warranty Truth — Jargon Decoder + Energy Translator + Warranty Legend Propagation | FIX | **HIGH** | Decision confidence / trust |
| 11 | **INV-16** | Installation Feasibility Checker — Pass/Fail Verdict + Priced Basket (Gate2 ops-gated) | NEW | **HIGH** | Conversion / post-purchase |
| 12 | **INV-17** | Variant & Family Navigator — Sibling Chips with Delta & Stock | NEW | **HIGH** | Decision / discovery |
| 13 | **INV-20** | Social Proof Pipeline — Ratings, Review Count, Badges, Facet, Q&A | NEW | **VERY HIGH** | Trust / conversion |
| 14 | **INV-21** | Authenticity / Authorized-Retailer Badging at Price Context | NEW | **VERY HIGH** | Trust / conversion |
| 15 | **INV-22** | Browse Resumption — Recently Viewed Rail + Continue Shopping Deep-Link | NEW | **HIGH** | Retention / engagement |
| 16 | **INV-23** | Smart Compare Workspace — Persistent, Auto-Populated, Decisive & Total-Cost Aware | NEW | **HIGH** | Decision / conversion |
| 17 | **INV-24** | Guided Selling Framework — Need→Constraints→Budget Finder (5 Lenses + Hub) | NEW | **HIGH** | Decision / discovery |
| 18 | **INV-25** | Complete-the-Setup — Bundles, FBT & Consumable Attach | NEW | **MEDIUM** | AOV / post-purchase |
| 19 | **INV-26** | Plural Payment Row — COD + bKash/Nagad + Card-on-Delivery + Online/EMI | NEW | **VERY HIGH** | Conversion / trust |
| 20 | **INV-C06** | Cart Drawer & Feedback System — Drawer, Stepper, Landed-Cost Truth, Toasts, CTA Hierarchy | FIX/NEW | **VERY HIGH** | Conversion |
| 21 | **INV-28** | Open-Box Delivery + OTP Doorstep Verification | NEW | **MEDIUM** | Trust / post-purchase |
| 22 | **INV-C05** | Human Support Spine — WhatsApp/Messenger + Hotline + Store Visit | NEW/IMPROV | **MEDIUM** | Trust / conversion assist |
| 23 | **INV-32** | Authentication Friction & Guest→Auth Continuity (OTP, History Migration) | FIX | **MEDIUM** | Retention / conversion enable |
| 24 | **INV-33** | Exchange & Return Value — 14-Day Badge + Cross-Category AI Diagnostics + Timeline | NEW | **MEDIUM** | Trust / retention |
| 25 | **INV-34** | Accessibility & Icon System — Labeled Controls, Contrast, Keyboard Order | FIX | **LOW** | Compliance / inclusion |

**Counts:** VERY HIGH **9** · HIGH **9** · MEDIUM **6** · LOW **1** — total 25. (INV-26 at boundary; rationale below.)

---

## Detailed Evaluation — All 25

### INV-C01 — IA & Discoverability Hygiene (Flat PDP, Orphan `/tv-av`, Trailing-Hyphen, Canonical & Tile Alignment)
- **Source INVs:** INV-02 + INV-03 + INV-05 → M-01 (`initiative-merging.md:50`)
- **Type:** FIX — `issue-register.md:8-12,16` IA-01 P1, IA-02 P2, IA-04 P2, NAV-02 P2, DISC-04 P2
- **USER VALUE:** Medium-High. Users can still browse via category cards/search, but flat `/{brand}-{model}` at root (`sitemap-analysis.md:27` 101 PDPs) severs mental model, back-navigation, and share/bookmark confidence; truncated `pureit-classic-23l-` etc. risk 404 on copy-paste; duplicate brand PLP vs `search?Brand=` creates authoritative-path confusion.
- **JOURNEY IMPACT:** Discovery (IA/seo entry) across all journeys; PDP↔category traversal. Not a single-moment abandonment like `/undefined`, but degrades findability and crawl.
- **FRICTION REDUCTION:** Removes low-grade persistent confusion and duplicate-content tax; fixes tile→taxonomy expectation violation (Dishwashers tile without `/dishwashers` route `page-analysis.md:47`).
- **BUSINESS RELEVANCE:** Discovery throughput + SEO equity; bounce/crawl-waste reduction rather than direct cart lift.
- **STRATEGIC RELEVANCE:** HIGH for mature posture — canonical discipline, hierarchical signal, and taxonomy truth are expected baselines. Not EMERGING; table-stakes hygiene that competitors (Daraz/Pickaboo brand PLPs) already normalize.
- **WHY HIGH (not VERY HIGH):** Fixes credibility and entry routes but does not hard-block considered-purchase decision or paywall. Users work around flat URL; they cannot work around `/undefined` or missing delivery truth. Ships as one sitemap/redirect release, lower user-visible lift per effort than funnel-terminus fixes.

### INV-01 — Repair Broken Browse Paths (`/undefined` See All)
- **Source:** INV-01 alone, P0 (`initiative-merging.md:132`)
- **Type:** FIX — `issue-register.md:7` NAV-01 P0 HIGH
- **USER VALUE:** Very High. Primary intent CTA dead-ends to 404/`/undefined` (`page-analysis.md:56-57` VERIFIED 5+ homepage occurrences + `/samsung/undefined`×4). Journey abandoned before PLP metrics begin.
- **JOURNEY IMPACT:** Discovery — Journeys A/B/C entry. Homepage feature sections and Brand PLP sub-sections are primary alternative to Shop By Category; failure starves every downstream OPP.
- **FRICTION REDUCTION:** Eliminates P0 abandonment. `user-journey-friction.md:34` NAV-01 removes alternative path; `user-journeys.md:29` Blocked Steps VERIFIED. No recovery except manual nav.
- **BUSINESS RELEVANCE:** Conversion throughput at funnel entry — every downstream conversion lever is moot if browse path is broken.
- **STRATEGIC RELEVANCE:** Prerequisite for any maturity claim. Benchmark is irrelevant — broken links are below STANDARD; no retailer can be considered functional with 7+ dead See All.
- **WHY VERY HIGH:** Single P0 in register. Code fix + CI link-check, near-zero build cost, unlocks all discovery volume. Kept distinct per `initiative-merging.md:165` precisely because merging would hide P0.

### INV-04 — SEO Architecture (Move Buying-Guide Wall Below Fold, Hub)
- **Source:** INV-04 alone (`initiative-merging.md:133`)
- **Type:** FIX — `issue-register.md:10` IA-03 P1 HIGH · `applicability-review.md:64-66` STANDARD (Currys/Coolblue)
- **USER VALUE:** High. 1,500+ word generic prose above grid on L1/L2 (`page-analysis.md:90-91` VERIFIED) forces scroll past SEO to reach filters/products. Users seeking to narrow are delayed; SEO vs discovery compete as stacks not layers.
- **JOURNEY IMPACT:** Discovery — Journey B/C highest-friction cluster (`user-journey-friction.md:35` IA-03 pushes grid below fold). Affects every category browse.
- **FRICTION REDUCTION:** Removes scroll cost and filter-discovery delay; preserves SEO equity by re-layering (hub `/buying-guides/{category}` + CTA), not deleting.
- **BUSINESS RELEVANCE:** Discovery throughput + filter engagement + SEO crawl equity (re-layer, not trade).
- **STRATEGIC RELEVANCE:** STANDARD (Currys/Coolblue buying-guides hub `pattern-library.md:42-44` 2D). Enabler for INV-24 wizard — hub gives wizard an SEO-native landing.
- **WHY HIGH:** Re-layering is high-value discovery hygiene with broad reach, but grid is still reachable by scrolling. Friction is delay + cognitive cost, not dead-end. Users can still filter after scroll; they cannot filter without chips or buy without delivery truth.

### INV-C02 — PLP Browse Controls Hygiene (Chips, Sort, Pagination, Facet Repair)
- **Source INVs:** INV-09 + INV-10 + INV-11 → M-02 (`initiative-merging.md:51`)
- **Type:** FIX — `issue-register.md:20` FILTER-01 P1, `issue-register.md:21-23` FILTER-02 P2/03/04, `issue-register.md:24-25` SORT-01 P1/SORT-02 P2
- **USER VALUE:** Very High. PLP is where category-aware buyers (TV 55", fridge 300L) shortlist 2–3 candidates. Without chip summary, selected state beyond per-row highlight, with `Select Sort Option` placeholder and `Show 12 <of 1> 1` model obscuring totals, and with empty `Customer Review` heading + competing price slider+buckets + `Screen` vs `Display Size` duplication, users cannot narrow with confidence.
- **JOURNEY IMPACT:** Discovery/decision — Journey B shortlist is highest-friction cluster (`user-journey-friction.md:38-39` FILTER-01/SORT-01/price-duplication). Affects all filtered PLPs, Brand PLP `/samsung`, Search `/search`.
- **FRICTION REDUCTION:** Eliminates visibility-of-system-status violation (Nielsen) and taxonomy paralysis. Cross-journey top-5 friction (`user-journey-friction.md:147` FILTER-01/SORT-01 among most co-occurring). `product-discovery.md:74-88` facets VERIFIED present but feedback missing.
- **BUSINESS RELEVANCE:** Discovery-to-shortlist conversion; filter/sort engagement is pre-condition for PDP view and compare.
- **STRATEGIC RELEVANCE:** STANDARD baseline — counted as remediation not opportunity per `pattern-library.md:9-18` expectation gap. Absence is conspicuous on any electronics PLP.
- **WHY VERY HIGH:** Three code owners but one PLP template; single QA release fixes the sharpest browse bottleneck. Journey cannot shortlist efficiently without it. Benchmark maturity = STANDARD, so maturity without it is not credible.

### INV-06 — Homepage Prioritization & Performance Budget
- **Source:** INV-06 alone (`initiative-merging.md:135`)
- **Type:** IMPROVEMENT — `issue-register.md:13` DISC-01 P1, `issue-register.md:46` MOBILE-01 P2 · `applicability-review.md:128-135` OPP-15 QUESTIONED deferred
- **USER VALUE:** Medium. 7+ serialized mini-grids + 68 DOM images on PDP / 68+ homepage images `page-analysis.md:48-54` + `product-page-variations.md:49` create cognitive overload and low-bandwidth mobile burden (Bangladesh mobile-first). Benefit is faster orientation and scroll economy.
- **JOURNEY IMPACT:** Discovery entry (Journey B/C homepage re-entry, mobile).
- **FRICTION REDUCTION:** Reduces overload and load time, not a task failure. No dead-end removed; browsing remains possible but heavy.
- **BUSINESS RELEVANCE:** Engagement/scroll-depth + mobile bounce; indirect conversion via performance.
- **STRATEGIC RELEVANCE:** Valid but weakest evidence among discovery improvements. Full affinity reorder (OPP-15) explicitly QUESTIONED/`pattern-library.md:184-189` deferred until P0 hygiene proven; this triage (cut, not reorder) is hygiene, not differentiator.
- **WHY MEDIUM:** Subtraction (budget carousel count + lazy-load) helps but does not unblock decision or trust at price moment. Reach is broad (homepage) but depth shallow. Higher-value discovery fixes (C02, C03) outrank it for funnel impact.

### INV-C03 — Intelligent Search & Recovery (Autocomplete + Recent + Recovery)
- **Source INVs:** INV-07 + INV-08 → M-03 (`initiative-merging.md:52`)
- **Type:** NEW (gated: Stage1 P0, Recovery P1b) — `issue-register.md:17-19` SEARCH-01 P1, SEARCH-02 P3, SEARCH-03 P2 · `applicability-review.md:83-92` VALIDATED
- **USER VALUE:** Very High. "Know exactly what I want" buyer (Daikin `FTKL12TV16WD`, Haier `H55P7UX` `page-analysis.md:111`) has no fast-path: `Search Here` placeholder generic (`issue-register.md:18` SEARCH-02 P3), suggestions NOT FULLY VERIFIED (`product-discovery.md:40-43` typing timed out), recent searches not recalled. Typo `FTLK↔FTKL` or Bangla-English mix dead-ends on zero-result with no `Did you mean` (`ecommerce-capabilities.md:15` NOT TESTED).
- **JOURNEY IMPACT:** Discovery — Journey A primary (`user-journey-friction.md:10-24` P1 drop-off: primary fast-path failure pushes to heavy browse). Also brackets Journey A failure path (recovery catches remaining typos after typeahead reduces them).
- **FRICTION REDUCTION:** Eliminates full-code memorization, shortens `type→tap→PDP` vs `type→submit→PLP→select` (`pattern-library.md:99-103` Problem 7). Recovery prevents 12–18% zero-result abandonment (`pattern-library.md:103` 7C).
- **BUSINESS RELEVANCE:** Discovery conversion — highest-intent traffic (model-aware) converts best; zero-result volume recovered without merchandising overhead.
- **STRATEGIC RELEVANCE:** STANDARD since ~2018 (`pattern-library.md:101` 7A STANDARD). SKU-boost for 3+ alphanumerics is electronics-specific expectation; recent chips are cheap localStorage (`applicability-review.md:83-87`).
- **WHY VERY HIGH:** Two moments of one search capability (`applicability-review.md:89-92` brackets pre/post-submit). Same header input + same index + Bangla symmetry is BD-specific adaptation. Direct intent cannot be served by browsing alternatives; failure here is P1.

### INV-12 — Rich Media Inspection (Zoom, Pinch, Video, 360°, Dimension Overlay & AR)
- **Source:** INV-12 alone (`initiative-merging.md:137`)
- **Type:** IMPROVEMENT — `issue-register.md:26` PDP-01 P1 HIGH · `applicability-review.md:100-104` VALIDATED
- **USER VALUE:** High. High-consideration decisions (600L door swing, 65" bezel depth, AC wall piping, washer drum) under-supported by 4+ generic placeholders `page-analysis.md:134-135` + zero video (`ecommerce-capabilities.md:30` NOT OBSERVED). Remote inspection hesitation directly correlates with return/service risk.
- **JOURNEY IMPACT:** Decision-making — all considered PDP research (AC/Fridge/TV/Washer) pre-cart.
- **FRICTION REDUCTION:** Reduces pre-purchase anxiety; phased: hover-zoom/pinch+scrub+count (week, no reshoot) highest anxiety reduction per effort; functional 15–25s video per category template reuses brand reels; 360°/dimension overlay `W×H×D+ventilation gap+door swing` shared source with INV-16.
- **BUSINESS RELEVANCE:** Consideration-to-cart + return-rate reduction.
- **STRATEGIC RELEVANCE:** STANDARD hygiene — zoom since ~2018 (`pattern-library.md:60-67` Problem 4A STANDARD); video is STANDARD. Absence is conspicuous for Tk50k+ goods. AR is EMERGING phase 3, not required for baseline.
- **WHY HIGH (not VERY HIGH):** Inspection meaningfully lifts confidence but does not block purchase as absolutely as delivery/EMI/availability truth. Users can still buy without video; they hesitate. Phased viewer pipeline — first gate (zoom) is quick win, later gates asset-dependent (`applicability-review.md:104`).

### INV-13 — Delivery & Serviceability Estimator (Pincode-First Landed Cost + Fast Badge)
- **Source:** INV-13 alone (`initiative-merging.md:138`)
- **Type:** NEW — `issue-register.md:27` PDP-02 P1 HIGH · `applicability-review.md:46-49` ENHANCED (HIGH)
- **USER VALUE:** Very High. At exact price exposure users cannot answer "can this 600L/1 Ton be delivered to my district, at what fee, when, with free install?" — gate is `Enable your Location` permission (`page-analysis.md:125` VERIFIED) that hides answer until commitment; homepage `Free Installation Selective Items` not echoed per SKU (`page-analysis.md:34`).
- **JOURNEY IMPACT:** Purchase decision — Journeys B/C/E all high-ticket (Tk50k–1.5L). PDP→Cart propagation prevents checkout pincode-mismatch drop-off (`issue-register.md:38` CHECKOUT-01 P1).
- **FRICTION REDUCTION:** Moves failure before commitment. Single district/area text (not GPS permission — Bangladesh sparse formal pincodes, low trust `regional: Finding 5`) returning serviceability yes/no + SLA + fee + install flag + nearest store-pickup distance (`pattern-library.md:26-31` Problem 1).
- **BUSINESS RELEVANCE:** Conversion unblock — PDP-02 is primary P1 barrier; landed-cost truth propagates to Cart `Subtotal+Delivery+Install→Total` without re-entry (shared table with INV-14/26/28/C06).
- **STRATEGIC RELEVANCE:** STANDARD South Asia / EMERGING BD (`pattern-library.md:28` 1A/1B). Daraz Fast Delivery Aug 2026 earned badge pattern already on Transcom PLP as `EMI36` — mirroring it with `Fast Delivery` is expected. Moat vs pure marketplace.
- **WHY VERY HIGH:** ENHANCED anchors every other landed-cost row. 80% ops data / 20% memory; district text swap alone unlocks OPP-01, NEW-03, NEW-02 badge.

### INV-14 — True Cost & EMI Planner (Ownership Row + Tenure Picker + Eligibility Verdict)
- **Source:** INV-14 alone (`initiative-merging.md:139`)
- **Type:** NEW — `issue-register.md:31,44` PDP-06 P2, CONSISTENCY-01 P3 · `applicability-review.md:94-98` ENHANCED
- **USER VALUE:** Very High. Sticker illusion: EMI eligibility inconsistent — absent as silence on Haier 622IBG Fridge `product-page-variations.md:55` vs present elsewhere; energy hidden as `EER 3.15` token; install fee gated → monthly affordability unknown at decision moment. BD buyer needs `Upfront+Delivery+Install+Energy→EMI/mo` with tenure picker 3/6/12/24/36 + tariff slider.
- **JOURNEY IMPACT:** Decision + purchase — Journeys B/C/E at PDP decision and Cart total hesitation (`user-journey-friction.md:109` EMI inconsistency surprises financing buyers).
- **FRICTION REDUCTION:** De-risks financing at price exposure; explicit verdict `EMI not available for this SKU → see EMI Bank List` replaces silence (trust repair `pattern-library.md:79` 5C); offline form latency `blocked amount → signed form 3d → bank converts 5–10d` disclosed (`applicability-review.md:96-98` Pickaboo 32 banks BDT 5k / Daraz 10k).
- **BUSINESS RELEVANCE:** Conversion for financed high-ticket; cart inherits grouped breakdown, reducing paywall surprise.
- **STRATEGIC RELEVANCE:** DIFFERENTIATOR in BD — few retailers combine energy+install+EMI in one row (`pattern-library.md:72-80` Problem 5 DIFF). EMI36 badge exists but interactive picker is EMERGING.
- **WHY VERY HIGH:** Regional offline truth enhances scope beyond typical EMI widget. BDT 5k threshold suppress per `product-page-variations.md:104` keeps row honest. Financing is primary affordability lens for Tk1.38L fridge.

### INV-C04 — Spec Literacy & Warranty Truth (Jargon Decoder + Energy Translator + Warranty Legend Propagation)
- **Source INVs:** INV-15 + INV-18 → M-04 (`initiative-merging.md:53`)
- **Type:** FIX (dominant) — `issue-register.md:29-30` PDP-04 P2, PDP-05 P2, `issue-register.md:35` TRUST-01 P2
- **USER VALUE:** High. Spec tab reveals `EER/R32/HQLED/Dolby Vision/Twin inverter/Coanda` without explainer; warranty legend `Service-24M/Parts-24M/Compressor-120M` vs `Motor-300M` vs `Special Component-0M` implausible (`product-page-variations.md:61`); buyer leaves to Google. Content-only glossary CMS 25–40 terms category-scoped solves literacy without backend.
- **JOURNEY IMPACT:** Decision-making — all PDP research moments; unlocks INV-14/16/24 literacy (energy math, install guard, finder explainability) per `applicability-review.md:105-109` VALIDATED.
- **FRICTION REDUCTION:** Tap-any-term drawer `EER 3.15 = 1.1kW → ~Tk Y/mo @8h/day` + energy A–G+QR fiche + `Special Component = Compressor/Panel/Motor per category` (`pattern-library.md:86-92` 6C). Normalize `Parts-0M` display + propagate trust claims to price context (`page-analysis.md:34` homepage bar echoed at PDP/Cart).
- **BUSINESS RELEVANCE:** Decision confidence + trust; prerequisite multiplier — every finder/planner output becomes explainable.
- **STRATEGIC RELEVANCE:** STANDARD (EU energy communication) / EMERGING inline decoder (`pattern-library.md:91` 6C). Prerequisite before interactive finders.
- **WHY HIGH:** Low complexity, high unlock value, but literacy alone does not convert if delivery/EMI still gated. It is the multiplier that must ship before or with finders/calculator — hence HIGH not VERY HIGH.

### INV-16 — Installation Feasibility Checker (Pass/Fail Verdict + Priced Basket, Gate2 ops-gated)
- **Source:** INV-16 alone (`initiative-merging.md:141`)
- **Type:** NEW — `issue-register.md:28` PDP-03 P1 HIGH · `applicability-review.md:110-117` ENHANCED
- **USER VALUE:** High for large-appliance slice. No feasibility signal before ordering — AC without outdoor wall/drain/bracket, 600L without ventilation gap/door swing, washer without inlet/drain (`product-page-variations.md:60` NOT OBSERVED). Most expensive post-purchase failure is failed install.
- **JOURNEY IMPACT:** Purchase + post-purchase — AC/Fridge/Washer PDP→Cart→fulfilment. Gate1 content verdict prevents ordering undeliverable sites; Gate1b priced basket SKU converts vague inclusion into purchasable scope; Gate2 slot booking is ops-gated calendar.
- **FRICTION REDUCTION:** Per-SKU toggles → `✓ Feasible — Add to Cart` / `⚠ Requires bracket Tk 2,500 — order bundle` with fee table `Free/Paid+Tk X` shares table with INV-13/14; dimension spec normalization `W×H×D+gap+swing` shared with INV-12 (`pattern-library.md:132-137` 10A).
- **BUSINESS RELEVANCE:** Failed-install waste elimination + large-appliance differentiation vs Daraz/Pickaboo marketplace who cannot credibly slot-book (moat for owned fleet + Store Locator `page-analysis.md:199-204`).
- **STRATEGIC RELEVANCE:** DIFFERENTIATOR / EMERGING (`pattern-library.md:137` 10A). Gate1 ships as content; booking deferred behind capacity feed.
- **WHY HIGH:** High value but scoped to AC/Fridge/Washer and suppressed for Personal Care (`product-page-variations.md:104`). Not universal like delivery/EMI. Gate2 is ops-gated high complexity — value realized stepwise.

### INV-17 — Variant & Family Navigator (Sibling Chips with Delta & Stock)
- **Source:** INV-17 alone (`initiative-merging.md:142`)
- **Type:** NEW — `issue-register.md:33` PDP-08 P2 HIGH · `applicability-review.md:118-122` VALIDATED
- **USER VALUE:** High. PLP `Display Size 55"(10) 43"(7) 65"(7)` `page-analysis.md:86` proves families exist, but PDP has no jump — 55" TV PDP cannot reach 65" sibling without returning to PLP. Only AC shows `Choose Ton 1 / 1.5` `product-page-variations.md:52`. Family exploration violates expectation.
- **JOURNEY IMPACT:** Decision — PDP variant exploration for all families; vault discovery without PLP loop.
- **FRICTION REDUCTION:** Sibling chips with price delta + stock badge `65" +Tk18,000 In stock | 75" Currently Unavailable` navigates PDP→sibling PDP (new URL) preserving `?familyRef` for Compare/Recently Viewed; price/availability live; placed above estimator so size change re-validates delivery/energy/EMI (`pattern-library.md:119-128` 9A/9B/9C).
- **BUSINESS RELEVANCE:** Cross-sell without new SKUs — top 30 roots ≈70% high-ticket (`sitemap-analysis.md:44` Haier 12, Tron 9). Compensates for flat PDP URL (IA-01) by giving hierarchy URL lacks.
- **STRATEGIC RELEVANCE:** STANDARD (Apple/Samsung chips `pattern-library.md:125` 9A). Graph `model_root→variants by tonnage/litres/display size/kg` drives 4 surfaces but is one modeling task.
- **WHY HIGH:** No duplicate in pool (`duplicates-and-overlaps.md:139` FEA-04 alone). High leverage for vault, but PDP variant exploration is one step narrower than site-wide discovery or paywall truth.

### INV-20 — Social Proof Pipeline (Ratings, Review Count, Badges, Facet, Q&A)
- **Source:** INV-20 alone (`initiative-merging.md:143`)
- **Type:** NEW — `issue-register.md:32` PDP-07 P1 HIGH, `issue-register.md:21` FILTER-02 P2 · `applicability-review.md:124-126` ENHANCED
- **USER VALUE:** Very High. Tabs exist `page-analysis.md:131-133` + `ecommerce-capabilities.md:31-33` headings only, no aggregate stars/count/cards visible (`product-page-variations.md:62`); PLP card lacks rating to bias shortlist; `Customer Review` facet is empty heading (FILTER-02 P2 expectation violated). High-ticket research lacks peer validation — users rely on price alone.
- **JOURNEY IMPACT:** Decision — Journeys B/C shortlist (PLP bias) and PDP confidence. Also populates broken filter, repairing PLP feedback (INV-C02 wiring).
- **FRICTION REDUCTION:** Pipeline `Collection→Moderation→Aggregation→Badges→Facet` (`pattern-library.md:87-90` 6B): PDP header `4.6★ (212)` + PLP card badge + review facet `★★★★&up (41)` indexed + Q&A `Verified Purchase` marker; suppressed `n<5 → Be first to review — ask Q` (no fake `5.0 (1)`).
- **BUSINESS RELEVANCE:** Proven conversion lift for electronics; turns empty facet into decision facet; seeds Q&A to reduce support load.
- **STRATEGIC RELEVANCE:** STANDARD since ~2016 (`pattern-library.md:90` 6B). In BD post-Evaly context, verified-purchase matters disproportionately; pipeline before badges is maturity baseline.
- **WHY VERY HIGH:** Paired with INV-21 as two-layer trust (`applicability-review.md:124-126`). Building badges without pipeline yields empty `Be first` at best, fake counts at worst. Conspicuous absence for Tk80k+.

### INV-21 — Authenticity / Authorized-Retailer Badging at Price Context
- **Source:** INV-21 alone (`initiative-merging.md:144`)
- **Type:** NEW — `applicability-review.md:142-144` NEW-01 STANDARD BD
- **USER VALUE:** Very High. Authorization is true (13 authorized brands `sitemap-analysis.md:26` Samsung/Daikin/Haier) but invisible at decision moment. PDP brand link generic `page-analysis.md:112`; `ecommerce-capabilities.md:46` warranty reads as claim not proof; homepage `Original Product Guaranteed` not echoed PDP/Cart (`issue-register.md:35` TRUST-01 P2).
- **JOURNEY IMPACT:** Purchase — all considered PDP decisions where Tk80k+ stake meets trust hesitation.
- **FRICTION REDUCTION:** PDP hero lockup `✓ Authorized — Official Warranty` + `Authenticity Guarantee (replacement + 3× if fake)` + Mall/flagship tag + seller identity + warranty detail sheet (`pattern-library.md:87-90` 6A DarazMall/Pickaboo/Bikroy Verified). No backend — reuses partnerships.
- **BUSINESS RELEVANCE:** Trust — marketplace variance is BD #1 barrier post-Evaly, penetration 2–3% barrier `regional Finding 1`. Reuses partnerships, no backend, immediate.
- **STRATEGIC RELEVANCE:** STANDARD BD / DIFFERENTIATOR retailer PDP proof (`pattern-library.md:89` 6A). Companion to INV-20: ratings = peer proof, authenticity = institutional proof (`applicability-review.md:174`).
- **WHY VERY HIGH:** Highest trust ROI per effort in Bangladesh context. Trust dissipates PDP/Cart precisely where built homepage trust must be proved.

### INV-22 — Browse Resumption (Recently Viewed Rail + Continue Shopping Deep-Link)
- **Source:** INV-22 alone (`initiative-merging.md:145`)
- **Type:** NEW — `issue-register.md:14` DISC-02 P1 HIGH · `applicability-review.md:51-54` VALIDATED
- **USER VALUE:** High. No trail to resume interrupted high-consideration journeys (`personalization-current-state.md:9-10` NOT OBSERVED 20+ reads; empty cart/wishlist `page-analysis.md:159-164` no history). Returning users rebuild hierarchy from root, re-find last filtered PLP/search (Journey F wholly unserved `user-journey-friction.md:130-131` P1).
- **JOURNEY IMPACT:** Retention/engagement — Journey F + Journeys B/C multi-session + empty-cart recovery.
- **FRICTION REDUCTION:** `localStorage viewHistory (8)+ lastPlpUrl + compareQueue + searchHistory` shared with INV-C03/INV-23, migrated on OTP; rail thumbnail+price+stock + deep-link card `Smart TV: Samsung 55"+, 1–2L (14) → Continue` reopens filtered PLP/search with query+facets reapplied (`pattern-library.md:108-116` Problem 8).
- **BUSINESS RELEVANCE:** Cheapest retention lift; recaptures highest-intent returners; shortens time-to-shortlist; empty-state injection converts abandonment moment into resumption.
- **STRATEGIC RELEVANCE:** STANDARD (`pattern-library.md:112` 8A STANDARD). No backend stage1, validated without BD adaptation risk.
- **WHY HIGH (not VERY HIGH):** Retention high but purchase conversion must convert first visit before retention compounds. 80% of returner value achievable with this + Recent Searches; full affinity reorder (INV-06/OPP-15) deferred. HIGH not VERY HIGH because not a first-visit funnel blocker.

### INV-23 — Smart Compare Workspace (Persistent, Auto-Populated, Decisive & Total-Cost Aware)
- **Source:** INV-23 alone (`initiative-merging.md:146`)
- **Type:** NEW — `issue-register.md:41` INTERACTION-01 P1 HIGH, `issue-register.md:15` DISC-03 P2 · `applicability-review.md:56-60` VALIDATED
- **USER VALUE:** High. `/compare` empty 3-slot expects hand-typed `Model name or part of product details`×3 `page-analysis.md:173-178` — recall burden high; Journey D (compare 3 Smart TVs/Fridges) is high-friction. Decisive attributes buried in 40 rows; total ownership invisible.
- **JOURNEY IMPACT:** Decision — Journey D + Journey B shortlist 2–3 (`user-journey-friction.md:75-93` D P1: core for high-ticket).
- **FRICTION REDUCTION:** Sticky bar `Compare (2/3)` accumulates taps (session+auth) → auto-populated `/compare`; search remains as add-more only; decisive-attribute tint per category (AC `EER/tonnage/R32/Applicable sq ft` etc.) collapses 40 rows to 6–8; verdict strip; total-cost pin row (`Price+Install+1yr Energy+EMI/mo` from INV-13/14) pinned; diff-highlight checkbox; share URL for WhatsApp family decision (`pattern-library.md:47-56` Problem 3).
- **BUSINESS RELEVANCE:** Consideration-to-cart for big ticket; share URLs drive referral in BD WhatsApp family huddle.
- **STRATEGIC RELEVANCE:** STANDARD considered electronics (`pattern-library.md:53` 3A STANDARD; verdict strip DIFFERENTIATOR). Coolblue/Best Buy/RTINGS evidence.
- **WHY HIGH:** Fixes sharpest high-ticket decision gap with no ML (spec normalization limited to decisive rows). Not VERY HIGH because subset journey (D) vs universal browse/search/purchase blocked paths.

### INV-24 — Guided Selling Framework (Need→Constraints→Budget Finder, 5 Lenses + Hub)
- **Source:** INV-24 alone (`initiative-merging.md:147`)
- **Type:** NEW — `applicability-review.md:62-67` ENHANCED
- **USER VALUE:** High. Shoppers must translate life need (room size/top-floor/sun, family size, viewing distance, household load, water TDS) into specs (tonnage/EER, litres/door, size/resolution, kg, filter) themselves (`opportunity-pool.md:54-68` OPP-04). SEO wall is generic text not interactive helper (`issue-register.md:10` IA-03).
- **JOURNEY IMPACT:** Discovery/decision — Journeys B/C primary, Journey A entry via finder. Outputs filtered PLP + PDP verdict chip `Right for your 120 sq ft — 1.5 Ton`.
- **FRICTION REDUCTION:** Single 3-step wizard `Need→Constraints→Budget/Preference` + lenses AC (sq ft×height×top-floor→tonnage, LG `20 BTU/sq ft` rule), Fridge (AO `18L=1 bag` + 7-step measure guard), TV (distance→size→resolution/panel), Washer, Kitchen/Purifier (`pattern-library.md:34-44` Problem 2). Lenses share wizard UI + PLP filter mapping; no ML.
- **BUSINESS RELEVANCE:** Converts problem-aware traffic to filtered shortlist; reduces wrong-size returns; each lens independently shippable (AC first = largest ticket, fewest SKUs, variant proof `product-page-variations.md:52`).
- **STRATEGIC RELEVANCE:** DIFFERENTIATOR vs Daraz/Pickaboo marketplace — rule tables + family graph + verdict chip cannot be copied with marketplace breadth (`applicability-review.md:62-67`). Kitchen/Purifier lens MED confidence (7 PDPs).
- **WHY HIGH:** ENHANCED is the differentiator moat, but buyers can still browse and filter without wizard. Value is guided confidence and wrong-size prevention, not hard unblock. INV-04 hub is enabler; wizard is P1 decision support.

### INV-25 — Complete-the-Setup (Bundles, FBT & Consumable Attach)
- **Source:** INV-25 alone (`initiative-merging.md:148`)
- **Type:** NEW — `applicability-review.md:69-72` VALIDATED
- **USER VALUE:** Medium. PDP sells isolated unit (TV without mount, AC without stabilizer/bracket/copper wire, washer without stand/detergent, purifier without cartridge); total ownership invisible until separate trip; Related Products thin single card `product-page-variations.md:65-66`, FBT NOT OBSERVED `ecommerce-capabilities.md:56`.
- **JOURNEY IMPACT:** Purchase/AOV — Journey E cart-attach moment; post-add confidence.
- **FRICTION REDUCTION:** Complement rule engine per family (AC→stabilizer, TV→soundbar+mount, etc.) as toggleable PDP bundle row + Cart post-add rail `Complete your setup` with grouped-line pricing; purifier cartridge cadence every 6m converts one-time to recurring (`pattern-library.md:143-152` 11A/11B).
- **BUSINESS RELEVANCE:** AOV/attach rate + "need extra part" dissatisfaction reduction; mandatory-kit model ties to INV-16 install-failure prevention.
- **STRATEGIC RELEVANCE:** STANDARD for large appliances (Home Depot mandatory hookup kits). Suppressed for low-ticket trimmer/mixer `Tk 3k–5k` where attach generic; validated high for AC/TV/Fridge/Washer/purifier.
- **WHY MEDIUM:** Meaningful for considered families but attach is complementary, not prerequisite to purchase decision. Rule engine complexity + family inventory dependency lower immediate funnel priority vs delivery/EMI/trust rows.

### INV-26 — Plural Payment Row (COD + bKash/Nagad + Card-on-Delivery + Online/EMI, District-Aware)
- **Source:** INV-26 alone (`initiative-merging.md:149`)
- **Type:** NEW — `issue-register.md:38` CHECKOUT-01 P1 · `applicability-review.md:144-146` NEW-03 STANDARD BD
- **USER VALUE:** Very High. PDP only shows `Avail Bank EMI` for cardholders — excludes 75–90% COD buyers (`regional-commerce.md:65-74` Finding 4 Levree 75–90% COD + bKash wallet growth). PDP/Cart truth `◉ COD ✓ | ◉ Card on Delivery (Swipe) ✓ | ◉ bKash/Nagad ✓ | ◉ Online Card (EMI eligible) ✓` with district-aware `Delivery to Rajshahi: COD available` from same zone matrix as INV-13.
- **JOURNEY IMPACT:** Purchase — all PDPs at price exposure + Cart Order Summary; unblocks uncarded buyer at decision moment (`user-journeys.md:135` `Cash on Delivery, Net Banking, Credit Card, easy EMI` homepage-only today).
- **FRICTION REDUCTION:** Plural row reframes choice itself as trust (Pickaboo "for your best convenience" `pattern-library.md:161` 12A). No backend beyond zone availability; shares EMI master with INV-14.
- **BUSINESS RELEVANCE:** Conversion — no BD checkout can be card-first; choice assures COD buyer before paywall.
- **STRATEGIC RELEVANCE:** STANDARD BD — Daraz/Pickaboo/ChalDal/Rokomari plural row is hygiene (`pattern-library.md:161` STANDARD). Absence excludes majority persona.
- **WHY VERY HIGH:** At boundary with HIGH, elevated to VERY HIGH because 75–90% market share makes card-first a de-facto exclusion. Text + zone availability ships with INV-13 table; immediate trust ROI. If forced to 8 VERY HIGH, this would be first borderline to downgrade to HIGH — but BD context justifies VERY HIGH.

### INV-C06 — Cart Drawer & Feedback System (Drawer, Stepper, Landed-Cost Truth, Toasts, CTA Hierarchy)
- **Source INVs:** INV-27 + INV-31 + INV-19 → M-06 (`initiative-merging.md:55`)
- **Type:** FIX/NEW — `issue-register.md:36` CART-01 P1, `issue-register.md:37` CART-02 P2, `issue-register.md:38` CHECKOUT-01 P1, `issue-register.md:42` FEEDBACK-01 P1, `issue-register.md:34` PDP-09 P3 · `applicability-review.md:150` NEW-06 STANDARD
- **USER VALUE:** Very High. Purchase intent stalls at funnel terminus: duplicate `Add To Cart ×2` `page-analysis.md:126-128` without role distinction, no toast/count after tap (`user-journey-friction.md:105` FEEDBACK-01 duplicate clicks), empty cart disables Checkout with no inline recovery `page-analysis.md:159-164` `You have not added…`, checkout steps undiscoverable before cart+auth (`user-journeys.md:126-131` empty-cart blocked), delivery fee not previewed in Order Summary `page-analysis.md:161-162` Subtotal ৳0.
- **JOURNEY IMPACT:** Purchase — Journey E funnel to cart→checkout is P0/P1 boundary (`user-journey-friction.md:117` broken discovery + invisible checkout starve funnel before Journey E starts).
- **FRICTION REDUCTION:** Slide-in mini-cart on Add confirmation; `Subtotal + Delivery + Install → Total` truth row (shared zone/fee table with INV-13/14/26); progress stepper `Cart → Delivery → Payment → Confirm` with trust micro-copy; feedback toast on every add/wishlist/compare (`pattern-library.md:164` 12D STANDARD Apple/ASOS/Best Buy drawer); single sticky primary CTA + secondary Compare/Wishlist; empty-state injects INV-22 rails.
- **BUSINESS RELEVANCE:** Conversion terminus — visibility of system status + landed-cost truth before paywall prevents paywall surprise and duplicate-click abandonment.
- **STRATEGIC RELEVANCE:** STANDARD cart drawer + stepper (`pattern-library.md:164` 12D STANDARD). Elevated from remediation tail M-01 to build unit per benchmark (`applicability-review.md:150`).
- **WHY VERY HIGH:** Three PDP→Cart symptoms one system. Without drawer/stepper/truth/toast, delivery/EMI estimators have no price-context surface to propagate to. P0-adjacent funnel blocker.

### INV-28 — Open-Box Delivery + OTP Doorstep Verification
- **Source:** INV-28 alone (`initiative-merging.md:151`)
- **Type:** NEW — `applicability-review.md:145` NEW-02 EMERGING BD
- **USER VALUE:** Medium. Solves doorstep anxiety for 600L/65"/1 Ton + COD 75–90% dispute risk — rider opens outer + brand packing in front of customer, checks damage/correct item/IMEI/accessories; OTP shared only after satisfaction, photographed + reference logged (`pattern-library.md:162` 12B Flipkart OBD both packings + OTP). PDP badge `Eligible for Open Box Delivery at your pincode ✓` shares INV-13 zone truth.
- **JOURNEY IMPACT:** Post-purchase/doorstep — after PDP/Cart decision; reassurance before paywall via eligibility badge.
- **FRICTION REDUCTION:** Documentation burden shifts from buyer (self-unbox → return fight) to logistics; proves `Original Product Guaranteed`.
- **BUSINESS RELEVANCE:** Trust differentiator + COD dispute reduction; owned Store Locator `page-analysis.md:199-204` + logistics gives credible Wishmaster vs pure marketplace.
- **STRATEGIC RELEVANCE:** STANDARD India / EMERGING BD (`applicability-review.md:145` EMERGING differentiator; `pattern-library.md:162` 12B). Ops cost justifies only for >Tk20k electronics.
- **WHY MEDIUM:** High value for large-ticket but deferred until zone truth (INV-13) proven. Eligibility badge is quick trust signal; full doorstep protocol is ops-heavy and post-purchase. Not funnel entry blocker.

### INV-C05 — Human Support Spine (WhatsApp/Messenger + Hotline + Store Visit)
- **Source INVs:** INV-29 + INV-30 → M-05 (`initiative-merging.md:54`)
- **Type:** NEW/IMPROVEMENT — `page-analysis.md:14` `Need help? Click Here `, `page-analysis.md:18-19` `16212 9AM–9PM` footer-only, `page-analysis.md:199-204` Store Locator, `applicability-review.md:147-149` NEW-04/05 12C
- **USER VALUE:** Medium-High. Tier-2/3 high-ticket needs human reassurance in funnel, not footer-only (`issue-register.md:35` TRUST-01 P2). Footer hotline not in decision sightline; `Need help?` not conversational; PDP `Share` icon lacks WhatsApp deep-link; Store Locator VERIFIED but not linked from PDP.
- **JOURNEY IMPACT:** Purchase assist — Journeys B/C/E trust moment; `user-journey-friction.md:71` no `Talk to expert` inline in filter/PDP spec vicinity.
- **FRICTION REDUCTION:** Elevate `16212` to sticky call bar on PDP/Cart + PDP Store Pickup estimator shows nearest 3 stores + `Schedule your visit` district cards + `Track Order/Service` `page-analysis.md:7` wiring; `Need help?` → human WhatsApp/Messenger PDP deep-link `Share via WhatsApp — Ask agent about this fridge` + hotline fallback; optional premium manager for >Tk50k (`pattern-library.md:163` 12C).
- **BUSINESS RELEVANCE:** Trust reassurance + assisted conversion for low self-serve confidence; same ops dependency (agent roster + store inventory) as INV-13 pickup alt.
- **STRATEGIC RELEVANCE:** STANDARD BD hotline in funnel is hygiene; human WhatsApp manager EMERGING (`pattern-library.md:163` STANDARD/EMERGING). Deep-links, no platform build.
- **WHY MEDIUM:** Trust layer important but conversational care is support surface, not core product truth. Sticky hotline/store bridge is hygiene-level, WhatsApp manager is differentiator with roster dependency. Ranks below price-context trust (INV-21) and proof pipeline (INV-20) for direct decision impact.

### INV-32 — Authentication Friction & Guest→Auth Continuity (OTP, History Migration)
- **Source:** INV-32 alone (`initiative-merging.md:153`)
- **Type:** FIX — `issue-register.md:39-40` AUTH-01 P2, AUTH-02 P2
- **USER VALUE:** Medium. Login requires phone OTP only — no password/social alternative, phone input split into two fields (`user-journeys.md:159` +880 + two textboxes); wishlist/compare as guest require login for persistence but give no inline prompt (`issue-register.md:40` AUTH-02 guest clicks appear to do nothing; `page-analysis.md:159-171` `/wishlist` guest empty with `about:blank`). Returning users cannot restore saves.
- **JOURNEY IMPACT:** Retention/enablement — Journey F + Journeys B/C resumption gates; gate for INV-07/22/23/31 `localStorage`→account migration (`initiative-merging.md:115` resumption store).
- **FRICTION REDUCTION:** OTP split-field repair + no-password continuity + history migration (`viewHistory+lastPlpUrl+compareQueue+searchHistory`) on OTP; inline guest prompt explains outcome before login.
- **BUSINESS RELEVANCE:** Auth base enables wishlist/compare persistence, price-watch (INV-33), and personalization, but COD purchase does not require auth (`regional Finding 4` 75–90% COD).
- **STRATEGIC RELEVANCE:** Hygiene fix, not capability expansion. `personalization-current-state.md:13` persistence lifecycle gap.
- **WHY MEDIUM:** Critical path for retention and later personalization, but not a first-visit purchase blocker — guest can still search, filter, view PDP, add to cart, and pay COD without auth. Downgraded from HIGH because COD market tolerates guest checkout; auth is enablement, not conversion terminus.

### INV-33 — Exchange & Return Value (14-Day Badge + Cross-Category AI Diagnostics + Timeline)
- **Source:** INV-33 alone (`initiative-merging.md:154`)
- **Type:** NEW — `issue-register.md:43` FEEDBACK-02 P2 · `applicability-review.md:150` NEW-07 EMERGING · `opportunity-pool.md:86-100` OPP-06 QUESTIONED layer
- **USER VALUE:** Medium. Exchange hub `/exchange` `page-analysis.md:208-212` + PLP `Get Exchange up to 12000 Tk` `product-discovery.md:119-120` exist but valuation/execution opaque (`ecommerce-capabilities.md:52` NOT TESTED); PDP lacks badge next to `In stock` `product-page-variations.md:58`; `TRUST-01` `Exchange Program` not echoed PDP; `Get Stock Alert` has no ETA (`issue-register.md:43` FEEDBACK-02 trust low). Idle BD households (second fridge/washer) as currency.
- **JOURNEY IMPACT:** Post-purchase lifecycle + trust at PDP (pre-decision badge).
- **FRICTION REDUCTION:** PDP badge `14-Day Hassle-Free Return ✓` + `Exchange value: Estimate up to Tk 12k → doorstep inspection → OTP` beneath price; cross-category (fridge→washer etc.); 10-step AI condition check within minutes (Flipkart ReCommerce 26 categories `regional-commerce.md:113-122`).
- **BUSINESS RELEVANCE:** Dormant-demand capture + trust baseline after Daraz expanded 14-day to ALL products 2025 (TBS Ben Yi) — expectation is now table-stakes.
- **STRATEGIC RELEVANCE:** EMERGING BD / STANDARD India (`applicability-review.md:150`). Ops feed for valuation and slot capacity gates AI diagnostics; QUESTIONED sequencing per `applicability-review.md:74-81` due to AUTH/ops dependency.
- **WHY MEDIUM:** Lifecycle differentiator, but P2 after delivery/EMI/auth base proves. Starts static "up to + inspection truth" before AI; high post-purchase value, lower immediate funnel urgency vs price-context truth.

### INV-34 — Accessibility & Icon System (Labeled Controls, Contrast, Keyboard Order)
- **Source:** INV-34 alone (`initiative-merging.md:155`)
- **Type:** FIX — `issue-register.md:45` ACCESS-01 P2 · `page-analysis.md:7-14` header icons `  `
- **USER VALUE:** Medium for affected users, low reach. Icon-only controls in header (cart ``, wishlist ``, share ``) lack visible text labels; color contrast and focus order not enumerated — screen-reader/keyboard discovery failure.
- **JOURNEY IMPACT:** All journeys for assistive-technology users; narrow but total for that cohort.
- **FRICTION REDUCTION:** Labeled controls + WCAG contrast + keyboard order restores access.
- **BUSINESS RELEVANCE:** Compliance / inclusion / legal risk; not direct conversion lever for majority.
- **STRATEGIC RELEVANCE:** WCAG hygiene — distinct from feedback/cart drawer (`initiative-merging.md:183` keep separate for tracking). Not benchmark-competitive; required for maturity but not market differentiator.
- **WHY LOW:** Necessary, non-debatable, but narrowest user-reach among 25 and lowest funnel leverage. Sequencing keeps it visible (WCAG audit) without competing with P0/P1 conversion blockers. Only LOW in set for that reason — not "not needed".

---

## Cross-Cutting Observations

1. **Trust is two-layer and sits at price context.** INV-20 (peer proof) + INV-21 (institutional proof) together repair `TRUST-01 P2` — neither alone is VERY HIGH in isolation in many markets, but in post-Evaly BD (`regional Finding 1` 2–3% penetration) the pair is VERY HIGH. Both share PDP hero lockup near price, same moderation/authenticity narrative (`applicability-review.md:142-144`).
2. **Paywall truth is four rows, one table.** INV-13 (delivery) + INV-14 (EMI/energy) + INV-26 (plural payment) + INV-C06 (drawer/stepper truth row) feed from single District→Zone/SLA + delivery/install fee + EMI master (`applicability-review.md:158-169`). Building any one without the others wastes motion — value compounds when shipped as platform block.
3. **Retention is cheap via `localStorage`.** INV-C03 Recent + INV-22 rail + INV-23 queue + INV-32 migration are HIGH/MEDIUM with no backend stage1 (`pattern-library.md:180` 7A/8A). They deliver 80% of returner value that OPP-15 affinity reorder (`applicability-review.md:128-135` QUESTIONED) would at fraction of cost — hence INV-06 MEDIUM.
4. **Content-first gates beat ops-gated bookings.** INV-C04 (glossary), INV-16 Gate1 (checker toggles), and INV-04 hub ship without slot-calendars or feed — prerequisite literacy. Booking/cadence/AI diagnostics (INV-16 Gate2, INV-25 cadence, INV-33 AI) are MEDIUM until feed proven.

---

## Evidence Index

| Claim | File:Line |
|-------|-----------|
| 25 consolidated (34→25, 6 merges) | `05-prioritization/initiative-merging.md:15-23` |
| 32 issues P0=1 P1=13 + severities | `02-ux-audit/issue-register.md:7-46` |
| Journeys A–F friction + drop-off risks | `02-ux-audit/user-journey-friction.md:5-148` |
| Journeys J1–J9 VERIFIED/NOT TESTED tiers | `01-current-state/user-journeys.md:7-273` |
| `/undefined` 5+ VERIFIED, flat PDP 101, orphan `/tv-av`, trailing hyphen 4 | `05-prioritization/master-initiative-inventory.md:84-98` · `00-input/sitemap-analysis.md:27,74-77,132` |
| SEO wall 1,500+ words pushes grid below fold | `01-current-state/page-analysis.md:90-91` |
| `Search Here` generic, suggestions NOT FULLY VERIFIED, zero-result NOT TESTED | `01-current-state/ecommerce-capabilities.md:12-15` · `01-current-state/product-discovery.md:40-43` · `01-current-state/page-analysis.md:9` |
| PLP chips missing, sort placeholder, dual price, Screen vs Display Size | `01-current-state/page-analysis.md:75-86` · `01-current-state/product-discovery.md:74-88` · `02-ux-audit/issue-register.md:20-25` |
| PDP gate `Enable your Location`, no install line, warranty `Parts-0M/Motor-300M`, no EMI on fridge, no video, 68 images | `01-current-state/page-analysis.md:125-128,134-135` · `01-current-state/product-page-variations.md:49-62,104` |
| `Add To Cart ×2`, cart empty dead-end, Checkout disabled | `01-current-state/page-analysis.md:126-128,159-164` · `01-current-state/user-journeys.md:98-148` |
| `Need help? Click Here `, `16212 9AM–9PM`, Store Locator `Schedule your visit` | `01-current-state/page-analysis.md:14,18-19,199-204` |
| 15 OPPs + NEW-01..08 classification VALIDATED/ENHANCED/QUESTIONED | `04-benchmark/applicability-review.md:22-38,138-152` |
| 12 problems / 38 variations maturity STANDARD/EMERGING/DIFF | `04-benchmark/pattern-library.md:9-18,22-165` |

*Value analysis generated 2026-09-03. Next Step 4 will sequence the 25 by value × dependency × effort.*
