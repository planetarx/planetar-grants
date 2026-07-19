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
demo + benchmark, not greenfield.

> 🟠 **AMENDED 2026-07-13 (R8, Steven — supersedes the 2026-06-23 $131K solo lock).** Team grows to two
> employees (founder + **Colin Broughton**, IC-design engineer; named inventor US 7,320,065 multithread
> embedded processor, US 6,684,062 / 6,346,047 RF control) and adds a **$50,000 hardware
> enforcement-datapath work package** — RISC-V core + custom instructions (envelope parse, label match,
> disposition), architecture + simulation in M1, **FPGA prototype** on live bus traffic in M2.
> **New total: $181,000** (≈72 % of cap) = founder 900 hrs + IC engineer 330 hrs, both × **$140/hr
> fully-loaded** (no separate overhead line, sidesteps §3.7; no subcontractors — both employees) + $5,000
> other costs + **$3,800 FPGA dev board & tools**.

## DIP milestone mapping

The DIP form takes **two** milestones (Labour / Materials / Travel / Other each). FCE work plan:
- **Milestone 1 (concept → design):** policy model + ODRL→classification/release mapping; `zmesg`
  classification + domain-of-origin fields; synchronous policy-eval hook design; demo-modality (AIS + SAR)
  + Protected-B synthetic-marking data setup; **hardware datapath architecture spec + cycle simulation** (CB).
- **Milestone 2 (build → demo):** enforcement engine at the chokepoint; WAL enforcement-action record type;
  exportable ingestion→output lineage; **evaluator-operable** live planetar.ca FCE demonstration (Q5);
  FCE-on overhead benchmark; **FPGA prototype of the RISC-V enforcement datapath on live bus traffic** (CB).

## Table A — Total budget by cost category (AMENDED 2026-07-13, R8)

| Category | Amount (CAD) | % | Justification |
|---|---|---|---|
| Direct labour — founder (900 hrs × $140 fully-loaded) | $126,000 | 69.6 % | Full-time PhD CS/ML founder, 6 mo FTE (~150 hrs/mo); fully-loaded rate, well below ~$200/hr market |
| Direct labour — IC-design engineer (330 hrs × $140 fully-loaded) | $46,200 | 25.5 % | Colin Broughton (employee, ~half-time over ~3 mo): hardware enforcement-datapath WP — architecture, simulation, RTL, FPGA prototype |
| Cloud compute | $3,500 | 1.9 % | Sentinel-1 fetches (free data), policy-eval + ring-hop/overhead benchmark runs, live planetar.ca hosting, storage. **No model training** |
| Software / tools | $1,000 | 0.6 % | IDE, CI, observability (RTL flow on open-source tools) |
| Datasets / licences | $500 | 0.3 % | AIS + SAR public/free; small reserve |
| Materials — FPGA dev board & tools | $3,800 | 2.1 % | RISC-V-capable FPGA development board + prototyping sundries for the datapath demo |
| Travel / Subcontractors | $0 | 0 % | No subcontractors (both team members employees); no travel |
| **Total** | **$181,000** | 100 % | **≈72 % of the $250K cap** |

## Table B — Milestone split (DIP 2-milestone; SC-1 check) (AMENDED 2026-07-13, R8)

| DIP milestone | Labour (hrs × $140) | Other costs | Total | % of total |
|---|---|---|---|---|
| **Milestone 1** (design) | founder 400 + IC 100 = 500 hrs = $70,000 | $2,000 (compute $1,500 + sw $500) | **$72,000** | **39.8 %** |
| **Milestone 2** (build + demo) | founder 500 + IC 230 = 730 hrs = $102,200 | $6,800 (compute $2,000 + sw $500 + data $500 + FPGA board $3,800) | **$109,000** | 60.2 % |
| **Total** | **1,230 hrs = $172,200** | **$8,800** | **$181,000** | 100 % |

**SC-1:** Milestone 1 = **39.8 % ≤ 70 %** → passes with a 30.2 pp margin. Cross-check: labour $172,200 +
other $8,800 = **$181,000** ✅.

## Decisions
1. ~~LOCKED 2026-06-23: $131,000 solo (900 hrs × $140 + $5K other + $0 hardware).~~ **Superseded by R8.**
2. **R8 (2026-07-13, Steven):** add Colin Broughton (employee) + $50,000 hardware WP (330 hrs × $140 =
   $46,200 + $3,800 FPGA board/tools) → **$181,000 total**. Fit-filter risk (screen #2: hardware in a
   scored software bid) raised by the assistant and **accepted by the founder**; mitigation = the hardware
   WP is framed as the FCE enforcement datapath (DO3/DO1), subordinate to the software thesis.
3. **Compute:** $5,000 — no model training; hosting, storage, benchmarks, Sentinel fetches.
4. **Rate parity:** both team members at $140/hr fully-loaded (carried from CH13; audit-simple).

## TODO
- [x] Figures locked **2026-06-23** ($131,000 total; SC-1 = 44.3 %).
- [ ] At submission, transcribe into the real DIP 2-milestone tables (like CH13 `submission/20-work-plan-milestones.md`); optionally a ~$5K bottom-up compute-estimate note (mirror `../../planetar/docs/compute-estimate.md`) if a reviewer wants the model.

## Char-count / format
Financial tables go in the DIP wizard (later steps, per CH13 `submission/19,22`). No prose cap; follow the portal field structure.
