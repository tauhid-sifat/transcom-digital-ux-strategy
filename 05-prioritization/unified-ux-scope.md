# Unified UX Scope — Consolidated & Prioritized Initiatives

> 25 consolidated initiatives grouped by strategic area. Each: Priority | Type | Problem | Recommended Direction | Expected User Value | Dependencies | Evidence.

## A. Foundation & Core UX

### INV-01 Fix Browse Paths Terminating at /undefined
- **Priority:** **P0 — CRITICAL** | **Type:** FIX — Source: Phase 2 NAV-01 P0 HIGH `issue-register.md:7` `page-analysis.md:56-57`
- **Problem:** 11× See All + brand sub See All resolve to `/undefined` / `/samsung/undefined`; primary discovery CTA dead-ends (Journeys B/C).
- **Direction:** Guard slug generation + fallback/redirect for empty slug + CI link audit. Ship as hotfix, decouple from IA migration.
- **User Value:** Browse recovers — homepage → PLP no longer 404. **Evidence:** Phase 1 VERIFIED.
- **Dependencies:** None (HOTFIX, blocks all).

### INV-C01 IA Hygiene (Canonical / Orphan / Tile / Hyphen)
- **Priority:** P1 — HIGH | **Type:** FIX — Source: Phase 2 IA-01/02/04 + NAV-02 + DISC-04 `issue-register.md:8-12,16`
- **Problem:** Flat PDP URLs (`sitemap-analysis.md:27` 101 at root) sever hierarchy; `/tv-av` orphan; Brand vs `/search?Brand=samsung` duplicate; Dishwashers tile vs taxonomy mismatch; 4 trailing-hyphen slugs.
- **Direction:** Ship 3 LOW fixes now: canonical brand→PLP (brand PLP authoritative), `/tv-av` landing, Dishwashers tile→category or campaign mark, sanitize 4 slugs + 301; **DEFER** hierarchical PDP URL migration (VERY HIGH, parked) per `decision-log.md`.
- **User Value:** SEO coherence, shareable URLs, no canonical confusion.
- **Dependencies:** INV-01 fixed first.

### INV-C04 Spec Jargon Decoder & Warranty Truth
- **Priority:** P0 warranty truth + P1 decoder | **Type:** FIX (warranty) + NEW CAPABILITY (decoder) — Source: Phase 2 PDP-05 P2 + Phase 3 EDS-05 `opportunity-pool.md:166-180`
- **Problem:** `Service-12M / Parts-0M / Motor-300M` implausible; EER/R32/HQLED opaque `product-page-variations.md:61` `issue-register.md:30`.
- **Direction:** **P0:** normalise warranty legend (`Service/Parts/Compressor|Panel|Motor + humanised 5 years`) per-phase. **P1:** glossary CMS 8–10 terms tap-to-explain + `kWh×rate` Tk/mo formula (Bangladesh tariff). Prerequisite for True Cost & finders.
- **User Value:** Decode without Googling; warranty trust repaired.
- **Dependencies:** Term bank authoring; tariff input.

---

## B. Navigation & Product Discovery

### INV-04 SEO Wall Re-layer (Former IA-03)
- **Priority:** P1 | **Type:** IMPROVEMENT — Source: `issue-register.md:10` IA-03 P1 `page-analysis.md:90-91` 1,500-word guide pushes grid below fold
- **Problem:** Category L1/L2 discovery delayed — filters/grid below fold.
- **Direction:** Move long-form to collapsible "Buying Guide" below pagination + add PLP CTA `Not sure? 30-sec guide → finder` (Coolblue/Currys pattern). Preserve SEO equity.
- **User Value:** Grid above fold; guide still accessible.
- **Dependencies:** INV-C02 PLP controls fixed.

### INV-06 Homepage Curated Prioritization
- **Priority:** P2 — IMPORTANT (deferred experiment per `applicability-review.md:128-135` QUESTIONED) | **Type:** IMPROVEMENT — Source: `issue-register.md:13` DISC-01 P1 `page-analysis.md:48-54` 7+ grids overload
- **Problem:** Homepage serves 7+ mini-grids (Electric Kettles…TV) with no prioritisation → cognitive overload (`user-journey-friction.md` Journey B/C high cluster).
- **Direction:** Immediate budget-only: cull to category navigation + single hero + one curated carousel per segment (subtraction, not addition); **DEFER** returner affinity reorder to P2 A/B `Rail only vs Rail+hero reweight` requiring modular CMS + scorer (OPP-15 QUESTIONED). Suppress for low-ticket.
- **User Value:** Scannable homepage; first-timer orientation preserved.
- **Dependencies:** CMS modularity audit; depends on INV-22 rail proof.

### INV-22 Browse Resumption: Recently Viewed & Continue Shopping
- **Priority:** **P0 — CRITICAL** | **Type:** NEW CAPABILITY — Source: Phase 3 PER-01/02 + ECS-09 `opportunity-pool.md:21-36` `issue-register.md:14` DISC-02 P1 F unserved `ecommerce-capabilities.md:55` NOT OBSERVED
- **Problem:** No trail to resume interrupted high-consideration research (Journey F).
- **Direction:** Anonymous `localStorage viewHistory (8) + lastPlpUrl (filter state)` → rails on homepage/PLP/PDP + empty-cart injection + auth migration on OTP 0157… Deep-link restores `Brand + Display Size + Price` state. Cap 8.
- **User Value:** One-tap resume with facet state intact; cheapest retention.
- **Dependencies:** Event instrumentation + 3 rails; LOW (no backend stage1).

---

## C. Search & Filtering

### INV-C02 PLP Browse Controls (Chips / Sort / Facet Hygiene)
- **Priority:** **P0 — CRITICAL** (FILTER-01/SORT-01 P1) | **Type:** FIX — Source: `issue-register.md:20-25` `ecommerce-capabilities.md:16-22` `page-analysis.md:75-87`
- **Problem:** `Customer Review` heading empty (FILTER-02 P2), price slider+buckets compete (FILTER-03), `Display Size` vs `Screen` duplication (FILTER-04 P3), sort shows placeholder `Select Sort Option` with `sortOptions: []`, pagination `Show 12 <of 1> 1` ambiguous.
- **Direction:** Chip row + `X filters applied` + `Clear all` above grid; merge `Display Size/Screen` to single Size facet; bucket presets drive slider or collapsed tick labels; sort becomes real select `Relevance/Price low→high/high→low/Newest/Discount`; pagination `Showing 1–12 of 45 — Show [12|24|48]`.
- **User Value:** System status visible; sorting anticipated; pagination comprehends catalog depth.
- **Dependencies:** PLP header wiring; suppress `Customer Review` until feed.

### INV-C03 Intelligent Search & Recovery
- **Priority:** P0 Stage1 + P1 Stage2/Recovery | **Type:** NEW CAPABILITY — Source: FEA/ECS search clusters `opportunity-pool.md:101-132` `issue-register.md:17,19` SEARCH-01 P1/SEARCH-03 P2
- **Problem:** Header `Search Here` `page-analysis.md:9` VERIFIED but suggestions NOT FULLY VERIFIED `user-journeys.md`; `FTKL12TV16WD` alphanumeric no fast-path; typos `FTLK↔FTKL` dead-end; placeholder generic.
- **Direction:** **P0 Stage1:** debounced 150–200ms dropdown `Product (+price/badge/thumb) / Brand / Category / SKU-exact (3+ alnum ranks SKU)` + Recent 6 chips (localStorage). **P1 Stage2:** affinity-biased ranking after INV-22 volume. **P1b:** Zero-result `Did-you-mean + Remove Brand → N + Related + Try AC Finder` (fuzzy edit 1–2 + synonym table, Bangla digit mapping). Placeholder rotates `Try "1.5 Ton Inverter AC"`.
- **User Value:** Exact-model fast-path; typo-resilient; recent one-tap.
- **Dependencies:** Suggestion index + `searchHistory` store (shares with INV-22); verify empty dropdown is missing index vs rendering bug.

---

## D. Product Research & Decision Support

### INV-23 Smart Compare Workspace (Persistent, Auto-Populated, Decisive & Total-Cost Aware)
- **Priority:** P1 | **Type:** NEW CAPABILITY — Source: FEA-08+PER-03+EDS-08 `opportunity-pool.md:37-52` `issue-register.md:41` INTERACTION-01 P1 `page-analysis.md:173-178` 3× hand-typed inputs
- **Problem:** `/compare` requires hand-typing model names; Journey D recall-task fails; no decisive tint or total-cost.
- **Direction:** Sticky bar `Compare (2/3)` accumulates PDP `Compare` taps → auto-populated `/compare` + `Highlight differences` → decisive rows tinted + total-cost pin `price+install+1yr energy+EMI/mo` (feeds OPP-01/09) + share URL with OG preview (WhatsApp family decision).
- **User Value:** Build shortlist without typing; side-by-side decisive attributes + cheaper-to-own verdict.
- **Dependencies:** `compareQueue` store (`viewHistory`) + spec decisive-row normalisation + delivery/EMI feeds (INV-13/14) + share permalink; share after INV-22 migration.

### INV-24 Guided Selling Framework (Requirement-Led Finders → Filtered PLP → PDP Verdict)
- **Priority:** P1 AC lens → P2 Fridge/TV/Washer/Kited | **Type:** NEW CAPABILITY — Source: FEA-02 + EDS-01–04 + ECS-11 `opportunity-pool.md:54-68` `issue-register.md:10,28` IA-03/PDP-03 P1
- **Problem:** Life need (sq ft, family, distance, TDS) → spec (tonnage, litres, size, filter) translation is manual.
- **Direction:** One wizard `Need→Constraints→Budget/Preference` → filtered PLP + PDP chip `✓ Fits your 120 sq ft — 1.5 Ton`. Shippable lenses: **P1:** AC (sq ft×height/top-floor→tonnage, 20 BTU/sq ft LG) — fewest SKUs, `Choose Ton` proof `product-page-variations.md:52`. **P2:** Fridge (litres→family + bag ladder 18L=1 bag + 7-step measure guard → `W×H×D+gap+swing` shared with INV-10/12), TV (distance→size→panel explainer), Washer (kg→front/top). **REMOVE** Kitchen/Purifier lens (7 PDPs thin, `opportunity-pool.md:67` MED) per strategic critique.
- **User Value:** Answer right spec before spec table; filters pre-applied; PDP verdict confirms fit.
- **Dependencies:** Rule tables per lens validated vs brand sheets; INV-C04 glossary; PLP filter mapping reuse.

### INV-C04 (also listed in Foundation) covers jargon decoder prerequisite.

---

## E. Product Detail Experience

### INV-12 Rich Media Suite (Zoom, Video, Dimension Overlay)
- **Priority:** P0 zoom → P1 video/overlay → LATER 360/AR | **Type:** NEW CAPABILITY — Source: FEA-03+ECS-02 `opportunity-pool.md:150-163` `issue-register.md:27` PDP-01 P1 `page-analysis.md:134-135` 68 images but generic
- **Problem:** No video/zoom/360 for considered goods.
- **Direction:** Phased: **P0:** hover-zoom desktop / pinch mobile + `1/7` count + scrub. **P1:** short functional video per category template (AC wall, TV panel/HDR, fridge door swing 15–25s muted lazy) reusing Samsung/Haier reels. **LATER:** 360° where asset + dimension overlay `W×H×D+gap+swing` from structured spec (shared W×H×D table); AR `View TV virtually` phase 3.
- **User Value:** Validate fit/finish/features without store visit.
- **Dependencies:** Brand asset pipeline + spec W×H×D normalisation.

### INV-17 Variant & Family Navigator (Sibling Chips + Delta & Stock)
- **Priority:** P1 | **Type:** NEW CAPABILITY — Source: FEA-04 `opportunity-pool.md:199-213` `issue-register.md:33` PDP-08 P2 `page-analysis.md:86` Display Size facets prove family exists
- **Problem:** TV/Washer/Fridge PDP has no way to jump sibling (55"→65"); only AC has `Choose Ton`. Flat PDP namespace severs family context.
- **Direction:** Family graph `model_root → variants by tonnage/litres/display size/kg` rendered as chips `55" — Tk79,900 In stock | 65" +Tk18,000 | 75" Currently Unavailable` + `Get Stock Alert`; re-validates delivery/energy/EMI on switch.
- **User Value:** Explore siblings without returning to PLP.
- **Dependencies:** Family graph modeling (top 30 roots 70%); price/stock feed.

---

## F. Cart & Checkout

### INV-C06 Cart Drawer & Feedback System (Mini-Cart, Landed-Cost Breakdown, Stepper & Toast)
- **Priority:** **P0 — CRITICAL** | **Type:** FIX + NEW (drawer) — Source: `issue-register.md:36-38,42` CART-01/CART-02/CHECKOUT-01 P1 `page-analysis.md:159-164` empty `Subtotal ৳0 Total 0`, PDP `Add To Cart` ×2 `page-analysis.md:126-128`, FEEDBACK-01 `issue-register.md:42`
- **Problem:** Empty cart dead-end, invisible checkout steps, no landed-cost breakdown `Subtotal+Delivery+Install→Total` truth, no toast after add/wishlist/compare → duplicate taps.
- **Direction:** Slide-in mini-cart on Add confirmation; Cart `Order Summary` becomes `Subtotal+Delivery+Install→Total` with `Free Installation vs TkX` explicit (reuses INV-13/14 tables); progress stepper `Cart→Delivery→Payment→Confirm` with trust micro-copy; toast on every add/wishlist/compare to fix FEEDBACK-01. `Terms & Conditions` link stays but plus `Continue Shopping` CTA for CART-01 recovery.
- **User Value:** Paywall surprise eliminated; system status visible; confidence in what happens next.
- **Dependencies:** INV-13/14 fee/SLA tables + EMI master; low drawer UI.

### INV-13 Delivery & Serviceability Estimator (Pincode-First Landed Cost)
- **Priority:** **P0 — CRITICAL** | **Type:** NEW CAPABILITY — Source: FEA-01+PER-07+ECS-05 `opportunity-pool.md:7-20` `issue-register.md:27` PDP-02 P1 `page-analysis.md:125` gate `Enable your Location`
- **Problem:** Delivery confidence gated behind permission before cost/SLA/free-install flag.
- **Direction:** Pincode/area district text input (not GPS) → `serviceability yes/no, SLA, fee, free-install flag, store pickup alt + distance`; result propagates to Cart; earned `Fast Delivery` PLP badge/filter (1C) on `Show 12` header; suppress low-ticket Philips BT1235 Tk3k `product-page-variations.md:104`. Single table built once.
- **User Value:** Immediate landed-cost confidence at price exposure; store alternative.
- **Dependencies:** District→Zone/SLA master + delivery fee + install fee + store inventory feed; founding table for 7 initiatives.

### INV-14 True Cost & EMI Planner (Ownership + Energy + Install + Financing)
- **Priority:** P0 static row → P1 interactive | **Type:** NEW CAPABILITY — Source: FEA-05+EDS-06 `opportunity-pool.md:136-148` `issue-register.md:31` PDP-06 P2 `page-analysis.md:114-117` EMI badges inconsistent
- **Problem:** Sticker-price illusion; EMI inconsistent (Haier 622L no EMI `product-page-variations.md:55`); energy hidden as `EER 3.15` token; install gated.
- **Direction:** Unified ownership row `Upfront × + Install + Energy ~Tk/mo (1yr/5yr) → EMI from Tk/month × bank/tenure` with tenure picker 3/6/12/24/36 + tariff/running-hours slider (tariff×EER formula `pattern-library.md:90-92`). Explicit ineligibility verdict `EMI not available for this SKU → EMI Bank List` + offline form-latency copy (Pickaboo/Daraz 7–10d `regional-commerce.md:52-64`). Cart inherits row as breakdown. Suppress <BDT5k.
- **User Value:** Compare ownership, not sticker; validate monthly affordability; hidden energy transparent.
- **Dependencies:** INV-13 table + INV-C04 glossary + EMI master (32 banks, BDT5k/10k thresholds).

---

## G. Trust, Delivery & Post-Purchase

### INV-21 Authenticity / Authorized-Retailer Badging at Price Context
- **Priority:** **P0 — CRITICAL** | **Type:** NEW CAPABILITY — Source: Regional Finding 1 DarazMall/Pickaboo `04-benchmark/new-opportunities.md:22` `issue-register.md:35` TRUST-01 P2 post-Evaly barrier `sitemap-analysis.md:26` 13 brands
- **Problem:** Homepage `Original Product Guaranteed` vs PDP generic brand link — trust dissipates where needed.
- **Direction:** PDP hero lockup `✓ Authorized — Official Warranty` + warranty detail sheet + Mall/flagship tag at price context; echoes `Original Product` as proof. Reuses partnerships, no backend.
- **User Value:** Authorisation proof at decision moment.
- **Dependencies:** Brand authorization assets; pairs with INV-20 ratings.

### INV-20 Social Proof Pipeline (Ratings, Review Count & On-Card Badges)
- **Priority:** P1 after pilot (deferred per critique) | **Type:** NEW CAPABILITY — Source: ECS-01 `opportunity-pool.md:216-231` `issue-register.md:32,21` PDP-07 P1, FILTER-02 P2 `ecommerce-capabilities.md:31-33` NOT OBSERVED
- **Problem:** Review tabs exist `page-analysis.md:131-133` but no aggregate stars/count; `Customer Review` facet empty.
- **Direction:** Pipeline `Collection (post-delivery SMS prompt + verified-purchase) → Moderation → Aggregation (suppressed if n<5 → Be first to review — ask Q) → PDP header badge near price + PLP card 4.6★(212) + Customer Review facet ★★★★&up(n) + Q&A verified marker`. Seed empty-state governance (no fake 5.0(1)).
- **User Value:** Peer validation before Tk80k+ commitment; return-to-shelf badges bias shortlist.
- **Dependencies:** Review submission/moderation + aggregation service; pilot in 1 cat (AC/TV) to prove n≥5 supply before wide pipeline.

### INV-28 Open-Box Delivery + OTP Doorstep Verification
- **Priority:** P1 badge + P2 OTP protocol | **Type:** NEW CAPABILITY — Source: Regional Finding 2 Flipkart OBD `new-opportunities.md:44-50`
- **Problem:** 600L/65" doorstep anxiety for COD 75–90% (`regional-commerce.md:65-74` Levree).
- **Direction:** Badge `Eligible for Open Box Delivery at your pincode ✓` (reuses INV-13 eligibility) now; opt-in at Order Summary `open outer+brand packing, check damage/correct/IMEI, OTP only after satisfaction, photo+reference logged` post ops confirmation.
- **User Value:** Self-unbox burden transferred to rider; dispute-proofed handover.
- **Dependencies:** INV-13 pincode eligibility; rider protocol/log.

### INV-16 Installation Feasibility & Slot Booking (Checker → Bookable)
- **Priority:** P1 Gate1 checker → LATER Gate2 booking | **Type:** NEW CAPABILITY — Source: EDS-07+FEA-06 `opportunity-pool.md:182-196` `issue-register.md:28` PDP-03 P1
- **Problem:** No feasibility (outdoor wall/drain/socket/gap) before ordering; no slot.
- **Direction:** **Gate1 (P1 content):** per-SKU checklist + verdict `✓ Feasible — Add to Cart / ⚠ Requires bracket Tk2,500`. **Gate1b:** priced basket SKU `Add Installation + Recycling` (£115 model John Lewis). **Gate2 (LATER ops-gated):** calendar by district/team + prereqs + order↔service link + reschedule via `Track Your Service` `page-analysis.md:7` + push. Gate2 after slot-capacity feed confirmed (`cross-review.md:175`).
- **User Value:** Avoid ordering AC that cannot be walled; schedule certainty.
- **Dependencies:** SKU install table + W×H×D table + slot inventory feed; shares install table with INV-13.

### INV-33 Exchange & 14-Day Return (Doorstep AI Diagnostics)
- **Priority:** P2 static badge → LATER AI | **Type:** NEW CAPABILITY — Source: Regional Finding 8 Daraz 14-day ALL 2025 + Flipkart ReCommerce 26 cats 10-step AI `new-opportunities.md`
- **Problem:** Exchange hub `/exchange` existing but opaque `ecommerce-capabilities.md:52` NOT TESTED; homepage `Exchange Program` not echoed PDP.
- **Direction:** PDP badge `14-Day Hassle-Free Return ✓` + `Exchange value up to Tk12k → doorstep inspection → OTP` cross-category next (fridge→washer etc.) — static inspection truth first; AI diagnostics cross-category 10-step after ops.
- **User Value:** Idle second fridge/washer becomes currency; risk-free return expected after Daraz Aug 2025.
- **Dependencies:** Valuation feed; doorstep inspection ops.

---

## H. Account & Customer Retention

### INV-C05 Human Support Spine (WhatsApp/Messenger + Hotline-Sticky + Schedule Visit)
- **Priority:** P0 sticky hotline + P1 WhatsApp | **Type:** NEW CAPABILITY — Source: `page-analysis.md:14` Need help trigger + `page-analysis.md:18-19` 16212 9AM–9PM `issue-register.md:36` CART-01 dead-end, blended
- **Problem:** `Need help? Click Here` not conversational; footer-only hotline; PDP `Share` lacks WhatsApp; Tier-2/3 high-ticket needs voice/chat before cart.
- **Direction:** Sticky 16212 call bar on PDP/Cart + 3-store stock + `Schedule your visit` linkage to existing Mapbox Store Locator `page-analysis.md:199-204` (wire, not rebuild). PDP `Share via WhatsApp — Ask agent about this fridge` deep-link + hotline fallback; optional premium manager for >Tk50k (ChalDal Premium Care model) deferred.
- **User Value:** Human reassurance for Tk80k+ collective purchase; share for family huddle.
- **Dependencies:** WhatsApp deep-link; store inventory from INV-13; low.

### INV-32 Authentication UX (OTP + Guest→Auth Continuity)
- **Priority:** P1 | **Type:** FIX — Source: Phase 2 AUTH-01/02 P2 `issue-register.md:39-40` `page-analysis.md:192-195` two textboxes + phone-only, Wishlist guest inert `issue-register.md:40`
- **Problem:** Split-field OTP slows entry; guest wishlist/compare appear inert without inline prompt; `viewHistory/compareQueue/searchHistory` not migrated on login.
- **Direction:** Single tel input with +880 mask `autocomplete=tel` + format hint replacing two textboxes; guest tap → toast `Saved for now — log in to keep across devices` + Log In affordance; localStorage→account memory migration on OTP. Deferred social/password.
- **User Value:** Save persists across devices; auth friction at cart/wishlist/compare eased.
- **Dependencies:** INV-22 store; auth handoff logic.

### INV-22 Resumption also retention — listed in B.

---

## I. Personalization

### INV-06-advanced & INV-15 are captured under B/H — no additional. Personalized ranking Stage2 of INV-C03 is the sole behavioral ranking layer.

---

## J. New Differentiators & Growth

### INV-25 Complete-the-Setup Bundles & Consumable Attach
- **Priority:** P2 pilot | **Type:** NEW CAPABILITY — Source: `opportunity-pool.md:70-84`
- **Problem:** Thin single cross-sell `product-page-variations.md:65-66` `ecommerce-capabilities.md:56` FBT NOT OBSERVED.
- **Direction:** Curated attach rule engine per family (AC→stabilizer/bracket, TV→mount/soundbar) as PDP bundle row + Cart grouping. Suppress low-ticket. Purifier cartridge cadence phase2. Curated pilot over full catalog FBT.
- **User Value:** One-trip ownership; recurring consumable convenience.
- **Dependencies:** Family→attach mapping (shared Family Graph) + bundle price delta.

---
*All 25 initiatives mapped to P0/P1/P2/LATER with strategic area. No UI specs. See dependency-map for hard/soft sequencing.*

