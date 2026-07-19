# Field 25 — Glossary

**DIP page:** Component 1a → Glossary. Add each as a **term + definition** (separate entries).
**Format:** term in bold, definition alone in the code fence below it — copy the fence contents straight into the definition box.
**Status:** ✅ READY — covers the terms actually used in the CH14 narratives (incl. the R8 hardware terms). Drop any the form already defines.

FCE (Fusion Compliance Engine)
```
A modular, AI-enabled component that automatically enforces classification and release-authority policy in real time during multi-sensor fusion.
```

Compliance-by-design
```
Building policy enforcement into the data path itself, rather than applying review or audit after the fact.
```

Chokepoint
```
The single message bus that every fused observation crosses; where the FCE enforces policy.
```

Disposition
```
The FCE's decision on a data element — permit, restrict, downgrade, or segregate.
```

Downgrade
```
Reducing the classification or release sensitivity of a data element so it can be shared more widely.
```

Segregate
```
Isolating a data element so it is not merged across a security domain it is not cleared for.
```

Multi-sensor (multi-domain) fusion
```
Combining data from two or more sensor types or security domains into a single picture.
```

AIS (Automatic Identification System)
```
A transponder system broadcasting a vessel's identity, position, course and speed (the unclassified modality in the demonstration).
```

SAR (Synthetic-Aperture Radar)
```
Satellite or airborne radar imaging that operates day or night and through cloud.
```

Sentinel-1
```
The European Space Agency's free, public C-band SAR satellite mission (the Protected-B-marked modality in the demonstration).
```

EO (Electro-Optical)
```
Visible-spectrum (camera) imagery.
```

RF (Radio Frequency)
```
Radio-frequency emissions.
```

Hydrophone
```
An underwater microphone for passive acoustic detection.
```

MDA (Maritime Domain Awareness)
```
The demonstration domain (a named CH14 example).
```

ISR
```
Intelligence, Surveillance and Reconnaissance.
```

C2
```
Command and Control.
```

DND/CAF
```
Department of National Defence / Canadian Armed Forces.
```

Classification marking
```
Machine-readable metadata stating a data element's classification level, releasability and policy identifier.
```

Protected B
```
A Government of Canada classification level for sensitive information whose unauthorized disclosure could cause serious injury outside the national interest.
```

Release authority / coalition caveat
```
Rules governing who a data element may be released to (e.g., national-only, or specific coalition partners).
```

ODRL (Open Digital Rights Language)
```
A W3C standards-track machine-readable policy language; the FCE's policy substrate.
```

STANAG 4774 / 4778
```
NATO standards for confidentiality metadata label syntax (4774) and for binding that label to the data object (4778).
```

ABAC / XACML
```
Attribute-Based Access Control, and its OASIS policy-language standard; the incumbent access-decision approach the FCE contrasts with.
```

W3C PROV
```
The W3C standard data model for provenance and lineage; the interoperable target for the FCE's exportable lineage.
```

Cross-Domain Solution (CDS) / guard
```
A device that screens data at a network boundary between security domains; "Raise the Bar" is the NCDSMO security standard for them.
```

WAL (write-ahead log)
```
An append-only, integrity-protected log recording every event so state can be replayed exactly — the FCE's audit-and-lineage spine.
```

Provenance / lineage
```
The recorded chain of which inputs and rules produced a given output, enabling audit, forensic review and accreditation.
```

Entity resolution
```
Linking observations to a single canonical entity and tracking it, with provenance on each link.
```

Hot-reload
```
Updating policy without restarting the system (policy is data, not code).
```

Accreditation / Authority-to-Operate (ATO)
```
The formal approval to run a system that handles classified data.
```

TRL (Technology Readiness Level)
```
The 1-to-9 scale for technology maturity used to stage IDEaS funding components.
```

SWaP (Size, Weight and Power)
```
The constraints of edge/deployed hardware.
```

FPGA (Field-Programmable Gate Array)
```
Reconfigurable hardware used to prototype and validate a digital circuit design before committing it to fixed silicon; the project demonstrates the hardware enforcement datapath on an FPGA.
```

RISC-V
```
An open, royalty-free processor instruction-set architecture; the hardware enforcement datapath is a RISC-V core extended with custom instructions for envelope parse, label match, and disposition.
```

Tape-out / multi-project wafer (MPW)
```
Committing a verified chip design to fabrication; an MPW run shares one mask set across many small projects, reducing test-chip cost (the Component 1b silicon path).
```

GBA Plus (Gender-Based Analysis Plus)
```
The Government of Canada framework for assessing diverse population impacts.
```

ONC (Ocean Networks Canada)
```
The University of Victoria-operated cabled ocean observatory (source of the applicant's peer-reviewed hydrophone machine learning).
```
