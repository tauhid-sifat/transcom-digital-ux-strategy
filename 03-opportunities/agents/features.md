# Product Feature Opportunities — Transcom Digital (Phase 3 — Agent B)

> Agent B — Product Feature Strategist. Source knowledge base: `00-input/sitemap-analysis.md`, `01-current-state/*` (8 docs), `02-ux-audit/*` (6 docs), all verified 2026-09-03 via BrowserOS Neo. Scope: **genuine new product capabilities** — not UX polish. Every feature below is net-new vs `01-current-state/ecommerce-capabilities.md: VERIFIED` inventory. UX fixes (broken links, missing chips, placeholder sorts, absent toasts) are deliberately excluded — see §1.

---

## 0. Method & Ground Rules

**What counts as a feature here:** A new user-facing capability that requires product logic, data, or service design — it creates a new job-to-be-done, not just makes the existing shell work correctly. If engineering could ship it as a string fix, copy change, or CSS/ARIA restoration, it is a UX fix and belongs to Phase 2 remediation, not this register.

**Evidence tier used:** Only `VERIFIED` / `OBSERVED` states from Phase 1 are treated as existing. `NOT OBSERVED` and `NOT TESTED` states are the opportunity space — but each candidate was re-checked against `ecommerce-capabilities.md` to confirm it does not already exist as a VERIFIED entry. `AUTHENTICATION REQUIRED` flows are not assumed to exist.

**Domains covered:** Discovery, Research, Purchase Confidence, Delivery, Installation, Financing, Post-Purchase, Retention — per mission brief.

---

## 1. Features vs. UX Fixes — Boundary

| Example Issue (Phase 2) | Why it is a FIX, not a feature | What the FEATURE counterpart is in this doc |
|---|---|---|
| `NAV-01` See All → `/undefined` — repair broken href hydration (`site-inventory.md:92`, `page-analysis.md:56`) | Single-line slug fallback; no new capability | — |
| `FILTER-01` no active-filter chips, `SORT-01` placeholder `Select Sort Option`, `FEEDBACK-01` no toast (`usability-issues.md`) | Restoring expected PLP/cart feedback; no new data model | — |
| `PDP-04` tab set shifts (`Feature` absent on Mixer — `product-page-variations.md:57`) | Normalise existing tab contract | — |
| `CART-01` empty cart dead-end with disabled Checkout (`cart-checkout.md:7`) | Add `Continue Shopping` CTA to existing empty state | — |
| `INTERACTION-01` compare requires hand-typing model (`page-analysis.md:173`) if only the input is fixed | Fixing recall burden without rethinking compare | `FEA-08` below — persistent, auto-populated workspace with total-cost comparison is a new decision system, not a placeholder fix |
| `PDP-02` gating `Enable your Location` before any delivery signal (`product-page-variations.md:59`) | Replacing gate with a pincode field is a fix | `FEA-01` — pincode serviceability engine with cost/timeline/install eligibility and cart/checkout propagation is a new fulfillment capability |
| `PDP-07` Review tab with no aggregate (`ecommerce-capabilities.md:31`) | Surfacing existing rating is a fix | Social proof aggregation is deferred to personalization/social layer; not duplicated here |

**Rule applied below:** If a proposal could be completed by correcting markup, adding a chip row, or exposing an already-fetched sort array, it was discarded.

---

## 2. Feature Register — 9 New Capabilities

> Each entry: **User problem → Target user → Journey → Feature concept → Interaction model → User value → Business value → Dependencies → Complexity → Why it matters (and why it is not a fix).**

---

### FEA-01 — Pincode-First Delivery, Installation & Serviceability Estimator

- **User problem:** At the exact moment price is seen, the PDP hides the only answer that makes price actionable — *can you deliver this 600L side-by-side to my area, when, and at what cost including installation?* Current PDP shows `Home Delivery Enable your Location / Store Pickup Enable your Location` with a permission gate and no pincode fallback (`page-analysis.md:125`, `product-page-variations.md:59-60`, `ecommerce-capabilities.md:43-44` VERIFIED as preview-only). Users without location permission or on desktop abandon rather than guess.
- **Target user:** Primary — high-consideration buyers of large appliances (AC, Refrigerator, Washing Machine, TV >50") outside Dhaka central; Secondary — store-pickup intenders checking nearest outlet stock.
- **Journey:** Journey C ("I need an AC for my room") and Journey E ("I found a product and want to buy it") — PDP → Cart → Checkout. Also supports Store Locator intent (`/store-locator` List/Map — `page-analysis.md:199-204`).
- **Feature concept:** A **serviceability engine** that, given a pincode/area/district text input (no permission required), returns in one call: (a) delivery serviceable Y/N + SLA window (e.g., 2–4 days), (b) delivery fee or free-delivery eligibility, (c) installation fee / free-install flag per SKU (`Free Installation Selective Items` trust claim at `page-analysis.md:34` is currently homepage-only and not SKU-bound), (d) Store Pickup alternative with nearest 2 stores + stock signal, (e) exchange pickup eligibility for the trade-in SKU. Result persists in session and propagates to Cart Order Summary and Checkout step preview.
- **Interaction model:** Inline field under PDP price/warranty block: `Enter area / pincode [Check]` → instant result card: `✔ Deliverable to 1212 — Delivery Tk 0 (free) · Installation Tk 1,500 · Earliest Thu Sep 05 · Also available for pickup at Gulshan (1.2 km) [View stores]`. `Change` link retains edit. On Cart, same estimate re-surfaces as `Delivery & Installation estimate for 1212 — [Change]` above Subtotal (currently Subtotal-only at `page-analysis.md:161`). No permission prompt unless user opts into "Use my location". Failure state suggests nearest serviceable area.
- **User value:** Converts price interest into total-cost-of-ownership certainty before Add to Cart; eliminates permission friction; enables store-pickup as first-class choice, not fallback.
- **Business value:** Reduces PDP→Cart abandonment at the highest-ticket SKUs; lowers COD refusal / failed delivery attempts; surfaces paid installation revenue where applicable; drives Store Locator usage as fulfillment channel, not just marketing page; collects demand signals by pincode for logistics expansion.
- **Dependencies:** Delivery zone / SLA matrix by SKU category/weight; installation fee table by SKU/brand; store inventory feed or at-least store-serviceability by district; pincode/area master (Bangladesh divisions/districts already in Store Locator dropdown `page-analysis.md:201`); session persistence; CMS flag for free-install SKU set.
- **Complexity:** **High** — cross-functional (catalog, logistics, store ops, pricing).
- **Why it matters / Not a fix:** A pincode field alone is a fix. A *serviceability decision service* that unifies delivery, installation, pickup, and exchange eligibility into a single session-persistent estimate and carries it through Cart→Checkout is a new fulfillment capability. Verified existing is only a gated prompt, not a calculation (`ecommerce-capabilities.md:43-44`).

---

### FEA-02 — Room & Capacity Fit Advisor (Interactive Buying Guide)

- **User problem:** Buying guides are 1,500+ words of SEO prose above/below the PLP grid (`issue-register.md: IA-03`, `site-inventory.md:72`) that bury products and still do not answer the personal question: *Is a 1 Ton AC enough for my 130 sq ft top-floor room? Is 300L or 420L the right fridge for a family of 4? Is 55" right at 8 ft viewing distance?* `PDP-03` notes the only fit signal (`Applicable For 120 sq ft ; Height 10 ft`, `EER 3.15`) is hidden inside the `Specification` tab post-click (`product-detail-experience.md:12`). Ton/Litre/size filters exist (`product-discovery.md:77-83`) but do not map human context → spec.
- **Target user:** First-time buyers and problem-solvers (Journey C), especially AC, Refrigerator, Washing Machine, TV buyers who lack domain literacy.
- **Journey:** Journey C and B — Category L1/L2 entry → Advisor → Filtered PLP → PDP variant choice. Re-usable from PDP as "Check if this fits me".
- **Feature concept:** **Guided advisors** per appliance family, each a 2–4 question lightweight wizard that outputs a recommendation and auto-applies PLP filters + PDP variant callout:
  - **AC Advisor:** Room size (sq ft) + floor + sun exposure + room type → recommended tonnage (1 / 1.5 / 2) + inverter vs non-inverter nudge + energy label explainer.
  - **Refrigerator Advisor:** Family size + cooking frequency + space constraints → recommended litres bucket + door type (top-mount vs side-by-side vs multi-door).
  - **TV Advisor:** Viewing distance + wall vs stand + primary use → recommended size range (43"/55"/65") + resolution tier.
  - **Washing Machine Advisor:** Family size + wash frequency + space → kg capacity + front vs top load.
- **Interaction model:** Entry as `Find the right [AC/Refrigerator] for me` card above PLP filters (does not replace filters). Wizard is 3 steps with visual selectors (room icons, family icons), single primary CTA per step, and a result screen: `For 120 sq ft, 1 Ton Inverter is ideal — [See 1 Ton ACs (18)] [See 1.5 Ton if top floor]`. From PDP, a compact `Will this fit my room?` link re-opens wizard pre-filled with current SKU's spec and gives `✔ Fits / ⚠ Consider 1.5 Ton` verdict. Results are shareable via URL params.
- **User value:** Transforms generic SEO into actionable personal recommendation; validates tonnage/litres/size before financial commitment; reduces wrong-size returns and post-purchase regret.
- **Business value:** Increases high-consideration conversion where advice gap currently pushes buyers to competitors with sizing tools; lifts average order value by nudging to correctly-sized (often higher) variant; generates structured intent data (room size, family size) for merchandising; reduces service burden from undersized AC complaints.
- **Dependencies:** Rule tables per category (tonnage→sq ft, litres→family size, size→distance) validated by brand specs; PLP filter mapping (advisor output → Price/Brand/Display Size/Capacity query params); PDP spec extraction for fit verdict; analytics on advisor completion.
- **Complexity:** **Medium** — content + logic + filter integration; no new inventory system.
- **Why it matters / Not a fix:** Moving spec above the fold is a fix. A *personal-fit engine* that takes human inputs and drives filtering, variant selection, and PDP validation is a new decision-support capability. No advisor of any kind was `OBSERVED` in `product-discovery.md:27-31` or `personalization-current-state.md`.

---

### FEA-03 — Rich Media Inspection Suite (Video + Zoom + 360° + Dimension Overlay)

- **User problem:** High-ticket electronics are bought on visual and spatial confidence — bezel depth, door swing, outdoor unit size, drum depth, port layout. All 8 sampled PDPs show `4+ generic image containers` with no video player or verifiable zoom/360 (`page-analysis.md:134-135`, `product-page-variations.md:49-51` NOT OBSERVED). The 68-image DOM on the Mixer PDP (`product-page-variations.md:49`) suggests assets exist but no viewer is offered. Users cannot answer *will it fit in my alcove?*
- **Target user:** TV buyers (bezel, stand, wall mount), AC buyers (indoor/outdoor dimensions), Refrigerator buyers (door swing, depth), Washing Machine buyers (drum, door opening) — essentially every L1 category (`exploration-plan.md:22`).
- **Journey:** PDP research phase (Journey B/C/D/E) — gallery is the primary decision surface before specs.
- **Feature concept:** A **unified PDP media viewer** that, per template, layers: (a) pinch/hover-zoom on all images (mobile/desktop), (b) optional short feature video per category (e.g., 20-sec "Coanda airflow demo" for AC, "DEO Fresh" for fridge — asset-dependent), (c) 360° spin where brand assets exist, (d) **dimension overlay** — a toggle that renders key dimensions on the hero image (W×H×D + door swing arc + outdoor unit silhouette for AC) from spec-table values, so users need not parse the `Specification` tab table. Gallery count and category label are explicit.
- **Interaction model:** Gallery is a swipeable carousel with thumbnail strip, `1 / 8` count, `Zoom` affordance on hover, `▶ Video` thumb where available, `360°` badge, and `Show dimensions` toggle that overlays measurements on-image. On mobile, full-screen viewer with pinch. Missing assets degrade gracefully — viewer renders zoom-only if no video/360.
- **User value:** Visual and spatial certainty without a store visit; validates fit-for-space before delivery commitment; reduces perceived risk for Tk 50k–1.5L purchases.
- **Business value:** Increases PDP dwell and Add-to-Cart on visually-driven categories (TV/AC/Fridge); reduces returns due to "didn't fit / didn't look like photo"; unlocks brand co-op video assets already produced for offline retail; differentiates from price-only competitors.
- **Dependencies:** Brand media asset pipeline (images, video URLs, 360 frames); spec-table dimension fields normalized; image CDN / viewer component; CMS toggle per PDP for video/360 presence.
- **Complexity:** **Medium** — front-end viewer + CMS contract; asset acquisition is organizational, not technical.
- **Why it matters / Not a fix:** No viewer exists to fix — `ecommerce-capabilities.md:30-33` records gallery as `OBSERVED` placeholders and video as `NOT OBSERVED`. This is a new media capability, not a repair of a broken gallery.

---

### FEA-04 — Product Family & Variant Navigator

- **User problem:** Choice within a product family is artificially hard. Only AC exposes an in-PDP variant control (`Choose Ton: 1 Ton / 1.5 Ton` — `page-analysis.md:121`, `product-page-variations.md:52` VERIFIED); TVs show no size switcher despite PLP `Display Size 55"(10) 43"(7)` filters, fridges no litre switcher, washers no kg switcher (`product-detail-experience.md:52`, `issue-register.md: PDP-08`). Users who landed on a 55" TV PDP but wondered about the 65" sibling must back out to the PLP and re-filter.
- **Target user:** Comparison shoppers narrowing within a brand/model line (Journey B/D) — especially Samsung/Transtec/ROWA TV families, Haier fridge lines, Daikin AC families.
- **Journey:** PDP → PDP sibling navigation; also PLP → PDP entry where family context is preserved.
- **Feature concept:** **Family navigator** — where a PDP belongs to a product family (same model root, different capacity/size/tonnage), the PDP renders a variant chip row: `Also in this family: 43" · 55" (you are here) · 65" · 75"` or `1 Ton (you are here) · 1.5 Ton · 2 Ton`, each chip linking to the sibling PDP slug and showing its price/delta inline. Chips reflect live availability (`In stock` vs `Currently Unavailable` — `page-analysis.md:113` pattern). PLP cards for family products show `+2 sizes` affordance.
- **Interaction model:** Horizontal chip row directly under Title/SKU line (above price), with selected state, stock badge, and micro-price delta (`+Tk 8,000`). Hover shows mini-spec diff (e.g., `65" — 4K · 120Hz`). From Cart, family context persists for exchange.
- **User value:** Single-tap exploration of the adjacent choice without losing PDP context; validates whether a step-up in size/tonnage is worth the delta; preserves mental model of a family rather than isolated SKUs.
- **Business value:** Increases PDP-to-PDP traversal within owned family (higher likelihood to find the right variant vs exiting); lifts AOV via step-up chips; reduces PLP bounce; gives merchandising a lever to steer families (e.g., surface 55" hero variant).
- **Dependencies:** Product family graph (model root → variant SKUs) — requires catalog enrichment beyond flat root slugs (`sitemap-analysis.md:26` flat namespace); variant dimension field mapping; price/availability feed per sibling.
- **Complexity:** **Medium** — catalog modeling + PDP component; no checkout dependency.
- **Why it matters / Not a fix:** Adding a second tonnage button is a fix for AC only. A *family graph* that unifies TVs, fridges, washers, and AC into a consistent sibling navigator is a new catalog capability. Current `VERIFIED` is only the isolated AC tonnage buttons.

---

### FEA-05 — Interactive EMI & Affordability Planner

- **User problem:** Financing is signaled but not plannable. PLP cards show `EMI36` + `EMI From 1167 Tk/month` and PDPs show `EMI From … Avail Bank EMI` with a footer link to `EMI Bank List` (`page-analysis.md:114-117`, `ecommerce-capabilities.md:47` VERIFIED), but EMI availability is inconsistent (Haier 622IBG Fridge at Tk 1.38L showed **no EMI line** — `product-page-variations.md:55`, `product-detail-experience.md:25`). Users cannot answer *which bank, for how many months, at what effective monthly cost including down payment?* High-ticket COD anxiety is unaddressed.
- **Target user:** Price-sensitive and EMI-dependent buyers of TV, AC, Refrigerator, Washing Machine (Tk 30k–1.5L range) — a core Transcom financing segment per `page-analysis.md:114-117`.
- **Journey:** PDP price consideration → Cart affordability check → Checkout payment method choice.
- **Feature concept:** **Affordability planner** — a PDP and Cart-embedded calculator that, given a product (or cart total), lets users: select tenure (3/6/12/18/24/36), select bank from EMI Bank List, see `Monthly: Tk X · Total with EMI: Tk Y · Savings vs MRP` with bank-specific interest flag, toggle `Down payment` slider, and see eligibility threshold messages where EMI is unavailable (`Not eligible for EMI — Cash/Card only — [Why?]`). At Cart level, planner aggregates cart total and recommends an EMI plan for the basket.
- **Interaction model:** PDP link `See EMI options` opens a bottom sheet: tenure chips → bank dropdown (with bank logo) → live `Tk X / month` readout + `Check eligibility` hint. Selected plan can be saved as checkout preference (`Pay with EMI · BRAC 12 months · Tk 7,120/mo` pill near Checkout). Cart shows `Or pay Tk X/mo × 12 with EMI — [Plan]` under Order Summary (currently Subtotal-only at `page-analysis.md:161`). Unavailable case shows rationale + alternative financing links, not silence.
- **User value:** Turns a badge into a budget decision; removes EMI ambiguity that currently varies by product without explanation; lets users self-qualify before checkout.
- **Business value:** Directly lifts conversion on high-ticket where EMI is the gating factor; reduces checkout abandonment at payment step; increases attachment of EMI transactions (higher bank settlement certainty); generates demand signal for bank partnership optimization.
- **Dependencies:** EMI rule table by price threshold + bank (sourced from `EMI Bank List` page); interest/effective-rate data per bank/tenure; product-level EMI eligibility flag; Cart aggregation logic.
- **Complexity:** **Medium** — business rules + UI; no payment gateway change until checkout integration phase 2.
- **Why it matters / Not a fix:** Normalising the `EMI36` badge vs `Avail Bank EMI` text divergence (`issue-register.md: CONSISTENCY-01`) is a fix. An *interactive, bank-aware affordability plan* that persists to checkout is a new financing capability. Existing `VERIFIED` is only static badge/text.

---

### FEA-06 — Installation & Extended Service Slot Booking

- **User problem:** Installation is a trust claim (`Free Installation Selective Items` homepage bar at `page-analysis.md:34`, footer `Installation` link at `page-analysis.md:22-26`) but never an actionable step. AC, refrigerator, washing machine, and TV buyers face unquantified post-purchase work: *who installs, when, is it free, what if my wall needs a bracket?* PDPs show no install line (`product-page-variations.md:60` NOT OBSERVED) and Cart shows no install scheduling. Anxiety peaks after payment, driving support calls.
- **Target user:** AC / Refrigerator / Washing Machine / Large TV buyers requiring installation or wall-mount — the highest-value, most service-sensitive segment.
- **Journey:** PDP delivery estimate (FEA-01) → Cart → Checkout address → Post-purchase order confirmation → Service tracking (`Track Your Service` header link at `page-analysis.md:7-8` OBSERVED but flow NOT TESTED).
- **Feature concept:** **Install & service booking** — at Checkout (or immediately post-order), users can: (a) see install eligibility per SKU (free vs paid + fee), (b) pick a preferred installation window (date + half-day slot), (c) add prerequisites checklist per appliance (e.g., AC: pre-install site requirements, bracket note), and (d) opt into extended service/warranty add-on where offered. Post-order, the slot is trackable via `Track Your Service` and reschedulable. Non-booking flow remains valid (install scheduled via call), but the digital path is now offered.
- **Interaction model:** Checkout step `Delivery & Installation` adds `Installation: ✔ Free for this AC — [Choose slot]` or `Installation: Tk 2,500 — [Choose slot] [Skip & arrange later]`. Calendar widget shows next 7 days with half-day slots, plus prerequisite summary (`Requires: 10A socket, drain point, wall bracket — included/free`). Confirmation renders on Order Success + Order History (AUTHENTICATION REQUIRED area at `ecommerce-capabilities.md:59-60`) with `Reschedule` link.
- **User value:** Converts a vague promise into a committed appointment before payment; clarifies total cost including install; reduces post-delivery uncertainty and support burden.
- **Business value:** Reduces failed-install visits (prerequisite communicated upfront); improves NPS for large appliances; creates service revenue attach for paid installs; differentiates on after-sales where pure-price competitors cannot compete; drives `Track Your Service` engagement.
- **Dependencies:** Installation fee/eligibility table (ties to FEA-01); slot capacity by district/installer team; order ↔ service order linkage; `Service Charges / Service Pre-Requisite / Service Payment` content pages referenced in footer (`page-analysis.md:23`) as source of truth; authenticated Order History (requires `AUTH-01` OTP flow at `page-analysis.md:191-195`).
- **Complexity:** **High** — operations + scheduling + order linkage.
- **Why it matters / Not a fix:** Surfacing install fee text on PDP is a fix (`product-detail-experience.md:44`). A *bookable, trackable installation appointment with slot choice and prerequisite disclosure* is a new post-purchase service capability. No booking flow was `OBSERVED` in any of `ecommerce-capabilities.md:42-46`.

---

### FEA-07 — Price Drop, Stock Alert & Wishlist Intelligence

- **User problem:** Wishlist and stock alerts exist as buttons but not as intelligence. PDPs show `Wishlist ()`, `Get Stock Alert` when `Currently Unavailable` (Dell outlier — `product-page-variations.md:58`, `ecommerce-capabilities.md:49` VERIFIED), and `/wishlist` guest empty state is `You have not added any product...` with no price history or notification explanation (`page-analysis.md:168`, `ecommerce-capabilities.md:37-38` AUTHENTICATION REQUIRED). Users who save a 55" TV at Tk 79,900 have no way to know it dropped to Tk 74,900, and users who request stock alert get no timeline expectation (`issue-register.md: FEEDBACK-02`).
- **Target user:** Consideration-phase savers (Journey F — returning), deal watchers, and out-of-stock seekers.
- **Journey:** PDP Wishlist/Save → Wishlist page → Return visit (retention) — plus Campaign/PLP discovery loops.
- **Feature concept:** **Wishlist intelligence** — wishlist becomes a tracked list where each saved item shows: live price, discount vs saved-at price, price delta badge (`↓ Tk 5,000 since saved`), stock status with restock ETA where available, EMI change, and campaign eligibility (`Now in Online Offer`). Users can opt into **Price Drop Alert** (threshold: any drop or ≥5%) and **Back-in-Stock Alert** with explicit promise copy (`We'll notify by SMS/email within X hours of restock — avg restock 6 days for this category`). Alerts are managed in Wishlist and Account. Low-stock nudge (`Only 3 left`) is optional.
- **Interaction model:** PDP `Wishlist` toggle becomes `Saved — alerts on/off` with inline `Notify on price drop [✓]`. Wishlist cards enrich: `Haier 55" H55P7UX — Tk 74,900 (was Tk 79,900 ↓6.2%) · In stock · EMI Tk 2,100/mo · [Move to Cart] [Set alert]`. Out-of-stock PDP replaces `Get Stock Alert` with `Notify me — avg restock 5–7 days for TVs [Notify via SMS]`. Empty-state copy teaches value (`Save items to track price & stock — we'll alert you`).
- **User value:** Turns save-for-later into active monitoring; justifies delay without losing intent; removes need to re-check price manually; makes stock alert trustworthy via timeline.
- **Business value:** Recaptures high-intent savers via triggered alerts (highest-ROI retention channel for electronics where purchase cycles are weeks); increases wishlist persistence/return visits; reduces "saved then forgot" leakage; provides demand signal per SKU for restock prioritization.
- **Dependencies:** Price history per SKU; stock/ETA feed per warehouse; notification channel (SMS/email; OTP phone already collected at `page-analysis.md:191`); authenticated wishlist persistence (currently guest-empty — `ecommerce-capabilities.md:57-58`); preference store for alert thresholds.
- **Complexity:** **Medium** — wishlist enrichment + notification plumbing; ETA accuracy is the hardest part.
- **Why it matters / Not a fix:** Adding a toast after Wishlist click (`FEEDBACK-01`) is a fix. A *monitored, alerting wishlist with price history and restock ETA* is a new retention capability. `ecommerce-capabilities.md:54` records price alerts as `NOT OBSERVED` and stock alert as a button only, not a managed intelligence.

---

### FEA-08 — Smart Compare Workspace (Persistent, Auto-Populated, Total-Cost Aware)

- **User problem:** Comparison is essential for TVs, refrigerators, ACs, and washers, but the current `/compare` is a manual recall task: three empty inputs `Model name or part of product details` + `Highlight differences` + `Clear All` (`page-analysis.md:173-178`, `ecommerce-capabilities.md:23-24` VERIFIED as empty-state, populated `NOT TESTED`). PDP `Compare ()` exists on every PDP (`page-analysis.md:129`, `user-journeys.md:234` VERIFIED) but there is no evidence it populates `/compare`. Journey D friction is P1 precisely because accumulation is not observed (`user-journey-friction.md:75-96`, `issue-register.md: INTERACTION-01`).
- **Target user:** Short-listers comparing 2–3 shortlisted SKUs within a category — TV buyers (size/panel), fridge buyers (litres/door), AC buyers (ton/inverter).
- **Journey:** PLP shortlist → PDP accumulation → Compare workspace → Decision → Cart (Journey D → E).
- **Feature concept:** **Smart Compare workspace** — a persistent, session-wide decision board: (a) PDP `Compare` toggles add/remove to a sticky `Compare bar` (footer) showing up to 4 items with thumbnails; (b) `/compare` auto-populates from the bar (no typing required) but retains `Add more by search` as secondary; (c) table auto-highlights differing specs (panel, compressor, EER, capacity, warranty, EMI monthly delta) with `Highlight differences` on by default; (d) **total-cost row** per SKU: `Price + Delivery/Install (from FEA-01) + EMI total (from FEA-05) + Warranty term` so comparison is on ownership cost, not sticker price alone; (e) `Clear / Remove` per column and deep-linkable share URL.
- **Interaction model:** PDP `Compare` → bar animates `Tv added — 1/4 [Compare now]` (no page leave). Bar persists across PLP/PDP via session. `/compare` renders column per SKU with spec rows; diff-highlighted rows are tinted; total-cost row is pinned at top. Search inputs remain for "Add a 4th model" but pre-filled suggestions include recently viewed (ties to FEA-09).
- **User value:** Zero-effort accumulation via recognition (not recall); diff-highlighting reduces spec-hunting cost; total-cost lens prevents sticker-price illusion; share URL enables family decision.
- **Business value:** Increases comparison completion rate (core for high-ticket conversion); lifts AOV by making step-up cost visible in context; reduces returns from spec misread; creates a shortlist signal for retargeting and sales assist.
- **Dependencies:** Persistent compare store (session/local + authenticated sync); spec normalization per category (needs canonical row labels — currently shifting tab sets at `product-detail-experience.md:15`); FEA-01 delivery/install and FEA-05 EMI feeds for total-cost row; share-link generation.
- **Complexity:** **Medium** — front-end workspace + spec normalization; no new inventory system.
- **Why it matters / Not a fix:** Replacing manual search inputs with autocomplete is a fix. A *persistent, auto-populated, total-cost decision board* is a new comparative shopping capability. Current `VERIFIED` is only entry + empty table.

---

### FEA-09 — Complete-the-Setup Bundles & Consumables Attach

- **User problem:** PDPs sell an isolated unit with no notion of total ownership. No `Frequently bought together`, bundle, or accessory rail was `OBSERVED` across any category (`product-page-variations.md:66-67`, `ecommerce-capabilities.md:56`, `product-detail-experience.md:55` NOT OBSERVED). Yet ownership requires accessories: stabilizer/UPS for TV, bracket/wiring for AC, detergent/stand for washer, water filter cartridge for purifiers, wall mount for TV. Users discover the missing part after delivery, causing a second purchase trip.
- **Target user:** First-time category buyers completing a setup — especially TV, AC, Washing Machine, Water Purifier, Small Appliances.
- **Journey:** PDP consideration → Cart attach → Post-purchase re-order (retention).
- **Feature concept:** **Contextual bundles** per appliance family, attachable in one tap:
  - TV → stabilizer / wall mount / HDMI / soundbar (as defined bundle)
  - AC → bracket + wiring kit + extended service add-on
  - Washing Machine → detergent starter + stand
  - Water Purifier → consumable cartridge refill cadence
  - Small/Kitchen → accessory variants (e.g., ironing board for irons — where catalog supports)
  Bundles are **not** forced kits; each item is individually toggleable with bundle discount vs à la carte sum. Cart and post-order surfaces re-offer consumables on a schedule.
- **Interaction model:** PDP section `Complete your setup — frequently bought with this [TV]` with 2–4 accessory cards, each with checkbox, mini-price, and bundle saving badge (`Bundle save Tk 1,200`). Single `Add setup to Cart (3 items)` CTA. Cart renders bundle as grouped line items with individual removal. Post-order, purifier consumable shows `Next refill due: Jan 2027 — [Remind me]` tied to Order History.
- **User value:** One-trip complete purchase; transparent total setup cost upfront; no post-delivery surprise accessory hunt; consumable reminders prevent lapse.
- **Business value:** Directly increases average items per order and margin via accessory attach; unlocks bundle discount as promotional lever without site-wide discounting; builds post-purchase re-order habit (especially purifiers); reduces support tickets for "what else do I need?"
- **Dependencies:** Accessory catalog tagging per family; bundle definition CMS (which accessories bundle with which PDP family); pricing/discount rule for bundle vs à la carte; Cart grouped-line support; post-purchase reminder plumbing (ties to Account Order History `AUTHENTICATION REQUIRED` area).
- **Complexity:** **Medium** — catalog + CMS + cart grouping; consumable cadence is Med-High if fully automated.
- **Why it matters / Not a fix:** Related Products exists as a single cross-sell card (`product-page-variations.md:66` Related Products H2 with one HP card). A *curated, toggleable ownership bundle with bundle pricing and post-purchase consumable cadence* is a new merchandising and retention capability, not an extra Related card.

---

## 3. Cross-Feature View & Sequencing Notes

### 3.1 Coverage of Mission Domains

| Domain | Features |
|---|---|
| Discovery | FEA-02 Advisor (problem→product), FEA-09 Bundles (setup discovery) |
| Research | FEA-03 Rich Media, FEA-08 Smart Compare |
| Purchase Confidence | FEA-04 Variant Navigator, FEA-03 Dimensions, FEA-07 Wishlist Intelligence |
| Delivery | FEA-01 Serviceability Estimator |
| Installation | FEA-01 (fee/timeline) + FEA-06 Slot Booking |
| Financing | FEA-05 EMI Planner |
| Post-Purchase | FEA-06 Slot/Track, FEA-09 Consumable cadence |
| Retention | FEA-07 Price/Stock alerts, FEA-08 Shareable compare, FEA-09 re-order |

### 3.2 Priority Sequencing (Suggested Build Order)

1. **FEA-01 + FEA-05 (Estimator + EMI)** — highest conversion leverage on PDP/Cart with shared session persistence; unlocks total-cost lens for FEA-08 and FEA-06.
2. **FEA-08 (Smart Compare)** — transforms the highest-friction journey (D) with moderate effort via spec normalization.
3. **FEA-04 (Variant Navigator)** — small catalog enrichment, immediate findability win for families.
4. **FEA-02 (Advisor)** — content-heavy but no integration risk; effective for AC/Refrigerator entry.
5. **FEA-03 (Rich Media)** — asset-dependent; start with zoom + dimension overlay, then video/360 as assets arrive.
6. **FEA-07 (Wishlist Intelligence)** — retention flywheel; depends on authenticated wishlist hardening.
7. **FEA-09 (Bundles)** — merchandising lever; bundles can ship before full bundle discounting.
8. **FEA-06 (Slot Booking)** — highest operational dependency; phase after logistics/slot capacity is confirmed.

### 3.3 Explicit Non-Features (Deferred as Fixes, Not Opportunities)

Broken `See All` → `/undefined` hydration (`site-inventory.md:92`), active-filter chip restoration (`FILTER-01`), sort enumeration (`SORT-01`), wishlist/compare toasts (`FEEDBACK-01`), `Customer Review` bucket empty state (`FILTER-02`), warranty nomenclature cleanup (`PDP-05`), and icon-label accessibility (`ACCESS-01`) are acknowledged as required remediation but not recast as features here.

---

## 4. Evidence Index (Traceability)

| Feature | Primary Evidence (file:line) | Gap Signal |
|---|---|---|
| FEA-01 | `page-analysis.md:125`, `product-page-variations.md:59-60`, `ecommerce-capabilities.md:43-44`, `site-inventory.md:58-63` | `Enable your Location` gate only; no pincode serviceability |
| FEA-02 | `issue-register.md: IA-03`, `product-detail-experience.md:12-13`, `product-discovery.md:74-83` | Generic SEO guide not interactive; fit data tab-hidden |
| FEA-03 | `page-analysis.md:134-135`, `product-page-variations.md:49-51`, `ecommerce-capabilities.md:30` | Gallery placeholders only; `NOT OBSERVED` video/zoom |
| FEA-04 | `page-analysis.md:121`, `product-page-variations.md:52`, `product-detail-experience.md:52`, `sitemap-analysis.md:26` | Only AC has PDP variant; TV/Wash/Fridge have no sibling switch |
| FEA-05 | `page-analysis.md:114-117`, `product-page-variations.md:55`, `ecommerce-capabilities.md:47`, `issue-register.md: PDP-06` | Static `EMI36`/`Avail Bank EMI` badges; inconsistent availability |
| FEA-06 | `page-analysis.md:33-34`, `product-page-variations.md:60`, `ecommerce-capabilities.md:45-46` | Install referenced only in trust bar/footer; no booking |
| FEA-07 | `page-analysis.md:168`, `product-page-variations.md:58`, `ecommerce-capabilities.md:36-38,54,49`, `issue-register.md: FEEDBACK-02` | Wishlist guest-empty; price alert `NOT OBSERVED`; stock alert no timeline |
| FEA-08 | `page-analysis.md:173-178`, `ecommerce-capabilities.md:23-24`, `user-journey-friction.md:75-96` | Manual 3-search compare; accumulation not observed |
| FEA-09 | `product-page-variations.md:66-67`, `ecommerce-capabilities.md:56`, `product-detail-experience.md:55` | `Frequently bought together / Bundles NOT OBSERVED` |

---

*Author: Agent B — Product Feature Strategist. Phase 3 output. Nine new capabilities, each net-new vs VERIFIED inventory, each with user + business value and delivery dependencies. First pass sequencing favours fulfillment + financing + comparison as the conversion-critical path.*
