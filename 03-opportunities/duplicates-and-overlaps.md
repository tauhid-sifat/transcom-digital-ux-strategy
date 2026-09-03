# Duplicates & Overlaps — Phase 3

> Source: Cross-Review of 38 raw opportunities (PER-01–09, FEA-01–09, EDS-01–09, ECS-01–11). Evidence base `01-current-state/*`, `02-ux-audit/issue-register.md`. This doc records every merge/remove decision.

## Summary

| Metric | Count |
|---|---|
| Raw opportunities | 38 |
| Pure duplicate clusters | 6 clusters covering 26 rows |
| Layers-of-one-capability clusters | 3 clusters |
| Merged into consolidated capabilities | 28 rows → 8 consolidated |
| Removed as UX-fix (not opportunity) | 2 rows (ECS-06, ECS-07) |
| Removed as generic/unsupported tail | 1 row tail (PER-09 seasonal) |
| Category moves | 4 |
| Distinct keepers (proposed once) | 7 rows |
| Final consolidated capabilities | 15 |
| Missing high-value gaps none covered | 8 (M-01–M-08, flagged not merged) |

## Detailed Decisions

### Cluster C1 — Delivery & Serviceability Estimator

| Original | Source Agents | Decision | Rationale |
|---|---|---|---|
| PER-07 Location-Aware Delivery Confidence | Personalization | **MERGE** → C1 anchor FEA-01 | Personalization layer is only "remember pincode" — 20% of effort; core is fulfillment engine (pincode→ fee/SLA/store alt). All three cite `page-analysis.md:125` gate + `issue-register.md:27` PDP-02 |
| FEA-01 Pincode-First Delivery Estimator | Features | **KEEP as anchor** | Most complete: zone matrix + install fee + Cart propagation |
| ECS-05 Pre-Cart Serviceability Estimator | Standards | **MERGE** → C1 | Standards framing of same engine |

**Merge rationale:** Single pincode input → single serviceability matrix → single PDP→Cart propagation. Only pincode-first estimator solves PDP-02 gate failure; location-awareness alone does not.

---

### Cluster C2 — Browse Resumption

| Original | Source Agents | Decision | Rationale |
|---|---|---|---|
| PER-01 Recently Viewed | Personalization | **MERGE** → C2 | Item-level history layer |
| PER-02 Continue Shopping | Personalization | **MERGE** → C2 | Context deep-link layer (last filtered PLP/search) — same store |
| ECS-09 Recently Viewed & Continue Shopping | Standards | **MERGE** → C2 | ECS bundles correctly; PER splits layers |

**Rationale:** Both depend on same `localStorage` viewHistory + lastPlpUrl and same placements (homepage, PLP, empty cart). Two opportunities would double-count one retention store.

---

### Cluster C3 — Smart Compare

| Original | Source Agents | Decision | Rationale |
|---|---|---|---|
| PER-03 Resume Comparison | Personalization | **MERGE** | Persistence/memory layer |
| FEA-08 Smart Compare Workspace | Features | **KEEP as anchor** | Most complete mechanics: sticky bar, auto-populate, total-cost pin, share URL |
| EDS-08 Decisive-Attribute Lens | Electronics | **MERGE** | Category lens + verdict strip layer |

**Rationale:** Journey D `user-journey-friction.md:75` requires all three layers; building any one without others leaves comparison broken. One decision board, three acceptance criteria.

---

### Cluster C4 — Guided Selling Framework

| Original | Source Agents | Decision | Rationale |
|---|---|---|---|
| FEA-02 Room & Capacity Advisor | Features | **KEEP as umbrella** | Generic wizard pattern → filtered PLP → PDP verdict |
| ECS-11 Needs-Based Guided Selling | Standards | **MERGE** → C4 | Verbatim duplicate label of FEA-02 |
| EDS-01 AC Finder | Electronics | **MERGE** as lens | Category instantiation (sq ft → tonnage) |
| EDS-02 Fridge Validator | Electronics | **MERGE** as lens | Litres→family + doorway guard |
| EDS-03 TV Advisor (calc half) | Electronics | **MERGE** as lens | Distance→size calculator; glossary half → EDS-05 |
| EDS-04 Washer Advisor | Electronics | **MERGE** as lens | kg→household |
| EDS-09 Kitchen/Purifier Finder | Electronics | **MERGE** as lens | Wattage→task, TDS→filter (lowest evidence, deprioritise) |

**Rationale:** One finder framework with 5 content packs + validated rule tables. Counting each lens as separate opportunity overstates breadth 7×.

---

### Cluster C5 — Complete-the-Setup (Bundles/Attach)

| Original | Source Agents | Decision | Rationale |
|---|---|---|---|
| PER-08 Cart Complementary | Personalization | **MERGE** + **MOVE to Features** | Cart trigger is 20% — core is affinity rules |
| FEA-09 Bundles & Consumables | Features | **KEEP as anchor** | Adds bundle pricing + cadence |
| ECS-08 FBT/Bundles | Standards | **MERGE** | Standards framing of same affinity table |

**Rationale:** Placements (PDP bundle row vs cart rail vs PLP checkbox) are surfaces, not capabilities. One rule engine (TV→mount, AC→stabilizer) drives all; suppress for low-ticket (trimmer/mixer) where attach is generic.

---

### Cluster C6 — Price/Stock Notifications

| Original | Source Agents | Decision | Rationale |
|---|---|---|---|
| PER-09 head (wishlist price/stock nudge) | Personalization | **MERGE** | Head is same as wishlist intelligence |
| FEA-07 Price Drop/Stock Alert | Features | **KEEP as anchor** | Most detailed with price delta + restock ETA |
| ECS-10 Transparent Notifications | Standards | **MERGE** | Adds timeline promise layer |

**Rationale:** All three share authenticated wishlist + price history + stock ETA feed. PER-09 seasonal tail (campaign broadcast) is **REMOVE** — generic segmentation, no price/stock signal, fails True Personalization test.

---

### Cluster C7 — Search

| Original | Source Agents | Decision | Rationale |
|---|---|---|---|
| ECS-03 Autocomplete/Recent | Standards | **KEEP as Stage 1** | Foundational hygiene (debounced suggestions + recent) |
| PER-06 Personalized Ranking | Personalization | **MERGE as Stage 2** | Personalization layer atop Stage 1 (affinity-biased ranking) |

**Rationale:** Foundation vs personalization are maturity stages, not duplicates. Keep as one capability with staged delivery. Adjacent ECS-04 zero-result recovery is **distinct — keep separate**.

---

### Cluster C8 — Rich Media

| Original | Source Agents | Decision | Rationale |
|---|---|---|---|
| FEA-03 Rich Media Suite | Features | **KEEP as anchor** | Includes dimension overlay facet |
| ECS-02 Rich Media | Standards | **MERGE** | Same gallery viewer + video pipeline |

**Rationale:** One viewer component + asset pipeline; dimension overlay is phasing not separate capability.

---

### Cluster C9 — True Cost & EMI

| Original | Source Agents | Decision | Rationale |
|---|---|---|---|
| FEA-05 EMI Planner | Features | **MERGE** | Financing half (bank/tenure/monthly) |
| EDS-06 True Cost Calculator | Electronics | **MERGE** | Energy/consumable + EMI half (kWh/month, Year-1 ownership) |

**Rationale:** PDP needs single `Ownership: Price + Energy + Install + EMI/month` row. Each proposal rebuilds half the row — merge.

---

### Distinct Keepers (no merge)

| ID | Title | Why distinct |
|---|---|---|
| PER-04 Behavior-Aware Recommendations | Catalog generic `Related/Best Deals` vs browsing-aware re-ranking — verified as NOT OBSERVED behavioral, no other agent proposes | True personalization, behavioral signal, no duplicate |
| EDS-05 Spec Jargon Decoder | Only inline glossary + running-cost translator (tap EER/HQLED) — complements but not overlaps finders |
| ECS-01 Ratings & Social Proof | Only ratings/reviews proposal — NOT OBSERVED per `ecommerce-capabilities.md:31-32` + PDP-07 P1 |
| ECS-04 Zero-Result Recovery | Only typo/Did-you-mean recovery — adjacent to Search but distinct (suggestions vs recovery) |
| FEA-04 Variant & Family Navigator | Only family graph / sibling PDP chips — net-new catalog modeling |
| PER-05 Category-Affinity Homepage Reorder | Only homepage/PLP affinity reorder — weakest evidence but distinct; kept as P2 experiment |

---

### Removed (not opportunities)

| ID | Title | Reason | Correct home |
|---|---|---|---|
| ECS-07 Active Filter/Sort Feedback | Filter chips + enumerated sort | UX-fix: Filter controls VERIFIED (`ecommerce-capabilities.md:16-22`); gap is missing feedback, not capability. Maps to FILTER-01 P1/SORT-01 P1 | Remediation backlog P1 |
| ECS-06 Populated Cart Completeness | Quantity/coupon/breakdown/save-for-later | UX-fix: Empty shell VERIFIED; quantity/coupon are baseline hygiene, not opportunity. Maps to CART-02 P2. Cross-sell part belongs to C5 | Split — hygiene fix + bundle |
| PER-09 tail Seasonal broadcast | "Prepare for summer: Inverter ACs in your viewed range" | Generic campaign segmentation, no price/stock behavioral signal, fails True Personalization test `personalization.md:30-33` | Remove — campaign optimisation |

---

### Category Moves

| ID | From | To | Reason |
|---|---|---|---|
| PER-07 | Personalization | **Delivery/Features** | Core is logistics matrix; personalization only persistence 20% |
| PER-08 | Personalization | **Features/Merchandising** | Core is complement affinity rules; cart trigger is minor |
| ECS-09 | Standards | **Personalization** | Recently Viewed is inherently user-specific history |
| FEA-03/ECS-02 | Both | **PDP Content** | Rich media is content pipeline, single owner regardless of label |

---

### Missing Gaps (not merged — flagged for future)

M-01 Checkout discoverability & trust (CHECKOUT-01 P1) | M-02 IA-03 SEO wall + IA-01 flat URLs + NAV-01 `/undefined` | M-03 Trust-bar PDP propagation (TRUST-01) + warranty nomenclature | M-04 Mobile performance (MOBILE-01) | M-05 Auth OTP split-field + guest→auth continuity | M-06 Track Order/Service post-purchase | M-07 Brand vs Search canonical (NAV-02) + tile mismatch | M-08 Exchange trade-in estimator + EMI Bank List distinctiveness

*These are not opportunities from agents but cross-review flagged omissions — triage separately, do not re-propose.*

---
*All decisions traceable to `cross-review.md:32-73` Fate table and `cross-review.md:126-138` Clusters C1–C9 with file:line evidence.*
