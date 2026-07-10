# MC-2 — Alignment to the challenge

> **Field cap:** 3,000 characters. **Pass/fail.** Must show the solution addresses CH14.
> Traceability source: [`../01-CHALLENGE.md`](../01-CHALLENGE.md) (EO1–EO6). Keep consistent with PRC-6.
> CH13 analogue: `../../planetar/proposal/MC-2_alignment.md`.

## Draft (workspace markdown — strip headings before submission)

**Solution.** The Fusion Compliance Engine (FCE) is a modular, AI-enabled compliance layer that sits between sensor ingestion and the fusion analytics pipeline and acts as a policy-aware gatekeeper: it tags, filters, and routes each data element by machine-readable classification and operational-release policy, in real time, during multi-sensor fusion — exactly the automated compliance layer CH14 requires in place of manual review and procedural checklists. It is built on a provenance-tracked message bus the applicant has already developed, demonstrated for the 1a in a Maritime Domain Awareness setting (a CH14 example) fusing two modalities — open AIS and synthetic-Protected-B SAR detections — so that cross-domain merges carry a genuine classification decision.

**Essential Outcome compliance.** The FCE meets each Essential Outcome:

- **(EO1)** A modular component enforces classification and policy constraints *during* multi-sensor (≥2) fusion — enforcement is a synchronous hook at the bus chokepoint every fused element already crosses.
- **(EO2)** Enforcement is driven by **machine-readable policy** (W3C ODRL [P1], already built as an expression layer) applied across **≥2 sensor modalities** (AIS, SAR), at least the **Network-security** domain, and at least **Protected B** (the Government of Canada categorization baseline [S6]); classification markings are structured to NATO **STANAG 4774** confidentiality-label syntax [S1].
- **(EO3)** Checks and enforcement actions run **programmatically during ingestion and fusion, without human approval** for predefined policy conditions.
- **(EO4)** **Provenance records** are generated and retained for all data in and out of the pipeline — source-sensor id, classification marking, timestamp, and domain of origin (`zmesg` envelope + the 1a's added classification/domain fields), each marking bound to its element per NATO **STANAG 4778** [S2].
- **(EO5)** **Audit logs** record the policy rules applied, the enforcement action taken (**permit / restrict / downgrade / segregate**), and the resulting disposition, written to the CRC32 append-only WAL.
- **(EO6)** **Data lineage** from original ingestion through fused output is reconstructable (WAL replay + per-edge graph provenance) and **exportable** for compliance review, forensic analysis, or accreditation.

**Fit to the challenge intent.** CH14 seeks a sovereign, Canadian-developed and Canadian-controlled compliance engine for multi-domain fusion — a reusable building block "from Arctic surveillance to coalition interoperability hubs," supporting the CAF Digital Campaign Plan, the DND/CAF AI Strategy, NORAD modernization, and the Cyber Forces mandate. The FCE is Canadian-owned foreground IP built on the applicant's open-source spine; because it enforces at a chokepoint already benchmarked at nanosecond scale, it adds compliance without degrading tactical decision speed.

## TODO
- [x] Standards wired **2026-06-22** (all web-verified, see `../06-REFERENCES.md`): EO2 → ODRL [P1] + GoC
      Protected B [S6] + STANAG 4774 markings [S1]; EO4 → STANAG 4778 binding [S2].
- [ ] ⚠️ **Design-commitment check (for Steven):** "markings structured to STANAG 4774 / bound per STANAG 4778"
      and "Protected B per the GoC baseline" are **1a design commitments, not built code today** — the phrasing
      ("structured to", "bound per") keeps it honest as a TRL 2→3 design intent. Confirm willingness to commit
      the bid to these standards (low-risk: they *are* the standards for this); if not, soften to "designed to align with."
- [ ] Verbatim-check each EO against `../CH14-challenge.txt` lines 57–77 before lock (source confirmed 2026-06-22).
- [ ] Confirm "Network security domain" wording maps to our demo (synthetic markings).

## Char-count budget
Target ≤ 2,950. Measured 2026-06-22: ~2,790 after wiring cites — comfortable headroom.
