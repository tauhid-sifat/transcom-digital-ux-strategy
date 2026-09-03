# Executive Summary — Transcom Digital UX Strategy

> Standalone distillation of `final-ux-ui-improvement-scope.md` — answers the 5 executive questions in <7 minutes.

## What did we review?

A sitemap-driven assessment of **Transcom Digital** (`transcomdigital.com`, 167 URLs via octopus.do, 101 PDPs flat at `/`, 39 PLPs, 13 brand PLPs) → 22 live pages tested via BrowserOS Neo (Homepage, 5 top cats, `smart-tv`/`dry-irons`/`inverter-ac`, `samsung` brand, search, 8 PDPs across 9 appliance categories), 9 journey tests (Journey A know-exactly `FTKL12TV16WD` → F returning), 32 UX issues (P0 1 / P1 13 / P2 14 / P3 4), benchmarked against 21 platforms (Amazon.in, Flipkart, Daraz BD, Coolblue, Best Buy, AO, Currys, Pickaboo etc.) → 33 patterns → 12 problem groups → 38 raw opportunities → 15 consolidated + 8 benchmarking NEW → 34 normalized initiatives → 25 after 6 merges. Priorities set via value (9 VERY HIGH) vs feasibility (8 LOW) vs strategic critique, wired via 7 foundational tables, sequenced NOW/NEXT/LATER/EXPERIMENT per `05-prioritization/phase-5-summary.md`. Not a visual UI review.

## What are the biggest problems?

**Confidence + memory fail where high-consideration purchase is made (Tk 50k–1.5L).** 11× See All → `/undefined` (NAV-01 P0) blocks browse at entry. PLP cannot narrow: no chips, placeholder `Select Sort Option` with empty options, pagination `Show 12 <of 1> 1` (P0 cluster Journey B). PDP hides what matters at price exposure: delivery gated behind `Enable your Location` permission before fee/SLA/free-install flag, no landed-cost row, no spec glossary for `EER 3.15 / R32 / HQLED` and warranty `Parts-0M/Motor-300M`, static generic gallery (68 DOM images `product-page-variations.md:49-50` but no zoom), no sibling navigation for 55"→65", and no aggregate stars (Review tabs exist but no counts). Cart is `Subtotal ৳0 Total 0` dead-end with no toast; checkout steps are a black box. Trust claimed as `Original Product Guaranteed` on homepage dissipates at price where it is needed — post-Evaly 2–3% penetration context. No Recently Viewed resumption (Journey F wholly unserved DISC-02 P1) and no history-driven ranking before any personalization.

**Theme summary:** (1) Discovery breaks, (2) Decision support thin (problem→spec self-translation), (3) System status invisible, (4) Purchase boundary opaque, (5) Consistency fractures (flat URLs, warranty, EMI badge vs text).

## What opportunities matter most?

Six validated opportunity **themes** that repair confidence + memory without invention — each proven as INDUSTRY STANDARD or differentiator on same-category platforms, not as Daraz feature dump:

1. **Fulfillment Confidence as one row** — pincode-first SLA + delivery/install fees + store pickup + Fast Delivery badge, wired to True Cost ownership `Upfront+Install+Energy→EMI/mo` with tenure picker 3/6/12/24/36 + ineligibility `→ EMI Bank List` + offline 7–10d truth (Pickaboo 32 banks) + plural `COD+bKash/Nagad+Card` row for 75–90% COD market.
2. **Browse Memory** — anonymous `localStorage viewHistory/lastPlpUrl/compareQueue/searchHistory` still durable: Recently Viewed rail (8) + Continue Shopping deep-link restoring filters + Recent Searches chips.
3. **Requirement Translation** — Guided Selling wizard `Need→Constraints→Budget→filtered PLP + PDP chip ✓ Fits your 120 sq ft — 1.5 Ton` — AC tonnage first (LG 20 BTU/sq ft), then Fridge bag ladder 18L=1 bag + 7-step measure guard, TV distance→size.
4. **Inspection + Comparison without memory load** — zoom/pinch first (no reshoot) + persistent compare sticky→auto-populated `/compare` + decisive-attribute tint + total-cost pin + variant Family chips `55" — Tk79,900 In stock | 65" +Tk18k`.
5. **Trust Mechanics at price** — `✓ Authorized — Official Warranty` hero lockup reusing 13 brand authorizations + OBD badge→OTP photograph + hotline-sticky 16212 + WhatsApp `Share via WhatsApp — Ask agent` deep-link.
6. **Literacy prerequisite** — tap-to-explain jargon decoder `EER 3.15 = ~Tk Y/mo` + warranty legend `Service/Parts→5 years` content-only, prerequisite for finders/cost literacy.

Together they turn taxonomy (`product-discovery.md:74-83` frontspecific facets already adapting) into assisted shopping vs listing.

## What should be done first?

**NOW (10 P0 — must address).** Ship the 7-table foundation that makes 7 later initiatives work for free:

`/undefined` hotfix → PLP chips/sort/facet hygiene + warranty truth → start district→Zone/SLA+delivery+install+store table → Recently Viewed+Continue rail + Search Stage1 `Product/Brand/Category/SKU-exact (3+ alnum ranks SKU)` + Recent 6 + jargon decoder 8–10 terms → complete estimator + static True Cost row with offline truth → plural payment row → authenticity lockup → Cart drawer/stepper/toast (mini-cart + `Subtotal+Delivery+Install→Total` + `Cart→Delivery→Payment→Confirm` + `Continue Shopping` recovery).

**Why first:** Every P0 is VERY HIGH value + mostly LOW feasibility, or essential HIGH that gates purchase (INV-13 delivery table wires 7 themes). `NAV-01` P0 blocks every browse path; `FILTER-01/SORT-01` P1 cluster blocks Journey B shortlisting; gated delivery + invisible landed cost block every Tk50k–1.5L conversion; post-Evaly trust and 75–90% COD plurality exclude the majority if deferred.

**NEXT (11 P1, after foundations):** Canonical IA fixes, SEO re-layer below pagination + `30-sec guide` CTA, Smart Compare sticky→auto-populated, AC Finder lens, full decoder, Rich Media zoom, Variant chips, Gate1 installation checker content + priced `Add Installation` SKU, sticky hotline+WhatsApp deep-link, auth split-field fix + guest toast `Saved for now — log in`, Zero-Result `Did-you-mean + Remove Brand →12`.

**LATER / P2:** Beware budget cull, curated bundles pilot, OBD OTP protocol, 14-day static badge (→ AI diagnostics later), full ratings pipeline after pilot proves n≥5 supply `ecommerce-capabilities.md:31-33` zero, additional finder lenses (Fridge/TV/Washer after AC proves).

**EXPERIMENT:** Affinity homepage full reorder `Rail only vs Rail+hero reweight` A/B only after rail proof + modular CMS audit.

## What is the strategic vision?

**From catalog shell to need-led retailer:** where homepage guides rather than dumps 7+ grids — `Not sure? 30-sec guide → finder (room→tonnage, family→litres, distance→size, kg→front/top, wattage→task, TDS→filter) → filtered PLP (rule-governed) → PDP with ✓ Fits your X, total-cost-owned row, zoom/dimension, variant + delivery re-validation, trustworthy install/return + OBD photograph → cart that remembers and compares total cost → human WhatsApp/hotline huddle → delivered-to-door proof.*

Vision is not a feature count — it is **"I was helped to choose the right spec, shown what it will really cost monthly, and delivered with proof."** Horizons NOW/NEXT/LATER/EXPERIMENT reflect sequencing logic, not dates, per `05-prioritization/dependency-map.md` 7 foundational tables (district master, EMI bank×tenure, W×H×D, tariff glossary, family graph, localStorage store, review pipeline) that feed 13 initiatives when built once before touching CMS reorder.

---
*Teams:* Product — lock NOW vs PARKED, gate P1 on INV-13 table + INV-22 proof. UX/UI — wire PLP chip row + real sort + `Showing 1–12 of 45 — Show [12|24|48]`, PDP landed-cost row + `✓ Authorized` + warranty legend, search 150ms dropdown + Recent, cart drawer+stepper. Engineering — spike 7 tables before build: `viewHistory/lastPlpUrl/compareQueue/searchHistory` + family graph for 101 PDPs `sitemap-analysis.md:27`. Business — fund P0 trust row as conversion unlock, not cosmetics; approve deferred experiment criteria (affinity A/B after rail, Gate2 after ops feed).*
