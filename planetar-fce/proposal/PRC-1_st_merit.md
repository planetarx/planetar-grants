# PRC-1 — Science & Technology merit (10 pts)

> **Field cap:** 3,000 characters. CH13 analogue: `../../planetar/proposal/PRC-1_st_merit.md`.
> Threshold: contributes to the 70-pt minimum. Inline-labelled prose (DIP strips line breaks).

## Draft (skeleton)

The S&T merit is the **method for real-time policy enforcement inside a fusion pipeline**:
- **Problem rigor:** today compliance = manual review/checklists that can't keep pace with
  AI-fusion volume/velocity (CH14 background). The S&T question: can machine-readable policy
  be evaluated *per element, at the chokepoint, at fusion speed*, with provable audit?
- **Approach:** ODRL policy → evaluable rule over `{classification, domain, source,
  modality, releasability}`; decision = permit/restrict/downgrade/segregate; immutable WAL
  disposition; reconstructable lineage. [detail in `../03-ARCHITECTURE.md`]
- **Evidence base:** measured ns-scale chokepoint (latency headroom for enforcement);
  applicant's peer-reviewed ML/data-engineering record [reuse CH13 PRC-1 credentials].
- **Measurability:** define the 1a's measurable outcomes — enforcement overhead vs.
  baseline, policy-decision correctness on a labelled synthetic set, lineage-export fidelity.

## TODO
- [ ] State 2–3 falsifiable success metrics for the 1a.
- [ ] Reuse applicant S&T credentials from CH13 PRC-1 (re-verify still apt for compliance angle).

## Char-count budget
Target ≤ 2,950.
