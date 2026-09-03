# Page Analysis — Current State Templates

> Evidence: BrowserOS Neo exploration of ~22 representative pages (see exploration-plan.md). Reads/snapshots/evaluate outputs captured 2026-09-03. No UX judgment — documentation only.

## I. Global Shell (All Pages)

### Header — VERIFIED
- **Top utility bar:** B2B / Dealership, Store Locator (with icon), Track Order Status, Track Your Service, NEW badge — observed on homepage, TV PLP, PDP, cart.
- **Main header (banner):**
  - Left: Transcom logo link to `/`
  - Center: `Search Here` textbox (placeholder "Search Here"), two generic icon buttons (search/clear) at ` [ref=e3]` region
  - Right: Cart icon link (`` / cart count), Wishlist icon (`` / ``), secondary header links: `All Categories`, `Products`, `Brands`, `Gift Voucher`, `Campaign`
  - Top-right account: `Wishlist` link → `/wishlist`, `Log In` link → `/login` (icon ``)
- **Help trigger:** Sticky `Need help? Click Here ` button at top (visible on every page)
- **Primary navigation menu:** `All Categories` is the entry to mega-menu/category tree. Hover interaction captured on homepage (no full mega-menu dump in limited eval; link structure reveals categories).

### Footer — VERIFIED
- **App download:** Links to Google Play (`tel.transcomdigital`) and Apple App Store (`1615345916`)
- **Contact:** `9:00 AM-9:00 PM @ 16212` (tel link), `estore@transcomdigital.com`
- **Social:** Connect with us icons (links observed but not expanded)
- **Columns (4):**
  1. Transcom Digital — EMI Bank List, Terms & Conditions, Contact Us, Store Locator
  2. Customer Service — Shipping & Delivery, Register Your Complaints, Installation, Service Hours
  3. Let Us Help You — FAQs, Chat With Us, Track Orders
  4. After Sales Service — Service Charges, Service Pre-Requisite, Service Payment
- Copyright `© 2022 Transcom Digital. All rights reserved.`

### Breadcrumbs — VERIFIED (PLPs & PDPs)
- Pattern: `Home > Parent Category > Child > Current`
- Examples: `Home > Air Conditioner > Residential AC > Inverter AC`, `Home > Home & Kitchen > Home Appliances > Irons > Dry Irons`, `Home > TV | AV > Television > Smart TV`
- Breadcrumb is a `navigation "Breadcrumb"` landmark with individual link refs.

### Trust / Promo Bar — OBSERVED (Homepage)
- Four items: Free Installation (Selective Items), Original Product Guaranteed, Exchange Program (Selective Products), Secure Payment System

---

## II. Homepage Template — VERIFIED

- **URL:** `https://transcomdigital.com/`
- **Primary purpose:** Brand / category discovery, promotional entry
- **User goal:** Browse by category/brand, discover featured/best-selling products, enter search.

**Components observed:**
- Countdown promo strip: Two list items with countdown timers (e.g., `27 DAYS 12 HOURS 00 MINS 58 SECS` → `/campaign/online-offer`)
- Hero Best Deals carousel: 4+ product cards with image + link + Quick View button (e.g., Haier AC IntelliCool variants)
- Shop By Category grid: 6 cards — TV | AV, Air Conditioner, Refrigerator, Home & Kitchen, Dishwashers, Personal Care — each with image + link + heading (Prev/Next slide buttons disabled state observed)
- Category feature sections (serialized):
  - Electric Kettles (See All) — 5+ product mini-cards + Quick View
  - Microwave Oven (See All) — similar
  - Washing Machine, Celling | Rechargeable Fans, Air Conditioner, Refrigerator, TV | AV, Food Processors — each with See All link
  - Featured Product (See All)
  - Shop By Brand carousel
  - Best Selling (See All)
- SEO long-form block: "Buy Original Electronic products at Transcom Digital..." with internal links to Kitchen/Home/TV/Ref/AC/Personal categories; additional "Why Transcom Digital" copy; category link lists (Mobile-Tablets, TV-AV QLED/Smart/UHD etc.).
- **Interaction notes:**
  - See All links in homepage modules currently resolve to `/undefined` (broken) — VERIFIED (homepage snapshot shows 5+ occurrences)
  - Quick View buttons present on every product mini-card — OBSERVED (not clicked in this phase)
  - Carousels have Previous/Next slide controls; disabled state present when at start.

---

## III. Category / Brand / Search PLP Template — VERIFIED

Shared layout across:
- Top-Level Category (`/air-conditioner`, `/refrigerators`, etc.),
- Mid/Deep Category (`/tv-av/television/smart-tv`, `/home-kitchen/home-appliances/irons/dry-irons`),
- Brand PLP (`/samsung`),
- Search (`/search?Brand=samsung`),
- Campaign PLP (`/campaign/online-offer`)

**Common structure:**
- Breadcrumb nav
- Page title H1 (e.g., `Smart TV`, `Dry Irons`, `Refrigerator`)
- **Filters sidebar (left):**
  - `Filters` heading + `Reset` link
  - **Price:** dual slider (two slider controls observed) + price range text `Price: 0 - 10,55,000` + bucket links e.g., `0 to 1,00,000`, `1,00,001 to 2,00,000` ...
  - **Brand:** checkbox list with counts e.g., `SAMSUNG(14) Haier(10) LG(9) ROWA(6) Transtec(5)` — rendered as Abbr/checkbox elements
  - **Campaign:** e.g., `Online Offer(1)`
  - **Display Size / Screen / Color / Power:** taxonomy-specific (Smart TV shows `55"(10) 43"(7) 65"(7)...` and `32"(2) 43"(1)`; Dry Irons shows `Color: Green(1)`, `Power: 1000W(1)`)
  - **Customer Review:** filter heading present (no rating buckets captured)
  - Filters reset link present
- **Latest Products** mini-carousel (above grid on smart-tv PLP: 4 product thumbnails with links + prices `27,900 25,900` etc.)
- **Sorting & pagination controls:**
  - `Select Sort Option` dropdown/textbox + `Show 12` + `<of 1>` + numeric page input `1` (seen on air-conditioner, smart-tv, dry-irons)
- **Product grid:**
  - Each card: image, title link, category label (e.g., `Smart TV`), original price (strikethrough), discounted price, discount % (e.g., `-23.45%`), EMI badge `EMI36` + `EMI From 1167 Tk/month`, tags `New`, `Pre-Order`, exchange promo `Get Exchange up to 12000 Tk`, and `Quick View` button
  - Example smart-tv PLP shows 12 products per page, 4 pages total on that view (`of 4`)
- **Empty/SEO block:**
  - When no filter applied, PLP may show `Show 12‹of 1›` with zero cards + long-form SEO explanatory copy (air-conditioner, refrigerators, washing-machine display large buying-guide text blocks) — VERIFIED
  - Dry-irons PLP shows `5 results` with full grid; air-conditioner filtered states show empty grid but SEO remains.

**Template variations:**
- **Brand PLP (`/samsung`):** Adds brand sub-category See All rows (with broken `/samsung/undefined` links) above the All Products grid; grid uses identical card markup plus EMI36.
- **Campaign PLP:** Identical grid + `Load more` button at end.
- **Search PLP:** Same chrome; filtered title indicates active brand filter.

**Interaction states:**
- Filter checkboxes/multi-select — OBSERVED as interactive Abbr/inputs (not individually clicked this phase)
- Reset link — OBSERVED
- Sort dropdown — OBSERVED (not enumerated)
- Quick View — OBSERVED
- Pagination input — OBSERVED

---

## IV. Product Detail Page (PDP) Template — VERIFIED (8 samples)

**Shared PDP shell (all categories):**

- **Title H1:** Full product name with model + capacity (e.g., `Daikin Inverter Split Air Conditioner | FTKL12TV16WD | 1 Ton`)
- **Brand link:** `→ /brand/{brand}` (e.g., Daikin brand, Haier brand, Philips brand, DELL brand)
- **Stock status:** `In stock` (most) or `Currently Unavailable` (Dell outlier) — text node adjacent to price
- **Pricing block:**
  - Original price (strikethrough) + sale price + savings amount + discount % e.g., `88,000 81,000 Save 7,000 -7.95%` (AC), `1,38,605 1,45,900 Save 7,295 -5%` (Fridge), `79,900 84,900 Save 5,000 -5.89%` (TV), `3,000` (Trimmer flat), `9,500` (Mixer flat), `22,000` (Dell)
  - EMI line where applicable: `EMI From 2633 Tk/month`, `EMI From 746 Tk/month`, `EMI From 315 Tk/month` + `Avail Bank EMI` link — VERIFIED (present on AC, TV, Mixer, Dell; absent on Fridge sample)
  - EMI badge `EMI36` on PLP cards; PDP shows textual EMI.
- **SKU + Model:** e.g., `SKU: 70091 Model: FTKL12TV16WD` — visible on every PDP
- **Key features bullet list:** 4 bullets typical (e.g., Power chill operation / Coanda airflow / Econo mode / Indoor unit quite operation — AC; DEO Fresh / Twin inverter / Large Storage / Longer Freshness — Fridge; HQLED / Dolby Vision / Dolby Atmos — TV)
- **Options / Variants:**
  - AC: `Choose Ton` with buttons `1 Ton`, `1.5 Ton` — VERIFIED (Daikin PDP shows two variant buttons)
  - Other PDPs: no variant selector
  - **Warranty block** under Options heading:
    - Fridge: `Service-24 M, Parts-24 M, Compressor-120 M` (also AC: `12 M / 12 M / 60 M`, Washing: `24 M / 24 M / Motor-300 M`, TV: `24 M / 24 M / Panel-48 M`, Mixer: `24 M / 0 M / Special Component-60 M`, Trimmer: `24 M / 24 M / Special Component-0 M`, Vacuum: `12 M / 12 M / 12 M`)
  - **Delivery options:** `Home Delivery Enable your Location` / `Store Pickup Enable your Location` — VERIFIED (present on all PDPs; some show combined line)
- **CTAs (main):**
  - `Add To Cart` button (two instances: inline near price and below Options) — background button with `` icon — VERIFIED on all in-stock PDPs
  - `Get Stock Alert` button (replaces Add To Cart when `Currently Unavailable`) — VERIFIED on Dell outlier
- **Secondary actions:**
  - `Compare` button (``), `Wishlist` button (``), `Share` button (``) — trio under key features — VERIFIED on all PDPs
- **Tabs (below media):**
  - Horizontal tab strip: `Overview` / `Feature` / `Specification` / `Review` / `Product Policy` — observed as text nodes on all PDPs (Dell and Philips brand pages show them as active tab labels). Snapshot shows them as generic text + button refs but evaluate confirms presence. Tab content not expanded in read truncation — NOT TESTED (did not click each tab).
  - Some PDPs omit `Feature` (e.g., Philips Mixer shows Overview/Specification/Review/Product Policy only)
- **Media:**
  - Image gallery area: generic `div` placeholders with pointer cursor above title (4+ generic image containers) — OBSERVED but image count not enumerated per PDP beyond 68 images in DOM for Mixer PDP
  - No video confirmed in reads — NOT TESTED (gallery may contain carousel/video on scroll)
- **Related Products:**
  - Section heading `Related Products` at bottom — VERIFIED (Daikin and Dell show it; Mixer/TV/Trimmer reads truncated before related)
  - Dell related shows HP CORE i5 product with Quick View

**Category-specific variations documented:**

- **AC PDP:** Only variation with tonnage selector buttons; compressor warranty 60M; Econo/Coanda feature bullets.
- **Refrigerator PDP:** Emphasizes freshness/inverter tech; largest price point (≈1.38L); warranty compressor 120M; no EMI line in Haier fridge sample.
- **TV PDP:** Panel warranty variant; Dolby/HQLED bullets; EMI line present.
- **Washing Machine PDP:** Motor-300M warranty (300 months); Super Big Drum bullet; Online Offer validity badge `Valid Till: Sep 30, 2026`.
- **Kitchen (Mixer) PDP:** Special Component warranty 60M; wattage/jar bullets; EMI line present.
- **Personal Care (Trimmer):** USB charging / battery bullets; no discount line (flat 3,000); EMI absent.
- **Laptop outlier:** Entire page shares shell but stock state is `Currently Unavailable` → CTA becomes `Get Stock Alert`; otherwise spec bullets (RAM/HDD/GPU).

**Empty / edge states:**
- In-stock: Add To Cart enabled (two instances) — VERIFIED
- Out-of-stock: Disabled Add To Cart replaced by Get Stock Alert — VERIFIED (Dell)

---

## V. Cart Template — VERIFIED

- **URL:** `/cart`
- **Empty state:** Heading `Your Cart`, illustration image, copy `You have not added any product to your cart yet.`
- **Order Summary:** Table with `Subtotal: ৳0`, `Total: 0` (LayoutTable)
- **Terms trigger:** Text `By clicking this button, you agree with the Terms & Conditions` (link → `/page/terms-and-conditions`)
- **Checkout CTA:** Button `Checkout` — `disabled` when empty — VERIFIED
- No cart items, quantity steps, coupon field, or delivery estimate visible in empty state — NOT TESTED (requires items).

## VI. Wishlist Template — VERIFIED

- **URL:** `/wishlist`
- **Guest empty state:** `You have not added any product to your wishlist.` (with iframe about:blank loader)
- No product grid, sharing, or price alert in empty guest state.
- Persistence likely requires login — AUTHENTICATION REQUIRED for populated state.

## VII. Compare Template — VERIFIED

- **URL:** `/compare`
- **Controls:** `Highlight differences` checkbox ( LabelText ), `Clear All` button, three search textboxes placeholder `Model name or part of product details`
- **Table:** Header `Products | Product Preview | Product Preview | Product Preview` with placeholder preview cells and Product Preview images
- **Empty state:** No products compared; table cells empty.

## VIII. Campaign Templates — VERIFIED

- **`/campaigns` (Hub):**
  - H1 `Transcom Campaigns`, H2 `Special Offers`, countdown link `27 DAYS 12 HOURS 02 MINS 21 SECS` → `/campaign/online-offer`
  - Controls `Show 10` + pagination `Showing 1 of 1 result <of 1>` + numeric page input `1`
- **`/campaign/online-offer` (Detail PLP):**
  - Pre-order section with identical product card grid as PLP (EMI36, discount, New tags)
  - Header `All Products` with `See All` link to filtered search `?Campaign=640030c5ba29e86494d1f4ad&isCampaign=true&Stock Status=Show all products`
  - `Load more` at end of grid.

## IX. Login Template — VERIFIED

- **URL:** `/login`
- **Copy:** `Log In`, `Welcome back! Enter your mobile phone number to log in to your account. If you are a new user, your account will be created.`
- **Form:** Bangladesh prefix `+880` selector (image `Bangladesh ( +880)`), two textbox inputs (phone number split-field), `Next` button.
- No password field; OTP flow implied (Next triggers OTP). No social login observed in snapshot.
- No post-login state captured this phase — AUTHENTICATION REQUIRED for dashboard exploration (phone `01571721235` reserved).

## X. Store Locator Template — VERIFIED

- **URL:** `/store-locator`
- **Mode toggle:** `Find Store | List View | Map View`
- **Search:** `Search by store name` textbox + search button `` + district dropdown `All Districts`
- **Store cards:** Each shows Outlet name, full address, hours `Saturday - Thursday 9.30 AM- 9.00 PM`, `Schedule your visit` button — 4 districts observed: Sirajgonj, Kishorgonj, Chittagong, Sylhet
- **Map:** `Map` region with Mapbox logo — VERIFIED
- **Actions:** `Show more ` button for pagination.

## XI. Exchange Template — VERIFIED

- **URL:** `/exchange`
- **Purpose:** Trade-in selector
- **Cards:** 2 category cards — Refrigerator (link `→ /exchange/63735c57285af729b535a425?category=refrigerators` with image), Washing Machine (link `→ /exchange/637f1263285af729b5c1b?category=washing-machine`)
- No valuation form visible at hub level; detail flow not entered this phase (NOT TESTED beyond hub).

## XII. Policy Page Template — VERIFIED

- **URL:** `/page/terms-of-use`
- **Loader:** `Loading content...` spinner + duplicate nav lists `ALL` with identical link sets
- **External policy:** Links to `about.transcomdigital.com/terms-of-use` etc. (Product, Web Order, Delivery, Payment, Exchange, Warranty, Service, Privacy)
- **Content:** H2 `Policies & Terms and Conditions` with prose paragraphs + sub-headings: Copyright, Information on Our Site, Your Account and Registration Obligations, Order Confirmation, Termination of Use, Use of the Transcom Digital Properties
- Rendering uses iframe/dialog wrappers; no additional UI beyond article.

## XIII. Cross-Cutting UI Components Inventory

| Component | Location(s) | Exists | Notes |
|-----------|-------------|--------|-------|
| Search box + autocomplete | Header (all pages) | VERIFIED exists; autocomplete NOT TESTED beyond type test (suggestions not captured due to timeout) | Placeholder Search Here |
| Product cards | PLPs, campaign, related, homepage | VERIFIED | Image + title link + category label + strikethrough price + sale price + discount % + EMI36 badge + New/Pre-Order tag + Quick View |
| Quick View button | Every product card | VERIFIED presence; interaction NOT TESTED |  |
| Wishlist (heart icon) | Header + PDP + PLP | VERIFIED |  |
| Compare button | PDP, PLP | VERIFIED |  |
| Share button | PDP | VERIFIED |  |
| EMI badge / financing line | PLP cards + PDP | VERIFIED |  |
| Filters | PLP sidebar | VERIFIED |  |
| Sorting | PLP | VERIFIED (Select Sort Option) | Options not enumerated |
| Tabs (Overview/Spec/Review) | PDP | VERIFIED presence; content NOT TESTED |  |
| Pagination | PLPs, campaign hub | VERIFIED (Show 12 / page input) |  |
| Breadcrumbs | PLP/PDP | VERIFIED |  |
| Stock / availability badge | PDP | VERIFIED |  |
| Warranty block | PDP Options | VERIFIED |  |
| Delivery options | PDP Options | VERIFIED |  |
| Countdown timer | Campaign hub | VERIFIED |  |
| Map (Mapbox) | Store Locator | VERIFIED |  |
| Disabled / empty states | Cart/Wishlist/Compare/Pagination | VERIFIED |  |
| Modals/Popups | Not triggered this phase; dialog in policy page | OBSERVED only |  |
| Tooltips/Notifications | Not observed | NOT TESTED |  |

---
*All components documented from live snapshot/read/evaluate outputs; no evaluative language. Where interaction not exercised, marked NOT TESTED or AUTHENTICATION REQUIRED.*
