# Executive Summary — Transcom Digital UX Audit (Phase 2)

> Baseline: `01-current-state` knowledge base (167 URLs, 22 templates, 22 representative pages verified via BrowserOS Neo 2026-09-03). This summary synthesises findings without redesigning. Full evidence in `issue-register.md` and module audits.

## Overall Experience Assessment

Transcom Digital presents a **functionally complete catalogue commerce shell** — homepage, category hierarchy (L1→L4), brand pages, search, PDPs, cart/wishlist/compare, campaigns, store locator, and warranty/EMI supporting content all load. PDPs render price/SKU/variants/warranty and cart/wishlist entry points consistently. PLP filtering is taxonomy-aware (Display Size/Screen for TVs, Color/Power for Irons).

However, the experience is **structurally inconsistent and low in decision support for high-consideration electronics**. Discovery CTAs terminate at broken destinations, sorting is an unlabeled placeholder, review/social proof is absent in reads, delivery confidence is gated before it is given, and the end-to-end purchase path (add→cart→checkout) cannot be previewed from an empty state. Persona journeys that require research, comparison, and confidence before a Tk 50k–1.5L purchase stall at multiple checkpoints.

## Major Strengths

- **Catalog breadth signals reliability:** 39 category PLPs + 13 brand PLPs with deep taxonomy (e.g., `refrigerators/no-frost/side-by-side`, `home-kitchen/home-appliances/irons/dry-irons`) correctly mirrored in breadcrumbs (`01-current-state/page-analysis.md:28-31`) — supports user orientation.
- **Filter taxonomy adapts by category:** Price + Brand + Display Size/Screen for TVs vs. Color/Power for Irons — reduces irrelevant filtering (`page-analysis.md:75-81`).
- **PDP warranty line adapts per appliance type** (`Service/Parts/Compressor-120M` for fridge vs `Panel-48M` for TV vs `Motor-300M` for washer) — acknowledges life-cycle reality of electronics (`product-page-variations.md:61`).
- **Trust peripherals exist:** Free Installation / Original Product / Exchange Program / Secure Payment bar on homepage; EMI `EMI36` badges on PLP cards and `EMI From… Avail Bank EMI` on PDPs; Store Locator with List/Map + Mapbox; Breadcrumbs throughout (`page-analysis.md:7-34`).
- **Compare and Wishlist entry points are ubiquitous:** `Compare`/`Wishlist`/`Share` trio on every PDP and persistent header links — foundation for considered comparison (`page-analysis.md:129-130`).

## Critical UX Problems (P0 + P1)

| Severity | ID | Issue |
|----------|----|-------|
| **P0** | NAV-01 | Multiple “See All” discovery CTAs resolve to `/undefined` — primary browse paths dead-end |
| **P1** | IA-01 | Flat PDP URLs (`/{brand}-{product}` at root) sever category hierarchy and SEO coherence |
| **P1** | IA-03 | Long-form SEO guides on category L1/L2 bury product grid below the fold |
| **P1** | DISC-01 | Homepage serialises 7+ category mini-grids with no prioritisation → cognitive overload |
| **P1** | DISC-02 | No Recently Viewed / Continue Shopping to resume interrupted research |
| **P1** | SEARCH-01 | Search suggestions/autocomplete not verifiable — “know exactly what I want” lacks fast-path |
| **P1** | FILTER-01 | No active-filter chips/summary after filtering — loss of system status visibility |
| **P1** | SORT-01 | Sort control reads “Select Sort Option” with no enumerated options in snapshot |
| **P1** | PDP-01 | High-consideration inspection unsupported — no video/zoom verified, gallery generic |
| **P1** | PDP-02 | Delivery confidence gated behind “Enable your Location” before cost/availability |
| **P1** | PDP-03 | Installation/energy/room-suitability info absent or buried in tabs/SEO |
| **P1** | PDP-07 | Review/Q&A tabs exist but no aggregate rating or sample review visible |
| **P1** | CART-01 | Empty cart disables Checkout with no inline next-step guidance |
| **P1** | CHECKOUT-01 | Checkout steps/progress undiscoverable from empty-cart state |
| **P1** | INTERACTION-01 | Compare requires 3 manual “Model name …” searches — comparison journey high-friction |
| **P1** | FEEDBACK-01 | No toast/confirmation after Add To Cart / Wishlist / Compare |

## Major Friction Themes

1. **Discovery friction** — Broken navigation (NAV-01), heavy homepage (DISC-01), no resumption aids (DISC-02), and hidden search acceleration (SEARCH-01) combine to penalise both browse and direct-search users.
2. **Decision-making friction for considered purchases** — Missing/ gated install/energy/room-fit data (PDP-03), no video/zoom (PDP-01), no visible social proof (PDP-07), and EMI inconsistency (PDP-06) increase research cost for ACs/TVs/Fridges/Washers.
3. **System status & feedback gaps** — No active filter summary (FILTER-01), no sort options (SORT-01), no post-action toasts (FEEDBACK-01), and pagination model (`Show 12 <of 1> 1`) that obscures total results (SORT-02) violate Nielsen’s visibility of system status.
4. **Consistency fractures** — Flat vs hierarchical URLs (IA-01/IA-02), warranty nomenclature (`Parts-0M` vs `Motor-300M`) (PDP-05), EMI badge vs text divergence (CONSISTENCY-01), and homepage-to-sitemap category mismatch (DISC-04) undermine learnability and trust.
5. **Conversion friction at purchase boundary** — Empty-cart dead-end (CART-01), invisible checkout preview (CHECKOUT-01), comparison that must be hand-searched (INTERACTION-01), and location-gating before confidence (PDP-02) each add a drop-off point on Journey E.

## Most Affected User Journeys

- **Journey B — “I know the category but not which product to buy”** and **Journey C — “I need an AC for my room”** — hit DISC-01, IA-03, FILTER-01/SORT-01, PDP-01/03/07; highest friction cluster.
- **Journey E — “I found a product and want to buy it”** — hits PDP-02, CART-01, CHECKOUT-01, FEEDBACK-01; conversion boundary friction.
- **Journey D — “I want to compare several products”** — dominated by INTERACTION-01 (+ PDP-08 variant mismatch).
- **Journey A — “I know exactly what I want”** — penalised by SEARCH-01/SEARCH-02/IA-01 (URL opacity).
- **Journey F — “I am returning to continue shopping”** — wholly unserved by DISC-02.

## High-Level UX Maturity

**Developing — bordering Foundational.**

*Reasoning:* Core catalogue commerce is implemented and loads reliably, but foundational UX hygiene (working navigation links, visible sort/filter feedback, system-status toast, review proof, checkout preview) is incomplete. Information architecture treats SEO content and product discovery as competing stacks rather than layered support, and high-consideration decision needs (install/energy/room-fit, EMI clarity, warranty credibility) are not surfaced where researched. The site is best described as **content-present, interaction-immature**: it documents products, but the journeys that convert them need further maturation before advanced personalization would be effective.

*No numeric UX score assigned; maturity is qualitative per prompt and supported by 40 issues (P0=1, P1=15, P2=20, P3=4; HIGH confidence approx 30, MEDIUM approx 10).*


---
*Evidence: `01-current-state/*` (8 docs) + live verification 2026-09-03 (header/sort/spec/tab/filter snapshots). No Phase 3 personalization or competitor benchmarking undertaken. STOP AFTER PHASE 2.*
