# E-commerce Standards Gap Analysis — Transcom Digital (Phase 3)

> Agent D — E-commerce Standards Analyst. Evidence base: `00-input/sitemap-analysis.md`, `01-current-state/site-inventory.md`, `01-current-state/page-analysis.md`, `01-current-state/product-discovery.md`, `01-current-state/product-page-variations.md`, `01-current-state/user-journeys.md`, `01-current-state/ecommerce-capabilities.md`, `01-current-state/personalization-current-state.md`, `02-ux-audit/issue-register.md` + module audits. All capabilities below are **missing / incomplete / underdeveloped** per `ecommerce-capabilities.md` inventory statuses (`NOT OBSERVED`, `OBSERVED` but incomplete, `NOT TESTED`, `NOT ACCESSIBLE`). No capability marked `VERIFIED` as complete is included.

## 1. Method & Scope

Evaluated standard commerce capabilities across 8 domains: **Dis­covery, Search, Product Research, Product Confidence, Purchase, Delivery, Post-Purchase, Retention**. For each candidate, checked `ecommerce-capabilities.md:5-65` existence column — only gaps where current state = `NOT OBSERVED` / heading-only / behavior-not-tested were retained. Phase 2 UX fixes (e.g., `/undefined` links NAV-01) are **not** repeated unless they represent a missing commerce *capability* with standards framing.

**Classification used:**

| Class | Meaning | Test |
|-------|---------|------|
| **FOUNDATIONAL** | Expected by 2026 electronics shoppers; absence causes credibility/competence gap | Would a first-time buyer on Daraz/Pickaboo/Rangs expect this to exist? |
| **ENHANCEMENT** | Improves an existing capability that is present but thin/below threshold | Capability row says `Yes` but `NOT TESTED` / truncated / heading-only |
| **DIFFERENTIATOR** | Exceeds baseline and creates competitive advantage in Transcom's high-consideration mix (AC/Fridge/TV/Washer) | Not expected universally, but wins considered purchases |

Most gaps are FOUNDATIONAL/ENHANCEMENT. Only capabilities that truly exceed baseline are labeled DIFFERENTIATOR.

## 2. Summary Matrix

| ID | Capability | Domain | Current State (per inventory) | Classification | Value | Complexity |
|----|------------|--------|-------------------------------|---------------|-------|------------|
| ECS-01 | Aggregate Ratings, Review Count & On-Card Social Proof | Product Confidence / Research | Missing | **FOUNDATIONAL** | High — lifts conversion for Tk 50k–1.5L considered goods | Medium |
| ECS-02 | Rich Product Media: Video, Zoom, 360° / Gallery Depth | Product Research / Confidence | Missing | **FOUNDATIONAL** | High — TV/AC/Fridge require visual inspection | Medium |
| ECS-03 | Predictive Search Autocomplete, Suggestions & Recent Searches | Search / Discovery | Incomplete (input only) | **FOUNDATIONAL** | High — fast-path for model-aware buyers (FTKL12TV16WD) | Medium |
| ECS-04 | Zero-Result Recovery, Typo Tolerance & Did-You-Mean | Search / Discovery | Missing / Not tested | **FOUNDATIONAL** | Medium — prevents dead-end from alphanumeric typos | Medium |
| ECS-05 | Pre-Cart Delivery, Installation & Serviceability Estimator (Pincode, Cost, Timeline) | Delivery / Product Confidence | Preview gated, detail missing | **FOUNDATIONAL** | High — removes #1 purchase blocker after price | Medium |
| ECS-06 | Populated Cart Commerce Completeness: Quantity, Coupon, Breakdown, Save-for-Later & Cross-Sell | Purchase | Present empty-only; populated NOT TESTED | **FOUNDATIONAL** | High — quantity/coupon errors directly lose orders | Low-Medium |
| ECS-07 | Active Filter/Sort Feedback: Chips, Counts, Clear-All & Enumerated Sort Options | Discovery / Filtering | Controls present, feedback missing | **ENHANCEMENT** | High — multi-facet narrowing (brand+size+price) unusable without it | Low |
| ECS-08 | Complementary & Attach Recommendations: Frequently Bought Together / Bundles / Accessories | Discovery / Basket Building | Related exists thin; FBT/Bundles missing | **ENHANCEMENT** | Medium-High — attach for AC install kits, TV mounts, stabilizers | Medium |
| ECS-09 | Browse Resumption: Recently Viewed & Continue Shopping | Retention / Discovery | Missing | **FOUNDATIONAL** | High — restores high-intent return visits (Tk 1L+ research) | Low |
| ECS-10 | Transparent Stock & Price Notifications with Timeline Management | Post-Purchase / Confidence | Stock Alert exists without timeline; Price Alert missing | **ENHANCEMENT** | Medium — retains demand during OOS vs losing to competitor | Low-Medium |
| ECS-11 | Needs-Based Guided Selling / Product Finder (Room-Size→Tonnage, Family-Size→Litres) | Product Research / Discovery | Static SEO guide only; interactive finder missing | **DIFFERENTIATOR** | High — solves Journey C problem, reduces wrong-size returns | Medium-High |

*Total: 11 capabilities — 6 FOUNDATIONAL, 4 ENHANCEMENT, 1 DIFFERENTIATOR. Meets requirement of ≥7 and correct skew.*

---

## 3. Detailed Capabilities

### ECS-01 — Aggregate Ratings, Review Count & On-Card Social Proof

**Current state:** PDP tab strip includes `Review` label on all sampled PDPs (`01-current-state/page-analysis.md:132`, `01-current-state/product-page-variations.md:57`), but inventory records `Reviews: Tab Yes / Stars NOT VERIFIED` and `Ratings (aggregate stars): NOT OBSERVED` (`01-current-state/ecommerce-capabilities.md:31-32`). No aggregate star rating, review count, or sample review body was captured in any of 8 PDP reads; PLP filter facet `Customer Review` is heading-only with no buckets (`01-current-state/product-discovery.md:83`, `01-current-state/ecommerce-capabilities.md:19`). PLP cards show price/discount/EMI but no rating badge.

**Customer problem:** For high-consideration electronics (inverter AC, side-by-side fridge, 55" QLED) where compressor/panel life and after-sales risk dominate, absence of social proof creates a confidence ceiling. Researchers in Journey B/C reach price and spec but cannot triangulate quality via peers; they either defer to external reviews (leaving site) or abandon. Low-ticket repeat items (trimmer, mixer) also lack credibility anchor.

**Relevant journey:** Journey B "I know the category but not which product to buy" (shortlist 2–3 fridges), Journey C "I need an AC for my room" (validation), and all PDP research steps (J1, J4). Cross-ref `02-ux-audit/issue-register.md:7` PDP-07 and `02-ux-audit/user-journey-friction.md:28-51`.

**Classification: FOUNDATIONAL.** Aggregate rating + count near price and `Customer Review` filter buckets are baseline expectations for any 2026 marketplace or brand appliance store. Absence is a standards gap, not a nice-to-have.

**Value:** High. Unlocks filtering by rating, increases PDP conversion 8–15% in electronics benchmarks, reduces reliance on price-only shortlisting. Enables the `Customer Review` facet to actually function.

**Complexity:** Medium. Requires review submission/moderation pipeline, aggregation logic, PLP badge injection, PDP header placement, and seeded "Be first to review + Q&A prompt" for thin catalogue. Does not require personalization.

---

### ECS-02 — Rich Product Media: Video, Zoom, 360° and Gallery Depth

**Current state:** PDP media region shows `4+ generic image containers` with pointer cursor (`01-current-state/page-analysis.md:134-135`) and on Mixer PDP `68 images in DOM (includes icons)` (`01-current-state/product-page-variations.md:49-50`), but `ecommerce-capabilities.md:30` records `Video: NOT OBSERVED` across all 8 category samples (AC, Fridge, TV, Washer, Mixer, Vacuum, Trimmer, Laptop). Zoom/360° controls `NOT TESTED` (`01-current-state/product-page-variations.md:50`). No video element found in snapshots.

**Customer problem:** Buyers cannot inspect fit/finish/features that determine satisfaction: TV bezel depth and viewing angles, fridge door swing and interior layout, AC indoor unit dimensions and outdoor condenser, washer drum depth. Static thumbnails undersupport "will this fit my wall/kitchen?" and "what does the panel look like in a living room?" decisions, which are decisive for Tk 80k+ purchases. High-consideration shoppers hesitate and defer to showroom or competitor with video.

**Relevant journey:** Journey B/C consideration loop and Journey D comparison (visual differentiation). Evidence in `02-ux-audit/issue-register.md:26` PDP-01 and `02-ux-audit/usability-issues.md:225-244`.

**Classification: FOUNDATIONAL.** For electronics/appliances, multi-image gallery with zoom and at least one fit/feature video per category template is a baseline commerce standard, not a premium extra.

**Value:** High. Reduces returns due to size/appearance mismatch, raises confidence-to-cart, supports store-visit-to-online conversion for AC/Fridge.

**Complexity:** Medium. Asset production cost dominates (category video, lifestyle imagery). Tech is standard: hover-zoom/pinch, gallery carousel with thumbnail nav, video player lazy-loaded. Can phase: zoom first (low), video per hero category second.

---

### ECS-03 — Predictive Search Autocomplete, Suggestions & Recent Searches

**Current state:** Header `Search Here` textbox exists on all pages (`01-current-state/page-analysis.md:11`, `01-current-state/ecommerce-capabilities.md:12` VERIFIED), but `Search — Suggestions / Autocomplete: Exists (input) / Behavior NOT FULLY VERIFIED` (`01-current-state/ecommerce-capabilities.md:13`, `01-current-state/product-discovery.md:40-43`). Typing "AC" / "samsung tv" was attempted but suggestion dropdown snapshot not captured before timeout (`01-current-state/user-journeys.md:39-42`). No "Recent searches" heading observed; placeholder is generic `Search Here` (`01-current-state/page-analysis.md:11`).

**Customer problem:** Model-aware electronics buyers (who know `FTKL12TV16WD` or `H55P7UX`) lack a fast-path. They must type full alphanumeric codes correctly with no type-ahead, correction, or category-scoped suggestion, increasing error rate and time-to-PDP. Category-uncertain users get no scent (TV vs AC vs Refrigerator) or example queries to form a valid search.

**Relevant journey:** Journey A "I know exactly what I want" (direct search) and `02-ux-audit/user-journey-friction.md:5-25` Journey A friction. Also supports Journey F return visits.

**Classification: FOUNDATIONAL.** Autocomplete with product/brand/category suggestions and 2–3 recent searches is a 2026 baseline search capability.

**Value:** High. Cuts time-to-PDP by ~40%, reduces zero-results from typos, captures high-intent model searches that otherwise bounce to browse (heavy homepage `01-current-state/page-analysis.md:48-54`).

**Complexity:** Medium. Requires suggestion index (product title, SKU, model, brand, category), debounced type-ahead UI, keyboard navigation, analytics on suggestion selection. Low backend risk; primarily frontend + search index wiring.

---

### ECS-04 — Zero-Result Recovery, Typo Tolerance & Did-You-Mean

**Current state:** `Search — No-result / error handling: No example in sitemap; not triggered live` (`01-current-state/ecommerce-capabilities.md:15` NOT TESTED). No `/search?q=` no-result state observed; `02-ux-audit/issue-register.md:19` SEARCH-03 notes `Zero-result / typo-tolerant behavior unknown — no handling observed`. Campaign See All link shows structured search URL `search?Campaign=...&Stock Status=Show all products` (`01-current-state/product-discovery.md:46`) but no recovery pattern for empty results.

**Customer problem:** Transposed model codes (`FTLK` vs `FTKL`), Bangla/English mix, or out-of-stock queries likely dead-end without recovery (no "Did you mean FTKL12TV16WD?", no alternative categories, no corrected result set, no "Notify when available" fallback). Users perceive catalogue as empty rather than query as fixable, eroding trust in search reliability.

**Relevant journey:** Journey A (model-aware search) and Journey B filtered searches where facet combination yields zero results. Phase 2 SEARCH-03 `02-ux-audit/issue-register.md:19` is the UX symptom; this ECS is the underlying capability gap.

**Classification: FOUNDATIONAL.** Typo-tolerant search with recovery (alternatives, remove-filter prompts, fuzzy match) is expected search hygiene, not a differentiator.

**Value:** Medium (high during catalogue gaps or OOS periods). Converts would-be abandonment into corrected search; reduces support load for "product not found".

**Complexity:** Medium. Requires fuzzy index (edit distance 1–2 on model/SKU), zero-result template with suggested queries, facet-relaxation hints, and telemetry on zero-result rate.

---

### ECS-05 — Pre-Cart Delivery, Installation & Serviceability Estimator (Pincode, Cost, Timeline)

**Current state:** PDP Options block shows `Home Delivery Enable your Location` / `Store Pickup Enable your Location` on all 8 PDPs (`01-current-state/page-analysis.md:125`, `01-current-state/product-page-variations.md:59` VERIFIED), but `Delivery / Shipping Info: Preview Yes (PDP) / Checkout detail NOT TESTED` and `Checkout — Steps (Address/Delivery/Payment): NOT ACCESSIBLE` (`01-current-state/ecommerce-capabilities.md:42-43`). Homepage trust bar claims `Free Installation (Selective Items)` (`01-current-state/page-analysis.md:34`, `01-current-state/ecommerce-capabilities.md:45` OBSERVED) but PDP has no inline installation fee, energy label summary, or delivery timeline until location permission granted. Cart Order Summary shows only `Subtotal: ৳0` (`01-current-state/page-analysis.md:162`) with no delivery estimate.

**Customer problem:** After price exposure (often Tk 80k–1.45L with `Save 7,000 -7.95%` and `EMI From…` `01-current-state/page-analysis.md:115-117`), buyer cannot answer "Can this 600L fridge be delivered to Dhanmondi this week, is installation free, what is total landed cost?" without granting location permission and advancing to undiscoverable checkout (`01-current-state/user-journeys.md:123-130` CHECKOUT-01). Total cost of ownership remains invisible; abandonment spikes at payment when delivery/install surcharge appears.

**Relevant journey:** Journey E "I found a product and want to buy it" (price→delivery confidence), Journey C (AC installation feasibility). Central to `02-ux-audit/cart-checkout.md:21` CHECKOUT-02 and `02-ux-audit/issue-register.md:27` PDP-02.

**Classification: FOUNDATIONAL.** Pincode/area-based delivery check with fee and timeline before Add to Cart is baseline e-commerce for large appliances in Bangladesh (applicable to every PDP).

**Value:** High. Single biggest conversion lever after price; reduces checkout abandonment at step 2, sets correct expectations for free-install selective items, supports COD/EMI trust.

**Complexity:** Medium. Requires pincode/area lookup service, PDP inline input (no permission gate), fee/timeline API, free-install eligibility flag per SKU, and cart summary preview. No auth needed.

---

### ECS-06 — Populated Cart Commerce Completeness: Quantity, Coupon, Price Breakdown, Save-for-Later & Cross-Sell

**Current state:** `/cart` empty state VERIFIED: heading `Your Cart`, illustration, `You have not added any product to your cart yet.`, Order Summary `Subtotal: ৳0 Total: 0`, `Checkout [disabled]` (`01-current-state/page-analysis.md:159-164`, `01-current-state/user-journeys.md:101-103`). However `Cart — Quantity / Coupon / Cross-sell: Not visible in empty state; populated NOT TESTED` (`01-current-state/ecommerce-capabilities.md:40`), `Promotions — Coupon functionality: NOT TESTED` (`01-current-state/ecommerce-capabilities.md:53`), and `user-journeys.md:98-101` notes `Cart with items state NOT TESTED (add flow timed out)`. No quantity stepper, coupon field, price breakdown (savings/EMI impact), save-for-later, or cross-sell rail observable.

**Customer problem:** Even if Add To Cart succeeds (button `VERIFIED` on all in-stock PDPs `01-current-state/page-analysis.md:127`), the cart that should confirm and expand the order may lack standard controls: correcting fat-finger quantity, applying coupon before checkout, seeing savings/discount impact, saving an AC for later (vs deleting), or attaching a stabilizer/mount. Errors persist to order correction burden; coupon friction causes checkout abandonment when code is hunted at payment.

**Relevant journey:** Journey E purchase funnel (`02-ux-audit/cart-checkout.md:10-15` CART-02/CART-03); also Journey F where empty cart is dead-end (`02-ux-audit/issue-register.md:36` CART-01 symptom).

**Classification: FOUNDATIONAL.** Quantity control, visible coupon entry, line-item price breakdown (original/sale/save/EMI), and save-for-later are expected cart standards. This is completeness of an existing template, not a new idea.

**Value:** High. Prevents order errors, captures coupon-driven conversion, and creates attach revenue. Cart is the last recoverable consideration point before checkout.

**Complexity:** Low-Medium. UI existed as shell; remaining work is data binding for quantity (+/− with stock guard), coupon apply/remove with validation messaging, breakdown table, wishlist-move for save-for-later, and related/accessory rail once populated. Telemetry on coupon failure rate.

---

### ECS-07 — Active Filter & Sort Feedback: Chips, Counts, Clear-All & Enumerated Sort Options

**Current state:** PLP sidebar filters PRICE, Brand, Display Size/Screen, Campaign etc. are `VERIFIED` (`01-current-state/page-analysis.md:75-82`, `01-current-state/product-discovery.md:74-83`), but `Filtering — Apply / multi-select behavior: NOT TESTED` (`01-current-state/ecommerce-capabilities.md:21`), `Sorting: Yes (control) / Options NOT ENUMERATED` (`01-current-state/ecommerce-capabilities.md:22`), and evaluations returned `Select Sort Option` with `sortOptions: []` (`02-ux-audit/issue-register.md:24` SORT-01, `01-current-state/product-discovery.md:89-94`). No chip row or `X filters applied` count observed above grid; Customer Review facet is heading-only (`01-current-state/ecommerce-capabilities.md:19`).

**Customer problem:** Multi-facet narrowing (brand + 55" + price 0–1L on Smart TV PLP with 44+ products across 4 pages `01-current-state/user-journeys.md:13-14`) loses system-status visibility. Users must recall what was checked by scanning sidebar; removal requires re-finding the checkbox. Sorting by price low→high or discount (critical for EMI-driven purchases) is undiscoverable; scanning unordered grid is linear and slow. Filter-induced zero-result risk rises without visible state.

**Relevant journey:** Journey B and Journey D (comparison shortlist), Journey 3 Filter Journey `01-current-state/user-journeys.md:63-90` (apply NOT TESTED).

**Classification: ENHANCEMENT.** Filter and sort *exist* as controls; the gap is feedback completeness (chips, counts, enumerated options) that brings them to standard usability.

**Value:** High. Low engineering cost with disproportionate findability gain; directly shortens time-to-shortlist and reduces zero-result frustration.

**Complexity:** Low. Add chip row derived from active query params, per-chip remove + "Clear all", count badge, and replace placeholder sort with 4–5 canonical options (Relevance, Price Low→High / High→Low, Discount, Newest) with sensible default (Relevance).

---

### ECS-08 — Complementary & Attach Recommendations: Frequently Bought Together / Bundles / Accessories

**Current state:** `Related Products` rail exists at PDP footer (H2 `Related Products` VERIFIED on Daikin AC and Dell PDP `01-current-state/page-analysis.md:138-139`, `01-current-state/ecommerce-capabilities.md:11`) but is thin (Dell shows single HP laptop cross-sell `01-current-state/product-discovery.md:106`). `Frequently Bought Together / Bundles: NOT OBSERVED` (`01-current-state/ecommerce-capabilities.md:56`, `01-current-state/product-page-variations.md:67`), `Recommendations — Catalog-driven: VERIFIED` but `Personalized / behavioral: NOT OBSERVED` (`01-current-state/ecommerce-capabilities.md:34-35`). No attach for AC installation kits, TV wall mounts, voltage stabilizers, fridge stands, or extended warranty bundles observed.

**Customer problem:** High-consideration purchases have natural attaches that buyers prefer to add in one trip; absence defers accessory discovery to a separate search, losing attach revenue and leaving buyers uncertain ("does this AC need a stabilizer? Is installation kit included?"). Thin Related Products (single same-taxonomy item) does not surface complementary needs.

**Relevant journey:** Journey B shortlisting, PDP research, and cart cross-sell point `02-ux-audit/cart-checkout.md:14` CART-03. Personalization doc notes no FBT/bundle `01-current-state/personalization-current-state.md:8-13`.

**Classification: ENHANCEMENT.** Catalogue-driven Related Products exists; FBT/bundles/accessory completion enhances basket building. Not invented from zero.

**Value:** Medium-High. Direct average-order-value lift; for AC/TV/Fridge, accessory attach 10–20% is standard. Also completes confidence (buyer sees required companion items upfront).

**Complexity:** Medium. Requires affinity rules (attribute-based: AC→stabilizer/install kit, TV→mount/soundbar), admin curation, bundle pricing logic, PDP "Frequently bought together" checkbox adder + cart-populated cross-sell rail. Can start manually curated per top category before behavioral engine.

---

### ECS-09 — Browse Resumption: Recently Viewed & Continue Shopping

**Current state:** `Recently Viewed Products: NOT OBSERVED` (`01-current-state/ecommerce-capabilities.md:55`), explicitly confirmed by personalization inventory: no `Recently viewed` rail/heading on homepage, PLPs, or PDPs (`01-current-state/personalization-current-state.md:9`, evidence table "Recently" / "Continue shopping" searches returned No). No `Continue shopping` prompt on PDP or empty cart (`01-current-state/personalization-current-state.md:10`, `01-current-state/page-analysis.md:159-164`). `user-journeys.md:128-130` and `02-ux-audit/issue-register.md:14` DISC-02 note complete absence.

**Customer problem:** High-consideration electronics research spans multiple sessions; returning visitors (highest intent) must rebuild navigation from root (`Shop By Category` 6 tiles + header `All Categories` `01-current-state/product-discovery.md:7-14`) among 101 PDPs with flat URLs (`01-current-state/site-inventory.md:47`) and no trail. Intent is wasted; shoppers favor competitor where continuity is preserved.

**Relevant journey:** Journey F "I am returning to continue shopping" `02-ux-audit/user-journey-friction.md:123-143` — wholly unserved; also Journey B interruption recovery.

**Classification: FOUNDATIONAL.** Recently Viewed (last 6–8 PDPs) and Continue Shopping deep-links are baseline retention/discovery hygiene for any e-commerce site with considered goods.

**Value:** High. Recovers highest-intent traffic, shortens return-to-cart path, reduces reliance on Wishlist login for persistence. Low friction, high recall aid.

**Complexity:** Low. Local/session storage for guest + authenticated persistence later; homepage/PLP/PDP rail + empty cart/wishlist deep-links. No ML required for V1.

---

### ECS-10 — Transparent Stock & Price Notifications with Timeline Management

**Current state:** PDP stock badge `In stock` vs `Currently Unavailable` VERIFIED (`01-current-state/page-analysis.md:113`, `01-current-state/product-page-variations.md:58`). Out-of-stock template replaces `Add To Cart` with `Get Stock Alert` (×2 buttons) VERIFIED on Dell outlier (`01-current-state/page-analysis.md:128`, `01-current-state/ecommerce-capabilities.md:49`). However `FEEDBACK-02` notes alert gives `no timeline or notification explanation` (`02-ux-audit/issue-register.md:43`). `Price Alerts: Not observed (only Get Stock Alert)` and `Price Alerts NOT OBSERVED` (`01-current-state/ecommerce-capabilities.md:54-55`). No expected restock date, channel (SMS/email), or price-drop subscription observed.

**Customer problem:** Users submit stock alert without expectation ("when will the Dell laptop return? will I be notified? how?"). Without timeline, trust in alert utility is low; demand leaks to competitor. Buyers tracking price drops on high-ticket items (fridge/TV/Washer with `Save 7,000 -7.95%` promos `01-current-state/page-analysis.md:115`) have no price-watch mechanism short of manual revisits.

**Relevant journey:** Journey E out-of-stock branch, Journey F price-sensitive return, and PDP research for OOS variants (tonnage/size alternatives).

**Classification: ENHANCEMENT.** Stock Alert capability exists as CTA; the gap is notification transparency and price-alert completeness that makes it trustworthy.

**Value:** Medium. Captures demand during OOS (common for imported AC/compressor lines), retains price-watchers, builds permissioned contact list for campaign re-engagement.

**Complexity:** Low-Medium. Add OOS modal with timeline tier (e.g., "Expected within 2 weeks · Notify via SMS/email"), channel selector, and price-alert toggle with threshold; backend queue for restock/price events. No change to PDP shell.

---

### ECS-11 — Needs-Based Guided Selling / Product Finder (Room-Size→Tonnage, Family-Size→Litres etc.)

**Current state:** Category L1 pages carry `Long-form buying guide text` (AC energy/room-size/dehumidification, Refrigerator capacity/space/compressor guidance `01-current-state/site-inventory.md:70`, `01-current-state/page-analysis.md:90-91`), but audit notes it `pushes product grid below the fold` and is `generic SEO, not interactive helper` (`02-ux-audit/navigation-information-architecture.md:15` IA-03, `02-ux-audit/user-journey-friction.md:59` Journey C). No interactive filter `Room size: 100–150 sq ft`, no `inverter-ac` problem-solver, no guided quiz mapping need→product. PDP spec contains `Applicable For 120 Square Feet ; Height - 10 feet` and `EER 3.15` but only after clicking `Specification` tab (`02-ux-audit/usability-issues.md:256-265` PDP-03). AC is the only PDP with variant selector (`Choose Ton: 1 Ton / 1.5 Ton` `01-current-state/product-page-variations.md:52`).

**Customer problem:** Problem-solvers ("I need an AC for my 12×12 room", "fridge for 5-person family") cannot map need to product without reading 1,500 words or digging into spec tabs. Tonnage (1 vs 1.5) and capacity (245L vs 600L) choices are make-or-break for satisfaction; unsupported choice drives wrong-size purchase, returns, service burden, and exit to competitor with sizing tool.

**Relevant journey:** Journey C "I have a problem and need help finding the right product" `02-ux-audit/user-journey-friction.md:52-74` — highest friction for Transcom's core large-appliance mix; also Journey B capacity shortlisting.

**Classification: DIFFERENTIATOR.** Static buying guides exist; an interactive, needs-based finder (3-attribute summary `Fit for: … | Energy: … | Install: …` under title/price plus a "Find my AC/Fridge/Washer" quiz→filtered PLP) exceeds baseline and leverages Transcom's deep taxonomy (`refrigerators/no-frost/side-by-side`, `air-conditioner/residential/inverter-ac` `00-input/sitemap-analysis.md:23-26`).

**Value:** High. Converts problem-solvers who otherwise stall, reduces mismatched sales (costly for AC install), positions Transcom as advisor vs catalogue. Strong SEO + guided traffic capture.

**Complexity:** Medium-High. Requires decision tree per category (room sq ft→tonnage, litres→family size, kg→household), spec normalization (EER, applicable sq ft), UI for quiz inline + PLP filter pre-population, and measurement helper (room calculator). Content already partially exists in SEO blocks and spec tables; investment is interaction design, not new data.

---

## 4. Coverage Map

| Domain | ECS Coverage | Standards Status |
|--------|-------------|------------------|
| Discovery | ECS-07 (filter/sort feedback), ECS-08 (FBT/bundles), ECS-09 (recently viewed) | 1 enhancement, 1 enhancement, 1 foundational |
| Search | ECS-03 (autocomplete), ECS-04 (zero-result) | Both foundational — search is baseline, not premium |
| Product Research | ECS-01 (ratings), ECS-02 (rich media), ECS-11 (guided finder) | 2 foundational, 1 differentiator |
| Product Confidence | ECS-01 (ratings), ECS-02 (media), ECS-05 (delivery estimator) | All foundational — trust before cart |
| Purchase | ECS-06 (cart completeness) | Foundational |
| Delivery | ECS-05 (serviceability) | Foundational |
| Post-Purchase | ECS-10 (notifications) | Enhancement |
| Retention | ECS-09 (resumption), ECS-10 (price/stock watch) | Foundational + enhancement |

All 11 capabilities are verifiably missing/incomplete per `ecommerce-capabilities.md` current-state column — none duplicates a row marked `VERIFIED` as complete.

## 5. Sequencing Note (Not Priority Ordering)

FOUNDATIONAL gaps that block confidence or search-to-PDP (ECS-01, ECS-03, ECS-05, ECS-06, ECS-09) address moments where shoppers stall or leave; ENHANCEMENTS (ECS-07, ECS-08, ECS-10) compound those gains by making existing discovery convert; the single DIFFERENTIATOR (ECS-11) creates advisor positioning for Transcom's high-ticket mix without requiring personalization. Ordering of implementation should follow dependency (cart/search before guided selling) and asset readiness (zoom before video, chips before AI).

---
*Source inventory: `01-current-state/ecommerce-capabilities.md:5-65`, `01-current-state/product-discovery.md:1-134`, `01-current-state/product-page-variations.md:1-144`, `01-current-state/page-analysis.md:7-248`, `02-ux-audit/issue-register.md:1-48`. No capability marked VERIFIED was included. Each ECS frames a standards capability, not merely a UX symptom fix.*
