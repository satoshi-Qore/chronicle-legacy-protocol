# Chronicle / Legacy Protocol

A documentation-first blockchain research project for a Protocol Memory Layer that preserves ecosystem contribution, knowledge, reputation, and historical legacy.

## Short Description

Chronicle / Legacy Protocol is a conceptual research initiative focused on how decentralized ecosystems can remember meaningful human contribution over time. The project explores a protocol memory layer for verified contribution records, contributor reputation, ecosystem archives, knowledge inheritance, AI-assisted mentorship, and long-term legacy preservation.

This repository is not focused on implementation code yet. It is a concept, architecture, and documentation-stage project intended to define the problem space before any smart contracts, modules, or production systems are introduced.

## Problem

Decentralized ecosystems often depend on human work that is difficult to preserve. Code contributions, documentation, governance discussions, infrastructure operation, research, education, localization, community support, and historical decisions are frequently spread across repositories, forums, chat platforms, social networks, and governance portals.

As ecosystems grow, much of this memory becomes fragmented or lost. Contributors may leave without their work being understood. New participants may lack context. Governance decisions may lose their historical reasoning. Reputation may become reduced to social visibility, token ownership, or short-term activity rather than durable contribution.

The problem is not only technical. It is cultural, archival, and institutional.

## Vision

Chronicle / Legacy Protocol proposes a Protocol Memory Layer for decentralized ecosystems. The vision is to preserve verified contribution, knowledge, reputation, and historical context in a structured way that can support governance, onboarding, research, mentorship, and long-term community continuity.

The protocol is not designed as a rewards farming system. It does not treat every action as valuable by default. Instead, it asks how meaningful contribution can be documented, attested, contextualized, and inherited across time.

## Research Relationship

Chronicle / Legacy Protocol is the broader research framework. It studies the full memory layer: contribution records, attestation context, reputation safeguards, governance history, knowledge preservation, decision records, AI-assisted retrieval, and long-term ecosystem legacy.

Chronicle originated from earlier research into Proof of Contribution systems. That earlier work explored how contribution claims may be submitted, verified, attested, disputed, and preserved as evidence-aware records.

This separation keeps the research structure clear. Chronicle defines the larger protocol memory problem. Proof of Contribution examines a specific verification component that could later inform Chronicle's contribution and attestation layers.

## Core Principles

| Principle | Meaning |
|---|---|
| Memory before rewards | Preserve contribution history before assigning incentives |
| Context over score | Avoid reducing complex human contribution to a single number |
| Verification over noise | Prefer evidence, attestations, and review over raw activity volume |
| Human contribution matters | Recognize documentation, education, governance, infrastructure, and research work |
| Knowledge should survive | Preserve decisions, lessons, and contributor experience for future participants |
| Reputation must be contextual | Separate technical, governance, educational, infrastructure, and community reputation |
| AI should mentor, not replace | Use AI to help transmit ecosystem knowledge without erasing human judgment |
| Legacy should be accountable | Preserve historical records with limitations, disputes, and evidence quality in mind |

## Why It Matters

Blockchains often preserve transactions well, but they do not automatically preserve the human memory around those transactions. Ecosystems need more than ledgers of value transfer. They need durable records of contribution, governance reasoning, design decisions, operational knowledge, and community learning.

A protocol memory layer could help future contributors understand who built what, why decisions were made, which knowledge should be inherited, and how reputation emerged from verified participation rather than speculation or visibility alone.

## Canonical Architecture

The canonical architecture specification is the primary source of truth for Chronicle terminology, system flow, component boundaries, and dependency relationships.

Readers seeking the authoritative system model should begin with:

[Canonical Architecture Specification](./docs/Canonical_Architecture_Specification.md)

Canonical flow:

```text
Identity / Pseudonymity
-> Contribution Submission
-> Evidence
-> Memory Object
-> Evidence Quality
-> Privacy / Disclosure
-> Attestation
-> Attestation Authority
-> Lifecycle State
-> Protocol Memory Layer
-> Chronicle Archive
-> Reputation Graph
-> Knowledge Inheritance
-> AI Mentor
-> Legacy
```

Reader-friendly summary:

```text
Identity -> Contribution Submission -> Evidence -> Memory Object -> Attestation -> Archive/Reputation -> Knowledge Inheritance -> AI Mentor -> Legacy
```

## Research Map

This repository is organized as a layered research project. New readers can use the map below as a suggested reading path.

| Step | Document | Role in the Research |
|---|---|---|
| 0 | [Concept FAQ](./docs/Concept_FAQ.md) | Provides a quick question-and-answer introduction for new readers |
| 1 | [Canonical Architecture Specification](./docs/Canonical_Architecture_Specification.md) | Defines the authoritative system flow, terminology, boundaries, and dependency relationships |
| 2 | [Architecture Diagram](./docs/Architecture_Diagram.md) | Provides a visual view of the canonical Chronicle / Legacy Protocol research layers |
| 3 | [Protocol Memory Layer](./docs/Protocol_Memory_Layer.md) | Defines the central problem space and the purpose of protocol memory |
| 4 | [Identity and Pseudonymity Model](./docs/Identity_and_Pseudonymity_Model.md) | Defines actor continuity, pseudonymous contribution, reviewer identity, and identity boundaries |
| 5 | [Contribution Submission Protocol](./docs/Contribution_Submission_Protocol.md) | Defines contribution intake, evidence package formation, duplicate handling, and candidate Memory Object creation |
| 6 | [Evidence Quality Framework](./docs/Evidence_Quality_Framework.md) | Defines how evidence strength, source quality, and uncertainty should be interpreted |
| 7 | [Privacy and Disclosure Framework](./docs/Privacy_and_Disclosure_Framework.md) | Defines disclosure levels, redaction principles, consent-aware handling, and privacy boundaries |
| 8 | [Memory Object Model](./docs/Memory_Object_Model.md) | Defines the conceptual unit of record used to preserve contribution and knowledge context |
| 9 | [Memory Object Schema](./docs/Memory_Object_Schema.md) | Defines draft Memory Object fields, validation expectations, object types, and versioning rules |
| 10 | [Memory Lifecycle](./docs/Memory_Lifecycle.md) | Explains how records move through draft, review, verification, dispute, archival, and deprecation states |
| 11 | [Lifecycle State Machine](./docs/Lifecycle_State_Machine.md) | Defines formal lifecycle states, allowed transitions, invalid transitions, and review gates |
| 12 | [Attestation Model](./docs/Attestation_Model.md) | Explains how Memory Objects may be reviewed, accepted, disputed, or rejected |
| 13 | [Attestation Protocol Specification](./docs/Attestation_Protocol_Specification.md) | Defines structured attestation workflow, decision outcomes, and lifecycle transition mapping |
| 14 | [Attestation Authority Model](./docs/Attestation_Authority_Model.md) | Defines reviewer authority, attestation scope, and accountability within the attestation subsystem |
| 15 | [Chronicle Archive Model](./docs/Chronicle_Archive_Model.md) | Defines how Memory Objects, source references, evidence metadata, and historical context may be preserved over time |
| 16 | [Archive Reputation Interface](./docs/Archive_Reputation_Interface.md) | Defines how Archive records contribute to Reputation interpretation while ensuring reputation remains secondary to protocol memory |
| 17 | [Reputation Graph](./docs/Reputation_Graph.md) | Defines contextual reputation relationships across contributors, Memory Objects, attestations, domains, and disputes |
| 18 | [Knowledge Inheritance Framework](./docs/Knowledge_Inheritance_Framework.md) | Connects archived records to learning paths, handoff context, and long-term knowledge continuity |
| 19 | [AI Mentor Safety Model](./docs/AI_Mentor_Safety_Model.md) | Defines safety boundaries for source-linked AI-assisted retrieval and mentorship |
| 20 | [Governance Context](./docs/Governance_Context.md) | Preserves reasoning, trade-offs, and historical context around ecosystem decisions |
| 21 | [Chronicle Self-Governance](./docs/Chronicle_Self_Governance.md) | Defines how Chronicle evolves, how its rules may change, and how governance decisions become part of protocol memory |
| 22 | [Chronicle Network Architecture](./docs/Chronicle_Network_Architecture.md) | Defines how Chronicle may evolve into a multi-ecosystem memory network while preserving protocol neutrality, portability, and historical continuity |
| 23 | [Threat Model](./docs/Threat_Model.md) | Identifies abuse, manipulation, privacy, and memory-integrity risks |
| 24 | [Related Work](./docs/Related_Work.md) | Compares Chronicle with existing contribution, attestation, reputation, and governance systems |

The map separates canonical architecture, identity and intake, evidence and privacy, Memory Object design, attestation, archive and reputation, knowledge transmission, AI-assisted retrieval, governance memory, network architecture, and risk analysis.

## Dependency Flow

```text
Identity / Pseudonymity
-> Contribution Submission
-> Evidence
-> Memory Object
-> Evidence Quality
-> Privacy / Disclosure
-> Attestation
-> Attestation Authority
-> Lifecycle State
-> Protocol Memory Layer
-> Chronicle Archive
-> Reputation Graph
-> Knowledge Inheritance
-> AI Mentor
-> Legacy
```

| Dependency | Primary Document |
|---|---|
| Canonical architecture | [Canonical Architecture Specification](./docs/Canonical_Architecture_Specification.md) |
| Identity / Pseudonymity | [Identity and Pseudonymity Model](./docs/Identity_and_Pseudonymity_Model.md) |
| Contribution Submission | [Contribution Submission Protocol](./docs/Contribution_Submission_Protocol.md) |
| Evidence | [Evidence Quality Framework](./docs/Evidence_Quality_Framework.md) |
| Memory Object | [Memory Object Model](./docs/Memory_Object_Model.md) |
| Memory Object Schema | [Memory Object Schema](./docs/Memory_Object_Schema.md) |
| Evidence Quality | [Evidence Quality Framework](./docs/Evidence_Quality_Framework.md) |
| Privacy / Disclosure | [Privacy and Disclosure Framework](./docs/Privacy_and_Disclosure_Framework.md) |
| Attestation | [Attestation Model](./docs/Attestation_Model.md) |
| Attestation Protocol | [Attestation Protocol Specification](./docs/Attestation_Protocol_Specification.md) |
| Attestation Authority | [Attestation Authority Model](./docs/Attestation_Authority_Model.md) |
| Lifecycle State | [Lifecycle State Machine](./docs/Lifecycle_State_Machine.md) |
| Protocol Memory Layer | [Protocol Memory Layer](./docs/Protocol_Memory_Layer.md) |
| Chronicle Archive | [Chronicle Archive Model](./docs/Chronicle_Archive_Model.md) |
| Reputation Graph | [Reputation Graph](./docs/Reputation_Graph.md) |
| Archive / Reputation Boundary | [Archive Reputation Interface](./docs/Archive_Reputation_Interface.md) |
| Knowledge Inheritance | [Knowledge Inheritance Framework](./docs/Knowledge_Inheritance_Framework.md) |
| AI Mentor | [AI Mentor Safety Model](./docs/AI_Mentor_Safety_Model.md) |
| Chronicle Network | [Chronicle Network Architecture](./docs/Chronicle_Network_Architecture.md) |

## Research Roadmap

| Phase | Focus | Expected Output | Status |
|---|---|---|---|
| Phase 1 | Conceptual foundation | Core vision, problem framing, canonical architecture, architecture map, protocol memory definition, and foundational Memory Object model | In progress |
| Phase 2 | Identity, contribution intake, evidence, and privacy | Identity model, contribution submission protocol, evidence quality framework, and privacy/disclosure boundaries | In progress |
| Phase 3 | Memory Object and lifecycle specification | Memory Object schema, lifecycle narrative, state machine, validation expectations, and archival criteria | In progress |
| Phase 4 | Attestation and authority model | Attestation model, attestation protocol, reviewer authority, dispute handling, and accountability boundaries | In progress |
| Phase 5 | Archive, reputation, inheritance, and AI mentor research | Archive model, archive-reputation interface, reputation graph, knowledge inheritance, and source-linked AI mentor safety | In progress |
| Phase 6 | Governance and network research | Governance context, self-governance, Chronicle domain/network architecture, and risk analysis | In progress |
| Phase 7 | Specification and prototype research | Formal data models, privacy controls, validation flows, and possible implementation prototypes | Future research |

## Research Status

| Area | Current State | Next Research Need |
|---|---|---|
| Canonical Architecture | Drafted as source of truth | Keep all architecture documents aligned with the canonical flow |
| Concept FAQ | Drafted | Keep updated as architecture terms evolve |
| Architecture Diagram | Drafted | Keep visual flow aligned with the canonical architecture |
| Protocol Memory Layer | Drafted | Align conceptual layer with identity, submission, memory object, lifecycle, archive, and evidence quality models |
| Identity / Pseudonymity | Drafted | Refine identity continuity, portability, and pseudonymity boundaries |
| Contribution Submission | Drafted | Refine submission review thresholds and candidate Memory Object criteria |
| Evidence Quality Framework | Drafted | Refine evidence levels by object type and reviewer role |
| Privacy / Disclosure | Drafted | Refine consent, redaction, restricted access, and disclosure boundary rules |
| Memory Object Model | Refined foundational model | Formalize object identity, validation rules, and future schema constraints |
| Memory Object Schema | Drafted | Refine required fields, type-specific schemas, and portability constraints |
| Memory Lifecycle | Drafted | Align narrative lifecycle language with the formal state machine |
| Lifecycle State Machine | Drafted | Refine transition rules, review gates, and archival criteria |
| Attestation Model | Drafted | Align attestation outcomes with lifecycle state definitions |
| Attestation Protocol | Drafted | Refine structured workflow, decision outcomes, and lifecycle transition mapping |
| Attestation Authority | Drafted | Align reviewer authority with research-stage non-scoring boundaries |
| Chronicle Archive | Archive model drafted | Refine preservation modes, redaction rules, archival integrity requirements, and link-rot handling |
| Archive Reputation Interface | Drafted | Refine signal classification, lifecycle-aware interpretation rules, and privacy boundary enforcement |
| Reputation Graph | Reputation graph drafted | Refine graph relationships, privacy boundaries, archive interface, and dispute-sensitive interpretation |
| Knowledge Inheritance | Refined architecture model | Add concrete lineage examples and inheritance review criteria |
| AI Mentor Layer | Safety model drafted | Add retrieval policy examples and source-citation response patterns |
| Governance Context | Drafted | Add more governance memory scenarios |
| Chronicle Self-Governance | Drafted | Refine governance actor model, ADR structure, RCP lifecycle, and dispute resolution process |
| Chronicle Network | Network architecture drafted | Refine domain model, cross-domain exchange conventions, and identity continuity approach |
| Decision Record Template | Drafted and sample-tested | Add more sample decision records over time |
| Related Work | Drafted | Expand comparison with additional academic and open-source systems |
| Threat Model | Drafted | Refine mitigations into future protocol requirements |
| Future Research | Drafted | Prioritize open questions for specification work |

## Repository Structure

```text
chronicle-legacy-protocol/
|
|-- README.md
|-- CONTRIBUTING.md
|
|-- docs/
|   |-- Canonical_Architecture_Specification.md
|   |-- Concept_FAQ.md
|   |-- Architecture_Diagram.md
|   |-- Protocol_Memory_Layer.md
|   |-- Identity_and_Pseudonymity_Model.md
|   |-- Contribution_Submission_Protocol.md
|   |-- Evidence_Quality_Framework.md
|   |-- Privacy_and_Disclosure_Framework.md
|   |-- Memory_Object_Model.md
|   |-- Memory_Object_Schema.md
|   |-- Memory_Lifecycle.md
|   |-- Lifecycle_State_Machine.md
|   |-- Attestation_Model.md
|   |-- Attestation_Protocol_Specification.md
|   |-- Attestation_Authority_Model.md
|   |-- Chronicle_Archive_Model.md
|   |-- Archive_Reputation_Interface.md
|   |-- Reputation_Graph.md
|   |-- Knowledge_Inheritance_Framework.md
|   |-- AI_Mentor_Safety_Model.md
|   |-- Governance_Context.md
|   |-- Chronicle_Self_Governance.md
|   |-- Chronicle_Network_Architecture.md
|   |-- Decision_Record_Template.md
|   |-- Related_Work.md
|   |-- Threat_Model.md
|   |-- 01-proof-of-contribution.md
|   |-- 02-contributor-reputation.md
|   |-- 03-chronicle-archive.md
|   |-- 04-knowledge-inheritance.md
|   |-- 05-ai-mentor-layer.md
|   |-- 06-legacy-protocol.md
|   |-- 07-chronicle-network.md
|   `-- 08-future-research.md
|
|-- research/
|   |-- sample-decision-record.md
|   |-- use-cases.md
|   `-- ecosystem-scenarios.md
|
`-- manifesto/
    `-- chronicle-manifesto.md
```

The numbered documents in `docs/` are early concept notes. They preserve the initial research framing of the project. The current architecture documents listed below should be treated as the primary reading path for public review.

## Key Documents

- [Canonical Architecture Specification](./docs/Canonical_Architecture_Specification.md)
- [Concept FAQ](./docs/Concept_FAQ.md)
- [Architecture Diagram](./docs/Architecture_Diagram.md)
- [Protocol Memory Layer](./docs/Protocol_Memory_Layer.md)
- [Identity and Pseudonymity Model](./docs/Identity_and_Pseudonymity_Model.md)
- [Contribution Submission Protocol](./docs/Contribution_Submission_Protocol.md)
- [Evidence Quality Framework](./docs/Evidence_Quality_Framework.md)
- [Privacy and Disclosure Framework](./docs/Privacy_and_Disclosure_Framework.md)
- [Memory Object Model](./docs/Memory_Object_Model.md)
- [Memory Object Schema](./docs/Memory_Object_Schema.md)
- [Memory Lifecycle](./docs/Memory_Lifecycle.md)
- [Lifecycle State Machine](./docs/Lifecycle_State_Machine.md)
- [Attestation Model](./docs/Attestation_Model.md)
- [Attestation Protocol Specification](./docs/Attestation_Protocol_Specification.md)
- [Attestation Authority Model](./docs/Attestation_Authority_Model.md)
- [Chronicle Archive Model](./docs/Chronicle_Archive_Model.md)
- [Archive Reputation Interface](./docs/Archive_Reputation_Interface.md)
- [Reputation Graph](./docs/Reputation_Graph.md)
- [Knowledge Inheritance Framework](./docs/Knowledge_Inheritance_Framework.md)
- [AI Mentor Safety Model](./docs/AI_Mentor_Safety_Model.md)
- [Governance Context](./docs/Governance_Context.md)
- [Chronicle Self-Governance](./docs/Chronicle_Self_Governance.md)
- [Chronicle Network Architecture](./docs/Chronicle_Network_Architecture.md)
- [Decision Record Template](./docs/Decision_Record_Template.md)
- [Related Work](./docs/Related_Work.md)
- [Threat Model](./docs/Threat_Model.md)
- [Sample Decision Record](./research/sample-decision-record.md)
- [Contribution Guidelines](./CONTRIBUTING.md)
- [Chronicle Manifesto](./manifesto/chronicle-manifesto.md)
- [Use Cases](./research/use-cases.md)
- [Ecosystem Scenarios](./research/ecosystem-scenarios.md)

## Early Concept Notes

The following documents are shorter early-stage concept notes. They remain useful for understanding the original project framing, but they should not be treated as the most complete architecture documents where a newer model exists.

- [01 - Proof of Contribution](./docs/01-proof-of-contribution.md)
- [02 - Contributor Reputation](./docs/02-contributor-reputation.md)
- [03 - Chronicle Archive](./docs/03-chronicle-archive.md)
- [04 - Knowledge Inheritance](./docs/04-knowledge-inheritance.md)
- [05 - AI Mentor Layer](./docs/05-ai-mentor-layer.md)
- [06 - Legacy Protocol](./docs/06-legacy-protocol.md)
- [07 - Chronicle Network](./docs/07-chronicle-network.md)
- [08 - Future Research](./docs/08-future-research.md)

## Current Stage

Current stage: **concept and architecture research**.

This repository intentionally avoids smart contract code, implementation code, token mechanics, and deployment claims. The current goal is conceptual clarity: defining the architecture, research questions, risks, and long-term purpose of a Protocol Memory Layer.

## Relationship to Proof of Contribution

Proof of Contribution can be understood as historical context for Chronicle / Legacy Protocol. It focuses on verified contribution records and the verification process around those records. Chronicle / Legacy Protocol extends this narrower contribution-verification question toward ecosystem memory, knowledge inheritance, AI-assisted mentorship, governance context, and long-term legacy preservation.

## Author

**Satoshi-Qore**  
Community Research Contributor

## Status

This project is exploratory. All claims should be treated as research framing until supported by formal specifications, implementation prototypes, governance review, and empirical ecosystem data.
