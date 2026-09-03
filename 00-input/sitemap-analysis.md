# Sitemap Analysis

## Total URLs

**167 URLs** in a single sitemap file: `sitemap.xml` (urlset, generated via https://octopus.do, lastmod 2026-09-03 for all entries).

## Sitemap Files Found

| File | Location | Type | URL Count | Relationship |
|------|----------|------|-----------|--------------|
| sitemap.xml | `/sitemap.xml` (workspace root) | urlset (sitemap.org 0.9) | 167 | Primary and only sitemap discovered. No sitemap-index.xml, no additional XML sitemap files found. No robots.txt sitemap reference verified (robots.txt not inspected in sitemap itself). All URLs share same host `https://transcomdigital.com`. |

No sitemap index. No partitioned sitemaps (e.g., product-sitemap.xml, category-sitemap.xml). Single flat file.

## URL Categories

Categorization derived from URL path patterns and verified against site navigation (category/brand structure). Note: 4 top-level category slugs contain hyphens (`air-conditioner`, `home-kitchen`, `washing-machine`, `personal-care`) and are category pages, not product pages.

| Category | Number of URLs | URL Pattern | Example URLs |
|----------|---------------:|-------------|--------------|
| **Homepage** | 1 | `/` | `https://transcomdigital.com/` |
| **Top-Level Category Pages** | 5 | `/{category-slug}` where slug = `air-conditioner`, `home-kitchen`, `personal-care`, `refrigerators`, `washing-machine` | `https://transcomdigital.com/air-conditioner`, `https://transcomdigital.com/refrigerators`, `https://transcomdigital.com/home-kitchen`, `https://transcomdigital.com/washing-machine`, `https://transcomdigital.com/personal-care` |
| **Category Hierarchy — Level 2** | 11 | `/{parent}/{child}` | `https://transcomdigital.com/air-conditioner/residential`, `https://transcomdigital.com/home-kitchen/home-appliances`, `https://transcomdigital.com/home-kitchen/kitchen-appliances`, `https://transcomdigital.com/refrigerators/no-frost`, `https://transcomdigital.com/tv-av/television`, `https://transcomdigital.com/personal-care/hair-dryers` |
| **Category Hierarchy — Level 3** | 19 | `/{parent}/{child}/{grandchild}` | `https://transcomdigital.com/air-conditioner/residential/inverter-ac`, `https://transcomdigital.com/home-kitchen/kitchen-appliances/mixer-grinders`, `https://transcomdigital.com/refrigerators/no-frost/side-by-side`, `https://transcomdigital.com/tv-av/television/smart-tv`, `https://transcomdigital.com/home-kitchen/home-appliances/irons` |
| **Category Hierarchy — Level 4** | 4 | `/{parent}/{child}/{grandchild}/{great-grandchild}` | `https://transcomdigital.com/home-kitchen/home-appliances/irons/dry-irons`, `https://transcomdigital.com/home-kitchen/kitchen-appliances/microwave-oven/convection`, `https://transcomdigital.com/home-kitchen/kitchen-appliances/microwave-oven/solo` |
| **Brand Listing Pages** | 13 | `/{brand-slug}` (single token, no hyphen) | `https://transcomdigital.com/samsung`, `https://transcomdigital.com/daikin`, `https://transcomdigital.com/haier`, `https://transcomdigital.com/hitachi`, `https://transcomdigital.com/candy`, `https://transcomdigital.com/miyako`, `https://transcomdigital.com/panasonic`, `https://transcomdigital.com/philips`, `https://transcomdigital.com/pureit`, `https://transcomdigital.com/rowa`, `https://transcomdigital.com/sanford`, `https://transcomdigital.com/transtec`, `https://transcomdigital.com/whirlpool` |
| **Product Detail Pages** | 101 | `/{brand}-{product-descriptor}-{model}` (hyphenated slug, flat at root) + 1 outlier `/dell-inspiron-15-3501-laptop-intel-i5-11th-gen` | `https://transcomdigital.com/daikin-inverter-split-air-conditioner-ftkl12tv16wd-1-ton`, `https://transcomdigital.com/samsung-side-by-side-refrigerator-rs72r5011b4d2-700-`, `https://transcomdigital.com/haier-55-bezel-less-4k-google-tv-h55p7ux`, `https://transcomdigital.com/philips-beard-trimmer-bt1235`, `https://transcomdigital.com/pureit-classic-mineral-romf-4` |
| **Search Pages** | 1 | `/search?Brand={brand}` | `https://transcomdigital.com/search?Brand=samsung` |
| **Campaign / Promotional Pages** | 2 | `/campaigns` and `/campaign/{slug}` | `https://transcomdigital.com/campaigns`, `https://transcomdigital.com/campaign/online-offer` |
| **Compare** | 1 | `/compare` | `https://transcomdigital.com/compare` |
| **Cart** | 1 | `/cart` | `https://transcomdigital.com/cart` |
| **Wishlist** | 1 | `/wishlist` | `https://transcomdigital.com/wishlist` |
| **Login / Authentication** | 1 | `/login` | `https://transcomdigital.com/login` |
| **Exchange / Trade-in Service** | 4 | `/exchange` and `/exchange/{id}?category=...` or `?productSlug=...` | `https://transcomdigital.com/exchange`, `https://transcomdigital.com/exchange/63735c57285af729b535a425?category=refrigerators`, `https://transcomdigital.com/exchange/6370a9c5bf162f3ba8df63d2?productSlug=rowa-65-smart-tv-65u62` |
| **Store Locator** | 1 | `/store-locator` | `https://transcomdigital.com/store-locator` |
| **Policy / Content Page** | 1 | `/page/{slug}` | `https://transcomdigital.com/page/terms-of-use` |
| **Total** | **167** | — | — |

### Detailed Product Detail Breakdown by Brand Hint

Product slugs are prefixed by brand token. Counts reflect flat product URLs (101) + brand hint in slug:

| Brand Hint | Product URLs |
|------------|--------------|
| haier | 12 |
| hitachi | 9 |
| transtec | 9 |
| whirlpool | 9 |
| miyako | 8 |
| panasonic | 8 |
| philips | 8 |
| samsung | 8 |
| sanford | 8 |
| pureit | 7 |
| daikin | 6 |
| rowa | 6 |
| candy | 2 |
| dell | 1 |
| store (store-locator not product, excluded from above) — dell outlier product also counted | 1 |

Note: Some product slugs may contain brand hint that diverges from actual brand taxonomy (e.g., `dell-inspiron...` maps to Dell, not a sitemap brand page).

### Detailed Category Hierarchy Inventory

**Root categories referenced in sitemap (explicit pages):**

- `air-conditioner` → `residential` → `inverter-ac`, `non-inverter-ac`; also `air-purifier`
- `refrigerators` → `frost` → `top-mount`; `no-frost` → `side-by-side`, `multi-door`, `no-frost-top-mount`, `hitachi-made-in-japan`
- `home-kitchen` → `home-appliances` → `irons` → `dry-irons`, `steam-irons`; `vacuum-floor-cleaner`, `water-purifier`; and `kitchen-appliances` → `blenders-juicers`, `cookers-fryers`, `food-processors`, `microwave-oven` → `convection`, `solo`, `mixer-grinders`, `toasters-sandwich`
- `tv-av` (no root page in sitemap, but subcategories exist) → `television` → `qled-tv`, `smart-tv`, `uhd-tv`; `soundbar`
- `personal-care` → `hair-dryers`, `hair-styler`, `shaver-trimmer`
- `washing-machine` (root category, no subcategories in sitemap)

**Missing root pages in sitemap that are referenced as parents:**

- `/tv-av` itself is not listed as a URL but its children `/tv-av/television` and `/tv-av/soundbar` are present.

## Important Commerce Pages

| Page | URL | Category |
|------|-----|----------|
| Homepage | `https://transcomdigital.com/` | Homepage |
| Cart | `https://transcomdigital.com/cart` | Cart |
| Wishlist | `https://transcomdigital.com/wishlist` | Wishlist |
| Compare | `https://transcomdigital.com/compare` | Product Comparison |
| Campaigns hub | `https://transcomdigital.com/campaigns` | Promotional |
| Campaign detail | `https://transcomdigital.com/campaign/online-offer` | Promotional |
| Search (brand filtered) | `https://transcomdigital.com/search?Brand=samsung` | Search |
| Exchange hub | `https://transcomdigital.com/exchange` | Service |
| Category PLPs (39) | e.g., `/air-conditioner`, `/refrigerators/no-frost/side-by-side` | Category / Subcategory / PLP |
| Brand PLPs (13) | e.g., `/samsung`, `/daikin` | Brand Listing |
| Product PDPs (101) | e.g., `/daikin-inverter-split-air-conditioner-ftkl12tv16wd-1-ton` | Product Detail |

**Not present as distinct URLs in sitemap (expected but absent):**

- `/checkout` (no checkout URL in sitemap)
- `/account`, `/profile`, `/orders`, `/addresses` (no authenticated account sub-pages)
- `/blog`, `/buying-guide`, `/support`, `/service`, `/warranty` distinct content areas
- Faceted search URLs beyond the single `search?Brand=samsung` example
- Pagination URLs
- Product category pagination or sorting URL variants

## Important Account Pages

| Page | Sitemap Presence | Notes |
|------|------------------|-------|
| Login | Present — `/login` | Only explicit auth page |
| Account Dashboard | Absent | May exist as `/account` or similar but not in sitemap |
| Profile Management | Absent | Not in sitemap |
| Saved Addresses | Absent | Not in sitemap |
| Order History | Absent | Not in sitemap |
| Wishlist | Present — `/wishlist` | Likely requires authentication for persistence; accessible URL exists |
| Cart | Present — `/cart` | May require auth for checkout |

All other account-related pages (profile, orders, addresses, personalization) are not exposed in the sitemap. Exploration must discover them via site navigation after authentication.

## Important Content Pages

| Page | URL | Notes |
|------|-----|-------|
| Terms of Use | `https://transcomdigital.com/page/terms-of-use` | Sole policy/content page in sitemap |
| Campaigns | `https://transcomdigital.com/campaigns` | Promotional content hub |
| Campaign Online Offer | `https://transcomdigital.com/campaign/online-offer` | Promotional detail |
| Store Locator | `https://transcomdigital.com/store-locator` | Service/content page |
| Exchange | `https://transcomdigital.com/exchange` + 3 parameterized exchange URLs | Trade-in service flows |
| Brand pages (13) | `/samsung`, etc. | Serve as both brand landing and filtered PLP |

No blog, buying guide, support, FAQ, warranty, installation, or after-sales content pages are present in sitemap.

## Potential Duplicate URLs

| Pattern | Example | Issue |
|---------|---------|-------|
| Trailing hyphen slugs | `https://transcomdigital.com/pureit-classic-23l-`, `https://transcomdigital.com/pureit-mineral-ultima-rouvmf-`, `https://transcomdigital.com/samsung-65-qn85c-neo-qled-4k-smart-tv-qa65qn85carser-`, `https://transcomdigital.com/samsung-side-by-side-refrigerator-rs72r5011b4d2-700-` | 4 product URLs end with `-` suggesting truncation or export artifact; may have canonical duplicates without trailing hyphen |
| Brand vs. Search overlap | `/samsung` (brand page) vs. `/search?Brand=samsung` (search filtered) | Two URL patterns serving similar brand-filtered product list; potential duplicate content if not canonicalized |
| Product vs. Exchange productSlug param | `/rowa-65-smart-tv-65u62` (PDP) vs. `/exchange/6370a9c5bf162f3ba8df63d2?productSlug=rowa-65-smart-tv-65u62` | Exchange URL references same product slug as query param; not duplicate but indicates product slug reuse in service flow |
| Category vs. Brand ambiguity | `/candy`, `/daikin` appear as brand pages but could be confused with category structure | No duplicate per se, but flat brand slugs at root collide visually with category pattern `/{slug}` |

No exact duplicate `loc` entries detected; all 167 loc values are unique.

## Unusual URL Patterns

1. **Flat product URL structure:** All 101 product detail pages live at root `/` (e.g., `/daikin-inverter-split-air-conditioner-ftkl12tv16wd-1-ton`) rather than nested under `/{category}/{product}`. This diverges from typical e-commerce hierarchy (`/ refrigerators/no-frost/side-by-side/product-slug`).
2. **Missing `/tv-av` root:** Subcategories `/tv-av/television` and `/tv-av/soundbar` exist without a parent `/tv-av` entry in sitemap.
3. **Single search URL:** Only `search?Brand=samsung` is present; no generic `/search?q=`, faceted, or paginated search URLs. Suggests sitemap is manually curated / Octopus.do export, not auto-generated from full catalog.
4. **Parameterized exchange URLs:** `/exchange/{objectId}?category=washing-machine` and `?productSlug=...` mix path ID + query string; unusual for sitemap (typically static URLs).
5. **Trailing hyphen artifacts:** As noted above, 4 URLs with trailing `-` likely export truncation.
6. **Title-cased lastmod uniformity:** All 167 URLs share identical `lastmod: 2026-09-03`, indicating bulk generation date rather than true per-page last modification.
7. **No checkout/account URLs:** Commerce-critical URLs absent from sitemap (may be intentionally excluded via noindex/nositemap or not linked in Octopus.do prototype).

## Pages Potentially Requiring Authentication

| URL | Reason |
|-----|--------|
| `https://transcomdigital.com/wishlist` | Wishlist typically requires login to persist; guest view may be empty or redirect to login |
| `https://transcomdigital.com/cart` | Cart view is guest-accessible but checkout from cart will require authentication |
| `https://transcomdigital.com/compare` | Compare may be guest-accessible but saved comparisons may require login |
| `https://transcomdigital.com/exchange/*` | Exchange/trade-in flows often require login to complete valuation and order linkage |
| `https://transcomdigital.com/login` | Authentication entry point itself |
| *Undiscovered* `/account`, `/profile`, `/orders`, `/addresses` | Not in sitemap but likely exist and will require OTP authentication with phone `01571721235` |

Sitemap does not explicitly flag auth requirements; inference based on e-commerce convention. No `authentication-required` URL pattern is labeled in sitemap metadata.

---
*Source: `sitemap.xml` (167 loc entries), parsed 2026-09-03. No sitemap-index.xml found. Classification verified by manual pattern analysis; product vs. category disambiguation applied for hyphenated top-level categories.*
