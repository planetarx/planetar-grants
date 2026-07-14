# DIP Portal — CH14 submission kit (field map + protocol + checklist)

**For:** Steven Ness, Zax Analytics — IDEaS CFP6 **Challenge 14** (Reliable AI Sensor Fusion / FCE), **Component 1a**
**Solicitation:** `W7714-248676/014` · **Portal:** https://defence-innovation-portal.my.site.com/
**Deadline:** **2026-07-21 14:00 EDT** (extended 2026-07-13 — was 07-14) · **Target file: 2026-07-17** (4-day buffer)
**Built:** 2026-06-23 · mirrors the proven CH13 kit (`../../planetar/submission/README.md`)

This directory maps the **Component 1a step** of the DIP wizard field-by-field, in portal order. The portal
advances field-by-field on *Next* (no jumping around), so each row = one form input. The narrative content
already lives in [`../proposal/`](../proposal/); this kit says **which file → which field**, the **cap**, and
what still needs drafting. At T-3 you produce the paste-ready plaintext per the protocol below.

> **Locked facts threaded through every field.** Thesis = **compliance-by-design / Fusion Compliance Engine**
> (`../THESIS.md`). **TRL 2 → 3.** **Budget $131,000** (≈52% of the $250K cap; DIP M1 = 44.3% ≤ 70%) —
> `../proposal/PRC-7_budget.md`. Demo = **evaluator-operable** AIS + SAR at planetar.ca, synthetic Protected-B
> markings (Q5/R7). Latency claim gated on **Q7** (run `ring-hop` on Linux — `../08-OPEN-QUESTIONS.md` §Q7).

## Form-step navigation table

| # | DIP form field | Cap | Source in workspace | Status |
|---|---|---|---|---|
| 01 | Proposal Title | short | [`01-proposal-title.md`](01-proposal-title.md) | ✅ |
| 02 | S&T Challenge (dropdown) | — | **"Reliable AI sensor fusion for real-world missions" (CH14)** | ✅ pick |
| 03 | Project Synopsis | **2,000** | [`03-project-synopsis.md`](03-project-synopsis.md) (1,847) | ✅ |
| 04 | Synopsis sharing checkbox | — | agree | ✅ |
| 05 | Synopsis upload not-evaluated checkbox | — | agree | ✅ |
| 06 | Keywords (3–5) | — | [`06-keywords.md`](06-keywords.md) | ✅ |
| 07 | Project Overview | **3,000** | [`07-project-overview.md`](07-project-overview.md) (2,669) | ✅ |
| 08 | MC-1: TRL **before** (dropdown) | — | **TRL-2** | ✅ |
| 09 | MC-1: **R&D activities** | 3,000 | [`09-mc1-rd-activities.md`](09-mc1-rd-activities.md) (2,940) — split from `MC-1_trl.md` | ✅ |
| 10 | MC-1: End-state TRL (dropdown) | — | **TRL-3** | ✅ |
| 11 | MC-1: **Justify end-state TRL** | 3,000 | [`11-mc1-end-state-justify.md`](11-mc1-end-state-justify.md) (2,641) — split from `MC-1_trl.md` | ✅ |
| 12 | MC-2: Alignment | 3,000 | `proposal/MC-2_alignment.md` (2,825) | ✅ |
| 13 | PRC-1: S&T Merit | 3,000 | `proposal/PRC-1_st_merit.md` (2,550) | ✅ |
| 14 | PRC-2: Novelty | 3,000 | `proposal/PRC-2_novelty.md` (2,943) ⚠️ tightest | ✅ |
| 15 | PRC-3: Impact | 3,000 | `proposal/PRC-3_impact.md` (2,638) | ✅ |
| 16 | PRC-4: Feasibility | 3,000 | `proposal/PRC-4_feasibility.md` (2,664) | ✅ |
| 17 | PRC-5: GBA Plus | 3,000 | `proposal/PRC-5_gba_plus.md` (2,888) | ✅ |
| 18 | PRC-6: Desired Outcomes | 3,000 | `proposal/PRC-6_desired_outcomes.md` (2,150) | ✅ |
| 19 | Financial — cost summary (ref) | (ref) | `proposal/PRC-7_budget.md` Table A — **$131,000** | ✅ |
| 20 | Work Plan & Deliverables — **2 milestones** (the real SC-1/PRC-7 entry) | (tables) | `proposal/PRC-7_budget.md` Table B (M1 = 44.3%) | 🟡 transcribe to wizard |
| 21+ | Milestone 1 / Milestone 2 entries; Location & Language; Certifications | — | §"To draft" below | ⏳ |

> **✅ MC-1 split done (2026-06-23).** `MC-1_trl.md` → field 09 ([`09-mc1-rd-activities.md`](09-mc1-rd-activities.md),
> 2,940) = current-TRL-2 + prior-R&D; field 11 ([`11-mc1-end-state-justify.md`](11-mc1-end-state-justify.md),
> 2,641) = the TRL-3 justification (twofold demo: synthetic AIS+SAR Protected-B scenario + evaluator-operable
> live planetar.ca). Each has its own 3,000 cap; both fit.

## Still to draft (remaining non-narrative fields)

✅ **Done 2026-06-23:** 01 title, 03 synopsis, 06 keywords, 07 overview, 09/11 MC-1 split, 24 location/language,
[`25-glossary.md`](25-glossary.md), [`26-reference-documents.md`](26-reference-documents.md), [`27-progression-1b.md`](27-progression-1b.md) (4,939 / 8,000).

| Field | Cap | How to build | Source |
|---|---|---|---|
| **21+ Milestone entries** | tables | At submission, expand PRC-7 Table B into per-milestone deliverable/price entries (CH13 model: `../../planetar/submission/20–23`). | `PRC-7` |
| **28 Certifications** | — | Portal checkboxes — CFP6 Amendment 2 certs (solo bid, no subcontractors, Canadian). Fill in-portal. | Amendment 2 |

**Authoring is complete.** Only the milestone-table transcription (T-2, against the live wizard) and the
certification checkboxes (in-portal) remain — neither is paste content.

## T-3 strip-and-paste protocol (per narrative field)

For each of MC-1(→09+11), MC-2, PRC-1…6:
1. Take the body between `## Draft` and the next `##` heading.
2. Strip markdown: `**bold**`→bold, `*italic*`→italic, `` `code` ``→code; remove the inline `(a)`/`(b)`/`(c)`
   sub-labels only if the DIP field is split into sub-boxes (CH14 isn't — keep them as plain text).
3. Remove workspace meta (the `>` blockquote notes, the `## TODO` / `## Char-count budget` sections).
4. **Strip blank lines between paragraphs** — DIP's rule: *"blank line spaces between paragraphs count toward
   character count."* Separate paragraphs with a **single newline**, not a blank line.
5. **Re-count in the DIP field itself** (the portal counter is authoritative; the workspace `wc` is a proxy).
   Target ≤ 2,950; PRC-2 (2,943) and PRC-5 (2,888) are tightest.
6. Screenshot after each *Next*-save.

**Char-count gotchas (cost real characters):**
- **Smart-quote / dash conversion.** DIP may auto-convert straight quotes to curly and may re-render `—`/`–`.
  Our drafts already use `—`, `–`, `"…"`. If DIP counts higher than the workspace, normalize `— – " " ' '` to
  ASCII `- - " " ' '`, re-count, re-paste. (This is the #1 cause of "file says under, DIP says over.")
- Single newlines between paragraphs render as line breaks in the textarea — reviewer experience preserved,
  characters minimized.

## Pre-submission checklist (T-7 → T-0)

Deadline **2026-07-21 14:00 EDT** (extended 2026-07-13; was 07-14); target file **2026-07-17**. Gate on **Q8** (CH14 Q&A doc) before final assembly.

**T-7 (~2026-07-04) — freeze**
- [ ] 🛑 **Q7 benchmark** run on Linux (`./tests/ring-hop 1000000`); p50/p99 recorded; latency claim reconciled across MC-1/MC-2/PRC-1/2/4/6 (or reworded to predecessor framing if not run). — `08-OPEN-QUESTIONS.md` §Q7
- [ ] DIP registration / login confirmed for Zax Analytics.
- [ ] Admin fields drafted: 01 title, 03 synopsis, 06 keywords, 07 overview.
- [ ] MC-1 split into the 09 + 11 paste blocks.
- [ ] Re-verify **Q4** — no CFP6 amendment newer than 2 on notice `cb-0-11990877` (re-check; notices change).
- [ ] **Patent sanity-grep** (Q6): `grep -riE "our patent|applicant'?s patent|owns? the patent|patented by"` across `proposal/` → must be **0**.

**T-3 (~2026-07-08) — strip + convert**
- [ ] Run the strip-and-paste protocol on all narrative fields; save paste-ready `.txt` per field.
- [ ] Each stripped block re-counted ≤ 2,950 (workspace proxy) — flag PRC-2/PRC-5.

**T-2 (~2026-07-09) — DIP dry run**
- [ ] Paste every field into DIP; confirm the portal counter matches within ±2 (else apply the smart-quote fix).
- [ ] Transcribe PRC-7 into the 2-milestone Work Plan tables; confirm SC-1: total $131,000 ≤ $250K **and** M1 = 44.3% ≤ 70%.
- [ ] Screenshot each saved field.

**T-1 (~2026-07-10) — final review (DO NOT submit)**
- [ ] Full read-through in the portal; thesis-consistency + no markdown artifacts.
- [ ] Certifications + Location/Language complete.

**T-0 (2026-07-11) — submit**
- [ ] Morning submit attempt; afternoon verify the proposal shows *Submitted*. Buffer 07-12 → 07-14.

## How to use this in the portal
1. Log in, open the Component-1a draft proposal.
2. Open this README beside the portal; go **down the table in order**.
3. For each field, paste the stripped block, verify the DIP counter, click *Next*, screenshot.
4. When this step is done, the wizard advances to Work Plan / Milestones / Location / Certifications — drive
   those from the §"Still to draft" rows.
