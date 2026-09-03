# Final UX/UI Improvement Scope & Strategic Roadmap — Transcom Digital

> **Electronics & Home Appliance E-Commerce — Bangladesh**
> Synthesis of Phases 1–5: Current State Discovery → Gap Analysis → Opportunity Discovery → Market Benchmarking → Prioritization | Date: 2026-09-03 | Evidence spans `00-input` → `05-prioritization`

---

# 1. Executive Summary

**Purpose.** A six-phase programme reviewed Transcom Digital (transcomdigital.com) beyond a visual UI audit — covering how customers discover, research, compare, afford, receive and trust electronics purchases (AC 1–1.5 Ton, fridge 245–600L, TV 32–100", washer 8KG) in a Bangladesh mobile-first, high trust-sensitivity, 75–90% COD market.

**Scope.** Sitemap 167 URLs → 22 templates, 8 PDP samples across 9 categories, 9 journey tests, 32 UX issues, 38 raw opportunities → 15 consolidated + 8 benchmarking NEW, benchmarked against 21 platforms (Amazon.in, Flipkart, Daraz, Coolblue, Best Buy, AO, Currys, Pickaboo etc.) across 33 patterns, consolidated into 25 prioritized initiatives.

**Overall observation.** The platform is **content-present, interaction-immature**. Catalog breadth, 39 category PLPs + 13 brand PLPs with taxonomy-aware filters, warranty adapted per appliance, and EMI36 financing signal a functioning shell. But foundational hygiene fails: primary discovery CTAs dead-end, PLP browse controls are placeholder/empty, delivery confidence is permission-gated before price trust, and the purchase path (Add→Cart→Checkout) has no landed-cost truth or step visibility. High-consideration decisions (room-size, tonnage, energy, install, warranty, total cost) are buried or absent where researched, and post-Evaly trust is claimed on the homepage but not proved at the price context. The result is not a catalog gap — it is a **confidence + memory gap**.

**Key problem themes (Phase 2).**
1. Discovery breaks — `NAV-01 /undefined` blocks browse; heavy homepage serialises 7+ grids; no Recently Viewed resumption.
2. Decision support thin — spec buried one click deep, no jargon decoder, no video/zoom, no ratings.
3. System status invisible — no filter chips, placeholder sort `Select Sort Option` + `sortOptions:[]`, pagination `Show 12 <of 1> 1`, no toast after Add.
4. Purchase boundary opaque — `FEEDBACK-01/CART-01/CHECKOUT-01` cluster: gated delivery, no landed-cost row, no stepper.
5. Consistency fractures — flat PDP URLs, warranty `Parts-0M/Motor-300M`, EMI badge vs text divergence.

**Major opportunities validated.**
Fulfillment confidence as one row (pincode-first delivery + install + energy + EMI), browse resumption without backend, requirement-led finders (AC tonnage → Fridge litres), persistent compare with total-cost pin, variant family chips, spec jargon decoder, and trust-stack mechanics (authorized badging + OBD + plural payment + human WhatsApp) — each validated as INDUSTRY STANDARD or differentiator vs Daraz, not as invention.

**Strategic direction.** Fix foundations first (makes 7 future initiatives work for free), then prove high-value differentiators (finders, true cost, family navigator) on the highest-ticket family (AC) before scaling, defer affinity homepage and full AI diagnostics until hygiene and supply prove. NOW = critical friction + trust row + memory. NEXT = decision support + compare + media. LATER = install booking + review pipeline + bundles at scale. EXPERIMENT = affinity reorder A/B. Detail in §10–13.

---

# 2. Review Scope & Methodology

**What was reviewed.**

- **Sitemap-driven exploration** — `00-input/sitemap-analysis.md` 167 URLs (urlset via octopus.do, 101 PDPs flat at root `/{brand}-{product}`, 39 category PLPs L1–L4, 13 brand PLPs). Consolidated inventory, duplicate/hygiene signals (trailing-hyphen 4, `/tv-av` orphan, `search?Brand=samsung` duplicate).
- **Representative page analysis** — 22 live pages via BrowserOS Neo: Homepage, 5 top cats, 3 deeper PLPs (`smart-tv`, `dry-irons`, `inverter-ac`), brand `samsung`, search, 8 PDPs including AC `FTKL12TV16WD EER 3.15 Applicable For 120 sq ft`, fridge `HRF-622IBG 600L`, TV `H55P7UX`, washer, Dell outlier `Currently Unavailable` — see `01-current-state/page-analysis.md:7-34,134-135` and `product-page-variations.md:49-61`.
- **User journey testing** — 9 journeys A–F (Journeys A know-exactly, B know-category, C problem AC-for-room, D compare 3 TVs, E buy, F returning) per `01-current-state/user-journeys.md:14-48` and `02-ux-audit/user-journey-friction.md`.
- **UX/UI gap analysis** — 32 issues against Nielsen heuristics + e-commerce principles (P0 1, P1 13, P2 14, P3 4) per `02-ux-audit/issue-register.md:7-46` (CONF HIGH 23, MED 9).
- **Multi-agent opportunity discovery** — 38 raw (PER 9 + FEA 9 + EDS 9 + ECS 11) → cross-review 9 duplicate clusters C1–C9 → 15 consolidated OPP-01–15 per `03-opportunities/opportunity-pool.md` + `duplicates-and-overlaps.md:6-19`.
- **Market benchmarking** — 33 patterns across 21 platforms (Global 12, Electronics 11, Regional 10) → 12 problem-centered groups × 38 reusable variations `04-benchmark/pattern-library.md` → applicability review validated 8 / enhanced 5 / questioned 2 + 8 NEW regional distinct `04-benchmark/applicability-review.md:22-152`.
- **Strategic consolidation & prioritization** — 34 normalized INVs → 25 after 6 merges `05-prioritization/initiative-merging.md:15-23` → value (9 VERY HIGH…) + feasibility (8 LOW/6 MED/8 HIGH/3 VERY HIGH) + strategic critique (8 APPROVE/14 SIMPLIFY/3 DEFER) → decision-log resolutions → dependency map 7 foundational tables → unified scope by 10 strategic areas + NOW/NEXT/LATER/EXPERIMENT `05-prioritization/phase-5-summary.md`.

**What this is not.** Not a visual UI review. Scope covers user experience, product discovery, decision making, e-commerce capabilities, personalization lifecycle, and electronics-specific buying journeys (capacity, room-size, energy, compatibility, installation, ownership). Traceability per `recommendation-traceability.md`.

---

# 3. Current Experience Overview

**Website structure.** Single domain `https://transcomdigital.com` with flat PDP namespace (101 PDPs at `/` like `/daikin-...-1-ton`) and hierarchical PLP taxonomy L1 `air-conditioner` / `refrigerators` / `home-kitchen` / `washing-machine` / `personal-care` → L2 `residential` → L3 `inverter-ac` → L4 `dry-irons` etc. (39 PLPs) + 13 brand PLPs `/samsung` etc. Campaign hub `/campaigns` → `/campaign/online-offer` (`Load more`), cart/wishlist/compare/login/store-locator/exchange. Checkout not in sitemap — reachable only after non-empty cart + OTP `0157…`.

**Major page types.** Homepage (7+ mini-grids Electric Kettles…TV + 6 Shop By Category tiles + trust bar `Free Installation / Original / Exchange / Secure`), Category/Brand/Search PLP (breadcrumb `Home>TV|AV>Television>Smart TV`, price dual slider + buckets `0 to 1,00,000` + brand checkboxes `SAMSUNG(14)`, `Display Size 55"(10)`, `Latest Products` rail, `Select Sort Option` + `Show 12 <of 1> 1`), PDP (title+model `/brand` + `In stock` vs `Currently Unavailable` Dell → `Get Stock Alert` + `Save 7,295 -5%` + `EMI From X` + 4-bullet Key features + `Options: Choose Ton 1/1.5` on AC only + warranty `Service-12M / Parts-12M / Compressor 60M` vs `Special 0M/Motor-300M` + `Home Delivery Enable your Location / Store Pickup Enable your Location` + tabs `Overview|Feature|Specification|Review|Product Policy` (spec table after click: `Refrigerant R32 / EER 3.15 / Applicable For 120 sq ft`) + `Compare/Wishlist/Share` + two `Add To Cart` + `Related Products`), cart empty `Subtotal ৳0 Total 0` disabled Checkout, wishlist/compare empty 3-slot with `Highlight differences` + `Model name or part…` hand-search, login `+880` split two textboxes + `Next`.

**Core journeys.** A know-exactly via `Search Here` (placeholder generic), B know-category via Shop By Category → filtered PLP → sort → compare → PDP, C problem solver `I need AC for 120 sq ft`, D compare 3 smart TVs, E add→cart→checkout (stops before payment `Need help? Click Here`), F returning resume (empty). Journeys B/C/E/D carry P0/P1 clusters.

**Existing capabilities.** Taxonomy-aware filters, EMI36 badges, campaign countdown 27 days, Related Products, track order/service links, store locator List/Map + Mapbox 68 images PDP weight.

**Existing personalization.** **None observed as guest** for 14 capabilities (`01-current-state/personalization-current-state.md:9-14` all NOT OBSERVED except PARTIAL gate `Enable your Location`; grep `Recently viewed / Recommended for you / Continue shopping / Because you viewed X` = 0/20 pages). Generic `Best Deals / Latest / Related` verified but catalog-driven.

**Strengths.** Catalog breadth signals reliability (39 PLPs correctly mirrored in breadcrumbs), filter taxonomy adapts by category, warranty per-appliance, trust peripherals exist (4-icon bar + EMI badges + store locator), Compare/Wishlist entry ubiquitous, breadcrumbs throughout.

---

# 4. Key UX/UI Challenges

Grouped as strategic themes (not an exhaustive 32-issue dump; see `02-ux-audit/issue-register.md:7-46` for file:line).

## Navigation & Information Architecture
**Problem summary.** Primary discovery terminates, hierarchy severs. **Affected:** Journeys B/C at entry. **Why it matters:** Browse is the default for appliance consideration; dead-ends trash funnel before PLP. **Evidence:** `NAV-01 P0 HIGH` 11× See All → `/undefined` `/samsung/undefined` `page-analysis.md:56-57`; IA-01 flat 101 PDPs `sitemap-analysis.md:27` severs hierarchy; IA-02 `/tv-av` orphan `sitemap-analysis.md:74-76`; IA-03 1,500-word SEO pushes grid below fold `page-analysis.md:90-91`; NAV-02 brand vs `/search?Brand=samsung` duplicate confusion; IA-04 trailing-hyphen 4 slugs.

## Product Discovery
**Problem summary.** Overload plus no memory. **Affected:** B/C heavy, F wholly unserved. **Why it matters:** Appliances need resumption across sessions (50k–1.5L). **Evidence:** `DISC-01 P1` homepage 7+ serial grids + 11 See All → cognitive overload `page-analysis.md:48-54`; `DISC-02 P1` no Recently Viewed/Continue `personalization-current-state.md:9-10` DISC-02 P1; DISC-03 Related thin single card `product-page-variations.md:65-66`.

## Search & Filtering
**Problem summary.** Fast-path invisible, controls unusable. **Affected:** A (exact model `FTKL12TV16WD`), B (narrow). **Why it matters:** Model-aware buyers in store photograph codes; typos for alphanum dead-end. **Evidence:** `SEARCH-01 P1 MEDIUM` suggestions NOT FULLY VERIFIED `user-journeys.md`; `SEARCH-02 P3` placeholder `Search Here` `page-analysis.md:9`; `SEARCH-03 P2` zero-result NOT TESTED `ecommerce-capabilities.md:15`; `FILTER-01 P1 MEDIUM` no chips; `FILTER-02 P2` `Customer Review` empty heading; `FILTER-03 P2` price slider+buckets compete `page-analysis.md:77-78`; `FILTER-04 P3` `Display Size` vs `Screen` duplication; `SORT-01 P1 HIGH` placeholder `sortOptions:[]`; `SORT-02 P2` pagination `Show 12 <of 1> 1` ambiguous.

## Product Research & Decision Making
**Problem summary.** Problem solvers self-translate life need → spec without help. **Affected:** C/I need AC for room, family→litres. **Why it matters:** Wrong tonnage/litres → dissatisfaction/return/service. **Evidence:** Guided Selling wizard NOT OBSERVED; spec buried one click deep `product-detail-experience.md:12` tab-hidden `EER 3.15 / Applicable For 120 sq ft` only after click; SEO wall generic text; PDP-05 warranty implausible `Parts-0M`.

## Product Detail Experience
**Problem summary.** Confidence thin where needed. **Affected:** All high-consideration PDPs at price exposure. **Why it matters:** Visual + proof + variant + landed-cost determine Tk80k+ trust. **Evidence:** `PDP-01 P1` no video/zoom 4+ generics `page-analysis.md:134-135` 68 DOM images `product-page-variations.md:49-50` Video NOT OBSERVED `ecommerce-capabilities.md:30`; `PDP-07 P1` Review tabs exist `page-analysis.md:131-133` but no aggregate stars count; `PDP-08 P2` only AC has `Choose Ton` `page-analysis.md:120-121` TV no sibling; `PDP-02/03` delivery gated `Enable your Location` + install absent; `PDP-06 P2` EMI absent on Haier 622L `product-page-variations.md:55`; `PDP-09` duplicate Add To Cart `page-analysis.md:126-128`.

## Cart & Checkout
**Problem summary.** Boundary opaque, cost surprise. **Affected:** Journey E purchase. **Why it matters:** Location-gated fee + invisible install + checkout preview missing = paywall surprise for big ticket. **Evidence:** `CART-01 P1` empty `Subtotal ৳0` disabled Checkout no `Continue Shopping` `page-analysis.md:159-164`; `FEEDBACK-01 P1 MEDIUM` no toast after Add; `CHECKOUT-01 P1 HIGH` steps/Address/Delivery/Payment NOT ACCESSIBLE in empty `user-journeys.md:122-148` + `ecommerce-capabilities.md:42`; landed-cost truth missing.

## Trust & Confidence
**Problem summary.** Claimed on homepage, not proved at price. **Affected:** All journeys at PDP/Cart price context. **Why it matters:** Post-Evaly penetration 2–3% (TBS), trust is #1 barrier. **Evidence:** `TRUST-01 P2` trust bar homepage-only `page-analysis.md:34` vs PDP generic brand link `page-analysis.md:112` + warranty claim not proof `ecommerce-capabilities.md:46`.

## Account & Retention
**Problem summary.** Save is inert, return is amnesiac. **Affected:** F/Wishlist/Compare persistence. **Why it matters:** High-ticket consideration happens over days, often collective (WhatsApp huddle). **Evidence:** `AUTH-01 P2` split two textboxes `page-analysis.md:192-195` + phone-only OTP; `AUTH-02 P2` guest wishlist/compare empty `page-analysis.md:167-171` `issue-register.md:40` no inline `Saved for now — log in` prompt; `personalization-current-state.md:13,9` persistence AUTH required.

## Consistency & Interaction Design
**Problem summary.** Fragments add load. **Affected:** Learnability across 101 PDPs sharing shell with variations. **Why it matters:** Shifting layouts increase hunting cost per category. **Evidence:** `PDP-04 P2` tab set shifts (Mixer omits `Feature` `product-page-variations.md:57`); `PDP-05 P2` Special Component legend; `CONSISTENCY-01 P3` EMI badge `EMI36` vs text `Avail Bank EMI` `page-analysis.md:114-117` vs `issue-register.md:44`; `pdp-tabs` inconsistent.

---

# 5. Strategic Opportunity Areas

Organized per Phase 3 clusters, validated in Phase 4. Each entry: user problem → opportunity + why it matters + strategic relevance (not a feature dump).

## Product Discovery — Fix foundations so browse succeeds
- **Problem:** Browse dead-ends + heavy homepage + no trail. **Opportunity:** Repair `/undefined` guard (P0 hotfix), canonical + orphan remediation, re-layer SEO below pagination with `30-sec guide` CTA, resurrect browse with `Recently Viewed` rail + `Continue shopping: Smart TV Samsung 55"+ 1–2L (14) → Continue` deep-link that restores filters (OPP-02). **Why matter:** Browse is default for appliance consideration; memory is cheapest retention. **Strategic:** Enables every later finder/compare without new backend.

## Product Research — Turn search from typing into finding
- **Problem:** Journey A exact-model `FTKL12TV16WD` has no fast-path; placeholder generic; typos `FTLK` dead-end. **Opportunity:** Staged intelligent search: Stage1 debounced 150ms `Product (+price/badge)/Brand/Category/SKU-exact (3+ alnum ranks SKU)` + Recent 6 → Stage2 affinity-biased ranking after OPP-02 volume; plus zero-result `Did-you-mean + Remove Brand →12 + Related + Try AC Finder` with synonym table & Bangla digit mapping (OPP-07/08). **Why matter:** Shortest path for direct intent; typo resilience for alphanum codes photographed in store. **Strategic:** Hygiene P0 before personalization; brackets Journey A failure path.

## Decision Support — Translate life need → spec
- **Problem:** Buyer must self-translate sq ft, family, distance, TDS. **Opportunity:** Guided Selling framework `Need→Constraints→Budget/Preference → filtered PLP + PDP chip ✓ Fits your 120 sq ft — 1.5 Ton` — AC lens first (sq ft×height/top-floor/EER→tonnage), Fridge bag ladder `18L=1 bag` + 7-step measure guard (`W×H×D+gap+swing` shared with media/install), TV distance→size, Washer kg→front/top (OPP-04). **Why matter:** Differentiator vs Daraz marketplace (requires rule governance Coolblue-grade); reduces wrong-size returns. **Strategic:** One wizard + governed rule tables validated per brand sheet, not ML.

## Product Detail Experience — Make inspection + total cost visible at price exposure
- **Problems:** Static PDP generic gallery, hidden ownership cost, no sibling navigation. **Opportunities:** Rich Media suite zoom/pinch+count first → functional video per template 15–25s → dimension overlay `W×H×D+gap+swing` (OPP-10); Variant Family chips `55" — Tk79,900 In stock | 65" +Tk18k` (OPP-13) re-validating delivery/energy/EMI on switch; Spec jargon decoder tap-to-explain `EER 3.15 = ~1.1kW → ~Tk Y/mo` + warranty legend (OPP-11, content-only prerequisite). **Why matter:** Remote inspection without store visit; total-ownership clarity. **Strategic:** Single `W×H×D` normalisation feeds media + checker + finder.

## Personalization — Memory before magic
- **Problem:** No history-driven continuity for returning research (Journey F wholly unserved DISC-02 P1). **Opportunities:** Foundation `Recently Viewed + Continue` (OPP-02 localStorage, no backend) + Recent Searches (OPP-07 Stage2) + behavior-aware recommendations `Because you viewed` (generic `Best Deals/Latest/Related` `product-discovery.md:98-107` → browsing-aware re-ranking) — mature only after hygiene proof. **Why matter:** Spare returner value with localStorage only (defer scorer). **Strategic:** PLP behaviour before homepage affinity reorder (OPP-15 experiment) — 80% value via rails.

## Customer Retention — Price watch without phantom
- **Problem:** Wishlist inert as guest + `Get Stock Alert` on Dell `Currently Unavailable` with no ETA FEEDBACK-02. **Opportunity:** Wishlist-gated Price-Drop & Back-in-Stock intelligence with explicit timeline `Restocking 2–3 weeks — or show in-stock alternatives` (OPP-06) after wishlist persistence + PDP-07 social proof prove AUTH volume. **Why matter:** Captures dormant demand that would go to competitor; measurable CTR. **Strategic:** Deferred to P2 — auth-gated, needs price history + stock ETA feed + consent vs 14-day/exchange immediate ROI.

## Post-Purchase — Fulfillment as promise not surprise
- **Problems:** Delivery gated, install opaque, plural payment missing, doorstep anxiety for COD 75–90%, hotline only footer. **Opportunities:** Pincode-first estimator `serviceability+SLA+fee+free-install flag+pickup alt` + Fast Delivery badge (OPP-01) shared source for True Cost ownership row `Upfront+Delivery+Install+Energy → EMI/mo` with tenure picker + ineligibility verdict + offline 7–10d truth (OPP-09, Pickaboo/Daraz `regional-commerce.md:52-64`) + Installation checker → priced basket SKU (OPP-12 Gate1) + Authenticity `✓ Authorized` (NEW-01) + Open-Box OTP badge→opt-in (NEW-02) + Plural `COD+bKash/Nagad+Card-on-Delivery+Online` row (NEW-03) + Hotline-sticky+WhatsApp deep-link + Schedule Visit (NEW-04/05) + 14-Day Return badge + cross-category AI Exchange (NEW-07) + Cart Drawer landed-cost breakdown + stepper + toast (NEW-06). **Why matter:** Bangladeshi fulfillment is district/area text not GPS; financing needs offline form literacy; human reassurance before cart (ChalDal Premium Care model). **Strategic:** One district→Zone/SLA+fee table wires 7 initiatives — build once.

## Differentiators — Own what marketplace cannot copy with governance
- **Guided Selling rule tables + verdict (vs generic description),** True Cost combined row (no Bangladeshi retailer combines energy+install+EMI yet), and **Installation checker→slot** with owned fleet + Store Locator Mapbox (`page-analysis.md:199-204`) + threshold bundling `Free on 3+` — each requires owned-asset moat, not a marketplace listing boost.

---

# 6. Recommended UX/UI Improvement Scope

> Organized by strategic area A–J per `05-prioritization/unified-ux-scope.md` (25 consolidated initiatives, 34→25 after 6 merges per `initiative-merging.md:15-23`). No dev hour estimates or full specs. Type: FIX / IMPROVEMENT / NEW CAPABILITY. Priority deciders: user impact + pain severity + benchmark maturity (STANDARD vs EMERGING) + shared dependencies (7 tables).

## A. Foundation & Core UX

### INV-01 Fix Browse Paths Terminating at /undefined
- **Priority:** **P0** | **Type:** FIX | **Problem:** 11× See All dead-ends `page-analysis.md:56-57` `/undefined` `/samsung/undefined` blocks browse for Journeys B/C (Phase 2 P0).
- **Direction:** Guard slug generation + fallback/redirect for empty slug + CI link audit. Decouple from IA migration. Hotfix.
- **User Impact:** Browse recovers — homepage → PLP no longer 404. **Business:** funnel before PLP metrics begin. **Dependencies:** None (blocks all). **Evidence:** `01-current-state/page-analysis.md:56-57` VERIFIED `02-ux-audit/issue-register.md:7` P0 HIGH.

### INV-C01 IA Hygiene (Canonical / Orphan / Tile / Hyphen)
- **Priority:** **P1** | **Type:** FIX | **Problem:** Flat 101 PDPs `sitemap-analysis.md:27` sever hierarchy; `/tv-av` orphan `sitemap-analysis.md:74-76`; Brand vs `/search?Brand=samsung` duplicate; Dishwashers tile mismatch; 4 trailing-hyphen slugs.
- **Direction:** Ship 3 LOW fixes now: canonical brand→PLP (brand authoritative), `/tv-av` landing, sanitize 4 slugs + 301 + tile→category fix. **DEFER** hierarchical PDP URL migration (VERY HIGH) per `05-prioritization/decision-log.md`.
- **User Impact:** Shareable, crawl-coherent URLs. **Business:** SEO + share + history coherence. **Dependencies:** INV-01 first. **Evidence:** `00-input/sitemap-analysis.md:27,74-76,131` `02-ux-audit/issue-register.md:8-12,16`.

### INV-C04 Spec Jargon Decoder & Warranty Truth (part A here, also D)
- **Priority:** P0 warranty truth + P1 decoder | **Type:** FIX + NEW — **Problem:** `Parts-0M/Motor-300M` implausible + EER/R32 opaque `product-page-variations.md:61` `issue-register.md:30` PDP-05 P2; spec buried.
- **Direction:** P0: normalise warranty legend `Service/Parts/Compressor|Panel|Motor + 5 years`. P1: glossary CMS 8–10 terms tap `EER 3.15 = 1.1kW → Tk Y/mo` (Bangladesh tariff) + warranty legend row. Content-only, prerequisite for finders.
- **User Impact:** Decode without Googling; warranty trust. **Dependencies:** Term bank + tariff. **Evidence:** `product-detail-experience.md:12` BrowserOS click reveals spec rows but no glossary.

## B. Navigation & Product Discovery

### INV-04 SEO Wall Re-layer
- **Priority:** **P1** | **Type:** IMPROVEMENT — **Problem:** IA-03 1,500-word guide pushes grid below fold `page-analysis.md:90-91` (category L1/L2).
- **Direction:** Move long-form to collapsible `Buying Guide` below pagination + PLP CTA `Not sure? 30-sec guide → finder` per Currys/Coolblue patternLibrary Problem 2. Preserve SEO.
- **Impact:** Grid above fold; guide still accessible. **Dependencies:** INV-C02 fixed. **Evidence:** IA-03 P1, pattern `buying-guides` hub.

### INV-06 Homepage Curated Prioritization
- **Priority:** **P2** (deferred experiment) | **Type:** IMPROVEMENT — **Problem:** `DISC-01 P1` 7+ serial grids `page-analysis.md:48-54` overload.
- **Direction:** Budget-only cull now (category nav + single hero + one curated carousel); DEFER returner affinity reorder to A/B `Rail only vs Rail+hero reweight` requiring modular CMS+scorer (`applicability-review.md:128-135` QUESTIONED OPP-15). Suppress low-ticket.
- **Impact:** Scannable first-timer; 80% returner via INV-22 rail. **Dependencies:** CMS modularity audit; INV-22 proof.

### INV-22 Browse Resumption: Recently Viewed & Continue Shopping
- **Priority:** **P0** | **Type:** NEW — **Problem:** Journey F wholly unserved DISC-02 P1 `personalization-current-state.md:9-10` empty cart/wishlist no history.
- **Direction:** Anonymous `localStorage viewHistory(8) + lastPlpUrl (filter state)` → rails on homepage/PLP/PDP + empty-cart injection + auth migration on OTP 0157… Deep-link restores `Brand+Display Size+Price` state. Cap 8.
- **Impact:** One-tap resume with facet state; cheapest retention. **Dependencies:** Event instrumentation; LOW; **Validates** STANDARD (Amazon Pick up where you left off, eBay, Zalando) `04-benchmark/pattern-library.md:108-116`.

## C. Search & Filtering

### INV-C02 PLP Browse Controls (Chips / Sort / Facet Hygiene)
- **Priority:** **P0** | **Type:** FIX — **Problem:** No chips (`FILTER-01 P1 MEDIUM` no `filterCount` chips `page-analysis.md:75-82`), `Select Sort Option` placeholder `sortOptions:[]` `SORT-01 P1 HIGH`, pagination `Show 12 <of 1> 1` ambiguous `SORT-02`, `Customer Review` empty, price slider+buckets compete `FILTER-03`, `Display Size` vs `Screen` duplication `FILTER-04`.
- **Direction:** Chip row `X filters applied` + `Clear all` above grid; merge Size facet; bucket presets drive slider; sort becomes `Relevance/Price low→high/high→low/Newest/Discount`; pagination `Showing 1–12 of 45 — Show [12|24|48]`.
- **Impact:** System status visible; sorting anticipated; depth understood. **Dependencies:** PLP header wiring; suppress empty facet.

### INV-C03 Intelligent Search & Recovery
- **Priority:** P0 Stage1 + P1 Stage2/Recovery | **Type:** NEW — **Problem:** `Search Here` placeholder generic `SEARCH-02 P3` `page-analysis.md:9`; suggestions NOT FULLY VERIFIED `user-journeys.md`; `FTKL12TV16WD` no fast-path; typos dead-end.
- **Direction:** P0 Stage1: debounced 150ms dropdown `Product (+price/badge)/Brand/Category/SKU-exact (3+ alnum ranks SKU)` + Recent 6; P1 Stage2 affinity-biased after INV-22; P1b Zero-result `Did-you-mean + Remove Brand →12 + Related + Try AC Finder` with synonym table & Bangla digit mapping.
- **Impact:** Exact-code fast-path; typo-resilient; recent one-tap. **Dependencies:** Index + `searchHistory` store (shares INV-22); verify empty dropdown is missing index vs bug.

## D. Product Research & Decision Support

### INV-23 Smart Compare Workspace
- **Priority:** **P1** | **Type:** NEW — **Problem:** `/compare` 3× hand-typed `Model name or part…` `page-analysis.md:173-178` `issue-register.md:41` INTERACTION-01 P1 recall task.
- **Direction:** Sticky bar `Compare (2/3)` → auto-populated `/compare` + `Highlight differences` → decisive rows tinted + total-cost pin `price+install+1yr energy+EMI/mo` + share URL with OG preview (WhatsApp huddle). Spec decisive-row normalisation limited to 6–8 rows.
- **Impact:** Shortlist without typing; verdict + cheaper-to-own pin. **Dependencies:** `compareQueue` (INV-22 store) + feeds INV-13/14 + Family Graph; **VALIDATED** Coolblue/Best Buy/RTINGS STANDARD.

### INV-24 Guided Selling Framework
- **Priority:** P1 AC lens → P2 Fridge/TV/Washer | **Type:** NEW — **Problem:** Life need→spec self-translation; SEO wall generic.
- **Direction:** One wizard `Need→Constraints→Budget/Preference → filtered PLP + PDP chip ✓ Fits your 120 sq ft — 1.5 Ton`. Lenses: **P1 AC** (sq ft×height/top-floor→tonnage 20 BTU/sq ft LG few SKUs, `Choose Ton` proof), **P2 Fridge** (litres→family + bag ladder 18L=1 bag + 7-step guard `W×H×D+gap+swing` shared with INV-10/12), TV (distance→size→panel), Washer (kg→front/top). REMOVE Kitchen/Purifier lens (7 PDPs thin `opportunity-pool.md:67`).
- **Impact:** Reduces wrong-size returns; converts problem-aware. **Business:** Differentiator vs Daraz (rule governance). **Dependencies:** Rule tables per lens + INV-C04 glossary. **ENHANCED** Coolblue choose-your-tv-size.

## E. Product Detail Experience

### INV-12 Rich Media Suite
- **Priority:** P0 zoom → P1 video/overlay → LATER 360/AR | **Type:** NEW — **Problem:** `PDP-01 P1` no video/zoom 4+ generics `page-analysis.md:134-135` 68 DOM images VIDEO NOT OBSERVED `ecommerce-capabilities.md:30`.
- **Direction:** P0 hover-zoom desktop/pinch mobile + `1/7` count + scrub. P1 short functional video per template 15–25s muted lazy (reuse Samsung/Haier reels). LATER 360° where asset + dimension overlay `W×H×D+gap+swing` from structured spec; AR phase 3.
- **Impact:** Fit/finish without store visit. **Dependencies:** Asset pipeline + spec W×H×D normalisation. **STANDARD** Apple hover/dimension.

### INV-17 Variant & Family Navigator
- **Priority:** **P1** | **Type:** NEW — **Problem:** `PDP-08 P2` only AC has `Choose Ton` `page-analysis.md:120-121` TV/Washer no sibling despite `Display Size 55"(10)` facet proof `page-analysis.md:86` + flat PDP severs family.
- **Direction:** Family graph `model_root → variants` as chips `55" — Tk79,900 In stock | 65" +Tk18,000 | 75" Currently Unavailable` + `Get Stock Alert`; re-validates delivery/energy/EMI on switch.
- **Impact:** Explore vault without PLP loop; top 30 roots 70% high-ticket. **Dependencies:** Family modeling; price/stock feed.

### INV-C04 full glossary (also A) completes E.

## F. Cart & Checkout

### INV-C06 Cart Drawer & Feedback System
- **Priority:** **P0** | **Type:** FIX+NEW — **Problem:** `FEEDBACK-01/CART-01/CHECKOUT-01` P1 cluster: no toast, `Subtotal ৳0 Total 0` dead-end `page-analysis.md:159-164`, checkout black box `user-journeys.md:122-148` NOT ACCESSIBLE.
- **Direction:** Slide-in mini-cart on Add confirmation; Cart `Order Summary` becomes `Subtotal+Delivery+Install→Total` with `Free Installation vs TkX` explicit (reuses INV-13/14 tables); `Cart→Delivery→Payment→Confirm` stepper + trust micro-copy; toast on every add/wishlist/compare. `Terms & Conditions` + `Continue Shopping` CTA for CART-01.
- **Impact:** Paywall surprise eliminated; status visible. **Dependencies:** INV-13/14 fee/SLA tables; **STANDARD** Apple/ASOS/Best Buy drawer+stepper.

### INV-13 Delivery & Serviceability Estimator
- **Priority:** **P0** | **Type:** NEW — **Problem:** `Enable your Location` gate hides fee/SLA `page-analysis.md:125` `issue-register.md:27` PDP-02 P1; `ecommerce-capabilities.md:42-44` gated; district/area text > GPS per `regional-commerce.md:77-86`.
- **Direction:** District/area text input (not GPS) → `serviceability yes/no, SLA, fee, free-install flag, pickup alt + distance`; propagate to Cart; earned `Fast Delivery` PLP badge/filter (1C) on `Show 12` header; suppress low-ticket BDT 5k. Single table built once.
- **Impact:** Landed-cost confidence at price exposure; store alternative. **Dependencies:** District→Zone/SLA master + delivery fee + install fee + store inventory.

### INV-14 True Cost & EMI Planner
- **Priority:** P0 static row → P1 interactive | **Type:** NEW — **Problem:** Sticker illusion; EMI inconsistent Haier 622L absent `product-page-variations.md:55` `issue-register.md:31` PDP-06; energy hidden `EER 3.15` token.
- **Direction:** Unified row `Upfront × + Install + Energy ~Tk/mo (1yr/5yr) → EMI from Tk/month × bank/tenure` with picker 3/6/12/24/36 + tariff/running-hours slider + explicit ineligibility `→ EMI Bank List` + offline form truth (blocked→signed form 3d → bank converts 5–10d). Cart inherits breakdown. Suppress <BDT5k.
- **Impact:** Affordability verdict at decision moment. **Business:** Captures EMI-sensitive 50k–1.5L. **Dependencies:** INV-13 + INV-C04 + EMI master (32 banks, BDT5k/10k thresholds `regional-commerce.md:52-64`) — **ENHANCED** Pickaboo/Daraz truth.

## G. Trust, Delivery & Post-Purchase

### INV-21 Authenticity / Authorized-Retailer Badging
- **Priority:** **P0** | **Type:** NEW — **Problem:** `TRUST-01 P2` `page-analysis.md:34` Original Product homepage-only vs PDP generic `page-analysis.md:112`.
- **Direction:** PDP hero lockup `✓ Authorized — Official Warranty` + warranty detail sheet + Mall/flagship tag at price context; echoes `Original Product Guaranteed` as proof. Reuses 13 brand authorizations `sitemap-analysis.md:26` moat vs Daraz.
- **Impact:** Post-Evaly #1 barrier resolved with no backend. **Dependencies:** Brand assets; companion to INV-20 ratings.

### INV-20 Social Proof Pipeline
- **Priority:** P1 after pilot (deferred per critique) | **Type:** NEW — **Problem:** Review tabs exist `page-analysis.md:131-133` but no aggregate stars/count `ecommerce-capabilities.md:31-33` NOT OBSERVED; `Customer Review` facet empty.
- **Direction:** Pipeline `Collection (post-delivery SMS prompt+verified-purchase) → Moderation → Aggregation (suppressed n<5 → Be first — ask Q) → PDP header badge near price + PLP card 4.6★(212) + facet ★★★★&up(n) + Q&A verified marker`.
- **Impact:** Peer validation for Tk80k+; turns broken facet into decision facet. **Dependencies:** Collection/moderation VERY HIGH until pilot proves supply — defer full scale after 1-cat pilot.

### INV-28 Open-Box Delivery + OTP Doorstep Verification
- **Priority:** P1 badge → P2 OTP | **Type:** NEW — **Problem:** 600L/65" doorstep anxiety for COD 75–90% Levree.
- **Direction:** Badge `Eligible for Open Box Delivery at your pincode ✓` (reuses INV-13 eligibility) now; opt-in at Order Summary `open outer+brand packing, check damage/correct/IMEI, OTP only after satisfaction, photo+reference logged` after ops confirmation.
- **Impact:** Handover proven; dispute reduced; owned fleet differentiator vs marketplace. **Dependencies:** INV-13 eligibility; rider protocol.

### INV-16 Installation Feasibility & Slot Booking
- **Priority:** P1 Gate1 → LATER Gate2 | **Type:** NEW — **Problem:** No feasibility (wall/drain/socket/gap) before ordering `product-page-variations.md:60` NOT OBSERVED PDP-03 P1.
- **Direction:** Gate1 (P1 content): per-SKU checklist + verdict `✓ Feasible / ⚠ Requires bracket Tk2,500` + fee table. Gate1b priced basket SKU `Add Installation + Recycling` (£115 model John Lewis). Gate2 (LATER ops-gated): calendar by district/team + prereqs + order↔service link + reschedule via `Track Your Service` `page-analysis.md:7` + push. Gate2 after slot-capacity feed confirmed `cross-review.md:175`.
- **Impact:** Failed-install waste eliminated. **Dependencies:** SKU install table + W×H×D + feed; **DIFFERENTIATOR** owned Fleet.

### INV-33 Exchange & 14-Day Return
- **Priority:** P2 static → LATER AI | **Type:** NEW — **Problem:** Exchange hub `/exchange` existing but opaque `ecommerce-capabilities.md:52` NOT TESTED; homepage `Exchange Program` not echoed PDP; baseline shifting to 14-day (Daraz Aug 2025).
- **Direction:** PDP badge `14-Day Hassle-Free Return ✓` + `Exchange value up to Tk12k → doorstep inspection → OTP` cross-category (+bag/guard feed from INV-24 lens) — static inspection truth first; AI diagnostics 26-cat 10-step cross-category after ops.
- **Impact:** Idle second fridge as currency; baseline expected after Daraz move. **Dependencies:** Valuation feed.

## H. Account & Customer Retention

### INV-C05 Human Support Spine (WhatsApp/Messenger + Hotline-Sticky + Schedule Visit)
- **Priority:** P0 sticky hotline + P1 WhatsApp | **Type:** NEW — **Problem:** `Need help? Click Here` not conversational; footer-only 16212 9AM–9PM `page-analysis.md:18-19`; PDP `Share` lacks WhatsApp; collective purchase.
- **Direction:** Sticky 16212 call bar on PDP/Cart + 3-store stock + `Schedule your visit` linkage to existing Mapbox Store Locator `page-analysis.md:199-204` (wire, not rebuild). PDP `Share via WhatsApp — Ask agent about this fridge` deep-link + hotline fallback; premium manager for >Tk50k deferred (ChalDal Premium Care 24h model).
- **Impact:** Human reassurance for high-ticket before cart. **Dependencies:** Store inventory from INV-13; LOW.

### INV-32 Authentication UX
- **Priority:** **P1** | **Type:** FIX — **Problem:** `AUTH-01 P2` split two textboxes + phone-only `page-analysis.md:192-195` `issue-register.md:39`; `AUTH-02 P2` guest inert `issue-register.md:40`.
- **Direction:** Single tel `+880` mask + format hint `autocomplete=tel` replacing two textboxes; guest tap → toast `Saved for now — log in to keep across devices` + Log In; localStorage→account migration on OTP.
- **Impact:** Save persists across devices; friction at cart/wishlist eased. **Dependencies:** INV-22 store.

### INV-22 also retention — listed in B.

## I. Personalization

### INV-06-advanced & INV-15 Affinity Homepage Reorder (deferred experiment)
- **Priority:** **P2 EXPERIMENT** | **Type:** NEW — **Problem:** Returner sees same 7 grids as first-timer; PLP order identical (OPP-15 QUESTIONED `applicability-review.md:128-135`).
- **Direction:** Do not build before rails: ship INV-22 rail + INV-C03 Recent first; then A/B `Rail only vs Rail+hero reweight` requiring modular CMS+scorer+governance. PLP affinity chips `Your size:55"` rank earlier as low-cost tweak.
- **Impact:** 80% returner value via localStorage already; scorer needs proof.

### Behavioral ranking Stage2 of INV-C03 is the sole behavioral layer.

## J. New Differentiators & Growth (Bundles)

### INV-25 Complete-the-Setup Bundles & Consumable Attach
- **Priority:** **P2 pilot** | **Type:** NEW — **Problem:** Thin single Related `product-page-variations.md:65-66` FBT NOT OBSERVED `ecommerce-capabilities.md:56`.
- **Direction:** Curated attach rule per family (AC→stabilizer/bracket, TV→mount/soundbar) as PDP bundle row + Cart grouping. Suppress low-ticket; purifier cartridge cadence phase2. Pilot over full catalog FBT.
- **Impact:** One-trip ownership; recurring convenience. **Dependencies:** Family→attach mapping (shared Family Graph).

---

# 7. Personalization Strategy

Maturity is staged — no advanced without foundations (`05-prioritization/decision-log.md`, `cross-review.md:168` suppress low-ticket / BDT5k).

## Foundation — No backend, anonymous durable, immediate

**Only validated P0 foundations** (INDUSTRY STANDARD Amazon Pick up where you left off, eBay):

- **Recently Viewed (INV-22 rail).** *Signal:* `PDP view` (productId, category, price) over session + 30d. *Trigger:* second PDP view or Return to homepage/PLP. *Experience:* `Recently viewed (8)` horizontal rail on homepage, PLP sidebar, PDP footer + empty-cart injection. *Value:* User — resume without re-navigation; Business — recaptures multi-session high-consideration (Journey F). *Dependencies:* `localStorage viewHistory` + anonymous persistence; auth migration later (`INV-32`).

- **Continue Shopping — Last Filtered PLP/Search (INV-22 deep-link).** *Signal:* `PLP filter apply` (`Brand Samsung + Display Size 55" + Price 1–2L`) + `searchHistory`. *Trigger:* return to homepage after filtered PLP. *Experience:* `Continue where you left off — Smart TV: Samsung 55"+, 1–2L (14) → Continue` restores filters. *Value:* Restores intent state, not just item. *Dependencies:* `lastPlpUrl` (filter query string) + `searchHistory` (shares store with INV-C03).

- **Recent Searches (INV-C03 Stage1 Recent chip row).** *Signal:* typed search string. *Trigger:* focus `Search Here` input. *Experience:* chip row `Recent: samsung 55" | daikin 1 ton | h55p7ux` (6) + debounced dropdown `Product/Brand/Category/SKU-exact`. *Value:* One-tap recent for collective decision; shortens Journey A. *Dependencies:* `searchHistory` store (shares INV-22); no model inference.

**Why foundation first:** Cheapest retention (localStorage only) + 80% of returner value without scorer/CMS; deferred affinity needs proof.

## Behavioral — History-ranked, still on-device, modest backend

- **Behavior-aware recommendations — `Because you viewed` (generic `Best Deals/Latest/Related` → browsing-aware re-ranking).** *Signal:* `viewHistory` category affinity (e.g., viewed Samsung TV + AC 1.5T 3 sessions). *Trigger:* return to homepage/PLP/PDP. *Experience:* `Because you viewed Samsung TVs` re-ranked shelf (not new shelf) — same `Best Deals` positions, affinity-biased order + social proximity via share URL (family huddle WhatsApp). *Value:* Relevance lift without personal data lake. *Dependencies:* Affinity scorer on `viewHistory` (view-count per category/brand); no collaborative filtering required.

- **Personalized Search Stage2 — affinity-biased ranking (INV-C03 Stage2).** *Signal:* accumulated affinity (`Samsung 55"` bias). *Trigger:* type `sams` after viewing Samsung TV. *Experience:* Samsung suggestions ranked up + `Your size: 55"` chip rank within category. *Value:* Direct intent shortens `type→tap→PDP`. *Dependencies:* Volume of `viewHistory` after Stage1; deferred until 1k active histories prove signal quality per `applicability-review.md:22-152`.

- **Cart-context complementary — `Complete your setup` trigger (INV-25 tail behavioural).** *Signal:* cart contains `Samsung 55"`. *Trigger:* Add to cart. *Experience:* Cart rail `Complete your setup: Add mount → Save` (PDP bundle row also). *Value:* Contextual cross-sell with purchase intent. *Dependencies:* `Family→attach` rule table (familial, not behavioural ML).

**Why behavioral second:** Requires accumulated view history volume; still on-device affinity, not collaborative filtering.

## Advanced — Lifecycle, contextual, scorer + auth

- **Lifecycle price/stock nudges (INV-33 head + OPP-06 wishlist intelligence) — Deferred P2.** *Signal:* `wishlist.add` + `savedPrice vs current` + stock ETA feed + consent. *Trigger:* price drop % or back-in-stock + explicit `Restocking 2–3 weeks — or show in-stock alternatives` timeline vs perpetual waitlist. *Experience:* On-site banner + email/SMS `Your saved 55" dropped 5% → See`. Sparkline phase2. *Value:* Monitors high-ticket without daily checking; measurable CTR. *Dependencies:* VERY HIGH `02-ux-audit` zero reviews + auth-gated wishlist persistence `ecommerce-capabilities.md:38,54` + price history + stock ETA feed + consent — deferred until wishlist persistence + INV-20 social proof prove auth value.

- **Category-Affinity Homepage & PLP Prioritization — Full reorder (INV-06 advanced, OPP-15).** *Signal:* affinity scorer `viewCount per category/brand` over sessions. *Trigger:* return visit with confident `affinity == AC`. *Experience:* Returner module reorder + hero reweighted to affinity category vs first-timer orientation `Shop By Category + single hero`. *Value:* Continuity for returning researcher; uncluttered for first-timer. *Dependencies:* **VERY HIGH** modular CMS + affinity scorer + A/B + campaign-pin governance. **EXPERIMENT** A/B `Rail only vs Rail+hero reweight` before commit per `05-prioritization/decision-log.md`.

- **Contextual / Seasonal — Removed as opportunity.** Seasonal `Prepare for summer: Inverter ACs in your viewed range` (`personalization.md:356`) fails True Personalization test (`personalization.md:30-33`) — calendar + broad affinity = campaign segmentation, not signal-driven personalization. Kept as campaign optimisation, not capability.

**Dependencies narrative:** Foundation (`localStorage` viewHistory/lastPlpUrl/compareQueue/searchHistory) → Behavioral (affinity scorer) → Advanced (auth history + price/stock feeds + CMS). Never invert.

---

# 8. Electronics & Appliance Decision Support Strategy

> Appliances are not `Add — Checkout` commodities. Wrong tonnage (1 vs 1.5 vs 2 Ton) or litres (245L vs 600L), distance vs panel size, or drain/socket site mismatch creates Tk10–50k value error + return/service cost. Strategy distinguishes Berger "Help Me Choose" from mere listing.

**Why more than standard listings.** Bangladesh flat PDPs (`sitemap-analysis.md:27` 101 at `/`) + SEO wall generic text (`page-analysis.md:90-91`) force self-translation. BrowserOS click revealed `Specification: Refrigerant R32 / EER 3.15 / Applicable For 120 sq ft` only after tab, with no glossary; warranty `Special 60M` opaque. Feedback loops are expensive (600L door swing 5cm, AC outdoor wall/bracket).

## Help Me Choose — Guided Selling Wizard (INV-24)

**Customer problem:** "I need X for Y life situation" without spec literacy (CBC's `I need AC for 120 sq ft`). **Direction:** One wizard `Need→Constraints→Budget/Preference → filtered PLP + PDP chip ✓ Fits your X — Y`. **Applicable categories:** *All high-ticket finders share same wizard + filtered PLP mapping* — shippable lenses: **AC** (ROOM-SIZE & THERMAL FINDER `EDS-01`) `sq ft × height × top-floor/sun exposure × occupancy → BTU (20/sq ft) → tonnage + EER` (LG pattern), **Fridge CAPACITY & SPACE VALIDATOR** (`EDS-02`) `family size → litres + door (single/double/Triple/Side-by-Side 200–850L) + niche H/W/D + 90° hinge 5cm + ventilation 1–2cm + water proximity` (AO bag ladder + Currys 7-step), **TV SIZE–DISTANCE–RESOLUTION ADVISOR** (`EDS-03`) `distance → diagonal → resolution + panel HQLED vs QLED explainer + Dolby row`, **Washer CAPACITY & LOAD ADVISOR** (`EDS-04`) `kg (100–350L analogy: 6kg→2, 7kg→3–4) → front/top + Eco 40–60`. *Kitchen/Purifier lens suppressed — 7 PDPs thin.* **Scenario:** Mother for 4 (2 adults+2 kids) → 250–350L fridge, side-by-side preferred but doorway 70cm → guard suggests 2-door `No-Frost Top Mount` with tap-to-explain EER vs Inverter fluctuation saving `Tk Y/mo`. **Value:** Right spec first time; PLP pre-filtered; PDP verdict closes loop.

## Product Comparison — Smart, not hand-typed

**Customer problem:** `D802HVOS 8.5/5kg vs HW80 8KG vs HWM80 8KG` specs differ subtly. **Direction:** Sticky bar `Compare (2/3)` + auto-populated `/compare` + `Highlight differences` tinting only decisive rows per category (AC `EER/tonnage/R32/Applicable sq ft + Applicable For height`, TV `panel/HDR/size`, Fridge `litres/door/inverter + Twin inverter`, Washer `RPM/front-load/Eco`) + total-cost pin `price+install+1yr energy+EMI/mo` + share URL (WhatsApp huddle). **Applicable:** TV (`RTINGS`-style scored 10M+ buyer pattern), fridge, AC, washer (decisive rows). **Scenario:** Choose between two 55" TVs — decisive panel/HDR row green-tinted winner, total-cost pin shows Samsung cheaper-to-own despite higher upfront.

## Specification Understanding — Jargon becomes Tk/month

**Customer problem:** `EER 3.15 / R32 / HQLED / Twin inverter / Coanda airflow / Special 60M` tokens without meaning. **Direction:** `TAP-TO-EXPLAIN` glossary CMS 8–10 high-frequency terms per category on PDP → `EER 3.15 = 1.1kW draw → ~Tk Y/mo @8h/day @Tk Z/kWh (Bangladesh tariff)`; refrigerant class; panel class; compressor vs panel vs motor vs `Special Component = X` warranty legend humanised `60M = 5 years`. **Applicable:** All PDPs (8 samples show 4-bullet brevity shifting per cat `product-page-variations.md:52,57`). **Scenario:** Tap `EER` in spec table → drawer shows consumption + monthly Tk plus year-1 ownership. Same formula feeds True Cost.

## Use-Case Matching — Budget without literacy loss

**Customer problem:** Budget-constrained buyer sees savings % `Save 7,295 -5%` but not monthly affordability. **Direction:** True Cost EMI row per INV-14 (see §6 G). Finder already matches use-case; decoder glossary makes match explainable. **Applicable:** All EMI-eligible ≥BDT5k.

## Capacity & Compatibility — Measure once, deliver right

**Customer problem:** 600L side-by-side needs 50mm side gap + floor strength + door swing 90° to 180°; vacuum vs purifier compatibility not stated. **Direction:** (Fridge/AC/WM lenses above) + **Site Compatibility Checker** (INV-16 Gate1) `outdoor wall / bracket / drain / 3-pin within 1m / 4-hour stand / 90° hinge 5cm`. **Applicable:** AC (outdoor wall/drain), Fridge (ventilation/floor/swing), Washer (inlet/drain/floor level), TV (wall mount VESA). **Scenario:** PDP checker verdict `⚠ Requires bracket Tk 2,500 — order bundle (INV-25) or fetch at store`.

## Installation & Ownership — Price is not delivered-cost

**Customer problem:** PDP shows install as vague `Free Installation Selective Items` vs actual. **Direction:** Installation as **priced basket SKU** `Add Installation + Add Recycling (haul away)` with fee table `Free/Paid + Tk` (John Lewis £115 / £25 model) + `Before You Buy / Before We Deliver` checklist+video (Coolblue Eigen Plan) → bookable slot calendar by district/installer team + reschedule via `Track Your Service` only after slot-capacity feed confirmed (Gate2). True Cost ownership row adds energy `149kWh/yr → Tk39/yr` (AO) + install + delivery → total. **Applicable:** AC, fridge, washer (large), TV (mount), purifier cartridge cadence. **Scenario:** PDP `Upfront × + Install Tk0 (free) + Energy ~Tk/mo → EMI Tk Y/mo × 36 (bank B)` with eligibility verdict `EMI not available → see EMI Bank List` avoids PDP-06 silence.

*Do not force every category into every feature:* personal-care trimmer (Tk3k flat `BT1235`, `Special 0M` blades) suppresses EMI row, energy row, checker, FBT, install bundle per BDT5k + low-ticket suppress rule.

---

# 9. Market & Competitive Insights

> Organized by PROBLEM (not competitor list), per `04-benchmark/pattern-library.md` 12 groups × 38 reusable variations. Each: observed approaches → strategic lesson → applicability. Classify: INDUSTRY STANDARD / EMERGING / DIFFERENTIATOR.

## Reducing Delivery & Affordability Uncertainty
**Observed approaches:** (1) Pincode/district serviceability input before PDP gate (Amazon.in 19k pincodes/India Post 1.6L offices, Flipkart, Daraz Fast Delivery 50k SKUs earned-badge Aug 2026 — STANDARD South Asia, EMERGING BD; 1A district text); (2) Landed-cost truth row `Subtotal+Delivery+Install→Total` with `Fast Delivery` badge alongside `EMI36` on PLP header `Show 12` (1C); (3) True monthly row `Price+Install+Energy (kWh×rate) → EMI/mo` with tenure/bank picker + ineligibility verdict (5B Pickaboo 32 banks 0% 36m BDT5k, Daraz form 7–10d). **Strategic lesson:** Pincode text beats `Enable your Location` GPS gate in BD (sparse formal pincodes/mauzas, low permission trust `regional-commerce.md:77-86`). One district→Zone/SLA+fee+install+store table (INV-13) feeds 7 initiatives — build once. **Applicability:** **HIGH** — unblocks all 50k–1.5L; one row fixes sticker illusion + install gate + plural payment truth.

## Reducing Requirement Translation (Room → Spec)
**Observed approaches:** (1) Buying-guide hub + PLP finder entry `Not sure? 30-sec guide` (Currys/Cooolblue); (2) AC BTU calculator 20/sq ft (LG) + Home Comfort; (3) Fridge `18L=1 bag` ladder + 7-step measure guard (AO/Currys) including `W×H×D+gap+swing`; (4) TV distance→size + panel HQLED decoder (Samsung). **Lesson:** SEO wall `page-analysis.md:90-91` IA-03 must live at `/buying-guides/{cat}` + PLP CTA, not above grid — preserves SEO without burying discovery. **Applicability:** **DIFFERENTIATOR** (rule governance vs generic text) — AC→Fridge→TV order; suppress Kitchen/Purifier until evidence thickens. **EMERGING** for combined row, **STANDARD** for advisor entry.

## Reducing Comparison Overhead
**Observed approaches:** (1) Persistent bar `Compare (2/3)` (Coolblue up to 4); (2) `Show only differences` + decisive-attribute tint vs 40 rows (RTINGS `TV tools compare` green winner, Amazon A+ table 8–20% lift); (3) Total-cost pin in comparison (Home Depot tiered protection). **Lesson:** Book `/compare` with 3× hand-typed `Model name or part…` recall task (`page-analysis.md:173-178` P1) is hand-type failure — sticky→auto-populate + decisive tint collapses table to 6–8 rows; share URL + WhatsApp huddle matters for BD collective decision. **Applicability:** **HIGH** Journey D.

## Inspection Without Store
**Observed approaches:** (1) Hover-zoom/pinch + `1/7` scrub (Apple); (2) functional video per template 15–25s muted (Samsung/Dyson); (3) dimension overlay `W×H×D+gap` from structured spec + AR `View TV virtually` (Coolblue) **Lesson:** Generic 68 DOM images + 4 placeholders without zoom is weight without value; zoom first (no reshoot) delivers highest anxiety reduction. **Applicability:** **STANDARD** zoom; **EMERGING** video/AR — phased, asset-gated.

## Trust at Decision Moment
**Observed approaches:** (1) Authenticity proof `✓ Authorized — Official Warranty + Mall/flagship + warranty detail sheet` at price context (DarazMall, Pickaboo 100% genuine 400+ brands) — post-Evaly #1 barrier; (2) PLP/PDP rating `★★★★☆ 4.3 +2,184 Verified Purchase + Q&A` + star facet (Amazon, Best Buy `4.6★ 212`) + Tap-to-explain EER→Tk/mo (Energy Saving Trust A–G+QR fiche, AO); (3) Spec/warranty legend `Special 60M = Compressor`. **Lesson:** Homepage `Original Product Guaranteed` vs PDP generic brand link (TRUST-01 P2) fails at price; homepage trust must be *proved* at PDP/Cart with mechanics, not claimed. **Applicability:** **STANDARD** BD marketplace authenticity + social proof hygiene — together form trust row.

## Human Reassurance & Plural Money
**Observed approaches:** (1) Plural `COD+bKash/Nagad+Card-on-Delivery+Online/EMI` co-equal row `◉` + district-aware `COD available` (Daraz/Pickaboo `Free Shipping, bKash, Card on Delivery, COD`) — Levree 75–90% COD; (2) Open-Box OTP at doorstep `Opt-in → open both packings → check damage/correct/IMEI → OTP+photo log` (Flipkart OBD — STANDARD India/EMERGING BD); (3) WhatsApp/Messenger deep-link + ChalDal Premium Care dedicated agent 24h + hotline-sticky 16212/Schedule Visit (Star Tech 20+ stores). **Lesson:** BD high-ticket = human reassurance before cart + COD plurality excludes majority if card-first PDP. Converters when considered together with OBD-photograph as post-Evaly proof. **Applicability:** **HIGH** — owned fleet vs pure marketplace moat.

## Browse Continuity (Retention)
**Observed approaches:** (1) Recently Viewed rail (8) + Continue Shopping deep-link restoring filters (Amazon Pick up where you left off, eBay Watchlist) — `localStorage viewHistory+lastPlpUrl` still anonymous; (2) Recent Searches chip row (ASOS/John Lewis recent chips) — `searchHistory` share. **Lesson:** Full affinity homepage reorder (scorer+CMS) QUESTIONED `applicability-review.md:128-135` — no P0 pattern validates rewrite before hygiene; `localStorage` rail+deep-link+recent delivers 80% returner value (Journey F) with no backend. **Applicability:** **HIGH** — cheapest validated retention.

## Decision *Pattern* Maturity Map (what to borrow when)

| Pattern | Type | When to borrow for Transcom |
|---|---|---|
| Pincode/district estimator, Recently Viewed, Compare persistent workspace, Variant family chips, PLP badges for ratings, Cart drawer+stepper | **STANDARD** | NOW — hygiene expected since ~2018; absence is conspicuous |
| True Cost ownership row combined, Energy translator kWh→Tk/mo, Zero-result facet-relax count preview, Bundles with cadence | **EMERGING** | NEXT — becoming expected in electronics; differentiates in BD now |
| Guided Selling wizard (Coolblue-grade rule tables + verdict), Installation prereq checker→priced SKU→bookable slot | **DIFFERENTIATOR** | NEXT (wizard) / LATER (slot booking ops-gated) |
| Affinity homepage full reorder | **EXPERIMENTAL** | After P0 rails proven + modular CMS + A/B proof |

*Only insights landing in recommendations (§6). Competitors' names validate pattern, not copy — adaptation per BD district/pincodes, bKash, banga numeral, offline form latency.*

---

# 10. Strategic Prioritization

> Qualitative matrix per `05-prioritization/executative-priority-view.md` and `value-analysis.md` (VERY HIGH/HIGH) vs `feasibility-dependencies.md` (LOW→VERY HIGH) vs Critic. Do not average — reason.

## P0 — Critical (Must address — journey blockers / trust failures at Tk50k–1.5L)

**Strategic reasoning:** Broken discovery + no system status + gated delivery + invisible landed cost together trash funnel before P1 differentiators can matter. All P0 are VERY HIGH value + mostly LOW or essential HIGH complexity (INV-13 table).

| Initiative | Type | Problem | Why now |
|---|---|---|---|
| **INV-01 /undefined fix** | FIX | Browse dead-end P0 blocks every path | LOW fix before any browse |
| **INV-C02 PLP Browse Controls** | FIX | Chips/placeholders hide system status (Nielsen visibility) | LOW restore unlocks finder |
| **INV-13 Delivery Estimator** | NEW | PDP-02 P1 permission gate hides landed cost | Single table wires 7; FOUNDATIONAL |
| **INV-C06 Cart Drawer & Feedback** | FIX+NEW | FEEDBACK/CART/CHECKOUT P1 cluster black box | Visibility of status + landed-cost truth |
| **INV-21 Authenticity Badging** | NEW | TRUST-01 P2 post-Evaly barrier | No backend, reuses 13 brands moat vs Daraz |
| **INV-22 Browse Resumption** | NEW | Journey F wholly unserved DISC-02 P1 | Cheapest retention localStorage |
| **INV-26 Plural Payment Row** | NEW | 75–90% COD excluded by card-first PDP | LOW co-equal row beneath EMI; zone-aware truth |
| **INV-C04 warranty truth (half)** | FIX | `Parts-0M/Motor-300M` warranty implausible | Content-only, immediate |
| **INV-C03 Stage1 Search** | NEW | Journey A no suggestions, `Search Here` generic | 150ms dropdown + Recent 6 hygiene P0 |
| **INV-14 True Cost static row (part of EMI)** | NEW | Sticker illusion `FTKL…` + EMI silence Haier 622L | Upfront+Delivery+Install+Energy→EMI/mo verdict; offline 5–10d truth |

## P1 — High Priority (Strongly recommended after foundations stable)

**Reasoning:** High user/business value + proven benchmark STANDARD; complexity HIGH but phased (static row before slider, checklist before booking). **11 initiatives:**

**INV-C01 IA Hygiene (canonical fixes P1), INV-04 SEO re-layer, INV-23 Smart Compare (sticky→auto-populate), INV-24 AC Finder (P1 lens → P2 Fridge/TV), INV-C04 jargon decoder (full 8–10 terms), INV-12 zoom (P0 slice) + video pilot P1, INV-17 variant chips, INV-16 Gate1 checker (content), INV-C05 sticky hotline+WhatsApp deep-link, INV-32 auth split-field fix + guest toast, INV-C03 Zero-Result Recovery, INV-14 interactive True Cost (slider phase2)** — see `executive-priority-view.md` for why-after-P0 rationale per row.

## P2 — Important (Meaningful but gated by dependency proof)

**Reasoning:** Value HIGH only after foundational volume/feeds prove; criticized as deferred per `decision-log.md`.

| Initiative | Why gated now |
|---|---|
| INV-06 Homepage budget cull | Budget subtraction ships now as P1 subtraction, affinity reorder is P2 A/B experiment requiring modular CMS+scorer |
| INV-25 Bundles pilot (curated AC/TV only) | Needs Family Graph top 30 roots validation + price/stock feed; suppress low-ticket BDT5k |
| INV-28 OBD OTP protocol (beyond badge) | Badge eligibility P1 by pincode; full OTP+photo log HIGH needs fleet protocol confirmation |
| INV-33 14-day static badge (→ AI diagnostics LATER) | Static `14-Day + up to Tk12k → inspection → OTP` now; 10-step AI cross-category VERY HIGH after ops |
| INV-20 Social Proof full pipeline (beyond) | VERY HIGH collection/moderation while current supply zero; pilot post-delivery SMS for 1 cat to prove n≥5 first |
| INV-34 Accessibility incremental | LOW feasibility shipped with each touchpoint, not standalone sprint |

## P3 — Future Opportunities (Longer-term)

INV-24 Fridge/TV/Washer additional finder lenses after AC proves pattern + rule governance; INV-12 video/360/AR beyond zoom after asset audit.
*Future = higher maturity or infrastructure required; not now.*

## Parked — Not recommended currently

| Idea | Why parked | Conditions to reconsider |
|---|---|---|
| Hierarchical PDP URL migration | VERY HIGH 101 PDPs 301, SEO risk | When canonical/hyphen fixes prove + 10-URL pilot shows lift |
| Full Affinity Homepage Reorder | Scoring + modular CMS + governance `applicability-review.md:128-135` QUESTIONED; cheaper rail achieves 80% | After INV-22/INV-C03 rails proven → A/B `Rail only vs Rail+hero` with CMS |
| Gate2 Bookable Slot (calendar) | Ops-gated slot-capacity + order↔service link not confirmed `cross-review.md:175` | Ops confirms per-district capacity feed |
| Full Ratings at scale | Zero supply `ecommerce-capabilities.md:31-33` | Pilot post-delivery proves n≥5 consistently |
| Kitchen/Purifier finder lens (7 PDPs) | Evidence thin `sitemap-analysis.md:43` | When catalog ≥20 PDPs with validated rules |
| AI Diagnostics 26-cat | VERY HIGH cross-category AI | After static 14-day badge + inspection truth proves demand |

*P2/Parked are not "less valuable" — they are later because dependencies or proof not yet met.*

---

# 11. Recommended Implementation Sequence

> Horizons = sequencing logic, not calendar dates per `05-prioritization/executive-priority-view.md`. WHY column traces to dependencies. Do not invent timelines unless project planning data supports.

## NOW — Critical friction + foundational trust row + memory (P0, ships first, single data table)

**Focus:** Make 7 future initiatives work for free; repair funnel before decision support. *One district→Zone/SLA+fee+install+store table built once wires OPP-01/09/12/14/21/26/28/C05/C06.*

| Build | Why NOW |
|---|---|
| **INV-01** /undefined hotfix | Blocks every browse path — LOW, first. |
| **INV-C02** chips/sort/facet hygiene + `Customer Review` suppress until feed | Visibility of system status P1; unlocks filtering for finders. |
| **INV-C04 warranty truth** | Content-only `Parts-0M→h` fix; immediate trust. |
| **INV-22** Recently Viewed rail + Continue deep-link + `searchHistory` Recent chip foundation | Cheapest retention, anonymous durable `localStorage viewHistory+lastPlpUrl+compareQueue` still no backend; auth migration later (INV-32). |
| **Start INV-13 table** district→Zone/SLA+delivery fee+install fee+store inventory | Single table — geneis for INV-14/26/21/28/C05/C06; start week 0–2. |
| **Complete INV-13 → INV-14 static True Cost row** `Upfront+Delivery+Install+Energy→EMI/mo` + tenure 3/6/12/24/36 + ineligibility verdict `→ EMI Bank List` + offline 5–10d truth Pickaboo/Daraz; suppress <BDT5k | Single landed-cost truth — highest ROI for 50k–1.5L stuck between PDP-02 gate and PDP-06 silence. |
| **INV-26** Plural `COD+bKash/Nagad+Card-on-Delivery+Online` row beneath EMI on PDP + Cart district-aware `COD available` | 75–90% market excluded if card-first; no backend beyond zone truth. |
| **INV-21** `✓ Authorized — Official Warranty` hero lockup + warranty sheet + Mall/flagship tag at price context | Reuses 13 brand authorizations moat vs Daraz variance; no backend. |
| **INV-C06** slide-in mini-cart + Cart `Subtotal+Delivery+Install→Total` + `Cart→Delivery→Payment→Confirm` stepper + toast on every add/wishlist/compare | `FEEDBACK-01/CART-01/CHECKOUT-01` cluster cheapest ROI; landed-cost truth before paywall. |
| **INV-C03 Stage1** debounced autocomplete `Product/Brand/Category/SKU-exact (3+ alnum ranks SKU)` + Recent 6 + rotated placeholder `Try "1.5 Ton"` | Journey A `FTKL12TV16WD` fast-path; verify empty dropdown is missing index not rendering bug. |

## NEXT — High-value enhancements after foundations stable

**Focus:** Decision support + compare + media + variant navigation that reuse foundations.

| Build | Why NEXT (after foundations) |
|---|---|
| **INV-C01** canonical fixes + hyphen/Dishwashers tile (DEFER hierarchical migration) | SEO coherence after browse paths work. |
| **INV-04** SEO wall re-layer below pagination + `Not sure? 30-sec guide` → finder CTA | Grid above fold; preserves `buying-guides` equity (Currys). |
| **INV-23** Smart Compare sticky→auto-populated `/compare` + `Highlight differences` (decisive tint/verdict deferred) | Sticky→auto-populate solves Journey D hand-type recall; total-cost pin + decisive tint phase2 after decisive rows validated. Share URL + WhatsApp huddle. |
| **INV-24 AC Finder lens** (sq ft×height/top-floor→tonnage 20 BTU) | Fewest SKUs, `Choose Ton` proof, differentiator moat vs Daraz; rule table governed. Fridge/TV lenses follow AC proof. |
| **INV-C04** jargon decoder full 8–10 terms `tap EER→Tk/mo` + `R32/HQLED` | Content-only, unlocks finders/cost literacy; taps rare terms before verdict. |
| **INV-12 Rich Media P0 slice** hover-zoom/pinch + `1/7` scrub + dimension overlay from W×H×D W×H×D shared | No reshoot; highest anxiety reduction. Video pilot 1 cat next. |
| **INV-17** Variant & Family Navigator sibling chips `+Tk delta` + `Get Stock Alert` | Vault exploitation top 30 roots 70%; re-validates delivery/energy/EMI on switch. |
| **INV-16 Gate1 Installation Checker** per-SKU checklist + verdict `✓ Feasible` + priced `Add Installation` SKU | Content checklist before booking; shares install table with INV-13. |
| **INV-C05 WhatsApp deep-link + sticky hotline** `Schedule your visit` linkage to existing Mapbox | Human reassurance Tk80k+ (ChalDal Premium Care model); sticky 16212 + Share PDP. |
| **INV-32** Auth split-field fix + guest toast `Saved for now — log in` + localStorage→account migration | Enablement for wishlist persistence; single tel + format hint. |
| **INV-C03 Zero-Result** synonym table + Did-you-mean + `Remove Brand →12` + advisor CTA | Short build brackets Journey A failure path after OPP-07. |

## LATER — Advanced / Differentiators (higher dependency, ops/content gated)

**Focus:** Scale after proof + supply.

| Build | Why LATER |
|---|---|
| **INV-12** functional video per template 15–25s → dimension overlay+360/AR | Asset production scales by category; reuses Samsung/Haier reels not yet audited. |
| **INV-20** Social Proof full pipeline | VERY HIGH — needs post-delivery pilot proves n≥5 supply `ecommerce-capabilities.md:31-33` zero; keep PLP badge wiring low but pipeline after. |
| **INV-28** OBD/OTP protocol (beyond eligibility badge) | HIGH fleet rider protocol/photo/log; badge eligibility P1 by pincode ships now. |
| **INV-33** 14-day badge → cross-category AI diagnostics 10-step | Static `14-Day + up to Tk12k → inspection → OTP` now; AI VERY HIGH ops feed. |
| **INV-25** Bundles curated pilot → full catalog | Needs Family→attach mapping + price delta proven on AC/TV pilot before low-ticket. |
| **INV-24 additional lenses** Fridge bag/guard + TV distance→size + Washer kg | After AC lens proves pattern + `W×H×D+gap+swing` normalisation sampled 10 PDPs. |
| **INV-33 Exchange AI + threshold bundling `Free on 3+` (NEW-08)** | Phygital assisted linkage + deal threshold differentiator after CHOICE single-warehouse. |

## EXPERIMENT — Validation before invest

| Build | Why EXPERIMENT |
|---|---|
| **INV-06 Affinity Homepage Reorder** `Rail only vs Rail+hero reweight` A/B | Highest CMS dependency (modular CMS + affinity scorer + A/B + campaign governance) `applicability-review.md:128-135` QUESTIONED OPP-15; no P0 pattern validates full rewrite before hygiene. Cheaper rail+recent gives 80% value. Run EXPERIMENT after `Rail only` proven with A/B `Rail only vs Rail+hero reweight`. Also `Your size:55"` rank within PLP could ship earlier as low-cost tweak. |

---

# 12. Dependency & Foundation Map

> Hard vs Soft per `05-prioritization/dependency-map.md`. Foundational initiatives enable ≥3 others — build once. Graph notation: `A ↓ B` means B cannot ship before A.

## Foundational Initiatives

| Foundational | Enables | Why Foundational |
|---|---|---|
| **INV-01 /undefined fix** | All browse/discovery INV-04/22/23/24/INV-C02 | P0 blocker — no discovery path completes |
| **INV-13 District→Zone/SLA + fee + install + store inventory table** | INV-14, INV-16, INV-26, INV-28, INV-C05, INV-C06, NEW-08 Fast filter (7 consumers) | Single table built once |
| **INV-C04 Glossary 8–10 terms + Warranty Truth** | INV-14 True Cost row, INV-24 verdict, INV-16 checklist literacy | Literacy prerequisite — finder verdicts reference EER etc. |
| **INV-22 localStorage viewHistory+lastPlpUrl+compareQueue** | INV-23 Compare, INV-C03 Recent, INV-32 migration | Same store `viewHistory/compareQueue/searchHistory` |
| **EMI Master (bank×tenure×threshold 5k/10k + form latency)** | INV-14, INV-23 total-cost pin, INV-26, INV-C06 breakdown | Finance truth table |
| **Family Graph model_root→variants** | INV-17, INV-23, INV-25, INV-10 re-validation | Top 30 roots 70% high-ticket |
| **W×H×D + ventilation gap normalisation** | INV-10 dimension overlay, INV-16 checker, INV-24 Fridge guard | One spec enrichment |

## Full Register

| Initiative | Depends On | Why | Strength |
|---|---|---|---|
| INV-C01 IA Hygiene | INV-01 | Hireachy fixes assume browse paths resolve | HARD (canonical); SOFT (migration parked) |
| INV-C02 PLP Browse Controls | INV-01 | Chips rely on reachable PLP | HARD |
| INV-04 SEO Re-layer | INV-C02 | Re-layer must know PLP filter placement above fold | SOFT |
| INV-C03 Search | INV-22 Recent | Recent chip shares searchHistory store | SOFT |
| INV-14 True Cost | INV-13 + INV-C04 + EMI master | Delivery fee/SLA + tariff×EER + bank master | HARD delivery; HARD glossary; HARD EMI |
| INV-16 Checker→Booking | INV-13 + INV-C04 + W×H×D + slot-capacity feed (VERY HIGH parked Gate2) | Install fee + glossary + dimensions | HARD / VERY HIGH Gate2 |
| INV-17 Variant Navigator | Family Graph | model_root enrichment | HARD |
| INV-22 Resumption | — | Anonymous localStorage; auth migration INV-32 | SOFT auth |
| INV-23 Smart Compare | INV-22 store + INV-13/14 feeds + Family Graph | Persistence + total-cost pin + add sibling | HARD store; SOFT feeds |
| INV-24 Guided Selling | INV-C04 + rule tables per lens | Literacy + tonnage/litres tables | HARD glossary |
| INV-25 Bundles | Family Graph + INV-13 | Family→attach + price/stock | HARD family |
| INV-26 Plural Payment | INV-13 zone matrix | District-aware COD truth | HARD |
| INV-28 OBD badge→protocol | INV-13 zone eligibility | Badge by pincode | HARD |
| INV-C05 Human Spine | INV-13 store inventory for Schedule Visit | Store Pickup mapping | SOFT |
| INV-C06 Cart Drawer & Landed-Cost | INV-13/14 delivery+install | `Subtotal+Delivery+Install→Total` truth | HARD |
| INV-32 Auth UX | INV-22 store | viewHistory/compareQueue/searchHistory migration on OTP | SOFT |
| INV-33 Exchange | valuation feed | Cross-category AI diagnostics | HARD |
| INV-06 Affinity Reorder | INV-22 rail + INV-C03 Recent + CMS modularity + scorer | Affinity scorer needs history + modular CMS + A/B | HARD cms |

## Visual Graph

```
P0 Foundations (ship first, unblock dependents)
  INV-01 /undefined ──► All browse/discovery
  INV-C04 glossary+ warranty ──► INV-14 True Cost, INV-24 Guided Selling, INV-16
  INV-13 District→Zone/SLA ──► INV-14, INV-16, INV-26, INV-28, INV-C05, INV-C06, NEW-08
  INV-22 localStorage store ──► INV-23 Compare, INV-C03 Recent, INV-32 migration
  EMI Master ──► INV-14, INV-23 pin, INV-26, INV-C06
  Family Graph ──► INV-17, INV-23, INV-25, INV-10 re-validation
  W×H×D normalisation ──► INV-10 overlay, INV-16 checker, INV-24 Fridge guard

P1 Decision core (depend on foundations)
  INV-14 True Cost (needs INV-13 + INV-C04 + EMI master)
  INV-24 Guided Selling AC lens (needs INV-C04)
  INV-23 Compare (needs INV-22 + INV-13/14 feeds + family graph)
  INV-12 Rich Media zoom (low deps) → video/dimension (needs W×H×D)
  INV-17 Variant chips (needs family graph)
  INV-16 Gate1 checker (needs W×H×D + INV-13 + INV-C04)

P2 Differentiators (ops/content gated)
  INV-20 Reviews pipeline → INV-21 companion
  INV-33 14-day → AI
  INV-25 Bundles pilot → full catalog
  INV-28 badge → OTP protocol
  INV-06 affinity → needs CMS + A/B
```

*Wiring table: 7 foundational tables feed 13 initiatives. Building the district table once avoids 7× duplicate effort `applicability-review.md:158-169`.*

---

# 13. Recommended Strategic Themes

> 5–8 memorable themes emerging from evidence (not forced consulting terms). Each theme bundles P0/P1 that must ship together to deliver one customer promise.

| THEME | Promise (customer voice) | Constituent initiatives | Strategic lesson (benchmark pattern) |
|---|---|---|---|
| **THEME 1 — Make Discovery Actually Work** | "I can reach what Browse promised." | INV-01 /undefined + INV-C02 chips/sort/facets + INV-C03 Stage1 autocomplete+Recent + INV-04 SEO re-layer | Fixes discovery before decision support — browse is hygiene, not differentiator. Coolblue `advice` hub + Currys `buying-guides` show guide belongs below pagination, not above filters. |
| **THEME 2 — Help Me Choose, Don't Make Me Translate** | "Room → tonnage, family → litres, distance → size — you tell me." | INV-24 Guided Selling (AC first) + INV-C04 decoder 8–10 terms + INV-C03 Zero-Result recovery | Requirement translation is the moat vs Daraz marketplace (rule governance vs generic description `pattern-library.md:34-44` Problem 2). Content-only decoder unlocks wizard literacy; frugal 20 BTU/sq ft + bag ladder already validated. |
| **THEME 3 — See It, Compare It, Trust It for Real** | "I can inspect fit, compare decisive rows, and share with family." | INV-12 zoom/pinch + INV-23 Smart Compare (sticky→auto-populate) + INV-17 variant chips | Compare is recall task today `page-analysis.md:173-178` P1; zoom first (no reshoot) + scrub has highest ROI; variant graph compensates flat PDP `sitemap-analysis.md:27`. Validated STANDARD (RTINGS/Cooolblue/dk 10M buyers). |
| **THEME 4 — Tell Me What It Will Really Cost to Own** | "Sticker is not delivered-cost. Tell me EMI/mo and Tk/mo together." | INV-13 pincode-first SLA + INV-14 True Cost ownership row `Upfront+Install+Energy→EMI/mo` + INV-26 plural `COD+bKash` row + verdict `→ EMI Bank List` + offline 7–10d truth | One district→Zone table wires 7 themes; sticker illusion (Haier 622L no EMI `product-page-variations.md:55` P2) + permission gate PDP-02 + plural COD 75–90% Levree — combined row is DIFFERENTIATOR in BD (Pickaboo 32 banks BDT5k). |
| **THEME 5 — Prove Trust at the Price, Not Just the Homepage** | "You claim Original — prove it where I pay." | INV-21 `✓ Authorized` at price + INV-20 ratings pilot (PDP header + PLP card 4.6★ + `★★★★&up` facet) + INV-28 OBD badge→OTP | Homepage bar `page-analysis.md:34` vs PDP generic `page-analysis.md:112` dissipates trust where needed; post-Evaly barrier needs mechanics (DarazMall guarantee+Mall `regional-commerce.md:29-38`). Ratings pipeline VERY HIGH — pilot n≥5 first. |
| **THEME 6 — Remember Me Without Making Me Log In Yet** | "Come back and pick up where you left — filters intact." | INV-22 Recently Viewed rail + Continue deep-link + INV-C03 Recent Searches + INV-C05 hotline/WhatsApp huddle | Journey F wholly unserved DISC-02 P1; cheapest retention localStorage (Amazon Pick up where you left off); human reassurance before cart per ChalDal Premium Care — full affinity reorder (scorer+CMS) is P2 experiment only. |
| **THEME 7 — Make Delivery, Install & Return Feel Certain** | "Wall? Drain? Slot? Return? You check before I pay." | INV-16 Gate1 checker + priced basket `Add Installation` + INV-33 14-day badge + INV-28 OBD + INV-C06 Cart stepper+landed-cost toast + INV-C05 Schedule Visit | Gate2 bookable slot LATER ops-gated; checker content solves 90% failed-install waste without slot inventory. Theme seals post-purchase. |
| **THEME 8 — One Trip Ownership (Attach Where It Pays)** | "Get everything needed in one cart, not two." | INV-25 curated attach pilot AC/TV/Fridge/Washer/purifier | Thin Related single card `product-page-variations.md:65`; generic low-ticket (trimmer) suppressed per BDT5k threshold — AOV via curated rule table Family→attach, not full FBT. Phase pilot. |

---

# 14. What Not to Do Yet

> Strategic "Not Now" is anti-scope-creep. Each idea explains why not, what is missing, when to reconsider — all traceable to `05-prioritization/not-now.md` and `decision-log.md`.

| Idea | Decision | Why Not Now | Conditions to Reconsider |
|---|---|---|---|
| **Hierarchical PDP URL migration** `sitemap-analysis.md:27` 101 → `/refrigerators/no-frost/side-by-side/ro...` | **PARKED** | VERY HIGH 301 map, SEO risk vs canonical fix LOW delivers 80% `decision-log.md` INV-C01 SIMPLIFY | When canonical/hyphen fixes prove + 10-URL pilot shows lift with clean 301 log |
| **Category-Affinity Homepage full reorder** (scorer+modular CMS+campaign governance) `opportunity-pool.md:15` OPP-15 QUESTIONED `applicability-review.md:128-135` | **P2 EXPERIMENT only** | No P0 pattern validates full rewrite before hygiene; cheapest retention (INV-22 rail) gives 80% `decision-log.md` affinity deferred; `DISC-01` overload already `page-analysis.md:48-54` | After INV-22/INV-C03 rails proven → A/B `Rail only vs Rail+hero reweight` with modular CMS audit passing |
| **Gate2 Bookable Calendar Slot** `cross-review.md:175` FEA-06 | **LATER** (Gate1 checker now) | VERY HIGH slot-capacity + order↔service linkage not confirmed; UI without feed worse than no booking | Ops confirms per-district capacity feed; Gate1 checker proves demand |
| **Full Ratings pipeline at scale** `ecommerce-capabilities.md:31-33` NOT OBSERVED zero supply | **PILOT only (1 cat) → scale later** | VERY HIGH collection/moderation while supply zero; badge without pipeline = fake counts | Pilot post-delivery SMS for AC/TV proves n≥5 supply consistently |
| **Kitchen/Purifier Guided Selling lenses (7 PDPs)** `sitemap-analysis.md:43` thin `opportunity-pool.md:67` MED | **REMOVED within INV-24** | Thin evidence vs AC/TV/FRIDGE 8–12 each; thin ticket attach generic per BDT5k suppress | When catalog ≥20 PDPs with validated wattage/TDS rule tables |
| **Complete Season Broadcast (PER-09 tail)** `personalization.md:356` | **REMOVED generic** | Calendar+broad affinity = campaign segmentation, fails True Personalization test `personalization.md:30-33`, no benchmark validates | As campaign schedule, not product capability; revisit only with behavioural price/stock signal |
| **Populated Cart quantity/coupon as standalone initiative** ECS-06 `ecommerce-capabilities.md:39-42` NOT TESTED populated | **REMOVED — reclassified as hygiene inside INV-C06** | Empty shell VERIFIED; quantity/coupon are baseline hygiene, not differentiator `cross-review.md:201-208` | Track as remediation inside Cart Drawer |
| **Active Filter/Sort Feedback as opportunity** ECS-07 `issue-register.md:20-25` | **REMOVED — P0 fix** | Shell VERIFIED `ecommerce-capabilities.md:16-22`; gap is missing chip row + empty `sortOptions:[]` — restoration, not opportunity | Track as INV-C02 P0 fix |
| **Full AI Diagnostics 26-cat cross-category Exchange** INV-33 `regional-commerce.md:113-122` 10-step AI | **LATER** | VERY HIGH cross-category AI; static `up to Tk12k → inspection → OTP` truth proves demand first | After static 14-day+valuation proves trade-in intent |

*"Not Now" is not "Never" — each row is a measurable exit condition. Do not build high-cost differentiators on unproven supply (reviews) or unconfirmed feed (slots) or thin catalog (7 PDPs).*

---

# 15. Conclusion & Recommended Next Steps

**Where the platform is today.** A functionally complete catalog shell with breadth (39 PLPs correctly breadcrumbed), taxonomy-aware filters, and EMI financing — but interaction-immature: funnel blocks before decision support can matter, system status invisible, delivery permission-gated, landed cost hidden, and post-Evaly trust claimed not proved at price. Maturity: **Developing — bordering Foundational**.

**Biggest opportunities.** The **single district→Zone/SLA+fee+install table** that unblocks *landed-cost confidence* for every Tk50k–1.5L purchase (Theme 4); **browse memory + intelligent search** that spards returner value with localStorage alone (Theme 6); and **requirement-led finders + spec literacy** that vs Daraz are the only non-copyable moat (Theme 2). Each is validated as STANDARD or differentiator by 21 platforms.

**What should happen first.** The **NOW horizon** (10 P0): `/undefined` hotfix → PLP chips/sort/facet hygiene + warranty truth → start district table → Recently Viewed + Continue + Recent Searches Stage1 → complete estimator + static True Cost row `EMI from Tk/mo × bank` + plural row + authenticity lockup → Cart drawer/stepper/toast. Ship foundations first so 7 later initiatives work for free; *do not* start with homepage affinity or slot booking.

**Longer-term vision.** A **need-led electronics retailer** where homepage guides rather than dumps 7 grids — `Not sure? 30-sec guide → finder → filtered PLP (rule-governed) → PDP with ✓ Fits your X, total-cost-owned row, zoom/dimension, variant + delivery re-validation, trustworthy install/return + OBD photograph — → cart that remembers and compares total cost → human WhatsApp/hotline huddle → delivered-to-door proof.* The vision is not a feature count — it is **"I was helped to choose the right spec, shown what it will really cost monthly, and delivered with proof."**

**Next actions.**

| Role | Next Action |
|---|---|
| **Product** | Lock NOW vs PARKED scope (`executive-priority-view.md`); gate P1 on INV-13 table + INV-22/INV-C02 proof; own rule tables (sq ft→ton) per lens + EMI master 32 banks + district matrix governance; suppress low-ticket BDT5k guard. |
| **UX/UI** | Phase NOW wireframes: PLP chip row + sort real select + pagination `Showing 1–12 of 45 — Show [12|24|48]`; PDP landed-cost row + `✓ Authorized` lockup + warranty legend; Search debounced dropdown + Recent chips; Cart drawer+stepper; Recently Viewed rail. Keep guidance concrete per `BAD vs GOOD` style. |
| **Engineering** | Spike 7 shared tables before build: district master, EMI bank/tenure, W×H×D normalisation for top families, glossary CMS 8–10 terms, `localStorage` schema `viewHistory/lastPlpUrl/compareQueue/searchHistory` + auth migration on OTP 0157…, family graph for 101 PDPs `sitemap-analysis.md:27`; instrument `viewHistory/compareQueue/searchHistory` events for gating metrics. |
| **Business stakeholders** | Fund P0 trust row as conversion unlock, not cosmetics; approve deferred experiments criteria (INV-06 affinity A/B after rail proven, Gate2 after ops feed); align post-delivery SMS pilot for ratings (prove n≥5) + slot-capacity feed decision; approve 14-day badge shift (Daraz Aug 2025 ALL baseline) before AI. |

> **Final synthesis rule:** Not a bigger list, but a *smaller, defensible* one — 25 prioritized initiatives (10 P0, 11 P1, 4 P2, parked P3/LATER), 5–8 themes, 7 foundational tables, staged horizons NOW/NEXT/LATER/EXPERIMENT, all traceable to `00-input` → `05-prioritization` file:line. STOP AFTER PHASE 6 — Phase 7 would be detailed UX design & roadmap tickets (not ticket dump).

---
*Generated 2026-09-03. All priorities traceable via `recommendation-traceability.md`. Executive Critic review per `executive-review.md`.*
