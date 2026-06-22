# PRC-2 — Novelty (20 pts)

> **Field cap:** 3,000 characters. **Tight section** (high weight). CH13 analogue: `../../planetar/proposal/PRC-2_novelty.md`.
> ⚠️ **Novelty here is the FCE engine + policy model — NOT the fusion model** (`THESIS.md`).

## Draft (skeleton)

The novel contribution is **compliance-by-design enforcement embedded in the fusion path**:
1. **Enforcement at the chokepoint, not beside it.** Existing approaches bolt compliance on
   after fusion or via manual review. Novelty: a synchronous policy gate at the single bus
   every fused element crosses, with permit/restrict/downgrade/**segregate** dispositions.
2. **Machine-readable policy → cross-domain fusion control.** Repurpose W3C **ODRL** (a
   civil data-rights standard) as a defence classification/release-authority policy language,
   evaluated per element across modalities and security domains. [differentiator]
3. **Provenance-native, exportable audit by construction.** Append-only CRC32 WAL +
   per-edge lineage → accreditation-grade lineage as a property of the substrate, not an
   afterthought.
4. **Sovereign Canadian foreground IP.** Net-new, Canadian-owned (vs. allied-nation
   compliance tech CH14 says Canada lacks). Background: applicant-named-inventor patents
   (US 10,936,582 / 11,442,952, Salesforce-assigned) — **background, not owned IP** [CH13 Q9 rules].

## TODO
- [ ] Prior-art contrast: name how current cross-domain/guard solutions differ (no overclaiming).
- [ ] Keep the fusion model to ≤1 background sentence.

## Char-count budget
Target ≤ 2,960 (tight — budget headroom carefully).
