# Field 03 — Project Synopsis

**Form section:** Component 1a → 2 - Project Description → A · **Cap:** 2,000 characters
**Type:** Text area (do NOT use the optional file upload — Field 05 acknowledges it won't be evaluated).
**Audience:** published externally if funded (Field 04). Non-specialist; leads with the problem, not the internals.
**Status:** ✅ READY.

--- PASTE THIS BELOW ---
Multi-sensor fusion — combining radar, imagery, signals and acoustic data into one picture — is how modern forces make sense of contested environments. But every data element carries classification rules, release authorities and coalition caveats, and today those are enforced by manual review and checklists that cannot keep pace with AI-driven fusion. Canada lacks a sovereign, Canadian-controlled engine to enforce them automatically.
Planetar's Fusion Compliance Engine (FCE) closes that gap. It sits at the single message chokepoint every fused observation crosses and, in real time, evaluates machine-readable policy against each data element — deciding whether to permit, restrict, downgrade or segregate it before a cross-domain merge occurs — while writing an immutable, exportable audit-and-lineage record. It enforces compliance during fusion without adding latency that would degrade a tactical decision.
At project start the supporting platform is working open-source code: a provenance-tracked real-time message bus with an append-only audit log, a typed envelope that already carries source and timing provenance, a machine-readable policy layer (W3C ODRL), a per-edge lineage graph, an analyst console, and four per-modality detectors. The new research for Component 1a is the policy-evaluation-and-enforcement engine itself, the classification and domain provenance fields, the enforcement-action audit record, the exportable lineage format, and an FPGA-prototyped hardware enforcement datapath for edge deployment.
End-state: an evaluator-operable live demonstration at planetar.ca that fuses two modalities (AIS and synthetic-aperture radar) under synthetic Protected-B markings, enforces policy per element, and exports an accreditation-grade lineage trail. A two-person Zax Analytics team; public data only; no government-furnished property, no field deployments, no real classified content.
--- END PASTE ---

## Notes
- If DIP rejects as over 2,000: trim the final sentence's tail ("no government-furnished property…") first, then the detector list in paragraph 3.
