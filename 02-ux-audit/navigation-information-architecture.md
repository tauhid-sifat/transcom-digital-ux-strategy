# Navigation & Information Architecture — Audit

> Baseline evidence cross-referenced; each issue traces to phase-1 doc + snapshot element.

## [NAV-01] Browse paths terminate at `/undefined` (P0, HIGH)
See `usability-issues.md:10-35`. **Location:** Homepage 11 See All + Brand sub See All. **Current:** links render as `/undefined` / `/samsung/undefined` per `page-analysis.md:56-57`. **Why friction:** Central discovery affordance dead-ends — violates consistency/error-prevention; blocks Journey B/C at entry. **Who:** Browsing first-timers and category-knowers. **Direction:** Guard slug generation, automated link audit.

## [IA-01] Flat PDP URL namespace severs category hierarchy (P1, HIGH) — Type D/C
**Location:** All 101 PDPs at root (e.g., `/daikin-...-1-ton`) — `sitemap-analysis.md:1-3` Unusual URL Pattern 1. **Current:** No `/refrigerators/.../product` nesting; PDP slug gives no category scent. **Problem:** Users cannot infer parent category from URL/sharing; breadcrumb is only hierarchy signal, not URL. SEO crawl coherence weakened. **Impact:** Return users via history/bookmark lose context; link sharing omits category context. **Direction:** Consider hierarchical alias with 301 while preserving flat canonical.

## [IA-02] Missing `/tv-av` root creates orphan children (P2, HIGH) — Type C
**Location:** `/tv-av/television/*`, `/tv-av/soundbar` exist; `/tv-av` absent from sitemap (`sitemap-analysis.md:74-76`). **Current:** Clicking TV|AV breadcrumb parent may land on missing/redirect. **Problem:** IA completeness gap; inconsistent parent for category tree. **Impact:** TV discovery (huge ticket) has broken parent navigation. **Direction:** Create `/tv-av` landing that aggregates television+sounds.

## [IA-03] Long-form SEO buying guide buries product discovery on L1/L2 category pages (P1, HIGH) — Type A/D
**Location:** `/air-conditioner`, `/refrigerators`, `/washing-machine`, `/home-kitchen` — `page-analysis.md:90-91`. **Current:** 800–1500-word guide (“Energy Efficiency… Room size…” for AC; “Capacity… Space…” for fridge) sits above/beside product grid and pushes filters/grid below the fold. **Problem:** Discovery goal vs SEO goal clash; interaction cost spikes before filtering/sorting even seen. **Impact:** Category shoppers must scroll past education before they can narrow — cognitive load. **Direction:** Collapse SEO into expandable “Buying Guide” below grid or into separate guide hub, keep above-fold for filters/sort.

## [IA-04] Trailing-hyphen product slugs indicate hygiene risk (P2, HIGH) — Type C/E
**Location:** 4 PDPs (`pureit-classic-23l-`, `samsung-65-qn85c-…-`, `samsung-side-by-side-…-700-`) — `sitemap-analysis.md:4-6`. **Current:** Slugs end with `-` suggesting truncation. **Problem:** Copy-pasted links may 404; share/bookmark failures. **Impact:** External traffic (social/SEO crawl) hits dead ends. **Direction:** Sanitise slug generation + redirect trailing-hyphen variants.

## [NAV-02] Brand and search paths duplicate without canonical clarity (P2, HIGH) — Type C/F
**Location:** `/samsung` (brand PLP) vs `/search?Brand=samsung`. **Current:** Both render brand-filtered grid (`sitemap-analysis.md:Duplicate URLs` table). **Problem:** Two authoritative paths for same intent — user uncertainty which is “official”. **Impact:** Bookmark/confusion; analytics split. **Direction:** Canonical brand PLP; search brand filter redirects to brand PLP when brand is sole facet.

## [NAV-03] Header navigation labels conflate categories (P2, MEDIUM) — Type C
**Location:** Header `All Categories` + `Products` + `Brands` + utility bar (B2B/Store Locator/Track). **Current:** `page-analysis.md:8-14` header reveals overlapping labels without clear scope (“All Categories” vs “Products”). **Problem:** Recognition vs recall — users cannot predict where Smart TV lives. **Impact:** Reliance on search over browse; taxonomy learning slowed. **Direction:** Consolidate into single mega-menu under `Shop by Category` with brand as filter, not parallel nav.

## [NAV-04] Footer policy content loaded via `about.transcomdigital.com` iframe — IA boundary leakage (P3, HIGH) — Type C
**Location:** `/page/terms-of-use` — `page-analysis.md:214-220`. **Current:** Terms render in iframe/article loader with duplicate ALL lists and external About host links. **Problem:** Navigation jumps domain; back behaviour inconsistent. **Impact:** Trust/legal discovery ruptures flow. **Direction:** Host policy content natively with same header/footer shell.

---
*Evidence: `sitemap-analysis.md`, `site-inventory.md:6`, `page-analysis.md:7-34,56-57`.*
