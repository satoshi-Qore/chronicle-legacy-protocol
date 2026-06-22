# ADR-0001: Memory Object as Canonical Protocol Primitive

**Status:** Accepted  
**Decision Date:** 2026-06-22  
**Deciders:** Chronicle Architecture Working Group  
**ADR Type:** Foundational — affects all subsequent architectural decisions  
**Supersedes:** None (first ADR)  
**Superseded by:** None

---

## Status

Accepted. This decision is foundational to Chronicle's architecture and is not expected to be revised except through a full foundational review under the Self-Governance framework. Any proposed revision requires an RCP (Rule Change Proposal) with Foundational scope.

---

## Decision Date

2026-06-22

This ADR is written at the conceptual architecture research stage. No Chronicle instance has been deployed. The decision reflects architectural reasoning developed across the core specification documents produced in the first phase of research.

---

## Context

Chronicle / Legacy Protocol is a research architecture for a Protocol Memory Layer. Its purpose is to preserve and make retrievable the contributions, governance decisions, knowledge artifacts, and institutional reasoning of decentralized ecosystems over time.

At the design stage, a fundamental question must be answered before any other architectural decision can be made: what is the canonical unit of the protocol?

A protocol's canonical primitive determines what everything else is built around. It determines:

- what gets persisted and how;
- what gets attested and by whom;
- what reputation is derived from;
- what knowledge inheritance connects;
- what an AI mentor retrieves and explains;
- what governance records track;
- what the archive preserves;
- what can be disputed, revised, deprecated, and superseded.

Without a clear canonical primitive, every subsequent design decision would require re-establishing first principles. Different layers of the protocol might use different primitives — contributors in one layer, events in another, hash references in another — producing an incoherent architecture that cannot be consistently evaluated, extended, or governed.

This decision establishes the canonical primitive and explains why it was chosen.

---

## Problem Statement

Chronicle must represent, preserve, and make retrievable the following categories of ecosystem activity:

1. Contribution records — what was built, proposed, reviewed, or submitted;
2. Evidence records — what supports or disputes a contribution's claims;
3. Attestation records — who reviewed what, to what scope, under what authority;
4. Governance records — what was decided, by whom, through what deliberation, with what dissenting positions;
5. Knowledge artifacts — what was documented, explained, or synthesized for the benefit of future participants;
6. Reputation signals — what reliability and expertise context does a contributor's history support;
7. Knowledge inheritance relationships — how does later work build on earlier work;
8. AI Mentor interactions — how does automated guidance retrieve and represent archived material.

The problem is that each of these categories could, in principle, be treated as a separate protocol primitive with its own structure, lifecycle, and access model. This would produce:

- an incoherent schema with no consistent unit of evaluation;
- siloed lifecycle models that cannot be compared or composed;
- inconsistent privacy and disclosure handling across record types;
- attestation schemes that apply differently to different record types;
- knowledge inheritance that cannot cross type boundaries;
- AI Mentor retrieval that cannot uniformly source its claims;
- governance records that cannot reference contribution records through a shared identifier model;
- reputation signals that cannot be traced to a unified evidentiary record.

The problem, stated precisely: what single structural unit should all categories of protocol memory instantiate, so that Chronicle can be a coherent, consistent, and composable protocol memory system?

---

## Decision

**Memory Objects are the canonical protocol primitive of Chronicle.**

Every significant unit of ecosystem activity that Chronicle preserves is represented as a Memory Object. A Memory Object is a structured, evidence-linked, lifecycle-managed record with a defined schema, a scoped attestation model, a disclosure level, and a set of optional inheritance relationships.

The following categories of activity are all represented as Memory Objects with specific `object_type` values:

| Category | Memory Object Type |
|---|---|
| Contribution record | `contribution_record` |
| Evidence record | `evidence_record` |
| Attestation record | `attestation_record` |
| Governance decision | `governance_record` |
| Architectural decision | `architectural_decision_record` |
| Rule change proposal | `rule_change_proposal` |
| Knowledge artifact | `knowledge_artifact` |
| Retrospective | `retrospective` |
| Dispute record | `dispute_record` |
| Mentorship record | `mentorship_record` |

All of these types share:

- a common core schema with 14+ defined fields;
- a common lifecycle model with 13 states and defined transitions;
- a common attestation model with scope declarations;
- a common disclosure framework with four levels;
- a common evidence reference model;
- a common inheritance relationship vocabulary;
- a common contributor reference model;
- a common context tag system.

This decision means: **nothing in Chronicle's architecture is canonical except through a Memory Object**. Contributions do not exist independently of Memory Objects. Reputation is not stored independently — it is interpreted from Memory Objects. Governance decisions are Memory Objects. Knowledge inheritance connects Memory Objects to other Memory Objects. The AI Mentor retrieves and explains Memory Objects. The Archive persists Memory Objects.

---

## Rationale

### 1. A single canonical primitive enables uniform lifecycle management

Protocol memory degrades over time. Evidence links decay. Context becomes ambiguous. Contributions are disputed, superseded, or deprecated. A canonical primitive that supports a formal lifecycle model allows all categories of memory to be managed, reviewed, and updated through a consistent process.

Without a shared primitive, lifecycle management must be designed separately for each record type — producing inconsistent rules for when a governance record is considered valid, when a contribution record is considered archived, and when a knowledge artifact is superseded.

The Memory Object's 13-state lifecycle model applies to all object types. This means: the same review, dispute, revision, archival, and deprecation processes apply to a contribution record, a governance record, a knowledge artifact, and an attestation record. The protocol does not need separate lifecycle reasoning for each category.

### 2. A single canonical primitive enables consistent attestation

Attestation — the process by which a reviewer asserts scope-limited confidence in a record — must be applicable across all record types for Chronicle to function. If contributions and governance records use different attestation models, then attestation authority cannot be consistently reasoned about across the archive.

The Memory Object's scoped attestation model applies uniformly: every Memory Object may be attested by a qualified reviewer, with explicit scope declarations and explicit limitations. An attestation applied to a `contribution_record` uses the same structural form as one applied to a `knowledge_artifact` or a `governance_record`.

### 3. A single canonical primitive enables unified privacy and disclosure handling

Chronicle's privacy model requires that every record have a defined disclosure level and that AI Mentor retrieval, cross-domain memory exchange, and reputation signal derivation all respect those disclosure levels. If different record types have different disclosure models, then privacy handling must be re-engineered for each type.

The Memory Object's four disclosure levels — `public`, `ecosystem_restricted`, `contributor_controlled`, `redacted` — apply uniformly across all object types. A `governance_record` that involves sensitive internal deliberation can be marked `contributor_controlled` using the same mechanism as a `contribution_record` that involves sensitive technical details.

### 4. A single canonical primitive enables traceable reputation

Chronicle's reputation model is explicitly non-additive: reputation signals are contextual, domain-scoped, and lifecycle-aware. They are derived from Archive records — not stored independently. This design requires that all reputation sources be represented through a consistent evidentiary unit.

If contributions use one primitive and governance participation uses another, then reputation interpretation must reason across two incompatible evidentiary forms. By representing all reputation-relevant activity as Memory Objects, reputation interpretation can uniformly query the Archive, apply lifecycle awareness (distinguishing disputed from verified records), and trace every signal to a specific stored record.

### 5. A single canonical primitive enables coherent knowledge inheritance

Knowledge inheritance requires that later work can formally declare intellectual dependency on earlier work through a structured relationship. This requires both the earlier work and the later work to be represented in a form that supports relationship declarations.

If knowledge artifacts use one primitive and contribution records use another, then inheritance relationships cannot coherently cross type boundaries. A `knowledge_artifact` that synthesizes prior `contribution_records` and `governance_records` must be able to express `inherits_from`, `extends`, and `references` relationships to records of all three types. This is only possible if all three types share a common primitive form.

### 6. A single canonical primitive enables uniform AI Mentor sourcing

Chronicle's AI Mentor must be able to cite specific Archive records as the source of its responses. Citation requires a stable, retrievable identifier for each cited record. If different record types use different identifier schemes, then AI Mentor citation becomes structurally inconsistent.

The Memory Object's `memory_object_id` field provides a stable, type-consistent identifier for all records. The AI Mentor can cite a `governance_record`, a `contribution_record`, and a `knowledge_artifact` in the same response, using the same citation format for all three.

### 7. A single canonical primitive enables cross-domain memory exchange

When memory moves across Chronicle Domain boundaries, it must carry its provenance, evidence, lifecycle state, and privacy constraints with it. This is only possible if memory is represented in a single, domain-portable form.

If different record types use different structural forms, then cross-domain exchange must implement separate portability rules for each type — multiplying complexity and creating inconsistency in how origin domain identity is preserved. The Memory Object's common schema means that a single portability protocol can handle all record types.

---

## Alternatives Considered

### Alternative 1: Contributor-centric architecture

**Description:** The canonical primitive is a Contributor Profile — a persistent record of a participant's identity, history, and attributes. All activity is stored as properties or sub-records of the contributor's profile.

**Why it was considered:** Many existing protocol reputation systems center on the contributor as the primary entity. Blockchain identity systems (ENS, DID, Lens Protocol) use on-chain or cryptographically-controlled identity primitives. This is familiar and has existing infrastructure.

**Why it was rejected:**

- **Conflates memory with identity.** A contributor profile answers "who is this person" — not "what happened, when, and why." Protocol memory requires the latter.
- **Privacy-hostile.** If all activity is attached to a persistent contributor identity, then privacy-preserving contribution (pseudonymous, restricted-disclosure, or anonymous) becomes structurally incompatible with the architecture. Chronicle's privacy model requires that memory records can exist without being attached to a disclosed identity.
- **Does not survive contributor departure.** When a contributor leaves an ecosystem, their contributions should remain discoverable and usable. A contributor-centric architecture makes it difficult to preserve and discover contributions independently of the contributor's continued presence and identity maintenance.
- **Cannot represent governance and knowledge artifacts coherently.** A governance decision is not a property of a specific contributor — it is a record of a collective process. A knowledge artifact is not a contributor attribute — it is a documented understanding that outlives its author.
- **Reputation becomes circular.** In a contributor-centric architecture, reputation is derived from the contributor profile, which is maintained by the contributor. This creates incentives for profile manipulation rather than genuine contribution quality.

**Conclusion:** Contributor-centric architecture makes Chronicle a reputation or identity system — not a protocol memory system. Rejected.

---

### Alternative 2: Reputation-centric architecture

**Description:** The canonical primitive is a Reputation Signal — a scored or weighted indicator of contributor or content reliability. All protocol activity is processed into reputation signals that aggregate over time.

**Why it was considered:** Reputation systems (SourceCred, Coordinape, on-chain governance reputation) are established patterns for capturing and expressing ecosystem value. They provide directly actionable signals for governance decisions and reviewer selection.

**Why it was rejected:**

- **Destroys the underlying record.** Reputation aggregation collapses the specific, contextual, evidence-linked history of contributions into a score or weight. Once aggregated, the original reasoning, disputes, and limitations are lost. Chronicle's core claim is that memory should be preserved and retrievable — aggregation defeats this.
- **Cannot represent governance decisions.** A governance decision is not a reputation signal — it is a record of deliberation, evidence, and outcome. A reputation-centric architecture has no natural place for governance records.
- **Cannot support AI Mentor sourcing.** An AI Mentor cannot cite a reputation score as a source. It can only cite the underlying records that the score was derived from. A reputation-centric architecture that suppresses the underlying records makes AI Mentor sourcing impossible.
- **Highly gameable.** Reputation signals optimized for aggregation become targets for metric gaming — a known failure mode in tokenized reputation systems. Chronicle's design principles explicitly require that evaluation must be honest before it is positive and that vanity metrics should be avoided.
- **Context-destroys lifecycle awareness.** A reputation score cannot capture the difference between a contribution that was accepted, a contribution that was later disputed, and a contribution that was deprecated. Lifecycle awareness — critical for Chronicle's model — is lost in aggregation.

**Conclusion:** Reputation-centric architecture makes Chronicle a scoring system — not a protocol memory system. The record is destroyed in service of the score. Rejected.

---

### Alternative 3: Archive-centric architecture

**Description:** The canonical primitive is an Archive Entry — a raw storage record of what occurred, without a defined schema, lifecycle model, or attestation process. The archive functions as an append-only log of ecosystem events.

**Why it was considered:** Append-only logs are well-established in distributed systems (event sourcing, blockchain transaction history, git commit history). They are simple, tamper-evident, and do not require upfront schema design.

**Why it was rejected:**

- **Lacks interpretability.** A raw archive entry records that something happened but not what it means, whether it has been reviewed, whether it is disputed, or whether it should be trusted. Protocol memory requires interpretation, not just storage.
- **Cannot support attestation.** An append-only log has no mechanism for reviewers to assert scope-limited confidence in specific entries. Without attestation, there is no way to distinguish carefully reviewed records from unreviewed ones.
- **Cannot support lifecycle management.** If every entry is permanent and append-only, then correction, dispute, revision, and deprecation require additional workaround conventions — introducing exactly the informal complexity that Chronicle's architecture is designed to avoid.
- **Cannot support privacy.** An append-only public log is structurally hostile to the disclosure levels Chronicle requires. Once an entry is appended, it cannot be redacted without compromising the integrity of the log.
- **Cannot support knowledge inheritance.** Inheritance relationships require structured declarations between records. A raw log entry cannot carry structured relationship metadata without becoming a Memory Object in all but name.

**Conclusion:** Archive-centric architecture provides storage without comprehension. It captures events but cannot make them interpretable, attestable, disputable, or inheritable. Rejected as a canonical primitive, though the Chronicle Archive is a critical infrastructure layer built on top of Memory Objects.

---

### Alternative 4: Governance-centric architecture

**Description:** The canonical primitive is a Governance Record — a formal record of protocol decisions, proposals, and deliberations. All other activity is documented as context for or consequence of governance decisions.

**Why it was considered:** Governance is the mechanism through which protocols evolve and self-correct. Making governance the center of the protocol memory system would ensure that institutional decision-making is the most carefully preserved category of activity.

**Why it was rejected:**

- **Excludes most ecosystem activity.** Most valuable protocol memory is not governance-related. Technical contributions, infrastructure work, documentation, mentorship, and knowledge synthesis all contribute to ecosystem continuity but are not governance decisions.
- **Cannot represent knowledge inheritance.** The evolution of ideas across contributors and time — documented through knowledge inheritance relationships — does not fit naturally into a governance record structure.
- **Overweights formal process relative to informal contribution.** Many critical contributions to ecosystems are informal, exploratory, and not connected to governance proposals. A governance-centric architecture would systematically undervalue these contributions.
- **Creates path dependency on governance participation.** In a governance-centric architecture, contributors who do not participate formally in governance have no canonical representation. This creates perverse incentives and excludes important contributors from protocol memory.

**Conclusion:** Governance-centric architecture makes Chronicle a governance log — not a protocol memory system. Rejected as a canonical primitive, though governance records are a critically important Memory Object type.

---

## Consequences

### Structural consequences

**All Chronicle layers must be designed around Memory Objects.** The Attestation Protocol, Chronicle Archive, Reputation Graph, Knowledge Inheritance Framework, AI Mentor Layer, Chronicle Self-Governance model, and Chronicle Network all use Memory Objects as their fundamental unit. No layer may introduce a competing canonical primitive.

**The Memory Object schema is a first-class protocol specification.** Changes to the core Memory Object schema require a Foundational-scope governance review. Field additions that maintain backward compatibility may be processed as Additions; field removals or semantic changes require Revisions or Foundational review.

**Memory Object types define the typology of protocol memory.** Adding a new object type is an architectural decision that must be recorded in an ADR. Object types should be defined conservatively; proliferation of types without clear differentiation should be avoided.

**The lifecycle state machine is a first-class protocol specification.** The 13 lifecycle states and their allowed transitions apply uniformly to all object types. Lifecycle exceptions for specific object types require ADR justification.

### Operational consequences

**Ecosystem participants must create Memory Objects to participate in Chronicle.** Contributions that are not documented as Memory Objects are not part of the protocol memory. This creates an incentive for documentation but also creates a burden on contributors.

**Attesters must review Memory Objects, not contributor claims.** Attestation is record-scoped, not contributor-scoped. An attester reviewing a `contribution_record` is asserting scope-limited confidence in that specific record — not in the contributor's general reliability.

**Reputation interpretation requires Archive access.** Because reputation signals are derived from Memory Objects rather than stored independently, any system that interprets reputation must have read access to the relevant Memory Objects. Systems without Archive access cannot interpret Chronicle reputation.

**AI Mentor responses must be source-linked to Memory Objects.** The AI Mentor cannot make a claim without citing the specific Memory Objects that support it. This is a strong constraint on AI Mentor behavior and requires that the Archive be comprehensive enough to support the full range of expected queries.

---

## Benefits

**Consistency.** A single canonical primitive means that every Chronicle layer uses the same structural vocabulary. Developers, researchers, governance participants, and contributors learn one model rather than several.

**Composability.** Because every record type shares the same core schema, they can be combined, compared, and referenced through uniform mechanisms. A knowledge artifact can reference a contribution record, a governance record, and an evidence record through the same relationship model.

**Evaluability.** Chronicle's evaluation framework can assess Memory Object quality, discoverability, lifecycle accuracy, and evidence durability using a single set of methods applied uniformly across all record types.

**Extensibility.** New object types can be added without changing the core architecture. An `impact_record` type or a `collaboration_record` type could be introduced as extensions of the Memory Object schema without requiring architectural revision.

**Portability.** The Chronicle Network's cross-domain memory exchange can use a single portability protocol for all record types, because all records share the same structural form.

**Falsifiability.** Chronicle's core claim — that a protocol memory layer improves ecosystem memory — can be evaluated by studying Memory Object coverage, quality, and discoverability. The single canonical primitive makes the evaluation target clear.

---

## Risks

**Schema rigidity.** A canonical schema shared across all object types is a coordination point that resists change. As Chronicle's understanding of protocol memory matures, the core schema may need revision — and those revisions will affect all object types simultaneously.

**Object type proliferation.** The decision to make all record categories Memory Objects creates pressure to add new object types for every category of ecosystem activity. Without discipline, the typology becomes unwieldy.

**Mandatory documentation burden.** Requiring that contributions be represented as Memory Objects places a documentation burden on contributors. Ecosystems where documentation culture is weak may find that Chronicle's canonical primitive creates friction rather than value.

**Attestation bottleneck.** If all object types require attestation to advance through the lifecycle, then the attestation capacity of the ecosystem constrains the throughput of the archive. Object types that are high-volume but low-complexity may create attestation queue problems.

**Reputation gaming via Memory Object creation.** If reputation signals are derived from Memory Objects, then contributors may be incentivized to create many low-quality Memory Objects to increase their archive presence. Mitigation requires that reputation interpretation be quality-weighted, not volume-weighted.

---

## Relationship to Existing Documents

| Document | Relationship |
|---|---|
| `Memory_Object_Model.md` | Defines the Memory Object concept, its purpose, and its role in the protocol. This ADR records the architectural decision that makes the Memory Object the canonical primitive. |
| `Memory_Object_Schema.md` | Specifies the 14+ core fields, object type vocabulary, field validation rules, and evidence reference model. The schema is the technical expression of the decision recorded here. |
| `Lifecycle_State_Machine.md` | Defines the 13 lifecycle states and 38 allowed transitions that apply uniformly to all Memory Object types. The lifecycle model's uniformity is a consequence of the canonical primitive decision. |
| `Attestation_Protocol_Specification.md` | Defines the scoped attestation model. The uniformity of attestation across object types is a direct consequence of all object types being Memory Objects. |
| `Chronicle_Archive_Model.md` | Defines the persistence and retrieval layer. The Archive's architecture is built around Memory Objects as its unit of storage. |
| `Reputation_Graph.md` | Defines how reputation signals are derived from Archive records. Reputation's traceability to specific Memory Objects is a direct consequence of the canonical primitive decision. |
| `Knowledge_Inheritance_Framework.md` | Defines how later Memory Objects formally reference and build upon earlier ones. The inheritance model's ability to cross object type boundaries — a `knowledge_artifact` citing a `contribution_record` citing a `governance_record` — is a direct consequence of the shared canonical primitive. |

---

## Future Implications

**ADR-0002 and subsequent ADRs will build on this foundation.** All subsequent architectural decisions should reference ADR-0001 when they depend on the Memory Object canonical primitive. ADRs that propose exceptions to or limitations on the canonical primitive should explicitly engage with the rationale recorded here.

**The Self-Governance framework inherits this decision.** Chronicle's ADR and RCP system — itself documented as Memory Objects — is built on the canonical primitive defined here. Governance records that record the evolution of Chronicle's own architecture are Memory Objects, which means the protocol's self-governance is itself an instance of the canonical primitive in action.

**Cross-domain interoperability depends on this decision's stability.** The Chronicle Network's interoperability conventions assume that all Chronicle Domains use Memory Objects as their canonical primitive. A domain that adopted a competing primitive model would not be compatible with the Chronicle Network's exchange protocols.

**The whitepaper's empirical claims require this decision.** Chronicle's whitepaper will claim that a Memory Object-centric protocol memory layer improves ecosystem knowledge continuity, contribution discoverability, and governance quality. These claims are only coherent if Memory Objects are in fact the canonical unit of what is being measured and preserved.

**AI Mentor architecture is constrained by this decision.** Future AI Mentor specifications must design their retrieval and citation systems around Memory Objects as the atomic unit of sourcing. Architectural proposals that require the AI Mentor to synthesize information without Memory Object citations are inconsistent with this decision.

---

## Open Questions

1. **Object type governance:** Who has authority to propose new Memory Object types, and what review process should new types require? Should new types require ADR-level deliberation, or can they be added through a lighter-weight RCP process?

2. **Backward compatibility obligations:** When the core Memory Object schema is revised, what obligations does Chronicle have to maintain backward compatibility for existing archived records? Is there a minimum support window for each schema version?

3. **Object type deprecation:** Can an existing object type be deprecated? If a `mentorship_record` type were later found to be redundant with `knowledge_artifact`, what process would govern its deprecation and the migration of existing records?

4. **Minimum viable Memory Object:** What is the minimum set of fields that a Memory Object must populate to be considered valid for archival? Is a Memory Object with only `memory_object_id`, `object_type`, `created_at`, and `summary` a valid archived record, or does the archive require more complete field population?

5. **Cross-type attestation:** Can a single attestation record attest to multiple Memory Objects simultaneously, or is attestation always one-to-one? If batch attestation is permitted, what are the integrity implications?

6. **Memory Object merging:** If two partially-overlapping Memory Objects are discovered that represent the same contribution event, is there a protocol for merging them? What identity and provenance rules govern merged records?

7. **AI-generated Memory Objects:** If an AI system generates a Memory Object (e.g., to capture the structure of a governance discussion), what attestation and disclosure requirements apply? Is human review always required before archival?

8. **Relationship between Memory Objects and on-chain records:** If Chronicle records are eventually anchored to a blockchain or content-addressed storage system, how should the on-chain record relate to the Memory Object schema? Does the on-chain record supersede the Memory Object, or is it an evidence reference to it?

---

## Decision Summary

**Memory Objects are the canonical protocol primitive of Chronicle.** This decision was made because:

1. A single canonical primitive is required for consistency across all Chronicle layers — attestation, lifecycle, disclosure, reputation, knowledge inheritance, AI Mentor sourcing, and cross-domain exchange.

2. The alternatives — contributor-centric, reputation-centric, archive-centric, and governance-centric architectures — each fail to represent one or more critical categories of protocol memory without significant architectural compromise.

3. The Memory Object's combination of structured schema, uniform lifecycle management, scoped attestation, disclosure levels, evidence references, and inheritance relationships makes it the only candidate primitive that can coherently serve all categories of ecosystem activity Chronicle is designed to preserve.

4. Protocol memory is not the same as identity, reputation, storage, or governance. It is the structured, evidence-linked, lifecycle-managed record of what happened, why it happened, who was responsible, and what it means for future participants. The Memory Object is designed to capture exactly this — and nothing less.

This decision is foundational. All subsequent Chronicle architecture builds on it.

---

*Chronicle Legacy Protocol — Architectural Decision Record*  
*ADR-0001 — Accepted — 2026-06-22*
