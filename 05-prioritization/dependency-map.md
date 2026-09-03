# Dependency Map — Initiative Relationships

> Identifies FOUNDATIONAL initiatives that enable multiples. Dependency strength: HARD (cannot ship dependent without foundation) vs SOFT (benefit amplified but can ship independently).

## Foundational Initiatives (enable ≥3 others)

| Foundational | Enables | Why Foundational |
|---|---|---|
| **INV-01 Fix /undefined** | All browse/discovery (INV-04, INV-22, INV-23, INV-24, INV-C02) | P0 blocker — no discovery path completes with broken See All |
| **INV-13 Delivery & Serviceability Table (District→Zone/SLA + fee + install + store inventory)** | INV-14 True Cost energy row, INV-16 Install checker, INV-26 Plural COD truth, INV-28 OBD eligibility, INV-C05 hotline/store visit, INV-C06 landed-cost breakdown, NEW-08 threshold filter | Single table; 7 consumers share zone/fee/SLA |
| **INV-C04 Jargon Decoder + Warranty Truth (Glossary 8–10 terms)** | INV-14 True Cost EMI row explainability, INV-24 Guided Selling verdict, INV-16 checklist literacy | Literacy prerequisite — finder verdicts and cost formulas reference EER/R32/HQLED etc. |
| **INV-22 Browse Resumption Store (localStorage viewHistory + lastPlpUrl + compareQueue)** | INV-23 Smart Compare persistence, INV-C03 Search Recent, INV-32 auth migration | Same store `viewHistory/compareQueue/searchHistory` + auth migration gate |
| **EMI Master (bank×tenure×threshold×form-latency) — part of INV-14** | INV-23 total-cost pin, INV-26 plural payment, INV-C06 breakdown, NEW-06 | Finance-owned truth table |
| **Family Graph (model_root → variants) — part of INV-17** | INV-23 total-cost/add-to-compare, INV-10 dimension re-validation on switch, INV-25 attach mapping | Top 30 roots 70% high-ticket; one enrichment |
| **W×H×D + ventilation gap normalisation — part of INV-12/INV-10** | INV-10 dimension overlay, INV-16 checker, INV-24 Fridge guard (OPP-04 lens) | One spec enrichment feeds media + checker + finder |

## Full Dependency Register

| Initiative | Depends On | Why | Strength |
|---|---|---|---|
| INV-C01 IA Hygiene (canonical/hyphen/tile) | INV-01 /undefined fix | Hireachy fixes assume browse paths resolve; canonical for brand vs search (`issue-register.md:12` NAV-02) needs working links | HARD for canonical; SOFT for flat→hierarchical migration (parked) |
| INV-C02 PLP Browse Controls (chips/sort/facet) | INV-01 | PLP chips rely on reachable PLP; filter UX assumes PLP exists | HARD |
| INV-04 SEO Wall Re-layer | INV-C02 | Re-layer (`page-analysis.md:90-91` IA-03) must know PLP filter/sort placement is fixed above fold before moving SEO below pagination | SOFT |
| INV-C03 Intelligent Search & Recovery | INV-22 (Recent) | Recent Searches chip uses same `searchHistory` store as resumption | SOFT |
| INV-13 Delivery Table | — | Foundational — geneis | — |
| INV-14 True Cost & EMI | INV-13 delivery table + INV-C04 glossary + EMI master | Delivery fee/SLA + tariff×EER formula + bank master | HARD delivery table; HARD glossary; HARD EMI master |
| INV-16 Install Checker/Gate2 | INV-13 delivery table + INV-C04 + W×H×D | Install fee + glossary + dimensions | HARD |
| INV-17 Variant Navigator | Family Graph modeling | Requires model_root enrichment | HARD |
| INV-20 Social Proof Pipeline | — (pilot) | Collection/moderation independent but PLP badge wiring overlaps INV-C02 facet | SOFT PLP facet |
| INV-21 Authenticity Badging | — (reuse 13 brands) | Reuses brand partnerships `sitemap-analysis.md:26` without pipeline | — |
| INV-22 Resumption | — | Anonymous localStorage; auth migration depends on INV-32 | SOFT auth |
| INV-23 Smart Compare | INV-22 persistence + INV-13/14 feeds + Family Graph | Persistence store + total-cost pin (delivery+EMI/energy) + add sibling | HARD persistence; SOFT feeds |
| INV-24 Guided Selling | INV-C04 glossary + rule tables per lens | Literacy + validated tonnage/litres tables | HARD glossary |
| INV-25 Bundles | Family Graph + INV-17 + INV-13 | Family→attach mapping + price/stock + delivery | HARD family; SOFT delivery |
| INV-26 Plural Payment | INV-13 zone matrix | District-aware COD truth from same table | HARD |
| INV-28 OBD/OTP | INV-13 zone/pincode eligibility | Badge eligibility by pincode | HARD |
| INV-C05 Human Support Spine | INV-13 store inventory for Schedule Visit | Store Pickup mapping from delivery table | SOFT |
| INV-C06 Cart Drawer & Landed-Cost | INV-13/14 delivery+install fee tables | `Subtotal+Delivery+Install→Total` truth row | HARD |
| INV-32 Auth UX | INV-22 store | viewHistory/compareQueue/searchHistory migration on OTP login `0157…` | SOFT |
| INV-33 Exchange & 14-Day | — (valuation feed) | Cross-category AI diagnostics feed + 14-day badge wiring | HARD valuation |
| INV-06 Curated Prioritization | INV-22 + INV-C03 Recent + CMS modularity | Affinity scorer needs viewHistory + searchHistory + modular CMS + A/B; deferred until rails proven | HARD cms |
| INV-10 Rich Media (video/AR) | W×H×D + INV-12 dimension source | Dimension overlay reuses spec; AR phase after zoom proof | SOFT |

## Dependency Graph (text)

```
P0 Foundations (ship first, unblock dependents)
  INV-01 /undefined ──► All browse/discovery
  INV-C04 glossary+ warranty ──► INV-14 True Cost, INV-24 Guided Selling, INV-16
  INV-13 District→Zone/SLA table ──► INV-14, INV-16, INV-26, INV-28, INV-C05, INV-C06, NEW-08
  INV-22 localStorage store ──► INV-23 Compare, INV-C03 Recent, INV-32 migration
  EMI master ──► INV-14, INV-23 pin, INV-26, INV-C06
  Family graph ──► INV-17, INV-23, INV-25, INV-10 re-validation
  W×H×D normalisation ──► INV-10 overlay, INV-16 checker, INV-24 Fridge guard

P1 Decision core (depend on foundations)
  INV-14 True Cost (needs INV-13 + INV-C04 + EMI master)
  INV-24 Guided Selling AC lens (needs INV-C04 rule table)
  INV-23 Compare (needs INV-22 + INV-13/14 feeds + family graph)
  INV-12 Rich Media zoom (low deps) → video/dimension (needs W×H×D)
  INV-17 Variant chips (needs family graph)
  INV-16 Gate1 checker (needs W×H×D + INV-13 + INV-C04)

P2 Differentiators (ops/content gated)
  INV-20 Reviews pipeline → INV-21 authenticity companion
  INV-33 14-day badge → AI diagnostics
  INV-25 Bundles pilot → full catalog
  INV-28 OBD badge → OTP protocol (needs ops fleet)
  INV-06 Affinity reorder → needs CMS + A/B + proven INV-22/C03 rails
```

## Critical Path

1. **Week 0–2 Foundations:** INV-01 + INV-C02 chips/sort + INV-C04 warranty fix + INV-22 resumption + start INV-13 table (district→Zone)
2. **Week 2–4 Trust Row:** INV-13 completed → INV-14 static True Cost + INV-26 plural payment + INV-21 authenticity + INV-C06 cart drawer (share table) + INV-C03 Search Stage1 + INV-11 jargon decoder
3. **Next:** INV-04 SEO re-layer, INV-23 compare, INV-24 AC finder, INV-12 zoom, INV-17 family chips
4. **Later:** Ops-gated Gate2 booking, full AI diagnostics, bundle scale, review pipeline at volume

---
*Wiring table: 7 foundational tables/components feed 13 initiatives. Building the district table once avoids 7× duplicate effort (`applicability-review.md:158-169`).*
