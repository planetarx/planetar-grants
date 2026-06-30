# PRC-2 — Novelty (20 pts)

> **Field cap:** 3,000 characters. **Tight + high weight.** CH13 analogue: `../../planetar/proposal/PRC-2_novelty.md`.
> ⚠️ **Novelty = the FCE engine + policy model, NOT the fusion model** (`../THESIS.md`). Keep fusion to ≤1 line of background.

## Draft (workspace markdown — strip headings before submission)

**(a) New knowledge / technology.**

<<<<<<< HEAD
(1) *Enforcement embedded in the fusion path — the core contribution.* Compliance for multi-domain fusion is enforced today by manual review and checklists, or by guards that screen data at a network boundary — after or beside fusion. The FCE instead places a **synchronous policy gate at the single chokepoint every fused element crosses**, deciding per element to **permit, restrict, downgrade, or segregate** before a cross-domain merge. Per-element, in-line enforcement *during* multi-sensor fusion — not perimeter screening or post-hoc audit — is, to the applicant's knowledge, absent from the literature: novel, separately patentable Canadian foreground IP.

(2) *Machine-readable rights repurposed as defence classification policy.* The FCE adopts **W3C ODRL** — a standards-track rights language used across IDSA, Gaia-X, and JPEG Trust — as the policy language for classification guides, release authorities, and coalition caveats. The applicant has already built an ODRL *expression* layer (`planetar-market`); by design it expresses but does not enforce. The novelty is the **evaluation-and-enforcement engine** binding an ODRL policy to a real-time disposition over an element's {classification, domain, source, modality, releasability}, hot-reloadable with no system restart.

(3) *Accreditation-grade lineage as a property of the substrate.* Because every decision is written to an append-only, CRC32-protected, bit-exact-replayable log and every fused edge carries provenance, exportable ingestion-to-output lineage is a **structural property**, not a bolt-on report — accreditation-ready by construction.

**(b) Enhanced capability vs SOTA.** *Speed:* manual compliance cannot keep pace with AI-fusion volume and velocity; the FCE enforces at a chokepoint benchmarked at p50 80–140 ns / p99 400–900 ns, so enforcement adds negligible tactical latency — the explicit CH14 constraint. *Placement:* in-path per-element dispositions (downgrade/segregate, not just allow/deny) versus boundary guards' coarse pass/block. *Trust:* each disposition renders its governing rule and provenance for operator inspection and controlled override. *Pedigree:* the applicant's peer-reviewed ML over noisy, scarce-label sensor streams (ORCA-SLANG, Interspeech 2021 [A2]; Sattar et al., PacRim 2011, on Ocean Networks Canada data [A1]) and named-inventor provenance/entity-resolution IP (US 10,936,582; US 11,442,952, Salesforce-assigned background) evidence delivery capability.
=======
(1) *Enforcement embedded in the fusion path — the core contribution.* Compliance for multi-domain fusion is enforced today by manual review and checklists, or by cross-domain guards [S3] that screen at a network boundary, beside or after fusion. The FCE instead places a **synchronous policy gate at the single message chokepoint every fused element crosses**, deciding per element to **permit, restrict, downgrade, or segregate** before a cross-domain merge occurs. Per-element, in-line enforcement *during* multi-sensor fusion — not perimeter screening or post-hoc audit — is, to the applicant's knowledge, absent from the open literature: novel, separately patentable Canadian foreground IP.

(2) *Machine-readable rights repurposed as defence classification policy.* The FCE adopts **W3C ODRL** [P1] — a standards-track rights language used across IDSA, Gaia-X, and JPEG Trust — as the policy language for classification guides, release authorities, and coalition caveats. The applicant has built an ODRL *expression* layer (`planetar-market`) that by design expresses but does not enforce; the novelty is the **evaluation-and-enforcement engine** binding an ODRL policy to a real-time disposition over an element's {classification, domain, source, modality, releasability}, hot-reloadable with no restart. This brings a civil-standards substrate to sovereign defence fusion.

(3) *Accreditation-grade lineage as a property of the substrate.* Because every decision is written to an append-only, CRC32-protected, replayable log and every fused edge carries provenance, exportable ingestion-to-output lineage is a **structural property**, not a bolt-on report — forensic review and accreditation by construction.

**(b) Enhanced capability vs SOTA.** *Speed:* manual compliance cannot keep pace with AI-fusion volume; the FCE enforces at a benchmarked chokepoint (p50 80–140 ns / p99 400–900 ns), adding negligible tactical latency — the CH14 constraint. *Placement:* in-path per-element dispositions (downgrade/segregate, not just allow/deny) versus boundary guards' coarse pass/block. *Trust:* each disposition renders its governing rule and provenance for inspection and controlled override, beyond opaque after-the-fact logging. *Pedigree:* the applicant's peer-reviewed reliable-ML work on noisy, scarce-label sensor streams [A1, A2] and named-inventor provenance/entity-resolution IP (US 10,936,582 — Salesforce-assigned background, not owned) evidence capability to deliver.
>>>>>>> bcfd69ed4dbffd688c9d7c7049f9348755b82181

**(c) Future potential.** The "enforce policy at the fusion chokepoint" pattern generalizes to any multi-domain setting CH14 names — Joint ISR (SIGINT + EO/IR + radar), Arctic surveillance, tactical edge, coalition interoperability — without redesign, since the engine is agnostic to which modalities cross the bus. As sovereign Canadian foreground IP, it is a reusable building block for every future fusion system and a basis for Component 1b/2 hardening.

## TODO
- [x] Confirm ODRL adopters — **verified 2026-06-22** against `planetar-market/src/odrl.ts` header
      (cites `RESEARCH-LEGAL.md` §B): "W3C Recommendation already adopted across JPEG Trust, IDSA,
      Gaia-X and EUIPO"; and "ODRL *expresses* rights; it does not *enforce* them." Draft's
      adopter subset (IDSA/Gaia-X/JPEG Trust) and the expresses-not-enforces claim are accurate.
- [x] Prior-art cites wired **2026-06-22**: (a)(1) cross-domain-guard contrast → **[S3]**; (a)(2) ODRL → **[P1]**.
      Both web-verified (NCDSMO RTB 2018; W3C ODRL 2018-02-15) — see `../06-REFERENCES.md`. Optional future add:
      XACML/ABAC contrast **[P3, P4]** — but PRC-2 has no char room and no XACML prose; better placed in PRC-1/PRC-4.

## Char-count budget
Target ≤ 2,960. **Trimmed 2026-06-22: 3,260 → ~2,950** (stripped paste block). Re-measure at red-team.
