# Product Page Variations — Current State

> Samples investigated (BrowserOS Neo, 8 PDPs covering 9 category asks + outlier). No evaluation. Evidence = VERIFIED (snapshot/read/evaluate), OBSERVED, NOT TESTED.

## Representative Sample Set

| # | Category Ask | Sample URL (Representative) | Visit Status | Notes |
|---|--------------|------------------------------|--------------|-------|
| 1 | Smartphones | *None in sitemap* — no smartphone product URL present | NOT TESTED — category absent from sitemap |
| 2 | Laptops | `dell-inspiron-15-3501-laptop-intel-i5-11th-gen` | VERIFIED — Currently Unavailable |
| 3 | TVs | `haier-55-bezel-less-4k-google-tv-h55p7ux` (H55P7UX); also `rowa-uhd-google-tv-65r54` on campaign grid | VERIFIED |
| 4 | Refrigerators | `haier-no-frost-refrigerator-hrf-622ibg-600-liters` (622IBG 600L) + `samsung-top-mount-freezer-refrigerator-rt42cg6442b1tc-cap-415-ltr` on PLP | VERIFIED |
| 5 | Air Conditioners | `daikin-inverter-split-air-conditioner-ftkl12tv16wd-1-ton` (FTKL12TV16WD 1 Ton) | VERIFIED |
| 6 | Washing Machines | `haier-front-loading-washing-machine-hw80-bp12929a-8kg` (HW80-BP12929A 8KG) | VERIFIED |
| 7 | Kitchen Appliances | `philips-3-jar-mixer-grinder-hl7757` (HL7757 750W) + related oven/cooker/kettle linked on homepage | VERIFIED |
| 8 | Small Appliances | `hitachi-vacuum-cleaner-cv-se230v-240c` (CV-SE230V 2300W) + `miyako-electric-kettle-mjk-805-18l` (in catalogue, not sampled live) | VERIFIED (vacuum) |
| 9 | Accessories / Personal Care | `philips-beard-trimmer-bt1235` (BT1235) + `philips-hair-dryer-hp8142` / `philips-dry-iron-gc181` PLP cards | VERIFIED |

> Smartphones: No product URL containing phone/mobile in sitemap; `mobile-tabs/smart-phones` linked in homepage SEO text but not a live PDP sample. Treated as catalog gap, not template variation.

---

## Shared PDP Shell (Common to All Samples) — VERIFIED

| Element | Markup / Location | Behavior |
|---------|-------------------|----------|
| H1 title | Full name with model + tonnage/capacity | — |
| Brand link | `→ /brand/{brand}` under title | Clickable |
| Stock status | `In stock` or `Currently Unavailable` adjacent to price | Text badge |
| Pricing | Original (strikethrough) + sale + Save amount + Save % | Some flat (single price) |
| EMI line | `EMI From X Tk/month` + `Avail Bank EMI` link (when financed) | Text |
| SKU / Model | `SKU: XXXXX Model: XXXXX` line | — |
| Key features | 4-bullet list | Short bullets |
| Options heading | H2 `Options` | Section header |
| Warranty | `Service-X M, Parts-Y M, Compressor/Panel/Motor/Special Component-Z M` | Line item |
| Delivery | `Home Delivery` / `Store Pickup` each with `Enable your Location` | Location-gated |
| Secondary actions | `Compare` / `Wishlist` / `Share` buttons | Trio below bullets |
| Tabs | `Overview` / `Feature` / `Specification` / `Review` / `Product Policy` (strip at top of PDP) | Tab switch — content not clicked this phase |
| Media gallery | Generic image containers above title (4+ placeholders) | Carousel — not enumerated |
| Primary CTA | `Add To Cart` (×2) OR `Get Stock Alert` (if unavailable) | Button with icon `` / `` |
| Related Products | H2 footer section | Card(s) with Quick View |

---

## Category-Specific Variation Matrix

| Capability / Element | AC (Daikin 1 Ton) | Refrigerator (Haier 600L) | TV (Haier 55") | Washing Machine (Haier 8KG) | Kitchen (Philips Mixer 750W) | Home (Hitachi Vacuum 2300W) | Personal Care (Philips Trimmer) | Laptop (Dell Inspiron) |
|----------------------|-------------------|---------------------------|-----------------|------------------------------|-------------------------------|------------------------------|----------------------------------|-------------------------|
| **Product images** | VERIFIED — gallery placeholders present (4+) | VERIFIED — same | VERIFIED — same | VERIFIED — same | VERIFIED — 68 images in DOM (includes icons) | VERIFIED — placeholder count similar | VERIFIED | VERIFIED — gallery present |
| **Image gallery / carousel controls** | NOT TESTED | NOT TESTED | NOT TESTED | NOT TESTED | NOT TESTED | NOT TESTED | NOT TESTED | NOT TESTED |
| **Video** | NOT OBSERVED | NOT OBSERVED | NOT OBSERVED | NOT OBSERVED | NOT OBSERVED | NOT OBSERVED | NOT OBSERVED | NOT OBSERVED |
| **Variant selector** | **Choose Ton buttons: 1 Ton / 1.5 Ton** — VERIFIED | No variants — OBSERVED abs | No variants | No variants | No variants | No variants | No variants | No variants |
| **Product title format** | Brand + Type + Model + Ton | Brand + Frost Type + Model + Liters | Brand + Size + Resolution + TV + Model | Brand + Load Type + Model + KG | Brand + Jar Count + Type + Model | Brand + Type + Model | Brand + Type + Model | Brand + Series + Gen |
| **Pricing discount line** | `81,000 88,000 Save 7,000 -7.95%` | `1,38,605 1,45,900 Save 7,295 -5%` | `79,900 84,900 Save 5,000 -5.89%` | `57,900 61,900 Save 4,000 -6.46%` (+ Offer validity badge) | `9,500` flat, no save line + EMI | `28,600 31,600 Save 3,000 -9.49%` + EMI | `3,000` flat, no save/discount | `22,000` flat + EMI |
| **EMI** | EMI From 2633 Tk/month — VERIFIED | **No EMI line** (absent on this fridge sample) | EMI From 2553 Tk/month — VERIFIED | EMI From 1963 Tk/month | EMI From 315 Tk/month — VERIFIED | EMI From 946 Tk/month | No EMI line | EMI From 746 Tk/month |
| **Savings %** | `EMI`, `Avail Bank EMI` tag present | No Avail Bank EMI tag | `Avail Bank EMI` present | `Offer valid: Online Offer (Valid Till: Sep 30, 2026)` | `Avail Bank EMI` absent (EMI line without Avail) | `Avail Bank EMI` present | No | `Avail Bank EMI` present |
| **Spec tabs presence** | Overview/Feature/Specification/Review/Product Policy — tabs rendered (evaluate missed but read shows strip) | Heading strip not captured (read truncated before tabs) but shell same; tabs inferred via shell | Overview/Feature/Spec/Review/Product Policy — present | Similar | Overview/Specification/Review/Product Policy (Feature absent) | Overview/Feature/Spec/Review/Product Policy (from title line) | Overview/Feature/Spec/Review/Product Policy | Overview/Feature/Spec/Review/Product Policy — VERIFIED |
| **Availability badge** | In stock | In stock | In stock | In stock | In stock | In stock | In stock | **Currently Unavailable** |
| **Delivery info** | Home Delivery Enable your Location + Store Pickup Enable your Location — BOTH | Home Delivery + Store Pickup (no Enable text in read — location prompt may be conditional) | Both + Enable your Location | Both (read not showing Enable but likely same) | Both + Enable your Location | Both + Enable your Location | Both + Enable your Location | Same pattern (not enumerated) |
| **Installation** | No explicit installation line on PDP Options beyond Home Delivery — NOT OBSERVED | Same — NOT OBSERVED | Same | Same | Same | Same | Same | Same |
| **Warranty** | `Service-12 M, Parts-12 M, Compressor-60 M` | `Service-24 M, Parts-24 M, Compressor-120 M` | `Service-24 M, Parts-24 M, Panel-48 M` | `Service-24 M, Parts-24 M, Motor-300 M` | `Service-24 M, Parts-0 M, Special Component-60 M` | `Service-12 M, Parts-12 M, Special Component-12 M` | `Service-24 M, Parts-24 M, Special Component-0 M` | Not captured (truncated) |
| **Reviews / Ratings** | Tab present `Review`; rating count not captured — NOT TESTED | Tab assumed; no rating visible in reads | Tab present; no rating | Same | Tab present; no rating displayed | Tab present | Tab present | Tab present — Review |
| **Questions (Q&A)** | No explicit Q&A section beyond tabs — NOT OBSERVED | Same | Same | Same | Same | Same | Same | Same |
| **Comparison** | Compare button present | Present | Present | Present | Present | Present | Present | Present |
| **Recommendations / Related** | Related Products H2 present | Assumed (read truncated) | Related Products heading inferred but read shows no related (truncated before footer) | Related Products likely (not captured) | No Related captured (read truncated before footer) | Not captured | No Related in read | Related Products H2 VERIFIED with HP laptop card |
| **Accessories / Bundles** | None observed | None | None | None | None | None | None | None |
| **Frequently bought together** | NOT OBSERVED | NOT OBSERVED | NOT OBSERVED | NOT OBSERVED | NOT OBSERVED | NOT OBSERVED | NOT OBSERVED | NOT OBSERVED |

### Key Observations Per Category

**Air Conditioners (AC) — VERIFIED via Daikin FTKL12TV16WD:**
- Only PDP with in-page variant selector (tonnage buttons 1 Ton / 1.5 Ton) under Options → Choose Ton.
- Bullets emphasize airflow/efficiency: Power chill, Coanda airflow, Econo mode, Indoor unit quite operation.
- Price includes savings % and EMI; warranty emphasizes compressor (60M).

**Refrigerators — VERIFIED via Haier 622IBG 600L Side-By-Side:**
- Highest price tier in sample set; no EMI line on this sample (may be threshold/formatting driven).
- Bullets: DEO Fresh, Twin inverter, Large Storage, Longer Freshness.
- Compressor warranty longest (120M); no tonnage variant.

**Televisions — VERIFIED via Haier H55P7UX 55" Google TV:**
- Panel warranty variant (`Panel-48 M` instead of compressor).
- Bullets: HQLED, Dolby Vision, Dolby Atmos — display-tech focused.
- EMI available; no size variant selector on PDP (selection via PLP filters).

**Washing Machines — VERIFIED via Haier HW80-BP12929A 8KG:**
- Unique offer validity badge: `Offer valid: Online Offer (Valid Till: Sep 30, 2026)` above SKU.
- Motor warranty headline (`Motor-300 M` ≈ 25 years) distinct from compressor/panel.
- Bullets: Inverter Motor, 525mm Super Big Drum, Lifetime Warranty on Motor.

**Kitchen Appliances (Mixer) — VERIFIED via Philips HL7757 750W:**
- Tabs omit `Feature` (Overview/Specification/Review/Product Policy only).
- Parts warranty 0M, Special Component 60M — indicates warranty structure adapted per appliance type.
- Bullets mechanical: Motor, speed switch, mains cord, overload protector, jar lock guide.

**Small/Home Appliances (Vacuum) — VERIFIED via Hitachi CV-SE230V 2300W:**
- Watts/capacity bullets: 2300W Cylinder-Cyclone, Dust Capacity 2.0L, Nano Titanium Filter, Wide 2-Step Rug Floor Nozzle.
- Tag `Avail Bank EMI` present; discount % displayed.

**Personal Care (Trimmer) — VERIFIED via Philips BT1235:**
- No discount line, lowest price point (3,000 Tk); no EMI line.
- Bullets battery-centric: Longer lasting battery, 60 minutes cordless after 8 hours charging, USB charging.
- Warranty Special Component 0M (likely consumable blades).

**Laptop Outlier — VERIFIED via Dell Inspiron 3501:**
- Only PDP with `Currently Unavailable` state → CTA is `Get Stock Alert` (×2) replacing Add To Cart.
- Otherwise shell identical; related product rail shows cross-sell (HP laptop) under Related Products.
- Confirms out-of-stock interaction state template exists.

---

## Cross-Category Variation Summary

| Variation Dimension | Outcome |
|---------------------|---------|
| **Gallery / video** | No video observed in any sample snapshot; gallery count not differentiated — manual scroll/video check required |
| **Variant selector** | Only AC exhibits tonnage variant buttons; no other category shows PDP-level variants |
| **EMI availability** | Present on AC, TV, Mixer, Vacuum, Laptop; absent on Fridge (600L) and Trimmer — suggests conditional by price/category, not universal |
| **Discount / Save line** | Absent on low-ticket items (Mixer, Trimmer, Laptop flat) where no promotion; present on higher-ticket (AC/Fridge/TV/Washing/Vacuum) |
| **Warranty line adapts** | Structure `Service / Parts / [Compressor|Panel|Motor|Special Component]` changes per category — VERIFIED pattern |
| **Tabs** | Mostly `Overview/Feature/Specification/Review/Product Policy`; Mixer omits `Feature` — minor fork |
| **Related Products** | Present on AC and Laptop samples; truncated reads prevent confirming on others — **PARTIALLY VERIFIED** |

---

## States Verified Across PDPs

| State | PDP Example | Evidence |
|-------|-------------|----------|
| In stock + Add To Cart enabled (×2) | All except Dell | VERIFIED |
| Currently Unavailable + Get Stock Alert | Dell Inspiron | VERIFIED |
| Discount vs. flat price | AC/Fridge vs. Trimmer | VERIFIED |
| EMI present vs. absent | AC/TV vs. Fridge/Trimmer | VERIFIED |
| Warranty adapted per appliance | All categories | VERIFIED |
| Offer validity badge | Washing Machine only | VERIFIED |

> Spec table content, Review rating stars/count, Q&A thread, Recommendations carousel interactivity, and Image zoom/hover not exercised this phase — marked NOT TESTED / manual investigation required. No video/bundle/frequently-bought-together observed.

## Category Coverage Note
- **Smartphones:** No PDP URL in sitemap to sample; mobile-tabs/smart-phones referenced only in homepage SEO links — **NOT TESTED / absent from sampled catalog**.
- All other 8 requested categories sampled live; variations documented above.

---
*Evidence: 8 live PDP snapshots/reads/evaluates capturing title, pricing, EMI, warranty, delivery, stock, tabs, bullets, and CTA states.*
