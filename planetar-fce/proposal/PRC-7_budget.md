# PRC-7 — Budget

> CH13 analogue: `../../planetar/proposal/PRC-7_budget.md` + `../../planetar/submission/19-prc7-financial-tables.md`,
> `22-milestone-financials.md`. **Reuse the CH13 structure**; re-scope hours to the FCE build.

> 🟢 **LOCKED 2026-06-23** (Steven's decisions). Component 1a ceiling: **≤$250,000 CAD, ≤6 months**;
> SC-1 screen: **total ≤ $250K AND Milestone 1 ≤ 70 % of total**. Structure mirrors CH13
> (`../../planetar/proposal/PRC-7_budget.md`, submission files 19/22).

## Scope basis (FCE vs CH13)

CH13 filed at **$157,924** (925 hrs × $140/hr fully-loaded + $7,924 laptop; DIP M1 = 50.7 %). The FCE 1a is
leaner: (a) **no model training** → compute drops to ~$5K (CH13's $18K was mostly GPU detector fine-tunes);
(b) **the substrate is already built** → effort concentrates on the enforcement engine + additive fields +
demo + benchmark, not greenfield. **Locked: $131,000 total** (≈52 % of cap) — 900 hrs × **$140/hr
fully-loaded** (no separate overhead line, sidesteps §3.7) + **$5K other costs** + **$0 hardware** (CH13
funded the dev laptop ~2026-05; a second is not justified).

## DIP milestone mapping

The DIP form takes **two** milestones (Labour / Materials / Travel / Other each). FCE work plan:
- **Milestone 1 (concept → design):** policy model + ODRL→classification/release mapping; `zmesg`
  classification + domain-of-origin fields; synchronous policy-eval hook design; demo-modality (AIS + SAR)
  + Protected-B synthetic-marking data setup.
- **Milestone 2 (build → demo):** enforcement engine at the chokepoint; WAL enforcement-action record type;
  exportable ingestion→output lineage; **evaluator-operable** live planetar.ca FCE demonstration (Q5);
  FCE-on overhead benchmark.

## Table A — Total budget by cost category (LOCKED 2026-06-23)

| Category | Amount (CAD) | % | Justification |
|---|---|---|---|
| Direct labour (900 hrs × $140 fully-loaded) | $126,000 | 96.2 % | Full-time PhD CS/ML founder, 6 mo solo FTE (~150 hrs/mo); fully-loaded rate, well below ~$200/hr market |
| Cloud compute | $3,500 | 2.7 % | Sentinel-1 fetches (free data), policy-eval + ring-hop/overhead benchmark runs, live planetar.ca hosting, storage. **No model training** (vs CH13's GPU-heavy $18K) |
| Software / tools | $1,000 | 0.8 % | IDE, CI, observability |
| Datasets / licences | $500 | 0.4 % | AIS + SAR public/free; small reserve |
| Materials / Travel / Subcontractors | $0 | 0 % | Clean solo bid; no new hardware |
| **Total** | **$131,000** | 100 % | **≈52 % of the $250K cap** |

## Table B — Milestone split (DIP 2-milestone; SC-1 check) (LOCKED)

| DIP milestone | Labour (hrs × $140) | Other costs | Total | % of total |
|---|---|---|---|---|
| **Milestone 1** (design) | 400 hrs = $56,000 | $2,000 (compute $1,500 + sw $500) | **$58,000** | **44.3 %** |
| **Milestone 2** (build + demo) | 500 hrs = $70,000 | $3,000 (compute $2,000 + sw $500 + data $500) | **$73,000** | 55.7 % |
| **Total** | **900 hrs = $126,000** | **$5,000** | **$131,000** | 100 % |

**SC-1:** Milestone 1 = **44.3 % ≤ 70 %** → passes with a 25.7 pp margin. Cross-check: labour $126,000 +
other $5,000 = **$131,000** ✅.

## Decisions — LOCKED 2026-06-23 (Steven)
1. **Total / hours:** 900 hrs × **$140/hr fully-loaded** = $126,000 labour ($140 carried from CH13).
2. **Compute:** **$5,000** — no model training (the FCE has no GPU run); just hosting, storage, benchmark, Sentinel fetches.
3. **Hardware:** **$0** — no second laptop (CH13 funded one ~2026-05).

## TODO
- [x] Figures locked **2026-06-23** ($131,000 total; SC-1 = 44.3 %).
- [ ] At submission, transcribe into the real DIP 2-milestone tables (like CH13 `submission/20-work-plan-milestones.md`); optionally a ~$5K bottom-up compute-estimate note (mirror `../../planetar/docs/compute-estimate.md`) if a reviewer wants the model.

## Char-count / format
Financial tables go in the DIP wizard (later steps, per CH13 `submission/19,22`). No prose cap; follow the portal field structure.
