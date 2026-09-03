# Transcom Digital — UX/UI Improvement Scope & Strategic Roadmap

**Electronics & Home Appliance E-Commerce — Bangladesh** | Six-phase programme rendered into one actionable strategy.

This repository contains the complete evidence base and strategic deliverable for Transcom Digital (`transcomdigital.com`), transformed from research → prioritized roadmap without wireframes or hour estimates.

## Programme Overview

| Phase | Focus | Key Output |
|---|---|---|
| **01** | Current State Discovery | Sitemap 167 URLs → 22 templates, 8 PDP samples, 9 journey tests |
| **02** | UX/UI Gap Analysis | 32 issues (P0 1 / P1 13 / P2 14 / P3 4) |
| **03** | Opportunity Discovery | 38 raw → 15 consolidated (6 duplicate clusters) + 8 benchmarking NEW |
| **04** | Competitor & Market Benchmarking | 33 patterns (21 platforms) → 12 problem groups, 8 VALIDATED / 5 ENHANCED / 2 QUESTIONED |
| **05** | Consolidation & Prioritization | 34 → 25 initiatives (10 P0 / 11 P1 / 4 P2 / Parked) via value/feasibility/critique |
| **06** | Final Synthesis | Unified scope + roadmap (15 sections) |

## Quick Start

- **Executive in 7 minutes:** [`06-final-deliverable/executive-summary.md`](06-final-deliverable/executive-summary.md)
- **Main deliverable (15 sections):** [`06-final-deliverable/final-ux-ui-improvement-scope.md`](06-final-deliverable/final-ux-ui-improvement-scope.md)
- **Visual horizons:** [`06-final-deliverable/strategic-roadmap.md`](06-final-deliverable/strategic-roadmap.md)
- **Priorities at-a-glance:** [`05-prioritization/executive-priority-view.md`](05-prioritization/executive-priority-view.md)
- **What NOT to do yet:** [`05-prioritization/not-now.md`](05-prioritization/not-now.md)

## Repository Structure

```
00-input/                 # Sitemap inventory (167 URLs, duplication/hygiene signals)
01-current-state/         # 8 docs — site-inventory, page-analysis, product-discovery, etc.
02-ux-audit/              # 12 files — 32 issues, themes, journey friction, accessibility
03-opportunities/         # 4 agents + cross-review → 15 consolidated + 8 NEW
04-benchmark/             # 3 agents + pattern library → applicability + competitive map
05-prioritization/        # 34→25 merges, value/feasibility/critique → P0/P1/P2 horizons
06-final-deliverable/     # Final scope + executive summary + roadmap + traceability
sitemap.xml               # Source sitemap (octopus.do export)
```

## Top Strategic Themes

1. **Make Discovery Actually Work** — Fix `/undefined` browse, PLP chips/sort hygiene, intelligent search
2. **Help Me Choose** — Requirement-led finders (room→tonnage, family→litres, distance→size)
3. **See It, Compare It, Trust It** — Zoom + variant chips + persistent compare with total-cost pin
4. **Tell Me What It Will Really Cost** — District→Zone table → True Cost ownership row + plural `COD+bKash` row
5. **Prove Trust at Price** — `✓ Authorized` + ratings + OBD photograph + 14-day return
6. **Remember Me Without Login** — Recently Viewed + Continue Shopping + Recent Searches (localStorage)
7. **Make Delivery, Install & Return Certain** — Checker → priced basket SKU → bookable slot (ops-gated)
8. **One-Trip Ownership** — Curated attach pilot AC/TV only

## Implementation Horizons (logic, not dates)

- **NOW (10 P0)** — `/undefined` hotfix + PLP hygiene + warranty truth + District→Zone table → True Cost static row + authenticity + plural payment + Recently Viewed rail + Search Stage1 + Cart drawer/stepper/toast
- **NEXT (11 P1)** — Canonical IA, SEO re-layer, Smart Compare, AC Finder lens, full decoder, zoom, variant chips, Gate1 checker, WhatsApp deep-link, auth split-field fix, Zero-Result recovery
- **LATER (P2/LATER)** — Bundles pilot, OBD OTP protocol, 14-day→AI, full ratings pipeline after `n≥5` pilot, additional finder lenses, video/360/AR
- **EXPERIMENT** — Affinity homepage reorder A/B `Rail only vs Rail+hero reweight` after rail proof

See [`05-prioritization/dependency-map.md`](05-prioritization/dependency-map.md) for 7 foundational tables wiring 13 initiatives when built once.

## Evidence & Traceability

Every recommendation maps: Current State `01-current-state/*:line` → UX Issue `02-ux-audit/issue-register.md:7-46` → Opportunity `03-opportunities/opportunity-pool.md` 38→15 → Benchmark Pattern `04-benchmark/pattern-library.md` STANDARD/EMERGING/DIFFERENTIATOR → Priority `05-prioritization/decision-log.md` → Final Scope §6. Full trace in [`06-final-deliverable/recommendation-traceability.md`](06-final-deliverable/recommendation-traceability.md).

## Local Workflow

This repo is git-initialized on `master`. Push to GitHub after `gh auth login`:

```powershell
gh auth login
gh repo create <YOUR-USERNAME>/transcom-digital-ux-strategy --public --source="F:\My Code\Transcom" --push
# or if repo already created remotely:
git remote add origin https://github.com/<YOUR-USERNAME>/transcom-digital-ux-strategy.git
git push -u origin master
```

## License & Use

Internal strategic deliverable — share with Product, UX/UI, Engineering, Business stakeholders per §15 Next Steps in the main deliverable.

---
*Generated 2026-09-03. STOP AFTER PHASE 6 — Phase 7 would be detailed UX design & tickets.*
