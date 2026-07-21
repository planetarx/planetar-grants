# CH14 replacement pass — 2026-07-19 (supersedes CP6-143774 if filed)

**Window:** a revised submission replaces CP6-143774 if filed before **2026-07-21 14:00 EDT**
(CH13 precedent: CP6-132296 → CP6-132484). **Q8 gate: ✅ PASSED 2026-07-19** — the Q&A doc is
live on the notice, downloaded and read (archived: `CH14-QA-amendment003-2026-07-13.pdf`);
**no amendment 004**; closing date confirmed. One Q&A answer changed this plan: **Q1 — DND
clarified the FCE itself must incorporate AI/ML** (any technique qualifies, incl.
knowledge-based AI, per Q19). PRC-1's grounding sentence and MC-2's EO1 line now state the
engine is knowledge-based AI (automated reasoning over a machine-readable policy knowledge
base). Everything else in the Q&A validates the filed design (synthetic/public data OK;
STANAG encouraged not mandated; AIS+SAR = two distinct modalities; offeror defines the
representative policy model; the between-ingestion-and-pipeline architecture is DND's own).

## Scope — exactly five text surfaces change; everything else re-files as-is

| Field | Change | New count (target ≤2,950) |
|---|---|---|
| **Reference Documents** | Restore all 12 entries from `submission/26-reference-documents.md` (plain text, no `**`/backticks); verified dates per §Dates below | per-entry fields |
| **MC-2** (`paste/12`) | `(≥2)`→`(at least two)`; `across ≥2`→`across two`; + EO2 parenthetical mechanizing the Network-security domain (domain-of-origin field); + EO1 "AI-enabled (knowledge-based AI: automated reasoning over machine-readable policy)" per Q&A Q1; compensating trims (line-1 compression, "Essential Outcome compliance:") | **2,928** |
| **PRC-1** (`paste/13`) | `ingestion→output`→`ingestion-to-output`; + AI-enabled grounding sentence in (a): the engine is knowledge-based AI per the CH14 Q&A, governing learned per-modality detections, dispositions auditable by construction | **2,847** |
| **PRC-4** (`paste/16`) | `SAR → CFAR`→`SAR with CFAR detection`; `stays ≤70%`→`is 39.8% of the total, under the 70% CFP cap`; trim: dropped "and wireless RF control systems" from the Colin Broughton credential (US 7,320,065 kept) | **2,939** |
| **PRC-5** (`paste/17`) | Cross-cutting principle reworded to enforce-first ("enforces predefined policy automatically… accountable through review, explanation, and logged override") — EO1/EO3 alignment; `no kernel bypass or FPGA` → `… FPGA required`; `Bilingual`→`Bilingual-ready` | **2,917** |

**Unchanged (re-paste verbatim from the filed version / existing paste files):** title, synopsis,
keywords, overview, MC-1 (both fields), PRC-2, PRC-3, PRC-6, glossary, location/language,
progression-to-1b, all milestone activity/deliverable/risk cells, labour/materials rows.

## Cost-description cells — re-enter without backticks (numbers UNCHANGED)

- **M1 Cloud compute ($1,500):** Cloud compute for Sentinel-1 scene fetching and processing, policy-evaluation test runs, and hosting the live planetar.ca system. No model training.
- **M2 Cloud compute ($2,000):** Cloud compute for enforcement-overhead benchmark runs, policy-correctness and lineage-fidelity evaluation, Sentinel-1 processing, and hosting the live evaluator-operable planetar.ca demonstrator.
- **M2 Datasets / licences ($500):** Reserve for paid data access if a public source proves insufficient; core demonstration data (AIS, Sentinel-1) are public and free.
- **M2 Software / tools ($500):** Development and operations tooling: continuous-integration runner minutes, observability/monitoring, and ancillary paid developer services. RTL flow on open-source toolchains.
  *(the filed cell had a pasted "Description: `" prefix — drop it)*

After editing any financial cell, re-verify: M1 total $72,000 · M2 total $109,000 · grand total
$181,000 · M1 = 39.8%.

## Dates for the reference list — ✅ ALL VERIFIED 2026-07-19/20

`submission/paste/26-reference-documents.txt` is complete (13 entries, no placeholders):
thesis **2013-12-23** (filed "2013-12-31" was wrong) · ODRL 2018-02-15 · XACML 2013-01-22 ·
PROV 2013-04-30 · SP 800-162 2014-01/upd 2019-08-02 · ADatP-4774 Ed A V1 **2017-12-20** ·
ADatP-4778 Ed A V1 **2018-10-26** · Raise the Bar **v4.1 2022-07-11** (initiative 2018) ·
TBS Appendix J **2019-07-01** · ITSG-33 **2012-11-01**. Sources + corrections recorded in
`submission/26-reference-documents.md`; evidence PDFs in `refs-evidence/`.

## Portal protocol (in order)

1. **Q8 gate:** confirm no amendment 004 / read the Q&A doc if available. If the Q&A changes
   any interpretation (Network security, Protected B, data, references, 1a scope), STOP and
   revise MC-2/PRC-4 first.
2. Open a revision of the proposal in DIP. Paste the five changed fields from `paste/`;
   re-paste unchanged fields only if the wizard forces re-entry.
3. Verify the DIP counter for each pasted field matches the file count within ±10
   (single newlines between paragraphs count; if DIP counts higher, normalize dashes/quotes
   to ASCII and re-paste).
4. Re-enter the Reference Documents article (12 entries) and the four cost cells above.
5. Confirm the synopsis one-pager (`submission/03-synopsis-onepager.pdf`) is attached if it
   wasn't in CP6-143774 (founder to confirm whether it was uploaded the first time).
6. Certifications + location/language re-confirmed unchanged.
7. **Generate the portal summary PDF and grep its extracted text** for the denylist before
   submitting: `**` · backtick · `ingestionoutput` · `(2) fusion` · `stays 70%` · `SAR CFAR` ·
   `operator adjudicates` · `≥` `≤` `→` (should be absent because the sources are now
   ASCII-safe) · dangling `[P1]`-style keys with no matching reference entry.
8. Submit; verify status; save the new PDF beside the old one; update `submission-record.md`
   with the new CP6 number (supersede, do not rewrite the CP6-143774 record).

## Deliberately NOT changed (decided 2026-07-19; rationale in session notes)

No "immutable" rewording sweep · no hash-chain deliverable or any work-plan content change ·
no R8 reversal · no success-metrics table · no Protected-B rewording (filed text already says
synthetic throughout) · PRC-6 left entirely untouched ("orders of magnitude" attaches to the
measured baseline and is immediately hedged) · PRC-2, PRC-3, overview, synopsis, MC-1 untouched.
