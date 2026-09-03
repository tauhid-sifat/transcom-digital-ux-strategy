# Product Discovery & Search — Audit

## Discoverability Theme

### [DISC-01] Homepage serialises 7+ category mini-grids without prioritisation (P1, HIGH) — Type A/F
**Location:** Homepage (`/`) — `page-analysis.md:48-54` (Electric Kettles, Microwave Oven, Washing Machine, Celling Fans, AC, Refrigerator, TV, Food Processors + Best Deals + Best Selling). **Current:** Each is a carousel (5 cards + Quick View) stacked vertically. **Problem:** No visual weight differentiation; scanning cost high; cognitive load exceeds 7±2 limits; hero *Best Deals* competes with multiple micro-grids. **Impact:** First-time browse users cannot choose a starting point; bounce. **Direction:** Curate homepage to category navigation + single hero + one curated carousel per intent segment, defer long tail to PLPs.

### [DISC-02] No “Recently Viewed” / “Continue Shopping” trail (P1, HIGH) — Type G
**Location:** Homepage, PLP header, Cart empty, PDP — `personalization-current-state.md:1-3`. **Current:** Grep for “Recently”, “Recommended for you”, “Continue shopping” returns 0 hits across 20+ reads. Cart empty offers no “Continue Shopping” CTA (`cart-checkout.md:10-35`). **Problem:** Interrupted high-consideration sessions (research TVs then return) lack resumption. **Impact:** Journey F unserved; returning users restart hierarchy from root. **Direction:** Add persistent Recently Viewed rail (guest localStorage + account sync).

### [DISC-03] Related Products rail is thin and not browsing-aware (P2, MEDIUM) — Type G
**Location:** PDP footer — `product-page-variations.md:65` (Dell→HP single card; other PDPs truncated before rail). **Current:** Single cross-sell card observed. **Problem:** Insufficient alternatives/complements to inform decision; not personalized. **Impact:** Users who want 2–3 comps must return to PLP to hunt. **Direction:** Expand to 4-6 category-relevant related + accessories per template.

### [DISC-04] Shop By Category taxonomy vs marketing tiles mismatch (P2, HIGH) — Type C
**Location:** Homepage `Shop By Category` 6 tiles list *Dishwashers* (`page-analysis.md:45-47`) but sitemap/category hierarchy has no `/dishwashers` top category. **Current:** Tile links vs sitemap taxonomy diverge. **Problem:** Content–navigation inconsistency. **Impact:** Dishwasher shoppers follow tile to sparse/placeholder state. **Direction:** Align marketing tiles to indexed taxonomy or explicitly mark tiles as campaign.

---

## Search Theme

### [SEARCH-01] Search suggestions/autocomplete not verifiable (P1, MEDIUM) — Types A/B
**Location:** Header `Search Here` textbox — `01-current-state/product-discovery.md:40-43`, `ecommerce-capabilities.md:13`. **Current:** Textbox focus/type works but suggestion dropdown not captured before timeout; evaluation returned no suggestion DOM. Verify `pdpTabs` speculation not present. **Problem:** “Know exactly what I want” (Journey A, e.g., `FTKL12TV16WD`) lacks fast-path acceleration; violates efficiency heuristic. **Impact:** Typing full model vs picking suggestion doubles effort; typos not corrected inline. **Direction:** Implement debounced typeahead with product/brand/category suggestions + typo tolerance; verify via retest.

### [SEARCH-02] Search placeholder is generic (P3, HIGH) — Type D
**Location:** Header placeholder `Search Here` on all pages (`page-analysis.md:11`). **Current:** No example hint (“Try ‘1.5 Ton Inverter AC’ or ‘55 inch TV’”). **Problem:** Recall burden; users uncertain whether SKU, model, or plain language works. **Impact:** Vague queries, higher zero-result rate. **Direction:** Rotate example hint per category context.

### [SEARCH-03] Zero-result / typo handling unknown (P2, MEDIUM) — Type F/G
**Location:** `/search` (no-result not triggered in Phase 1, `user-journeys.md:56-58`). **Current:** No observed zero-result template. **Problem:** Typos for Bengali-English mixed queries likely dead-end. **Impact:** Silent failure → exit. **Direction:** Design zero-result page with did-you-mean, category fallbacks, and related suggestions.

### [SEARCH-04] Search vs brand PLP duplication (P2, HIGH)
Duplicate of NAV-02 — listed here for search governance. `/search?Brand=samsung` vs `/samsung` renders identically; search facet not canonicalised.

---
*Evidence: `product-discovery.md:1-27`, `page-analysis.md:38-60,72-88`, `personalization-current-state.md:1-3`, BrowserOS `searchEval`.*
