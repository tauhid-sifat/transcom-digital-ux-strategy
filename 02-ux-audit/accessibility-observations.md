# Accessibility Observations — Audit

> No automated axe/lighthouse run; observations from snapshot/read semantics and interaction captures only. Marked MEDIUM confidence where heuristic rather than tool-measured. Not a WCAG conformance audit.

## Semantic Structure

### [ACCESS-01] Heading hierarchy on PLP and PDP is plausible but unverified for skipped levels
**Location:** PLP `h1 Smart TV` → `h2 Latest Products` → `h3 Price/Brand` (`page-analysis.md:74-76`); PDP `h1 Daikin…` → `h2 Options, Related Products` (`page-analysis.md:111`). **Current:** Headings appear logical. **Risk:** SEO long-form on PLPs may insert multiple `h2`/`h3` before filters/grid, pushing grid heading below fold for screen-reader virtual cursor. **Direction:** Order headings so `h1 category name` → `h2 Filters` → `h2 Latest Products` → product list `<ul>`; keep SEO in `<section aria-labelledby>`.

### [ACCESS-02] Icon-only controls risk missing accessible names
**Location:** Header cart ``, wishlist ``, PDP trio ` Compare /  Wishlist /  Share`. Snapshot shows banner/link generics with icon glyph text, not explicit `aria-label` strings beyond ` Wishlist` text node. Evaluate did not surface `aria-label`. **Current:** Some controls expose glyph + text; others expose glyph alone (header cart link text is glyph only ``). **Problem:** Screen-reader label missing where glyph is non-text. **Risk:** WCAG 4.1.2 Name-Role-Value failure for cart/wishlist buttons. **Confidence:** MEDIUM. **Direction:** Retest with screen reader/axe; ensure each icon control has `aria-label` (e.g., “Shopping cart, 0 items”).

## Keyboard & Focus

### [ACCESS-03] Filter sidebar keyboard operability not tested but implied to work — focus order suspect
**Location:** PLP slider (two handles) + checkboxes as `Abbr` elements (`page-analysis.md:77-79`). **Current:** Filters rendered as `Abbr` or generic divs, not native `input[type=checkbox]` in some snapshots; slider is `role=slider`-less div pair. If custom controls, keyboard reach may be missing. **Risk:** Keyboard users cannot refine category → critical path blocked. **Confidence:** MEDIUM (requires tab-sequence test). **Direction:** Verify tab order reaches each facet; ensure custom checkboxes have `role=checkbox` + `aria-checked` + spacebar handling.

### [ACCESS-04] Sort control placeholder — not a native select so not announced as combobox
**Location:** PLP `Select Sort Option` — `category-filtering.md SORT-01` placeholder. **Current:** Element is generic textbox/div, not `<select>` or `role=combobox`. No `aria-expanded` or option list relationship. **Risk:** Keyboard and screen-reader users do not perceive it as a listbox. **Direction:** Replace with native `<select>` or ARIA 1.2 combobox + listbox.

## Forms

### [ACCESS-05] Login phone split-field lacks instructions and association
**Location:** `/login` two textboxes + `+880` selector (`page-analysis.md:193-194`). **Current:** Two unlabeled textboxes (`textbox [ref=e11]` `textbox [ref=e12]`) beneath single country selector. No field label beyond country image. **Risk:** Screen readers announce two unlabelled textboxes; placeholder label missing → WCAG 3.3.2 Labels. **Direction:** Use single `<input type=tel>` with `autocomplete=tel` + visible label “Phone number (Bangladesh +880)”, with format hint.

## Perceivable — Contrast & Text

### [ACCESS-06] Discount/savings badge colour contrast not measured — dense card badges compete
**Location:** PLP cards: strikethrough original price, red? discount `%` badge, `EMI36` badge, `New`/`Pre-Order` tag (`page-analysis.md:86-88`). **Current:** Multiple small badges with likely coloured backgrounds; contrast not captured. **Risk:** Colour-only conveyance for “New/Pre-Order” vs discount distinction. **Direction:** Run contrast audit (WCAG AA) on card badges; supplement colour with shape/position and ensure savings % is not colour-alone.

### [ACCESS-07] PDP stock status text colour likely carries semantic meaning but not proven non-colour-dependent
**Location:** PDP `In stock` vs `Currently Unavailable` (`product-page-variations.md:58`). **Current:** Text status adjacent to price; colour likely green/red. **Risk:** Colour-alone status → users with colour vision deficiency miss availability. **Direction:** Ensure status includes icon/position plus text, not colour alone.

## Operable — Target Size & Responsive

### [ACCESS-08] Touch target crowding on PLP filter facets and product cards
**Location:** Filter facets: small `Abbr` checkboxes per brand (`SAMSUNG(14)` etc.) + dense card Quick View buttons (`page-analysis.md:87`). **Current:** `Abbr` labels likely <24px hit area. **Risk:** Motor impairment + mobile touch → missed taps. **Direction:** Increase row height to ≥44px per WCAG 2.5.8; retest mobile.

## Understandable — Feedback & Errors

### [ACCESS-09] Filter reset and no-result feedback not keyboard-announced
**Location:** PLP filter Reset link + empty PLP state (`page-analysis.md:82,90-91`). **Current:** PLPs may show `Show 12‹of 1›` with zero cards + SEO text — no live region announcing “0 results” or “filters cleared”. **Risk:** Screen-reader users do not perceive filter result change. **Direction:** Add `aria-live="polite"` region for result count updates; announce filter changes.

## Additional Observations Requiring Tooling

| Area | Why not conclusive | Next step |
|------|---------------------|-----------|
| Colour contrast across page | No tool run | Lighthouse/axe on homepage, PLP, PDP |
| Heading skip audit | Snapshot headings not enumerated for hidden sections | WAVE structural run |
| Focus order | Tab sequence not captured | Manual keyboard trail PLP→PDP→Cart |
| Alternative text for gallery | Image `alt` not captured beyond “Transcom logo” | Product image alt audit (PDP gallery) |

---
*Evidence: snapshots/textboxes refs `e3`, `e8`, `e9`, `e11–13`; Phase 1 page-structure reads; no claims beyond observed glyph/text presence.*
