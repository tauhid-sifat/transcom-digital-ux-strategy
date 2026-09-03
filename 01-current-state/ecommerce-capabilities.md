# E-commerce Capabilities — Inventory

> Scope: Current state only. No gaps or recommendations. Evidence: VERIFIED (live BrowserOS Neo), OBSERVED, NOT TESTED, NOT ACCESSIBLE, AUTHENTICATION REQUIRED.

| Capability | Exists | Pages / Locations | Notes | Verified |
|------------|--------|-------------------|-------|----------|
| **Product Discovery — Category Navigation** | Yes | Homepage Shop By Category; Header All Categories/Products/Brands; Breadcrumbs | 6 homepage tiles + header menu + breadcrumbs Home>Category>Subcategory | VERIFIED |
| **Product Discovery — Brand Navigation** | Yes | `/samsung` + 12 other brand PLPs; homepage Shop By Brand | Brand PLP with sub-sections + All Products grid | VERIFIED |
| **Product Discovery — Campaign/Promotion Entry** | Yes | `/campaigns` hub + `/campaign/online-offer` detail; homepage countdown timers | Countdown `27 DAYS...` → campaign detail PLP with Load more | VERIFIED |
| **Product Discovery — Latest Products Rail** | Yes | PLPs (smart-tv, dry-irons) above grid; homepage category minis | 4 thumbnails + prices above filter grid | VERIFIED |
| **Product Discovery — Related Products** | Yes | PDP footer (Dell shows HP laptop cross-sell) | H2 `Related Products` | VERIFIED (presence) |
| **Search — Input** | Yes | Header `Search Here` textbox (all pages) | Placeholder Search Here + 2 icon buttons | VERIFIED |
| **Search — Suggestions / Autocomplete** | Exists (input) / Behavior NOT FULLY VERIFIED | Header search | Typing triggers input but suggestion dropdown not captured before timeout | OBSERVED (input) / NOT TESTED (dropdown) |
| **Search — Filtered Results** | Yes | `/search?Brand=samsung` (brand-filtered) + campaign filtered link | Same PLP chrome as category | VERIFIED |
| **Search — No-result / error handling** | No example in sitemap; not triggered live | — | Requires no-result query test | NOT TESTED |
| **Filtering — Price** | Yes | PLP sidebar (smart-tv, dry-irons) | Dual slider + price buckets (e.g., 0 to 1,00,000) | VERIFIED |
| **Filtering — Brand** | Yes | PLP sidebar | Checkbox with counts SAMSUNG(14), Haier(10) etc. | VERIFIED |
| **Filtering — Category-specific facets** | Yes | PLP sidebar adaptive | Smart TV: Display Size, Screen; Dry Irons: Color, Power; Campaign bucket | VERIFIED |
| **Filtering — Customer Review** | Heading Yes / Buckets not captured | PLP sidebar | Heading present; bucket values not enumerated | OBSERVED |
| **Filtering — Reset** | Yes | PLP sidebar | Link `Reset` above filters | VERIFIED |
| **Filtering — Apply / multi-select behavior** | Exists (checkbox) / Behavior NOT TESTED | PLP sidebar | Elements present but URL/result refresh not exercised | NOT TESTED |
| **Sorting** | Yes (control) / Options NOT ENUMERATED | PLP above/below grid | Control `Select Sort Option` + Show 12 + pagination `1` | OBSERVED |
| **Product Comparison — Entry** | Yes | PDP `Compare` button (× every PDP) + header Compare link | Icon `` | VERIFIED |
| **Product Comparison — Interface** | Yes | `/compare` | 3-slot table, `Highlight differences` checkbox, `Clear All`, 3 search inputs | VERIFIED |
| **Product Comparison — Populated compare** | NOT TESTED — empty state only | `/compare` | Requires adding 2+ products via PDP buttons | NOT TESTED |
| **Product Information — Title / Brand / SKU / Model** | Yes | All PDPs | H1 + `brand` link + `SKU: Model:` | VERIFIED |
| **Product Information — Key Features bullets** | Yes | All PDPs | 4 bullets typical | VERIFIED |
| **Product Information — Specifications tab** | Yes (tab present) / Content NOT TESTED | PDP tabs | Tab label `Specification` visible; table content not clicked | OBSERVED |
| **Product Information — Image Gallery** | Yes (placeholders) / Controls NOT TESTED | PDP top | 4+ generic image containers | OBSERVED |
| **Product Information — Video** | Not observed in snapshots | PDP | No video element found | NOT OBSERVED |
| **Reviews** | Tab Yes / Stars NOT VERIFIED | PDP tabs | Tab `Review` present; star rating/count not captured | OBSERVED |
| **Ratings (aggregate stars)** | Not observed | PDP / PLP | No star text in reads; count filter heading exists but not buckets | NOT OBSERVED |
| **Product Q&A** | Tab may conflate; no dedicated Q&A beyond tabs | PDP | No Q&A heading found | NOT OBSERVED |
| **Recommendations — Catalog-driven** | Yes | Homepage Best Deals/Featured/Best Selling; PLP Latest; PDP Related | Generic curation, not labeled personalized | VERIFIED |
| **Recommendations — Personalized / behavioral** | NOT OBSERVED | — | No "Recommended for you" labeling | NOT OBSERVED |
| **Wishlist — Entry** | Yes | PDP `Wishlist` button (``) + header `Wishlist` link | Present on all PDPs | VERIFIED |
| **Wishlist — Page** | Yes | `/wishlist` | Guest empty: `You have not added any product...` | VERIFIED (empty) |
| **Wishlist — Persistence / price alert** | AUTHENTICATION REQUIRED | PDP → Wishlist | Guest add not clicked; persistence deferred | NOT TESTED |
| **Cart — View** | Yes | `/cart` | Heading, illustration, empty copy, Order Summary Subtotal/Total | VERIFIED (empty) |
| **Cart — Quantity / Coupon / Cross-sell** | Not visible in empty state; populated NOT TESTED | `/cart` | Empty shows no stepper/coupon; populated requires add flow | NOT TESTED |
| **Cart — Checkout CTA** | Yes (disabled when empty) | `/cart` | Button `Checkout` disabled attr; Terms link present | VERIFIED |
| **Checkout — Steps (Address/Delivery/Payment)** | Gate blocked by empty cart + auth; PDP preview indicates Home Delivery/Store Pickup | PDP Options + `/cart` → checkout | PDP shows `Home Delivery Enable your Location` premise; checkout pages NOT ACCESSIBLE in empty state | NOT ACCESSIBLE |
| **Delivery / Shipping Info** | Preview Yes (PDP) / Checkout detail NOT TESTED | PDP Options + footer Shipping & Delivery page | PDP: `Home Delivery` / `Store Pickup` each gated | VERIFIED (preview) |
| **Store Pickup** | Yes (preview) | PDP Options; Store Locator `/store-locator` | `Store Pickup Enable your Location` + store locator with List/Map, district filter, Schedule your visit | VERIFIED |
| **Installation Information** | Referenced (footer + homepage trust bar) / PDP detail NOT OBSERVED | Homepage trust bar `Free Installation Selective Items`; footer `Installation` link | No explicit installation block on PDP Options beyond delivery | OBSERVED (trust bar) |
| **Warranty Information** | Yes (adapted per category) | PDP Options → Warranty line | e.g., `Service-24 M, Parts-24 M, Compressor-120 M` (Fridge) | VERIFIED |
| **EMI / Financing** | Yes | PLP cards (`EMI36` + `EMI From X Tk/month`) + PDP `EMI From ... Avail Bank EMI` + footer `EMI Bank List` | Present on most PDPs/PLPs | VERIFIED |
| **Stock Information** | Yes | PDP badge | `In stock` vs `Currently Unavailable` | VERIFIED |
| **Back-in-stock / Stock Alert** | Yes (out-of-stock state) | PDP Dell | Button `Get Stock Alert` replaces Add To Cart when unavailable (×2) | VERIFIED |
| **Promotions — Discount badges** | Yes | PLP cards + PDP pricing | `Save 7,000 -7.95%`, `-23.45%` etc.; tags `New`, `Pre-Order` | VERIFIED |
| **Promotions — Campaigns** | Yes | `/campaigns` + `/campaign/online-offer` + campaign filter | Countdown timer, campaign-filtered PLP, Load more | VERIFIED |
| **Promotions — Exchange** | Yes | `/exchange` hub + `/exchange/{id}?category=...` + PLP `Get Exchange up to 12000 Tk` | 2-card selector (Fridge/Washing Machine) | VERIFIED (hub) |
| **Promotions — Coupon functionality** | Not visible in empty cart; may be checkout field | Cart/Checkout | No coupon input in empty cart snapshot; checkout not reached | NOT TESTED |
| **Price Alerts** | Not observed (only Get Stock Alert) | PDP | Get Stock Alert is stock-based, not price-based | NOT OBSERVED |
| **Recently Viewed Products** | NOT OBSERVED | — | No rail/heading found on homepage/PLP/PDP | NOT OBSERVED |
| **Frequently Bought Together / Bundles** | NOT OBSERVED | PDP | No FBT heading/carousel | NOT OBSERVED |
| **Account — Login Entry** | Yes | `/login` | Phone +880 input + Next, Welcome back copy, new-user auto-create note | VERIFIED |
| **Account — OTP Verification Screen** | NOT TESTED (STOP before OTP request) | `/login` → OTP | OTP flow deferred per instruction | AUTHENTICATION REQUIRED |
| **Account — Dashboard / Profile / Addresses / Order History** | NOT IN SITEMAP; NOT TESTED | Unknown URLs under account | Requires OTP session to discover | AUTHENTICATION REQUIRED |
| **Account — Saved Addresses / Order History / Personalized nav** | NOT TESTED | — | Footer `Track Orders` hint; no concrete page verified | AUTHENTICATION REQUIRED |
| **Post-Purchase — Order Tracking / Service Tracking** | Links Yes / Flow NOT TESTED | Header `Track Order Status`, `Track Your Service`, footer `Track Orders` | Header links present → `/track-order`, `/track-service` | OBSERVED |
| **Post-Purchase — Warranty / Service pages** | Links Yes / Content NOT TESTED | Footer `Service Charges`, `Service Pre-Requisite`; `/page/terms-of-use` | External about site terms include Warranty/Service | OBSERVED |
| **Support — FAQs / Chat / Help** | Links Yes | Header `Need help? Click Here`, footer `FAQs`, `Chat With Us`, `Register Your Complaints`, `Contact Us` | Trigger button present; chat not opened | OBSERVED |
| **Store Availability (store-pickup inventory)** | Location-gated preview Yes | PDP Store Pickup + Store Locator + Mapbox map | `Enable your Location` gate; list/map toggle | VERIFIED (gate) |
| **Personalization — Any capability** | None observed as personalized (see separate doc) | — | Closest are catalog Related/Latest; location gate is gating, not personalizing | NOT OBSERVED |

---

## Capability Summary Counts

- **Capabilities VERIFIED as existing (at least empty/entry state):** ~36 (including discovery, filters, brand/campaign, compare entry/interface, cart/wishlist empty, PDP pricing/EMI/warranty/stock, store locator, exchange hub, PDP CTAs)
- **Existing but NOT FULLY TESTED (empty vs populated, content not clicked):** Sorting options, filter apply, populated compare/cart, reviews content, Q&A, coupon, no-result search, suggestions dropdown, checkout steps — flagged NOT TESTED / manual
- **NOT OBSERVED in sampled pages:** Video, ratings stars, Q&A, price alerts, recently viewed, FBT/bundles, personalized recommendations
- **AUTHENTICATION REQUIRED (deferred):** Wishlist persistence, checkout flow, account dashboard/profile/addresses/orders, personalized post-login experiences

*No gap analysis or improvements suggested; inventory is factual.*
