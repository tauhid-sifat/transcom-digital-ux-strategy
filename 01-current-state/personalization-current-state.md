# Personalization — Current State

> Lived exploration of ~22 pages + homepage/PLP/PDP/cart/wishlist/compare. Classification: VERIFIED (observed live), OBSERVED (visible hint), NOT OBSERVED (not found in sampled pages), NOT TESTED (requires authenticated browsing). No recommendations.

## Inventory

| # | Capability | Exists | Location(s) Observed | Trigger (if observable) | User Context | Example | Evidence |
|---|-------------|--------|----------------------|--------------------------|--------------|---------|----------|
| 1 | Recently Viewed Products | NOT OBSERVED | — (homepage, PLPs, PDPs scanned; no "Recently viewed" rail/heading) | — | — | — | Reads/snapshots of homepage, smart-tv PLP, dry-irons PLP, 8 PDPs contain no "Recently viewed" heading |
| 2 | Continue Shopping | NOT OBSERVED | — (no "Continue shopping" prompt after cart add or PDP) | — | — | — | Cart empty state shows only "You have not added any product..." with no history link |
| 3 | Personalized Recommendations (behavioral: "Recommended for you", "Based on your browsing") | NOT OBSERVED | Homepage shows generic `Best Deals`, `Best Selling`, `Featured Product` — not labeled as personalized; PLP shows `Latest Products`; PDP shows `Related Products` — all appear catalog-driven, not user-specific | — | Guest vs logged-in not differentiated (header still `Log In` as guest) | `Best Deals` carousel on homepage; `Related Products` on Dell PDP lists HP laptop (cross-sell, not behavioral) | VERIFIED generic recommendation modules exist but no personalization labeling observed |
| 4 | Behavioral Recommendations (view history / purchase history driven) | NOT OBSERVED | No evidence of browsing-history-driven shelf | — | Requires authenticated history — not reachable this phase | — | NOT TESTED beyond guest scan |
| 5 | User-Specific Promotions (targeted coupon/offer) | NOT OBSERVED as user-specific | Campaign `Online Offer` is site-wide; PDP `Offer valid: Online Offer (Valid Till: Sep 30, 2026)` appears generic; no user-segment badge observed | Global campaign | Guest / all users | Campaign countdown `27 DAYS 12 HOURS ...` on homepage + `/campaigns` | VERIFIED as site-wide, not personalized |
| 6 | Personalized Homepage Content (dynamic hero/modules per user) | NOT OBSERVED | Homepage hero is static Best Deals for guest; Shop By Category is fixed 6-tile; no greeting with name or tailored categories | — | Guest shows `Log In` not user name | — | VERIFIED homepage snapshot as guest shows identical hero on repeat loads |
| 7 | Location-Based Content (store proximity / delivery pincode) | PARTIALLY OBSERVED | PDP `Home Delivery Enable your Location` + `Store Pickup Enable your Location` buttons; Store Locator `Search by store name` + district dropdown + `Schedule your visit` — location gate exists but no personalization applied | Click "Enable your Location" | Guest with/without location permission | Example PDP: Daikin AC shows both delivery options requiring location enablement | VERIFIED location gate exists; location-personalized content NOT TESTED |
| 8 | Personalized Search (history, saved terms, suggested for you) | NOT OBSERVED | Search box `Search Here` shows no history dropdown in captured eval; no "Recent searches" heading | — | Guest | — | NOT FULLY VERIFIED — type interaction incomplete, but no history UI observed in snapshots |
| 9 | Saved Preferences (currency, language, category favorites) | NOT OBSERVED | No language/currency selector in header/footer; no "Favorites" beyond wishlist | — | — | — | Footer/header scans show no selector |
| 10 | Personalized Categories (custom order/hidden categories) | NOT OBSERVED | Category order is alphabetical/functional (TV, AC, Refrigerator...); no draggable/customization | — | — | — | OBSERVED fixed navigation |
| 11 | Product Recommendations Based on Browsing (PDP "You may also like" with browsing affinity) | NOT OBSERVED as browsing-aware | PDP `Related Products` exists (Dell shows HP laptop) but appears attribute-similar (laptop→laptop), not browsing-history | View PDP | Any user viewing laptop | Dell PDP Related: `HP CORE i5-11TH GEN 1135G7 (Ash Gray) 68,000` | VERIFIED Related Products heading; personalization not labeled |
| 12 | Cart-Based Recommendations (cross-sell/upsell in cart) | NOT OBSERVED | Cart empty shows no cross-sell; Order Summary only Subtotal/Total. Populated cart not loaded, so cross-sell **NOT TESTED** | Add to cart → view cart | — | — | Empty cart snapshot has no recommendation rail |
| 13 | Wishlist Persistence / Personal Wishlist | OBSERVED (empty) but personalization NOT TESTED | PDP `Wishlist` button present; header `Wishlist` persistent; `/wishlist` empty as guest | Add to wishlist | Requires authentication | PDP button ` Wishlist` on all samples; wishlist page `You have not added any product...` | VERIFIED button/page exist; save/consistency requires login — AUTHENTICATION REQUIRED |
| 14 | Account-Based Personalization (name greeting, order-based suggestions) | NOT TESTED | Header shows `Log In` as guest; post-login greeting not observed (OTP not completed) | Log in | Authenticated user `01571721235` | After login expected: `Astha IT Test` user label was transiently observed on Dell/TV PDP evaluate after session reuse (`Astha IT Test A verification mail was sent to ait.test@yopmail.com`) — suggests account switching side-effect, not verified as personalized content | Partial transient observation but **NOT TESTED** formally |

## Detailed Observations

### What IS Observable (Guest)
- **Generic discovery shelves:** Best Deals, Featured Product, Best Selling, Shop By Category, Electric Kettles, Microwave Oven, Washing Machine etc. on homepage (category-curated, not user-tailored).
- **PLP Latest Products:** 4-item carousel above grid (same for all visitors, e.g., Haier 32" TVs on smart-tv PLP).
- **PDP Related Products:** Cross-sell within same taxonomy (laptop→laptop).
- **Location gate:** PDP delivery blocks explicitly require "Enable your Location" — suggests location-aware fulfillment but personalization not applied until user consents.
- **Wishlist/Compare entry:** Global CTAs, persistent header icons.

### What is NOT Observable This Phase
- Any UI element containing "Recommended for you", "Recently viewed", "Based on your browsing", "Customers who viewed this also viewed", "Inspired by your history", "Because you viewed X", "Continue shopping" copy — none found in 20+ page reads (string search on reads).
- Any user-name greeting on homepage when guest — header remains `Log In`.
- Any persistence of viewed products across sessions.

### Gaps Requiring Authenticated Re-test
| Area | Why Blocked |
|------|-------------|
| Behavioral recommendations after browsing 2-3 PDPs and returning to homepage | Guest session may not persist; need authenticated browse trail + homepage reload |
| Personalized campaign/offers segmentation | Requires logged-in state |
| Recent views rail on homepage/PLP/PDP | May be injected only when history exists — not reachable with single-sample visit |
| Cart-based cross-sell | Requires populated cart (add flow timed out) |
| Saved preferences / address-based personalization | Requires login + address entry |

## Evidence Summary

| Signal | Search Term in Reads | Found? |
|--------|----------------------|--------|
| "Recently" | grep reads | No |
| "Recommended for you" / "For you" | body scans | No (only "Recommended" in generic sense not found; homepage shows Best Deals not "For you") |
| "Continue shopping" | body scans | No |
| "Based on" | body scans | No |
| "Enable your Location" | PDP Options | **Yes** — 6+ PDPs (Daikin, Haier TV, Philips Mixer etc.) |
| "Related Products" | PDP footer | **Yes** — Daikin + Dell |
| "Wishlist" | header + PDP | **Yes** — but not personalized rail |

---
*Conclusion factual: No personalized modules labeled or behaviorally triggered were observed as guest. Location-gated delivery and Related Products are the closest current candidates but are static/catalog-driven. Full personalization assessment requires authenticated, multi-page browsing sequence.*
