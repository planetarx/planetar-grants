# Field 17 — PRC-5: Gender-based Analysis Plus (GBA Plus)

**Form section:** Component 1a → PRC-5 (5 pts) · **Cap:** 3,000 characters
**LOCAL CHAR COUNT:** 2917 (cap 3,000)
**Source:** `../proposal/PRC-5_gba_plus.md` — R8 team/hardware amendment + 2026-07-13 benchmark; blank lines stripped per DIP rule.
**Status:** ✅ READY — **R9 replacement text (2026-07-20)**: cross-cutting principle reworded to enforce-first (the filed "engine proposes, operator adjudicates" contradicted EO1/EO3's no-human-approval requirement); "no kernel bypass or FPGA **required**"; "Bilingual-**ready**". Matches `paste/17-prc5-gba-plus.txt`.

## Paste-protocol notes

- Blank lines stripped (they count toward the DIP cap). Single newline between paragraphs.
- Markdown emphasis removed; (a)/(b)/(c), (1)/(2)/(3), (i)/(ii)/(iii), (EOn)/(DOn) labels kept as plain text.
- Citation keys like [P1]/[S1]/[A1] stay in — they resolve in field 26 (Reference Documents).
- After paste, DIP's counter should read ~2872 (±2). If it reads noticeably higher, normalize smart chars (— – µ " ') to ASCII and re-paste.

--- PASTE THIS BELOW ---
GBA Plus is applied to the FCE's technical solution along three axes, with one cross-cutting principle: the engine enforces predefined policy automatically, and the human analyst stays accountable — through review, explanation, and logged override — guarding against automation bias that can fall unevenly on under-represented groups.
(i) Bias in automated enforcement — the FCE-specific axis. An engine that automatically permits, restricts, downgrades, or segregates each data element exercises consequential authority; if its policy or the sensor coverage behind it is uneven, that authority falls unevenly. Classification and release rules — and the modality coverage informing them — are denser for commercial shipping lanes and Northern-hemisphere SAR than for Indigenous coastal fishing waters or low-traffic Arctic regions, so an FCE could systematically over-segregate (excluding under-represented sources from fusion) or mishandle data tied to specific communities. The 1a treats this as measurable: a disposition-audit protocol stratifies enforcement decisions by source, modality, and region to surface uneven handling — a concrete artefact, not a generality. Because every disposition is written human-readably to the immutable WAL with its governing rule and provenance, each decision is reviewable and contestable, and an authorised operator can override it with the override itself logged accountably.
(ii) Operator-side accessibility and multilingual usability — an M2 deliverable. CAF operators span genders, ages, abilities, neurodivergence, and linguistic backgrounds. The shell (planetar-ui, React 19) that surfaces each compliance decision and its causal evidence chain is built against a documented accessibility checklist: keyboard navigation, ARIA roles on the decision/provenance panels, screen-reader compatibility, and a colour-vision-deficient-safe palette (disposition double-encoded with shape/label, not colour alone). Bilingual-ready English/French via i18n. Plain-language, explainable decisions plus controlled override lower the expertise barrier, widening who can operate the system beyond specialist compliance officers. The accessibility checklist is itself a 1a deliverable.
(iii) Deployment-side equity. The engine's SWaP profile — commodity-Linux, laptop-class, no kernel bypass or FPGA required (the single-file C broker) — means it deploys at the same fidelity in low-bandwidth or remote settings (Indigenous coastal communities, small-port operations, Arctic coast-guard auxiliary stations) as in central operations centres. Equity is a structural property of the architecture, not a deployment afterthought.
Implementation in the 1a: the disposition bias-audit protocol (M2 evaluation) and the operator-accessibility + bilingual-readiness checklist (M2 demo) are explicit work-plan deliverables — GBA Plus applied to the technical solution, not deferred to a follow-on phase.
--- END PASTE ---
