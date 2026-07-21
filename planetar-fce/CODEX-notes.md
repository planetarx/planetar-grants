# CODEX notes for improving the CH14/FCE submission

Created: 2026-07-19

Scope: notes after reviewing the filed portal summary `CP6-143774_ProposalSummary.pdf`,
`submission-record.md`, the `submission/` paste files, and the source narratives in
`proposal/`. The proposal has already been submitted as CP6-143774 on 2026-07-18. If a
replacement is filed before the CH14 deadline, update `submission-record.md` with the new
proposal reference and do not silently rewrite the filed-state record.

## Executive summary

The submission is fundamentally credible: it matches CH14's FCE thesis, keeps the FCE at
TRL 2 -> 3, uses public/synthetic data, and has a clear "own the chokepoint" feasibility
argument. The strongest improvement is not a major rewrite. It is a replacement pass that
removes preventable portal/text artifacts, restores the missing reference list, and fixes a
few consistency issues that an evaluator could notice.

Highest-value fixes before a replacement submission:

1. Restore the standards/prior-art reference documents so inline citation keys resolve.
2. Scrub markdown and portal-rendering artifacts from the filed text.
3. Replace Unicode comparison/symbol shorthand that the PDF mangled (`>=`, `<=`, arrows).
4. Fix two internal consistency issues: GBA+ "operator adjudicates" vs. EO3 automation, and
   "no FPGA" in PRC-5 vs. the added FPGA datapath work package.
5. Tighten security language around "immutable", CRC32, Protected B, and downgrading.
6. Keep the hardware datapath explicitly subordinate and optional; the software FCE must
   remain the complete deliverable.

## Replacement-submission checklist

### 1. Fix the filed Reference Documents field

Filed state: the reference list contains only three applicant-credential entries:

- Orchive PhD thesis
- US Patent 11,442,952 B2
- US Patent 10,936,582 B2

But the scored narratives cite unresolved keys such as `[P1]`, `[P3]`, `[P4]`, `[S1]`,
`[S2]`, `[S3]`, `[S5]`, `[S6]`, `[A1]`, and `[A2]`. This is the biggest avoidable
reviewer-friction issue. The glossary decodes the terms, but it does not replace a reference
list.

Recommendation: in a replacement, include compact entries for all load-bearing references
from `06-REFERENCES.md`, especially:

- W3C ODRL Information Model / Vocabulary 2.2, 2018-02-15.
- OASIS XACML 3.0, 2013-01-22.
- NIST SP 800-162 ABAC, 2014 / 2019 update.
- NATO STANAG 4774 / ADatP-4774, confidentiality metadata label syntax.
- NATO STANAG 4778 / ADatP-4778, metadata binding mechanism.
- NCDSMO Raise the Bar for Cross Domain Solutions, 2018.
- W3C PROV family, 2013-04-30.
- TBS Standard on Security Categorization / Protected B and ITSG-33/PBMM framing.
- Sattar et al. 2011 and ORCA-SLANG 2021 for applicant sensor-ML pedigree.

Keep patent entries, but remove markdown from the author cells. Use plain text:
"named-inventor credit only, not the assignee or owner."

### 2. Scrub portal artifacts

The PDF contains cosmetic artifacts that are easy to fix and cost reviewer confidence:

- Literal `**not**` in patent author cells.
- Stray backticks in cost descriptions, for example around "No model training." and
  "Description: Development...".
- The PDF text shows "ingestionoutput" where an arrow was stripped from
  "ingestion->output".
- MC-2 shows "multi-sensor (2)" where the `>=`/greater-than-or-equal symbol was mangled.
- PRC-4 shows "Milestone 1 stays 70% of budget" where the source intended "<= 70%".

Recommendation: make all portal paste text ASCII-safe:

- Use "at least two" instead of `>=2`.
- Use "less than or equal to 70%" or "<= 70%" instead of `<=`/Unicode less-than-equal.
- Use "ingestion-to-output" instead of arrows.
- Use "microseconds" instead of the micro symbol if the portal is inconsistent.
- Avoid markdown entirely in table fields, including backticks and bold.

### 3. Fix the GBA+ automation wording

Filed PRC-5 says:

"the human analyst stays accountable in the loop - the engine proposes a disposition, the
operator adjudicates"

That can be read as contradicting EO3, which requires programmatic checks without human
approval for predefined policy conditions. The intended architecture is stronger than the
wording: the FCE automatically enforces predefined policy, while an authorized operator can
review and override with accountability.

Recommendation: replace with:

"The FCE automatically enforces predefined policy conditions; the human analyst remains
accountable through review, explanation, and authorized override, with every override logged."

This keeps GBA+ and operator trust without weakening MC-2.

### 4. Fix the PRC-5 FPGA contradiction

Filed PRC-5 says the SWaP profile requires "no kernel bypass or FPGA", while PRC-4/PRC-6
and the budget include an FPGA-prototyped hardware enforcement datapath.

Recommendation: change the PRC-5 sentence to:

"The baseline software FCE runs on commodity Linux without requiring kernel bypass or FPGA;
the FPGA work package is an optional acceleration and sensor-adjacent enforcement path, not
a dependency for deployment."

That resolves the contradiction and reinforces the hardware package as subordinate.

### 5. Be more precise about CRC32 and immutability

The proposal repeatedly calls the CRC32 append-only WAL "immutable". Append-only logging is
a good audit spine, and CRC32 is useful for accidental-corruption detection, but CRC32 is not
a tamper-evidence or cryptographic integrity primitive. A security-minded evaluator may notice.

Recommendation:

- Use "append-only, replayable, integrity-checked WAL" for the current built asset.
- Reserve "tamper-evident" or "immutable" for a 1a deliverable only if the project adds a
  hash chain, signature, or other cryptographic binding.
- If there is character room, add a small M2 deliverable: "hash-chained or signed
  enforcement records for tamper-evident export." This pairs well with STANAG 4778 binding
  and accreditation language.

Do not oversell CRC32 as a security feature.

### 6. Keep Protected B language synthetic and design-oriented

The current submission usually handles this correctly: public AIS/SAR data, synthetic
Protected-B markings, no real classified content. Preserve that discipline everywhere.

Risk: a phrase like "demonstrated across two modalities at Protected B" can sound like real
Protected B handling. For Component 1a, the honest claim is:

"demonstrated across AIS and SAR using synthetic Protected-B markings, with no real
classified or protected government data."

Also consider adding one sentence that the 1a tests policy semantics and lineage under
Protected-B-like markings, not operational Protected-B accreditation.

### 7. Clarify "Network-security domain"

MC-2 states EO2 compliance across at least the Network-security domain, but the demo is
maritime AIS + SAR. That is not necessarily wrong, because CH14 separates sensor modalities
from security domains, but the proposal should make the mapping explicit.

Recommendation: add or revise one sentence in MC-2:

"The demonstration labels each flow with a security-domain attribute, including the
Network-security domain required by CH14, while AIS and SAR provide the two sensor
modalities."

This prevents a reviewer from reading "maritime domain" as the answer to "Network security
domain."

### 8. Make the AI basis explicit without overclaiming

CH14 asks for an AI-enabled component. The proposal calls the FCE AI-enabled, but most of
the FCE as described is deterministic policy enforcement around an AI fusion pipeline.
That is defensible, but it should be stated cleanly.

Recommendation: add one compact phrase where MC-2 or the overview introduces the FCE:

"AI-enabled because it governs the AI fusion pipeline and its learned/per-modality
detections at the point where their outputs merge; the enforcement decisions themselves are
auditable policy decisions, not opaque model guesses."

This is better than pretending the policy engine is itself a black-box AI model.

### 9. De-risk the hardware datapath framing

The R8 hardware package makes the proposal more ambitious and gives a strong SWaP/edge path,
but it is the largest fit risk because CH14's essential outcomes are software/policy/audit
oriented and Component 1a is only six months.

If keeping the hardware package, every mention should reinforce:

- The software FCE is complete without the hardware datapath.
- The hardware datapath accelerates the common case only.
- Rare or complex policies safely fall back to the software FCE.
- The FPGA prototype is proof-of-concept, not a silicon deliverable.
- Hardware incompleteness cannot block EO1-EO6.

The filed milestone risk language already says this in places. Strengthen it in the overview,
PRC-4, and PRC-6 if space permits.

If replacing with a lower-risk proposal is more important than preserving R8, the alternative
is to remove the hardware work package and return to the leaner software-only budget. I do not
think this is required, but it is the main strategic tradeoff.

### 10. Repair the "downgrade" authority nuance

"Downgrade" is listed by CH14 as an enforcement action, so it belongs in the proposal. But in
real classified/protected workflows, downgrading can require explicit authority.

Recommendation: add precision where possible:

"downgrade when authorized by the machine-readable policy"

or:

"policy-authorized downgrade"

This protects against a reader thinking the system autonomously reclassifies data without
authority.

### 11. Tighten latency claims

The ring-hop benchmark is a useful baseline and was correctly updated to planetar-broker
numbers: p50 95-100 ns / p99 1.0-1.6 microseconds. The safest framing is:

- Built bus shared-memory ring-hop baseline is nanosecond/microsecond scale.
- The 1a measures incremental FCE-on overhead.
- The final claim of "no material tactical latency" depends on the measured FCE-on result.

Avoid implying the full broker path including TCP/UDP ingest, WAL, policy evaluation, UI, and
export is nanosecond-scale. Current text mostly says "shared-memory path" and "baseline";
keep that precision.

### 12. Strengthen PRC-1/PRC-4 with one concrete success table if space allows

The proposal names falsifiable outcomes, which is good. A replacement could make them more
reviewable by adding exact acceptance targets or evidence artifacts:

- FCE-on overhead report: p50/p99 overhead versus no-FCE baseline, stratified by policy
  complexity.
- Policy-decision correctness report: confusion matrix over labelled synthetic policy cases.
- Lineage fidelity: reconstructed ingestion-to-output chain matches ground truth for the demo
  scenario.
- WAL/export artifact: reviewer can download/export a replay bundle.
- Bias audit: dispositions stratified by modality/source/region.

Do not invent numeric thresholds unless Steven is comfortable being held to them. A named
artifact is enough if character space is tight.

### 13. Keep novelty focused on the FCE, not the maritime demo

The current novelty section is good. Preserve the hierarchy:

- Product/thesis: in-path policy enforcement and audit lineage.
- Demo setting: maritime AIS + SAR.
- Background: learned fusion and prior entity-resolution work.

Avoid turning the replacement into a dark-vessel or SAR proposal. That would weaken CH14 fit.

### 14. Re-check Q8 before any replacement

`08-OPEN-QUESTIONS.md` still records Q8: the CH14 "Questions and Answers" document posted in
notice amendment 003 on 2026-07-13 was not obtained before the first submission.

Recommendation:

- Try to obtain/read the Q&A before replacement.
- If unavailable, record the attempt in `submission-record.md`.
- If the Q&A changes interpretation of Network security, Protected B, data availability,
  references, or Component scope, update MC-2/PRC-4 first.

This is the only open external-document risk in the workspace notes.

### 15. Use the same plain-text paste protocol for every field

Before replacement, run a single audit over the paste files and PDF output:

- No markdown syntax: backticks, `**`, heading markers, workspace TODOs.
- No unresolved citation keys unless they are in Reference Documents.
- No Unicode symbols the portal may drop: arrows, greater-than-equal, less-than-equal.
- No accidental contradiction between budget, team, milestones, and narratives.
- No "real Protected B" implication.
- No "patent owner" implication.
- No hidden line-break damage such as "ingestionoutput".

The generated PDF summary, not the workspace character count, is the final artifact to read.

## Section-by-section notes

### Synopsis and Project Overview

Strong:

- Opens with the operational problem and sovereign gap.
- Distinguishes built substrate from new FCE research.
- States public/synthetic data and no real classified content.
- Names the live planetar.ca demo and two modalities.

Improve:

- Ensure "AI-enabled" is grounded in the AI fusion pipeline rather than left as an adjective.
- Make hardware datapath optional/subordinate in one phrase.
- If there is space, add "policy-authorized" before downgrade.

### MC-1 TRL

Strong:

- Honest TRL 2 -> TRL 3.
- Good distinction between built components and unbuilt enforcement engine.
- Benchmark attribution is now to planetar-broker, not predecessor `zbroker0`.

Improve:

- Avoid "immutable" unless strengthened beyond CRC32.
- Keep "classification marking and domain of origin are additive" but do not imply this is
  already implemented.
- Ensure the live demo promise is operationally realistic because evaluators may actually use
  planetar.ca.

### MC-2 Alignment

Strong:

- Maps EO1-EO6 directly.
- Correctly names ODRL, STANAG 4774/4778, Protected B, audit logs, dispositions, and exportable
  lineage.

Improve:

- Fix the portal-mangled "multi-sensor (2)".
- Add the Network-security-domain mapping.
- Ensure all reference keys resolve in the Reference Documents field.
- Use "designed to align with STANAG..." if full STANAG access is not available.

### PRC-1 S&T Merit

Strong:

- Good standards base: ODRL, ABAC/XACML, STANAG, PROV.
- Good falsifiable outcomes.

Improve:

- Replace "immutable" with security-accurate audit language.
- Consider adding hash-chain/signature as a 1a or 1b path if accreditation is emphasized.
- Fix "ingestionoutput" caused by PDF extraction/arrow rendering.

### PRC-2 Novelty

Strong:

- Best section structurally: it leads with in-path enforcement, not fusion model novelty.
- Strong contrast against ODRL expression-only, ABAC/XACML access gates, and CDS boundary guards.

Improve:

- "Separately patentable" is fine if intentional, but it may be less valuable than a stronger
  standards/prior-art contrast. If space is tight, prefer the contrast.
- Use "to the applicant's knowledge" only once; the evidence should carry the claim.

### PRC-3 Impact

Strong:

- Directly quotes the sovereign capability gap.
- Good impact frame: reduce risk and increase tempo.
- Good reuse/generalization story.

Improve:

- Keep sovereignty grounded in open-source spine plus new Canadian-owned foreground IP, not US
  patents.
- Avoid implying that open-source AGPL alone satisfies DND sovereignty/control concerns. The
  stronger claim is applicant-controlled Canadian foreground IP plus transparent codebase.

### PRC-4 Feasibility

Strong:

- The "we own the chokepoint" argument is the proposal's strongest feasibility point.
- The six increments are bounded and understandable.
- Data feasibility is honest.
- Team/budget alignment is mostly clear.

Improve:

- Fix "Milestone 1 stays 70% of budget" to "Milestone 1 is 39.8% of total, under the 70% cap."
- Keep hardware as a non-blocking optional accelerator.
- Add "software FCE deliverables satisfy EO1-EO6 even if the FPGA proves only a subset of policy
  classes."
- Replace "immutable" with accurate WAL language or add tamper-evident record work.

### PRC-5 GBA Plus

Strong:

- FCE-specific GBA+ angle is better than generic inclusion boilerplate.
- Disposition audit protocol is a concrete artifact.
- Accessibility checklist is useful and reviewable.

Improve:

- Fix the automation contradiction: automatic enforcement first, review/override second.
- Fix "no FPGA" contradiction.
- If bilingual support is only readiness, say "bilingual-readiness" or "i18n-ready English/French
  labels", not full bilingual operation.

### PRC-6 Desired Outcomes

Strong:

- Clean mapping to DO1-DO4.
- Hot-reload demo is concrete.
- Override accountability is well aligned.

Improve:

- Be careful with "orders of magnitude under any tactical-decision threshold" unless a threshold is
  stated. Safer: "well below millisecond-scale fusion-processing budgets" if that is defensible.
- Reinforce that FPGA is optional acceleration and software remains complete.
- State "measured compute and memory envelope" as a deliverable with a named report artifact.

### PRC-7 Budget and Work Plan

Strong:

- Total $181,000 is below the $250,000 cap.
- Milestone 1 is 39.8%, safely below the 70% cap.
- Labour rates are simple and audit-friendly.
- No travel, no subcontractors, no government-furnished property.

Improve:

- Remove backticks from Other Cost descriptions.
- Make sure both team members are consistently described as employees if certifications rely on no
  subcontractors.
- Keep the FPGA board under Materials, not Other.
- Consider adding "hardware work package is severable from software EO delivery" in risk mitigation.

## Suggested replacement order

1. Update `submission/26-reference-documents.md` and the portal reference rows first.
2. Patch paste text for MC-2, PRC-1, PRC-4, PRC-5, PRC-6, and the milestone cost fields.
3. Regenerate paste-ready `.txt` files with an ASCII-only rule for symbols.
4. Paste into the portal and immediately generate/read the PDF summary.
5. Search the generated PDF text for: `**`, backticks, `ingestionoutput`, `(2) fusion`, `stays 70%`,
   `no FPGA`, `operator adjudicates`, unresolved reference keys.
6. Submit replacement only after the generated PDF is clean.
7. Update `submission-record.md` with the replacement reference number and exact timestamp.

## Do not change

- Do not change the thesis away from compliance-by-design/FCE.
- Do not move from Component 1a.
- Do not claim real Protected B handling or real classified data.
- Do not claim ownership of Salesforce-assigned patents.
- Do not make the learned fusion model the novelty.
- Do not bury the live evaluator-operable demo; it is strong TRL-3 evidence.

## If there is no replacement submission

If CP6-143774 remains the filed proposal, the residual risks are acceptable but real:

- The missing reference list is the largest avoidable weakness.
- The markdown/backtick artifacts look sloppy but are probably not disqualifying.
- The GBA+/FPGA wording contradictions are noticeable but confined.
- The main technical case still reads as coherent and aligned to CH14.

In that case, preserve this file as the post-submission improvement log and use it to prepare
any clarification, interview, Component 1b pitch, or future IDEaS submission.
