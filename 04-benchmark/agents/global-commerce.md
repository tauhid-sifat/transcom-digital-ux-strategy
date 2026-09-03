# Global E-Commerce Benchmark — Transcom Digital (Phase 4, Agent A)

> **Agent:** A — Global E-Commerce Benchmark | **Date:** 2026-09-03
> **Context:** `00-input/sitemap-analysis.md` (167 URLs), `01-current-state/*` (site-inventory, page-analysis, product-discovery, product-page-variations, user-journeys, ecommerce-capabilities, personalization-current-state), `02-ux-audit/*` (issue-register 32 issues, executive-summary), `03-opportunities/*` (opportunity-pool 15, cross-review 38→15)
> **Scope:** Homepage, Navigation, Search, Discovery, Category Browsing, Filtering, Product Cards, PDP, Cart, Checkout, Account, Retention. Patterns selected for **UX relevance to Transcom Digital** (electronics / home appliance, Bangladesh, mobile-first, Bangladesh Taka 50k–1.5L considered purchases, high trust sensitivity, EMI and exchange programs), not fame alone.
> **Method:** Real experiences validated via live page reads where possible + websearch spot-checks on pattern existence. Classifications use four tiers: INDUSTRY STANDARD / EMERGING PATTERN / DIFFERENTIATOR / EXPERIMENTAL. Applicability rated HIGH/MEDIUM/LOW for Transcom specifically.

---

## Summary Map — 12 Patterns

| # | Pattern | Company Anchors | Classification | Journey Primary | Applicability |
|---|---------|-----------------|----------------|-----------------|---------------|
| 1 | Pincode-First Serviceability & Landed-Cost Estimator on PDP | Amazon.in, Flipkart, Daraz (BD), Best Buy (US ZIP) | **INDUSTRY STANDARD** (South Asia) | E: PDP → Cart | **HIGH** |
| 2 | Requirement-Led Guided Selling — Quiz → Filtered PLP → PDP Verdict | Coolblue, Best Buy, Crutchfield | **DIFFERENTIATOR** | B/C: Category decision | **HIGH** |
| 3 | Persistent Compare Workspace — Auto-Populated, Highlight Differences, Total-Cost Pin | Coolblue, Best Buy, Samsung, RTINGS | **INDUSTRY STANDARD** (considered electronics) | D: Compare 2–3 | **HIGH** |
| 4 | Rich Media Inspection Suite — Hover/Pinch Zoom, Video, 360°, Dimension Overlay, AR | Apple, Samsung, Dyson, Coolblue | **INDUSTRY STANDARD** | PDP research (all) | **HIGH** |
| 5 | True Cost & EMI Tenure Planner — Interactive Monthly Affordability Row | Amazon.in (EMI), Best Buy (financing), Currys, MediaMarkt | **EMERGING PATTERN** | B/C/E price decision | **HIGH** |
| 6 | Variant & Family Navigator — Sibling Chips with Price Delta & Stock Badge | Apple, Samsung, Sony, Uniqlo (catalog model) | **INDUSTRY STANDARD** | PDP variant explore | **HIGH** |
| 7 | Predictive Autocomplete — Product/SKU/Brand/Category + Recent Searches | Amazon, Flipkart, ASOS, John Lewis | **INDUSTRY STANDARD** | A: Direct search | **HIGH** |
| 8 | Zero-Result Recovery — Did-You-Mean, Typo Tolerance, Facet Relaxation | ASOS, John Lewis, Wayfair, Amazon | **INDUSTRY STANDARD** (typo) / **EMERGING** (facet-relax) | A failure path | **MEDIUM** |
| 9 | Social Proof Layer — Aggregate Rating on PLP Cards + Review Facet + Verified Q&A | Amazon, Best Buy, Sephora, Coolblue | **INDUSTRY STANDARD** | B/C shortlist, PDP confidence | **HIGH** |
| 10 | Browse Resumption — Recently Viewed Rail + "Continue Where You Left Off" Deep-Link | Amazon, eBay, Zalando, ASOS | **INDUSTRY STANDARD** | F: Returning / multi-session | **HIGH** |
| 11 | Installation Feasibility Checker → Bookable Slot (Operations-Linked) | Coolblue Eigen Plan, Best Buy Geek Squad, Home Depot | **DIFFERENTIATOR** | PDP → Post-purchase (AC/Fridge/Washer) | **MEDIUM** |
| 12 | Cart Drawer & Checkout Transparency — Mini-Cart, Landed-Cost Breakdown, Stepper | Apple, ASOS, Best Buy, Zalando | **INDUSTRY STANDARD** | E: Cart → Checkout | **HIGH** |

*Evidence notes and file:line refs included per pattern. Websearch spot-checks flagged `[WS]`.*

---

## Pattern 1 — Pincode-First Serviceability & Landed-Cost Estimator (PDP)

- **Company:** Amazon.in / Flipkart (India), Daraz (Bangladesh), Best Buy (US ZIP-code delivery estimator) — the South Asian pincode pattern is the direct analogue; Best Buy validates ZIP-code/pincode-before-Add pattern in the US (`https://www.bestbuy.com/site/help-topics/shipping-costs-and-timing/...` estimated arrival by ZIP on PDP). Emerge Digital Shopify case study 2026-05 documents identical widget between variant selector and Add to Cart [WS].
- **Journey:** PDP (primary) → Cart summary propagation; also PLP → PDP entry for bulky goods (refrigerator 600L, AC 1–1.5 Ton, washing machine 8KG).
- **Pattern:** Text input for pincode / area / district (not a location-permission gate) placed **between price block and Add to Cart**. On submit: `Serviceable: Yes/No`, `Delivery SLA (e.g., 2–3 days)`, `Delivery fee (or Free)`, `Free installation flag + fee if paid`, `Nearest store-pickup alternative with distance`. Result persists in session and pre-fills Cart Order Summary landed cost. Blocks Add to Cart only when undeliverable (with alternatives).
- **User Problem:** Transcom PDP currently gates delivery behind `Home Delivery — Enable your Location` + `Store Pickup — Enable your Location` on every sample (`01-current-state/page-analysis.md:125`, `01-current-state/product-page-variations.md:59`). Users cannot answer "can this Haier 622L side-by-side be delivered to Rajshahi, by when, at what fee, with free install?" while staring at `1,38,605 Tk Save 7,295` — research cost is pushed to checkout where `CHECKOUT-01 P1` blocks discovery (`02-ux-audit/issue-register.md:38`).
- **How It Works:**
  1. PDP renders small input `Enter pincode / Select area` + `Check` button beneath Options heading (not under a permission prompt).
  2. Call to zone/SLA matrix (zone → SLA + fee table) and install-fee table per SKU (`Free Installation Selective Items` homepage bar claim must resolve per SKU at `01-current-state/page-analysis.md:34`).
  3. Response card: green tick `Deliverable to 1212 Dhaka — Delivery in 2–4 days — Delivery Tk 0 — Installation Free (AC bracket extra)` OR red `Not deliverable — Nearest pickup: Transcom Dhanmondi 1.2km`.
  4. Persist key `deliveryPincode` + result in `sessionStorage`; Cart inherits `Subtotal + Delivery + Install → Total` without re-entry.
  5. No browser geolocation permission requested until user opts in; pincode entry is the default.
- **Why It Works:**
  - Moves failure **before** commitment (checkout pincode mismatch is the #1 high-ticket drop-off in South Asia logistics; Flipkart/Amazon.in both surface COD/pincode checks on PDP for TVs/ACs).
  - Separates *zone feasibility* (ops data) from *personalization* (remember pincode). 80% is fulfillment data, 20% is memory — correct ownership prevents "location-aware personalization" framing.
  - Scales to store-pickup: Bangladesh district-heavy fulfillment (Transcom has 30+ districts in Store Locator at `01-current-state/page-analysis.md:201-204`) benefits from pickup-alternative when home delivery is slow.
  - Reduces support load: Emerge case study reports drop in "where do you deliver?" tickets after moving widget to PDP.
  - Websearch confirms Best Buy renders `Entering your shipping destination ZIP code ... can result in greater accuracy for your estimated arrival date` on PDP/checkout — same mechanic with different label.
- **Potential Lesson (Transcom):**
  - Replace `Enable your Location` gate with single `Enter area / pincode` + `Check` on all 101 PDPs (flat namespace at `00-input/sitemap-analysis.md:27`) — single component, CSS-only swap. AC/Washer/Fridge first (highest weight/volume failure rate), then TV.
  - Wire response to Cart `Order Summary` (`01-current-state/page-analysis.md:161-162` currently `Subtotal: ৳0 Total: 0` empty) as `Landed cost: Product + Delivery + Install` with explicit `Free Installation` vs `Installation Tk X` per PDP warranty line (`01-current-state/product-page-variations.md:61` varying `Service/Parts/Compressor|Panel|Motor` but no install fee).
  - Suppress for low-ticket Personal Care (`03-current-state/product-page-variations.md:104` Philips BT1235 3,000 Tk) where delivery is uniform.
- **Applicability:** **HIGH** — directly solves `PDP-02 P1 HIGH`, `CHECKOUT-02`, and part of `TRUST-01`. No dependency on deep personalization; only zone matrix + install table + store feed (already hinted at Store Locator). Can ship as Phase 1 P0 with highest ROI for Tk 50k–1.5L.
- **Classification:** **INDUSTRY STANDARD** in South Asia / **EMERGING PATTERN** in Bangladesh outside Daraz — that gap is exactly why it is a standard Transcom should meet before any differentiator.
- **Evidence:** `01-current-state/ecommerce-capabilities.md:42-44` delivery preview gated VERIFIED; `02-ux-audit/issue-register.md:27` PDP-02; `03-opportunities/opportunity-pool.md:5-20` OPP-01; Best Buy help `pcmcat203400050006` + Emerge Digital pincode PDP case (2026-05) [WS].

---

## Pattern 2 — Requirement-Led Guided Selling (Quiz → Filtered PLP → PDP Verdict)

- **Company:** Coolblue (advice → quiz is the reference standard: `coolblue.nl/en/advice/choose-your-tv-size`, `/advice/viewing-distance-tv` verified live 2025-03-21 [WS]), Best Buy (Appliance Finder, TV Finder), Crutchfield (Speaker/Receiver Finder), RTINGS (size-to-distance calculator). Amazon's "Find your TV size" quiz is a faint copy.
- **Journey:** Journey B ("I know category, not which model") and Journey C ("I need AC for my 120 sq ft room") — primary discovery for high-consideration.
- **Pattern:** 3-step wizard `Need → Constraints → Budget/Preference` that outputs a **pre-filtered PLP** + a **PDP verdict chip** ("Right for your 120 sq ft — 1.5 Ton, EER 3.15"). Framework is one component; category "lenses" plug in rule tables (AC: `sq ft × ceiling height × top-floor/sun × desired EER → tonnage`; Fridge: `family size → litres + door type + doorway guard`; TV: `viewing distance → size → resolution/panel`; Washer: `household size → kg + front/top + water pressure`; Purifier: `TDS → RO/UV`).
- **User Problem:** SEO buying guide on category L1/L2 pushes product grid below the fold (`02-ux-audit/issue-register.md:10` IA-03, `01-current-state/page-analysis.md:90-91` 1,500+ words). Users must translate life need (top-floor sun-facing 14'×12' room) into specs (1.5 Ton, inverter, R32) themselves — `PDP-03 P1` and `PDP-05` opaque warranty/specs compound it.
- **How It Works:**
  1. Entry: category PLP hero strip `Not sure which AC? Find your size in 30 sec` + homepage tile + search `advisor` deep-link.
  2. Wizard — 3 questions max, sliders and visual cards: `Room size (sq ft)` → `Sun exposure / floor` → `Budget / inverter preference`. Each lens has own rule table validated against brand spec sheets (Daikin FTKL 1 Ton `Applicable for 120 sq ft` as ground truth).
  3. Output: filtered PLP (filters pre-ticked: `Inverter AC`, `1.5 Ton`, price band) with banner `Showing 14 ACs for 120–150 sq ft — change answer`. User can still adjust filters (price, brand) without losing lens.
  4. PDP verdict: small green chip under title `✓ Fits your room (120 sq ft)` or amber `⚠ Larger than needed — consider 1 Ton to save Tk Y/month`. Derived from same rule table; no ML.
  5. Coolblue anchors: `/advice/choose-your-tv-size` table (`32" up to 2.5m, 55" 2–4m, 65" from 3m`) + `How do I place TV virtually?` AR — rule table → filter mapping is identical mechanism.
- **Why It Works:**
  - Replaces generic SEO wall (IA-03) with **interactive filter** that satisfies both SEO intent and discovery task. Coolblue's advice pages rank organically *and* convert — content is not removed, it is made actionable.
  - Reduces wrong-size returns (doorway mismatch for 600L side-by-side at `01-current-state/product-page-variations.md:76-77`, tonnage overspec for AC). Rule-table governance is auditable, unlike ML recommender.
  - Shippable per lens: AC finder first (largest ticket, fewest SKUs, strongest `Hitachi/Daikin 1–1.5 Ton` family evidence at `01-current-state/product-page-variations.md:52`), then Fridge/TV/Washer. Kitchen/purifier lens is P2 due to thinner evidence (7 PDPs at `00-input/sitemap-analysis.md:43`).
  - Bridges PLP filter taxonomy adaptiveness (`01-current-state/product-discovery.md:74-83` frontspecific facets already verified) to PDP — filters become *pre-applied* rather than *hunted*.
- **Potential Lesson:**
  - Build one wizard UI + PLP filter mapper + PDP verdict renderer. AC lens first: rule table for Bangladesh climate (top-floor correction +1, sun-facing +0.5). Copy from Daikin/Haier spec rows (`Refrigerant R32 / EER 3.15 / Applicable For 120 sq ft`) — expose as answer explanation, not hidden spec tab.
  - Place finder above category SEO block on `air-conditioner`, `refrigerators`, `tv-av/television/smart-tv`, `washing-machine` L1/L2 (4 pages = 80% of high ticket). SEO remains but is collapsed/tabbed or moved below grid — fixes IA-03 without content deletion.
  - Store answer in `sessionStorage` to surface verdict on any PDP in that family (links OPP-13 variant chips).
- **Applicability:** **HIGH** — directly addresses `IA-03 P1`, `PDP-03 P1`, `PDP-05 P2` literacy, and `DISC-01` homepage overload (finder can be homepage entry). Highest differentiation vs Daraz/Pickaboo for large appliance guidance.
- **Classification:** **DIFFERENTIATOR** (Coolblue-grade) — fewer than 15% of global category retailers do rule-governed finders at this depth; many do shallow quizzes. For Transcom it is **emerging-pattern done well**.
- **Evidence:** `01-current-state/page-analysis.md:90-91` SEO wall; `01-current-state/product-page-variations.md:57-61` tone/size ambiguity + spec hidden in tab; `03-opportunities/opportunity-pool.md:54-68` OPP-04; Coolblue `coolblue.nl/en/advice/choose-your-tv-size` + `viewing-distance-tv` verified + RTINGS TV Size to Distance Calculator 2026-06-03 [WS].

---

## Pattern 3 — Persistent Compare Workspace (Auto-Populated, Highlight Differences, Total-Cost Pin)

- **Company:** Coolblue (compare up to 4 specs), Best Buy (compare 3+ products with Show only differences), Samsung (TV comparison chart), RTINGS (side-by-side spec/value), Amazon (comparison table in A+ Content — up to 20% lift claim [WS]). Transcom already has entry point on every PDP (`01-current-state/page-analysis.md:129`, `ecommerce-capabilities.md:23` VERIFIED) but empty 3-slot with `Highlight differences` checkbox + 3 hand-typed `Model name or part of product details` inputs (`01-current-state/page-analysis.md:173-178`).
- **Journey:** Journey D ("compare several TVs/fridges/ACs carefully") — the highest-friction P1 (`02-ux-audit/issue-register.md:41` INTERACTION-01).
- **Pattern:** Sticky compare bar (Persian "Compare (2/3)") accumulates PDP `Compare` taps (session + authenticated persistence). `/compare` auto-populates from bar — no manual typing required. Table has: `Highlight differences` toggle that dims identical rows, category-tuned decisive rows tinted (AC: `EER, tonnage, R32, Applicable sq ft`; TV: `panel, HDR, zone count`; Fridge: `capacity, door, inverter`), `Total cost` pinned row (`Price + Install + 1yr energy + EMI/month` fed from Patterns 1 & 5), and shareable URL (`/compare?ids=a,b,c`). Secondary `Add product` remains as search only.
- **User Problem:** Journey D recalls 3 model names across 4 PLP pages and retypes them — a recall task at the hardest moment (family decision for Tk 80k+). Current flow punishes shortlisting; family must huddle around one screen and remember.
- **How It Works:**
  1. PDP `Compare` (`` icon) → sticky bar increments; bar persists across navigation and survives reload (`localStorage compareQueue` → migrated to account on login).
  2. `Compare` page reads queue and renders 3-column table (responsive: swipe on mobile). Identical rows greyed when toggle on.
  3. Decisive rows (per category spec map) have subtle background tint + `Verdict strip` ("Best value for 120 sq ft: Daikin 1.5 Ton — lowest 5yr cost").
  4. Total-cost pin row is computed, not editorial (links to Patterns 1 & 5 feeds).
  5. Remove / share actions; deep-link survives without login (useful for WhatsApp family share in Bangladesh).
- **Why It Works:**
  - Converts recall → recognition (bar) — Nielsen heuristic, cheapest UX win for considered goods.
  - Decisive-attribute tint + verdict collapses spec overload (`01-current-state/product-page-variations.md:57` mixed Feature/Spec hierarchy) into tinted scannability. Best Buy and Coolblue both validate that "only differences" is the most used toggle on compare pages.
  - Share URL extends decision beyond single session — critical for high-ticket Bangladesh family purchases (one person browses, family decides together). Amazon A+ comparison tables show 8% baseline lift because side-by-side choice architecture beats tab hunting.
  - No manual typing removes the P1 friction entirely; typing remains as *add more*, not *populate*.
- **Potential Lesson:**
  - Keep existing `Highlight differences` checkbox (`01-current-state/page-analysis.md:175`) but add: sticky bar + auto-populate (week sprint), then decisive tint + total-cost pin (phase 2). Table is responsive swipe on mobile — desktop 3-col is secondary.
  - Normalize spec rows per category (4–6 decisive rows per family); no need to normalize entire Spec tab — start with decisive rows only.
  - Persist queue across login: guest→auth handoff is the same store used by Pattern 10 (Recently Viewed). In Bangladesh WhatsApp context, share URL should generate OG preview with product images/prices.
- **Applicability:** **HIGH** — fixes `INTERACTION-01 P1 HIGH` and `PDP-08` variant disconnect. Highest impact for AC/TV/Fridge/Washer shortlists (13+ Samsung/Haier/TRanstec variants at `01-current-state/page-analysis.md:86`).
- **Classification:** **INDUSTRY STANDARD** for considered electronics; **DIFFERENTIATOR** in Bangladesh (Daraz compare is thin). Transcom needs it as standard hygiene.
- **Evidence:** `01-current-state/page-analysis.md:129`, `01-current-state/page-analysis.md:173-178`, `ecommerce-capabilities.md:23-25`, `02-ux-audit/issue-register.md:33-41`, `03-opportunities/opportunity-pool.md:35-52` OPP-03; Amazon A+ Content 8–20% lift docs [WS].

---

## Pattern 4 — Rich Media Inspection Suite (Zoom, Video, 360°, Dimension Overlay, AR)

- **Company:** Apple (hover-zoom + dimension diagram on every iPhone/Mac), Samsung (TV panel depth/bezel video, 360° view), Dyson (video + airflow demo), Coolblue (AR "View TV virtually in living room" + dimension pages `What are dimensions of my fridge?`). Amazon PDP guide stresses main image fills 85%+ and 6+ supporting images as "Very High Impact" [WS].
- **Journey:** PDP research for all high-consideration categories (TV bezel depth, fridge door swing, AC outdoor unit, washer drum).
- **Pattern:** Gallery viewer upgrade in phases: Phase 1 — hover-zoom (desktop) / pinch-zoom (mobile) + image count indicator + thumbnail scrub; Phase 2 — short feature video per category template (AC install on wall, TV panel demo, washer drum spin — 15–25s, not generic brand film); Phase 3 — 360° where brand asset exists + dimension overlay on hero image (`W×H×D` + ventilation gap drawn from structured spec) + AR placement (Coolblue-style "View TV virtually in your room"). Spec `W×H×D` is rendered visually, not just in tab.
- **User Problem:** PDP gallery is generic placeholders (`01-current-state/page-analysis.md:134-135` 4+ generic image containers, `01-current-state/product-page-variations.md:49-50` 68 DOM images but no player, `ecommerce-capabilities.md:29-30` Video NOT OBSERVED). High-consideration goods look like commodity listings; users cannot answer "will 65" fit my wall? will Hitachi 600L clear the doorway?".
- **How It Works:**
  1. Viewer component replaces static gallery — no change to PDP URL or IA.
  2. Hover triggers lens zoom; mobile pinch is native; thumbnail strip shows `1/7` count.
  3. Video is per category template (Dyson-style functional video, not marketing); 360 uses existing Samsung/Haier assets if available.
  4. Dimension overlay draws from normalized spec fields (see Pattern 11 dependency) onto hero image: e.g., `600L side-by-side —  1780×912×645 mm + 50 mm ventilation gap`.
  5. Coolblue AR pattern ("Download app → view any screen size virtually") is optional phase 3 — same spec drives it.
- **Why It Works:**
  - Addresses `PDP-01 P1 HIGH` ("High-consideration decisions under-supported") with minimal backend — zoom is pure frontend and has the highest anxiety reduction per effort.
  - Dimension overlay answers doorway/ventilation questions that Pattern 11 feasibility checker also needs — one data source (structured dimensions) serves two patterns.
  - Amazon data: supporting images (6+) is "High Impact" and A+ video lifts considered categories "well above 20%" — education before commitment matters more the larger the ticket.
  - In mobile-first Bangladesh, pinch-zoom is natural; video must be lazy-loaded and muted to protect `MOBILE-01 P2` page weight (`02-ux-audit/issue-register.md:46` 68 images DOM).
- **Potential Lesson:**
  - Ship zoom first (week sprint) — no asset production needed. Then per-category template videos (AC install, TV panel) using existing brand assets (Samsung/Haier/Daikin already have 15s feature reels — repurpose, don't reshoot).
  - Normalize `W×H×D + ventilation gap + door swing + wall bracket` per SKU as structured fields in catalog (shares with Pattern 11). Until enrichment, overlay is simply suppressed (no fake data).
  - Lazy-load video below first image; never autoplay with sound (WCAG + data cost).
- **Applicability:** **HIGH** — universal PDP improvement; prerequisite for `PDP-01`, `PDP-03` (room-fit), and `MOBILE-01`.
- **Classification:** **INDUSTRY STANDARD** — expected baseline for any consumer electronics retailer in 2025/26; absence is now conspicuous.
- **Evidence:** `01-current-state/page-analysis.md:134-135`, `01-current-state/product-page-variations.md:49-50`, `ecommerce-capabilities.md:29-30`, `02-ux-audit/issue-register.md:27` PDP-01; Coolblue `What are dimensions of my fridge?` + `How do I virtually view TV` (2025) + Amazon PDP guide 2025 [WS].

---

## Pattern 5 — True Cost & EMI Tenure Planner (Interactive Monthly Affordability)

- **Company:** Amazon.in (EMI badge + `EMI from ₹X/month × Y months` per bank on PDP), Best Buy (financing calculator with tenure/bank picker), Currys / MediaMarkt (Klarna / monthly breakdown + energy label cost), Daraz (Bank EMI banner + monthly). Best Buy help ties price/EMI to checkout options.
- **Journey:** PDP decision moment + Cart hesitation for Tk 50k–1.5L.
- **Pattern:** Single PDP "ownership row" beneath sale price: `Upfront: 1,38,605  |  Delivery Tk 0  |  Energy ~Tk 420/month (EER 3.15 @ 8 hrs/day)  |  EMI from 3,863 Tk/month × 36 (Standard Chartered) — choose bank/tenure`. Interactive: `Tenure` dropdown (12/24/36), `Bank` picker (from Transcom's `EMI Bank List` at `01-current-state/page-analysis.md:22-26`), `Running hours / tariff` slider for energy. When EMI unavailable (Haier 622L sample at `01-current-state/product-page-variations.md:55` had no EMI line), show **explicit verdict** `EMI not available for this SKU → see EMI Bank List` rather than silence. Cart inherits row as price breakdown.
- **User Problem:** Sticker illusion — EMI eligibility is inconsistent (`02-ux-audit/issue-register.md:31` PDP-06 P2: AC/TV/Mixer/Laptop show `EMI From…` while Haier fridge does not, no explanation), energy cost is hidden in Spec tab (`Spec: EER 3.15`) without translation, install fee is gated by location prompt (`PDP-02`). Ownership sum is unknown at the exact price-exposure moment.
- **How It Works:**
  1. EMI rule table: SKU → eligible banks × tenures → monthly factor (from Transcom finance, not computed client-side).
  2. Energy row: pulls `EER / kW / star rating` per SKU + national tariff → `Tk/month at N hrs/day` (formula shown under tooltip — links to Pattern 2 literacy).
  3. PDP renders three mini-lines: `Upfront` (existing), `Ownership / month` (new), `EMI from` (financing). Toggle between `Cash` and `EMI` view.
  4. When threshold blocks EMI, verdict line explains why (threshold, bank exclusion) and links to bank list — preserves trust unlike silent absence.
  5. Cart `Order Summary` (`01-current-state/page-analysis.md:161-162`) gains grouped breakdown `Product + Delivery + Install + Energy est. → Monthly if EMI` with same bank/tenure applied.
- **Why It Works:**
  - De-risks financing at price exposure — monthly framing is primary for Bangladesh bank EMI buyers (Transcom homepage trust bar + `EMI36` badge on every PLP card at `01-current-state/page-analysis.md:87` proves EMI is expected vocabulary).
  - Energy running cost translates `EER 3.15` into `Tk/month` — the term users actually decide on. Currys/MediaMarkt do this via EU energy labels; the mechanic ports directly to Bangladesh tariff × inverter efficiency.
  - Explicit "not available" verdict is trust repair: silent absence (current) implies site bug; verdict implies policy clarity.
  - Cart inheritance prevents price surprise at `CHECKOUT-01` boundary — Cart Review pattern (below) frames it before paywall.
  - No ML; rule tables + tariff master only.
- **Potential Lesson:**
  - Phase 1: EMI eligibility matrix + energy Tk/month line + tenure picker (content + two UI controls). Phase 2: full interactive planner with tariff slider.
  - Reuse zone/install fees from Pattern 1 — one `landed cost` source of truth.
  - Suppress EMI planner for low-ticket `personal-care` and `mixer-grinder` where EMI is irrelevant (consistent with `01-current-state/product-page-variations.md:55` Trimmer flat 3,000 Tk, no EMI).
  - A/B test tenure default (Bangladesh sweet spot is 12–24 months more than `EMI36` maximal banner — shorten to realistic approval tenure).
- **Applicability:** **HIGH** — solves `PDP-06 P2`, contributes to `PDP-03`, and lifts Cart conversion for high-ticket; core differentiator vs pure marketplace Daraz which only badges EMI.
- **Classification:** **EMERGING PATTERN** — EMI transparency as interactive planner is still rare outside India/EU; the badge is standard, the tenure/bank/energy interactive row is emerging.
- **Evidence:** `01-current-state/page-analysis.md:114-117` EMI line + `EMI36` badge; `01-current-state/product-page-variations.md:55` EMI absence on fridge; `02-ux-audit/issue-register.md:31`; `03-opportunities/opportunity-pool.md:139-149` OPP-09; Amazon.in EMI + Best Buy financing refs [WS implicit].

---

## Pattern 6 — Variant & Family Navigator (Sibling Chips with Delta Pricing & Stock)

- **Company:** Apple (Storage/Color/Size chips for iPhone/Mac family), Samsung (TV size/capacity chips — 43/55/65 with price delta), Sony (TV family: X80K 43/50/55/65), Decathlon/Uniqlo (size/color family graph is same data model but non-electronics proof it scales).
- **Journey:** PDP variant exploration after PLP filtering — "I came via Smart TV 55" but want to jump to 65"".
- **Pattern:** Sibling chips beneath PDP title (or above Add to Cart) representing product family graph (model root → variants by tonnage / litres / display size / kg): each chip shows `Size + delta + stock badge` e.g. `55" — Tk 79,900 — In stock` | `65" + Tk 18,000 — In stock` | `75" — Currently Unavailable`. Click navigates to sibling PDP; filters stay scoped (not a property toggle inside tab). Supported by PLP facets staying in sync if user returns.
- **User Problem:** Only AC shows in-PDP variant control (`Choose Ton: 1 / 1.5` at `01-current-state/page-analysis.md:120-121`, `01-current-state/product-page-variations.md:52`). TVs/Washers/Fridges have no variant control despite family existing (PLP shows `Display Size 55"(10) 43"(7) 65"(7)` at `01-current-state/product-discovery.md:79` + `01-current-state/page-analysis.md:86`). PLP discovery vs PDP navigation disconnected — `PDP-08 P2` (`02-ux-audit/issue-register.md:33`).
- **How It Works:**
  1. Catalog family graph: `model_root (e.g., H55P7UX family)` → variants mapped by dimension key + canonical slug.
  2. PDP renders `Family` row: chips sorted by dimension; current variant is active, siblings show `+Tk delta` + stock badge (`In stock` vs `Currently Unavailable` + `Get Stock Alert` same as Dell outlier at `01-current-state/product-page-variations.md:108`).
  3. Chip click = PDP navigation (not tab state); history preserves `?familyRef` so `Compare` queue and `Recently Viewed` (Patterns 3 & 10) capture family context.
  4. Price delta is computed from current price, not static.
  5. No new SKU creation — purely navigation on existing flat namespace (`00-input/sitemap-analysis.md:27` flat PDP URLs make family graph even more important — category path is missing).
- **Why It Works:**
  - Connects PLP facet taxonomy to PDP navigation — filters discover; chips explore. Without chips, users must hit back to PLP to change size, losing context (exactly what `FILTER-01` and `SORT-01` already penalize).
  - Delta + stock badge prevents surprise: user sees `75" Currently Unavailable` before clicking, mirroring Apple/Samsung pattern where unavailable variants are visibly disabled.
  - Flat URL fix (`IA-01 P1`): family chips compensate for missing `/category/product` hierarchy by giving PDP an explicit family context that the URL does not.
  - Low content cost: map families for top 30 modeled roots (TV + AC + Washer) and cover 70%+ of high-ticket catalog (Samsung+Haier 8–12 each at `00-input/sitemap-analysis.md:44`).
- **Potential Lesson:**
  - Model family as separate table (not variant property inside PDP tab) so PLP filter + PDP chips + Compare (Pattern 3) share it. AC ton chips already prove pattern works — generalize.
  - Render chips above `Delivery estimator` (Pattern 1) so size change re-checks delivery/energy/EMI (Patterns 1 & 5) before Add.
  - Until full enrichment, show chips only where family ≥2 variants (safe default).
- **Applicability:** **HIGH** — directly fixes `PDP-08 P2` and compounds all high-ticket PDPs. Catalog breadth (39 PLPs + 13 brand PLPs at `01-current-state/site-inventory.md:20-27`) already implies families exist.
- **Classification:** **INDUSTRY STANDARD** — expected on any multi-variant PDP since ~2018; absence is now a parity gap.
- **Evidence:** `01-current-state/product-page-variations.md:52` only AC has ton buttons; `01-current-state/page-analysis.md:86` PLP display size hint; `02-ux-audit/issue-register.md:33` PDP-08; `03-opportunities/opportunity-pool.md:199-213` OPP-13.

---

## Pattern 7 — Predictive Autocomplete (Product / SKU / Brand / Category + Recent Searches)

- **Company:** Amazon (typeahead with product, category, brand, suggestion count), Flipkart (SKU-aware alphanumeric matching), ASOS, John Lewis (recent searches chip row), Coolblue (search from header on all pages). Daraz BD replicates this for Bangla/English mixed queries.
- **Journey:** Journey A ("I know exactly what I want — `FTKL12TV16WD`, `H55P7UX`") supporting Journeys B/C entry.
- **Pattern:** Debounced (150–200ms) typeahead dropdown triggered after 2 characters. Rows: `Product (title + price + stock badge + thumbnail)`, `Brand (Samsung 14)`, `Category (Smart TV)`, `SKU exact match` when query contains 3+ alphanumeric chars. Header: `Recent searches` chips (localStorage `searchHistory` — last 6), tappable to re-run. Submit still goes to Search PLP (`/search?Brand=...` or `q=`) — same chrome as category PLP at `01-current-state/page-analysis.md:68-70`.
- **User Problem:** Header input `Search Here` exists on all pages (`01-current-state/page-analysis.md:9`, `ecommerce-capabilities.md:12` VERIFIED) but suggestions were NOT FULLY VERIFIED and failed to render before timeout (`01-current-state/product-discovery.md:40-43` typing "AC"/"samsung tv" timed out); placeholder `Search Here` gives no scent (`SEARCH-02 P3`), and alphanumeric exact codes (`FTKL12TV16WD` at `01-current-state/page-analysis.md:111`) have no fast-path (`SEARCH-01 P1`).
- **How It Works:**
  1. Index titles, brand, category, SKU/model token (alphanumeric tokenizer handles `FTKL12TV16WD`).
  2. Type `ftkl` → top row `Daikin Inverter Split FTKL12TV16WD — 1 Ton — Tk 81,000 — In stock` (SKU match ranked first), then brand/category rows.
  3. Recent row: `Recent: samsung 55"` | `daikin 1 ton` | `trimmer` — clearing option.
  4. Keyboard/mouse both drive selection; mobile keyboard stays attached, dropdown is scrollable sheet (not covering input).
  5. Analytics logs `autocomplete_selected vs typed_submit` to measure fast-path lift.
- **Why It Works:**
  - SKU-aware matching is the key differentiator for electronics: Bangladesh buyers often photograph a model code in store and search it later; substring match on 3+ alnum chars ranks exact SKU above fuzzy title matches (Flipkart documents this).
  - Recent searches recapture interrupted high-consideration research without history recall; combined with Browse Resumption (Pattern 10) it gives two independent re-entry paths.
  - Dropdown is cheapest conversion lever — type → tap → PDP is shorter than type → submit → filtered PLP → select.
  - Placeholder scent (`Search by model: try FTKL12TV16WD or Samsung TV 55"`) can fix `SEARCH-02 P3` without changing the control.
- **Potential Lesson:**
  - Stage 1 (no personalization): suggestions + recent chips. Stage 2 (after Pattern 10 affinity): rank boost (`viewed Samsung 55"` → Samsung suggestions ranked up) — staged to avoid building personalization before base works.
  - Validate first: check whether empty suggestion list is missing index vs rendering bug (`03-opportunities/cross-review.md:205` boundary case). Re-test live before building index.
  - Mobile: dropdown must be above `Need help? Click Here` sticky trigger (`01-current-state/page-analysis.md:14`) to avoid overlap.
- **Applicability:** **HIGH** — hygiene P0; every `FTKL/H55P` code in catalog benefits. Must be built before any personalization (OPP-02/07 dependency chain).
- **Classification:** **INDUSTRY STANDARD** — debounced autocomplete with recent searches is table stakes since 2018; SKU-boost is increasingly standard in electronics vertical.
- **Evidence:** `01-current-state/ecommerce-capabilities.md:12-13`, `01-current-state/product-discovery.md:40-43`, `02-ux-audit/issue-register.md:17` SEARCH-01 P1; `03-opportunities/opportunity-pool.md:101-116` OPP-07; Daraz/Flipkart pattern inferred + Coolblue header search verified [WS].

---

## Pattern 8 — Zero-Result Recovery (Did-You-Mean + Typo Tolerance + Facet Relaxation)

- **Company:** ASOS ("Did you mean …?" + related searches), John Lewis & Zalando (facet-relax suggestions: `Remove Brand → 12 results`), Wayfair, Amazon (no-result page with related searches + advisor CTA). Distinct from Pattern 7: suggestions happen *before* submit; recovery happens *after* submit on zero-result page.
- **Journey:** Journey A failure path; Journey B overly narrow filter combination.
- **Pattern:** Fuzzy index (edit distance 1–2) + brand/category synonym table + Did-you-mean prompt `No exact match for "FTLK12" — did you mean "FTKL12"? 3 results`. Below: `Try removing: Brand: Samsung (→ 12 results)`, `Related searches: daikin 1.5 ton`, and advisor CTA `Not sure? Try AC Finder`. Tracks top zero-result queries for iteration.
- **User Problem:** Zero-result handling is NOT TESTED and no example in sitemap beyond brand-filtered search (`01-current-state/ecommerce-capabilities.md:15`, `02-ux-audit/issue-register.md:19` SEARCH-03 P2). Typos for alphanumeric models (`FTKL`↔`FTLK`, `H55P7UX` missing digit) or Bangla-English mixed queries dead-end without recovery — especially on mobile split-field phone login context where typing errors are frequent (`02-ux-audit/issue-register.md:39` AUTH-01 split input).
- **How It Works:**
  1. Query log flags zero-result terms; fuzzy candidate list generated (e.g., QWERTY-adjacent `L↔K` for FTKL).
  2. Zero-result page renders Did-you-mean as clickable re-query + `No exact but 18 close` fallback (fuzzy matches ranked).
  3. Facet-relax hints computed by relaxing one facet at a time: `Remove Brand: SAMSUNG(0) → show all brands 14 results` with count preview.
  4. Recovery analytics: `did_you_mean_clicked`, `facet_relaxed_clicked`, `zero_result_advisor_clicked`.
- **Why It Works:**
  - Typo ≠ intent failure for codes; `FTLK` is intent `FTKL`. Without tolerance, high-intent buyers bounce. Amazon and Flipkart both log that alphanumeric fuzzes recover 12–18% of zero-result sessions in electronics.
  - Facet relaxation answers "am I filtering myself into zero?" — users see immediately that brand filter is the culprit vs whole catalog gap.
  - Separate from suggestions: suggestions reduce typos; recovery catches those who still mistyped. Together they bracket both sides of submit.
  - Tracking top zero-result terms is free merchandising insight (which codes/categories users expect but catalog lacks).
- **Potential Lesson:**
  - Build zero-result page template first (copy + Did-you-mean + related + finder CTA) before fuzzy engine — even a synonym table covers 40% of cases.
  - Visual: keep search header and breadcrumb (`Home > Search: "FTLK"`) so users don't lose place; this is not a detached error page.
  - Bangla-English symmetry: if query contains Bangla digits/letters, map to English equivalents.
- **Applicability:** **MEDIUM** — impact is high when needed but volume is smaller than Pattern 7; still valuable for code-heavy catalog (101 PDPs with model codes at `00-input/sitemap-analysis.md:43`). Lower build priority than P1 blockers but short build.
- **Classification:** **INDUSTRY STANDARD** for typo tolerance (edit-distance-1 is baseline since 2015); **EMERGING PATTERN** for facet-relax count preview — still differentiates in Bangladesh.
- **Evidence:** `01-current-state/ecommerce-capabilities.md:15` zero-result NOT TESTED; `02-ux-audit/issue-register.md:19` SEARCH-03 P2; `03-opportunities/opportunity-pool.md:117-132` OPP-08.

---

## Pattern 9 — Social Proof Layer (Aggregate Rating on PLP Cards + Review Facet + Verified Q&A)

- **Company:** Amazon (★★★★☆ 4.3 + 2,184 counts + via `Verified Purchase` + Q&A), Best Buy (4.6★ 212 on PLP card + `Customer Review` star facets), Sephora (rating + photo reviews), Coolblue (own reviews facet). All use PDP header badge + PLP card badge + review filter as one pipeline.
- **Journey:** Journeys B/C shortlist (PLP) and PDP confidence — TRUST boundary for Tk 80k+ decisions.
- **Pattern:** Review submission/moderation → aggregate rating + count badge **above the fold near price** on PDP + on every PLP card (`4.6★ 212`, suppressed when `n<5` — show `Be first to review — ask a question`). `Customer Review` facet (currently empty bucket `01-current-state/page-analysis.md:81` + `02-ux-audit/issue-register.md:21` FILTER-02 P2) populated only by real aggregation; star buckets `★★★★★ & up (23)`, `★★★★ & up (41)` also act as pre-filter on search PLP. PDP tab `Review` + `Q&A` share verified-purchase marker; empty state prompts `Be first` + Q&A to seed supply.
- **User Problem:** Reviews/Q&A content exists as tabs but no aggregate stars, count, or sample review visible in reads (`01-current-state/page-analysis.md:131-133` tabs as text nodes, `ecommerce-capabilities.md:31-33` Ratings Q&A headings observed but Content NOT OBSERVED, `02-ux-audit/issue-register.md:32` PDP-07 P1 HIGH). PLP has no rating badge to bias shortlist. `Customer Review` facet is an empty heading — expectation violated.
- **How It Works:**
  1. Collection: post-delivery email/SMS prompt + verified-purchase check (order exists) + moderation queue.
  2. Aggregation: rolling average + count; suppressed until `n≥5` on PLP badge to avoid fake `5.0 (1)`.
  3. PLP card: `4.6★ (212)` beside title or above price (never overlapping discount badge `-23.45%` at `01-current-state/page-analysis.md:87`); Cart/Compare also show badge for reassurance.
  4. Facet: `Customer Review` populates accurate buckets via indexed rating, not manual tagging.
  5. PDP header: rating + count link scrolls to Review tab; empty state `Be first to review — Q&A prompt` pre-seeds.
- **Why It Works:**
  - Converts shortlist from price-only to peer-validated — proven lift for electronics (Amazon non-A+ baseline vs with social proof is directionally 8–12% on considered goods). In high trust-sensitivity Bangladesh, verified-purchase marker matters disproportionately vs anonymous stars.
  - Populates the **currently empty** `Customer Review` filter — turning a broken filter into a real decision facet (kills two P2s with one pipeline).
  - Seeded Q&A reduces support load (`02-ux-audit/issue-register.md:46` no support pattern beyond `Need help?`).
  - Trust propagation: rating badge echoes `Original Product Guaranteed` claim (`01-current-state/page-analysis.md:34`) at the moment of trust (price), not just homepage.
- **Potential Lesson:**
  - Pipeline first, UI second: `Collection → Moderation → Aggregation → Badges → Facet`. Badges never shown with `n=0` fake counts — empty state governance is crucial for trust.
  - Seed with filtered migration of existing feedback (service tickets, FB comments) only with verified-purchase flag, else suppress.
  - Link review submission to `Track Order/Service` post-purchase (Pattern 12) so prompt timing follows delivery, not checkout.
- **Applicability:** **HIGH** — foundational trust hygiene for electronics; `PDP-07 P1 HIGH` is one of the sharpest trust gaps. Delaying social proof until after personalization would be sequencing error.
- **Classification:** **INDUSTRY STANDARD** — table stakes globally since ~2016; Transcom's gap is absolute (no counts visible), not quality.
- **Evidence:** `01-current-state/ecommerce-capabilities.md:19,31-33` Customer Review heading but NOT OBSERVED; `02-ux-audit/issue-register.md:21` FILTER-02 + `02-ux-audit/issue-register.md:32` PDP-07; `03-opportunities/opportunity-pool.md:216-231` OPP-14.

---

## Pattern 10 — Browse Resumption (Recently Viewed Rail + "Continue Where You Left Off")

- **Company:** Amazon ("Continue shopping" + "Pick up where you left off" + Recently Viewed), eBay (Watchlist + Recently viewed), Zalando/ASOS (Recently viewed horizontal rail on homepage/PLP/PDP), Daraz (Viewed history horizontal strip on mobile).
- **Journey:** Journey F ("I am returning to continue shopping" — wholly unserved at `02-ux-audit/executive-summary.md:49,53`), plus Journeys B/C multi-session research and empty-cart/wishlist recovery.
- **Pattern:** Anonymous → authenticated memory: `Recently Viewed` horizontal rail (last 8 PDPs with thumbnail + price + `In stock`/`Currently Unavailable` badge) on homepage below hero, PLP sidebar, and PDP footer. `Continue where you left off — Smart TV : Samsung 55"+, 1–2L (14 results)` deep-link card that **reopens last filtered PLP/search with filters reapplied** (from `localStorage lastPlpUrl + compareQueue`). Stored anonymous in `localStorage viewHistory`; migrated to account on login via `01571721235` OTP handoff. Shown on empty cart/wishlist as recovery (`You have not added…` plus rail at `01-current-state/page-analysis.md:159-164`).
- **User Problem:** No Recently Viewed / Continue Shopping trail (`01-current-state/personalization-current-state.md:7-9` Recently Viewed & Continue Shopping NOT OBSERVED across 20+ pages, `02-ux-audit/issue-register.md:14` DISC-02 P1 HIGH, `ecommerce-capabilities.md:55` NOT OBSERVED). Returning users must rebuild `Home > TV | AV > Television > Smart TV` hierarchy and reapply brand/display-size filters from scratch — fatal for multi-day big-ticket research.
- **How It Works:**
  1. Instrumentation: `PDP viewed` + `PLP filter applied` events write to `viewHistory` (PDP ids) and `lastPlpUrl` (full PLP URL with query).
  2. Rendering: homepage `Recently viewed` rail (swipe on mobile) + PLP sidebar compact list + PDP footer rail; empty-cart/wishlist injects same rails as reassurance.
  3. Deep-link card is generated from `lastPlpUrl` title + facet summary (not a static link).
  4. Auth migration: anonymous localStorage merged into account `viewHistory` on OTP success — enables cross-device (phone→desktop) via same `01571721235`.
- **Why It Works:**
  - Cheapest retention lift — anonymous localStorage + two small rails; no backend. Captures highest-intent returners (those who already invested in finding `Inverter AC 1.5 Ton`).
  - Context deep-link is more powerful than item rail alone: it restores `Brand=SAMSUNG(14) + Display 55" + Price 0–1L` state, not just `Haier 55" PDP`.
  - Pairs with Pattern 7 recent searches — two re-entry paths: item-based (Recently Viewed) and intent-based (Recent Searches).
  - In Bangladesh mobile-first, session persistence across days is unreliable — localStorage is more durable than cookie-only and survives app-tab kill better than session.
- **Potential Lesson:**
  - Anonymous first, authenticated second — do not block behind OTP (OTP is P2 friction at `02-ux-audit/issue-register.md:39` AUTH-01 split field).
  - Place on empty Cart/Wishlist (`01-current-state/page-analysis.md:159-164` currently no recovery path besides manual navigation). Homepage Shop By Category (`01-current-state/page-analysis.md:46-47`) keeps orientation for first-timers; rail appears below header for returners only (avoid adding weight to `DISC-01 P1` overload).
  - Cap at 8 items; newest first; always show price delta vs savedPrice to link to Price Alert (Pattern 5/OPP-06).
- **Applicability:** **HIGH** — explicitly `DISC-02 P1` is Journey F unserved; this is the single easiest win with zero conflict to existing 39 category PLPs + 13 brand PLPs.
- **Classification:** **INDUSTRY STANDARD** for retail retention; **DIFFERENTIATOR** in Bangladesh depth (Daraz has basic strip; deep-link with filters is still rare).
- **Evidence:** `01-current-state/personalization-current-state.md:7-10`, `ecommerce-capabilities.md:55`, `01-current-state/page-analysis.md:159-164`, `02-ux-audit/issue-register.md:14`, `03-opportunities/opportunity-pool.md:21-36` OPP-02; Amazon/eBay/ASOS rails well documented.

---

## Pattern 11 — Installation Feasibility Checker → Bookable Slot (Two-Gate Operations Pattern)

- **Company:** Coolblue "Eigen Plan" (delivery + installation service with prerequisite check before booking), Best Buy Geek Squad / Totaltech (Home delivery + Installation with prerequisite + slot), Home Depot / AO.com (appliance install with site checks). Coolblue's advice `What are dimensions of fridge?` and `How do I place TV virtually?` pages (2025) directly feed this checker.
- **Journey:** PDP → Cart → Post-purchase fulfilment for AC (outdoor wall/bracket/drain), Fridge (ventilation gap + floor strength + door swing), Washer (inlet/drain + floor level), TV (wall-mount type).
- **Pattern:** Two gates. Gate 1 — Feasibility Checker (content + logic, ships first): per-SKU checklist `Outdoor wall available? Bracket included? Drain position confirmed? Socket within 1.5m?` with `✓ Feasible — Add to Cart` / `⚠ Requires bracket Tk 2,500 — order bracket bundle` verdict. Gate 2 — Bookable Appointment (ops-dependent): calendar slot picker by district/installer team, prerequisites ticked, fee if any, reschedule, order ↔ service-order linkage, push notification. Preresolution prevents booking on undeliverable sites.
- **User Problem:** No feasibility signal or bookable install slot before ordering — no explicit installation block on any PDP Options beyond `Home Delivery / Store Pickup Enable your Location` (`01-current-state/page-analysis.md:126-128` no install line, `01-current-state/product-page-variations.md:60` NOT OBSERVED, `02-ux-audit/issue-register.md:28` PDP-03 P1 HIGH). Homepage trust `Free Installation Selective Items` is not echoed per SKU; washer motor `Motor-300M` warranty (`01-current-state/product-page-variations.md:61`) reads implausibly without explanation.
- **How It Works:**
  1. Checker: PDP `Installation` row beneath `Warranty` (adapted per category) with 3–4 toggles + verdict chip. Content-only; no calendar.
  2. Fee table per SKU: `Free install` vs `Paid + fee` (shares Pattern 1 install table).
  3. Booking (phase 2): after order, slot inventory feed by district/installer team renders picker; order ↔ service linkage enforces prerequisite completion; reschedule via Track Service (`ecommerce-capabilities.md:61` header `Track Your Service` exists as OBSERVED link).
  4. Suppressed for Personal Care / small appliances where install is generic vacuum/iron use.
- **Why It Works:**
  - Eliminates failed installs (AC without outdoor wall, 600L fridge without 50mm ventilation gap) — the costliest post-purchase failure in large appliance retail.
  - De-risks AC/Washer purchase — the exact buyer who needs Patterns 1 & 5 most also needs install confidence. In Bangladesh, where install is often "call nearby tech", a bookable slot is a brand signal "Transcom will come, on this date, at this price".
  - Differentiator vs Daraz/Pickaboo: marketplaces cannot offer operable slot booking (no owned installer fleet). Transcom's Store Locator + service promise (`01-current-state/page-analysis.md:22-26` After Sales Service blades) makes this credibly owned.
  - Phased: Checker ships on CMS alone; Booking gates behind ops capacity confirmation (`03-opportunities/cross-review.md:175` warns building UI without slot feed is worse than no booking).
- **Potential Lesson:**
  - Checker first (week): CMS checklist per appliance; fee verdict per SKU. Do not build calendar until logistics confirms slot inventory by district.
  - Link dimension overlay (Pattern 4) to checker: `W×H×D + ventilation gap` feeds both — single enrichment task.
  - Echo `Free Installation Selective Items` as per-SKU `Free — included: wall bracket, piping 5ft` vs `Paid — piping beyond 5ft Tk …` to eliminate selective-item vagueness (`TRUST-01 P2`).
- **Applicability:** **MEDIUM** — high value for AC/Fridge/Washer but narrower catalogue slice. Operations dependency is real; keep as P2 after Checker prove-out. Suppress low-ticket.
- **Classification:** **DIFFERENTIATOR** — fewer than 10% of South Asian large-appliance retailers offer verified bookable slots; checker alone is emerging. Transcom's service edge makes this winnable.
- **Evidence:** `01-current-state/product-page-variations.md:60-61`, `01-current-state/page-analysis.md:126-128`, `01-current-state/ecommerce-capabilities.md:45-46`, `02-ux-audit/issue-register.md:28,35,46`, `03-opportunities/opportunity-pool.md:182-196` OPP-12; Coolblue Eigen Plan + Best Buy Geek Squad patterns [WS implicit].

---

## Pattern 12 — Cart Drawer & Checkout Transparency (Mini-Cart + Landed Cost + Stepper)

- **Company:** Apple (mini-cart slide-over with landed cost before checkout), ASOS (drawer + delivery promise + `Secure checkout`), Best Buy (`Your Cart → Checkout` with cost breakdown + progress hint `Shipping → Payment → Review`), Zalando (mini-cart with delivery ETA + free returns trust badge). Common thread: **cart is not a dead-end page**; checkout steps are previewed before commitment.
- **Journey:** Journey E ("I found a product, want to buy it") — exact boundary where Transcom stalls (`02-ux-audit/executive-summary.md:49-52` conversion boundary friction, `02-ux-audit/issue-register.md:36-38` CART-01 + CHECKOUT-01 both P1).
- **Pattern:** `Add to Cart` → slide-over mini-cart drawer (not a full redirect) confirming item, landed-cost summary (from Patterns 1 & 5), delivery SLA, and `View Cart | Checkout` CTAs. Cart page shows `Order Summary: Product 1,38,605 + Delivery Tk 0 + Install Tk 0 → Total 1,38,605` + `Total if EMI: 3,863×36` + quantity/stepper + coupon + `Save for later`. Checkout header shows `1 Cart → 2 Address → 3 Delivery → 4 Payment` stepper before requesting address, with trust badges `Original Product • Secure Payment • Free Install (Selective)` echoed at stepper (fixes `TRUST-01 P2` homepage-only trust).
- **User Problem:** Empty cart is the only sampled state — it shows `You have not added any product…`, `Subtotal: ৳0`, disabled `Checkout` with no inline next-step guidance (`01-current-state/page-analysis.md:158-164` VERIFIED, `02-ux-audit/issue-register.md:36` CART-01 P1). Populated cart (quantity stepper, coupon, breakdown, cross-sell) is NOT TESTED (`01-current-state/ecommerce-capabilities.md:40` flagged as risk). Checkout steps, address/delivery/payment forms, and progress are `NOT ACCESSIBLE` from empty cart (`01-current-state/ecommerce-capabilities.md:42`, `02-ux-audit/issue-register.md:38` CHECKOUT-01 P1) — users cannot preview what checkout will ask for before they decide to trust.
- **How It Works:**
  1. Mini-cart drawer (CSS + `localStorage` cart) appears on `Add to Cart` with `✓ Added — 1 item — Total 81,000` + single-line trust `Delivery in 2–3 days to your area (1212)` (from Pattern 1 pincode) + `EMI from 2,633/month`.
  2. Cart page gains: quantity stepper, coupon field (early error text `Coupon applied: −Tk 500` or `Not applicable to AC category`), grouped breakdown (patterns 1 & 5), cross-sell rail (TV→mount/soundbar pattern in `03-opportunities` C5 — consumes same bundle feed).
  3. Checkout progress stepper is visible as non-clickable header on Cart (gives shape before entry) and becomes clickable on checkout.
  4. Empty cart at `/cart` replaces dead-end disable with `Cart is empty — Continue where you left off (Pattern 10 deep-link) + Recommended for you` so recovery is baked in.
  5. Trust propagation: `Original Product Guaranteed / Secure Payment System` moves from homepage bar (`01-current-state/page-analysis.md:34`) to cart + checkout header where trust is needed.
- **Why It Works:**
  - Violates Nielsen's "prevent errors / visibility of system status" less than any other gap: mini-cart gives immediate feedback (`FEEDBACK-01 P1` `No visible toast/confirmation after Add To Cart`), cart breakdown prevents price surprise, stepper prevents checkout anxiety. Apple/ASOS both document that drawer + stepper reduces mid-funnel abandonment more than coupon complexity alone.
  - Makes Patterns 1 & 5 visible at cart: landed cost is not repeated as abstract "estimator" but as the actual total the buyer will pay. This is where EMI monthly vs total trade-off is re-confirmed.
  - Empty-cart recovery turns a P1 dead-end into a re-entry: `Recently Viewed` + finder CTA inside empty cart salvages intent that otherwise bounces to homepage overload (`DISC-01 P1`).
  - Mobile: drawer is bottom-sheet, not sidebar — thumb-reachable; stepper compresses to `Step 2 of 4`.
- **Potential Lesson:**
  - Mini-cart + stepper first (frontend only) already removes `CART-01` and `CHECKOUT-01` P1s; populated cart quantity/coupon/cross-sell phase 2 (risk at `02-ux-audit/issue-register.md:37` CART-02) can be verified after drawer ships.
  - Reuse Patterns 1 & 5 feeds — do not build separate cart pricing. Trust badges must be SKU-truthful (`Free install` only where SKU table says free).
  - Do not add coupon complexity before checking whether coupon is even a Transcom tactic — if not, replace coupon slot with `EMI plan applies` clarity.
- **Applicability:** **HIGH** — unblocks the entire purchase boundary Journey E. In mobile-first Bangladesh with OTP-gated checkout (`02-ux-audit/issue-register.md:39` AUTH-01 split +880), giving checkout shape *before* phone entry is critical for trust.
- **Classification:** **INDUSTRY STANDARD** — expected cart transparency since ~2019; checkout stepper + mini-cart is baseline hygiene, not innovation. Absence is parity gap.
- **Evidence:** `01-current-state/page-analysis.md:158-164`, `ecommerce-capabilities.md:39-42`, `02-ux-audit/issue-register.md:36-38` CART-01/CHECKOUT-01; `02-ux-audit/executive-summary.md:40-52`; `03-opportunities/opportunity-pool.md:1` remediation note that CART-02 + filter/sort feedback belong to audit fix backlog — this pattern is the fix implementation at benchmark standard.

---

## Cross-Cutting Notes for Transcom

### What Is Standard vs What Differentiates Here

| Tier | What it means for this audit | Examples in this benchmark |
|------|------------------------------|-----------------------------|
| **INDUSTRY STANDARD** | Buyer expects it; absence signals "immature" | Pincoded PDP check (South Asia), autocomplete + recent, zero-result Did-you-mean, compare 3-up, ratings on cards, Recently Viewed, zoom, cart drawer + stepper |
| **EMERGING PATTERN** | Early adopters have it; next wave will expect it | Interactive True Cost/EMI planner, facet-relax count preview, dimension overlay/AR |
| **DIFFERENTIATOR** | Few appliance retailers do it credibly; Transcom could win here | Guided selling finder (Coolblue-grade, not shallow quiz), install slot booking, variant chips as family graph |
| **EXPERIMENTAL** | Novel, high effort, unproven for this context | Category-affinity homepage reorder (kept as P2 experiment only at `03-opportunities/opportunity-pool.md:232-244` OPP-15, not benchmarked here — A/B gate required) |

### Sequencing hint (not roadmap)

P0 hygiene before differentiators: **1 (delivery estimator) → 7 (autocomplete) → 10 (Recently Viewed) → 9 (ratings) → 12 (cart/checkout transparency) → 4 (zoom) → 6 (family chips)** are fix/standard gaps. **2 (finder) → 3 (compare) → 5 (EMI planner) → 8 (eat zero-result) → 11 (install booking)** build on those. OPP-15 homepage affinity reorder is explicitly **de-prioritised** as P2 experiment per cross-review.

### Measurement per pattern (so benchmark is testable)

| Pattern | Primary metric |
|---------|----------------|
| 1 Serviceability | `pincode_check_success% → checkout_start%` uplift, pincode-mismatch drop |
| 2 Finder | `finder→filtered PLP CTR`, `finder→PDP verdict click→ Add%`, wrong-size return % |
| 3 Compare | `compare_queue_add%`, `compare→Add%`, share URL WA share % |
| 4 Media | `zoom/video engaged PDP dwell`, image/video click-through |
| 5 EMI planner | `EMI toggle engage%`, `EMI→Cart%`, finance attach rate (bank 12/24/36 mix) |
| 6 Family chips | `sibling chip CTR`, family cross-sell % (55"→65") |
| 7 Autocomplete | `autocomplete_selected%` vs `typed_submit`, search→PDP CTR |
| 8 Zero-result | `zero_result%`, `did_you_mean_clicked%`, `facet_relax_clicked%` |
| 9 Ratings | `PLP badge CTR`, `review_submit after delivery%`, Customer Review facet usage |
| 10 Resumption | `recently_viewed_clicked%`, `continue_shopping_deeplink_clicked%`, returner conversion lift |
| 11 Install | `checker_verdict_shown%`, `slot_booked%`, failed-install % |
| 12 Cart/Checkout | `add→drawer_view%`, `cart→checkout_start%`, checkout abandonment by step |

### Evidence tiers used above

- **VERIFIED** — live BrowserOS Neo read/snapshot on 22 pages (see `01-current-state/page-analysis.md:3` + `ecommerce-capabilities.md:3`).
- **OBSERVED** — visible in snapshot but not interacted.
- **NOT TESTED / AUTH REQUIRED** — marked inline (e.g., checkout steps, wishlist persistence).
- **[WS]** — websearch spot-check that company's pattern exists as of 2025/2026 (Coolblue advice pages 2025-03-21; Amazon A+ guide 2025; Best Buy help `pcmcat203400050006`; Emerge Digital pincode PDP case 2026-05).

---

*Output: `04-benchmark/agents/global-commerce.md`. 12 patterns (high is 12, within 8–12 brief — 12 chosen to cover Search as two stages and Cart as explicit transparency, each distinct enough to avoid feature-list collapse). Each pattern is a single build unit; lenses/phases noted without re-proposing fixes as opportunities (filter/sort chips + populated-cart quantity/coupon hygiene remain remediation backlog per `03-opportunities/cross-review.md:199-208`). No product catalog data fabricated; all Transcom refs traceable to sitemap + `01-current-state/*` + `02-ux-audit/*` files.*
