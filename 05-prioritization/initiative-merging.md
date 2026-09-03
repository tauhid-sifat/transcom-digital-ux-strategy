# Initiative Merging — Phase 5 Step 2: Deduplication & Initiative Consolidation

> **Phase:** 5 Step 2 — Deduplication & Initiative Merging  
> **Date:** 2026-09-03  
> **Status:** Step 2 Complete — consolidated, not yet prioritized/sequenced  
> **Input:** `05-prioritization/master-initiative-inventory.md` (34 initiatives, 55 candidate rows)  
> **Evidence base:** `00-input/sitemap-analysis.md` · `01-current-state/*` · `02-ux-audit/issue-register.md:7-46` (32 registered, 40 rows) · `03-opportunities/duplicates-and-overlaps.md` (38→15, Clusters C1–C9) · `03-opportunities/cross-review.md:32-73` (fate table) + `:126-138` (clusters) · `04-benchmark/pattern-library.md:22-165` (12 problems, 38 variations) · `04-benchmark/applicability-review.md:22-152` (15 OPP validated/enhanced/questioned + 8 NEW) · `04-benchmark/new-opportunities.md:7-14`

**Method (per task):** Identify exact duplicates, similar ideas, parent/child, overlapping capabilities, different solutions to same root problem. Example directive: `Product Comparison vs Better Product Comparison vs AI Product Comparison → one root with layers`. Root = user problem / capability outcome; layers = maturity / instantiation / channel / surface. A `FIX` repairs gated/broken/missing feedback where VERIFIED control exists; `IMPROVEMENT` evolves thin/inconsistent; `NEW CAPABILITY` introduces net-new (`NOT OBSERVED` in `01-current-state/ecommerce-capabilities.md`). Merge only when single build unit, shared data/component, shared placement, and same journey moment — otherwise document as **parent/child or sibling wiring** and keep distinct.

---

## 1. Before / After Counts

| Dimension | Before (master inventory) | After (consolidated) | Δ |
|-----------|---------------------------|----------------------|---|
| **Total initiatives** | **34** (`master-initiative-inventory.md:27`) | **25** | **−9 (−26.5%)** |
| FIX | 13 (inventory states 13; 14 rows incl. INV-27 FIX/NEW counted as FIX) | **8** | −5 |
| IMPROVEMENT | 6 | **2** | −4 |
| NEW CAPABILITY | 15 | **14** | −1 |
| HYBRID (FIX→NEW system) | 0 (INV-27 filed as FIX) | **1** (INV-C06 Cart & Feedback — FIX hygiene + NEW drawer/stepper) | +1 |

> Reconciliation: 34 − (6 merges collapsing 15 source INVs → 6 consolidated) = 34 − 9 = 25. Classification shift reflects merges across types (e.g., INV-15 NEW + INV-18 FIX → INV-C04 counted as FIX; INV-29 NEW + INV-30 IMPROVEMENT → INV-C05 counted as NEW).

### Before breakdown (for audit)

| Type | IDs (34) |
|------|----------|
| FIX (13) | INV-01, INV-02, INV-03, INV-04, INV-05, INV-09, INV-10, INV-11, INV-18, INV-19, INV-27, INV-31, INV-32, INV-34 *(14 rows, 13 counted — INV-27 hybrid counted once)* |
| IMPROVEMENT (6) | INV-06, INV-12, INV-30 + 3 subsumed IMPROVEMENT notes filed inside INV-04/INV-13 context *(inventory `:29`)* |
| NEW (15) | INV-07, INV-08, INV-13, INV-14, INV-15, INV-16, INV-17, INV-20, INV-21, INV-22, INV-23, INV-24, INV-25, INV-26, INV-28, INV-29, INV-33 *(15 counted; INV-33 absorbs OPP-06+NEW-07)* |

### After breakdown (25)

| Type | IDs (25) | Note |
|------|----------|------|
| FIX (8) | INV-C01, INV-01, INV-04, INV-C02, INV-C04, INV-C06, INV-32, INV-34 | INV-C04 is FIX-dominant (warranty truth) |
| IMPROVEMENT (2) | INV-06, INV-12 | INV-30 merged into INV-C05 |
| NEW (14) | INV-C03, INV-13, INV-14, INV-16, INV-17, INV-20, INV-21, INV-22, INV-23, INV-24, INV-25, INV-26, INV-28, INV-33 | INV-C05 filed as NEW (human care is net-new deep-link) |
| HYBRID FIX/NEW (1) | INV-C06 | Explicit FIX+NEW system |

---

## 2. Every Merge Decision with Reasoning & Source IDs

> 6 consolidations collapse 15 source INVs → 6. All other INVs **kept distinct** — rationale in §4. Each merge cites duplicate type and evidence.

| # | Consolidated ID | Source INVs → Consolidated | Duplicate Type | Root Problem (one) / Layers | Reasoning & Evidence | Fate |
|---|-----------------|----------------------------|----------------|-----------------------------|----------------------|------|
| **M-01** | **INV-C01 — IA & Discoverability Hygiene** | **INV-02 + INV-03 + INV-05 → INV-C01** | **Exact duplicate / Overlapping capability — different IA hygiene symptoms, one build domain** | **Root:** Category hierarchy & URL truth is unfindable / non-canonical. **Layers:** (a) URL namespace hygiene — flat PDP + orphan `/tv-av` + trailing-hyphen slugs, (b) Canonical hygiene — brand PLP vs search brand-filter duplication, (c) Tile→taxonomy alignment — Shop By Category `Dishwashers` vs sitemap. | All three are IA/seo crawl hygiene, same squad (IA + sitemap), same deliverable `sitemap.xml` + routing + redirect table. `02-ux-audit/issue-register.md:8-11` IA-01 P1, IA-02 P2, IA-04 P2 + `issue-register.md:12` NAV-02 P2 + `issue-register.md:16` DISC-04 P2. `00-input/sitemap-analysis.md:27` 101 PDPs flat at root · `:74-77` orphan `/tv-av` · `:132-134` trailing hyphens · `:26-28` 13 brand slugs vs `search?Brand=` indexed. `03-opportunities/cross-review.md:234-243` M-02 (IA wall + flat URLs + `/undefined`) and M-07 (brand canonical + tile mismatch) flagged as *same remediation backlog*. Building slug guard, orphan page, canonical, and tile map separately triples sitemap/redirect QA. Inventory already merged IA-01+IA-02+IA-04 inside INV-02 — this extends that merge to canonical + tile, which share the same IA decision. | **MERGE 3→1** (−2) |
| **M-02** | **INV-C02 — PLP Browse Controls Hygiene** | **INV-09 + INV-10 + INV-11 → INV-C02** | **Different solutions to same problem — one root: PLP cannot be narrowed/sorted with confidence** | **Root:** Filter/sort on PLP lacks feedback, clarity, and taxonomy truth → Journey B shortlist stalls (`02-ux-audit/executive-summary.md:50` highest friction cluster). **Layers:** (a) Active-filter feedback — chips/summary/clear-all (INV-09), (b) Sort & pagination model — enumerated sorts + `Showing 1–12 of 44` (INV-10), (c) Facet taxonomy repair — suppress empty Customer Review, merge Screen→Display Size, single price control (INV-11). | All three are **FIXes** of VERIFIED controls (`01-current-state/ecommerce-capabilities.md:16-22` filters/sort headings VERIFIED + `product-discovery.md:74-88` facets) where gap is missing feedback/taxonomy, not missing capability. `03-opportunities/duplicates-and-overlaps.md:144-150` already reclassified ECS-07 (filter/sort chips) and ECS-06 cart hygiene as *remediation* not opportunity — inventory re-elevated them as FIXes INV-09/10/11; they belong as one PLP-control hygiene release. `02-ux-audit/issue-register.md:20` FILTER-01 P1 + `:21-23` FILTER-02 P2/03/04 + `:24-25` SORT-01 P1/SORT-02 P2 share same PLP header (`page-analysis.md:75-86` sidebar + `Select Sort Option` + `Show 12`) and same `CART-02` hygiene family. Three code owners, one PLP template, one QA pass. | **MERGE 3→1** (−2) |
| **M-03** | **INV-C03 — Intelligent Search & Recovery** | **INV-07 + INV-08 → INV-C03** | **Parent/Child — two moments of one Search Experience; staged maturity (pre-submit vs post-submit)** | **Root:** Search fails to get `FTKL12TV16WD / H55P7UX` buyers to product (`02-ux-audit/issue-register.md:17-19` SEARCH-01 P1/02/03). **Layers:** (a) Stage 1 *Intelligent Typeahead* — debounced autocomplete + recent + scented placeholder (INV-07), (b) Stage 2 *Zero-Result Recovery* — did-you-mean + typo tolerance + facet relaxation (INV-08). | Inventory kept them distinct (INV-07 NEW Stage1, INV-08 NEW) following `03-opportunities/cross-review.md:99-105` C7 (foundation vs personalization) and `:164` C8 distinct recovery. `03-opportunities/duplicates-and-overlaps.md:99-105` Cluster C7 notes foundation vs personalization are stages — same index. At Step 2 granularity, they are **one search capability with two acceptance criteria**: typeahead *reduces* typos, recovery *catches* remaining typos. Same header input (`page-analysis.md:9` `Search Here`) + same suggestion index + same `Show 12` PLP output (`page-analysis.md:84`). `04-benchmark/pattern-library.md:96-104` Problem 7A/7B/7C groups autocomplete, recent, and zero-result under single Problem 7. `04-benchmark/applicability-review.md:83-92` OPP-07 VALIDATED + OPP-08 VALIDATED share wiring and should be tracked as one search epic with Template+Synonyms before fuzzy engine. | **MERGE 2→1** (−1) — *staged layers inside one initiative, 2 gates* |
| **M-04** | **INV-C04 — Spec Literacy & Warranty Truth** | **INV-15 + INV-18 → INV-C04** | **Exact duplicate on warranty legend + parent/child — literacy prerequisite + fix propagation, different solutions to PDP-05 trust erosion** | **Root:** Spec/warranty opaque at price exposure → buyer leaves to Google, warranty distrust. **Layers:** (a) Jargon decoder & energy translator + warranty legend CMS (INV-15), (b) Warranty nomenclature repair & trust-claims propagation to PDP/Cart price context (INV-18). | Direct duplication: INV-15 proposes `Special Component = Compressor/Panel/Motor per category` glossary (`product-page-variations.md:61` `Service-24M/Parts-24M/Compressor-120M` vs `Motor-300M` vs `Special 60M`) and INV-18 proposes *same legend* normalized (`master-initiative-inventory.md:259` explicitly `Normalize warranty legend per INV-15`). `02-ux-audit/issue-register.md:29-30` PDP-04 P2 + PDP-05 P2 + `issue-register.md:35` TRUST-01 P2 share PDP tabs `Specification/Feature` (`product-page-variations.md:57-61`). `04-benchmark/applicability-review.md:105-109` VALIDATED groups them as one literacy layer feeding OPP-09/12. Building glossary without fixing `Parts-0M` display, or fixing display without glossary, each leaves PDP-05 half-broken. | **MERGE 2→1** (−1) |
| **M-05** | **INV-C05 — Human Support Spine** | **INV-29 + INV-30 → INV-C05** | **Different solutions to same problem — reassurance before cart; overlapping capability (human voice/chat + store bridge)** | **Root:** Tier-2/3 high-ticket needs human reassurance *in funnel*, not footer-only (`02-ux-audit/issue-register.md:35` TRUST-01 P2). **Layers:** (a) Conversational care — WhatsApp/Messenger PDP deep-link + Share + premium manager (INV-29), (b) Hotline-sticky spine — elevate `16212 9AM–9PM` to sticky bar + Schedule Store Visit linkage + Track Order/Service wiring (INV-30). | `01-current-state/page-analysis.md:14` `Need help? Click Here ` + `:18-19` `16212` footer-only + `:199-204` Store Locator `Schedule your visit` + `:7` `Track Order/Service` are same support surface split across header/footer/locator. `04-benchmark/new-opportunities.md:10-11` NEW-04 + NEW-05 and `applicability-review.md:147-149` explicitly pair them as **12C** `WhatsApp/Messenger + Hotline` composite (regional Finding 7 `101-110` Facebook Commerce + ChalDal Premium Care). Same ops dependency (agent roster + store inventory), same PDP/Cart sticky placement, same trust wiring as `TRUST-01`. Two tickets would double-count one voice/chat spine. | **MERGE 2→1** (−1) — *IMPROVEMENT (hotline exists) + NEW (WhatsApp) = one spine* |
| **M-06** | **INV-C06 — Cart Drawer & Feedback System** | **INV-27 + INV-31 + INV-19 → INV-C06** | **Overlapping capability + parent/child — three PDP→Cart transition symptoms, one FEEDBACK-01 system** | **Root:** PDP→Cart purchase intent stalls — no landed-cost truth, undiscoverable checkout, duplicate CTAs, no confirmation → duplicate clicks/abandon (`02-ux-audit/issue-register.md:36` CART-01 P1 + `:37` CART-02 P2 + `:38` CHECKOUT-01 P1 + `:42` FEEDBACK-01 P1 + `:34` PDP-09 P3). **Layers:** (a) Drawer/stepper/landed-cost breakdown + empty-state recovery (INV-27), (b) Toasts & persistence confirmation + guest inline prompt (INV-31), (c) CTA hierarchy — deduplicate `Add To Cart ×2` to sticky primary + Compare/Wishlist secondary (INV-19). | INV-27 description *already includes* toasts (`master-initiative-inventory.md:349` `progress stepper + trust micro-copy; feedback toasts on every add/wishlist/compare (repairs FEEDBACK-01)`) and INV-31 is literally FEEDBACK-01 (`master-initiative-inventory.md:381-389`). INV-19 (`Add To Cart ×2` `page-analysis.md:126-128`) is role distinction within same drawer system — without fixing CTA hierarchy, drawer trigger is ambiguous; without drawer, toast has no surface. `04-benchmark/new-opportunities.md:12` NEW-06 elevated from `03-opportunities/cross-review.md:67` remediation tail M-01 and `04-benchmark/pattern-library.md:164` 12D groups drawer+stepper+toast as one STANDARD pattern; `ecommerce-capabilities.md:36-44` empty cart/wishlist/compare shells share one `localStorage` wiring with INV-22/32. | **MERGE 3→1** (−2) |

**Total merged:** 6 consolidations × (3+3+2+2+2+3 = 15 source INVs) → 6 consolidated = **net −9**.

---

## 3. Parent / Child Relationships (Hierarchy after Merging)

> Bold = consolidated parent. Indented = child layers shipped as gates/phases inside parent. Sibling wiring (shared table but distinct build) noted separately.

```
INV-C01  IA & Discoverability Hygiene  (FIX parent)
  ├─ (child) URL Namespace Hygiene — flat PDP + orphan /tv-av + trailing-hyphen slugs [ex-INV-02]
  ├─ (child) Canonical Strategy — brand PLP vs search brand filter [ex-INV-03]
  └─ (child) Tile↔Taxonomy Alignment — Dishwashers & Shop By Category [ex-INV-05]
  → depends on INV-01 fix shipping first (P0 /undefined guard)

INV-C02  PLP Browse Controls Hygiene  (FIX parent)
  ├─ (child) Active Filter Feedback — chips/summary/clear-all [ex-INV-09]
  ├─ (child) Facet Taxonomy Repair — suppress empty Review, merge Screen→Display Size, single price control [ex-INV-11]
  └─ (child) Sort & Pagination Model — enumerated sorts + Showing 1–12 of N [ex-INV-10]
  → sibling wiring: INV-20 Social Proof populates empty Review facet after INV-C02 suppresses it until n≥5

INV-C03  Intelligent Search & Recovery  (NEW parent, 2 gates)
  ├─ Gate 1 (P0) Typeahead — autocomplete + recent + scented placeholder [ex-INV-07 Stage1]
  ├─ Gate 2 (P2) Personalized Ranking — affinity-biased ranking [ex-INV-07 Stage2]
  └─ Gate 1b (P1b) Zero-Result Recovery — did-you-mean + typo + facet relax [ex-INV-08]
  → shares index with INV-C02 facet relax; feeds INV-24 finder CTA Try AC Finder

INV-C04  Spec Literacy & Warranty Truth  (FIX/NEW parent — content prerequisite)
  ├─ (child) Jargon Decoder & Energy Translator — tap-any-term drawer, EER→Tk/mo, energy label [ex-INV-15]
  └─ (child) Warranty Truth Propagation — Parts/Special/Motor legend + trust claims at price [ex-INV-18]
  → sibling: INV-21 Authenticity (same price context, two-layer trust with INV-20) + INV-12 dimension overlay + INV-14 energy row

INV-C06  Cart Drawer & Feedback System  (FIX/NEW parent)
  ├─ (child) CTA Hierarchy — single sticky Add To Cart + secondary Compare/Wishlist [ex-INV-19]
  ├─ (child) Drawer/Stepper/Landed-Cost — mini-cart, Showing 1–12 of N, Subtotal+Delivery+Install→Total, stepper Cart→Delivery→Payment→Confirm [INV-27 core]
  ├─ (child) Toasts & Persistence — animated count + inline guest prompt [ex-INV-31]
  └─ (child) Empty-State Recovery — inject INV-22 rails + Continue Shopping [INV-27 wiring]
  → shares zone/fee table with INV-13/14/26/28; depends on INV-32 auth migration for persistence

INV-C05  Human Support Spine  (NEW/IMPROVEMENT parent)
  ├─ (child) Conversational Care — WhatsApp/Messenger PDP deep-link + Share + premium manager [ex-INV-29]
  └─ (child) Hotline & Store Bridge — sticky 16212 + nearest 3 stores + Schedule Visit + Track wiring [ex-INV-30]
  → shares store inventory with INV-13 pickup alt; trust companion to INV-21/20

Sibling wiring (kept distinct — overlapping capability but separate build units, single shared table):
  Fulfillment Confidence Platform  (NOT merged — documented as siblings):
    INV-13 Delivery & Serviceability Estimator (pincode→ fee/SLA/store alt)
    INV-14 True Cost & EMI Planner (ownership row + tenure picker + verdict)
    INV-26 Plural Payment Row (district-aware COD/bKash/Card-on-Delivery + EMI)
    INV-28 Open-Box Delivery + OTP (eligibility badge + doorstep protocol)
    INV-C06 landed-cost truth row & INV-C05 store bridge
    → single table: District→Zone/SLA + delivery fee + install fee + store inventory (applicability-review.md:158-169)

  Trust Stack at Price Context (siblings):
    INV-C04 Spec/Warranty + INV-20 Social Proof + INV-21 Authenticity
    → same PDP hero lockup near price, same moderation/authenticity narrative (applicability-review.md:142-144)

  Resumption Store (siblings, no merge):
    INV-07 Recent Searches + INV-22 Recently Viewed + INV-23 Compare queue + INV-29 Share URL → same localStorage viewHistory+lastPlpUrl+compareQueue+searchHistory, migrated via INV-32

Other parent/child documented in inventory and preserved:
  INV-24 Guided Selling Framework (umbrella) → lenses AC / Fridge (bag+guard) / TV / Washer / Kitchen-Purifier [ex-EDS-01–04+09, FEA-02, ECS-11] — one framework, 5 content packs + buying-guides hub INV-04 as enabler
  INV-12 Rich Media (zoom/pinch → functional video → 360°/dimension overlay + AR) — one viewer pipeline, phased
  INV-16 Installation Feasibility Checker (Gate1 content) → Gate1b priced basket SKU + Gate2 Slot Booking (ops-gated, inside same INV filed as Gate2)
```

---

## 4. Final Consolidated Initiative List — 25 Initiatives

> New IDs `INV-C01..C06` are merges; single-source INVs retain original INV-## for traceability. Type shown is post-merge classification. Source column maps to `master-initiative-inventory.md:39-73` and ultimate deps `02-ux-audit/issue-register.md`.

| # | Final ID | Initiative Name | Type | Source INVs | Primary Evidence | Notes |
|---|----------|-----------------|------|-------------|------------------|-------|
| 1 | **INV-C01** | **IA & Discoverability Hygiene — Flat PDP, Orphan `/tv-av`, Trailing-Hyphen, Canonical & Tile Alignment** | FIX | **INV-02 + INV-03 + INV-05** | `00-input/sitemap-analysis.md:27,74-77,132` · `02-ux-audit/issue-register.md:8-12,16` · `01-current-state/site-inventory.md:112` | 3→1 merge M-01; sitemap/redirect/canonical single release |
| 2 | **INV-01** | Repair Broken Browse Paths (`/undefined` See All) | FIX | INV-01 | `02-ux-audit/issue-register.md:7` NAV-01 P0 · `page-analysis.md:56-57` VERIFIED | Kept distinct — P0 blocker, ships before C01 |
| 3 | **INV-04** | SEO Architecture — Move Buying-Guide Wall Below Fold, Buying-Guide Hub | FIX | INV-04 | `02-ux-audit/issue-register.md:10` IA-03 P1 · `page-analysis.md:90-91` · `applicability-review.md:64-66` STANDARD | Kept distinct — enabler for INV-24; IA fix vs finder NEW |
| 4 | **INV-C02** | **PLP Browse Controls Hygiene — Chips, Sort, Pagination, Facet Repair** | FIX | **INV-09 + INV-10 + INV-11** | `02-ux-audit/issue-register.md:20-25` FILTER-01 P1/SORT-01 P1 · `page-analysis.md:75-86` · `duplicates-and-overlaps.md:144-150` | 3→1 merge M-02 |
| 5 | **INV-06** | Homepage Prioritization & Performance Budget | IMPROVEMENT | INV-06 | `02-ux-audit/issue-register.md:13,46` DISC-01 P1/MOBILE-01 P2 · `page-analysis.md:48-54` | Kept distinct — triage, not affinity reorder (OPP-15 QUESTIONED) |
| 6 | **INV-C03** | **Intelligent Search & Recovery — Autocomplete + Recent + Recovery** | NEW CAPABILITY (gated) | **INV-07 + INV-08** | `02-ux-audit/issue-register.md:17-19` SEARCH-01-03 · `pattern-library.md:99-103` Problem 7 · `applicability-review.md:83-92` | 2→1 merge M-03; Gate1 P0, Recovery P1b |
| 7 | **INV-12** | Rich Media Inspection — Zoom, Pinch, Video, 360°, Dimension Overlay & AR | IMPROVEMENT | INV-12 | `02-ux-audit/issue-register.md:26` PDP-01 P1 · `pattern-library.md:60-67` Problem 4 | Kept distinct — phased viewer pipeline |
| 8 | **INV-13** | Delivery & Serviceability Estimator — Pincode-First Landed Cost + Fast Badge | NEW | INV-13 | `02-ux-audit/issue-register.md:27` PDP-02 P1 · `applicability-review.md:46-49` ENHANCED · `pattern-library.md:26-31` | Kept distinct — fulfilment engine anchor; shares table with C06/14/26/28 |
| 9 | **INV-14** | True Cost & EMI Planner — Ownership Row + Tenure Picker + Eligibility Verdict | NEW | INV-14 | `02-ux-audit/issue-register.md:31,44` PDP-06 · `applicability-review.md:94-98` ENHANCED · `pattern-library.md:72-80` | Kept distinct — financing/energy row vs delivery |
| 10 | **INV-C04** | **Spec Literacy & Warranty Truth — Jargon Decoder + Energy Translator + Warranty Legend Propagation** | FIX | **INV-15 + INV-18** | `02-ux-audit/issue-register.md:29-30,35` PDP-04/05 + TRUST-01 · `product-page-variations.md:57-61` | 2→1 merge M-04; content-only prerequisite |
| 11 | **INV-16** | Installation Feasibility Checker — Pass/Fail Verdict + Priced Basket (Gate2 Booking ops-gated) | NEW | INV-16 | `02-ux-audit/issue-register.md:28` PDP-03 P1 · `applicability-review.md:110-117` ENHANCED · `pattern-library.md:132-137` | Kept distinct — content Gate1 first |
| 12 | **INV-17** | Variant & Family Navigator — Sibling Chips with Delta & Stock | NEW | INV-17 | `02-ux-audit/issue-register.md:33` PDP-08 P2 · `applicability-review.md:118-122` VALIDATED | Kept distinct — family graph |
| 13 | **INV-20** | Social Proof Pipeline — Ratings, Review Count, Badges, Customer Review Facet, Q&A | NEW | INV-20 | `02-ux-audit/issue-register.md:32,21` PDP-07 P1/FILTER-02 · `applicability-review.md:124-126` ENHANCED | Kept distinct — pipeline before badges |
| 14 | **INV-21** | Authenticity / Authorized-Retailer Badging at Price Context | NEW | INV-21 | `applicability-review.md:142-144` NEW-01 STANDARD BD · `sitemap-analysis.md:26` 13 brands | Kept distinct — two-layer trust companion to INV-20 |
| 15 | **INV-22** | Browse Resumption — Recently Viewed Rail + Continue Shopping Deep-Link | NEW | INV-22 | `02-ux-audit/issue-register.md:14` DISC-02 P1 · `applicability-review.md:51-54` VALIDATED | Kept distinct — cheapest retention lift |
| 16 | **INV-23** | Smart Compare Workspace — Persistent, Auto-Populated, Decisive-Attribute & Total-Cost Aware | NEW | INV-23 | `02-ux-audit/issue-register.md:41,15` INTERACTION-01 P1 · `applicability-review.md:56-60` VALIDATED | Kept distinct — Journey D board |
| 17 | **INV-24** | Guided Selling Framework — Need→Constraints→Budget Finder (5 Lenses + Hub) | NEW | INV-24 | `applicability-review.md:62-67` ENHANCED · `pattern-library.md:34-44` Problem 2 | Kept distinct — umbrella + lenses (INV-04 enabler) |
| 18 | **INV-25** | Complete-the-Setup — Bundles, FBT & Consumable Attach (Pre-Add + Cart Grouping) | NEW | INV-25 | `applicability-review.md:69-72` VALIDATED · `pattern-library.md:143-152` | Kept distinct — affinity engine |
| 19 | **INV-26** | Plural Payment Row — COD + bKash/Nagad + Card-on-Delivery + Online/EMI (District-Aware) | NEW | INV-26 | `02-ux-audit/issue-register.md:38` CHECKOUT-01 · `applicability-review.md:144-146` NEW-03 STANDARD BD | Kept distinct — plural row in same zone truth |
| 20 | **INV-C06** | **Cart Drawer & Feedback System — Drawer, Stepper, Landed-Cost Truth, Toasts, CTA Hierarchy** | FIX/NEW | **INV-27 + INV-31 + INV-19** | `02-ux-audit/issue-register.md:36-38,42,34` CART-01/PDP-09/FEEDBACK-01 · `new-opportunities.md:12` NEW-06 · `pattern-library.md:164` 12D | 3→1 merge M-06 |
| 21 | **INV-28** | Open-Box Delivery + OTP Doorstep Verification | NEW | INV-28 | `new-opportunities.md:8` NEW-02 · `applicability-review.md:145` · `pattern-library.md:162` 12B | Kept distinct — doorstep protocol |
| 22 | **INV-C05** | **Human Support Spine — WhatsApp/Messenger + Hotline + Store Visit** | NEW/IMPROVEMENT | **INV-29 + INV-30** | `page-analysis.md:14,18-19,199-204` · `new-opportunities.md:10-11` NEW-04/05 · `pattern-library.md:163` 12C | 2→1 merge M-05 |
| 23 | **INV-32** | Authentication Friction & Guest→Auth Continuity (OTP, History Migration) | FIX | INV-32 | `02-ux-audit/issue-register.md:39-40` AUTH-01/02 P2 · `personalization-current-state.md:13` | Kept distinct — gate for resumption |
| 24 | **INV-33** | Exchange & Return Value — 14-Day Badge + Cross-Category AI Diagnostics + Timeline | NEW | INV-33 | `02-ux-audit/issue-register.md:43` FEEDBACK-02 P2 · `applicability-review.md:150` NEW-07 EMERGING | Kept distinct — QUESTIONED lifecycle, inventory retained |
| 25 | **INV-34** | Accessibility & Icon System — Labeled Controls, Contrast, Keyboard Order | FIX | INV-34 | `02-ux-audit/issue-register.md:45` ACCESS-01 P2 · `page-analysis.md:7-14` | Kept distinct — WCAG hygiene |

---

## 5. No-Merge Decisions — Kept Distinct with Justification

> All 19 single-source INVs retained as distinct build units. Each was tested against the same duplicate criteria and found to be **not mergeable** despite surface adjacency.

| Kept ID | Title | Why NOT merged (despite adjacency) | Adjacent INVs considered |
|---------|-------|------------------------------------|--------------------------|
| INV-01 | Repair Broken Browse Paths | **P0 blocker distinct from hygiene.** Hydration bug (`/undefined`) is code fix with CI link-check, zero copy — IA hygiene (C01) is sitemap/redirect/canonical design. Merging would hide P0. `cross-review.md:230` M-02 flagged as remediation but NAV-01 is P0. | INV-C01 |
| INV-04 | SEO Architecture | **FIX vs NEW parent/child — fix ships independently.** Moving 1,500-word wall below fold + hub (`page-analysis.md:90-91`) is IA re-layering with SEO equity preservation; wizard (INV-24) is interactive finder that *links* to hub. One can ship without the other; bundling overstates dependency. `applicability-review.md:62-67` ENHANCED notes wrapper vs lens distinction. | INV-24 |
| INV-06 | Homepage Prioritization & Budget | **Subtraction vs addition — opposite polarity.** Cuts 7+ grids/68 images vs adding rails (INV-22/23/25). Merging subtraction with addition would neutralise the performance budget goal (`product-page-variations.md:49` + `cross-review.md:178` M-04). Affinity reorder (OPP-15 QUESTIONED) explicitly deferred — this is hygiene, not personalization. | INV-22, INV-23 |
| INV-12 | Rich Media Inspection | **Asset pipeline vs content — phasing not duplication.** Zoom/pinch (week, no reshoot) vs functional video (brand reels, 15–25s) vs 360°/AR are maturity gates of one viewer but were **already merged** in `duplicates-and-overlaps.md:110-117` C8. Keeping as one IMPROVEMENT with gates is correct; further merging with INV-16 dimension overlay would conflate media viewer with install checker — shared `W×H×D` source is wiring, not build. | INV-16, INV-24 |
| INV-13 | Delivery & Serviceability Estimator | **Shared table ≠ same build.** Shares zone/fee table with INV-14/26/28/C06 but is distinct at PDP Options block (`page-analysis.md:125` `Enable your Location` gate) with SLA/fee/store alt + Fast badge. `duplicates-and-overlaps.md:22-31` C1 already collapsed 3 rows to this anchor — further merging into financing would re-create C1+C9 overlap that `cross-review.md:126-138` correctly kept separate. | INV-14, INV-26, INV-28 |
| INV-14 | True Cost & EMI Planner | **Financing vs fulfilment — different row, different owner.** EMI bank/tenure/form-latency (`applicability-review.md:94-98` Pickaboo 32 banks) + energy `Tk/mo` (`pattern-library.md:90-92`) is PDP pricing-block row, district-aware but finance-owned; delivery is ops-owned. `duplicates-and-overlaps.md:120-128` C9 kept EMI+energy as one row — correct, no further merge. | INV-13, INV-26 |
| INV-16 | Installation Feasibility Checker | **Checker vs booking — sequential gates, not duplicates.** `cross-review.md:157` `Checker before Booking`. Gate1 is content toggles → pass/fail verdict (`pattern-library.md:132-137` Problem 10A AC outdoor wall/drain); Gate2 is calendar/slot capacity ops-gated. Merging with INV-12 overlay would mix viewer with verdict; merging with INV-13 delivery would mix serviceability (can deliver?) with feasibility (can install?). Inventory correctly files Gate2 inside same INV as deferred phase. | INV-12, INV-13 |
| INV-17 | Variant & Family Navigator | **Only family-graph proposal — no duplicate.** `duplicates-and-overlaps.md:139` FEA-04 alone · `product-page-variations.md:52` only AC has `Choose Ton`. Merging with INV-23 compare or INV-13 estimator would hide catalog modeling work (model_root→variants). | INV-23 |
| INV-20 | Social Proof Pipeline | **Pipeline vs badge — two-layer trust but distinct.** Ratings pipeline (`pattern-library.md:87-90` Problem 6B collection→moderation→aggregation→badges) vs authenticity proof (INV-21 DarazMall). `applicability-review.md:124-126` ENHANCED pairs them as companions, not duplicates — building badges without pipeline yields fake `5.0 (1)`. | INV-21, INV-C04 |
| INV-21 | Authenticity Badging | **Proof vs peer — different trust mechanism.** `Original Product Guaranteed` reuse of 13 authorized brands (`sitemap-analysis.md:26`) + `replacement + 3× if fake` guarantee is institutional proof; INV-20 is peer validation. `applicability-review.md:142-144` NEW-01 STANDARD BD is *complement* to ratings, not layer. | INV-20, INV-C04 |
| INV-22 | Browse Resumption | **Store share ≠ build merge.** Shares `localStorage` with INV-07/23/29 but is distinct rail + deep-link placement (`personalization-current-state.md:9-10` NOT OBSERVED). `duplicates-and-overlaps.md:34-42` C2 already merged 3 rows correctly — further merging with search would mix retention with discovery. | INV-07, INV-23 |
| INV-23 | Smart Compare | **Board vs family vs resumption — layers already merged.** `duplicates-and-overlaps.md:46-54` C3 correctly merged PER-03+FEA-08+EDS-08 to this workspace; merging with INV-17 family chips or INV-22 rail would re-add bundled placements as false duplicates. | INV-17, INV-22 |
| INV-24 | Guided Selling Framework | **Umbrella + 5 lenses — already merged, kept as one.** `duplicates-and-overlaps.md:58-71` C4 collapsed 7 rows (FEA-02 + EDS-01–04+09 + ECS-11). Further merging with INV-04 hub would be parent/child kept distinct for IA reasons above; merging with INV-15 decoder would mix wizard with glossary (`cross-review.md:156` keeps EDS-05 distinct for literacy). | INV-04, INV-15 |
| INV-25 | Complete-the-Setup | **Affinity vs drawer — merchandising vs cart plumbing.** `duplicates-and-overlaps.md:74-82` C5 already merged 3 placements (PDP bundle + cart rail + PLP FBT). Merging with INV-27 drawer would mix rule engine (AC→stabilizer) with drawer stepper — shares family graph but separate build. | INV-27 |
| INV-26 | Plural Payment Row | **Choice row vs financing row — district-aware but card vs COD polarity.** COD/bKash (`regional Finding 4` 75–90% COD) is *choice* hygiene at same price context as EMI eligibility (INV-14) but opposite buyer persona (carded vs uncarded). Building plural row is text + zone availability; EMI row is bank picker + form latency — different UI, same table. | INV-14 |
| INV-28 | Open-Box Delivery + OTP | **Eligibility badge vs estimator — fulfilment protocol, not estimation.** Shares INV-13 zone truth for `Eligible at your pincode` badge but is doorstep protocol (rider opens packings, OTP, photo log `regional Finding 2` Flipkart OBD). `applicability-review.md:145` EMERGING differentiator vs STANDARD estimator — defer Gate2 of fulfilment. | INV-13 |
| INV-32 | Authentication Friction | **Gate for all personalization — distinct fix.** OTP split-field + guest→auth migration (`page-analysis.md:192-195`) is interaction fix + data migration; not duplicative of INV-22/23/31 which *consume* auth state. Merging would hide critical path (`cross-review.md:240` M-05). | INV-22, INV-31 |
| INV-33 | Exchange & Return Value | **Lifecycle vs PDP trust — ops estimator, not social proof.** `duplicates-and-overlaps.md:86-94` C6 already handled wishlist price/stock; NEW-07 `up to Tk 12k → inspection → OTP` + `14-Day ✓` (`regional Finding 8` Daraz 14-day + Flipkart AI diagnostics) is valuation flow distinct from ratings. Keep inventoried but QUESTIONED sequencing per `applicability-review.md:74-81`. | INV-20 |
| INV-34 | Accessibility & Icon System | **WCAG hygiene — distinct from feedback.** Icon-only `  ` (`page-analysis.md:7-14`) + contrast/focus order is audit remediation, not feature. Merging with INV-C06 toasts or INV-C02 chips would conflate ARIA with business logic — keep separate for WCAG tracking. | INV-C02, INV-C06 |

---

## 6. Overlapping Capabilities Kept Distinct — Wiring Map (Not Merged, Documented)

> These pairs share **single data/component** (`applicability-review.md:158-169`) but are separate build units/pl surfaces — merging would collapse distinct user moments.

| Shared Data / Component | Involved Consolidated INVs | Why kept distinct |
|--------------------------|----------------------------|-------------------|
| District→Zone/SLA + Delivery Fee + Install Fee + Store Inventory table | INV-13, INV-14, INV-16, INV-26, INV-28, INV-C05 (store bridge), INV-C06 (truth row), INV-04/24 guard | One table built once, surfaced at 7 placements: PDP estimator (INV-13), ownership row (INV-14), feasibility verdict (INV-16), payment row (INV-26), OBD badge (INV-28), cart truth (INV-C06), store picker (INV-C05). Distinct PDP/Cart/Order surfaces. |
| EMI Bank/Tenure Master + BDT 5k Threshold + Form-Latency Copy | INV-14, INV-23 total-cost pin, INV-26, INV-C06 | Finance-owned eligibility + cart inheritance — different UI: row picker (INV-14), pin row in compare (INV-23), plural radio (INV-26). |
| `W×H×D + ventilation gap + hinge/swing + bracket` Dimension Normalization | INV-12 overlay, INV-16 checker, INV-24 Fridge Validator guard | One enrichment task (`product-page-variations.md:61`), three viewers: gallery overlay (INV-12), verdict drawer (INV-16), validator guard (INV-24). |
| Tariff × EER/kWh → `Tk/mo` Formula + Glossary CMS 25–40 terms | INV-C04 (decoder), INV-14 (energy row), INV-24 explainability | Same `annual kWh × unit rate` `pattern-library.md:90-92`; glossary is CMS, energy row is calculator, finder is explainer — keep separate for content vs calc ownership. |
| Family Graph `model_root → variants by dimension` + Price/Stock Feed | INV-17 chips, INV-23 add-to-compare, INV-12 re-validate, INV-25 attach map | Top 30 roots ≈70% high-ticket (`sitemap-analysis.md:44` Haier 12, Tron 9). Graph drives 4 surfaces but model is one task. |
| `localStorage viewHistory + lastPlpUrl + compareQueue + searchHistory` + Auth Migration | INV-C03 Recent, INV-22 rail, INV-23 queue, INV-29 share URL | Same store, no backend stage1 (`cross-review.md:230` migration via INV-32). Resumption vs search vs compare are different rails on same store. |
| Review Aggregation + Verified-Purchase + Moderation Pipeline | INV-20, INV-21 companion | Pipeline before badges; suppress `n<5 → Be first`. Authenticity (INV-21) is proof layer, not pipeline. |
| Store Locator Feed (`/store-locator` VERIFIED `page-analysis.md:199-204`) | INV-13 pickup alt, INV-C05/INV-28 linkage | Wire, don't rebuild. |

---

## 7. Consolidation Traceability — Every Original INV Mapped

| Original INV (34) | Final ID (25) | Disposition |
|-------------------|---------------|-------------|
| INV-01 Broken Browse | **INV-01** | Keep |
| INV-02 IA Hygiene | **INV-C01** | Merged → C01 |
| INV-03 Canonical | **INV-C01** | Merged → C01 |
| INV-04 SEO Architecture | **INV-04** | Keep |
| INV-05 Tile vs Sitemap | **INV-C01** | Merged → C01 |
| INV-06 Homepage Budget | **INV-06** | Keep |
| INV-07 Intelligent Search | **INV-C03** | Merged → C03 Gate1/2 |
| INV-08 Zero-Result Recovery | **INV-C03** | Merged → C03 Gate1b |
| INV-09 Filter Chips | **INV-C02** | Merged → C02 |
| INV-10 Sort + Pagination | **INV-C02** | Merged → C02 |
| INV-11 Facet Taxonomy | **INV-C02** | Merged → C02 |
| INV-12 Rich Media | **INV-12** | Keep |
| INV-13 Delivery Estimator | **INV-13** | Keep |
| INV-14 True Cost & EMI | **INV-14** | Keep |
| INV-15 Spec Decoder | **INV-C04** | Merged → C04 |
| INV-16 Installation Checker | **INV-16** | Keep |
| INV-17 Variant Navigator | **INV-17** | Keep |
| INV-18 Warranty Propagation | **INV-C04** | Merged → C04 |
| INV-19 PDP CTA Hierarchy | **INV-C06** | Merged → C06 |
| INV-20 Social Proof | **INV-20** | Keep |
| INV-21 Authenticity | **INV-21** | Keep |
| INV-22 Browse Resumption | **INV-22** | Keep |
| INV-23 Smart Compare | **INV-23** | Keep |
| INV-24 Guided Selling | **INV-24** | Keep |
| INV-25 Complete-the-Setup | **INV-25** | Keep |
| INV-26 Plural Payment | **INV-26** | Keep |
| INV-27 Cart Drawer + Checkout | **INV-C06** | Merged → C06 |
| INV-28 Open-Box + OTP | **INV-28** | Keep |
| INV-29 Conversational Care | **INV-C05** | Merged → C05 |
| INV-30 Hotline-Sticky | **INV-C05** | Merged → C05 |
| INV-31 Post-Action Feedback | **INV-C06** | Merged → C06 |
| INV-32 Auth Friction | **INV-32** | Keep |
| INV-33 Exchange & Return | **INV-33** | Keep |
| INV-34 Accessibility | **INV-34** | Keep |

> Verification: 34 source → 6 merges (15→6) = **25 final**. No source dropped — all 34 trace to 25. Sole tail not inventoried remains `PER-09 seasonal broadcast` (`duplicates-and-overlaps.md:149` generic campaign) — correctly excluded per `master-initiative-inventory.md:479`.

---

## 8. Method Note & Audit Trail

1. **Dedup by root-cause capability, not label** — per `master-initiative-inventory.md:6` and `03-opportunities/cross-review.md:126-138` Clusters C1–C9. Re-applied at Step 2 across the 34 to catch **post-inventory overlaps** where FIX tails reinstated as separate INVs (INV-09/10/11, INV-27/31) and NEW complements (INV-29/30, INV-15/18) created adjacent duplicates at the inventory layer.

2. **Severity preserved:** Only one P0 (INV-01 NAV-01) exists — no merge hides it. All merges are P1/P2 FIXes or NEW siblings where co-shipping is lower risk than separate QA.

3. **Benchmark maturity respected:** `STANDARD` (delivery, ratings, search `pattern-library.md:9-18`) kept P0-capable; `EMERGING/DIFFERENTIATOR` (guided selling, OBD, AI exchange) stays P1/P2 with ops feed gate (`applicability-review.md:200`).

4. **Suppression rule carried forward** (`master-initiative-inventory.md:505` + `applicability-review.md:96` BDT 5k threshold): suppress EMI row, energy row, checker, and FBT for Personal Care trimmer/mixer `Tk 3k` (`product-page-variations.md:104`); show authenticity + plural payment everywhere.

5. **Build-once wiring** unchanged from `master-initiative-inventory.md:487-496` / `applicability-review.md:158-169` — table reuse does **not** imply merge; §6 documents wiring without collapsing distinct user moments.

6. **Evidence index for this doc:**

| Claim | File:Line |
|-------|-----------|
| 34 → 25 dedup, 13/6/15 typing | `master-initiative-inventory.md:27-31` |
| 38→15 (26 rows→8 clusters) + 2 remediation + 1 generic tail | `duplicates-and-overlaps.md:6-19` + `:144-150` |
| Fate table + C1–C9 clusters | `03-opportunities/cross-review.md:32-73` + `:126-138` |
| C1 Delivery, C2 Resumption, C3 Compare, C4 Guided Selling (7 rows), C5 Attach, C6 Notifications, C7/C8 Search, C9 True Cost | `duplicates-and-overlaps.md:22-118` |
| 15 OPP validation + 8 NEW + wiring | `04-benchmark/applicability-review.md:22-152` + `:158-169` |
| NAV-01 P0 `/undefined`, IA-01/02/04, IA-03 SEO wall, NAV-02 canonical, DISC-04 tile, FILTER-01/02/03/04, SORT-01/02 | `02-ux-audit/issue-register.md:7-25` |
| PDP-01 rich media .. PDP-09 CTA, TRUST-01, CART-01/02, CHECKOUT-01, AUTH-01/02, FEEDBACK-01/02, ACCESS-01, MOBILE-01 | `02-ux-audit/issue-register.md:26-46` |
| Flat PDP 101 at root, orphan `/tv-av`, trailing hyphen, 13 brand PLPs | `00-input/sitemap-analysis.md:26-28,74-77,132` |
| Header `Search Here`, `Enable your Location` gate, SEO wall, `68 DOM images`, `Add To Cart ×2`, `16212`, Store Locator | `01-current-state/page-analysis.md:9,48-54,56-57,75-86,90-91,113,125-128,159-164,192-195,199-204` |
| Choose Ton 1/1.5 only AC, EMI absent on Haier, warranty `Parts-0M/Motor-300M`, FBT NOT OBSERVED, suggestions NOT FULLY VERIFIED | `01-current-state/product-page-variations.md:49-61` + `product-discovery.md:40-43` + `ecommerce-capabilities.md:12-15,30-32,42-44,55-56` |

---

*Step 2 complete. 25 consolidated initiatives — every merge traceable INV→INV-C with file:line reasoning; no prioritization applied. Next Step 3 will score and sequence the 25.*

