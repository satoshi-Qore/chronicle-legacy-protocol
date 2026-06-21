![Chronicle Legacy Banner](./chronicle-legacy-banner.png)

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

The canonical architecture specification serves as the primary reference for Chronicle / Legacy Protocol.

Readers seeking the authoritative system model should begin with:

[Canonical Architecture Specification](./docs/Canonical_Architecture_Specification.md)

Core Flow:

```text
Contribution
-> Evidence
-> Memory Object
-> Attestation
-> Archive / Reputation
-> Knowledge Inheritance
-> AI Mentor
-> Legacy
```

## Research Map

This repository is organized as a layered research project. New readers can use the map below as a suggested reading path.

| Step | Document | Role in the Research |
|---|---|---|
| 0 | [Concept FAQ](./docs/Concept_FAQ.md) | Provides a quick question-and-answer introduction for new readers |
| 1 | [Canonical Architecture Specification](./docs/Canonical_Architecture_Specification.md) | Defines the authoritative system model, terminology, component boundaries, and dependency flow |
| 2 | [Architecture Diagram](./docs/Architecture_Diagram.md) | Provides a high-level view of the Chronicle / Legacy Protocol research layers |
| 3 | [Protocol Memory Layer](./docs/Protocol_Memory_Layer.md) | Defines the central problem space and the purpose of protocol memory |
| 4 | [Memory Object Model](./docs/Memory_Object_Model.md) | Defines the conceptual unit of record used to preserve contribution and knowledge context |
| 5 | [Memory Object Schema](./docs/Memory_Object_Schema.md) | Defines canonical fields, requirement levels, object types, relationship schema, validation rules, and example object shapes |
| 6 | [Memory Lifecycle](./docs/Memory_Lifecycle.md) | Explains how records move through draft, review, verification, dispute, archival, and deprecation states |
| 7 | [Lifecycle State Machine](./docs/Lifecycle_State_Machine.md) | Defines formal lifecycle states, allowed transitions, invalid transitions, review gates, and state effects |
| 8 | [Chronicle Archive Model](./docs/Chronicle_Archive_Model.md) | Defines how Memory Objects, source references, evidence metadata, and historical context may be preserved over time |
| 9 | [Evidence Quality Framework](./docs/Evidence_Quality_Framework.md) | Defines how evidence strength, source quality, and uncertainty should be interpreted |
| 10 | [Attestation Model](./docs/Attestation_Model.md) | Explains how contribution claims may be reviewed, accepted, disputed, or rejected |
| 11 | [Attestation Protocol Specification](./docs/Attestation_Protocol_Specification.md) | Defines the structured review workflow, decision outcomes, attestation record fields, and lifecycle transition mapping |
| 12 | [Attestation Authority Model](./docs/Attestation_Authority_Model.md) | Defines reviewer authority, attestation scope, and accountability within the attestation subsystem |
| 13 | [Reputation Graph](./docs/Reputation_Graph.md) | Defines contextual reputation relationships across contributors, Memory Objects, attestations, domains, and disputes |
| 14 | [Knowledge Inheritance Framework](./docs/Knowledge_Inheritance_Framework.md) | Connects archived records to learning paths, handoff context, and long-term knowledge continuity |
| 15 | [AI Mentor Safety Model](./docs/AI_Mentor_Safety_Model.md) | Defines safety boundaries for source-linked AI-assisted retrieval and mentorship |
| 16 | [Governance Context](./docs/Governance_Context.md) | Preserves reasoning, trade-offs, and historical context around ecosystem decisions |
| 17 | [Threat Model](./docs/Threat_Model.md) | Identifies abuse, manipulation, privacy, and memory-integrity risks |
| 18 | [Related Work](./docs/Related_Work.md) | Compares Chronicle with existing contribution, attestation, reputation, and governance systems |

The map separates conceptual foundation, evidence and verification, archival memory, knowledge transmission, AI-assisted retrieval, governance memory, and risk analysis. This helps the repository function as a research framework rather than a loose collection of documents.

## Dependency Flow

```text
Contribution -> Evidence -> Memory Object -> Attestation -> Attestation Protocol -> Attestation Authority -> Archive / Reputation -> Knowledge Inheritance -> AI Mentor -> Legacy
```

| Dependency | Primary Document |
|---|---|
| Contribution | [Proof of Contribution](./docs/01-proof-of-contribution.md) |
| Evidence | [Evidence Quality Framework](./docs/Evidence_Quality_Framework.md) |
| Memory Object | [Memory Object Model](./docs/Memory_Object_Model.md) |
| Memory Object Schema | [Memory Object Schema](./docs/Memory_Object_Schema.md) |
| Attestation | [Attestation Model](./docs/Attestation_Model.md) |
| Attestation Protocol | [Attestation Protocol Specification](./docs/Attestation_Protocol_Specification.md) |
| Attestation Authority | [Attestation Authority Model](./docs/Attestation_Authority_Model.md) |
| Archive | [Chronicle Archive Model](./docs/Chronicle_Archive_Model.md) |
| Reputation | [Reputation Graph](./docs/Reputation_Graph.md) |
| Knowledge Inheritance | [Knowledge Inheritance Framework](./docs/Knowledge_Inheritance_Framework.md) |
| AI Mentor | [AI Mentor Safety Model](./docs/AI_Mentor_Safety_Model.md) |
| Legacy | [Legacy Protocol](./docs/06-legacy-protocol.md) |

## Research Roadmap

| Phase | Focus | Expected Output | Status |
|---|---|---|---|
| Phase 1 | Conceptual foundation | Core vision, problem framing, canonical architecture, architecture map, memory object model, memory object schema, lifecycle model, lifecycle state machine, archive model, evidence quality framework, and protocol memory definition | In progress |
| Phase 2 | Contribution and attestation model | Proof of Contribution, attestation logic, attestation protocol specification, evidence categories, and anti-farming safeguards | In progress |
| Phase 3 | Governance memory | Governance context, decision records, dispute history, and retrospective review structures | In progress |
| Phase 4 | Knowledge inheritance and AI mentor research | Knowledge transmission, AI-assisted retrieval, source-linked summaries, safety boundaries, and uncertainty handling | In progress |
| Phase 5 | Chronicle network design | Multi-ecosystem archive structure, access patterns, contributor interfaces, and research APIs | Planned |
| Phase 6 | Specification and prototype research | Formal data models, privacy controls, validation flows, and possible implementation prototypes | Future research |

## Research Status

| Area | Current State | Next Research Need |
|---|---|---|
| Canonical Architecture | Drafted as source of truth | Keep aligned with all future architecture documents |
| Protocol Memory Layer | Drafted | Align conceptual layer with memory object, lifecycle, archive, and evidence quality models |
| Memory Object Model | Refined foundational model | Formalize object identity, validation rules, and future schema constraints |
| Memory Object Schema | Drafted as specification candidate | Refine type-specific schemas, validation test cases, and serialization format |
| Memory Lifecycle | Drafted | Refine transition rules, review gates, and archival criteria |
| Lifecycle State Machine | Drafted as specification candidate | Refine transition permissions, reviewer thresholds, and implementation test cases |
| Chronicle Archive | Archive model drafted | Refine preservation modes, redaction rules, archival integrity requirements, and link-rot handling |
| Evidence Quality Framework | Drafted | Refine evidence levels by object type and reviewer role |
| Proof of Contribution | Drafted as focused sub-proposal | Align verification model with Chronicle memory-layer requirements |
| Attestation Model | Drafted | Expand reviewer roles, dispute processes, and abuse resistance |
| Attestation Protocol | Drafted as specification candidate | Refine quorum rules, dispute thresholds, reviewer independence, and validation test cases |
| Attestation Authority | Drafted | Align reviewer authority with attestation, reputation, and inheritance models |
| Governance Context | Drafted | Add more governance memory scenarios |
| Decision Record Template | Drafted and sample-tested | Add more sample decision records over time |
| Related Work | Drafted | Expand comparison with additional academic and open-source systems |
| Threat Model | Drafted | Refine mitigations into future protocol requirements |
| Concept FAQ | Drafted | Keep updated as architecture terms evolve |
| Contributor Reputation | Reputation graph drafted | Refine graph relationships, privacy boundaries, and dispute-sensitive interpretation |
| Knowledge Inheritance | Refined architecture model | Add concrete lineage examples and inheritance review criteria |
| AI Mentor Layer | Safety model drafted | Add retrieval policy examples and source-citation response patterns |
| Legacy Protocol | Drafted | Clarify long-term memory without permanent hierarchy |
| Chronicle Network | Drafted | Expand network-level architecture and access model |
| Future Research | Drafted | Prioritize open questions for specification work |

## Repository Structure

```text
chronicle-legacy-protocol/
|
|-- README.md
|-- CONTRIBUTING.md
|
|-- docs/
|   |-- Concept_FAQ.md
|   |-- Canonical_Architecture_Specification.md
|   |-- Architecture_Diagram.md
|   |-- Protocol_Memory_Layer.md
|   |-- Memory_Object_Model.md
|   |-- Memory_Object_Schema.md
|   |-- Memory_Lifecycle.md
|   |-- Lifecycle_State_Machine.md
|   |-- Chronicle_Archive_Model.md
|   |-- Evidence_Quality_Framework.md
|   |-- Knowledge_Inheritance_Framework.md
|   |-- Reputation_Graph.md
|   |-- AI_Mentor_Safety_Model.md
|   |-- Attestation_Model.md
|   |-- Attestation_Protocol_Specification.md
|   |-- Attestation_Authority_Model.md
|   |-- Governance_Context.md
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

- [Concept FAQ](./docs/Concept_FAQ.md)
- [Canonical Architecture Specification](./docs/Canonical_Architecture_Specification.md)
- [Architecture Diagram](./docs/Architecture_Diagram.md)
- [Protocol Memory Layer](./docs/Protocol_Memory_Layer.md)
- [Memory Object Model](./docs/Memory_Object_Model.md)
- [Memory Object Schema](./docs/Memory_Object_Schema.md)
- [Memory Lifecycle](./docs/Memory_Lifecycle.md)
- [Lifecycle State Machine](./docs/Lifecycle_State_Machine.md)
- [Chronicle Archive Model](./docs/Chronicle_Archive_Model.md)
- [Evidence Quality Framework](./docs/Evidence_Quality_Framework.md)
- [Knowledge Inheritance Framework](./docs/Knowledge_Inheritance_Framework.md)
- [Reputation Graph](./docs/Reputation_Graph.md)
- [AI Mentor Safety Model](./docs/AI_Mentor_Safety_Model.md)
- [Attestation Model](./docs/Attestation_Model.md)
- [Attestation Protocol Specification](./docs/Attestation_Protocol_Specification.md)
- [Attestation Authority Model](./docs/Attestation_Authority_Model.md)
- [Governance Context](./docs/Governance_Context.md)
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
