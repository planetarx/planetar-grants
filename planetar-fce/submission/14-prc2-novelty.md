# Field 14 — PRC-2: Novel & Innovative Solution

**Form section:** Component 1a → PRC-2 (20 pts) · **Cap:** 3,000 characters
**LOCAL CHAR COUNT:** 2924 (cap 3,000) ⚠️ tightest narrative — re-verify the DIP counter before Next
**Source:** `../proposal/PRC-2_novelty.md` — R8 team/hardware amendment + 2026-07-13 benchmark; blank lines stripped per DIP rule.
**Status:** ✅ READY (regenerated 2026-07-13, post-R8)

## Paste-protocol notes

- Blank lines stripped (they count toward the DIP cap). Single newline between paragraphs.
- Markdown emphasis removed; (a)/(b)/(c), (1)/(2)/(3), (i)/(ii)/(iii), (EOn)/(DOn) labels kept as plain text.
- Citation keys like [P1]/[S1]/[A1] stay in — they resolve in field 26 (Reference Documents).
- After paste, DIP's counter should read ~2924 (±2). If it reads noticeably higher, normalize smart chars (— – µ " ') to ASCII and re-paste.

--- PASTE THIS BELOW ---
(a) New knowledge / technology.
(1) Enforcement embedded in the fusion path — the core contribution. Compliance for multi-domain fusion is enforced today by manual review and checklists, or by cross-domain guards [S3] that screen at a network boundary, beside or after fusion. The FCE instead places a synchronous policy gate at the single message chokepoint every fused element crosses, deciding per element to permit, restrict, downgrade, or segregate before a cross-domain merge occurs. Per-element, in-line enforcement during multi-sensor fusion — not perimeter screening or post-hoc audit — is, to the applicant's knowledge, absent from the open literature: novel, separately patentable Canadian foreground IP.
(2) Machine-readable rights repurposed as defence classification policy. The FCE adopts W3C ODRL [P1] — a standards-track rights language used across IDSA, Gaia-X, and JPEG Trust — as the policy language for classification guides, release authorities, and coalition caveats. The applicant has built an ODRL expression layer (planetar-market) that by design expresses but does not enforce; the novelty is the evaluation-and-enforcement engine binding an ODRL policy to a real-time disposition over an element's {classification, domain, source, modality, releasability}, hot-reloadable with no restart. This brings a civil-standards substrate to sovereign defence fusion.
(3) Accreditation-grade lineage as a property of the substrate. Because every decision is written to an append-only, CRC32-protected, replayable log and every fused edge carries provenance, exportable ingestion-to-output lineage is a structural property, not a bolt-on report — forensic review and accreditation by construction.
(b) Enhanced capability vs SOTA. Speed: manual compliance cannot keep pace with AI-fusion volume; the FCE enforces at a benchmarked chokepoint (p50 95–100 ns / p99 1.0–1.6 µs), adding negligible tactical latency — the CH14 constraint. Placement: in-path per-element dispositions (downgrade/segregate, not just allow/deny) versus boundary guards' coarse pass/block. Trust: each disposition renders its governing rule and provenance for inspection and controlled override, beyond opaque after-the-fact logging. Pedigree: the applicant's peer-reviewed reliable-ML work on noisy, scarce-label sensor streams [A1, A2] and named-inventor provenance/entity-resolution IP (US 10,936,582 — Salesforce-assigned background, not owned) evidence capability to deliver.
(c) Future potential. The "enforce policy at the fusion chokepoint" pattern generalizes to any multi-domain setting CH14 names — Joint ISR (SIGINT + EO/IR + radar), Arctic surveillance, tactical edge, coalition interoperability — without redesign, since the engine is agnostic to which modalities cross the bus. As sovereign Canadian foreground IP, it is a reusable building block for every future fusion system and a basis for Component 1b/2 hardening.
--- END PASTE ---
