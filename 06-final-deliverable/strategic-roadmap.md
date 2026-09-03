# Strategic Roadmap — Horizons & Dependencies

> Horizons = sequencing logic, not calendar. Each horizon ships when prior's proof gates pass. Traceability: `05-prioritization/executive-priority-view.md` P0/P1/P2 + `05-prioritization/dependency-map.md` 7 foundational tables.

```
HORIZON: NOW ── Critical friction + Foundational trust row + Memory
═══════════════════════════════════════════════════════════════════════
P0 fixes that blocks everything else — LOW or essential HIGH complexity, VERY HIGH value
───────────────────────────────────────────────────────────────────────────────
[INV-01]  /undefined hotfix (LOW) ─────────────────────────────────────┐
[INV-C02] PLP chips/sort/facet hygiene + suppress empty Review (LOW) ──┤
[INV-C04] Warranty truth `Parts-0M→h` (content LOW) ──────────────────┤  Unblocks
[INV-22]  Browse Resumption rail+deep-link (LOW localStorage) ────────┤  all browse
[START]   District→Zone/SLA+fee+install+store table (HIGH) ◄──────────┘  / discovery
          │
          ▼
[INV-13]  Delivery Estimator pincode-first SLA+fee+free-install+pickup ──► 7 consumers
          │
          ├──► [INV-14] True Cost static row `Upfront+Install+Energy→EMI/mo` + verdict + offline 7–10d truth
          │           + [INV-26] Plural COD+bKash+Nagad row (shares zone truth, LOW)
          │           + [INV-C06] Cart drawer/stepper/toast `Subtotal+Delivery+Install→Total` (shares tables)
          │
          ├──► [INV-21] Authenticity `✓ Authorized` hero lockup (LOW, reuses 13 brands)
          │
          └──► [INV-C03 Stage1] Search autocomplete `Product/Brand/Category/SKU-exact` + Recent 6

Parallel low: [INV-C04 decoder 8–10 terms tap `EER→Tk/mo`] content-only prerequisite
═══════════════════════════════════════════════════════════════════════


HORIZON: NEXT ── High-value enhancements after foundations stable
═══════════════════════════════════════════════════════════════════════
[INV-C01] IA canonical/hyphen/tile fixes (LOW) ───────────────── D1
[INV-04]  SEO wall re-layer below pagination + `30-sec guide` CTA
                                                                  ─┐
[INV-C03 Stage2] affinity-biased search ranking after INV-22 vol  │
[INV-C03 recovery] Zero-Result `Did-you-mean + Remove Brand→12`   │
[INV-23]  Smart Compare sticky→auto-populate (/compare)           │ D5
           + `Highlight differences` (decisive tint/verdict P2)   ─┤  Decision support
[INV-24]  Guided Selling AC lens (sq ft×height→tonnage 20 BTU)    │
           Fridge/TV/Washer lenses deferred to Fridge proof      ─┤
[INV-12]  Rich Media P0 zoom/pinch+scrub → P1 functional video    │
[INV-17]  Variant Family chips `+Tk delta` + `Get Stock Alert`     │
[INV-16]  Gate1 Installation Checker + priced `Add Installation` SKU
[INV-C05] Hotline-sticky 16212 + WhatsApp `Share via WhatsApp` ────┘ D1
[INV-32]  Auth split-field fix + guest toast `Saved for now — log in` + migration INV-22 store
[INV-14]  Interactive True Cost slider/bank picker (phase2 of static)
═══════════════════════════════════════════════════════════════════════


HORIZON: LATER ── Advanced / Differentiators (ops/content gated)
═══════════════════════════════════════════════════════════════════════
[INV-06]  Homepage budget cull (subtraction) ──► Affinity experiment deferred
[INV-25]  Bundles pilot curated AC/TV only (Family→attach mapping + price delta) ──► full catalog after pilot
[INV-28]  OBD badge eligibility (P1) ──► OTP+photo protocol (P2 ops-gated)
[INV-33]  14-day badge + `up to Tk12k → inspection → OTP` cross-category ──► AI diagnostics 10-step VERY HIGH
[INV-20]  Social Proof pipeline (collection/moderation) ──► after 1-cat pilot proves n≥5 supply `ecommerce-capabilities.md:31-33` zero
[INV-24]  Additional lenses Fridge bag ladder `18L=1 bag` + 7-step guard, TV distance→size, Washer kg
[INV-12]  Dimension overlay `W×H×D+gap+swing` + 360°/AR (after W×H×D normalisation)
═══════════════════════════════════════════════════════════════════════


HORIZON: EXPERIMENT ── Validation before major invest
═══════════════════════════════════════════════════════════════════════
[INV-06 advanced] Affinity Homepage Reorder A/B `Rail only vs Rail+hero reweight`
                  gated on modular CMS + affinity scorer + campaign-pin governance + proof:
                  ship INV-22 rail + INV-C03 Recent first → measure returner conversion
                  → if lift proven, A/B; otherwise keep rail only
                  QUESTIONED per `applicability-review.md:128-135` — not less valuable, just highest
                  CMS dependency where cheaper localStorage rail gives 80%.

                  Also `Your size:55"` rank within PLP could ship earlier as low-cost tweak.
═══════════════════════════════════════════════════════════════════════
```

## Dependency Arrows (Hard gates)

| Dependency | Why Hard |
|---|---|
| INV-01 → all browse/discovery INV-04/22/23/24/INV-C02 | No discovery path completes with broken See All |
| INV-13 table → INV-14, INV-16, INV-26, INV-28, INV-C05, INV-C06, Fast filter 1C | Single district table — 7 consumers |
| INV-C04 glossary → INV-14 True Cost + INV-24 verdict + INV-16 checklist | Literacy prerequisite (finder verdict references EER etc.) |
| INV-22 store → INV-23 Compare, INV-C03 Recent, INV-32 migration | Same `viewHistory/compareQueue/searchHistory` store |
| Family Graph → INV-17, INV-23, INV-25, INV-10 re-validation | Top 30 roots 70% high-ticket — one enrichment |
| INV-13 + EMI master → INV-14 row | Delivery fee/SLA + tariff×EER + bank master must exist together for single landed-cost row |
| W×H×D normalisation → INV-10 overlay, INV-16 checker, INV-24 Fridge guard | One spec enrichment feeds media + checker + finder |
| Post-delivery pilot n≥5 → INV-20 full reviews | VERY HIGH pipeline without supply = fake counts |

## Governance Rule

**Build the district→Zone/SLA+fee+install+store table once — before touching homepage affinity.** Every standard reveals a suppression rule: EMI, install, FBT, energy row, Customer Review facet all suppress for low-ticket (<BDT 5k `regional-commerce.md:52-64` Pickaboo 5k / Daraz 10k) per `05-prioritization/cross-review.md:168`.

*Roadmap traceable to `05-prioritization/executive-priority-view.md` horizons NOW/NEXT/LATER/EXPERIMENT — not dates.*
