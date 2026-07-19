# planetar-fce — IDEaS CFP6 CH14 proposal workspace (Fusion Compliance Engine)

**Project:** Zax Analytics application to IDEaS **Competitive Projects** for **Challenge 14
(CH14)** of CFP6: *"Reliable AI Sensor Fusion for Real-World Missions."*

**Applicant:** Steven Randolph Ness (PhD, CS/ML), Zax Analytics, solo founder.
**Solicitation:** `W7714-248676/014`. **Deadline was 2026-07-21 14:00 EDT** (extended by notice
amendment 2026-07-13 — was 2026-07-14; verified on `cb-0-11990877`).
**Target Component:** **1a** (TRL 1–3, ≤$250K CAD, ≤6 mo). **TRL 2 → 3.**

> **Status: ✅ SUBMITTED 2026-07-18 — CP6-143774** ($181,000, TRL 2→3, Component 1a),
> 3 days before the extended deadline. **[`submission-record.md`](submission-record.md) is now
> the authoritative current-state file** — read it before assuming what was or wasn't filed
> (portal PDF archived: [`CP6-143774_ProposalSummary.pdf`](CP6-143774_ProposalSummary.pdf)).
> Text under `proposal/` + `submission/` is **filed** — no silent edits. Live obligation:
> **planetar.ca stays up and evaluator-drivable.** Evaluation ~3–6 mo (movement expected
> ~2026-10 → 2027-01). Thesis SSOT = [`THESIS.md`](THESIS.md); this workspace mirrors
> `../../planetar/` (the filed CH13 bid) with the thesis swapped from *learned fusion model*
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
| No added latency | planetar-broker ring-hop benchmark (2026-07-13): p50 95–100 ns / p99 1.0–1.6 µs (ns-scale chokepoint median) |
| SWaP / edge | dependency-light single-file **C** broker (~1.5k LOC) (the Tactical-Edge example) |
| Explainable + override | `planetar-ui` clicks a decision back through its causation chain |
| Sovereign Canadian IP | net-new FCE engine = Canadian-owned foreground IP |

## Directory map (scaffold)

```
planetar-fce/
├── README.md              ← this file (status dashboard)
├── submission-record.md   ✅ AUTHORITATIVE filed-state record (CP6-143774, 2026-07-18)
├── CP6-143774_ProposalSummary.pdf  ✅ portal-generated summary of the filed proposal (28 pp)
├── CHALLENGE.md           ✅ CH14 research note (deadline updated 2026-07-13 → closes 2026-07-21)
├── FIT.md                 ✅ go/no-go + asset map (Component 1a; see R8 for the team/budget amendment)
├── THESIS.md              ✅ SSOT — compliance-by-design + subordinate R8 hardware-WP note
├── 01-CHALLENGE.md        ✅ EO/DO → planetar mapping (benchmark refreshed 2026-07-13)
├── 02-STRATEGY.md         ⏳ skeleton (superseded in practice by THESIS + FIT + the drafted narratives)
├── 03-ARCHITECTURE.md     ✅ FCE layer on the bus (benchmark refreshed 2026-07-13)
├── 06-REFERENCES.md       ✅ cite list — standards web-verified 2026-06-22; keys wired to `submission/26`
├── 08-OPEN-QUESTIONS.md   ✅ decisions log — Q7 CLOSED (2026-07-13); **Q8 OPEN** (CH14 Q&A doc); R8 recorded
├── benchmark-2026-07-13-ring-hop.md  ✅ Q7 provenance record (p50 95–100 ns / p99 1.0–1.6 µs)
├── CH14-challenge.{pdf,txt}  ✅ authoritative challenge doc (source of record)
├── proposal/              ✅ all 9 narratives authored, red-teamed, R8-amended (MC-1/2 + PRC-1…7)
└── submission/            ✅ DIP field map (README) + per-field paste docs 01–27 + `paste/*.txt` + checklist
```

✅ = done · ⏳ = skeleton. Per-field char counts live in `submission/README.md` and each field doc's header.

## Reuse from the filed CH13 bid (`../../planetar/`)

Lift-and-adapt (don't reuse the *thesis*, do reuse the *spine*): portfolio/credentials
(`04-PORTFOLIO.md`), **GBA+** (`PRC-5`), budget structure (`PRC-7`), benchmark report,
compute estimate, glossary, patent framing (named-inventor background), and the
char-count/strip protocol (`planetar/CLAUDE.md`). Evaluation framework (MC/PRC weights,
70-pt threshold, 3,000-char caps) is **identical** — CFP6 Amendment 2, already in hand.

## Status dashboard

| Item | Status |
|---|---|
| **PROPOSAL SUBMITTED** | ✅ **CP6-143774, 2026-07-18 06:32 PM** — New Submission on `W7714-248676/014`, $181,000 (M1 $72,000/13 wk + M2 $109,000/12 wk, SC-1 M1 = 39.8%), TRL 2→3. Filed-state deltas (3-entry reference list, cosmetic markdown artifacts) recorded in [`submission-record.md`](submission-record.md). A revised submission can still replace it until **2026-07-21 14:00 EDT** (CH13 precedent) |
| CH14 challenge + guide located + read | ✅ `W7714-248676/014`, closes **2026-07-21 14:00 EDT** (extended 2026-07-13; was 07-14); CFP6 Amendment 2 governs. ⚠️ New **Q&A doc** on the notice (amendment 003, 2026-07-13) — obtain + read before filing (§Q8) |
| Go/no-go | ✅ **BID, Component 1a** (`FIT.md`; originally LEAN/solo $131K — expanded per **R8** 2026-07-13 to two-person, $181K) |
| Thesis pivot defined | ✅ `THESIS.md` |
| Essential-outcome asset map | ✅ `FIT.md` (formalize into `01-CHALLENGE.md`) |
| Workspace docs 01/02/03/08 | ⏳ skeletons |
| 9 narrative drafts | 🟢 **All 9 drafted + red-teamed (2026-06-23):** MC-1/MC-2 + PRC-1/2/3/4/5/6 authored, cite-wired, char-checked, consistency-passed. **R8 (2026-07-13): budget re-locked at $181K** (SC-1 = 39.8%) — team of two + $50K hardware enforcement-datapath WP (Colin Broughton); synopsis/overview/11/PRC-4/PRC-6/PRC-7 amended accordingly |
| Benchmark gate (was BLOCKING) | ✅ **CLOSED 2026-07-13** — `ring-hop` run on the i9-9900K (four clean 1M-msg runs): **p50 95–100 ns / p99 1.0–1.6 µs**; MC-1 + PRC-1/2/4/6 + submission/09 updated to cite planetar-broker directly ([`benchmark-2026-07-13-ring-hop.md`](benchmark-2026-07-13-ring-hop.md), §Q7) |
| Component decision (1a vs 1b) | ✅ **1a** locked (R5) |
| Multiple-bid rule (CH14 + urban sibling) | ✅ urban sibling dropped (R6); CH14-only |
| GBA+ / budget reuse from CH13 | ✅ GBA+ done (PRC-5); budget re-locked per R8 (PRC-7, $181K, M1 39.8%) |
| planetar.ca demo extended to show FCE enforcement | ⏳ post-award M2 deliverable — scope locked & filed: **evaluator-operable** AIS + SAR, synthetic markings (R7/Q5). Until then: keep planetar.ca up |
| Submission kit (DIP field map + strip-paste protocol + T-7→T-0 checklist) | ✅ executed in the portal 2026-07-18 — all fields pasted, milestone tables transcribed, certifications checked, submitted as CP6-143774 |

## Open decisions

See [`08-OPEN-QUESTIONS.md`](08-OPEN-QUESTIONS.md). **One item gates final assembly: Q8 — obtain the CH14
"Questions and Answers" doc** (posted to the CanadaBuys notice 2026-07-13 as amendment 003, currently shown
removed; request drafted to the contracting authority, fallback = file on Amendment 2 as governing).
*(Closed: Q4 amendment check — re-verified 2026-07-13, deadline extended to **2026-07-21 14:00 EDT**;
Q5 demo scope; Q6 patent framing; **Q7 benchmark — closed 2026-07-13**; R5/R6/R7; **R8 team + $50K hardware
WP, budget $181K**.)* **Execution complete — filed 2026-07-18 as CP6-143774** (see
[`submission-record.md`](submission-record.md)). Remaining: keep planetar.ca up through evaluation;
the M2 evaluator-operable demo build is post-award work.
