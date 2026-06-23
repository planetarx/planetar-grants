# planetar-fce — IDEaS CFP6 CH14 proposal workspace (Fusion Compliance Engine)

**Project:** Zax Analytics application to IDEaS **Competitive Projects** for **Challenge 14
(CH14)** of CFP6: *"Reliable AI Sensor Fusion for Real-World Missions."*

**Applicant:** Steven Randolph Ness (PhD, CS/ML), Zax Analytics, solo founder.
**Solicitation:** `W7714-248676/014`. **Deadline: 2026-07-14 14:00 EDT.**
**Target Component:** **1a** (TRL 1–3, ≤$250K CAD, ≤6 mo). **TRL 2 → 3.**

> **Status: SCAFFOLD — not yet a committed bid.** Go/no-go = **LEAN BID** ([`FIT.md`](FIT.md)).
> Thesis SSOT = [`THESIS.md`](THESIS.md). This workspace mirrors `../../planetar/` (the
> filed CH13 bid) and reuses its spine; the thesis is swapped from *learned fusion model*
> to *compliance-by-design / Fusion Compliance Engine*.

---

## What the FCE is

A **modular AI-enabled compliance engine** that sits at the message chokepoint between
sensor ingestion and the fusion pipeline, enforcing **machine-readable classification &
release-authority policy** in real time — tagging, permitting, restricting, downgrading, or
segregating each data element — and emitting **immutable, exportable audit + data-lineage**
records, **without adding tactical-decision latency**. Demonstrated across ≥2 modalities at
Protected B. See [`THESIS.md`](THESIS.md), [`03-ARCHITECTURE.md`](03-ARCHITECTURE.md).

## Why planetar fits CH14 (vs. starting cold)

| CH14 demand | planetar answer |
|---|---|
| Enforcement *during* multi-sensor fusion | We **own the chokepoint** (`planetar-broker`); enforcement is a hook, not a rebuild |
| Machine-readable policy | `planetar-market` ships **W3C ODRL** policy + provenance manifests |
| Provenance records (source/class/ts/domain) | `zmesg` already carries source/ts/correlation/causation; class+domain are additive fields |
| Audit logs + exportable lineage | **CRC32 append-only WAL** + per-edge `planetar-ontology` lineage |
| No added latency | `zbroker0` benchmark: p50 80–140 ns / p99 400–900 ns (ns-scale chokepoint) |
| SWaP / edge | ~1.2k-LOC dependency-light **C** broker (the Tactical-Edge example) |
| Explainable + override | `planetar-ui` clicks a decision back through its causation chain |
| Sovereign Canadian IP | net-new FCE engine = Canadian-owned foreground IP |

## Directory map (scaffold)

```
planetar-fce/
├── README.md              ← this file (status dashboard)
├── CHALLENGE.md           ✅ CH14 research note: facts, guide links, verbatim outcomes
├── FIT.md                 ✅ go/no-go + asset map (LEAN BID, Component 1a)
├── THESIS.md              ✅ SSOT — compliance-by-design pivot
├── 01-CHALLENGE.md        ⏳ CH14 EO1–EO6 / desired-outcomes → planetar mapping (rubric)
├── 02-STRATEGY.md         ⏳ sovereign compliance-by-design pitch framing
├── 03-ARCHITECTURE.md     ⏳ the FCE layer on the bus (enforcement + audit + lineage)
├── 08-OPEN-QUESTIONS.md   ⏳ decisions log + open items
├── CH14-challenge.{pdf,txt}  ✅ authoritative challenge doc (source of record)
└── proposal/              ◐ 4 of 9 drafted (MC-1, MC-2, PRC-2, PRC-4); rest skeletons
    ├── MC-1_trl.md            ✅ DRAFT — FCE TRL 2 → 3 (~2.7k chars)
    ├── MC-2_alignment.md      ✅ DRAFT — EO1–EO6 walk (~2.6k chars)
    ├── PRC-1_st_merit.md      ⏳ 10 pts
    ├── PRC-2_novelty.md       ✅ DRAFT — FCE approach, NOT fusion model (~2.96k, at cap)
    ├── PRC-3_impact.md        ⏳ 20 pts
    ├── PRC-4_feasibility.md   ✅ DRAFT — own-the-chokepoint + ns latency (~2.65k chars)
    ├── PRC-5_gba_plus.md      ⏳ 5 pts  — reuse CH13 GBA+
    ├── PRC-6_desired_outcomes.md ⏳ 15 pts — real-time, hot-reload, SWaP, override
    └── PRC-7_budget.md        ⏳ budget tables
```

✅ = done · ⏳ = scaffolded skeleton, needs authoring.

## Reuse from the filed CH13 bid (`../../planetar/`)

Lift-and-adapt (don't reuse the *thesis*, do reuse the *spine*): portfolio/credentials
(`04-PORTFOLIO.md`), **GBA+** (`PRC-5`), budget structure (`PRC-7`), benchmark report,
compute estimate, glossary, patent framing (named-inventor background), and the
char-count/strip protocol (`planetar/CLAUDE.md`). Evaluation framework (MC/PRC weights,
70-pt threshold, 3,000-char caps) is **identical** — CFP6 Amendment 2, already in hand.

## Status dashboard

| Item | Status |
|---|---|
| CH14 challenge + guide located + read | ✅ `W7714-248676/014`, closes 2026-07-14; CFP6 Amendment 2 governs |
| Go/no-go | ✅ **LEAN BID, Component 1a** (`FIT.md`) |
| Thesis pivot defined | ✅ `THESIS.md` |
| Essential-outcome asset map | ✅ `FIT.md` (formalize into `01-CHALLENGE.md`) |
| Workspace docs 01/02/03/08 | ⏳ skeletons |
| 9 narrative drafts | ◐ **4 drafted** (MC-1, MC-2, PRC-2, PRC-4); 5 skeletons (PRC-1/3/5/6/7) |
| Demo design (Q2/R7) | ✅ AIS + SAR, dark-vessel/MDA setting, synthetic Protected-B markings |
| Component decision (1a vs 1b) | ⏳ 1a recommended; confirm honest TRL of FCE engine |
| Multiple-bid rule (CH14 + urban sibling) | ⏳ verify in Amendment 2 |
| GBA+ / portfolio / budget reuse from CH13 | ⏳ pending |
| planetar.ca demo extended to show FCE enforcement | ⏳ pending |

## Open decisions

See [`08-OPEN-QUESTIONS.md`](08-OPEN-QUESTIONS.md). Biggest: (1) confirm **1a** is the honest
TRL lane for the FCE engine; (2) scope the demo (which 2 modalities, what Protected-B
synthetic markings); (3) whether to also bid the urban sibling (CH15?).
