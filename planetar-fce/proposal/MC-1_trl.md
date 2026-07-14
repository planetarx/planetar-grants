# MC-1 — Current TRL and prior R&D

> **Field cap:** 3,000 characters. **Pass/fail.** Must accurately state current TRL + R&D to reach it.
> **Locked claim (R5):** the solution — the **Fusion Compliance Engine (FCE)** — is **TRL 2 at start → TRL 3** at end-state.
> CH13 analogue: `../../planetar/proposal/MC-1_trl.md`. LOC kept qualitative (broker is ~3.1k lines, ≈half doc comments → ~1.5k LOC of code; `zmesg` has no standalone repo here). Benchmark: planetar-broker's own ring-hop, measured 2026-07-13 (Q7 closed) — `../benchmark-2026-07-13-ring-hop.md`.

## Draft (workspace markdown — strip headings before submission)

**Current TRL: 2.** The solution is a modular Fusion Compliance Engine that evaluates machine-readable classification and release-authority policy at the message chokepoint between sensor ingestion and fusion, deciding per data element whether to permit, restrict, downgrade, or segregate, and emitting immutable, exportable audit and lineage. The concept is formulated with strong component-level evidence — a built, provenance-tracked fusion substrate and a built machine-readable policy layer — but the enforcement engine that binds policy to dispositions is not yet built or demonstrated. The 1a builds and demonstrates it across two sensor modalities at Protected B, advancing the solution to **TRL 3** (proof-of-concept demonstrated, including a live system at planetar.ca).

Prior R&D establishing the critical functions (all built, open-source, broker-integrated):

(1) **The fusion chokepoint (built).** `planetar-broker` — a dependency-light single-file C message bus (TCP/UDP/shared-memory, lock-free reserve path) — is the single point every fused observation crosses. Its append-only write-ahead log is CRC32-protected and bit-exact replayable: the audit-and-lineage spine the FCE writes to. A 1M-message benchmark of planetar-broker's own shared-memory ring (four runs, 2026-07-13) recorded p50 95–100 ns / p99 1.0–1.6 µs on an untuned workstation; measuring FCE-on enforcement overhead against this baseline is part of the 1a. This headroom shows an enforcement check can be inserted without material tactical latency.

(2) **Native provenance (built).** `zmesg`, a zero-copy typed envelope, already carries source id, nanosecond timestamps, and correlation/causation ids on every message — most of the provenance record an Essential Outcome requires (classification marking and domain-of-origin are additive fields delivered in the 1a).

(3) **Machine-readable policy (built).** `planetar-market` ships a working W3C ODRL policy layer (a standards-aligned rights language with tests) that *expresses* machine-readable terms; by its own design it does not yet *enforce* them. Adopting ODRL as the FCE's classification/release-authority policy language, and building the enforcement engine that acts on it, is the central advance of the 1a.

(4) **Per-edge lineage + analyst surface (built).** `planetar-ontology` (zero-dependency TypeScript, test-covered) tracks provenance per graph edge from ingestion through fused output; `planetar-ui` renders each result's causal evidence chain — the explainable-decision surface for operator trust.

These — measured and test-covered — demonstrate the critical functions in adjacent settings (TRL 3 components). The 1a delivers the application-specific advance: the policy-evaluation-and-enforcement engine, with classification/domain provenance fields, an enforcement-action audit record, and exportable lineage — TRL 2 → 3.

## TODO
- [x] LOC re-audited **2026-06-22**: broker `planetar-broker.c` = 3,125 lines (≈1,355 doc comments → ~1.5k LOC of code), single file; `planetar-ontology` ~1,676 LOC TS (non-test). **`zmesg` has no standalone repo here** — it's an envelope *format* embedded as per-language codecs (ui/ais/ontology/eo/sat/acoustic + `tests/zmesg-test.h`); broker.c cites a canonical `~/github/sness23/zmesg/zmesg.h` that is **absent on this machine**. → keep LOC qualitative; cite `zmesg` only functionally (verified: envelope carries `source`, ns timestamps, `correlationId`, `causationId` — `planetar-ui/src/types/zmesg.ts`).
- [x] Benchmark attribution fixed in MC-1 **2026-06-22**: numbers are predecessor `zbroker0`'s (benchmark-doc title + build path), not a measured planetar-broker run. MC-1 attributes to zbroker0 and folds the planetar-broker re-benchmark (incl. FCE-on overhead) into the 1a. **MC-2 + PRC-1/2/4/6 keep their forward wording** ("the chokepoint is benchmarked") per decision **Q7 / option C (2026-06-22): run the planetar-broker re-benchmark before 2026-07-14** to make the claim literally true — `../08-OPEN-QUESTIONS.md` Q7 (**BLOCKING**). On completion, reconcile MC-1 to cite planetar-broker directly.
- [x] **Q7 CLOSED 2026-07-13:** `planetar-broker tests/ring-hop 1000000` run on the i9-9900K (four clean sequential runs): **p50 95–100 ns / p99 1.0–1.6 µs**. p50 confirms the old bracket; p99 above it → headline updated per §Q7 branch (b) across MC-1 + PRC-1/2/4/6 + submission/09; all now cite planetar-broker directly (predecessor framing dropped). Record: `../benchmark-2026-07-13-ring-hop.md`.
- [ ] Courtesy (out of scope): planetar-broker's own `CLAUDE.md` says "~2.1k lines" — also stale (now 3,125).

## Char-count budget
Target ≤ 2,950 (50 buffer). Measured 2026-06-22: ~2,870 after the benchmark-attribution fix — "runs long" note was stale.
