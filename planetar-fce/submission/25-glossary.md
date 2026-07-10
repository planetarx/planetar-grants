# Field 25 — Glossary

**DIP page:** Component 1a → Glossary. Add each as a term + definition (separate entries; blank lines here are fine).
**Status:** ✅ READY — covers the terms actually used in the CH14 narratives. Drop any the form already defines.

FCE: Fusion Compliance Engine — a modular, AI-enabled component that automatically enforces classification and release-authority policy in real time during multi-sensor fusion.

Compliance-by-design: building policy enforcement into the data path itself, rather than applying review or audit after the fact.

Chokepoint: the single message bus that every fused observation crosses; where the FCE enforces policy.

Disposition: the FCE's decision on a data element — permit, restrict, downgrade, or segregate.

Downgrade: reducing the classification or release sensitivity of a data element so it can be shared more widely.

Segregate: isolating a data element so it is not merged across a security domain it is not cleared for.

Multi-sensor (multi-domain) fusion: combining data from two or more sensor types or security domains into a single picture.

AIS: Automatic Identification System — a transponder system broadcasting a vessel's identity, position, course and speed (the unclassified modality in the demo).

SAR: Synthetic-Aperture Radar — satellite or airborne radar imaging that operates day or night and through cloud.

Sentinel-1: the European Space Agency's free, public C-band SAR satellite mission (the Protected-B-marked modality in the demo).

EO: Electro-Optical — visible-spectrum (camera) imagery. RF: Radio Frequency emissions. Hydrophone: an underwater microphone for passive acoustic detection.

MDA: Maritime Domain Awareness — the demonstration domain (a named CH14 example).

ISR: Intelligence, Surveillance and Reconnaissance. C2: Command and Control. DND/CAF: Department of National Defence / Canadian Armed Forces.

Classification marking: machine-readable metadata stating a data element's classification level, releasability and policy identifier.

Protected B: a Government of Canada classification level for sensitive information whose unauthorized disclosure could cause serious injury outside the national interest.

Release authority / coalition caveat: rules governing who a data element may be released to (e.g., national-only, or specific coalition partners).

ODRL: W3C Open Digital Rights Language — a standards-track machine-readable policy language; the FCE's policy substrate.

STANAG 4774 / 4778: NATO standards for confidentiality metadata label syntax (4774) and for binding that label to the data object (4778).

ABAC / XACML: Attribute-Based Access Control, and its OASIS policy-language standard; the incumbent access-decision approach the FCE contrasts with.

W3C PROV: the W3C standard data model for provenance and lineage; the interoperable target for the FCE's exportable lineage.

Cross-Domain Solution (CDS) / guard: a device that screens data at a network boundary between security domains; "Raise the Bar" is the NCDSMO security standard for them.

WAL (write-ahead log): an append-only, integrity-protected log recording every event so state can be replayed exactly — the FCE's audit-and-lineage spine.

Provenance / lineage: the recorded chain of which inputs and rules produced a given output, enabling audit, forensic review and accreditation.

Entity resolution: linking observations to a single canonical entity and tracking it, with provenance on each link.

Hot-reload: updating policy without restarting the system (policy is data, not code).

Accreditation / Authority-to-Operate (ATO): the formal approval to run a system that handles classified data.

TRL: Technology Readiness Level (1–9). SWaP: Size, Weight and Power — the constraints of edge/deployed hardware.

GBA Plus: Gender-Based Analysis Plus — the Government of Canada framework for assessing diverse population impacts.

ONC: Ocean Networks Canada — the University of Victoria-operated cabled ocean observatory (source of the applicant's peer-reviewed hydrophone ML).
