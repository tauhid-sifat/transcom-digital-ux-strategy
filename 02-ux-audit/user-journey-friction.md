# User Journey Friction — Audit

> Each journey: Entry → Goal → Steps → Friction / Confusion / Decision points → Drop-off risk → Recovery.

## Journey A — “I know exactly what I want” (e.g., Daikin FTKL12TV16WD 1 Ton)

Entry: Direct search or external link; Header `Search Here`. Goal: Land on precise PDP in 1–2 actions.

Steps: Type model `FTKL12TV16WD` → suggestion → result → PDP.

Friction:
- SEARCH-01: No verifiable autocomplete; user must type full alphanumeric code correctly, no typo tolerance visible. Risk of zero-result on transposed `FTKL` characters.
- IA-01: Flat product URLs (`/{brand}-{model}`) give no category scent in autocomplete — user cannot disambiguate among similar models without PDP hop.

Confusion:
- SEARCH-02 generic placeholder (“Search Here”) gives no model-format hint.

Decision points:
- Choose among similar AC tonnage variants (PDP-08 ton switcher only on AC — actually helps here, but hidden under Options).

Drop-off risk: **P1** — direct search is primary fast-path for model-aware electronics buyers; failure pushes them to scroll browse, which is heavy.

Recovery:
- Search zero-result page (SEARCH-03) not observed — no did-you-mean fallback.

---
## Journey B — “I know the category but not which product to buy” (e.g., Refrigerator)

Entry: Homepage Shop By Category → Refrigerator L1 or header All Categories. Goal: Shortlist 2–3 fridges by capacity/price.

Steps: Homepage tile → L1 `refrigerators` → potentially `no-frost/side-by-side` L3 → filter Price/Brand/Side-by-side → sort → compare → PDP.

Friction:
- NAV-01: Homepage feature See All broken removes alternative path; users who start via “Refrigerator” feature section hit undefined.
- IA-03: SEO guide (“Capacity… Space… Compressors…”) pushes filters/grid below the fold — user must scroll before narrowing.
- FILTER-01: No active chip summary — multi-facet selection becomes invisible once scrolled.
- SORT-01: No visible sort options to order by price low→high — scanning 45 smart-TVs linearly.
- PDP-07: No visible aggregate rating on card/PLP to bias shortlist — reliance on price alone.

Confusion:
- FILTER-03/04 price dual controls (slider + buckets) and duplicate Size facets (`Display Size` vs `Screen`) confuse eligible set.

Decision points:
- Capacity choice (e.g., 245L vs 600L) has no PDP cross-variant helper; must return to PLP.

Drop-off risk: **P0/P1 cluster** — highest friction journey; multiple interaction debts compound.

Recovery:
- Reset link present (`page-analysis.md:82`) but without chip feedback users must remember what Reset clears.

---
## Journey C — “I have a problem and need help finding the right product” (e.g., “I need an AC for my room”)

Entry: Category guide or required-solve search. Goal: Solve room-fit problem, not browse.

Steps: PLP AC guide → L2 residential → L3 inverter-ac → filter tonnage? → PDP spec → delivery/install decision.

Friction:
- IA-03 guide is generic SEO, not interactive helper; `inverter-ac` L3 page shows similar wall of text before products.
- PDP-03/02: Room suitability (`Applicable For 120 sq ft`) only inside `Specification` tab after click; installation fee hidden; delivery gated by location before problem solved.
- FILTER-05: No room-size-derived filter (“Room size: 100–150 sq ft”) — tonnage filter not surfaced as problem-solver.

Confusion:
- Tonnage variants exist on AC PDP (1 / 1.5) but no pre-PDP helper mapping sq ft → tonnage.

Decision points:
- Tonnage choice is make-or-break for satisfaction; unsupported → return/service risk.

Drop-off risk: **P1** — problem-solvers who fail to map need → product exit to competitor with sizing tool.

Recovery:
- No “Talk to expert / Chat With Us” inline in filter or PDP spec vicinity (only footer/header Need help).

---
## Journey D — “I want to compare several products” (e.g., 3 Smart TVs 55–65”)

Entry: PLP or PDP Compare actions → `/compare`. Goal: Side-by-side spec/value comparison.

Steps: PDP A Compare → PDP B Compare → `/compare` configure → Highlight differences → choose.

Friction:
- INTERACTION-01: `/compare` empty table expects three hand-typed `Model name or part of product details` searches — recall burden high.
- PDP-08 variant mismatch: TVs filtered by Display Size but PDP cannot switch size — comparison setup must be via PLP loop, not PDP compare accumulation.
- FILTER-01: No active chips to recall which TVs are comparable set.

Confusion:
- `Highlight differences` checkbox visibility (LabelText at top) not obviously tied to previously typed rows.

Decision points:
- Which specs differentiate (Panel type, warranty, EMI) — table rows verified but Highlight behaviour not tested.

Drop-off risk: **P1** — comparison is core for high-ticket; high-friction table likely underused → uninformed purchase.

Recovery:
- `Clear All` present but no `Add more from category` affordance linking back to PLP shortlist.

---
## Journey E — “I found a product and want to buy it” (Funnel to cart→checkout)

Entry: PDP Add To Cart → `/cart`. Goal: Add item and complete purchase.

Steps: PDP Add To Cart (×2) → cart populated (not verified) → Checkout steps → address → delivery → payment.

Friction:
- FEEDBACK-01: No toast/count after tap — user uncertain if add succeeded.
- PDP-02: Delivery confidence post-price but location-gated pre-cart.
- CART-01/02: Empty cart is dead-end; populated cart quantity/coupon/cross-sell unknown.
- CHECKOUT-01/02: Checkout steps invisible before cart+auth; delivery cost not previewed in cart Order Summary.
- PDP-06 EMI inconsistency (fridge no EMI) surprises financing-eligible buyers at cart.

Confusion:
- Two Add To Cart buttons — which to tap? (PDP-09)

Decision points:
- Trust (TRUST-01 homepage vs PDP/Cart disconnect), warranty (PDP-05), install fee.

Drop-off risk: **P0/P1 boundary** — broken discovery (NAV-01) + invisible checkout combine to starve funnel even before Journey E starts; within E, feedback + trust + delivery gating each contribute abandonment.

Recovery:
- Need help (`Need help? Click Here`) sticky button visible but not contextual to cart error; `Need help` in header/footer generic.

---
## Journey F — “I am returning to continue shopping”

Entry: Return visit (direct or homepage). Goal: Resume prior research efficiently.

Steps: Expected: Homepage → Recently Viewed / Wishlist / Cart persistence.

Friction:
- DISC-02: No Recently Viewed / Continue Shopping trail — returning users must rebuild navigation from root.
- AUTH-02: Wishlist/Compare persistence requires login but gives no guest feedback; saved items appear empty.

Confusion:
- “Did my last Wishlist save?” — `/wishlist` guest empty with `about:blank` iframe gives no answer.

Decision points:
- Re-identify previously viewed fridge/TV among 101 PDPs via search or browse — high recall burden.

Drop-off risk: **P1** — returning shopper is highest intent; loss of context wastes that intent.

Recovery:
- Login entry (`/login` phone OTP) available but not contextualised as “Log in to restore your saves”; no “Continue Shopping” deep link from empty cart/wishlist.

---
## Cross-Journey Friction Pattern

Most-co-occurring issues: FILTER-01 (visibility), SORT-01 (placeholder), PDP-02/03 (delivery/spec gated), FEEDBACK-01 (post-action silence), INTERACTION-01 (compare-hand-search). These five affect at least three journeys each — priority for Phase 3 fix sequencing.

---
*Evidence: `01-current-state/user-journeys.md` (J1–J9) + journey-specific issue cross-links to `issue-register.md`.*
