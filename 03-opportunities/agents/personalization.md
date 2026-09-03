# Personalization Opportunities — Transcom Digital

> Agent A — Personalization Specialist | Phase 3
> Source knowledge base: `00-input/sitemap-analysis.md`, `01-current-state/site-inventory.md`, `01-current-state/page-analysis.md`, `01-current-state/product-discovery.md`, `01-current-state/product-page-variations.md`, `01-current-state/user-journeys.md`, `01-current-state/ecommerce-capabilities.md`, `01-current-state/personalization-current-state.md`, `02-ux-audit/issue-register.md`, `02-ux-audit/executive-summary.md`, `02-ux-audit/usability-issues.md`, `02-ux-audit/user-journey-friction.md`
> Date: 2026-09-03
> Scope: Converts Phase 2 friction (esp. DISC-02, DISC-03, PDP-02/03, INTERACTION-01, SEARCH-01, Journey F) into *personalization* opportunities. Does not repeat Phase 1 discovery or Phase 2 problem statements verbatim — reframes them as signal-driven, user-specific interventions.

---

## 1. Current Personalization Baseline

All 14 capabilities audited in `01-current-state/personalization-current-state.md:1-60` are **NOT OBSERVED** (or PARTIALLY OBSERVED gate only) as guest. No element containing "Recommended for you", "Recently viewed", "Continue shopping", "Based on your browsing", or "Because you viewed X" was found across ~22 pages / 8 PDP samples. Generic modules *do* exist — `Best Deals`, `Latest Products` (`01-current-state/product-discovery.md:98-107`), `Related Products` (`01-current-state/page-analysis.md:138-139`) — but they are catalog-driven, identical for all visitors, and not labeled or triggered by user behavior.

| Capability (# in personalization-current-state.md) | State | Implication for this doc |
|---|---|---|
| 1 Recently Viewed, 2 Continue Shopping, 3 Personalized Recommendations, 4 Behavioral Recommendations, 11 Browsing-based PDP recs | NOT OBSERVED | Safe to propose — no existing personalization to conflict |
| 5 User-Specific Promotions, 6 Personalized Homepage, 8 Personalized Search, 9 Saved Preferences, 10 Personalized Categories, 12 Cart-Based Recs, 14 Account-Based | NOT OBSERVED | Propose only if tied to behavioral/affinity signal |
| 7 Location-Based Content | PARTIALLY OBSERVED (`01-current-state/personalization-current-state.md:7`) — PDP gate `Enable your Location` exists but no personalization applied until consent | Opportunity is to *invert* gate into confidence (PER-07) |
| 13 Wishlist Persistence | OBSERVED empty only; persistence AUTHENTICATION REQUIRED | Opportunity to personalize without re-architecting wishlist |
| Related/Latest/Best Deals | VERIFIED as generic | Must not be re-proposed as-is; must add signal to qualify as personalization |

**Verification rule applied:** Every opportunity below was checked against the 14-row inventory; none duplicates an already-observed personalized module.

---

## 2. Guiding Principle: Generic Recommendation vs True Personalization

This distinction is enforced for every opportunity:

- **Generic Recommendation** = Same shelf for every visitor (e.g., current `Best Deals` carousel `01-current-state/page-analysis.md:46`, `Latest Products` 4-thumb rail `01-current-state/page-analysis.md:83`, `Related Products` laptop→laptop `01-current-state/product-page-variations.md:65`). No user signal consumed. Valuable for merchandising but not personalization.
- **True Personalization** = Content, order, or message changes *because of this user's* signals — explicit (view history, search term, cart content, location, wishlist) or inferred (category affinity from dwell/clicks, comparison set, time-since-last-visit). Requires at minimum anonymous session storage; ideally authenticated profile for cross-device.

All PER items below are **True Personalization** — each lists the signal, trigger, and why a static shelf would not achieve the same outcome. Where an idea could be built as either, the generic version is explicitly rejected.

---

## 3. High-Consideration Context

Transcom Digital sells infrequent, high-ticket, spec-sensitive goods (AC 1–1.5 Ton, 600L fridge, 55–65" TV, 8kg washer at Tk 50k–1.45L — `01-current-state/product-page-variations.md:48-56`). Journeys B, C, D, F (`02-ux-audit/user-journey-friction.md:27-148`) are research-heavy, multi-session, and comparison-driven. Personalization here is not "delight" — it is **memory, wayfinding, and confidence** to prevent rebuilding context on every visit.

---

## 4. Opportunities

### PER-01 — Recently Viewed Trail (Session-Persistent, Anonymous)

**User problem:** High-consideration shoppers view 3–6 PDPs (TV size, fridge capacity, tonnage) then lose them when they navigate to PLP, homepage, or return next day. Today there is no trail (`01-current-state/personalization-current-state.md:9`, DISC-02 `02-ux-audit/issue-register.md:14` P1). Users must recall model strings like `FTKL12TV16WD` or re-filter from root.

**Target user:** All browsers — especially Journey B/C/D researchers comparing specs before committing. Works for anonymous (cookie/localStorage) and authenticated (profile) alike; highest impact for first-time visitors who have not yet created an account.

**Trigger:** User views ≥1 PDP (any category). Trail updates on each PDP view, deduplicates, preserves order (most recent first), caps at last 8–12. Persists across sessions for 30 days unless cleared.

**Data signals required:**
- Minimal: `pdpView` events `{productSlug, categoryPath, brand, timestamp, imageUrl}` stored in localStorage/cookie + optional server session.
- Enhanced (authenticated): same events joined to `userId` for cross-device persistence.
- No PII, no purchase history required. No ML ranking — recency-ordered.

**Journey placement:**
- Primary: Horizontal strip `Recently Viewed` on homepage (above or below `Best Deals` — `01-current-state/page-analysis.md:45-46`), on every PLP (above pagination), on empty cart/wishlist/compare (`01-current-state/page-analysis.md:159-178`) as recovery, and compact rail on PDP below `Related Products`.
- Secondary: Sticky footer or header dropdown "History (3)" for fast return.

**User value:** Restores interrupted research in one tap; reduces re-navigation cost through 39 category PLPs + flat 101-PDP namespace (`00-input/sitemap-analysis.md:22-27`). Builds trust that the site "remembers" — critical for multi-day consideration.

**Business value:** Directly addresses DISC-02 return-visit drop-off (`02-ux-audit/user-journey-friction.md:123-142`). Increases PDP re-entry rate, reduces use of broken `See All → /undefined` paths (NAV-01), and keeps high-intent users from defecting to competitors during comparison.

**Complexity: Low**
- Dependencies: Front-end event capture on PDP, localStorage/cookie store, UI component (carousel/card). No recommendation engine, no backend personalization service.
- Effort: ~1 sprint front-end + QA. Upgrade path to authenticated sync is optional phase 2.

**Generic vs True Personalization:** Generic would be a static "Latest Products" rail (already exists — `01-current-state/ecommerce-capabilities.md:11` — identical for all). This is True Personalization because the set is *this user's* view history, ordered by *their* recency, empty for a first-page visitor and populated only after *their* browsing.

**Why this matters (not just a list):** For a Tk 1.3L 600L fridge, the decision is rarely one-session. Without memory, the site forces every returning visit to restart at `Home > Refrigerators > No Frost > Side-by-side` — a 4-level drill (`01-current-state/product-discovery.md:59`). The Recently Viewed trail is the lowest-cost way to prove the platform respects research effort.

> Overlap note: Closest to electronics decision support is PDP spec recall, but primary owner is **Personalization (memory/wayfinding)**. Decision-support team owns *what* spec is compared; personalization owns *that it is remembered*.

---

### PER-02 — Continue Shopping / Resume Journey

**User problem:** Distinct from Recently Viewed (which is item-level), users who narrowed a PLP (e.g., `Smart TV` filtered to `55" + SAMSUNG + 80k–1L`, or `Air Conditioner > Inverter AC` price band) and left, return to a cold homepage with no path back to that narrowed set. Cart empty state today shows only `You have not added any product...` with disabled Checkout and no history link (`01-current-state/page-analysis.md:159-164`, CART-01 `02-ux-audit/issue-register.md:36`).

**Target user:** Returning visitors (24h–7 days) who showed category/price/brand affinity but did not add to cart. Especially Journey F "returning to continue shopping" — wholly unserved (`02-ux-audit/user-journey-friction.md:123-142`).

**Trigger:**
- Session trigger: User applied ≥1 filter, performed search (`search?Brand=samsung`, `01-current-state/product-discovery.md:46`), or viewed ≥2 products in same category, then navigated away or abandoned session.
- Return trigger: Next visit within attribution window, or same-session cart/wishlist empty view.

**Data signals required:**
- `lastCategoryPath` (e.g., `/tv-av/television/smart-tv`), `lastFilterState` {brand, displaySize, priceBucket}, `lastSearchQuery`, `lastPlpUrl`, timestamp.
- Anonymous via cookie/localStorage; authenticated via profile `recentBrowzeContext`.
- No purchase history needed.

**Journey placement:**
- Homepage hero/secondary strip: `Continue shopping Smart TVs (55", Samsung) →` deep-linking to the exact filtered PLP URL (preserving `?Brand=samsung&Display+Size=55` etc.).
- Empty cart: Replace generic empty copy with primary CTA `Continue shopping where you left off` + secondary `View your 3 recently viewed`.
- Empty wishlist/compare: Same deep-link pattern.
- Optional: Exit-intent on PLP "Pick up where you left off next time?" (dismissible).

**User value:** One-tap resumption of a narrowed consideration set instead of rebuilding filters through dual slider + bucket controls (FILTER-03 `02-ux-audit/issue-register.md:22`) and placeholder sort (SORT-01). Respects filter effort.

**Business value:** Recovers abandoned browse-to-filter sessions that currently end at dead-end empty states. Increases filtered-PLP return rate and filter-to-PDP conversion; reduces homepage bounce for returning users.

**Complexity: Low–Medium**
- Dependencies: Serialize/deserialize filter state to URL, store `lastPlpUrl` + `lastFilterState`, homepage/empty-state component, deep-link routing (must survive broken `/undefined` hydration — NAV-01). No ML.
- Effort: Front-end state capture + 2–3 placement components.

**Generic vs True Personalization:** Generic would be homepage "Shop By Category" tiles identical for all (`01-current-state/page-analysis.md:47`). True because CTA URL, label, and category are derived from *this session's* last browsed context; a first-time visitor sees no Continue prompt, a TV browser sees TV, a fridge browser sees fridge.

**Why it matters:** FILTER-01 shows users lose track of applied filters even *within* a session; across sessions the loss is total. Continue Shopping externalizes that memory so research compounds instead of resets. For Transcom, where L1/L2 SEO blocks already push grids below the fold (IA-03), returning users should not pay that scroll cost twice.

---

### PER-03 — Resume Comparison (Persistent, Personalized Compare)

**User problem:** Comparison is core for high-ticket (Journey D — 3 Smart TVs 55–65" `02-ux-audit/user-journey-friction.md:75-96`) but today `/compare` is empty and requires hand-typing `Model name or part of product details` three times (`01-current-state/page-analysis.md:173-178`, INTERACTION-01 P1). PDP `Compare` clicks appear to do nothing guest-side (AUTH-02 `02-ux-audit/issue-register.md:40`), so users abandon comparison and buy uninformed.

**Target user:** Considered-comparison shoppers (TV, AC, fridge, washer) who added 1–2 items via PDP `Compare` (`01-current-state/page-analysis.md:129-130`) but did not complete the table.

**Trigger:**
- User clicks `Compare` on PDP (any of 101 PDPs) → item enqueued.
- Trigger to surface: Next PDP view, PLP visit, `/compare` visit, or return visit with 1+ queued items. Also trigger on second `Compare` click: "You have 2 TVs to compare — view now?"

**Data signals required:**
- `compareQueue` {productSlug, category, brand, addedAt} in localStorage (anonymous) synced to wishlist/compare store when authenticated.
- Category coherence signal: if queue contains `smart-tv` items, prioritize adding third TV vs mixing fridge — use category affinity.
- No ratings or inventory ML needed v1.

**Journey placement:**
- Sticky compare bar (bottom sheet) on PLP/PDP: thumbnails of queued items (1/3, 2/3) + `Compare now` + `Clear`.
- `/compare` table auto-populated from queue — search inputs become *add-more* only, not primary population.
- Toast on PDP Compare click: "Added Haier H55P7UX to comparison (2/3)" (also fixes FEEDBACK-01 `02-ux-audit/issue-register.md:42`).

**User value:** Converts comparison from recall-intensive typing to recognition-driven accumulation. Preserves research across PDP hops and sessions — users can build a set incrementally.

**Business value:** Directly unblocks Journey D (highest friction cluster). Increases compare completion rate and compare-to-cart conversion; reduces wrong-size/ticket returns by enabling informed side-by-side of tonnage/liters/panel/EMI.

**Complexity: Medium**
- Dependencies: PDP `Compare` event → localStorage queue → sticky bar component → `/compare` hydration. Requires fixing guest feedback (toast) and queue limit (3 slots `01-current-state/page-analysis.md:174`). Cross-device sync needs auth.
- Effort: Front-end state + compare page refactor + analytics.

**Generic vs True Personalization:** Generic would be a static "Compare popular TVs" table. True because the queued set is *this user's* accumulated shortlist across *their* browsing sequence; empty for new visitors, pre-filled with *their* picks on return.

**Why it matters:** The current table asks users to remember and type alphanumeric model codes — the worst possible interaction for a task that should be tap-to-accumulate. Persistence turns an abandoned tool into a decision accelerator.

> Overlap: Electronics decision support owns spec-diff logic (`Highlight differences`); personalization owns *that the set is remembered and surfaced personally*.

---

### PER-04 — Behavior-Aware Recommendations: "Because You Viewed / Inspired by Your Browsing"

**User problem:** Current PDP `Related Products` is thin and catalog-similar only (Dell→HP single card `01-current-state/product-page-variations.md:65`, DISC-03 P2 `02-ux-audit/issue-register.md:15`). Homepage `Best Deals`/`Best Selling` are identical for all visitors (`01-current-state/personalization-current-state.md:5`). A user who spent 10 minutes in `Air Conditioner > Residential > Inverter AC` then views Haier TVs gets no cross-category or within-category browsing-aware suggestions.

**Target user:**
- Anonymous browsers with ≥2 PDP views or ≥1 PLP filter interaction (category affinity signal).
- Returning visitors with prior category breadth (e.g., viewed AC + fridge).

**Trigger:**
- PDP footer (after `Related Products`): trigger browsing-aware shelf when view-history ≥1.
- Homepage return visit: trigger when history indicates strong affinity (e.g., 3 TV views in last session).
- Search no-result or low-result: trigger fallback "Based on your browsing" shelf.

**Data signals required:**
- `viewHistory` + `categoryAffinity` (count/dwell per `air-conditioner`, `tv-av/television`, `refrigerators` etc. — derive from `01-current-state/product-discovery.md:56-58` taxonomy depth L1–L4).
- `brandAffinity` (e.g., SAMSUNG 2 views, Haier 1), `priceBandAffinity` (e.g., 60k–90k).
- Co-view signal: products frequently viewed together in same session (no purchase needed).
- Anonymous: session affinity; authenticated: rolling 30-day affinity profile.

**Journey placement:**
- PDP: Second rail `Inspired by your browsing` below generic `Related Products` — labeled explicitly to set expectation.
- Homepage (returning): Dynamic module `Recommended for you — Smart TVs` replacing or reordering one of the 7+ serial category mini-grids (DISC-01 `02-ux-audit/issue-register.md:13`) to reduce overload with relevance.
- PLP empty/filtered-zero: `Because you viewed 55" QLED` alternative set.

**User value:** Discovery becomes *scented* by their own exploration rather than merchandising calendar. Reduces linear scanning of 45-result grids (SORT-01) by surfacing affinity-consistent products first.

**Business value:** Increases PDP-to-PDP traversal, attachment of higher-margin alternatives within affinity band, and mitigates broken discovery paths (NAV-01) by providing a personalized bypass. Differentiates from static Related which today shows single cross-sell and no behavioral lift.

**Complexity: Medium**
- Dependencies: View-history store → affinity scorer (simple rules v1: count + recency weighting, no ML), recommendation service that filters catalog by affinity taxonomy + excludes already-viewed, labeled UI rails.
- Effort: Affinity logic + recommendation API + 2 placement components. ML ranking is phase 2; v1 rule-based suffices.

**Generic vs True Personalization:** Generic = current `Related Products` (laptop→laptop for everyone viewing laptop). True = shelf composition changes per user: TV browser sees TV-led recommendations, AC browser sees inverter ACs in their tonnage band, mixed-browser sees cross-category affinity set. Label makes the personalization legible ("Because you viewed...").

**Why it matters:** `01-current-state/product-discovery.md:29-31` notes no "Frequently bought together" or browsing-aware discovery exists. Without it, every PDP is a dead-end except manual header navigation. Behavior-aware rails turn each PDP into a personalized hub that compounds research rather than restarting it.

---

### PER-05 — Category-Affinity Homepage & PLP Prioritization (First-Time vs Returning)

**User problem:** Homepage serialises 7+ identical mini-grids for every visitor (`01-current-state/page-analysis.md:48-54`, DISC-01 P1) regardless of whether they are a first-time AC seeker, a returning TV researcher, or a fridge comparer. First-time visitors face overload; returning visitors see no acknowledgement of their prior interest. `Personalized Homepage Content` is NOT OBSERVED (`01-current-state/personalization-current-state.md:6`).

**Target user:**
- First-time (no history): needs orientation, not personalization.
- Returning with affinity (≥2 views in category X): needs prioritized path to X.

**Trigger:**
- First-time: no cookie/profile history → show default hierarchy.
- Returning: `categoryAffinity` score exceeds threshold (e.g., ≥2 TV PDP views or ≥1 filtered TV PLP) → reorder/prioritize homepage modules and PLP defaults.

**Data signals required:**
- `visitCount`, `categoryAffinity` as in PER-04, `daysSinceLastVisit`, `trafficSource` (optional: campaign vs organic).
- Device signal for mobile vs desktop layout (MOBILE-01).

**Journey placement:**
- Homepage: Reorder `Shop By Category` tiles (bring affinity category first), promote one personalized mini-grid `Continue exploring — Inverter ACs in your range` above lower-priority categories (e.g., push `Food Processors` below fold for TV-affinity users). Keep `Shop By Brand` but surface affinity brand.
- PLP: Default sort/filter hints (e.g., for 55" affinity, surface `Display Size: 55"` as pre-checked suggestion, not auto-applied — preserves control).
- First-time alternative: Hero help block "Not sure where to start? Find your AC by room size" — a non-personalized orientation that still respects overload.

**User value:** First-timers get a calmer entry (orientation over overload); returners feel recognized and skip re-navigation through L1→L2→L3 hierarchy (`01-current-state/product-discovery.md:52-69`). Both reduce scroll cost past SEO blocks (IA-03).

**Business value:** Lifts homepage CTR for returning segments, reduces bounce, and tests personalization impact without altering catalog. Provides measurable A/B: personalized reorder vs static order.

**Complexity: Medium–High**
- Dependencies: Homepage CMS/modular layout that supports reordering (may require template refactor beyond front-end), affinity scorer, A/B framework, analytics for visitCount.
- Effort: Medium front-end + CMS/layout work; governance needed so merchandising can still pin campaigns (`/campaigns` countdown `01-current-state/page-analysis.md:45`).
- Risk: Over-personalization on first visit must be avoided — rule must default to generic for low-signal visitors.

**Generic vs True Personalization:** Generic = every visitor sees `Electric Kettles → Microwave Oven → Washing Machine → AC → Refrigerator → TV` in fixed order. True = order and promoted grid are per-user: TV-affinity user sees TV module first, AC-affinity user sees AC first, first-timer sees balanced orientation.

**Why it matters:** The homepage today optimizes for catalog completeness, not user journey stage. Personalization lets it serve two masters: quick orientation for the new and fast resumption for the returning — the exact split Journey A vs Journey F needs.

---

### PER-06 — Personalized Search: History-Aware Suggestions & Recent Searches

**User problem:** Search is the fast-path for model-aware buyers (Journey A "know exactly what I want" `02-ux-audit/user-journey-friction.md:5-25`) but today the `Search Here` box (`01-current-state/page-analysis.md:9-10`) has generic placeholder, no example, and autocomplete rendering not verifiable (SEARCH-01 P1 `02-ux-audit/issue-register.md:17`). No `Recent searches`, no typo-recovery (SEARCH-03), no personal history. Users typing `FTKL12TV16WD` must type perfectly.

**Target user:** Repeat searchers, model-aware electronics buyers, and returning visitors who searched `samsung tv` previously.

**Trigger:**
- Search box focus → show `Recent searches` (if any) + `Suggested for you` (affinity-based).
- Type-ahead (≥2 chars): show personalized suggestions ranked by personal history before global popularity.

**Data signals required:**
- `searchHistory` {query, timestamp, resultClickSlug} in localStorage (anonymous) or profile (authenticated) — last 10 queries.
- `viewHistory` → category/brand affinity to bias suggestion ranking (e.g., user with 3 AC views typing "hai" gets `Haier Inverter AC` above `Haier Refrigerator`).
- Global signals (popular queries, trending models) as fallback for low personal signal.

**Journey placement:**
- Search input dropdown: Two sections — `Recent searches` (with clear-X per item) and `Suggested for you` (3–5 affinity-biased suggestions). Below that, standard catalog suggestions.
- Search PLP: If zero/low results, personalized fallback rail `Based on your browsing, you might like...` (ties to PER-04).
- No-result handling: "Did you mean FTKL12TV16WD?" + personalized alternatives in affinity price band.

**User value:** Reduces typing, forgives typos, acknowledges prior search effort, and disambiguates among similar SKUs via personal context (solves IA-01 flat-URL confusion `02-ux-audit/issue-register.md:8`).

**Business value:** Increases search submission → PDP rate, reduces zero-result exits (SEARCH-03 P2), and captures search-to-cart intent faster for high-ticket SKUs where model precision matters.

**Complexity: Medium**
- Dependencies: Search index must support suggestion ranking with personal boost (front-end bias v1 is sufficient; backend boost phase 2), localStorage searchHistory, dropdown UI with sections, clear-history control, analytics for suggestion CTR.
- Effort: Front-end dropdown + history store + lightweight ranking logic; backend suggestion API enhancement optional.

**Generic vs True Personalization:** Generic = same autocomplete list for everyone typing "sam" (popular Samsung SKUs). True = list re-ranks per user: AC-affinity user sees AC models first, TV-affinity user sees TV models first, recent search for `samsung tv` promotes TV even if AC is globally more popular.

**Why it matters:** Electronics model codes are error-prone and high-stakes. Personalizing suggestions with *your* history and affinity turns search from a memory test into recognition — the core usability fix for Journey A.

---

### PER-07 — Location-Aware Delivery Confidence (Invert the Gate)

**User problem:** PDP delivery is gated behind `Enable your Location` before disclosing availability, cost, or timeline (`01-current-state/page-analysis.md:123-124`, PDP-02 P1 `02-ux-audit/issue-register.md:27`). High-consideration buyers at price exposure (Tk 88k AC, Tk 1.38L fridge) hesitate without delivery/install confidence and abandon before CTA. The capability `Location-Based Content` is PARTIALLY OBSERVED as a gate, not as personalization (`01-current-state/personalization-current-state.md:7`).

**Target user:** All PDP visitors, especially fridge/AC/washer buyers where delivery/install is decisive. Location-shy users who will not grant browser permission.

**Trigger:**
- PDP load: show inline `Check delivery & installation` input (pincode/area/district — `Store Locator` already has district dropdown `01-current-state/page-analysis.md:201-203`).
- On pincode entry (or granted location): reveal personalized availability, delivery window, and install fee/timeline without requiring full `Enable your Location` permission.
- Remember pincode/area per session (and profile when authenticated) to personalize delivery estimates on every subsequent PDP/PLP/cart.

**Data signals required:**
- `pincode` / `district` / `area` (user-entered, not permission-gated) — stored in cookie/localStorage + profile `defaultDeliveryLocation`.
- Serviceability matrix: pincode → delivery availability, install fee, timeline (requires ops/logistics feed).
- Store proximity for `Store Pickup` alternative (`Store Locator` data `01-current-state/page-analysis.md:199-204`).

**Journey placement:**
- PDP Options block: Inline field `Enter pincode / Select district → See delivery by [date] + Installation: Free/Paid` + `Store Pickup: 3 stores near you`.
- PLP cards: Badge personalization "Deliverable to your area" vs "Check delivery" based on remembered pincode (subtle, not blocking).
- Cart: Order Summary augments with personalized delivery estimate from remembered location.

**User value:** Confidence before commitment — price can be judged alongside delivery reality. No permission friction; location-shy users can type pincode instead of granting browser location. Memory avoids re-entering on every PDP.

**Business value:** Unblocks PDP-02 conversion gate; reduces PDP exit and cart abandonment where delivery uncertainty is the true blocker. Increases Store Pickup utilization by surfacing proximity from already-known Store Locator inventory.

**Complexity: Low–Medium**
- Dependencies: Pincode input component, serviceability API/logic, delivery estimate copy, persistence of location, Mapbox/store data already exists (`01-current-state/page-analysis.md:203`). No recommendation engine.
- Effort: Component + API integration + copy; logistics feed is the longest lead item.

**Generic vs True Personalization:** Generic = identical `Enable your Location` gate for all. True = delivery message is *personalized to this user's remembered pincode/district* — "Delivers to Mirpur by Sep 7, Installation Tk 1,500" vs "Delivers to Chittagong by Sep 9, Free installation". Two users see different, accurate estimates.

**Why it matters:** The current gate trades confidence for permission — the worst trade at the price-decision moment. Inverting it to pincode-first personalization keeps the trust bar promise (`Free Installation — Selective Items` `01-current-state/page-analysis.md:34`) credible at the PDP where it counts, without demanding location access.

> Overlap: Delivery/logistics team owns serviceability truth; personalization owns *remembering location and rendering personalized estimate per PDP/cart*.

---

### PER-08 — Cart-Based Complementary Suggestions: "Complete Your Setup"

**User problem:** No cross-sell/upsell exists in cart (`01-current-state/personalization-current-state.md:12` NOT OBSERVED, CART-02 `02-ux-audit/issue-register.md:37`) or as bundles/FBT on PDP (`01-current-state/product-discovery.md:30` NOT OBSERVED). Users buying a 55" TV, AC, or washer leave without logical complements (TV wall mount, AC stabilizer/cover, fridge stabilizer, mixer extra jar, vacuum bags) and return for fragmented purchases.

**Target user:** Cart owners (1 item) or PDP viewers with cart containing a primary high-ticket item.

**Trigger:**
- Add to cart (PDP `Add To Cart` ×2 `01-current-state/page-analysis.md:127`) → show personalized complementary shelf in cart drawer/page.
- PDP with cart non-empty: show `Pairs well with what's in your cart` shelf.

**Data signals required:**
- `cartContent` {category, brand, priceBand} — primary signal; no browsing history strictly required but augments.
- Complement affinity rules mapped per primary category:
  - TV (55"+): wall mount, soundbar (`tv-av/soundbar` exists `00-input/sitemap-analysis.md:67`), surge protector.
  - AC (1/1.5 Ton): stabilizer, AC cover, installation kit.
  - Refrigerator (Side-by-side): stabilizer, deodorizer.
  - Washing Machine (8kg): stand/cover, detergent bundle.
  - Mixer-Grinder: extra jar.
  - Fallback for low-ticket (trimmer): generic accessory not needed — suppress shelf.
- Warranty/price-eligibility signal: suppress EMI-ineligible complements if primary has no EMI (PDP-06 inconsistency).

**Journey placement:**
- Cart drawer/page: Rail `Complete your setup — frequently bought with Haier 55" TV` (2–4 complements, addable without leaving cart).
- PDP (when cart non-empty): Secondary rail `Pairs well with your cart`.
- Mini-cart dropdown: Same rail compact.

**User value:** One-stop completion without a second research trip; reduces post-purchase regret ("I forgot the mount") and fragmented delivery.

**Business value:** Increases average order value (AOV) and units per transaction; captures complementary margin on high-ticket primaries where accessory attach is natural. Measurable via attach rate.

**Complexity: Medium**
- Dependencies: Complement rule set per category (merchandised, not ML), cart-state service, add-to-cart from shelf without navigation, inventory/price validation, suppression logic for low-ticket.
- Effort: Rule table + cart/PDP components + analytics; ML co-purchase model is phase 2.

**Generic vs True Personalization:** Generic = static "Accessories" shelf identical for all TV PDPs. True = shelf is *cart-contingent*: empty cart shows no "Complete your setup" (or shows browsing-based fallback), cart with 55" TV shows mount+soundbar, cart with AC shows stabilizer — composition is *this cart's* complement set.

**Why it matters:** Transcom already sells the complements (soundbars, stabilizers, irons) but never connects them to the primary at the moment of highest intent — the cart. Cart-context personalization is the only shelf that can be both relevant and timely without being intrusive.

---

### PER-09 — Lifecycle & Post-Purchase Personalization: Wishlist Price/Stock Nudges, Replenishment & Seasonal Context

**User problem:** Three lifecycle gaps converge: (1) Wishlist appears empty as guest with no persistence feedback (`01-current-state/page-analysis.md:167-171`, AUTH-02), (2) no price/stock alerts beyond generic `Get Stock Alert` on unavailable PDP (`01-current-state/page-analysis.md:131`, FEEDBACK-02), and (3) no seasonal/contextual relevance for climate-driven categories (AC before summer, fridge before Eid, heater/iron seasonal). Users save nothing because saving seems to do nothing.

**Target user:**
- Wishlist savers (authenticated) who viewed high-ticket but did not purchase.
- Post-purchase owners (fridge/AC/washer) where accessory or service lifecycle exists.
- Seasonal considerers (AC interest in Feb–Apr, fridge pre-summer, TV pre-tournament) — contextual segment.

**Trigger:**
- Wishlist/add-to-wishlist → trigger price-drop or back-in-stock notification (email/SMS/push or on-site banner next visit).
- Post-purchase (after order tracking `Track Order Status` / `Track Your Service` `01-current-state/ecommerce-capabilities.md:61` confirms delivery) → trigger complementary/service reminder window (30/90 days).
- Seasonal calendar trigger + affinity: AC-affinity users in pre-summer see AC service/upgrade nudge.

**Data signals required:**
- `wishlist` {productSlug, savedPrice, savedAt, category} — requires authenticated persistence (already implied `AUTHENTICATION REQUIRED` `01-current-state/personalization-current-state.md:13-14`; `01571721235` OTP flow `01-current-state/user-journeys.md:154-178`).
- `purchaseHistory` / `orderStatus` (delivered).
- `priceHistory` / `stockStatus` feed (compare savedPrice vs current; `Currently Unavailable` vs `In stock` `01-current-state/page-analysis.md:112-113`).
- Contextual calendar signal: season, campaign window (`Campaign Online Offer Valid Till Sep 30, 2026` `01-current-state/page-analysis.md:118`), and user affinity.

**Journey placement:**
- On-site (next visit): Banner `Your wishlist: Haier 55" TV dropped Tk 5,000 — back in your price range` with deep-link to PDP; or `Your Haier AC (1 Ton) — pre-summer service check?`.
- Homepage (seasonal segment): `For you — Prepare for summer: Inverter ACs in your viewed range` (only for AC-affinity segment, not broadcast).
- Email/SMS/push (if consented): Price-drop and back-in-stock alerts — the only off-site personalization.

**User value:** Saved items become actionable — users are notified when waiting pays off. Post-purchase nudges are helpful, not promotional (service, not spam). Seasonal context aligns offers with *their* climate need, not broadcast blasts.

**Business value:** Recovers considerers without discounting to everyone (targeted price-drop only to wishlist owners). Increases repurchase/accessory attach and seasonal campaign efficiency by suppressing irrelevant seasonal promos for non-affinity users. Leverages existing EMI/warranty trust to make nudges credible.

**Complexity: High**
- Dependencies: Authenticated wishlist + order history, price/stock change feed, notification consent + channel, preference center, seasonal rule engine, on-site banner system. Requires cross-functional: engineering (event pipeline), ops (price/stock), CRM/marketing (messaging).
- Effort: Largest scope; should start on-site only (banner + homepage seasonal module) before off-site notifications.
- Prerequisites: PER-01/02/03 data layer (view history, affinity) reused here.

**Generic vs True Personalization:** Generic = site-wide `Online Offer Valid Till Sep 30` countdown for all (`01-current-state/page-analysis.md:118`). True = *your* wishlist item dropped to *your* saved-price threshold, or *your* AC-affinity triggers a pre-summer module that a TV-only browser never sees. Seasonal relevance is *segmented* by affinity, not broadcast.

**Why it matters:** Transcom's catalog is durable — the next purchase may be 6–18 months away. Without lifecycle memory, the platform treats a returning buyer as a new visitor. Lifecycle personalization is the only way the site proves it remembers ownership and consideration, which is how trust compounds for high-ticket repeat.

---

## 5. Prioritization & Sequencing

| Priority | Opportunity | Complexity | Why this order |
|---|---|---|---|
| **P0 — Foundation (sprint 1–2)** | PER-01 Recently Viewed, PER-02 Continue Shopping, PER-07 Location-Aware Delivery | Low / Low–Med | Immediate Journey F and PDP-02 recovery; no ML, highest signal-to-effort, unblocks all later personalization with view-history + location store |
| **P1 — High impact (sprint 3–5)** | PER-03 Resume Comparison, PER-06 Personalized Search, PER-04 Browsing-Aware Recs | Med | Unblocks Journey D (comparison) and Journey A (search precision); PER-04 reuses affinity signal from PER-01/02 |
| **P2 — Growth (sprint 6+)** | PER-05 Homepage Affinity Reorder, PER-08 Cart Complements | Med–High / Med | Requires CMS/layout + cart rule work; measurable AOV lift but needs foundation data layer |
| **P3 — Lifecycle (quarter 2)** | PER-09 Wishlist/Lifecycle/Seasonal | High | Depends on auth, order history, price feed, and consent; start on-site banners before off-site messaging |

**Measurement for each:** Define before build — e.g., PER-01 re-entry rate to PDP, PER-02 filtered-PLP return rate, PER-03 compare completion, PER-06 search-to-PDP, PER-07 PDP-to-cart where pincode entered, PER-08 attach rate, PER-09 wishlist-to-purchase recovery rate. All A/B-able anonymous vs control.

---

## 6. Dependencies & Enablers

- **Anonymous persistence layer:** localStorage/cookie schema for `viewHistory`, `categoryAffinity`, `searchHistory`, `lastPlpContext`, `compareQueue`, `deliveryLocation` — shared across PER-01/02/03/04/06/07. No backend required v1; authenticated sync phase 2.
- **Event taxonomy:** Standardize `pdpView`, `plpFilter`, `searchQuery`, `searchResultClick`, `addToCompare`, `addToCart`, `wishlistAdd`, `pincodeCheck` — required for affinity and trigger reliability.
- **Serviceability feed:** Pincode/district → delivery window/fee (PER-07 logistics dependency).
- **Catalog complement rules:** Per-category accessory mapping (PER-08 merchandising dependency).
- **Price/stock feed + consent:** For PER-09 on-site banners and future notifications.
- **CMS modularity:** Homepage must support module reordering/suppression (PER-05).

---

## 7. What Is *Not* Proposed (and Why)

- **Generic "Recommended for you" shelf with no signal:** Rejected — would duplicate existing non-personalized `Related Products`/`Latest Products` (`01-current-state/ecommerce-capabilities.md:34`) without behavioral trigger; fails the True Personalization test.
- **Language/currency/preference saving beyond wishlist:** `Saved Preferences` NOT OBSERVED but low value for this audience; deferred.
- **Static bundle `Frequently Bought Together`:** NOT OBSERVED but without personal signal it's merchandising, not personalization — covered instead by cart-contingent PER-08.
- **Any capability already observed as personalized:** None — all 14 checked remain NOT OBSERVED, so no exclusion needed beyond the generic modules above.

---

## 8. Source Traceability

Each opportunity maps to Phase 1/2 evidence:

- PER-01/02 trace to `01-current-state/personalization-current-state.md:9-10` (Recently Viewed / Continue Shopping NOT OBSERVED), `02-ux-audit/issue-register.md:14` DISC-02, `02-ux-audit/user-journey-friction.md:123-142` Journey F.
- PER-03 traces to `01-current-state/page-analysis.md:173-178` /compare, `01-current-state/ecommerce-capabilities.md:23-25`, INTERACTION-01 `02-ux-audit/issue-register.md:41`.
- PER-04 traces to `01-current-state/product-discovery.md:29-31` (no browsing-aware discovery), `01-current-state/personalization-current-state.md:11` PDP browsing-aware NOT OBSERVED, DISC-03 `02-ux-audit/issue-register.md:15`.
- PER-05 traces to `01-current-state/page-analysis.md:48-54` 7+ mini-grids, DISC-01 `02-ux-audit/issue-register.md:13`, `01-current-state/personalization-current-state.md:6` Personalized Homepage NOT OBSERVED.
- PER-06 traces to `01-current-state/page-analysis.md:9-10` Search Here, SEARCH-01/02/03 `02-ux-audit/issue-register.md:17-19`, Journey A `02-ux-audit/user-journey-friction.md:5-25`.
- PER-07 traces to `01-current-state/page-analysis.md:123-124` Enable your Location gate, PDP-02 `02-ux-audit/issue-register.md:27`, `01-current-state/personalization-current-state.md:7` Location-Based PARTIALLY OBSERVED.
- PER-08 traces to `01-current-state/personalization-current-state.md:12` Cart-Based Recs NOT OBSERVED, CART-02 `02-ux-audit/issue-register.md:37`.
- PER-09 traces to `01-current-state/personalization-current-state.md:13-14` Wishlist/Account, `01-current-state/page-analysis.md:118` Offer validity, `01-current-state/ecommerce-capabilities.md:61` Track Order/Service.

---

*End of personalization opportunities. 9 opportunities (PER-01–PER-09) each with user problem, target user, trigger, data signals, journey placement, user/business value, complexity, generic-vs-true distinction, and sequencing. All verified against NOT OBSERVED inventory. No generic recommendation proposed without signal.*
