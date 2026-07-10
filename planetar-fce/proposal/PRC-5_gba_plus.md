# PRC-5 — GBA Plus (5 pts)

> **Field cap:** 3,000 characters. CH13 analogue: `../../planetar/proposal/PRC-5_gba_plus.md` — **largely reusable.**
> GBA+ for a compliance engine has a specific, strong angle (below).

## Draft (workspace markdown — strip headings before submission)

GBA Plus is applied to the FCE's technical solution along three axes, with one cross-cutting principle: the human analyst stays accountable in the loop — the engine proposes a disposition, the operator adjudicates — guarding against automation bias that can fall unevenly on under-represented groups.

**(i) Bias in automated enforcement — the FCE-specific axis.** An engine that automatically permits, restricts, downgrades, or segregates each data element exercises consequential authority; if its policy or the sensor coverage behind it is uneven, that authority falls unevenly. Classification and release rules — and the modality coverage informing them — are denser for commercial shipping lanes and Northern-hemisphere SAR than for Indigenous coastal fishing waters or low-traffic Arctic regions, so an FCE could systematically over-segregate (excluding under-represented sources from fusion) or mishandle data tied to specific communities. The 1a treats this as measurable: a **disposition-audit protocol** stratifies enforcement decisions by source, modality, and region to surface uneven handling — a concrete artefact, not a generality. Because every disposition is written human-readably to the immutable WAL with its governing rule and provenance, each decision is **reviewable and contestable**, and an authorised operator can **override** it with the override itself logged accountably.

**(ii) Operator-side accessibility and multilingual usability — an M2 deliverable.** CAF operators span genders, ages, abilities, neurodivergence, and linguistic backgrounds. The shell (`planetar-ui`, React 19) that surfaces each compliance decision and its causal evidence chain is built against a documented accessibility checklist: keyboard navigation, ARIA roles on the decision/provenance panels, screen-reader compatibility, and a colour-vision-deficient-safe palette (disposition double-encoded with shape/label, not colour alone). Bilingual English/French via i18n. Plain-language, explainable decisions plus controlled override lower the expertise barrier, widening who can operate the system beyond specialist compliance officers. The accessibility checklist is itself a 1a deliverable.

**(iii) Deployment-side equity.** The engine's SWaP profile — commodity-Linux, laptop-class, no kernel bypass or FPGA (the single-file C broker) — means it deploys at the same fidelity in low-bandwidth or remote settings (Indigenous coastal communities, small-port operations, Arctic coast-guard auxiliary stations) as in central operations centres. Equity is a structural property of the architecture, not a deployment afterthought.

**Implementation in the 1a:** the disposition bias-audit protocol (M2 evaluation) and the operator-accessibility + bilingual-readiness checklist (M2 demo) are explicit work-plan deliverables — GBA Plus applied to the technical solution, not deferred to a follow-on phase.

## TODO
- [x] Lifted CH13 PRC-5 **2026-06-22**, re-targeted from the fusion model to the enforcement engine; axis (i) sharpened to the FCE's distinctive auto-disposition-bias angle (the strongest GBA+ point for a compliance engine). Milestones re-mapped to the FCE's two (M1/M2), not CH13's six.

## Char-count budget
Target ≤ 2,950 (CH13 PRC-5 was ~2,930).
