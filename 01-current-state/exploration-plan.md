# Exploration Plan — Unique Page Templates

> Derived from `sitemap.xml` (167 URLs). Grouping by URL pattern and inferred page structure. Flat product slugs at root suggest shared PDP template but content variations by appliance category require separate verification. Hierarchical category pages share PLP template but differ in filter taxonomy.

## Summary

- **Total URLs in sitemap:** 167
- **Unique page template groups identified:** 22
- **Template variations requiring separate inspection:** 9 product category variations + 4 PLP depth variations
- **Exploration scope:** Representative URLs prioritized P0 > P1 > P2 > P3 to ensure critical commerce journeys covered without visiting every product URL.

## Template Inventory

| # | Page Type | URL Count | Template Variation | Representative URL | Exploration Priority | Reason |
|---|-----------|-----------|--------------------|---------------------|----------------------|--------|
| 1 | Homepage | 1 | Single homepage template | `https://transcomdigital.com/` | **P0** | Entry point for all journeys; header/nav/mega-menu/footer discovery |
| 2 | Top-Level Category PLP — Air Conditioner | 1 | PLP L1 — large appliance with subtype filters (inverter/non-inverter) | `https://transcomdigital.com/air-conditioner` | **P0** | Critical commerce journey — high-value category |
| 3 | Top-Level Category PLP — Refrigerators | 1 | PLP L1 — frost/no-frost taxonomy | `https://transcomdigital.com/refrigerators` | **P0** | Critical commerce journey |
| 4 | Top-Level Category PLP — Home & Kitchen | 1 | PLP L1 — umbrella category with home vs kitchen sub-split | `https://transcomdigital.com/home-kitchen` | **P0** | Discovery path for many small appliances |
| 5 | Top-Level Category PLP — Personal Care | 1 | PLP L1 — beauty/personal care filters | `https://transcomdigital.com/personal-care` | **P1** | Important user journey — distinct filter taxonomy (shaver/trimmer etc.) |
| 6 | Top-Level Category PLP — Washing Machine | 1 | PLP L1 — laundry-specific filters | `https://transcomdigital.com/washing-machine` | **P0** | Critical commerce journey |
| 7 | Mid-Level Category PLP — Depth 2 | 11 | PLP L2 — e.g., residential AC, home-appliances vs kitchen-appliances, TV/television | `https://transcomdigital.com/air-conditioner/residential` | **P1** | Validates breadcrumb + filter narrowing |
| 8 | Deep Category PLP — Depth 3 | 19 | PLP L3 — e.g., inverter-ac, mixer-grinders, side-by-side, smart-tv | `https://transcomdigital.com/air-conditioner/residential/inverter-ac` | **P1** | Test filter + sorting on narrowed set |
| 9 | Deepest Category PLP — Depth 4 | 4 | PLP L4 — e.g., dry-irons, convection microwave | `https://transcomdigital.com/home-kitchen/home-appliances/irons/dry-irons` | **P2** | Verify breadcrumb depth + empty/loaded states |
| 10 | Brand Listing Page | 13 | Brand PLP — brand-filtered product grid (distinct header/brand hero possible) | `https://transcomdigital.com/samsung` | **P1** | Brand → Product discovery path; alternate to category |
| 11 | Product Detail — Air Conditioner (Inverter/Non-Inverter) | ~17 (subset of 101) | PDP Variation: AC — specs include tonnage, BTU, inverter, energy rating | `https://transcomdigital.com/daikin-inverter-split-air-conditioner-ftkl12tv16wd-1-ton` | **P0** | Must verify AC-specific specs, installation, warranty, EMI |
| 12 | Product Detail — Refrigerator (No-Frost / Side-by-Side / Top-Mount) | ~14 | PDP Variation: Refrigerator — capacity liters, door type, frost type | `https://transcomdigital.com/haier-no-frost-refrigerator-hrf-622ibg-600-liters` | **P0** | Verify capacity, door config, delivery/installation messaging |
| 13 | Product Detail — Television (Smart/QLED/UHD) | ~9 | PDP Variation: TV — screen size, resolution, OS, bezel | `https://transcomdigital.com/haier-55-bezel-less-4k-google-tv-h55p7ux` | **P0** | Verify display specs, video, comparison |
| 14 | Product Detail — Washing Machine (Front/Top Load) | ~5 | PDP Variation: Washing Machine — kg capacity, load type, RPM | `https://transcomdigital.com/haier-front-loading-washing-machine-hw80-bp12929a-8kg` | **P0** | Verify drum type, capacity filters |
| 15 | Product Detail — Kitchen Appliances (Mixer-Grinder, Oven, Cooker, Kettle) | ~18 | PDP Variation: Kitchen — wattage, capacity liters, jar count | `https://transcomdigital.com/philips-3-jar-mixer-grinder-hl7757` | **P1** | Small appliance PDP may lack installation/EMI but have bundles |
| 16 | Product Detail — Home Appliances (Vacuum, Iron, Water Purifier) | ~11 | PDP Variation: Home — generic (iron power, purifier RO/UV) | `https://transcomdigital.com/hitachi-vacuum-cleaner-cv-se230v-240c` | **P1** | Check filter relevance for low-ticket items |
| 17 | Product Detail — Personal Care (Trimmer, Dryer, Straightener) | ~7 | PDP Variation: Personal Care — battery, heat settings | `https://transcomdigital.com/philips-beard-trimmer-bt1235` | **P1** | Verify if reviews/Q&A present for personal-care |
| 18 | Product Detail — Laptop/Computing (Outlier) | 1 | PDP Variation: Laptop — Intel gen, RAM/Storage specs | `https://transcomdigital.com/dell-inspiron-15-3501-laptop-intel-i5-11th-gen` | **P2** | Single outlier; check if template diverges |
| 19 | Search Results Page | 1 (plus dynamic queries) | PLP variant driven by search query/brand filter | `https://transcomdigital.com/search?Brand=samsung` (+ test `?q` manually) | **P0** | Search journey; autocomplete/suggestions/filter interplay |
| 20 | Campaign / Promotional Hub + Detail | 2 | Content + offer grid → offer detail | `https://transcomdigital.com/campaigns` & `https://transcomdigital.com/campaign/online-offer` | **P1** | Promotional discovery mechanism |
| 21 | Utility / Service Pages | 6 | Cart, Wishlist, Compare, Login, Store Locator, Exchange (+ policy) | `https://transcomdigital.com/cart` | **P0** (Cart/Wishlist/Login) / **P2** (Compare, Store Locator, Exchange, Terms) | Cart/Checkout/Account are critical; others supporting |
| 22 | Checkout / Account (Not in sitemap, discovered via navigation) | unknown | Checkout steps (address/delivery/payment), Account dashboard/profile/addresses/orders | *Discovered via header/Cart → Checkout and Login flow* | **P0** | Requires browser exploration to confirm existence and capture URL patterns |

## Priority Definitions

- **P0 = Critical commerce journey** — Must be explored first; core purchase funnel
- **P1 = Important user journey** — High-frequency discovery or category-specific verification
- **P2 = Supporting experience** — Secondary flows, service content, edge variations
- **P3 = Low priority / informational** — Policy, static content; explore if time permits

## Exploration Strategy

1. **Do not visit all 101 product URLs.** Validate template by sampling one representative per variation (rows 11–18 = 8 products). If variations diverge (e.g., AC shows installation info but trimmer does not), document as variation rather than new template.
2. **PLP depth sampling:** Visit one L1, one L2, one L3, one L4 category to confirm shared template vs. depth-specific UI (breadcrumb, filter count).
3. **Brand PLP:** Visit 2 brands (Samsung — large catalog, Philps — small appliance) to check brand-specific hero vs. generic filter.
4. **Search:** Test brand-filter URL plus manual query via header search (requires browser).
5. **Authenticated flows:** After verifying guest journeys, attempt Login with `01571721235` and explore Account, Wishlist persistence, Cart checkout — stopping before payment confirmation.
6. **Undiscovered pages:** During browser exploration, note any navigation-revealed routes not in sitemap (e.g., `/checkout`, `/account`, `/account/orders`) and append to inventory.

## High-Priority Exploration Order (Execution Sequence)

1. Homepage → Header/Mega-Menu/Footer capture
2. Top-Level PLPs (rows 2–6)
3. Brand PLP (Samsung)
4. Search Results
5. Product Detail samples (AC, Refrigerator, TV, Washing Machine — P0)
6. Cart, Wishlist, Compare
7. Product Detail samples (Kitchen, Personal Care — P1)
8. Campaign, Store Locator, Exchange, Policy
9. Deep PLPs (L3/L4)
10. Authentication (+ Account, Checkout safe exploration)

## Representative URL Master List (To Visit)

```
P0 — https://transcomdigital.com/
P0 — https://transcomdigital.com/air-conditioner
P0 — https://transcomdigital.com/refrigerators
P0 — https://transcomdigital.com/washing-machine
P0 — https://transcomdigital.com/daikin-inverter-split-air-conditioner-ftkl12tv16wd-1-ton
P0 — https://transcomdigital.com/haier-no-frost-refrigerator-hrf-622ibg-600-liters
P0 — https://transcomdigital.com/haier-55-bezel-less-4k-google-tv-h55p7ux
P0 — https://transcomdigital.com/haier-front-loading-washing-machine-hw80-bp12929a-8kg
P0 — https://transcomdigital.com/search?Brand=samsung
P0 — https://transcomdigital.com/cart
P0 — https://transcomdigital.com/login
P1 — https://transcomdigital.com/personal-care
P1 — https://transcomdigital.com/air-conditioner/residential/inverter-ac
P1 — https://transcomdigital.com/samsung
P1 — https://transcomdigital.com/philips-3-jar-mixer-grinder-hl7757
P1 — https://transcomdigital.com/philips-beard-trimmer-bt1235
P1 — https://transcomdigital.com/campaigns
P1 — https://transcomdigital.com/hitachi-vacuum-cleaner-cv-se230v-240c
P2 — https://transcomdigital.com/home-kitchen/home-appliances/irons/dry-irons
P2 — https://transcomdigital.com/dell-inspiron-15-3501-laptop-intel-i5-11th-gen
P2 — https://transcomdigital.com/compare
P2 — https://transcomdigital.com/store-locator
P2 — https://transcomdigital.com/exchange
P2 — https://transcomdigital.com/page/terms-of-use
P2 — https://transcomdigital.com/campaign/online-offer
```

## Pages Requiring Separate Investigation (Potential Template Forks)

- **Exchange flow** (`/exchange/{id}?category=...`) — may be a distinct service funnel, not a standard PLP.
- **Outlier product** `dell-inspiron...` — only computing product in catalog; may use different spec table.
- **Trailing-hyphen products** (`pureit-classic-23l-`, etc.) — verify if they resolve or redirect.
- **TV hierarchy** — `tv-av` root missing; may reveal navigation vs. sitemap divergence.

---
*Next step: Systematic browser exploration of representative URLs per Step 3.*
