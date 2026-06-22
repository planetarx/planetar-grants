# MC-1 — Current TRL and prior R&D

> **Field cap:** 3,000 characters. **Pass/fail.** Must accurately state current TRL + R&D to reach it.
> **Locked claim (R5):** the solution — the **Fusion Compliance Engine (FCE)** — is **TRL 2 at start → TRL 3** at end-state.
> CH13 analogue: `../../planetar/proposal/MC-1_trl.md`. ⚠️ LOC figures are TODO (re-audit; broker grew since May snapshot).

## Draft (workspace markdown — strip headings before submission)

**Current TRL: 2.** The solution is a modular Fusion Compliance Engine that evaluates machine-readable classification and release-authority policy at the message chokepoint between sensor ingestion and fusion, deciding per data element whether to permit, restrict, downgrade, or segregate, and emitting immutable, exportable audit and lineage. The concept is formulated with strong component-level evidence — a built, provenance-tracked fusion substrate and a built machine-readable policy layer — but the enforcement engine that binds policy to dispositions is not yet built or demonstrated. The 1a builds and demonstrates it across two sensor modalities at Protected B, advancing the solution to **TRL 3** (proof-of-concept demonstrated, including a live system at planetar.ca).

Prior R&D establishing the critical functions (all built, open-source, broker-integrated):

(1) **The fusion chokepoint (built).** `planetar-broker` — a dependency-light C message bus (TCP/UDP/shared-memory, lock-free reserve path) — is the single point every fused observation crosses. Its append-only write-ahead log is CRC32-protected and bit-exact replayable: the audit-and-lineage spine the FCE writes to. A 1M-message benchmark of its shared-memory path measured p50 80–140 ns / p99 400–900 ns, demonstrating that an enforcement check can be inserted without material tactical latency.

(2) **Native provenance (built).** `zmesg`, a zero-copy typed envelope, already carries source id, nanosecond timestamps, and correlation/causation ids on every message — most of the provenance record an Essential Outcome requires (classification marking and domain-of-origin are additive fields delivered in the 1a).

(3) **Machine-readable policy (built).** `planetar-market` ships a working W3C ODRL policy layer (a standards-aligned rights language with tests) that *expresses* machine-readable terms; by its own design it does not yet *enforce* them. Adopting ODRL as the FCE's classification/release-authority policy language, and building the enforcement engine that acts on it, is the central advance of the 1a.

(4) **Per-edge lineage + analyst surface (built).** `planetar-ontology` (zero-dependency TypeScript, test-covered) tracks provenance per graph edge from ingestion through fused output; `planetar-ui` renders each result's causal evidence chain — the explainable-decision surface for operator trust.

These — measured and test-covered — demonstrate the critical functions in adjacent settings (TRL 3 components). The 1a delivers the application-specific advance: the policy-evaluation-and-enforcement engine, with classification/domain provenance fields, an enforcement-action audit record, and exportable lineage — TRL 2 → 3.

## TODO
- [ ] Re-audit LOC for broker/ontology/zmesg; insert exact figures (or drop if contested).
- [ ] Confirm benchmark phrasing matches `planetar/docs/benchmark-2026-04-27.md` exactly.

## Char-count budget
Target ≤ 2,950 (50 buffer). Measure stripped paste block at red-team — currently runs long; trim item (4) first.
