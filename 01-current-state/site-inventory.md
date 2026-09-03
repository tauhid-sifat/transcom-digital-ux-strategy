# Site Inventory — Current State

> Generated 2026-09-03. Source: `sitemap.xml` (167 URLs) + live browser exploration (BrowserOS Neo, 20+ representative pages). Evidence classification: VERIFIED = directly interacted, OBSERVED = visible in snapshot/read, NOT TESTED = inferred from sitemap/structure, NOT ACCESSIBLE = could not reach.

## 1. Domain & Technology Signals

| Attribute | Value | Evidence |
|-----------|-------|----------|
| Primary host | `https://transcomdigital.com` | VERIFIED — all sitemap loc + live pages share host |
| Sitemap file | `/sitemap.xml` (single flat urlset, 167 loc) | VERIFIED — file exists in workspace |
| Sitemap generator | `https://octopus.do` | OBSERVED — XML comment |
| Lastmod uniformity | All 167 entries `2026-09-03` | OBSERVED |
| Missing root category page | `/tv-av` absent but children `/tv-av/television`, `/tv-av/soundbar` present | OBSERVED (sitemap) |
| Checkout URL | Not in sitemap; discovered via Cart → Checkout button (disabled when empty) | OBSERVED |

## 2. Full URL Inventory Grouped by Function

### 2.1 Navigation & Discovery (53 URLs)

| Sub-group | Count | Example URLs | Status |
|-----------|-------|--------------|--------|
| Homepage | 1 | `/` | VERIFIED |
| Top-Level Categories | 5 | `/air-conditioner`, `/refrigerators`, `/home-kitchen`, `/washing-machine`, `/personal-care` | VERIFIED (all visited) |
| Level-2 Categories | 11 | `/air-conditioner/residential`, `/home-kitchen/home-appliances`, `/refrigerators/no-frost`, `/tv-av/television` | VERIFIED (sample: residential/inverter-ac, side-by-side, smart-tv) |
| Level-3 Categories | 19 | `/air-conditioner/residential/inverter-ac`, `/home-kitchen/kitchen-appliances/mixer-grinders`, `/refrigerators/no-frost/side-by-side`, `/tv-av/television/smart-tv`, `/home-kitchen/home-appliances/irons` | VERIFIED (inverter-ac, side-by-side, smart-tv visited) |
| Level-4 Categories | 4 | `/home-kitchen/home-appliances/irons/dry-irons`, `/home-kitchen/kitchen-appliances/microwave-oven/convection` | VERIFIED (dry-irons) |
| Brand Listing Pages | 13 | `/samsung`, `/daikin`, `/haier`, `/hitachi`, `/miyako`, `/panasonic`, `/philips`, `/pureit`, `/rowa`, `/sanford`, `/transtec`, `/whirlpool`, `/candy` | VERIFIED (samsung visited) |
| Search | 1 | `/search?Brand=samsung` | VERIFIED |

### 2.2 Product Detail (101 URLs)

| Sub-group | Count | Detection Method |
|-----------|-------|------------------|
| Root-level hyphenated product slugs | 101 | Pattern `/{brand}-{descriptor}-{model}` at host root |

Verified PDP samples (8 categories):

- `daikin-inverter-split-air-conditioner-ftkl12tv16wd-1-ton` — AC
- `haier-no-frost-refrigerator-hrf-622ibg-600-liters` — Refrigerator
- `haier-55-bezel-less-4k-google-tv-h55p7ux` — TV
- `haier-front-loading-washing-machine-hw80-bp12929a-8kg` — Washing Machine
- `philips-3-jar-mixer-grinder-hl7757` — Kitchen appliance
- `hitachi-vacuum-cleaner-cv-se230v-240c` — Home appliance
- `philips-beard-trimmer-bt1235` — Personal care
- `dell-inspiron-15-3501-laptop-intel-i5-11th-gen` — Laptop outlier (Currently Unavailable)

Additional: Flat structure means no category-prefixed product path (e.g., no `/refrigerators/.../product`).

### 2.3 Commerce & Transactions

| Page | URL | Sitemap | Live Status |
|------|-----|---------|-------------|
| Cart | `/cart` | Present | VERIFIED — empty state, disabled Checkout when empty, Order Summary subtotal |
| Wishlist | `/wishlist` | Present | VERIFIED — empty state |
| Compare | `/compare` | Present | VERIFIED — 3-slot comparison table, Highlight differences toggle, Clear All |
| Campaign Hub | `/campaigns` | Present | VERIFIED — Special Offers, countdown timer, pagination |
| Campaign Detail | `/campaign/online-offer` | Present (as `/campaign/online-offer`) | VERIFIED — product grid with Quick View, EMI badges, discount tags |
| Store Locator | `/store-locator` | Present | VERIFIED — List/Map view, district filter, Schedule your visit CTA |
| Exchange (Hub) | `/exchange` | Present | VERIFIED — Refrigerator / Washing Machine selection |
| Exchange Detail | `/exchange/{id}?category=...` (3 URLs) | Present | OBSERVED — parameterized service flow |
| Login | `/login` | Present | VERIFIED — phone +880 input, Next button, Welcome back copy |
| Checkout | *Not in sitemap* | Absent | OBSERVED — Cart links to Checkout; requires items in cart; not fully loaded in empty-cart test |
| Account / Orders / Addresses | *Not in sitemap* | Absent | NOT TESTED — may be revealed post-login |
| Policy | `/page/terms-of-use` | Present | VERIFIED — renders external About site terms inline |

### 2.4 Content / SEO

| Page | URL | Verified Content |
|------|-----|------------------|
| Category SEO blocks | All top-level categories | Long-form buying guide text (e.g., Refrigerator capacity/space/compressor guidance; AC energy/room-size/dehumidification); VERIFIED |
| Terms of Use | `/page/terms-of-use` | Full policy text with links to Product/Web Order/Delivery/Payment/Exchange/Warranty/Service/Privacy on `about.transcomdigital.com` |

## 3. Template Map (Inferred → Verified)

| Template | Inferred Count | Representative Live URL | Live Divergence Noted |
|----------|----------------|--------------------------|-----------------------|
| Homepage | 1 | `/` | VERIFIED — hero, Shop By Category, Electric Kettles/Microwave/Washing Machine etc. See All→ `/undefined` broken |
| Category PLP L1/L2/L3/L4 | 39 | `/air-conditioner`, `/tv-av/television/smart-tv`, `/home-kitchen/home-appliances/irons/dry-irons` | Shared layout: breadcrumb, Filters (Price/Brand/Display Size…), Reset, Latest Products, Sort (Select Sort Option), Show 12, pagination, disclosure SEO block |
| Brand PLP | 13 | `/samsung` | Similar grid to category PLP but hero sections for Brand subcats (All Products See All→ `/samsung/undefined` broken; brand product grid with EMI36, discount % , New/Pre-Order badges) |
| Search PLP | 1+ dynamic | `/search?Brand=samsung` | PLP variant; grid structure similar to category but filtered |
| Product PDP | 101 | Multiple (see above) | Shared PDP shell; tab variations determine template fork (see product-page-variations.md) |
| Campaign Hub | 1 | `/campaigns` | Distinct: countdown timer, Special Offers heading |
| Campaign PLP | 1 | `/campaign/online-offer` | PLP variant with Load more |
| Cart | 1 | `/cart` | Empty state illustration, Order Summary, disabled Checkout, Terms link |
| Wishlist | 1 | `/wishlist` | Empty state only when guest |
| Compare | 1 | `/compare` | 3-column table, search-by-model inputs, Highlight differences checkbox |
| Login | 1 | `/login` | Phone +880 input, Next, Welcome back copy |
| Store Locator | 1 | `/store-locator` | List View / Map View toggle, search by store name, district dropdown, Mapbox map |
| Exchange Hub | 1 | `/exchange` | 2-card selection (Refrigerator, Washing Machine) |
| Policy | 1 | `/page/terms-of-use` | Iframe/article loader, duplicate nav lists |

## 4. URL Health Signals (Observed)

| Signal | Detail | Evidence |
|--------|--------|----------|
| Broken See All links | Homepage Shop By Category and Brand sections link to `/undefined` | VERIFIED — homepage snapshot shows 5+ See All → `/undefined` |
| Brand sub-section undefined links | `/samsung/undefined` repeated 4x | VERIFIED — samsung brand page |
| Trailing-hyphen product slugs | 4 products end with `-` (e.g., `pureit-classic-23l-`, `samsung-65-qn85c...-`) | OBSERVED — sitemap list |
| Trust/promo bar | Homepage: Free Installation / Original Product / Exchange Program / Secure Payment System 4-icon bar | OBSERVED |
| Pagination pattern | PLPs show `Show 12` + `<of 1>` + paginated text box `1` | VERIFIED — smart-tv, dry-irons |

## 5. Pages Potentially Requiring Authentication

- `/wishlist` — empty as guest; persistence requires login (AUTHENTICATION REQUIRED)
- `/cart` → `/checkout` — Checkout flow expected to require login (OBSERVED via disabled checkout)
- `/login` — entry point using `01571721235` + OTP (NOT TESTED — awaiting OTP flow instruction per brief)
- Exchange detail flows may gate on login for trade-in valuation (NOT TESTED)

No `/account`, `/orders`, `/profile` URLs in sitemap; may be discoverable post-login. Documented as NOT TESTED / AUTHENTICATION REQUIRED.

## 6. Unusual / Notable Structures

1. **Flat product namespace:** All PDPs at host root instead of nested `/category/product` — verified live PDPs resolve at root.
2. **Missing TV-AV root:** Children exist without parent sitemap entry.
3. **Parameterized exchange sitemap entries:** `/exchange/{objectId}?category=...` included in static sitemap.
4. **Single search example:** Only `Brand=samsung` filtered search in sitemap; generic search query URLs absent.
5. **Uniform lastmod:** Indicates sitemap export date, not per-page freshness.
6. **SEO content on PLPs:** Every top-level category includes long-form guide text above/below product grid — verified.

---
*Evidence: sitemap.xml (167 loc) parsed; live pages verified via BrowserOS Neo reads/snapshots of homepage, 5 top cats, 4 deeper cats, brand page, search, 8 PDPs, cart/wishlist/compare/login/campaign/store/exchange/terms.*
