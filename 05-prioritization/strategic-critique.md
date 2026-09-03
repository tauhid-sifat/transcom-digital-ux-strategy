# Strategic Critique — Phase 5 Step 5

> **Role:** Strategic Critic — adversarial review of 25 consolidated initiatives. No idea protected.
> **Inputs:** `05-prioritization/master-initiative-inventory.md:27-535` (34→25) · `05-prioritization/initiative-merging.md:15-277` (6 merges M-01..M-06) · `05-prioritization/value-analysis.md:34-60` (9 VERY HIGH / 9 HIGH / 6 MEDIUM / 1 LOW) · `02-ux-audit/issue-register.md:7-46` (P0=1 P1=13 P2=14 P3=4) · `03-opportunities/opportunity-pool.md:7-244` (15 OPPs, C1–C9) · `04-benchmark/applicability-review.md:22-152` (15 classified VALIDATED/ENHANCED/QUESTIONED + 8 NEW) · `01-current-state/ecommerce-capabilities.md:1-76` (VERIFIED / NOT OBSERVED / NOT TESTED) · `01-current-state/page-analysis.md` + `product-page-variations.md` + `product-discovery.md`
> **Date:** 2026-09-03 · **Method:** 8-question stress test per initiative + portfolio-level redundancy / complexity / evidence check.

---

## Method — 8 Questions Applied to Every Initiative

| # | Question | Fails when |
|---|----------|------------|
| 1 | Does this solve a real, evidenced user problem? | Problem is assumed, generic, or invented for internal hygiene. |
| 2 | Is this merely copying a competitor pattern? | Benchmark cited as justification without Transcom-specific problem evidence. |
| 3 | Does the website actually need this now? | Sequencing wrong — P0/P1 hygiene still broken, or ops dependency not ready. |
| 4 | Is the problem better solved by a simpler UX change? | Content re-layer, copy, suppression, or wiring change achieves 80%. |
| 5 | Is this too complex relative to value? | Build/ops cost, asset pipeline, or maintenance exceeds funnel lift. |
| 6 | Does another initiative already solve this? | Shared table, shared surface, or same journey moment already covered. |
| 7 | Is there sufficient evidence? | VERIFIED gap is missing, or evidence is NOT TESTED / thin (e.g., 7 PDPs). |
| 8 | Is this a feature disguised as innovation? | AR/AI/manager language dresses commodity hygiene as differentiator. |

**Verdict taxonomy:** `APPROVE` (ship as scoped) · `SIMPLIFY` (cut scope, ship lean core now) · `DEFER` (move to P1b/P2, not now) · `VALIDATE FURTHER` (pilot / measure before committing) · `MERGE` (collapse into sibling) · `REMOVE` (drop).

---

## Portfolio Verdict Table — All 25

| # | Final ID | Initiative | Type | Value Class (`value-analysis.md:34-60`) | Verdict | One-line Rationale |
|---|----------|------------|------|------------------------------------------|---------|--------------------|
| 1 | **INV-C01** | IA & Discoverability Hygiene (flat PDP + orphan `/tv-av` + hyphen + canonical + tile) | FIX | HIGH | **SIMPLIFY** | Canonical + hyphen 301 + tile map = hygiene; hierarchical PDP URL migration is high-risk refacto with no observed user URL-reading behaviour. |
| 2 | **INV-01** | Repair Broken Browse Paths (`/undefined` See All) | FIX | VERY HIGH | **APPROVE** | Single P0 — `02-ux-audit/issue-register.md:7` VERIFIED 5+ homepage + 4× `/samsung/undefined`. Code guard + CI check, near-zero cost. Unblocks every downstream OPP. |
| 3 | **INV-04** | SEO Architecture — Move Buying-Guide Wall Below Fold + Hub | FIX | HIGH | **APPROVE** | `01-current-state/page-analysis.md:90-91` 1500+ words push grid below fold on every L1/L2. Re-layer (grid above, prose below, `/buying-guides/{cat}` hub) preserves equity with CSS/order change only. Enabler for INV-24. |
| 4 | **INV-C02** | PLP Browse Controls Hygiene — Chips / Sort / Pagination / Facet Repair | FIX | VERY HIGH | **APPROVE** | `02-ux-audit/issue-register.md:20-25` P1×2 + `01-current-state/product-discovery.md:74-88` facets VERIFIED but feedback missing. One PLP template, one QA pass, sharpest browse bottleneck (`02-ux-audit/executive-summary.md:50`). |
| 5 | **INV-06** | Homepage Prioritization & Performance Budget | IMPROVEMENT | MEDIUM | **SIMPLIFY + DEFER** | Performance budget (lazy-load, 68-image cap, carousel budget) is hygiene — APPROVE as tech debt. Curated hero/category prioritization = deferred until INV-01/C02 prove lift. Affinity reorder already QUESTIONED `04-benchmark/applicability-review.md:128-135` / `03-opportunities/opportunity-pool.md:233-244`. |
| 6 | **INV-C03** | Intelligent Search & Recovery (Autocomplete + Recent + Recovery) | NEW | VERY HIGH | **SIMPLIFY** | Stage 1 autocomplete + recent (localStorage 6) + scented placeholder + synonym `Did you mean` table are P0. Affinity-biased ranking (needs OPP-02 volume) + fuzzy edit-distance 1–2 engine are P2 — VALIDATE with query logs before building. |
| 7 | **INV-12** | Rich Media Inspection — Zoom / Pinch / Video / 360° / Dimension / AR | IMPROVEMENT | HIGH | **SIMPLIFY** | Zoom/pinch + `1/7` count + scrub + dimension overlay `W×H×D+gap+swing` (shared with INV-16) = week, no reshoot, highest anxiety reduction. Functional video → pilot 1 category (AC wall) reusing brand reel; 360°/AR = DEFER to VALIDATE (MOBILE-01 `02-ux-audit/issue-register.md:46` heavy 68 images already). |
| 8 | **INV-13** | Delivery & Serviceability Estimator — Pincode-First Landed Cost + Fast Badge | NEW | VERY HIGH | **APPROVE** | `02-ux-audit/issue-register.md:27` PDP-02 P1 + `01-current-state/page-analysis.md:125` `Enable your Location` gate. District/area text (not GPS — `04-benchmark/applicability-review.md:46-49` Finding 5 sparse pincodes) + shared District→Zone/SLA/fee/store table is platform anchor for INV-14/26/28/C06. |
| 9 | **INV-14** | True Cost & EMI Planner — Ownership Row + Tenure Picker + Verdict | NEW | VERY HIGH | **SIMPLIFY (APPROVE core)** | Static row `Upfront+Delivery+Install+Energy→EMI from Tk/mo @bank` + eligibility verdict `Not available → Bank List` + BDT 5k threshold suppress (`01-current-state/product-page-variations.md:104`) = APPROVE. Interactive tariff/running-hours slider + tenure picker in PDP = DEFER to Cart; validate energy formula after INV-C04 glossary. |
| 10 | **INV-C04** | Spec Literacy & Warranty Truth — Jargon Decoder + Energy Translator + Legend Propagation | FIX | HIGH | **SIMPLIFY (APPROVE core)** | Warranty `Parts-0M / Motor-300M` fix (`01-current-state/product-page-variations.md:61` + `02-ux-audit/issue-register.md:30,35`) + trust propagation to price context = P0 hygiene — APPROVE. Glossar CMS 25–40 terms trimmed to 8–10 decisive terms (EER/R32/inverter/HQLED/tonnage etc.) now; rest VALIDATE after finders. |
| 11 | **INV-16** | Installation Feasibility Checker — Pass/Fail + Priced Basket (Gate2 booking ops-gated) | NEW | HIGH | **SIMPLIFY** | Gate1 content checklist → verdict `✓ Feasible / ⚠ Requires bracket Tk 2,500` is content-only win for AC/Fridge/Washer (`02-ux-audit/issue-register.md:28` PDP-03 P1). Priced basket SKU + Gate2 calendar slot booking = DEFER until slot-capacity feed confirmed (`04-benchmark/applicability-review.md:110-117` ops-gated). Suppress Personal Care. |
| 12 | **INV-17** | Variant & Family Navigator — Sibling Chips with Delta & Stock | NEW | HIGH | **APPROVE** | Only family-graph in pool (`03-opportunities/duplicates-and-overlaps.md:139` FEA-04 alone). `01-current-state/page-analysis.md:86` `Display 55"(10) 43"(7)` proves families exist but PDP has no switcher except AC `Choose Ton` (`01-current-state/product-page-variations.md:52`). Compensates flat PDP IA, high leverage (top 30 roots ≈70%). |
| 13 | **INV-20** | Social Proof Pipeline — Ratings / Review Count / Badges / Facet / Q&A | NEW | VERY HIGH | **DEFER + VALIDATE FURTHER** | Real problem (`02-ux-audit/issue-register.md:32` PDP-07 P1 + FILTER-02 P2 empty heading `01-current-state/product-discovery.md:83`), but supply is zero (`01-current-state/ecommerce-capabilities.md:31-33` tabs headings only, `product-page-variations.md:62` no stars). Building aggregation→badge→facet with `n<5` suppress yields perpetual `Be first to review`. Immediate SIMPLIFY = suppress empty `Customer Review` heading (from INV-C02) + `Be first — ask Q` prompt. Full pipeline DEFER to P2; VALIDATE supply with post-delivery SMS pilot on top 100 SKUs to prove `n≥5`. |
| 14 | **INV-21** | Authenticity / Authorized-Retailer Badging at Price Context | NEW | VERY HIGH | **APPROVE** | No-backend, reuses 13 authorized brands (`00-input/sitemap-analysis.md:26`). PDP hero `✓ Authorized — Official Warranty + replacement 3× if fake` + detail sheet repairs `02-ux-audit/issue-register.md:35` TRUST-01 where homepage `Original Product Guaranteed` (`01-current-state/page-analysis.md:34`) dissipates. Post-Evaly #1 barrier (2–3% penetration) — highest ROI per effort. Companion to INV-20, but ships independently. |
| 15 | **INV-22** | Browse Resumption — Recently Viewed Rail + Continue Shopping Deep-Link | NEW | HIGH | **APPROVE** | `01-current-state/personalization-current-state.md:9-10` + `01-current-state/ecommerce-capabilities.md:55` NOT OBSERVED; empty Cart/Wishlist `01-current-state/page-analysis.md:159-164` no history. `localStorage viewHistory(8)+lastPlpUrl+compareQueue+searchHistory` no backend stage1, cap 8, migrates via INV-32. Cheapest retention lift; delivers 80% of OPP-15 value. |
| 16 | **INV-23** | Smart Compare Workspace — Persistent, Auto-Populated, Decisive & Total-Cost Aware | NEW | HIGH | **SIMPLIFY (APPROVE core)** | Sticky bar `Compare (2/3)` → auto-populated `/compare` (`01-current-state/page-analysis.md:173-178` 3× hand-typed recall vs `page-analysis.md:129` icon `` VERIFIED) + `Highlight differences` wiring = APPROVE. Decisive-attribute tint (6–8 rows), verdict strip, total-cost pin `Price+Install+Energy+EMI` = DEFER until INV-13/14 proven and share URL validated for WhatsApp family huddle. |
| 17 | **INV-24** | Guided Selling Framework — Need→Constraints→Budget Finder (5 Lenses + Hub) | NEW | HIGH | **SIMPLIFY + REMOVE (1 lens)** | Umbrella DIFFERENTIATOR (`04-benchmark/applicability-review.md:62-67` ENHANCED) but 5 lenses = scope explosion. Kitchen/Purifier lens has thin evidence (7 PDPs `03-opportunities/opportunity-pool.md:67` MED) → **REMOVE**. Ship AC Finder only (largest ticket, `Choose Ton` proves family, rule `20 BTU/sq ft` LG `lg.com/.../calculate`) + `/buying-guides/{cat}` hub from INV-04 as pilot. Fridge Validator (AO `18L=1 bag` + 7-step guard) + TV/Washer lenses DEFER to P2 after AC proves filtered-PLP lift. |
| 18 | **INV-25** | Complete-the-Setup — Bundles / FBT & Consumable Attach | NEW | MEDIUM | **SIMPLIFY + DEFER** | Rule engine per family (AC→stabilizer/bracket/wire, TV→mount/soundbar, purifier cartridge cadence) + cart grouped-line pricing is ops-heavy (`01-current-state/ecommerce-capabilities.md:56` FBT NOT OBSERVED, `product-page-variations.md:66-67` thin Related). Handles AOV not funnel unblock. SIMPLIFY to manually curated PDP bundle row + Cart `Complete your setup` rail on top 30 roots ×1 surface now. Full affinity table + cadence = DEFER and VALIDATE with 20-SKU pilot. Suppress low-ticket `Tk 3k` trimmer (`product-page-variations.md:104`). |
| 19 | **INV-26** | Plural Payment Row — COD + bKash/Nagad + Card-on-Delivery + Online/EMI (District-Aware) | NEW | VERY HIGH | **APPROVE** | 75–90% COD + bKash growth (`04-benchmark/applicability-review.md:144-146` Finding 4). PDP today shows `Avail Bank EMI` only for cardholders — excludes majority persona. Co-equal row + district-aware `Delivery to Rajshahi: COD available` from same INV-13 zone matrix, no backend. |
| 20 | **INV-C06** | Cart Drawer & Feedback System — Drawer / Stepper / Landed-Cost Truth / Toasts / CTA Hierarchy | FIX/NEW | VERY HIGH | **APPROVE** | Repairs funnel terminus: duplicate `Add To Cart ×2` (`01-current-state/page-analysis.md:126-128`), no toast (`02-ux-audit/issue-register.md:42` FEEDBACK-01), empty Cart disables Checkout with no recovery (`01-current-state/page-analysis.md:159-164` + `user-journeys.md:126-131`), `Subtotal ৳0` no landed-cost truth. `pattern-library.md:164` 12D STANDARD Apple/ASOS drawer + stepper `Cart→Delivery→Payment→Confirm` + `Subtotal+Delivery+Install→Total` from shared table. |
| 21 | **INV-28** | Open-Box Delivery + OTP Doorstep Verification | NEW | MEDIUM | **SIMPLIFY + DEFER** | Eligibility badge `Eligible for Open Box Delivery at your pincode ✓` from INV-13 zone truth = SIMPLIFY and ship (quick trust signal). Full rider protocol (open outer+brand packing, IMEI check, OTP + photo log — `04-benchmark/applicability-review.md:145` Flipkart OBD) is ops re-engineering for owned fleet, cost for >Tk20k only. DEFER to P2; VALIDATE with Dhaka-only pilot for Tk>50k. |
| 22 | **INV-C05** | Human Support Spine — WhatsApp/Messenger + Hotline + Store Visit | NEW/IMPROV | MEDIUM | **SIMPLIFY** | Sticky `16212 9AM–9PM` bar (`01-current-state/page-analysis.md:18-19` footer-only) + Store Locator linkage (`page-analysis.md:199-204` List/Map + `Schedule your visit` Mapbox) + PDP `Share via WhatsApp — Ask agent` deep-link (pre-filled URL) are no-platform-build wins — APPROVE lean. Premium manager for >Tk50k (ChalDal model `04-benchmark/applicability-review.md:147-149`) implies headcount/roster — DEFER to VALIDATE with ops capacity. |
| 23 | **INV-32** | Authentication Friction & Guest→Auth Continuity (OTP, History Migration) | FIX | MEDIUM | **SIMPLIFY** | Split-field phone input (`01-current-state/page-analysis.md:192-195` two textboxes) → single input + inline guest prompt `Saved — log in to persist` = APPROVE now (hygiene). Social/password alt + `localStorage→account` migration for viewHistory/compareQueue/wishlist = DEFER; value conditional on INV-22/23 proving retention, and COD purchase does not require auth (`04-benchmark/applicability-review.md:52-64` 75–90% COD). Measure desertion before building. |
| 24 | **INV-33** | Exchange & Return Value — 14-Day Badge + Cross-Category AI Diagnostics + Timeline | NEW | MEDIUM | **SIMPLIFY + DEFER** | Static badge `14-Day Hassle-Free Return ✓` next to `In stock` (`01-current-state/product-page-variations.md:58`) + `Exchange value: Estimate up to Tk 12k → doorstep inspection → OTP` beneath price = SIMPLIFY (content-only, expectation repair for `02-ux-audit/issue-register.md:43` FEEDBACK-02 + `ecommerce-capabilities.md:52` opaque `/exchange`). Cross-category + 10-step AI condition check (Flipkart ReCommerce 26 cats `04-benchmark/applicability-review.md:150`) is ops/AI fantasy without ops feed — DEFER to P2; VALIDATE with static valuation + inspection truth first. |
| 25 | **INV-34** | Accessibility & Icon System — Labeled Controls, Contrast, Keyboard Order | FIX | LOW | **APPROVE (hygiene sprint)** | Icon-only `  ` (`01-current-state/page-analysis.md:7-14` + `02-ux-audit/issue-register.md:45` ACCESS-01 P2) fails WCAG. Pair with visible label/aria-label + tooltip, verify contrast/tab order. Not competing with funnel P0 — treat as parallel eng sprint, not prioritized against conversion. |

**Count:** APPROVE 8 · SIMPLIFY 10 (+ 4 SIMPLIFY+DEFER hybrids) · DEFER 3 · VALIDATE 1 standalone (INV-20 supply) · REMOVE 1 lens (INV-24 Kitchen/Purifier) — no full initiative removed, 4 heavily rescoped.

---

## Strong Initiatives Explicitly Approved — Ship As Scoped

These 8 pass all 8 questions, have HIGH-conviction evidence, and are BD-necessary now:

**INV-01** (`02-ux-audit/issue-register.md:7` NAV-01 P0), **INV-04** (`01-current-state/page-analysis.md:90-91` + `04-benchmark/applicability-review.md:64-66` 2D), **INV-C02** (`02-ux-audit/issue-register.md:20-25` + `01-current-state/product-discovery.md:74-88`), **INV-13** (`02-ux-audit/issue-register.md:27` + `04-benchmark/applicability-review.md:46-49`), **INV-21** (`04-benchmark/applicability-review.md:142-144` + `00-input/sitemap-analysis.md:26` 13 brands), **INV-22** (`01-current-state/personalization-current-state.md:9-10` + `04-benchmark/applicability-review.md:51-54`), **INV-26** (`04-benchmark/applicability-review.md:144-146` Finding 4), **INV-C06** (`02-ux-audit/issue-register.md:36-38,42` + `04-benchmark/applicability-review.md:150` 12D).

Plus lean cores approved: INV-17 (family graph), INV-C04 warranty fix, INV-34 sprint.

---

## Detailed Critique — Questionable Initiatives (8-Question Stress Test)

### INV-C01 — IA & Discoverability Hygiene

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Partial.** Canonical confusion (`02-ux-audit/issue-register.md:12` NAV-02 P2) + trailing-hyphen 404 risk (4 slugs `00-input/sitemap-analysis.md:132-134`) + Dishwashers tile/taxonomy mismatch (`01-current-state/page-analysis.md:47`) are real micro-frictions. Flat PDP namespace `/{brand}-{model}` at root (101 PDPs `00-input/sitemap-analysis.md:27` + `01-current-state/site-inventory.md:112`) is an IA smell, but no user evidence that users read or reason about URLs — bounce is not traced to URL form. |
| 2 | Copying competitor? | **Yes, risk.** Hierarchical `/category/product` is SEO best practice (Daraz), but Transcom PDP has compensating context via breadcrumb + INV-17 family chips — copying URL pattern without crawl-revenue proof is orthodoxy. |
| 3 | Need now? | **No for hierarchy.** Canonical/hyphen/tile are P1 hygiene for crawl before any marketplace SEO push. Hierarchical PDP migration needs `NAV-01` stable first (`05-prioritization/initiative-merging.md:70` already notes dependency). Do not bundle with P0. |
| 4 | Simpler UX change? | **Yes.** Family chips (INV-17) + breadcrumb + `?familyRef` preserve traversal without 301 migration. Trailing hyphen = 301 guard, not rebuild. Dishwashers = remove tile or add `/dishwashers` route — content decision. |
| 5 | Too complex? | **Yes for URL rebuild.** Sitemap + redirect table + canonical cascade for 101 PDPs with backlink risk is large; value is SEO throughput not conversion. Isolate high-effort/low-user-visible piece. |
| 6 | Already solved? | **Partially by INV-17.** INV-17 explicitly filed as compensation for flat URL (`05-prioritization/master-initiative-inventory.md:242-248`): `Family compensates by giving PDP explicit family context that URL does not`. Don't pay twice. |
| 7 | Sufficient evidence? | **Mixed.** Sitemap audit HIGH for flat/orphan/hyphen; user-behaviour evidence for URL-induced confusion is LOW. Keep audit-true pieces, park hierarchy. |
| 8 | Feature as innovation? | No — presented as hygiene, not innovation. | 
**Verdict: SIMPLIFY** — Ship canonical (brand PLP as authoritative, `search?Brand=` as filtered view with `rel=canonical`), trailing-hyphen 301s, tile↔taxonomy alignment in one sitemap/redirect release. **DEFER hierarchical PDP URL migration** to VALIDATE with crawl / share-404 rate after INV-17 proves vault discovery. Do not block P0/P1 on URL philosophy.

### INV-06 — Homepage Prioritization & Performance Budget

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes but broad.** `01-current-state/page-analysis.md:48-54` 7+ grids + `product-page-variations.md:49` 68 DOM images + `02-ux-audit/issue-register.md:13,46` DISC-01 P1 / MOBILE-01 P2 = overload + low-bandwidth cost. |
| 2 | Copying? | **Afffinity portion yes.** Full affinity homepage reorder (OPP-15) is explicitly QUESTIONED (`04-benchmark/applicability-review.md:128-135` + `03-opportunities/opportunity-pool.md:233-244`) — no benchmark among 33 validates it as P0/P1; `electronics-commerce.md:236-241` says *Do not build before P0 hygiene*. The INV-06 triage (cut, not reorder) avoids the copy trap, but still risks conflating hygiene with personalization. |
| 3 | Need now? | **Half.** Performance budget is always needed on mobile-first BD; prioritization curation can wait until discovery funnel works. |
| 4 | Simpler change? | **Yes.** Lazy-load + image cap + `Valid Till:` suppressed unless campaign (`product-page-variations.md:56`) + carousel count budget + suppress low-ticket grids below fold is engineering hygiene, not IA redesign. INV-22 rail below hero already gives 80% returner value without scorer (`value-analysis.md:322-323`). |
| 5 | Too complex? | **Curated reprioritization is.** Affinity scorer + modular CMS + governance vs campaign pins (`03-opportunities/opportunity-pool.md:241`) is medium-high vs MEDIUM value funnel leverage. |
| 6 | Already solved? | **By INV-22 + INV-C03 Recent.** Returner continuity does not need homepage reorder when rail + Continue deep-link exists. |
| 7 | Evidence? | **Medium for overload, weak for reorder.** Homepage grids VERIFIED, but reorder lift has weakest evidence and highest CMS dependency per `04-benchmark/applicability-review.md:130-135`. |
| 8 | Innovation disguise? | **Reorder portion yes** — `Affinity reorder` dresses generic curation as personalization. Budget portion is not. |
**Verdict: SIMPLIFY + DEFER** — **APPROVE** performance budget + generic curation trim (image lazy-load, carousel cap) as tech-debt sprint. **DEFER** hero/category re-prioritization until INV-01/C02/C03 lift proven; then A/B `Rail only` vs `Rail + hero reweight` before committing.

### INV-C03 — Intelligent Search & Recovery

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes Stage1, partial Recovery.** `02-ux-audit/issue-register.md:17-19` SEARCH-01 P1 + SEARCH-02 P3 + `01-current-state/product-discovery.md:40-43` typing timed out + `01-current-state/ecommerce-capabilities.md:12-13` dropdown NOT FULLY VERIFIED + `ecommerce-capabilities.md:15` NOT TESTED zero-result = P1. `FTKL12TV16WD / H55P7UX` buyers (`01-current-state/page-analysis.md:111`) have no fast-path. |
| 2 | Copying? | **No for hygiene.** 150–200ms debounce, SKU-boost on 3+ alnums, recent chips 6 are STANDARD (`04-benchmark/pattern-library.md:99-103` 7A). Affinity-biased ranking copies Amazon without volume — that portion is copying. |
| 3 | Need now? | **Stage1 yes, fuzzy no.** Pre-submit typeahead is P0. Zero-result recovery brackets it, but fuzzy QWERTY/Bangla symmetry needs query volume to tune. |
| 4 | Simpler change? | **Yes.** Scented placeholder `Try FTKL12TV16WD or Samsung TV 55"` + brand/category rows + recent localStorage + synonym table (`inverter=invator` etc.) covers ~40% before fuzzy engine (`04-benchmark/applicability-review.md:88-92`). |
| 5 | Too complex? | **Fuzzy engine is.** Edit-distance 1–2 + Bangla digit map + analyzer is medium build for MEDIUM applicability volume. Pair with INV-24 `Try AC Finder` CTA cheaply. |
| 6 | Already solved? | No — only search entry. No duplication in 25; merging INV-07+INV-08 into INV-C03 (`05-prioritization/initiative-merging.md:52`) is correct (same index). |
| 7 | Evidence? | **HIGH Stage1, MED for fuzzy.** Header `Search Here` VERIFIED `01-current-state/page-analysis.md:9` but empty dropdown may be rendering bug not index (`03-opportunities/cross-review.md:205` — re-test before build). Log zero-result queries first. |
| 8 | Innovation? | **Personalized ranking yes** — dresses P2 affinity as P0. Fuzzy as innovation is borderline. |
**Verdict: SIMPLIFY** — Ship Gate 1 (P0): debounced typeahead + SKU boost + brand/category rows + recent chips + scented placeholder. Ship Gate 1b (P1b): zero-result template + synonym table + `Did you mean` + `Remove Brand →N` + advisor CTA to INV-24. **VALIDATE** query logs 4–6 weeks before building fuzzy/Bangla analyzer; **DEFER** affinity ranking until INV-22 volume proves.

### INV-12 — Rich Media Inspection

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes for inspection.** `02-ux-audit/issue-register.md:26` PDP-01 P1 + `01-current-state/ecommerce-capabilities.md:30` Video NOT OBSERVED + `01-current-state/page-analysis.md:134-135` 4+ generics + 68 images `product-page-variations.md:49-51` weight without inspection value. Fit anxiety for 600L/65"/wall piped is real. |
| 2 | Copying? | **Video/AR partially.** Hover/pinch (`pattern-library.md:60-67` 4A STANDARD since ~2018) is expected hygiene; `View TV virtually` AR (`pattern-library.md:67` 4C) is EMERGING differentiator without evidence it lifts Tk sale in low-bandwidth context. |
| 3 | Need now? | **Zoom yes, video staged, AR no.** Considered-high-ticket needs inspection before cart, but asset pipeline scales by category. |
| 4 | Simpler change? | **Yes.** Zoom/pinch + `1/7` count + scrub reuses existing generics with viewer component (week, no reshoot). Dimension overlay `W×H×D+ventilation gap+door swing` shares spec normalization with INV-16 (`05-prioritization/master-initiative-inventory.md:199` + `value-analysis.md:195`). Video is next, not same ship. |
| 5 | Too complex? | **As bundled yes.** Functional video per category template 15–25s muted lazy-loaded (AC wall, TV panel/HDR, washer spin) needs brand reel sourcing + rights; 360°/AR depends on availability. Cost spreads across 101 PDPs. |
| 6 | Already solved? | No — only media inspection. Dimension source shared but viewer vs checker are distinct (`05-prioritization/initiative-merging.md:168`). |
| 7 | Evidence? | **HIGH for gap, MED for asset.** Gallery VERIFIED as placeholder-heavy; video absence is HIGH, but evidence media improves conversion is generic, not BD-bound. |
| 8 | Innovation? | **AR yes** — `AR + View virtually` dresses viewer as flagship innovation on MOBILE-01 heavy page. |
**Verdict: SIMPLIFY** — P1 = zoom/pinch/count/scrub + dimension overlay. Pilot video on one category (AC) reusing Daikin/Samsung reel muted. **DEFER** 360° where asset missing + AR to VALIDATE with dwell/return-rate A/B after zoom.

### INV-14 — True Cost & EMI Planner

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes.** `02-ux-audit/issue-register.md:31,44` PDP-06 P2 + CONSISTENCY-01 P3 + `01-current-state/product-page-variations.md:55` Haier 622IBG no EMI (silent) vs others + `01-current-state/page-analysis.md:114-117` EMI inconsistency + `04-benchmark/applicability-review.md:94-98` Pickaboo 32 banks / Daraz 5–10d form truth missing. Sticker illusion P1. |
| 2 | Copying? | No — row merges BD-specific offline form truth (`blocked → form 3d → bank 5–10d` Pickaboo/Daraz) plus energy `Tk/mo` which few BD retailers combine — differentiator, not copy. |
| 3 | Need now? | **Static row yes, planner no.** Tenure/bank interactivity belongs in Cart after delivery truth, not blocking PDP decision. |
| 4 | Simpler change? | **Yes.** `Upfront × + Delivery Tk0 + Energy ~Tk/mo (1yr/5yr) → EMI from Tk/mo @bank` + BDT 5k suppress (`04-benchmark/applicability-review.md:96` + `product-page-variations.md:104` trimmer Tk3k) as static row + eligibility verdict is 80%. Interactive tariff/running-hours slider is refinement. |
| 5 | Too complex? | **Full planner is.** EMI rule table × bank/tenure + tariff × EER + consumable cadence (`pattern-library.md:72-80` 5A/5B) + cart inheritance. Ship eligibility matrix + energy line first. |
| 6 | Already solved? | Wired to INV-13/26/C06 via single EMI master + zone/fee table (`04-benchmark/applicability-review.md:158-169`) — kept distinct correctly (`05-prioritization/initiative-merging.md:169-170`), but UI moments are distinct (PDP row vs Cart vs plural radio). |
| 7 | Evidence? | **HIGH.** EMI presence/absence inconsistency VERIFIED; 32-bank EMI36 is hygiene but interactive picker + verdict is still EMERGING — threshold evidence solid. |
| 8 | Innovation? | No — presented as truth row, not innovation theatre. Tenure slider as innovation would be. |
**Verdict: SIMPLIFY (APPROVE core)** — Ship static ownership row + verdict + threshold + form-latency disclosure as P0; Cart inherits grouped breakdown. **DEFER** interactive tenure picker + tariff slider to Cart P1; VALIDATE EER→`Tk/mo` formula after INV-C04 glossary ships.

### INV-C04 — Spec Literacy & Warranty Truth

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes.** `02-ux-audit/issue-register.md:29-30` PDP-04 P2 + PDP-05 P2 + `01-current-state/product-page-variations.md:57-61` `R32 / EER 3.15 / Applicable For 120 sq ft` + HQLED/Dolby/Twin inverter/Coanda without explainer + warranty `Service-24M/Parts-24M/Compressor-120M` vs `Motor-300M (25yr)` vs `Special-0M` implausible. Buyer leaves to Google. |
| 2 | Copying? | No — content fix, not pattern copy. Energy A–G+QR fiche is STANDARD EU but needed literacy prerequisite. |
| 3 | Need now? | **Yes as prerequisite.** Unlocks INV-14/16/24 literacy (`04-benchmark/applicability-review.md:105-109`). Content-only, no backend. |
| 4 | Simpler change? | **Yes.** Warranty nomenclature fix + legend row `Special Component = Compressor/Panel/Motor per category` + trust propagation to price context (`01-current-state/page-analysis.md:34` homepage bar echoed) is the critical half. Glossary can be lean. |
| 5 | Too complex? | **If 25–40 terms at once, yes.** Authoring + maintenance per category is content burden; curation debt is real. |
| 6 | Already solved? | INV-15+INV-18 merge (`05-prioritization/initiative-merging.md:53`) correctly collapses duplicate legend (`master-initiative-inventory.md:259` explicitly `Normalize warranty legend per INV-15`). No further duplicate — but feeds INV-14/16/24 explainability. |
| 7 | Evidence? | **HIGH** for warranty implausibility (VERIFIED); HIGH for jargon opacity (click surfaced rows). |
| 8 | Innovation? | No. |
**Verdict: SIMPLIFY (APPROVE core)** — **APPROVE** warranty fix + legend + trust propagation. Approve glossary with **8–10 decisive terms** (EER/tonnage/R32/HQLED/inverter/Dolby etc.) + inline `EER 3.15 = 1.1kW → ~Tk Y/mo @8h` (`pattern-library.md:90-92`). Remainder CMS **VALIDATE** as demand signals from finders/planner.

### INV-16 — Installation Feasibility Checker

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes for AC/Fridge/Washer slice.** `02-ux-audit/issue-register.md:28` PDP-03 P1 + `01-current-state/product-page-variations.md:60` install line NOT OBSERVED + homepage `Free Installation Selective Items` not echoed per SKU. Most expensive post-purchase failure (AC without outdoor wall/drain, 600L without 50mm gap/door swing). |
| 2 | Copying? | No — John Lewis `Before You Buy / Before We Deliver` + Coolblue Eigen Plan adapted, but BD install failure is local differentiator. |
| 3 | Need now? | **Gate1 now, Gate2 not.** Checker is content; slot booking needs installer capacity feed by district (`04-benchmark/applicability-review.md:110-117` ops-gated, `value-analysis.md:168-176` Gate2 gated). Building UI without feed is worse than no booking. |
| 4 | Simpler change? | **Yes.** Per-SKU toggles → `✓ Feasible — Add to Cart / ⚠ Requires bracket Tk 2,500 — order bundle` with fee `Free/Paid+Tk X` shares table with INV-13/14 + dimension from INV-12 (`pattern-library.md:132-137` 10A) is the lean win. Priced basket SKU as separate line item is second-order. |
| 5 | Too complex? | **As bundled yes.** Checklist CMS + calendar + `order↔service-order` linkage + `Track Your Service` push (`01-current-state/page-analysis.md:7`) is ops-heavy. |
| 6 | Already solved? | No — distinct from delivery estimator (can deliver? vs can install?) and from dimension overlay (`05-prioritization/initiative-merging.md:171`). |
| 7 | Evidence? | **HIGH Gate1, MED Gate2.** NOT OBSERVED per-SKU checklist is HIGH; booking capacity evidence absent. |
| 8 | Innovation? | **Booking as innovation yes** — dresses ops calendar as differentiator before feed exists. Checker is not. |
**Verdict: SIMPLIFY** — Ship Gate1 content checklist + verdict + fee table + `Before You Buy` checklist video (John Lewis model). **DEFER** priced `Add Installation / Add Recycling` basket + Gate2 slot booking until ops confirms district/installer feed; suppress Personal Care.

### INV-20 — Social Proof Pipeline

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes shortlist confidence.** `02-ux-audit/issue-register.md:32` PDP-07 P1 + FILTER-02 P2 empty `Customer Review` `01-current-state/page-analysis.md:81` + headings-only `01-current-state/ecommerce-capabilities.md:31-33` + no stars on PLP card. |
| 2 | Copying? | **Partial.** Amazon `★★★★☆ 4.3 + 2,184 Verified` + Best Buy `4.6★ 212` + review facet `★★★★&up (41)` is STANDARD since ~2016 (`04-benchmark/pattern-library.md:85-93` 6B). BD copy without supply fails. Two-layer trust with INV-21 (`04-benchmark/applicability-review.md:124-126` ENHANCED) is BD adaptation, not pure copy. |
| 3 | Need now? | **No as full pipeline.** Broader funnel still blocked; building pipeline before auth base (INV-32) proves persistence is pipeline-heavy, auth-dependent, low-signal (`04-benchmark/applicability-review.md:74-81` QUESTIONED analogue OPP-06 reasoning applies). BD e-commerce review supply is thin post-Evaly. |
| 4 | Simpler change? | **Yes.** Suppress empty `Customer Review` heading until `n≥5` (INV-C02 already does) + inline `Be first to review — ask Q` + `Verified Purchase` prompt + `Q&A` marker (no fake `5.0 (1)`) achieves honesty without pipeline. |
| 5 | Too complex? | **Yes.** Collection (post-delivery prompt) → moderation → aggregation → badge → facet indexing + verified-purchase check is HIGH (`03-opportunities/opportunity-pool.md:216-231`). |
| 6 | Already solved? | **By suppression.** INV-C02 suppresses empty heading; authenticity (INV-21) provides institutional proof while peer proof accrues. |
| 7 | Evidence? | **HIGH gap, LOW supply proof.** Review `NOT OBSERVED` is HIGH, but willingness to write reviews in BD electronics is unproven — zero `n` in reads suggests thin pipeline. No validated BD-standard UI for this feed in benchmark (vs ratings STANDARD in US). |
| 8 | Innovation? | **AI diagnostics no, but pipeline as innovation would be.** |
**Verdict: DEFER + VALIDATE FURTHER** — Immediate **SIMPLIFY**: suppress facet, show `Be first` + verified prompt (no count). **VALIDATE** supply with light pilot: post-delivery SMS `How was your AC? 1-tap star + Verified Purchase` on top 100 high-ticket SKUs for 6–8 weeks; measure response `n` and moderation load. Only if `n≥5` median, build aggregation + PDP header badge + PLP card badge + facet indexing (P2). Pair sequencing with INV-21 which ships now.

### INV-23 — Smart Compare Workspace

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes.** `02-ux-audit/issue-register.md:41` INTERACTION-01 P1 + `01-current-state/page-analysis.md:173-178` empty 3-slot 3× `Model name…` recall + `01-current-state/ecommerce-capabilities.md:23-25` empty. Journey D high-friction. |
| 2 | Copying? | No — Coolblue/Best Buy/RTINGS patterns but recall task is Transcom-specific (`ecommerce-capabilities.md:23-25`). |
| 3 | Need now? | **Core yes, enrichment staged.** Sticky bar → auto-populate fixes recall without spec work. Decisive-attribute normalization + total-cost pin depends on INV-13/14 zone/fee/EMI tables. |
| 4 | Simpler change? | **Yes.** `Compare (2/3)` sticky bar + `/compare` auto-populated + search as add-more + `Highlight differences` (already exists `page-analysis.md:173-178`) is lean. |
| 5 | Too complex? | **Full scope is.** Category-tuned tint (AC `EER/tonnage/R32/Applicable`) collapses 40 rows to 6–8 needs spec normalization per category + total-cost pin `Price+Install+1yr Energy+EMI/mo` (`04-benchmark/pattern-library.md:47-56` 3A/3B/3C) + verdict strip + share URL. |
| 6 | Already solved? | INV-17 family chips + INV-22 rail share `localStorage` wiring (`05-prioritization/initiative-merging.md:114-115`) but compare board is distinct journey moment — correctly kept distinct (`05-prioritization/initiative-merging.md:176-177`). |
| 7 | Evidence? | **HIGH for recall, MED for enrichment.** Hand-search friction VERIFIED; enrichment lift inferred. |
| 8 | Innovation? | **Verdict strip/total-cost pin as innovation borderline** — useful but second-order. |
**Verdict: SIMPLIFY (APPROVE core)** — Ship sticky bar + auto-populate + remove/share + diff-highlight. **DEFER** decisive-attribute tint + total-cost pin + verdict strip to after INV-13/14 tables and family graph proven; `?familyRef` preserved for INV-17/22 context.

### INV-24 — Guided Selling Framework

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes for AC/Fridge/TV/Washer.** `03-opportunities/opportunity-pool.md:54-68` life-need (room size/top-floor/sun, family size, viewing distance, load) → spec (tonnage/EER, litres/door, size/resolution) translation is manual; SEO wall (`01-current-state/page-analysis.md:90-91` IA-03 P1) is generic text not helper. |
| 2 | Copying? | **Yes risk.** LG `20 BTU/sq ft` + Coolblue `advice/choose-your-tv-size` + AO `18L=1 bag` + Samsung `help-me-choose` + Currys hub `pattern-library.md:34-44` 2A/2B/2D. Framework claim is benchmarking-derived DIFFERENTIATOR that competitors with marketplace cannot copy — but copying wizard ontology without validating rule governance is theatre. |
| 3 | Need now? | **AC lens yes; 5 lenses no.** AC is largest ticket, fewest SKUs, variant proof `product-page-variations.md:52`, rule simplest (`sq ft×height×top-floor/sun→tonnage`). Fridge/TV/Washer each need distinct rule + doorway guard. |
| 4 | Simpler change? | **Yes.** INV-04 re-layer + hub alone improves discovery; wizard is second-order guided confidence. Filter hygiene (INV-C02) + glossary (INV-C04) already reduce hunting. |
| 5 | Too complex? | **5 lenses + PDP verdict chip wiring is.** Single 3-step wizard `Need→Constraints→Budget` outputs filtered PLP URL + chip `✓ Fits your 120 sq ft` per category needs CMS governance validated against brand spec tables (`product-page-variations.md:57`). |
| 6 | Already solved? | **Hub portion by INV-04.** INV-04 hub + CTA `Not sure? 30-sec guide` + INV-C04 glossary already explain SEO wall vs wizard interactive. Keeping hub distinct was correct (`05-prioritization/initiative-merging.md:166`). |
| 7 | Evidence? | **HIGH AC/Fridge/TV/Washer, MED thin Kitchen/Purifier** (`03-opportunities/opportunity-pool.md:67` 7 PDPs). |
| 8 | Innovation? | **Framework as innovation yes** — umbrella + 5 lenses dresses filters as AI-free "finder platform". |
**Verdict: SIMPLIFY + REMOVE** — Ship **AC Finder only + buying-guides hub + PDP verdict chip** as P1 pilot. **DEFER** Fridge Validator (bag ladder + measure guard) + TV/Washer lenses to P2 after AC lift proven. **REMOVE** Kitchen/Purifier lens (or park as content article, not finder) until SKU breadth proves. No ML; rule table governance only.

### INV-25 — Complete-the-Setup

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes.** PDP isolation (`01-current-state/ecommerce-capabilities.md:56` FBT NOT OBSERVED + `product-page-variations.md:66-67` thin single cross-sell + `personalization-current-state.md:12` Cart-Based Recs NOT OBSERVED) → total ownership invisible. |
| 2 | Copying? | **Yes partially.** Home Depot mandatory hookup kits (`pattern-library.md:143-152` 11A `New parts required`) + AO bundle row `Add soundbar+mount → Save` is pattern copy. BD attach is AOV play, not hygiene. |
| 3 | Need now? | **No.** Core funnel (delivery/EMI/Cart) is prior; attach is complementary, not prerequisite. |
| 4 | Simpler change? | **Yes.** Manually curated attach for top 30 roots on one surface (PDP toggleable bundle price) covers 70% lift without engine. |
| 5 | Too complex? | **Engine is.** Family→attach affinity table per family + bundle CMS + price delta logic + cart grouped-line handling + consumable cadence. Suppressed guard for trimmer/mixer `Tk 3k` (`product-page-variations.md:104`) already admits low value. |
| 6 | Already solved? | **Wiring vs build confusion.** Shares family graph with INV-17 (`05-prioritization/initiative-merging.md:178`), but attach vs family nav are distinct moments — kept distinct correctly. However INV-16 mandatory kit already prevents install failure, so bundle guard overlaps. |
| 7 | Evidence? | **HIGH for absence, MED for engine ROI.** NOT OBSERVED verified; attach converts but no BD-specific lift data in benchmark. |
| 8 | Innovation? | Borderline — affinity engine dressed as merchandising innovation. |
**Verdict: SIMPLIFY + DEFER** — Curated PDP bundle row + Cart `Complete your setup` rail on AC/TV/Fridge/Washer top 30 only (one surface each) now. **DEFER** rule engine + grouped-line pricing + purifier cartridge cadence to P2; **VALIDATE** with 20-SKU attach pilot measuring attach rate before building CMS.

### INV-28 — Open-Box Delivery + OTP

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes post-purchase.** Big-ticket COD dispute risk 75–90% + self-unbox burden (`01-current-state/ecommerce-capabilities.md:42-44` no OBD/OTP language, `04-benchmark/applicability-review.md:145` Finding 2). |
| 2 | Copying? | **Yes.** Flipkart OBD T&C (`If eligible… Order Summary page` + OTP + photo log + both packings opened) + India Post 1.6L offices COD OTP — STANDARD India, EMERGING BD. Wholesal copy without fleet proof is mimicry. |
| 3 | Need now? | **Badge now, protocol later.** Eligibility proof before paywall is P1 trust signal; rider protocol is ops re-engineering. |
| 4 | Simpler change? | **Yes.** PDP badge `Eligible for Open Box Delivery at your pincode ✓` plus Order Summary opt-in checkbox from INV-13 zone truth is cheap reassurance. |
| 5 | Too complex? | **Protocol is.** Wishmaster, both packings opened in front, IMEI/accessories check, photo log, reference logged is ops-heavy and cost-justified only >Tk20k (20k threshold `04-benchmark/applicability-review.md:145`). |
| 6 | Already solved? | **Badge layer by INV-13/21.** Zone truth + `Original Product Guaranteed` institutional proof already materially proven at handover; OBD duplicates proof mechanically. Keep badge wiring, defer protocol. |
| 7 | Evidence? | **HIGH anxiety, MED BD validation.** India pattern EMERGING in BD; owned Store Locator `01-current-state/page-analysis.md:199-204` + logistics gives credible Wishmaster but not proven at scale. |
| 8 | Innovation? | **OTP+photo log as innovation yes** — dresses logistics SOP as product feature. |
**Verdict: SIMPLIFY + DEFER** — Ship eligibility badge + Order Summary opt-in sharing INV-13 zone matrix now (fast trust). **DEFER** doorstep SOP (rider script, OTP, photo, reference) to P2; **VALIDATE** with Dhaka-only pilot `Tk>50k` measuring dispute-rate delta before fleet-wide rollout.

### INV-C05 — Human Support Spine

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes.** Tier-2/3 high-ticket needs human reassurance in funnel not footer-only (`02-ux-audit/issue-register.md:35` TRUST-01 P2 + `01-current-state/page-analysis.md:14` `Need help? Click Here ` generic + `page-analysis.md:18-19` footer-only 16212 + `page-analysis.md:199-204` Locator not PDP-linked). |
| 2 | Copying? | **Yes risk.** Facebook Commerce thousands BD sellers + ChalDal Premium Care dedicated agent 24h + Rokomari chat (`04-benchmark/applicability-review.md:147-149` Finding 7) cited, but manager model copies marketplace concierge. PDP share via WhatsApp is STANDARD social layer, not invention. |
| 3 | Need now? | **Sticky spine yes, manager no.** Voice before cart is hygiene; dedicated manager is roster-gated. |
| 4 | Simpler change? | **Yes.** Elevate `16212 9AM–9PM` to sticky call bar PDP/Cart + PDP Store Pickup estimator `nearest 3 stores + Schedule your visit` district cards + `Track Order/Service` wiring (`01-current-state/page-analysis.md:7` OBSERVED not real-time) achieves reassurance without headcount. |
| 5 | Too complex? | **Premium manager is.** `Get personal manager — message on WhatsApp` for >Tk50k (agent handles order, Tracks delivery, resolves post-delivery) needs roster, SLA, CRM — ops dependency akin to slot booking. |
| 6 | Already solved? | **By INV-21/13.** Authenticity proof + delivery estimator already answer most reassurance queries; C05 should not double-count. Workspace as `05-prioritization/initiative-merging.md:54-55` M-05 merge correctly collapsed conversational + hotline as one spine — keep merged. |
| 7 | Evidence? | **HIGH hotline in funnel is hygiene (`pattern-library.md:163` 12C), MED manager.** `Regional Finding 7` trust is human, but WOM β=0.13 indirect. |
| 8 | Innovation? | **Premium manager as innovation yes** — dresses support headcount as product innovation. |
**Verdict: SIMPLIFY** — Ship sticky hotline (existing 16212) + Locator wiring + PDP `Share via WhatsApp — Ask agent about this fridge` deep-link (pre-filled PDP URL + hotline fallback). **DEFER** premium manager roster; **VALIDATE** chat deflection with deep-link CTR before hiring.

### INV-32 — Authentication Friction & Guest→Auth Continuity

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes for returners.** `02-ux-audit/issue-register.md:39-40` AUTH-01 P2 split-field + phone-only OTP + `01-current-state/page-analysis.md:192-195` `+880` two textboxes + AUTH-02 guest wishlist/compare `appears to do nothing` (`product-page-variations.md` + `page-analysis.md:167-171` guest empty `about:blank`) + unmigrated history. |
| 2 | Copying? | No — hygiene fix vs OTP best practice. |
| 3 | Need now? | **Half.** Split-field consolidation is P1 hygiene before Journey F. Full `localStorage→account` migration for viewHistory/compareQueue (`05-prioritization/initiative-merging.md:115`) only matters if INV-22/23 prove. |
| 4 | Simpler change? | **Yes.** Single phone input + inline guest prompt `Saved — log in to persist across devices` + toast (INV-C06) fixes perception faster than backend migration. |
| 5 | Too complex? | **Migration is medium, social login higher.** Velocity + no-password + history merge is not trivial; COD market (`75–90%` Finding 4) tolerates guest checkout without auth, so auth is enablement not terminus. |
| 6 | Already solved? | **Consumes other INVs, not duplicate.** INV-22/23/31/C03 Recent all share same `localStorage` store (`05-prioritization/initiative-merging.md:115` Resumption Store). Fixing auth unlocks them but does not replace them. |
| 7 | Evidence? | **HIGH split-field friction, MED history-loss impact.** Phone-only VERIFIED; abandonment due to split field unmeasured. |
| 8 | Innovation? | No. |
**Verdict: SIMPLIFY** — Fix split field → single input + OTP velocity + inline guest prompt now. **DEFER** `localStorage→account` migration + social/password alt to P2 after INV-22/23 retention lift is measured.

### INV-33 — Exchange & Return Value

| Q | Ask | Answer |
|---|-----|--------|
| 1 | Real problem? | **Yes but lifecycle.** `02-ux-audit/issue-register.md:43` FEEDBACK-02 P2 + `01-current-state/page-analysis.md:208-212` `/exchange` 2-card + `product-discovery.md:119-120` `Get Exchange up to 12000 Tk` but valuation opaque (`01-current-state/ecommerce-capabilities.md:52` NOT TESTED). Idle household as currency is real but upgrade-cycle, not browse-cycle. |
| 2 | Copying? | **Yes.** Daraz 14-day ALL products 2025 (expanded from Mall) + Flipkart ReCommerce 26 categories 10-step AI cross-category + Trust Shield 30-day (`04-benchmark/applicability-review.md:150` Finding 8). BD copy without valuation ops is brochure. |
| 3 | Need now? | **Badge yes, exchange engine no.** After Daraz move, buyers expect `14-Day` as baseline — absence is now conspicuous but not prior P0. |
| 4 | Simpler change? | **Yes.** PDP badge next to `In stock` (`product-page-variations.md:58`) `14-Day Hassle-Free Return ✓` + static `Up to Tk 12k → doorstep inspection → OTP` beneath price + timeline copy `Restocking 2–3 weeks — or show similar in-stock` replaces perpetual waitlist without AI. |
| 5 | Too complex? | **AI diagnostics is.** Cross-category (fridge→washer, mobile→laptop) + 10-step AI condition check + valuation feed + OTP `cross-category` is P2 ops-gated (`04-benchmark/applicability-review.md:150` P2 start static → AI). Inventory already QUESTIONED (`03-opportunities/opportunity-pool.md:86-100` + `04-benchmark/applicability-review.md:74-81`). |
| 6 | Already solved? | **Trust partially by INV-21/20.** Return promise is distinct lifecycle from ratings-proof, but exchange as trust badge overlaps institutional proof. |
| 7 | Evidence? | **MED.** Exchange hub VERIFIED but valuation/execution opaque and AUTH/ops dependency high; price-watch (OPP-06 tail inside INV-33) had zero benchmark pattern among 33 (`04-benchmark/applicability-review.md:74-81`). |
| 8 | Innovation? | **AI diagnostics + cross-category as innovation yes** — dresses valuation feed as AI feature before static truth exists. |
**Verdict: SIMPLIFY + DEFER** — Ship `14-Day` badge + static `up to` line + inspection-truth now (content). **DEFER** cross-category + 10-step AI to P2; **VALIDATE** with ops feed confirmation and Auckland-style single-category inspection pilot.

### INV-34 — Accessibility & Icon System

Not questionable for inclusion, but challenged on competition with conversion lifts: `02-ux-audit/issue-register.md:45` ACCESS-01 P2 + `01-current-state/page-analysis.md:7-14` icon-only `  ` is WCAG risk, narrowest reach (value-analysis LOW `value-analysis.md:60` sole LOW). Not a funnel blocker but non-negotiable compliance. **Verdict: APPROVE** as parallel hygiene sprint (aria-label + tooltip + contrast + tab order), decoupled from prioritized roadmap so it does not contest P0/P1 sequening.

---

## Cross-Cutting Red Flags — Portfolio Level

1. **Shared table fallacy.** 6 merges are correct, but 7 initiatives (INV-13, INV-14, INV-16, INV-26, INV-28, INV-C05, INV-C06) feed one District→Zone/SLA/fee/store table (`04-benchmark/applicability-review.md:158-169`). Building table once is right — but portfolio proposes surfacing it at 7 placements simultaneously. Ship table + 3 surfaces (INV-13 PDP estimator, INV-14 static row, INV-C06 Cart truth) first; add other badges wiring after.

2. **LocalStorage as cheap personalization is under-claimed asset.** INV-C03 Recent + INV-22 + INV-23 queue + INV-32 migration are correctly documented as one store (`05-prioritization/initiative-merging.md:115`), but value-analysis still treats AFFINITY reorder (INV-06) as MEDIUM. The cheap store delivers 80% at zero backend — this supports DEFER on affinity while APPROVE on rails.

3. **Content-before-ops gating is the correct spine.** INV-C04 glossary, INV-16 Gate1 checklist, INV-04 hub, INV-14 static row + verdict all ship without slot-calendars/feeds. Portfolio correctly files Gate2/bookings as deferred gates inside same INVs (`05-prioritization/master-initiative-inventory.md:505` + `05-prioritization/initiative-merging.md:118-121`). Critic endorses: enforce this gating strictly — any Gate2 starting before feed confirmation repeats benchmarking error (`04-benchmark/applicability-review.md:110-117`).

4. **Thinnest-evidence initiatives cluster in P2.** INV-24 Kitchen/Purifier lens (7 PDPs), INV-25 full engine, INV-28 protocol, INV-33 AI, INV-20 full pipeline all demand ops/content supply not yet proven. Portfolio correctly marks them MEDIUM/P2 but still carries them as build units. Reduce blast radius: each gets a 20–100 SKU pilot before CMS.

5. **Metric risk: no prioritization yet masks complexity debt.** Value analysis (Step 3) deliberately avoids sequencing, but several VERY HIGH items (INV-20 pipeline, INV-12 video) are HIGH complexity. Without critique, Step 4 could schedule them as P0. This critique caps VERY HIGH at hygiene-feasible cores.

---

## Recommended Re-Sequencing Implications for Step 4

| Phase | Keep | Add / Rescope from Critique |
|-------|------|-----------------------------|
| **P0 — Conversion unblock** | INV-01 (`/undefined`) + INV-C02 (chips/sort/facet repair incl. suppress empty Review) + INV-C03 Stage1 (typeahead + recent) + INV-13 (district text estimator + Fast badge) + INV-14 static row + verdict + INV-21 authenticity + INV-26 plural payment + INV-C06 drawer/stepper/toast/CTA + INV-04 re-layer + INV-C04 warranty fix + 8-term glossary | Add INV-C01 canonical/hyphen/tile slice (not hierarchy). Add INV-12 zoom/pinch/overlay (week) + INV-22 rail. |
| **P1 — Decision support** | INV-12 video pilot (AC only) + INV-17 family chips + INV-23 sticky→auto-populate core + INV-24 AC Finder + INV-16 Gate1 checklist | Defer INV-23 tint/verdict, INV-24 other lenses, INV-16 priced basket/booking. |
| **P1b — Search hygiene** | INV-C03 Gate1b synonym table + Did you mean + advisor CTA | Defer fuzzy engine to VALIDATE. |
| **P2 — Ops-gated / Differentiator** | INV-20 pilot (post-delivery SMS) → if `n≥5` build pipeline; INV-25 curated attach pilot; INV-28 DHCP pilot; INV-33 static 14-day + up-to line; INV-16 Gate2 + INV-33 AI only after feed | Add VALIDATE gates: INV-32 migration after rail proves; INV-06 curated prioritization only after P0 lift A/B. |
| **Parallel sprint** | INV-34 accessibility (aria-labels, contrast, keyboard order) | No funnel competition. |
| **Parked / Removed** | — | **REMOVE** INV-24 Kitchen/Purifier lens; park INV-20 full pipeline until pilot; park affinity reorder (INV-06 reorder portion) until `Rail only` vs `Rail + hero` A/B proves. |

Suppression rule unchanged: suppress EMI/energy/checker/FBT for Personal Care trimmer/mixer `Tk 3k` (`01-current-state/product-page-variations.md:104` + `05-prioritization/master-initiative-inventory.md:505` + `04-benchmark/applicability-review.md:96` BDT 5k).

---

## Evidence Index (claims above trace per `file:line`)

| Claim | File:Line |
|-------|-----------|
| 25 consolidated (34→25, 6 merges 15→6) + wiring | `05-prioritization/initiative-merging.md:15-23` + `05-prioritization/initiative-merging.md:191` District→Zone table |
| 9 VERY HIGH / 9 HIGH / 6 MEDIUM / 1 LOW | `05-prioritization/value-analysis.md:34-60` |
| Only P0 = INV-01 NAV-01 `/undefined` 5+ homepage + 4× `/samsung/undefined` | `02-ux-audit/issue-register.md:7` · `01-current-state/page-analysis.md:56-57` · `05-prioritization/master-initiative-inventory.md:84-98` |
| SEO wall 1500+ words pushes grid below fold | `01-current-state/page-analysis.md:90-91` · `02-ux-audit/issue-register.md:10` IA-03 P1 |
| FILTER-01 P1 chips missing + SORT-01 P1 `Select Sort Option` + `Show 12 <of 1> 1` + dual price + Screen vs Display Size | `02-ux-audit/issue-register.md:20-25` · `01-current-state/product-discovery.md:74-88` · `01-current-state/page-analysis.md:75-86` |
| Homepage 7+ grids + 68 DOM images + heavy | `01-current-state/page-analysis.md:48-54` · `01-current-state/product-page-variations.md:49` · `02-ux-audit/issue-register.md:13,46` DISC-01/MOBILE-01 |
| Search `Search Here` generic + suggestions NOT FULLY VERIFIED + `SEARCH-01 P1` | `01-current-state/ecommerce-capabilities.md:12-13` · `01-current-state/product-discovery.md:40-43` · `02-ux-audit/issue-register.md:17-19` |
| Zero-result NOT TESTED | `01-current-state/ecommerce-capabilities.md:15` · `02-ux-audit/issue-register.md:19` SEARCH-03 P2 |
| Flat PDP 101 at root + orphan `/tv-av` + 4 trailing-hyphen + 13 brand PLPs vs `search?Brand=` | `00-input/sitemap-analysis.md:27` · `00-input/sitemap-analysis.md:74-77` · `00-input/sitemap-analysis.md:132-134` · `00-input/sitemap-analysis.md:26-28` |
| Delivery gate `Enable your Location` + `Free Installation Selective Items` not echoed | `01-current-state/page-analysis.md:125` · `01-current-state/page-analysis.md:34` · `02-ux-audit/issue-register.md:27` PDP-02 P1 · `01-current-state/ecommerce-capabilities.md:42-44` |
| `Add To Cart ×2` + empty Cart `Subtotal ৳0` disabled Checkout + no toast | `01-current-state/page-analysis.md:126-128` · `01-current-state/page-analysis.md:159-164` · `01-current-state/user-journeys.md:98-148` · `02-ux-audit/issue-register.md:36-38,42` CART-01/02/CHECKOUT-01/FEEDBACK-01 |
| EMI presence inconsistency (Haier 622IBG absent) + `EMI36` badge | `01-current-state/product-page-variations.md:55` · `01-current-state/page-analysis.md:87` · `01-current-state/page-analysis.md:114-117` · `02-ux-audit/issue-register.md:31,44` PDP-06/CONSISTENCY-01 |
| Spec rows `R32 / EER 3.15 / Applicable For 120 sq ft` + warranty `Parts-0M/Motor-300M` | `01-current-state/product-page-variations.md:57-61` · `02-ux-audit/issue-register.md:29-30,35` PDP-04/05/TRUST-01 |
| Video NOT OBSERVED + gallery generics 4+ | `01-current-state/ecommerce-capabilities.md:30` · `01-current-state/page-analysis.md:134-135` |
| Recently Viewed / Continue / FBT / Price Alerts NOT OBSERVED | `01-current-state/ecommerce-capabilities.md:55-56,54` · `01-current-state/personalization-current-state.md:9-10` · `01-current-state/page-analysis.md:159-164` |
| Compare empty 3× `Model name…` + entry `` + header `Search Here` + `16212` + Locator `Schedule your visit` | `01-current-state/page-analysis.md:173-178` · `01-current-state/page-analysis.md:129` · `01-current-state/page-analysis.md:9,14,18-19,199-204` |
| Phone OTP split-field `+880` two textboxes | `01-current-state/page-analysis.md:192-195` · `02-ux-audit/issue-register.md:39-40` AUTH-01/02 |
| `/exchange` 2-card + `Get Exchange up to 12000` vs NOT TESTED + `Get Stock Alert` no ETA | `01-current-state/page-analysis.md:208-212` · `01-current-state/product-discovery.md:119-120` · `01-current-state/ecommerce-capabilities.md:52` · `01-current-state/page-analysis.md:113` · `02-ux-audit/issue-register.md:43` FEEDBACK-02 |
| Icon-only `  ` + ACCESS-01 | `01-current-state/page-analysis.md:7-14` · `02-ux-audit/issue-register.md:45` |
| 15 OPP classification VALIDATED/ENHANCED/QUESTIONED + 8 NEW | `04-benchmark/applicability-review.md:22-38` + `04-benchmark/applicability-review.md:142-152` NEW-01..08 |
| ENHANCED wrappers (district text, form latency, bag+guard, priced SKU, two-layer trust) | `04-benchmark/applicability-review.md:46-49` OPP-01 · `04-benchmark/applicability-review.md:94-98` OPP-09 · `04-benchmark/applicability-review.md:62-67` OPP-04 · `04-benchmark/applicability-review.md:110-117` OPP-12 · `04-benchmark/applicability-review.md:124-126` OPP-14 |
| QUESTIONED OPP-06 / OPP-15 sequencing + affin defer | `04-benchmark/applicability-review.md:74-81` · `04-benchmark/applicability-review.md:128-135` |
| Value-analysis P0 hygiene before P1 differentiators | `05-prioritization/value-analysis.md:66-317` detailed per-INV rationale |

---

*Strategic Critique complete. 25 initiatives challenged — 8 APPROVED as scoped, 13 SIMPLIFIED (lean core now, remainder deferred/validated), 3 DEFERRED, 1 VALIDATE-first (INV-20 supply), 1 lens REMOVED (INV-24 Kitchen/Purifier). No weak idea protected; complexity trimmed at the P0/P1 boundary where BD ops evidence is thinnest.*
