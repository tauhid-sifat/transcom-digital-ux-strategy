# Account & Authentication — Audit

## Login Entry

### [AUTH-01] Phone-OTP-only authentication with split phone field (P2, HIGH) — Types A/E
**Location:** `/login` — `page-analysis.md:190-196`, `user-journeys.md:152-160`. **Current:** Form shows Bangladesh flag + `+880` selector, two textbox inputs for phone, `Next` button; copy “Welcome back! Enter your mobile phone number … If you are a new user, your account will be created.” No password, no social login observed in snapshot. **Problem:** Split field (two textboxes) is unusual — users must guess split point (e.g., 5+5 vs continuous). OTP-only flow excludes desktop users without immediate phone access and password-comfortable segments; split input slows entry and risks format errors. **Impact:** Authentication friction at the exact moment cart/wishlist/compare demand login — Journey E/F abandonment. **Direction:** Use single phone input with `+880` prefix auto-applied + format mask; document that OTP-verified session persists.

### [AUTH-02] Wishlist/Compare guest clicks appear inert — no inline persistence feedback (P2, MEDIUM) — Type F
**Location:** PDP `Wishlist`/`Compare` → `/wishlist` `/compare` empty as guest (`page-analysis.md:129-130`, `user-journeys.md:204-256`). **Current:** Buttons present on PDP; header shows `Wishlist` but guest page shows `You have not added any product…`. No toast “Log in to save” interjected. **Problem:** System feedback gap — guest cannot distinguish no-op from “saved locally”; no bridge to login prompt. Violates error prevention (attempting action that requires auth without guidance). **Impact:** Users assume save succeeded, return later to empty wishlist → trust break. **Direction:** Guest tap → toast “Saved for now — log in to keep across devices” with inline Log In affordance.

### [AUTH-03] Authenticated state leaves residue / session ambiguity (P2, MEDIUM) — Type C
**Location:** PDP evaluate after session reuse returned transient `Astha IT Test A verification mail was sent to ait.test@yopmail.com. Please confirm your account verification.` in body (`personalization-current-state.md:14`). **Current:** Stale auth banner leaked across pages. **Problem:** Session isolation not clean in reuse; leftover banner confuses identity. **Impact:** Low immediate conversion risk but undermines trust when banner overlays product decision. **Direction:** Clear verification banner post-verification; isolate browser sessions per audit phase.

## Account Experience (Deferred — Authentication Required)

### [ACCOUNT-01] Account pages not in sitemap and undiscoverable pre-login (P1, HIGH) — Type B/C
**Location:** Expected `/account`, `/profile`, `/orders`, `/addresses` absent from sitemap (`sitemap-analysis.md:Not present` + `site-inventory.md:62-64`). **Current:** No account nav exists as guest beyond `Log In`; post-login dashboard shape unobservable (`user-journeys.md:181-200` NOT TESTED). **Problem:** Even after login users cannot predict where orders/addresses/profile live — IA discoverability gap. **Impact:** Repeat shoppers (Journey F) cannot locate orders/returns; address re-entry friction. **Direction:** Expose consistent account hub IA (`Orders | Addresses | Profile | Wishlist | EMI Plans`) in sitemap/robots-safe navigation; ensure breadcrumbs include Account.

### [ACCOUNT-02] Order tracking and service tracking referenced in header/footer but flows not tested (P2, MEDIUM)
**Location:** Header `Track Order Status`, `Track Your Service`; footer `Track Orders` (`page-analysis.md:7-14`, `ecommerce-capabilities.md:61-62`). **Current:** Links `→ /track-order`, `/track-service` observed but flows not loaded. **Problem:** Post-purchase confidence cannot be assessed without exercising tracking/ returns initiation. **Impact:** Post-delivery satisfaction and repeat intent not evaluated. **Direction:** After auth, exercise Track Order → order history → re-order / register complaint path.

### [ACCOUNT-03] Saved address reuse in checkout is unverifiable until auth (P2, MEDIUM)
**Location:** Anticipated address form in checkout (not loaded). **Current:** PDP delivery gate suggests per-product Home Delivery; checkout address reuse unknown. **Problem:** Frequent appliance buyers (multiple rooms) benefit from address book; unverifiable gap. **Impact:** Repeat checkout friction hidden until populated test. **Direction:** Verify address book in authenticated checkout; flag for analytics if reuse low.

---
*Evidence: `page-analysis.md:190-196`, `user-journeys.md:152-200`, `site-inventory.md:52,62-64`, `personalization-current-state.md:14`.*
