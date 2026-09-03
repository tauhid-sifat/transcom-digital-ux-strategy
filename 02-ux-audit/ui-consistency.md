# UI Consistency — Audit

## Visual Hierarchy

### Inconsistency 1 — EMI signaling fragments across PLP vs PDP
**Category:** CONSISTENCY, TRUST — **P3**, HIGH. **Location:** PLP card badge `EMI36` + `EMI From 1167 Tk/month` vs PDP block `EMI From 2633 Tk/month` + `Avail Bank EMI` link — `page-analysis.md:86-88,114-117`. **Current:** Badge is numeric code; PDP text is prose. No shared pattern. **Direction:** Unify to “EMI up to X months — From Tk Y/month” label per card and PDP, same styling.

### Inconsistency 2 — Shop By Category tile taxonomy vs sitemap taxonomy (Dishwashers)
**Category:** CONSISTENCY, IA — **P2**, HIGH. See DISC-04.

### Inconsistency 3 — Category SEO heading style vs product grid typography
**Location:** PLP L1/L2 category guides use bold instructional headings (Energy Efficiency, Room size) while product grid uses dense card badges (discount, EMI, New) — visual priority conflict. **Direction:** Re-parent guide below grid or into collapsible drawer.

## Interaction Consistency

### Inconsistency 4 — Primary CTA duplication on PDP
**Category:** INTERACTION, VISUAL — **P3**, HIGH. Two `Add To Cart` buttons on PDP (`page-analysis.md:126-128`, `product-page-variations.md:40`). **Direction:** Single sticky CTA on scroll.

### Inconsistency 5 — Compare entry (PDP one-tap) vs compare population (hand-search)
**Category:** INTERACTION — **P1**, HIGH. PDP `Compare` is one-tap but `/compare` table expects search-by-model — asymmetrical interaction models. **Direction:** Make compare accumulation one-tap end-to-end (sticky bar).

### Inconsistency 6 — See All pattern: some cards link to category taxonomy, homepage feature See All links to `/undefined`
**Category:** CONSISTENCY, NAV — **P0**, HIGH. See NAV-01. Homepage See All vs Brand See All both broken — consistency failure of anchor generation.

## Content Consistency

### Inconsistency 7 — Warranty keys shift per appliance (Compressor vs Panel vs Motor vs Special Component)
**Category:** CONSISTENCY, PDP — **P2**, HIGH. `product-page-variations.md:61` shows `Special Component 0M/60M` unexplained. **Direction:** Canonical keys with per-category mapping table and legend.

### Inconsistency 8 — Trust and promo claims differ in location and promise
**Category:** CONSISTENCY, TRUST — **P2**, HIGH. Homepage trust bar 4 items (`Free Installation Selective Items` etc.) vs PDP no trust echo vs footer service columns. **Direction:** Echo relevant trust badges per PDP category near price/CTA.

### Inconsistency 9 — Iconography without labels
**Category:** CONSISTENCY, ACCESS — **P2**, MEDIUM. Header cart ``, wishlist ``, PDP Compare `` / Wishlist `` / Share `` are icon-glyphs without adjacent text in snapshot for some breakpoints; PDP trio has text, header has mixed. **Direction:** Ensure icon+label pair always, with `aria-label` fallback.

## State Consistency

### Inconsistency 10 — Stock state switch changes CTA type entirely
**Category:** CONSISTENCY, FEEDBACK — **P2**, HIGH. In-stock → `Add To Cart` (×2) vs out-of-stock (Dell) → `Get Stock Alert` (×2). No intermediate “Out of stock — alert me when back” microcopy. **Direction:** Standardise out-of-stock to disabled Add To Cart + explained alert affordance.

---
*All inconsistencies validated against `page-analysis.md:113-135`, `product-page-variations.md:45-67`, `site-inventory.md:92-93`, `ecommerce-capabilities.md:16-32`.*
