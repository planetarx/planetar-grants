# PRC-2 — Novelty (20 pts)

> **Field cap:** 3,000 characters. **Tight + high weight.** CH13 analogue: `../../planetar/proposal/PRC-2_novelty.md`.
> ⚠️ **Novelty = the FCE engine + policy model, NOT the fusion model** (`../THESIS.md`). Keep fusion to ≤1 line of background.

## Draft (workspace markdown — strip headings before submission)

**(a) New knowledge / technology.**

(1) *Enforcement embedded in the fusion path — the core contribution.* Compliance for multi-domain fusion is enforced today by manual review and checklists, or by guards that screen data at a network boundary — after or beside fusion. The FCE instead places a **synchronous policy gate at the single chokepoint every fused element crosses**, deciding per element to **permit, restrict, downgrade, or segregate** before a cross-domain merge. Per-element, in-line enforcement *during* multi-sensor fusion — not perimeter screening or post-hoc audit — is, to the applicant's knowledge, absent from the literature: novel, separately patentable Canadian foreground IP.

(2) *Machine-readable rights repurposed as defence classification policy.* The FCE adopts **W3C ODRL** — a standards-track rights language used across IDSA, Gaia-X, and JPEG Trust — as the policy language for classification guides, release authorities, and coalition caveats. The applicant has already built an ODRL *expression* layer (`planetar-market`); by design it expresses but does not enforce. The novelty is the **evaluation-and-enforcement engine** binding an ODRL policy to a real-time disposition over an element's {classification, domain, source, modality, releasability}, hot-reloadable with no system restart.

(3) *Accreditation-grade lineage as a property of the substrate.* Because every decision is written to an append-only, CRC32-protected, bit-exact-replayable log and every fused edge carries provenance, exportable ingestion-to-output lineage is a **structural property**, not a bolt-on report — accreditation-ready by construction.

**(b) Enhanced capability vs SOTA.** *Speed:* manual compliance cannot keep pace with AI-fusion volume and velocity; the FCE enforces at a chokepoint benchmarked at p50 80–140 ns / p99 400–900 ns, so enforcement adds negligible tactical latency — the explicit CH14 constraint. *Placement:* in-path per-element dispositions (downgrade/segregate, not just allow/deny) versus boundary guards' coarse pass/block. *Trust:* each disposition renders its governing rule and provenance for operator inspection and controlled override. *Pedigree:* the applicant's peer-reviewed ML over noisy, scarce-label sensor streams (ORCA-SLANG, Interspeech 2021 [A2]; Sattar et al., PacRim 2011, on Ocean Networks Canada data [A1]) and named-inventor provenance/entity-resolution IP (US 10,936,582; US 11,442,952, Salesforce-assigned background) evidence delivery capability.

**(c) Future potential.** The "enforce policy at the fusion chokepoint" pattern generalizes to any multi-domain setting CH14 names — Joint ISR (SIGINT + EO/IR + radar), Arctic surveillance, tactical-edge dismounted, coalition interoperability — without redesign, because the engine is agnostic to which modalities cross the bus. As sovereign Canadian foreground IP, it is a reusable building block for every future fusion system and a basis for Component 1b/2 hardening.

## TODO
- [ ] Add a real prior-art citation for cross-domain guards / ODRL adoption (new ref list).
- [ ] Confirm ODRL adopters (IDSA/Gaia-X/JPEG Trust) against `planetar-market/RESEARCH-LEGAL.md` §B.

## Char-count budget
Target ≤ 2,960 (tight — this draft runs over; trim (b) pedigree clause at red-team).
