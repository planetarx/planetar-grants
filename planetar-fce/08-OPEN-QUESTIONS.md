# 08 — Open questions & decisions log (CH14 / FCE)

> Mirrors `planetar/08-OPEN-QUESTIONS.md`. Log decisions here as they lock; convert any
> relative dates to absolute.

## Live questions (blocking or shaping the bid)

| # | Question | Why it matters | Owner | Status |
|---|---|---|---|---|
| Q4b | Confirm planetar-market ODRL = *expression only* (built); enforcement is the 1a's net-new build | Honesty spine for PRC-2/PRC-4 — odrl.ts header states it expresses but does not enforce | Steven | **Resolved 2026-06-22** — framing locked: policy-language built, enforcement novel |
| Q4 | Confirm **no CFP6 amendment newer than 2** changes caps/criteria for CH14. | Caps/criteria assumed identical to CH13. | Steven | **Resolved 2026-06-23** — live notice `cb-0-11990877` attaches only the CH14 PDF + **Amendment 2** (EN/FR); **no Amendment 3+**. Solicitation `W7714-248676/014` + deadline 2026-07-14 14:00 EDT re-confirmed. Re-check at final assembly (notices can change). **Re-checked 2026-07-13:** notice now shows closing **2026-07-21 14:00 EDT** (extended; "last amendment date 2026/07/13") and a new attachment *"CFP 6- CH14 (W7714-248676-014-A) Questions and Answers"* (notice amendment 003, added 2026-07-13, annotated "removed" — the challenge PDF carries the same annotation since 07-10, so likely attachment re-shuffling, not withdrawal; notice status **Open**). → **Q8**. |
| Q5 | How far to extend **planetar.ca** to show live FCE enforcement (TRL-3 "live system")? | CH13 used a live demo as TRL-3 evidence; CH14 should too. | Steven | **Resolved 2026-06-23** — **evaluator-operable** live FCE demo (match CH13): AIS + SAR with synthetic Protected-B markings; evaluator clicks a fused result → disposition + governing rule + WAL audit + lineage, and can change a policy → hot-reload. Built in M2; strongest TRL-3 "live system" evidence. |
| Q6 | **Patent framing** for CH14 — carry named-inventor background; assert FCE as new Canadian-owned foreground IP? | Sovereign-IP pitch (PRC-2/3); honesty rules from CH13 Q9 apply. | Steven | **Resolved 2026-06-23** — **keep the audit-safe CH13 form**: one named-inventor mention (PRC-2: "US 10,936,582 — Salesforce-assigned, not owned"); sovereignty grounded in the AGPL spine + new Canadian-owned FCE foreground IP, **not** the patents (PRC-3). Narratives already comply — no edits needed. |
| **Q7** | **Pre-submission gate — benchmark `planetar-broker` SHM (1M msgs) before 2026-07-14.** The narratives (MC-2 + scored PRC-1/2/4/6) state the chokepoint *is* benchmarked (MC-2 vaguely, "at nanosecond scale"; the rest with the numbers) at p50 80–140 ns / p99 400–900 ns; today those are the **predecessor `zbroker0`'s** measured numbers (`../../planetar/docs/benchmark-2026-04-27.md`), not a planetar-broker run. | Makes the scored latency claim literally true. Otherwise MC-2/PRC-1/2/4/6 over-attribute and must be reworded to predecessor framing (as MC-1 already is) before filing. | Steven | **✅ CLOSED 2026-07-13.** Ran per §Q7 on the i9-9900K (Linux 6.17, untuned, pm2 tier up): four clean sequential `./tests/ring-hop 1000000` runs → **p50 95–100 ns / p99 1.0–1.6 µs**. p50 inside the old bracket; p99 above it → **branch (b)** applied: headline updated to the measured bracket in MC-1 + PRC-1/2/4/6 + `submission/09`; all cite planetar-broker directly (predecessor framing dropped). MC-2's "nanosecond scale" stays literally true (median ~100 ns). Full record: [`benchmark-2026-07-13-ring-hop.md`](benchmark-2026-07-13-ring-hop.md). |

| **Q8** | **Obtain + read the CH14 "Questions and Answers" doc** (notice amendment 003, posted 2026-07-13 on `cb-0-11990877`, currently annotated "removed"; 28 downloads recorded). Q&As can clarify or change scope/criteria interpretation. | Filing on stale interpretation risks a correctness error an evaluator can check against the published Q&A. | Steven | **✅ CLOSED 2026-07-19.** The Q&A's third upload is **live** on the notice (the 07-10 and 07-13 "removed" annotations were the two earlier uploads); downloaded + read — archived as [`CH14-QA-amendment003-2026-07-13.pdf`](CH14-QA-amendment003-2026-07-13.pdf) (30 pp bilingual, 19 Q&As; Q13–15 duplicate Q6–8). CP6-143774 was filed 07-18 *without* it → **impacts folded into the replacement pass** ([`replacement-2026-07-19.md`](replacement-2026-07-19.md)): **Q1 — the FCE itself must incorporate AI/ML** (any technique incl. knowledge-based AI, per Q19) → PRC-1 + MC-2 EO1 now state the engine is knowledge-based AI (automated reasoning over machine-readable policy). Validations, no change needed: Q3/Q7 synthetic+public data explicitly acceptable; Q16 STANAG 4774/4778 encouraged not mandated; Q2 AIS+SAR = two distinct modalities; Q6 offeror defines the representative policy model ("at least one network security domain, at least Protected B"); Q10 confirms the between-ingestion-and-pipeline architecture; Q5 portal char limits authoritative. Also confirmed 2026-07-19: **no amendment 004**, closing **2026-07-21 14:00 EDT**, notice Open. |

## §Q7 — benchmark execution detail (scoped 2026-06-23)

Scoped `~/github/planetarx/planetar-broker`. Two findings that change *how* Q7 must be run:

1. **Use the right harness — `tests/ring-hop`, NOT `make perf`.** The headline `p50 80–140 ns` is a
   **direct SHM ring hop** (writer→ring→reader, no broker in path). `tests/ring-hop.c` reproduces exactly
   that zbroker0 topology against **planetar-broker's own ring code** (byte-for-byte the broker's
   `ring_header_t`/`ring_entry_hdr_t` contract) and reports percentiles **in nanoseconds** — its header
   says it is "the number planetar-broker can claim as its own." **`make perf` measures a *different*
   path** (TCP/UDP ingest → broker → consumer, with WAL + eventfd) and is **microseconds, not nanoseconds**
   — the perf script's own header warns the two "must not be conflated." Conflating them into the proposal
   would be a serious provenance error.
2. **Cannot run on this machine (macOS).** The broker is Linux-only (`epoll`/`eventfd`/`memfd_create`/
   `SCM_RIGHTS`; build here fails on `sys/epoll.h`). Must run on the Linux box where zbroker0 was measured
   (the i9-9900K workstation) or equivalent.

**Procedure to close Q7 (on Linux):**
```
cd ~/github/planetarx/planetar-broker
make tests/ring-hop
./tests/ring-hop 1000000            # 1M msgs, CPU-pinned writer/reader; ns percentiles
# (optionally pin cores explicitly: ./tests/ring-hop 1000000 64 2 4)
```
Record min/p50/p90/p99/max. **Then:** (a) if p50/p99 fall within `80–140 / 400–900 ns`, the narratives'
forward wording becomes literally true → reconcile MC-1 (drop "predecessor / re-benchmark in the 1a") and
cite planetar-broker's own ring-hop number; (b) if they differ, update the headline range to the measured
bracket everywhere (MC-1/MC-2/PRC-1/2/4/6 + `06`/`FIT`/`README`) — conservative numbers only, no tuning.
**Separately**, the FCE's *real* latency deliverable is the **marginal FCE-on overhead** (policy check vs.
FCE-off), measured during the 1a per PRC-4 — distinct from this ring-hop baseline; don't conflate.

> **Framing note (honest even before the run):** "the bus's shared-memory ring hop is p50 80–140 ns" is the
> defensible claim (the ring *is* planetar-broker's ring). Do **not** imply the *full* broker path (kernel
> ingest + WAL) is ns — that path is microseconds. The narratives currently say "shared-memory path/
> chokepoint," which reads as the ring hop; keep it that precise.

## Resolved

| # | Decision | Date |
|---|---|---|
| R1 | Solicitation = `W7714-248676/014` (CH14), closes 2026-07-14 14:00 EDT | 2026-06-22 |
| R2 | CH14 reuses CH13's CFP6 evaluation framework (MC/PRC weights, 70-pt, 3,000-char caps) — nothing new to learn | 2026-06-22 |
| R3 | Thesis = compliance-by-design / FCE; learned fusion model demoted to background | 2026-06-22 (`THESIS.md`) |
| R4 | Go/no-go = LEAN BID, Component 1a | 2026-06-22 (`FIT.md`) |
| R5 | **Q1 locked:** Component **1a** is the honest TRL lane (TRL 2 → 3) | 2026-06-22 (user) |
| R6 | **Q3 locked:** **DROP the urban sibling** (CH15) — CH14 only | 2026-06-22 (user) |
| R7 | **Q2 locked:** demo = **AIS + SAR** within the dark-vessel / MDA setting; **synthetic** classification markings (AIS unclassified, SAR Protected B) to give the FCE a real cross-domain-merge decision | 2026-06-22 (user + recommendation) |
| R8 | **Team + budget amendment:** add **Colin Broughton** (employee, IC-design engineer; named inventor US 7,320,065 / 6,684,062 / 6,346,047; Canadian, in Canada; availability confirmed) + **$50K hardware enforcement-datapath WP** (RISC-V + custom instructions, FPGA prototype; 330 hrs × $140 + $3,800 board). Budget $131K → **$181K**; M1 = 39.8 %. Supersedes the solo lock. **Consent confirmed 2026-07-13** (Steven): Colin agrees to be named in the bid and to on-award employment; work location Victoria area (field 24 unchanged). Fit-filter screen-#2 risk raised by assistant, **accepted by founder**; mitigation: WP framed as the FCE enforcement datapath (DO3/DO1), subordinate to the software thesis — "distributed disruptor" framing kept **out** of bid text | 2026-07-13 (user, after risk briefing) |

## Carry-over audits from CH13 (re-verify before reusing language)
- Patent language (CH13 Q9): "applicant-named inventor on US 10,936,582 / 11,442,952," never ownership.
- Conservative benchmark range only (no post-tuning numbers).
- Citation bylines (CH13 Q10/Q13) if any references are reused.
