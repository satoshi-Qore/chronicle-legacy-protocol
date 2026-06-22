# Memory Object Schema

**Status:** Draft - Protocol Specification Candidate  
**Scope:** Chronicle / Legacy Protocol Memory Object structure  
**Stage:** Concept and architecture research  
**Purpose:** Define the canonical schema fields, validation expectations, object types, and versioning rules for Memory Objects

## 1. Purpose

This document defines a draft schema for Memory Objects within Chronicle / Legacy Protocol.

The [Memory Object Model](./Memory_Object_Model.md) explains what a Memory Object is and why it matters. This document translates that model into a more structured specification candidate: required fields, optional fields, field types, validation expectations, lifecycle requirements, relationship fields, and example object records.

This document does not define a production database schema, smart contract format, API standard, or final serialization format. It defines the conceptual data structure that future specifications may refine into implementation-ready formats.

## 2. Relationship to Canonical Architecture

The Memory Object sits at the center of the canonical Chronicle flow:

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

A Memory Object is the structured record that Chronicle remembers. It is not the original contribution and it is not the contribution submission. It is formed after a contribution has been submitted with actor context, evidence, and reviewable scope.

The canonical architecture is defined in [Canonical Architecture Specification](./Canonical_Architecture_Specification.md). Lifecycle behavior is defined in [Lifecycle State Machine](./Lifecycle_State_Machine.md).

## 3. Canonical Definition

A **Memory Object** is a structured and verifiable memory record for a contribution, decision, knowledge artifact, governance event, or mentorship interaction that has identifiable evidence and contextual relevance.

A Memory Object must be able to answer six basic questions:

1. What is being remembered?
2. Who or what is associated with it?
3. Which submission or source context introduced it?
4. What evidence supports it?
5. What state is it in?
6. How does it relate to other memory records?

## 4. Schema Design Principles

The schema should follow these principles:

- preserve identity and submission context before Memory Object interpretation;
- preserve evidence before reputation;
- preserve privacy and disclosure boundaries before broad retrieval;
- preserve context before interpretation;
- support review without assuming truth;
- support dispute and revision without deleting history;
- separate required fields from type-specific fields;
- avoid universal scoring fields;
- support privacy and redaction from the beginning;
- remain portable across repositories, archives, applications, and future protocol implementations.

## 5. Field Requirement Levels

Fields are grouped into four requirement levels.

| Level | Meaning |
|---|---|
| Required | Needed for every valid Memory Object |
| Required when applicable | Needed when the object type, lifecycle state, or privacy context requires it |
| Optional | Useful but not required for all objects |
| Future research | Not part of the base schema yet; requires further study |

## 6. Required Core Fields

Every submitted Memory Object should contain the following fields.

| Field | Type | Description | Validation Expectation |
|---|---|---|---|
| `object_id` | string | Stable unique identifier for the Memory Object | Must be unique within its namespace |
| `schema_version` | string | Version of the Memory Object schema used by the record | Must reference a known schema version |
| `object_type` | enum | Type of memory record | Must match an accepted object type |
| `submission_ref` | string or object | Reference to the contribution submission or intake context that produced the candidate Memory Object | Should reference a submission record or explain why no submission record exists |
| `title` | string | Short human-readable title | Must be clear and non-empty |
| `description` | string | Summary of what the object records | Must describe the claim or memory purpose |
| `contributor_refs` | array | Contributors, groups, maintainers, reviewers, or participants associated with the record | May contain pseudonymous, organizational, or role-based references |
| `evidence_refs` | array | Evidence sources supporting the record | Must include at least one evidence reference or an explicit missing-evidence note |
| `created_at` | timestamp | Time the Memory Object was created | Must use a consistent timestamp format |
| `lifecycle_state` | enum | Current state of the Memory Object | Must match the Lifecycle State Machine |
| `context_tags` | array | Tags describing domain, topic, language, repository, role, or ecosystem area | Should use normalized tags where possible |
| `related_objects` | array | References to other Memory Objects or relationship records | May be empty at creation but should be present as a field |

## 7. Required When Applicable Fields

These fields are required only under specific conditions.

| Field | Type | Required When | Description |
|---|---|---|---|
| `identity_refs` | array | Object depends on contributor, reviewer, mentor, or actor continuity | References scoped identity or pseudonymous actor records |
| `attestation_refs` | array | Object has been reviewed, accepted, verified, disputed, or rejected | References scoped attestations or review outcomes |
| `attestation_scope` | array | Object has any attestation | Defines what was actually reviewed or confirmed |
| `attestation_authority_refs` | array | Object review depends on domain-scoped reviewer authority | References authority context without embedding numeric authority scores |
| `evidence_quality` | enum or object | Object has entered `observed`, `reviewed`, `accepted`, or `verified` states | Describes evidence confidence and limitations |
| `review_notes` | array | Object has entered review or dispute states | Human-readable review comments, limitations, or assumptions |
| `dispute_refs` | array | Object is disputed or was previously disputed | Links to dispute records or challenge explanations |
| `revision_history` | array | Object has been revised, corrected, redacted, deprecated, or superseded | Preserves change history |
| `privacy_level` | enum | Object contains sensitive, personal, private, or operational material | Defines visibility boundary |
| `disclosure_notes` | array or object | Object has public, limited, restricted, redacted, or consent-dependent material | Defines what may be shown, inherited, archived, or retrieved |
| `redaction_status` | enum | Any field or evidence source has been redacted | Indicates redaction state and reason where appropriate |
| `archive_refs` | array | Object has been preserved in Chronicle Archive or external archive context | Links to archive entries or preservation metadata |
| `superseded_by` | array | Object has been deprecated or replaced | References newer Memory Objects or guidance |
| `lineage_refs` | array | Object is inherited, extends another object, or contributes to a knowledge chain | Defines inheritance or knowledge lineage relationships |

## 8. Optional Fields

Optional fields may improve interpretation, retrieval, and future analysis.

| Field | Type | Description |
|---|---|---|
| `source_type` | enum | Primary source, secondary source, archive, summary, retrospective, or external publication |
| `validity_scope` | string or object | Scope in which the object should be interpreted |
| `domain_scope` | array | Domain categories such as documentation, governance, infrastructure, education, localization, security, research, or mentorship |
| `language` | string | Language code or language label for the object or source |
| `repository_refs` | array | Related repositories, issues, pull requests, commits, or release references |
| `governance_refs` | array | Related governance proposals, decisions, votes, or discussion records |
| `confidence_notes` | string | Human-readable uncertainty notes |
| `retrieval_notes` | string | Notes for AI mentor or search retrieval behavior |
| `duplicate_of` | string or array | Indicates whether the object duplicates another Memory Object |
| `external_refs` | array | External articles, reports, publications, or platform links |

## 9. Future Research Fields

The following fields should not be treated as part of the base schema yet.

| Field | Reason for Caution |
|---|---|
| `reputation_weight` | Risks creating speculative scoring or reward-like interpretation |
| `authority_score` | Belongs to future Attestation Authority research, not base Memory Object schema |
| `impact_score` | Difficult to define without bias, gaming, or over-quantification |
| `reward_value` | Outside Chronicle's current research scope |
| `token_reference` | Outside current non-token architecture |
| `automated_truth_score` | Conflicts with evidence-aware and dispute-aware design principles |

Chronicle may later define derived signals from Memory Objects, but those signals should not be embedded as universal base fields.

## 10. Object Types

The `object_type` field should use a controlled vocabulary.

| Object Type | Description |
|---|---|
| `contribution_record` | Records a meaningful contribution such as code, documentation, support, localization, or research |
| `evidence_record` | Records source evidence or metadata connected to another Memory Object |
| `governance_record` | Records governance proposal context, discussion, decision, or retrospective |
| `decision_record` | Records a decision, rationale, alternatives, trade-offs, and later review context |
| `knowledge_artifact` | Records a guide, tutorial, research note, glossary, educational resource, or explanation |
| `mentorship_record` | Records mentorship, onboarding, handoff, or learning support where privacy allows |
| `infrastructure_record` | Records operational knowledge, node operation context, monitoring notes, or incident lessons |
| `attestation_record` | Records a structured review statement or attestation context |
| `dispute_record` | Records a challenge, disagreement, correction request, or contested interpretation |
| `archive_record` | Records preservation metadata, source availability, or archival context |
| `lineage_record` | Records inheritance, extension, reference, supersession, or knowledge evolution relationships |
| `retrospective_record` | Records later analysis of an earlier contribution, decision, incident, or knowledge object |

Future specifications may add object types, but new types should not duplicate existing categories.

## 11. Controlled Vocabularies

### 11.1 Lifecycle States

The `lifecycle_state` field should follow [Lifecycle State Machine](./Lifecycle_State_Machine.md):

```text
draft
submitted
observed
reviewed
needs_revision
accepted
verified
disputed
revised
deprecated
rejected
archived
inherited
```

### 11.2 Evidence Quality Values

Evidence quality should align with the [Evidence Quality Framework](./Evidence_Quality_Framework.md):

```text
missing
weak
basic
contextual
accepted
verified
```

### 11.3 Privacy Levels

Privacy levels should align with the [Privacy and Disclosure Framework](./Privacy_and_Disclosure_Framework.md):

```text
public
limited
redacted
restricted
private
consent_required
```

### 11.4 Redaction Status

Suggested redaction states:

```text
none
partial
full
restricted_reference
pending_review
```

### 11.5 Attestation Scope Values

Suggested attestation scopes:

```text
authorship
existence
accuracy
usefulness
technical_relevance
governance_relevance
educational_value
historical_context
translation_quality
infrastructure_relevance
research_relevance
privacy_review
```

## 12. Relationship Schema

The `related_objects` and `lineage_refs` fields should use explicit relationship types.

| Relationship | Meaning |
|---|---|
| `identified_as` | An actor is represented by a scoped identity or pseudonymous reference |
| `submitted_by` | A submission or Memory Object was submitted by a contributor or participant |
| `submitted_as` | A contribution entered Chronicle as a contribution submission |
| `forms_candidate_object` | A reviewed submission may become a candidate Memory Object |
| `supported_by` | A submission or Memory Object is supported by evidence |
| `disclosure_limited_by` | A submission, Memory Object, evidence source, or archive entry has privacy, redaction, or consent constraints |
| `references` | Object cites another object as context |
| `inherits_from` | Object receives knowledge or context from an earlier object |
| `extends` | Object expands or improves an earlier object |
| `supersedes` | Object replaces earlier guidance or interpretation |
| `duplicate_of` | Object duplicates another object |
| `disputes` | Object challenges another object |
| `corrects` | Object corrects another object |
| `attests_to` | Object provides an attestation for another object |
| `archived_as` | Object is preserved by an archive record |
| `contributes_to_reputation_context` | Object informs domain-specific reputation interpretation |
| `retrieved_by` | An AI mentor or interface retrieved a Memory Object as source context |
| `originated_in` | A Memory Object or reference identifies its source Chronicle Domain |

Each relationship should ideally include:

- target object identifier;
- relationship type;
- timestamp;
- actor or process that created the relationship;
- optional explanation;
- lifecycle state of the relationship if contested.

## 13. Minimal Object Shape

The following pseudo-JSON shows a minimal valid Memory Object shape.

```json
{
  "object_id": "chronicle:example:memory-object-001",
  "schema_version": "0.1-draft",
  "object_type": "contribution_record",
  "submission_ref": {
    "submission_id": "submission-001",
    "submitted_by": "example-contributor"
  },
  "title": "Example Documentation Contribution",
  "description": "A structured record describing a documentation contribution and its supporting evidence.",
  "contributor_refs": [
    {
      "contributor_id": "example-contributor",
      "role": "author",
      "identity_type": "pseudonymous"
    }
  ],
  "evidence_refs": [
    {
      "evidence_id": "evidence-001",
      "source_type": "repository_pull_request",
      "uri": "https://example.org/pull/1",
      "description": "Pull request containing the documented change."
    }
  ],
  "created_at": "2026-06-21T00:00:00Z",
  "lifecycle_state": "submitted",
  "context_tags": ["documentation", "onboarding", "example"],
  "related_objects": []
}
```

## 14. Expanded Object Shape

The following example shows a richer object after review and archival context.

```json
{
  "object_id": "chronicle:qorechain:lightnode-guide-tr-001",
  "schema_version": "0.1-draft",
  "object_type": "knowledge_artifact",
  "submission_ref": {
    "submission_id": "chronicle:qorechain:submission-lightnode-guide-tr-001",
    "submitted_by": "satoshi-qore"
  },
  "title": "Turkish Light Node Setup Guide",
  "description": "A Turkish-language guide explaining light node setup concepts, operator notes, and common troubleshooting context.",
  "contributor_refs": [
    {
      "contributor_id": "satoshi-qore",
      "role": "author",
      "identity_type": "pseudonymous"
    }
  ],
  "evidence_refs": [
    {
      "evidence_id": "evidence-001",
      "source_type": "repository_file",
      "uri": "https://github.com/example/repo/blob/main/tr/light-node-guide.md",
      "description": "Guide source file."
    },
    {
      "evidence_id": "evidence-002",
      "source_type": "commit",
      "uri": "https://github.com/example/repo/commit/example",
      "description": "Commit adding or updating the guide."
    }
  ],
  "evidence_quality": "contextual",
  "created_at": "2026-06-21T00:00:00Z",
  "lifecycle_state": "accepted",
  "attestation_refs": [
    {
      "attestation_id": "attestation-001",
      "attestor_id": "example-reviewer",
      "attestation_scope": ["educational_value", "translation_quality"],
      "status": "accepted",
      "review_note": "Accepted as useful Turkish onboarding material within documentation scope."
    }
  ],
  "privacy_level": "public",
  "disclosure_notes": {
    "visibility": "public",
    "redaction_required": false
  },
  "redaction_status": "none",
  "context_tags": ["documentation", "turkish", "light-node", "onboarding"],
  "domain_scope": ["documentation", "education", "localization", "infrastructure"],
  "language": "tr",
  "archive_refs": [
    {
      "archive_id": "archive-001",
      "status": "preserved"
    }
  ],
  "related_objects": [
    {
      "target_object_id": "chronicle:qorechain:operator-onboarding-001",
      "relationship_type": "references",
      "description": "The guide supports later operator onboarding material."
    }
  ],
  "revision_history": [
    {
      "revision_id": "revision-001",
      "timestamp": "2026-06-21T00:00:00Z",
      "reason": "Initial accepted version."
    }
  ]
}
```

## 15. Validation Rules

A future validator should check at least the following rules.

### 15.1 Required Field Validation

A submitted Memory Object must include:

- `object_id`;
- `schema_version`;
- `object_type`;
- `submission_ref`;
- `title`;
- `description`;
- `contributor_refs`;
- `evidence_refs`;
- `created_at`;
- `lifecycle_state`;
- `context_tags`;
- `related_objects`.

### 15.2 Lifecycle Validation

The `lifecycle_state` must match the state machine.

A Memory Object should not move to `accepted`, `verified`, `disputed`, `revised`, `deprecated`, `rejected`, `archived`, or `inherited` without transition history.

### 15.3 Evidence Validation

Evidence references should include:

- evidence identifier;
- source type;
- URI, archive reference, or missing-evidence explanation;
- short description;
- privacy or redaction note when relevant.

### 15.4 Attestation Validation

If a Memory Object has `accepted` or `verified` lifecycle state, it should include either:

- attestation reference;
- reviewer note;
- governance process reference;
- maintainer acceptance reference;
- or another documented review mechanism.

### 15.5 Privacy Validation

If evidence includes private, sensitive, operational, or personally identifying material, the object should include:

- `privacy_level`;
- `disclosure_notes`;
- `redaction_status`;
- access or disclosure note;
- explanation of what is hidden or restricted where possible.

### 15.6 Relationship Validation

Relationship fields should not be ambiguous. A link should specify whether it references, inherits from, extends, disputes, corrects, supersedes, contributes to reputation context, or duplicates another object.

## 16. State-Dependent Field Requirements

| Lifecycle State | Additional Field Expectations |
|---|---|
| `draft` | Minimum draft fields may be incomplete; no reputation use |
| `submitted` | Required core fields and submission reference should be present |
| `observed` | Evidence source must be inspectable or explicitly marked unavailable |
| `reviewed` | Review notes, reviewer references, or attestation scope should be present |
| `needs_revision` | Revision request or missing requirement should be recorded |
| `accepted` | Scope-limited acceptance or attestation reference should be present |
| `verified` | Strong evidence and review references should be present |
| `disputed` | Dispute reference and disputed field or claim should be present |
| `revised` | Revision history should be present |
| `deprecated` | Supersession or deprecation reason should be present |
| `rejected` | Rejection reason should be present |
| `archived` | Archive reference or archival rationale should be present |
| `inherited` | Lineage relationship should be present |

## 17. Versioning Rules

Memory Objects should preserve history rather than overwrite it.

Versioning should follow these principles:

- corrections should create revision entries;
- major reinterpretations may create successor objects;
- deprecated records should point to replacements;
- disputed records should preserve the dispute trail;
- redactions should preserve that redaction occurred, where safe;
- schema changes should update `schema_version` without erasing old records.

A future specification should define whether Memory Objects use immutable versions, mutable records with revision history, or a hybrid model.

## 18. Portability Considerations

The schema should remain portable across:

- GitHub repositories;
- governance forums;
- archive systems;
- AI retrieval systems;
- decentralized identity tools;
- attestation frameworks;
- future protocol implementations.

For portability, the schema should avoid platform-specific assumptions where possible. Platform-specific links should be stored as evidence references, not as core identity assumptions.

## 19. Security and Abuse Considerations

Schema design should help reduce abuse.

| Abuse Risk | Schema Safeguard |
|---|---|
| Fake contribution | Requires submission context, evidence references, and lifecycle state |
| Duplicate claim | Supports `duplicate_of` and relationship validation |
| Reputation farming | Avoids embedded reputation score fields |
| Collusive attestation | Separates attestation references from evidence quality |
| Privacy leakage | Includes privacy, disclosure, and redaction fields |
| Link rot | Supports archive references and evidence status |
| Historical rewriting | Requires revision history and transition metadata |
| AI overconfidence | Supports lifecycle, evidence quality, disclosure context, and retrieval notes |

## 20. Open Specification Questions

1. Should `object_id` be namespace-based, content-derived, protocol-assigned, or hybrid?
2. Which fields should be required for each object type?
3. Should schema validation be strict or allow incomplete draft objects?
4. How should private evidence be referenced without exposing sensitive material?
5. Should lifecycle transitions be stored inside the Memory Object or as separate transition records?
6. Should attestations be embedded, linked, or represented as separate Memory Objects?
7. How should multilingual records be connected across languages?
8. How should duplicate records be merged without losing audit history?
9. Should archived records remain mutable through revision entries?
10. What serialization format is most appropriate for future prototypes?

## 21. Summary

The Memory Object Schema defines the structural foundation required for Chronicle to move from concept architecture toward protocol specification.

It clarifies what every Memory Object should contain, how submission context and evidence support object formation, which fields are state-dependent, how privacy and disclosure constraints should be represented, how relationships should be represented, and which fields should remain outside the base schema to avoid premature scoring or reward logic.

Future work should refine this draft into stricter type-specific schemas, validation test cases, privacy controls, and implementation-ready serialization formats.
