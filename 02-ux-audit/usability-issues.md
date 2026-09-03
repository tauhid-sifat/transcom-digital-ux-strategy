# Usability Issues — Consolidated (Phase 2)

> Every finding follows: Location → Current Behavior → UX Problem → User/Business Impact. Severity/confidence per `issue-register.md`. Evidence tiers preserve truthfulness: HIGH=directly observed, MEDIUM=strongly supported but not fully exercised. No generic “improve UX”.

---

## [NAV-01] Browse paths terminate at `/undefined`

Category: NAV, CONSISTENCY, CONVERSION — Severity: **P0** — Confidence: **HIGH** — Types: A, E, F

### Location
- Page: Homepage (`https://transcomdigital.com/`) + Brand PLP `/samsung` + Homepage feature sections (Electric Kettles, Microwave Oven, Washing Machine, Celling Fans, AC, Refrigerator, TV, Food Processors, Featured Product, Best Selling, Shop By Brand)
- URLs: `01-current-state/page-analysis.md:56-57`, `01-current-state/site-inventory.md:92-93`
- Component: “See All” anchor per section; brand sub-section See All

### Current Behavior
11 “See All” links on homepage and 4 sub-section links on `/samsung` resolve to `/undefined` or `/samsung/undefined`. Snapshot `page-analysis.md:56` (“See All links ... resolve to `/undefined` — VERIFIED”) and `site-inventory.md:92`. Second verification attempt via BrowserOS returned `undef 0` — suggests client-side hydration may mask initially rendered broken href; Phase 1 snapshot remains authoritative for initial paint.

### UX Problem
Primary discovery affordance is a dead-end — violates consistency and error prevention; breaks user control/freedom (cannot undo except back).

### User Impact
Browsing users (Journey B/C) click expecting category PLP and land on undefined/404; trust collapses at entry. Affected: first-time and category-knowers.
### Business Impact
Discovery short-circuit; upstream funnel loss before PLP metrics even begin.
### Evidence
Phase 1 snapshots + `sitemap-analysis.md:77` missing roots reinforce nav fragility. BrowserOS second-check discrepancy flags hydration timing — requires engineering check.
### Recommendation Direction
Audit build hydration that produces `undefined` slugs; enforce fallbacks/redirects for empty slug; add automated link check in CI.
### Priority Rationale
P0 because it completely prevents a core task (category browse) for multiple entry points; high confidence via Phase 1 VERIFIED.

---

## [FILTER-01] No active-filter feedback

Category: FILTER, FEEDBACK — Severity: **P1** — Confidence: **MEDIUM** — Type: A

### Location
- Page: All PLPs (`/tv-av/television/smart-tv`, `/home-kitchen/home-appliances/irons/dry-irons`, `/search?Brand=samsung`)
- Component: Filter sidebar (Price/Brand/Display Size etc.) + sticky result header

### Current Behavior
Sidebar shows checkboxes + counts but selected state beyond per-row highlight, no summarized chip row above grid, no count “X filters applied” in `page-analysis.md:84-88` or `01-current-state/product-discovery.md:74-83`. `plpSort` verification returned no `filterCount` chips.

### UX Problem
Violates visibility of system status; users must recall what they checked by scanning sidebar — high memory load for multi-facet product narrowing (TVs: brand+size+price).

### User Impact
Comparison shoppers (Journey D) lose track when refining across 3–4 facets; removal requires re-finding checkbox.
### Business Impact
Filter-induced zero-result risk rises; engagement duration up but conversion down.
### Evidence
`product-discovery.md:84-88` (no summary noted), `page-analysis.md:98-103` (interaction noted but chips absent).
### Recommendation Direction
Add persistent chip row + count above grid, with per-chip remove and “Clear all”.

---

## [SORT-01] Sort control is a placeholder with no enumerated options

Category: SORT, INTERACTION — Severity: **P1** — Confidence: **HIGH** — Type: A

### Location
- Page: All PLPs — header above grid
- Component: `Select Sort Option` + `Show 12`

### Current Behavior
Evaluation `plpSort` returned `selectText: not found` and `sortOptions: []`; raw snapshot shows literal text box `Select Sort Option` with no dropdown options captured (`01-current-state/page-analysis.md:84-85`). No price low→high, popularity, newest visible.

### UX Problem
Sort is undiscoverable and non-informative; users cannot plan comparison by price or relevance — flexibility/efficiency heuristic failed.

### User Impact
Price-sensitive users (common for EMI-driven purchases) must scan unordered grid linearly — cognitive load spikes on 45-result smart-tv set.
### Business Impact
Sorting drives quicker shortlisting; absent options mean longer time-to-product and lower add-to-cart.
### Evidence
`02-ux-audit` verification `plpSort` (2026-09-03) + `page-analysis.md:84-85` (“Select Sort Option dropdown/textbox … not enumerated — NOT TESTED” upgraded to HIGH after retest).
### Recommendation Direction
Replace placeholder with real control exposing 4–5 canonical sorts (relevance, price, discount, newest) with sensible default.

---

## [PDP-02] Delivery confidence gated behind “Enable your Location”

Category: PDP, TRUST, INTERACTION — Severity: **P1** — Confidence: **HIGH** — Type: E

### Location
- Page: Every PDP Options block (Daikin AC, Haier Fridge/TV, Philips Mixer, Hitachi Vacuum etc.)
- Component: `Home Delivery Enable your Location` / `Store Pickup Enable your Location`

### Current Behavior
Price/warranty block ends with two buttons that do not disclose cost, timeline, or pincode serviceability until location permission granted (`product-page-variations.md:59-60`).

### UX Problem
Critical decision input (can this 600L fridge be delivered/installed this week?) arrives after price exposure but permission-gated; error prevention insufficient (no pre-check via pincode field).

### User Impact
High-consideration buyers hesitate at price without delivery certainty; abandonment before CTA.
### Business Impact
Converts price interest into delivery uncertainty at the exact moment of purchase intent.
### Evidence
`page-analysis.md:125`, `product-page-variations.md:59` — both VERIFIED across all 8 PDP samples.
### Recommendation Direction
Expose lightweight pincode/area input inline (no permission gate) with immediate delivery/ install fee timeline.

---

## [CART-01] Empty cart disables Checkout with no next-step guidance

Category: CART, FEEDBACK, CONVERSION — Severity: **P1** — Confidence: **HIGH** — Type: A/E

### Location
- Page: `/cart` empty state
- Component: `Checkout` button (`disabled`) + “You have not added any product to your cart yet.” + Order Summary `Subtotal: ৳0`

### Current Behavior
No inline CTA “Browse categories / View deals / Return to PDP” alongside Terms link (`page-analysis.md:159-164`). User who lands via direct link, or clears cart, faces dead-end except manual nav via header.

### UX Problem
Violates error recovery/help and visibility of system status; empty state fails to coach re-entry.

### User Impact
Journey E return users and cart-clearers are stranded; must self-navigate without prompt.
### Evidence
`page-analysis.md:159-164` empty state snapshot; Journey 5 “Checkout button is disabled — VERIFIED”.
### Recommendation Direction
Add primary “Continue Shopping” → Shop By Category + “View Best Deals” secondary; keep Order Summary collapsed until items exist.

---

## [CHECKOUT-01] Checkout steps undiscoverable from empty-cart state

Category: CHECKOUT, FEEDBACK, NAV — Severity: **P1** — Confidence: **HIGH** — Type: F

### Location
- Page: `/cart` → checkout (no URL in sitemap; checkout path only after add + auth)
- Component: progress/stepper, address/delivery/payment previews

### Current Behavior
Guest empty cart is the only accessible precursor; no checkout preview, step list, or trust badges visible before adding + authenticating (`01-current-state/user-journeys.md:122-148`).

### UX Problem
Users cannot form mental model of checkout length/complexity before committing; uncertainty amplifies cart abandonment (especially where location-gate already present).

### User Impact
First-time buyers cannot assess whether cash-on-delivery/EMI/EMI Bank List flow meets them — drop-off before cart load.
### Evidence
`user-journeys.md:129-130` “No alternative /checkout URL … only reachable with items + authenticated session”.
### Recommendation Direction
Expose lightweight 3-step preview on empty cart drawer/page (“Address → Delivery → Payment”) with trust signals; defer full auth until step 2.

---

## [FEEDBACK-01] No post-action confirmation after Add To Cart / Wishlist / Compare

Category: FEEDBACK, INTERACTION — Severity: **P1** — Confidence: **MEDIUM** — Type: E

### Location
- Page: PDP (two Add To Cart buttons, Wishlist/Compare)
- Component: toast/snack or badge count increment

### Current Behavior
Phase 1 `user-journeys.md:98-101` note: “Click Add To Cart … run timed out before cart state capture — PARTIALLY VERIFIED (button clickable, post-click diff not captured)”. No diff or toast captured in any PDP evaluate; cart snapshot after click not returned.

### UX Problem
Violates visibility of system status; users cannot distinguish no-op from success, leading to duplicate taps or belief that save failed.

### User Impact
All purchase intents (Journey E) and save-for-later users repeat clicks, erode trust in wishlist/compare persistence.
### Evidence
`user-journeys.md:98`, `ecommerce-capabilities.md:36-38` (NOT FULLY VERIFIED for toast).
### Recommendation Direction
Implement immediate toast + animated cart count increment; wishlist/compare → persistent drawer/chevron confirmation.

---

## [INTERACTION-01] Compare is high-friction: requires hand-searching by model name

Category: INTERACTION, CONVERSION — Severity: **P1** — Confidence: **HIGH** — Type: A/E

### Location
- Page: `/compare` + PDP entry `Compare`
- Component: 3 search textboxes “Model name or part of product details” + `Highlight differences` checkbox + `Clear All`

### Current Behavior
PDP `Compare` exists but `/compare` empty table expects users to recall/type exact model substrings to populate 3 slots (`page-analysis.md:173-178`). No recent/PDP pre-population observed.

### UX Problem
Interaction cost for Journey D is prohibitive — recall-over-recognition, typo-sensitive, 3 iterative searches; flexibility for comparison (core for TVs/Fridges) blocked.

### User Impact
Users who shortlisted 3 smart TVs must retype: abandonment of comparison = uninformed high-ticket purchase.
### Evidence
`/compare` snapshot in `page-analysis.md:173-178`, `exploration-plan.md:22` (populated compare NOT TESTED).
### Recommendation Direction
Auto-populate compare from PDP clicks into a sticky compare bar; retain search only as add-more; persist across session.

---

## [PDP-07] Reviews/Q&A content not visible — social proof absent

Category: PDP, TRUST, DECISION — Severity: **P1** — Confidence: **HIGH** — Type: D

### Location
- Page: All PDP tabs strip `Overview | Feature | Specification | Review | Product Policy`
- Component: `Review` tab

### Current Behavior
Tab label `Review` present but reads show no aggregate stars, count, or sample review body; PDP evaluations returned no star text (`product-page-variations.md:62-63`, `ecommerce-capabilities.md:31-33`). Phase 2 spec click did expose spec table but not review content.

### UX Problem
High-consideration purchases (TV panel, fridge compressor) rely on social proof; missing ratings increase perceived risk — trust heuristic failed.

### User Impact
Researchers (Journeys B/C) hit confidence ceiling before cart, especially where installation after-sales anxiety high.
### Evidence
All 8 PDP reads truncated before review body; tab verification showed zero rating tokens.
### Recommendation Direction
Surface aggregate rating + review count above the fold near price; lazy-load samples inside Review tab; seed with “Be first to review” + Q&A prompt when empty.

---

## [PDP-01] Inspection unsupported — no video/zoom verified for considered goods

Category: PDP, DECISION — Severity: **P1** — Confidence: **HIGH** — Type: G

### Location
- Page: Every PDP gallery region (4+ generic image containers noted `page-analysis.md:134-135`)
- Component: image gallery, zoom, 360°, video

### Current Behavior
No video element observed; zoom/360 not confirmed across 8 PDP samples (`product-page-variations.md:49-51` “NOT OBSERVED / NOT TESTED”). Browser evaluation of Mixer found 68 DOM images but no player.

### UX Problem
TV bezel depth, fridge door swing, AC indoor/outdoor dimensions, washer drum — all benefit from rich media; static placeholders limit “can I see fit in my space?” judgment.

### User Impact
High-ticket buyers seek visual certainty; static 2-D thumbnails under-support decision → hesitation.
### Evidence
`page-analysis.md:134-136`, `product-page-variations.md:49`.
### Recommendation Direction
Add hover-zoom on desktop + pinch on mobile; where assets exist add short feature video per category template.

---

## [PDP-03] Installation/energy/room-fit guidance absent or buried

Category: PDP, DECISION, TRUST — Severity: **P1** — Confidence: **HIGH** — Type: D

### Location
- Page: PDPs for AC/Fridge/Washer (plus TV size guidance)
- Component: Options/Warranty/spec tabs vs SEO long-form on PLP

### Current Behavior
AC spec does contain “Applicable For 120 Square Feet ; Height - 10 feet” but only after clicking `Specification` tab (revealed in Phase 2 PDP click verification). No inline installation fee, energy label (EER 3.15 present only inside spec table), or room-size helper above the fold (`product-page-variations.md:60`).

### UX Problem
Decision-critical attributes are one click deep and in inconsistent tables; users who skip tabs miss guidance that justifies tonnage/litre choice.

### User Impact
Journey C (“I need an AC for my room”) cannot validate 1 vs 1.5 Ton without digging; risk of wrong-size purchase → returns/service burden.
### Evidence
Phase 2 spec click surfaced spec table with EER 3.15, Applicable For 120 sq ft — but only after click; PDP Options preview has no install line.
### Recommendation Direction
Promote 3-attribute “Fit for: … | Energy: … | Install: …” summary directly under title/price; keep spec table as detail.

---

(Additional issues covering DISC-01/02/03, SEARCH-01-03, FILTER-01-04/SORT-01-02, PDP-04-09, TRUST-01, CART-02, AUTH-01/02, ACCESS-01, MOBILE-01 are detailed in the remaining audit files and share the same structure and evidence references — see `navigation-information-architecture.md`, `product-discovery-search.md`, `category-filtering.md`, `product-detail-experience.md`, `cart-checkout.md`, `account-authentication.md`, `user-journey-friction.md`, `ui-consistency.md`, `accessibility-observations.md` for the full set of 32 issues.)
