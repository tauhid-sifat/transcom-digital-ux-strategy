# Category & Filtering — Audit

## Category Clarity

### [IA-03] SEO guide buries product discovery (P1, HIGH)
Duplicate from IA theme — impacts category L1/L2 specifically (`/air-conditioner`, `/refrigerators` long-form sections). Extends here because category PLP's primary job is product discovery; SEO block violates product-discovery priority. See `navigation-information-architecture.md`.

## Filters

### [FILTER-01] No active-filter feedback — chips/summary absent (P1, MEDIUM)
**Location:** All PLPs sidebar + results header. **Current:** Sidebar checkboxes exist but no chip row above grid; `plpSort` `filterCount 4` indicates DOM facets but zero chips. `user-journeys.md:74-76` notes “Apply filter … NOT TESTED”. **Problem:** System status invisible. **Impact:** Multi-filter refinement (e.g., TV 55"+ Samsung + 1–2L price) becomes unmanageable. **Direction:** Add chip row + count + Clear all above grid.

### [FILTER-02] Customer Review facet heading with no buckets (P2, HIGH)
**Location:** PLP sidebar — `page-analysis.md:81,102`. **Current:** Heading `Customer Review` renders but no rating buckets enumerated in any PLP evaluate (`ecommerce-capabilities.md:19`). **Problem:** Sets expectation then violates it — looks broken. **Impact:** Users seeking 4★+ filtered confidence get no payoff. **Direction:** Hide facet until buckets populated, or map to rating ranges.

### [FILTER-03] Price controls compete: dual slider + overlapping bucket list (P2, HIGH)
**Location:** Smart TV facet `Price: 0 - 10,55,000` dual slider + bucket list `0 to 1,00,000`, `1,00,001 to 2,00,000`, etc. (`page-analysis.md:77-78`). **Current:** Two isomorphic controls side-by-side. **Problem:** Users unsure which is canonical; slider precision vs bucket mental model conflict. **Impact:** Either ignored, reducing price-targeting that drives EMIs. **Direction:** Keep slider primary; show buckets as non-overlapping presets that update slider, or collapse buckets into slider tick labels.

### [FILTER-04] Taxonomy duplication: Display Size vs Screen facets share domain (P3, HIGH)
**Location:** Smart TV — `Display Size 55"(10) 43"(7) …` vs `Screen 32"(2) 43"(1)` (`page-analysis.md:80`). **Current:** Two headings partition size domain arbitrarily. **Problem:** Products may be classified under one not the other; filtering by one misses products in the other. **Impact:** False negatives → users wrongly conclude size unavailable. **Direction:** Merge into single Size facet with validated values.

### [FILTER-05] Filter apply interaction not verifiable (MEDIUM deferral)
**Location:** PLP sidebar checkboxes (brand/price) — `user-journeys.md:74` “Apply filter … NOT TESTED”. **Current:** Checkbox presence VERIFIED but URL/refresh not exercised. **Problem:** Unknown whether filters auto-apply vs require Apply button; unknown pagination reset; potential flicker. **Impact:** Research users risk losing scroll position or surprise zero-result. **Direction:** Retest filter click with network/progress feedback; ensure no full-page reload before scroll anchor.

## Sorting

### [SORT-01] Sort control is a placeholder with no visible options (P1, HIGH)
**Location:** PLP header — `page-analysis.md:84-85`, verification `plpSort sortOptions: []`. **Current:** Literal `Select Sort Option` textbox with no dropdown options. **Problem:** Undiscoverable sorting — users cannot sort by price low→high, popularity, discount. **Impact:** Comparison shopping slows; default order opaque. **Direction:** Implement real select: Relevance / Price low→high / Price high→low / Newest / Discount.

### [SORT-02] Pagination model is ambiguous (P2, HIGH)
**Location:** PLPs + campaign hub — `page-analysis.md:84-86` (`Show 12 <of 1> 1`; campaign `Show 10 Showing 1 of 1`). **Current:** `Show 12` selector plus `<of 4>` not obviously tied; numeric page input `1` plus `<` `>` arrows. Two `Show 12` instances (above and below grid) duplicate state. Verification: `plpSort paginationText: Showing 1-12 of 45 results` shows server knows total but header shows “‹of 1›”. **Problem:** Model confusion — is there 1 page or 4? Is Show 12 results per page or total? **Impact:** Users do not know catalogue depth; trust in completeness low. **Direction:** Unify to “Showing 1–12 of 45 — Show [12|24|48]” + numbered pagination with active state.

## Product Card Information (within category)

### [CARD-01] Card EMI badge “EMI36” cryptic without explanation (P2, MEDIUM)
**Location:** Every PLP card shows `EMI36` + `EMI From X Tk/month` (`page-analysis.md:86-88`). **Current:** Numeric suffix 36 (months) unexplained; tooltip not described. **Problem:** Recognition burden for financing novices. **Impact:** Financing-eligible users skip benefit because code is opaque. **Direction:** Label “EMI up to 36 months” with info icon linking EMI Bank List.

---
*Evidence: `page-analysis.md:62-104`, `product-discovery.md:70-95`, `ecommerce-capabilities.md:16-22`, BrowserOS `plpSort` + `filterEval`.*
