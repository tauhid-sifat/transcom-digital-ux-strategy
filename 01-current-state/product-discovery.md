# Product Discovery — Current State

> Evidence: BrowserOS Neo exploration of homepage, category hierarchy (L1-L4), brand pages, search, campaign pages. Sitemap inventory (39 category PLPs + 13 brand PLPs). No recommendation.

## 1. Available Discovery Paths (Current)

| Entry Point | Next Step | Destination Type | Observed Flow |
|-------------|-----------|------------------|---------------|
| Homepage → Shop By Category card | Click category image/title | Category PLP L1 | `Shop By Category` → TV | AV, Air Conditioner, Refrigerator, Home & Kitchen, Personal Care etc. VERIFIED — 6 cards with links |
| Homepage → Category feature sections (Electric Kettles, Microwave Oven, Washing Machine, AC, Refrigerator, TV | AV etc.) | Category PLP | `See All` link per section → category PLP (but currently → `/undefined` broken) — VERIFIED broken |
| Homepage → Best Deals / Featured Product / Best Selling | Click product card | Product Detail (PDP) | Carousel product cards → PDP; Quick View also available — VERIFIED |
| Header → All Categories | Hover/click | Mega-menu → Category hierarchy | `All Categories` trigger present in header; full menu items implied but not fully enumerated — OBSERVED |
| Header → Products / Brands | Click | Product or Brand PLP | OBSERVED |
| Header → Search Here textbox | Type query → (autocomplete suggestions) → submit | Search PLP | Textbox present on all pages; suggestions NOT FULLY VERIFIED (type test incomplete); search submission → `/search?Brand=...` or query — VERIFIED input exists |
| Breadcrumb navigation | Click parent category | Parent PLP | VERIFIED on PLPs (Home > Air Conditioner > Residential > Inverter AC) |
| Category PLP → Filters | Apply Price/Brand/Display Size/Campaign etc. | Filtered PLP (same URL pattern with query) | Filters sidebar VERIFIED; reset link; no post-filter URL captured beyond brand filter example |
| Category PLP → Sorting (`Select Sort Option`) | Select option | Re-sorted product grid | Control VERIFIED but option list not enumerated — NOT TESTED |
| Category PLP → Product card | Click title/image | PDP | VERIFIED — every card links to root-level product slug |
| Brand Listing Page (`/samsung`, `/philips` etc.) | Click brand card or sub-category | Brand-filtered PLP or PDP | VERIFIED — `/samsung` shows All Products grid + sub-section See All (broken `/undefined`) |
| Search Results (`/search?Brand=samsung`) | Click result | PDP | VERIFIED — filtered PLP variant |
| Campaign Hub (`/campaigns`) | Click Special Offers countdown | Campaign Detail PLP (`/campaign/online-offer`) | VERIFIED — 27 DAYS countdown link |
| Campaign Detail → product card | Click | PDP | VERIFIED — same card pattern |
| Latest Products carousel (above PLP grid) | Click thumbnail | PDP | VERIFIED — e.g., Haier 32" TVs on smart-tv PLP |
| Related Products (PDP footer) | Click | PDP (related) | VERIFIED heading exists (Dell PDP shows HP related); interaction NOT TESTED |
| Exchange Hub (`/exchange`) | Select Refrigerator / Washing Machine | Exchange detail flow (`/exchange/{id}?category=...`) | VERIFIED hub; detail NOT TESTED beyond link |
| Store Locator | Geographic browsing not product discovery | Store detail + possibly inventory | VERIFIED but no product tie observed |

**No observed discovery path (within scope):**
- No visible "Recently Viewed" rail — NOT OBSERVED
- No "Frequently bought together" / "Bundles" on PLP/PDP — NOT OBSERVED in reads
- No personalized recommendation carousel heading (e.g., "Recommended for you") — NOT OBSERVED as distinct from Best Deals/Related

## 2. Search Behavior (Current)

### 2.1 Search Entry
- **Location:** Header center on all pages — `Search Here` textbox with two icon buttons (adjacent generic divs with pointer cursor) — VERIFIED
- **Placeholder:** `Search Here`
- **Additional header links near search:** Cart icon (``), Wishlist icon (``), Wishlist/Log In text links

### 2.2 Search Suggestions / Autocomplete
- **Exists:** Textbox is interactive (click triggers focus) — VERIFIED via initial interaction attempt
- **Behavior:** Typing "AC" and "samsung tv" was attempted but suggestion dropdown snapshot not fully captured before timeout — **NOT FULLY VERIFIED** (deferred to manual investigation)
- Mark as **OBSERVED (input exists) / NOT TESTED (suggestion rendering)**

### 2.3 Search Submission
- **Observed pattern:** Sitemap shows only `search?Brand=samsung` as indexed example; live header search would submit to `/search` with query params (Brand, Campaign, isCampaign, Stock Status etc. observed in campaign See All link: `search?Campaign=640030...&isCampaign=true&Stock Status=Show all products`)
- **Result page:** Verified filtered PLP structure identical to category PLP (Filters, Sort, Show 12, grid) — VERIFIED for brand-filtered case

### 2.4 Search Filters (Post-search)
- Same filter taxonomy as category PLP (Price, Brand, Campaign etc.) — VERIFIED

## 3. Category Hierarchy (Current)

**Root categories (sitemap + live):**

| Root | Subcategories (sample) | Depth | Live Verified |
|------|-------------------------|-------|---------------|
| Air Conditioner | air-purifier; residential → inverter-ac, non-inverter-ac | 1→3 | inverter-ac page VERIFIED |
| Refrigerators | frost → top-mount; no-frost → side-by-side, multi-door, no-frost-top-mount, hitachi-made-in-japan | 1→3 | refrigerators L1 + side-by-side L3 VERIFIED |
| Home & Kitchen | home-appliances → irons → dry-irons/steam-irons, vacuum-floor-cleaner, water-purifier; kitchen-appliances → blenders-juicers, cookers-fryers, food-processors, microwave-oven → convection/solo, mixer-grinders, toasters-sandwich | 1→4 | home-kitchen L1 + dry-irons L4 VERIFIED |
| TV | AV (virtual root) → television → qled-tv, smart-tv, uhd-tv; soundbar | (1)→3 | smart-tv VERIFIED |
| Personal Care | hair-dryers, hair-styler, shaver-trimmer | 1→2 | personal-care L1 VERIFIED |
| Washing Machine | (no subcats in sitemap) | 1 | L1 VERIFIED |

**Navigation cues:**
- Breadcrumb reflects hierarchy depth accurately (e.g., 5 levels: Home > Home & Kitchen > Home Appliances > Irons > Dry Irons) — VERIFIED
- Homepage Shop By Category lists 6 top cards; not all roots listed identically (Dishwashers appears as card but not in sitemap tops — likely marketing tile)
- All Categories menu presumably exposes fuller tree — NOT FULLY ENUMERATED

## 4. Filter Options (Current — Aggregated Across PLPs)

Observed filter facets per PLP sample:

| Facet | Options Example | Page Observed |
|-------|-----------------|---------------|
| Price | Slider 0 - 10,55,000 + buckets `0 to 1,00,000`, `1,00,001 to 2,00,000` etc.; Dry Irons bucket `1,250 to 2,000`, `2,001 to 3,000` | smart-tv, dry-irons |
| Brand | Checkbox list with count: SAMSUNG(14), Haier(10), LG(9), ROWA(6) on smart-tv; Ocean(2), Philips(2) on dry-irons | smart-tv, dry-irons |
| Campaign | `Online Offer(1)` | smart-tv |
| Display Size | `55"(10) 43"(7) 65"(7) 32"(5)` | smart-tv |
| Screen | `32"(2) 43"(1)` | smart-tv |
| Color | `Green(1)` | dry-irons |
| Power | `1000W(1)` | dry-irons |
| Customer Review | Heading present, no bucket text captured | smart-tv, dry-irons |

- **Reset:** Link present above filters — VERIFIED
- **Filter behavior:** Checkbox multi-select implied; no live apply test performed — **NOT TESTED** (deferred)
- **Category-specific facets:** Display Size/Screen for TVs, Color/Power for Irons suggest facet set is category-aware — VERIFIED

## 5. Sorting Options (Current)

- **Control:** `Select Sort Option` dropdown/textbox + `Show 12` selector + pagination input `1`
- **Observed location:** Above and below product grid (both positions)
- **Options list:** Not enumerated in snapshots (text not expanded) — **NOT TESTED**
- Appears on all PLPs including deep categories and campaign detail — VERIFIED

## 6. Recommendation Modules (Current)

| Module | Location | Heading | Content | Evidence |
|--------|----------|---------|---------|----------|
| Best Deals | Homepage (below header) | `Best Deals` H1 + See All | Carousel of 4+ promoted products with countdown context | VERIFIED |
| Electric Kettles / Microwave Oven / Washing Machine / AC / Refrigerator / TV | Homepage | Section heading + See All | Category-curated mini-grids (5+ cards each) | VERIFIED |
| Featured Product | Homepage | `Featured Product` | Similar carousel | OBSERVED |
| Shop By Brand | Homepage | `Shop By Brand` | Brand logo/grid | OBSERVED |
| Best Selling | Homepage | `Best Selling` | Similar carousel | OBSERVED |
| Latest Products | Category PLP (e.g., smart-tv, dry-irons) | `Latest Products` H2 | 4 thumbnails above grid with prices | VERIFIED |
| Related Products | PDP footer | `Related Products` H2 | 1+ related product cards (Dell shows HP laptop) | VERIFIED |
| Campaign Products | Campaign hub/detail | `All Products` / Special Offers | Full PLP grid | VERIFIED |

**Not observed as distinct personalization:**
- No "Recently viewed", "Customers who viewed also viewed", "Continue shopping" labels — NOT OBSERVED

## 7. Promotional Discovery Mechanisms (Current)

| Mechanism | Location | Format | Evidence |
|-----------|----------|--------|----------|
| Countdown timer badge | Homepage + Campaign hub | `27 DAYS 12 HOURS ... SECS` link | VERIFIED |
| Discount % badge on card | PLP cards | e.g., `-23.45% -12.00% -18.48%` | VERIFIED |
| Tags | PLP cards | `New`, `Pre-Order` | VERIFIED |
| EMI badge | PLP cards | `EMI36` + `EMI From X Tk/month` | VERIFIED |
| Exchange promo | PLP cards | `Get Exchange up to 12000 Tk` | VERIFIED (ROWAs) |
| Offer validity note | PDP (washing machine) | `Offer valid: Online Offer (Valid Till: Sep 30, 2026)` | VERIFIED |
| Campaign filtering | PLP filters | `Campaign: Online Offer(1)` checkbox | VERIFIED |
| Free Installation/Exchange/Secure Payment bar | Homepage | 4-icon trust bar under hero | VERIFIED |

## 8. Discovery Path Coverage — Gaps & Notes

- Search suggestion/autocomplete rendering **requires manual verification** (type interaction incomplete due to timeout).
- Filter apply flows (multi-select, URL update, result count change) **NOT TESTED** beyond visual presence.
- Quick View interaction (modal vs. navigation) **NOT TESTED** (button exists but not clicked).
- All Categories mega-menu content **NOT FULLY ENUMERATED** (hover diff incomplete).
- Personalization-driven discovery (recently viewed, behavioral recommendations) appears absent but noted as **NOT OBSERVED** not conclusively absent site-wide (requires authenticated deep browse).

---
*All discovery paths documented without evaluation. Where behavior not exercised, marked NOT TESTED / manual investigation required.*
