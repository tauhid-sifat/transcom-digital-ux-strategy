# Cart & Checkout — Audit

> Safe exploration boundary respected: no cart populated with items was verifiable end-to-end in Phase 1; no payment credentials entered. This audit focuses on empty-state and pre-checkout information scent.

## Cart

### [CART-01] Empty cart disables Checkout with no inline next-step guidance (P1, HIGH)
**Location:** `/cart` — `page-analysis.md:157-164`, `user-journeys.md:93-119`. **Current:** Heading `Your Cart`, illustration, `You have not added any product to your cart yet.`, Order Summary `Subtotal: ৳0 Total:0`, Terms link, button `Checkout [disabled]`. No `Continue Shopping` or `View Deals` CTA beside Terms. **Problem:** Empty state — a recovery opportunity — is a dead-end. Users who arrive via direct link, or clear cart, must self-navigate without prompt. **Impact:** Recovery requires unaided header navigation; Journey E restart friction. **Direction:** Add primary CTA `Continue Shopping → Shop By Category` + secondary `View Best Deals` inline; collapse Order Summary until items exist.

### [CART-02] Populated-cart capabilities are unverifiable — potential gaps hidden by empty-state-only view (P2, MEDIUM)
**Location:** `/cart` (empty snapshot) — `page-analysis.md:164` “No cart items, quantity steps, coupon field … NOT TESTED (requires items)”. `ecommerce-capabilities.md:40` flagged NOT TESTED. **Current:** Speculation only from Phase 1: add flow timed out before cart populated (`user-journeys.md:98-101`). **Problem:** Whether quantity stepper prevents fat-finger errors, whether coupon field is visible before checkout, whether price breakdown shows savings/EMI impact — unknown. **Impact:** Hidden risks: coupon friction (users hunt at checkout), quantity error → order correction burden. Hidden in current audit scope; flagged for analytics. **Direction:** Retest populated cart with 2 items; capture quantity, coupon placement, cross-sell, Order Summary breakdown.

### [CART-03] No “Save for later” / cross-sell in empty cart (P2, MEDIUM) — Type G
**Location:** `/cart` empty + PDP cart add context. **Current:** No cross-sell rail; no per-item save-for-later (only wishlist exists per PDP but not in cart row). **Problem:** Cart is final consideration point; lack of cross-sell defers accessory attach to separate trip. **Impact:** Revenue and confidence deferred; accessory discovery already weak on PDP (PDP-10). **Direction:** Introduce “Save for later” per cart row (moves to wishlist) + cross-sell “Frequently bought with this item” rail once populated.

## Checkout (Safe Exploration — Stopped Before Payment)

### [CHECKOUT-01] Checkout steps, forms, and progress indication are undiscoverable before adding + authenticating (P1, HIGH)
**Location:** `/cart` → checkout (no sitemap URL; path only after non-empty cart + auth — `sitemap-analysis.md:Not present` + `user-journeys.md:122-148`). **Current:** Empty cart is only accessible precursor; no 3-step preview. PDP delivery preview exists but checkout’s address/delivery/payment components are invisible. **Problem:** Users cannot form mental model of checkout length/complexity before committing items to cart — uncertainty about address granularity, delivery choices, payment options ahead of time. **Impact:** First-time COD/EMI users hesitate to start checkout; cart abandonment before add. **Direction:** Surface 3-step preview on empty cart drawer/page (“1. Address → 2. Delivery & Installation → 3. Payment (COD/Cards/EMI)”) with trust signals; keep full auth deferrable to step 1 submit.

### [CHECKOUT-02] Delivery/installation cost and timeline not previewable alongside Order Summary (P1, HIGH)
**Location:** `/cart` Order Summary (Subtotal/Total only) vs PDP delivery gate `Enable your Location`. **Current:** Cart summary shows only monetary subtotal; delivery/ install surcharge, free-install eligibility, and timeline not previewed until checkout. **Problem:** Total cost of ownership invisible before checkout commitment; AC/fridge big-ticket shock at payment. **Impact:** Checkout abandonment at payment step when delivery cost appears. **Direction:** Surface “Delivery & Installation estimate — Enter area” inline above Order Summary; reflect free-install items distinct.

### [CHECKOUT-03] Trust signals at checkout are implied not demonstrated (P2, MEDIUM)
**Location:** Homepage/FOOTER mentions `EMI Bank List`, `Secure Payment System`, `Terms & Conditions` (`page-analysis.md:33-34`). **Current:** Cart shows “By clicking this button, you agree with the Terms & Conditions” link only. No secure lock, EMI eligibility preview, or return/exchange policy beside Order Summary. **Problem:** Confidence cues exist site-wide but not at the conversion point where anxiety peaks. **Impact:** Trust dip between homepage and checkout. **Direction:** Echo minimal trust ribbon (Secure Payment + Original Guarantee + Easy EMI) above Checkout CTA.

### [CHECKOUT-04] No progress feedback or error prevention preview before form entry (P2, MEDIUM)
**Location:** Anticipated address form (not loaded) — flagged `user-journeys.md:134` (form complexity NOT VERIFIED). **Current:** No preview of required fields, OT PRE population, address reuse, or validation style. **Problem:** Users cannot anticipate form length; error prevention (pincode lookup, division auto-fill, phone OTP pre-fill) not signalled ahead. **Impact:** Perceived form burden suppresses checkout start. **Direction:** Where feasible preview required vs optional fields, pincode auto-fill behaviour, and OTP pre-fill in step preview; retest live checkout with populated cart and observe validation.

## Payment & Transaction Safety Note
No payment card/bank/mobile-banking credentials were entered; no “Place Order” was clicked; exploration stops per safety rule. All checkout inferences are from pre-checkout pages and cart state.

---
*Evidence: `page-analysis.md:157-164`, `site-inventory.md:52`, `user-journeys.md:93-148` (blocked steps), `ecommerce-capabilities.md:39-45`.*
