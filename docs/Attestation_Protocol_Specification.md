# Attestation Protocol Specification

**Status:** Draft - Protocol Specification Candidate  
**Scope:** Chronicle / Legacy Protocol attestation workflow  
**Stage:** Concept and architecture research  
**Purpose:** Define how Memory Objects are reviewed, attested, disputed, revised, accepted, verified, or rejected

## 1. Purpose

The Attestation Protocol Specification defines the review workflow that connects Memory Objects, evidence, reviewers, attestation authority, lifecycle states, and archival outcomes.

This document translates the broader [Attestation Model](./Attestation_Model.md) into a protocol-oriented workflow. It does not define production implementation code, final governance rules, token incentives, or reward mechanics. Its purpose is to describe how a structured contribution memory record can move through review in a way that is evidence-aware, privacy-aware, accountable, dispute-capable, and suitable for long-term protocol memory.

## 2. Relationship to the Canonical Architecture

The attestation protocol sits inside the canonical Chronicle flow:

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

The protocol operates on [Memory Objects](./Memory_Object_Model.md), not directly on raw social activity, informal claims, or standalone contributions. A Memory Object may reference contribution submission context, evidence, contextual metadata, disclosure boundaries, related records, and lifecycle state. The attestation protocol determines how reviewers evaluate that object and what state transition may follow.

Related documents define adjacent boundaries:

| Document | Relationship |
|---|---|
| [Identity and Pseudonymity Model](./Identity_and_Pseudonymity_Model.md) | Defines contributor, reviewer, and pseudonymous actor continuity |
| [Contribution Submission Protocol](./Contribution_Submission_Protocol.md) | Defines how a contribution enters Chronicle before Memory Object formation |
| [Memory Object Schema](./Memory_Object_Schema.md) | Defines the data structure that attestation records reference |
| [Evidence Quality Framework](./Evidence_Quality_Framework.md) | Defines how evidence strength and uncertainty should be interpreted |
| [Privacy and Disclosure Framework](./Privacy_and_Disclosure_Framework.md) | Defines disclosure, redaction, consent, and restricted evidence boundaries |
| [Attestation Model](./Attestation_Model.md) | Defines the conceptual role of attestation |
| [Attestation Authority Model](./Attestation_Authority_Model.md) | Defines who may attest, under what scope, and with what accountability |
| [Lifecycle State Machine](./Lifecycle_State_Machine.md) | Defines valid state transitions resulting from review outcomes |
| [Reputation Graph](./Reputation_Graph.md) | Interprets accepted, disputed, or verified records as contextual reputation relationships |

## 3. Canonical Definition

An attestation is a structured, scoped, evidence-aware review statement about a Memory Object.

It is not a like, badge, endorsement, reward claim, social signal, or universal truth claim. It is a review record that states what was examined, by whom, under which scope, with what evidence, under which disclosure limits, and with what limitations.

## 4. Design Principles

| Principle | Meaning |
|---|---|
| Evidence-aware | Attestations should reference evidence and its limitations |
| Scope-limited | A reviewer should attest only within a declared domain or review scope |
| Accountable | Attestations should remain traceable to reviewer identity or review role |
| Dispute-capable | Accepted records should remain open to challenge when new evidence appears |
| Privacy-aware | Private or sensitive evidence should not be unnecessarily exposed |
| Non-speculative | Attestations should avoid unsupported claims about impact, rewards, or future value |
| Lifecycle-linked | Attestation outcomes should map to explicit Memory Object lifecycle transitions |
| Human-centered | Automated checks may assist review but should not replace human judgment in early research stages |

## 5. Attestation Inputs

An attestation workflow begins only when a Memory Object has enough structure to be reviewed.

| Input | Description | Required |
|---|---|---|
| `object_id` | Identifier of the target Memory Object | Yes |
| `submission_ref` | Reference to the contribution submission or intake context | Yes, unless unavailable with explanation |
| `object_type` | Type of record being reviewed, such as documentation, governance, research, or infrastructure | Yes |
| `evidence_refs` | Links or references supporting the Memory Object | Yes |
| `contributor_refs` | Contributor or author references associated with the object | Yes |
| `lifecycle_state` | Current lifecycle state of the Memory Object | Yes |
| `context_tags` | Domain, ecosystem, language, or topic tags | Recommended |
| `related_objects` | Linked Memory Objects that provide context or lineage | Recommended |
| `privacy_level` | Disclosure status of evidence or reviewer notes | Recommended |
| `disclosure_notes` | Explanation of redacted, restricted, or consent-dependent material | Recommended when relevant |
| `evidence_quality` | Existing evidence quality assessment, if available | Optional |

If the required inputs are absent, the object should remain in `draft`, `submitted`, or `needs_revision` rather than advancing to formal attestation.

## 6. Attestation Actors

| Actor | Role |
|---|---|
| Submitter | Creates or submits the Memory Object for review |
| Contributor | Person or group associated with the contribution being recorded |
| Reviewer | Evaluates the Memory Object within a defined scope |
| Attestor | Issues a structured attestation record |
| Domain Reviewer | Reviews within a specific area such as documentation, infrastructure, governance, research, or localization |
| Maintainer | Reviews repository, protocol, or project-level context when relevant |
| Governance Reviewer | Reviews governance-related records and decision context |
| Disputer | Challenges an existing attestation, disclosure decision, or Memory Object state |
| Archivist | Helps preserve accepted or verified records in long-term memory structures |
| Automated Checker | Provides supporting checks only, such as link availability or format validation |
| AI Mentor | May retrieve or explain attested records, but should not issue attestations |

## 7. Attestation Scopes

Attestations should be scoped. A reviewer may confirm one property of a Memory Object without confirming every possible interpretation of that object.

Suggested scope vocabulary:

| Scope | Meaning |
|---|---|
| `authorship` | Evidence supports the claimed contributor relationship |
| `existence` | The referenced contribution, event, or artifact exists |
| `accuracy` | The Memory Object describes the evidence accurately |
| `technical_relevance` | The object is relevant to a technical system, repository, or infrastructure process |
| `governance_relevance` | The object is relevant to governance context or decision history |
| `educational_value` | The object supports onboarding, learning, or knowledge transfer |
| `translation_quality` | The localized content is understandable and faithful to source context |
| `research_relevance` | The object contributes to research framing, comparison, or analysis |
| `historical_context` | The object preserves useful ecosystem memory or decision background |
| `privacy_review` | The object avoids exposing unnecessary private or sensitive information |

A single Memory Object may receive multiple attestations with different scopes.

## 8. Attestation Workflow

### 8.1 Submission and Object Intake

A Memory Object enters review from `submitted`, `observed`, or `needs_revision`. The reviewer first checks whether the object contains enough required fields, submission context, and evidence references to be reviewed.

### 8.2 Evidence Observation

The reviewer examines the cited evidence and records whether it is available, relevant, stale, incomplete, inaccessible, private, redacted, or contradictory.

### 8.3 Privacy and Disclosure Check

Before review conclusions are recorded, the reviewer checks whether the Memory Object, evidence, or reviewer notes include sensitive, restricted, personal, operational, or consent-dependent material.

### 8.4 Review Assignment

A reviewer or review group is selected based on domain relevance, independence, and authority scope. The selection process should avoid obvious conflicts of interest where possible.

### 8.5 Scope Declaration

The reviewer declares the scope of review before issuing a decision. A documentation reviewer, for example, may attest to educational value without attesting to protocol correctness.

### 8.6 Review Assessment

The reviewer evaluates the Memory Object against evidence quality, authorship, usefulness, originality, durability, privacy, disclosure boundaries, and scope accuracy.

### 8.7 Decision Output

The reviewer issues a structured decision. The decision may accept, verify, reject, dispute, or request revision of the Memory Object.

### 8.8 Lifecycle Transition

The decision maps to a valid lifecycle transition defined in the [Lifecycle State Machine](./Lifecycle_State_Machine.md).

### 8.9 Record Preservation

The attestation record is linked back to the Memory Object and preserved as part of the Protocol Memory Layer. Later archive and reputation interpretation should preserve the attestation scope and lifecycle state.

## 9. Decision Outcomes

| Decision | Meaning | Typical Lifecycle Effect |
|---|---|---|
| `accept_for_review` | The object is reviewable and can enter formal review | `observed -> reviewed` |
| `accept` | The record is sufficiently supported for inclusion as accepted memory | `reviewed -> accepted` |
| `verify` | The record has stronger review confidence and evidence support | `accepted -> verified` |
| `partial_accept` | Some scopes are accepted while others remain limited or unresolved | `reviewed -> accepted` or `needs_revision` |
| `request_revision` | The record may be valid but requires clarification, evidence, or correction | `reviewed -> needs_revision` |
| `dispute` | A reviewer or participant challenges the record or prior attestation | `accepted -> disputed` or `verified -> disputed` |
| `reject` | The record lacks sufficient evidence, relevance, or integrity | `reviewed -> rejected` |
| `archive_without_acceptance` | The record is preserved for history but should not be treated as accepted memory | `submitted -> archived` or `rejected -> archived` |
| `deprecate` | The record was useful historically but is no longer current or primary | `verified -> deprecated` or `accepted -> deprecated` |

## 10. Review Criteria

A reviewer should consider the following criteria before issuing an attestation:

| Criterion | Review Question |
|---|---|
| Evidence quality | Is the evidence accessible, relevant, durable, and sufficient for the claimed scope? |
| Authorship | Does the record accurately represent the contributor relationship? |
| Submission context | Does the Memory Object reasonably follow from the contribution submission or intake record? |
| Scope accuracy | Does the Memory Object avoid overstating what the evidence proves? |
| Usefulness | Does the object preserve knowledge, context, contribution, or decision history? |
| Originality | Does the object represent meaningful work rather than duplicate or low-effort activity? |
| Durability | Is the record likely to remain useful beyond short-term activity? |
| Privacy safety | Does the object avoid unnecessary exposure of personal or sensitive information? |
| Disclosure clarity | Are redactions, restrictions, or consent-sensitive elements clearly marked? |
| Lineage relevance | Does the object connect properly to prior or future Memory Objects? |
| Abuse risk | Is there evidence of spam, collusion, manipulation, or reputation inflation? |

## 11. Required Attestation Record Fields

An attestation record should be structured enough to support auditability and future interpretation.

| Field | Description |
|---|---|
| `attestation_id` | Unique identifier for the attestation record |
| `target_object_id` | Memory Object being reviewed |
| `attestor_id` | Reviewer, reviewer group, or authority reference |
| `attestor_role` | Role or domain of the reviewer |
| `attestation_scope` | Scope being reviewed |
| `decision` | Review outcome |
| `rationale` | Short explanation of the decision |
| `evidence_reviewed` | Evidence references examined during review |
| `confidence_level` | Stated confidence level for the decision |
| `limitations` | Known uncertainty, scope limits, or unresolved concerns |
| `timestamp` | Time of attestation |
| `privacy_notes` | Notes about redacted or private evidence, if applicable |
| `disclosure_notes` | Notes about visibility, restricted material, or consent boundaries, if applicable |
| `dispute_window` | Optional period or condition under which dispute is expected |
| `related_transition` | Lifecycle transition produced by the attestation |

## 12. Confidence Levels

Confidence levels should describe review certainty, not contributor worth or reputation score.

| Level | Meaning |
|---|---|
| `insufficient` | Evidence does not support a meaningful attestation |
| `low` | Some evidence exists, but important uncertainty remains |
| `moderate` | Evidence supports the decision with ordinary limitations |
| `high` | Evidence is strong, consistent, and contextually clear |
| `verified` | Evidence and review depth support stronger protocol memory confidence |

Confidence levels should not be treated as automatic reputation weights. Their interpretation belongs to the Reputation Graph and should remain contextual.

## 13. Reviewer Authority Checks

Before an attestation is accepted as protocol memory, the reviewer authority should be checked against the claimed scope.

Minimum checks:

- The reviewer has a relevant domain or review role.
- The reviewer declares the review scope.
- The reviewer does not have an obvious conflict of interest.
- The reviewer provides a rationale tied to evidence.
- The reviewer considers privacy and disclosure boundaries.
- The reviewer does not claim authority beyond the reviewed scope.
- The attestation can be disputed or revisited if later evidence changes the context.

This document does not define final reviewer tiers, numeric authority scores, or governance selection rules. Those remain open research areas for the [Attestation Authority Model](./Attestation_Authority_Model.md).

## 14. Dispute and Appeal Flow

Disputes are part of the protocol memory process. A disputed record should not be automatically deleted. Instead, the dispute should become part of the historical context.

Suggested dispute flow:

```text
Accepted or Verified Memory Object
-> Dispute Submitted
-> Dispute Evidence Reviewed
-> Prior Attestation Reassessed
-> Outcome Recorded
-> Lifecycle State Updated
```

Possible dispute outcomes:

| Outcome | Effect |
|---|---|
| `dispute_rejected` | Existing attestation remains active |
| `revision_required` | Memory Object moves to `needs_revision` |
| `attestation_limited` | Prior attestation remains but with narrower scope |
| `attestation_revoked` | Prior attestation is no longer treated as valid |
| `object_deprecated` | Object remains historically visible but no longer primary |
| `object_rejected` | Object is rejected due to invalid evidence or abuse |

## 15. Privacy and Redaction

Attestation should support privacy-aware review. Some evidence may be sensitive, personal, private, or context-dependent.

Privacy considerations:

- Public attestations should avoid exposing private evidence unnecessarily.
- Redacted evidence should be marked as redacted rather than silently omitted.
- Reviewers should distinguish between unavailable evidence and intentionally private evidence.
- Sensitive contributor information should not be turned into permanent public metadata without consent.
- Privacy limitations should be preserved as part of the attestation record.
- Disclosure limits should affect archive, reputation, inheritance, and AI mentor interpretation.

## 16. Anti-Abuse Safeguards

The attestation protocol should reduce the risk of memory pollution, reputation farming, and historical manipulation.

Potential safeguards:

- Require evidence references for reviewable claims.
- Limit attestation scope to what evidence supports.
- Preserve disputes rather than hiding them.
- Detect duplicate or near-duplicate Memory Objects.
- Require stronger review for high-impact or governance-related records.
- Flag reviewer conflicts of interest.
- Treat automated checks as assistance, not final judgment.
- Avoid automatic reputation increases from unreviewed activity.
- Preserve uncertainty instead of forcing binary acceptance.

## 17. State Transition Mapping

Attestation decisions should map to lifecycle states in a predictable way.

| Current State | Decision | New State |
|---|---|---|
| `submitted` | `observe_evidence` | `observed` |
| `observed` | `accept_for_review` | `reviewed` |
| `reviewed` | `accept` | `accepted` |
| `reviewed` | `verify` | `verified` |
| `accepted` | `verify` | `verified` |
| `reviewed` | `request_revision` | `needs_revision` |
| `needs_revision` | `resubmit` | `submitted` |
| `accepted` | `dispute` | `disputed` |
| `verified` | `dispute` | `disputed` |
| `disputed` | `restore` | `accepted` or `verified` |
| `disputed` | `reject` | `rejected` |
| `accepted` | `deprecate` | `deprecated` |
| `verified` | `deprecate` | `deprecated` |
| `accepted` | `archive` | `archived` |
| `verified` | `archive` | `archived` |

These transitions should remain aligned with the [Lifecycle State Machine](./Lifecycle_State_Machine.md).

## 18. Non-Goals

This specification does not attempt to define:

- Token rewards.
- Airdrop eligibility.
- Universal contributor scores.
- Final governance voting rules.
- Automated truth determination.
- Production smart contract logic.
- Permanent hierarchy among contributors.
- A claim that all accepted records are equally important.

The purpose is narrower: define a review protocol for preserving structured, evidence-aware memory records.

## 19. Open Specification Questions

Future versions should investigate:

- How many reviewers are required for different object types?
- When should a single reviewer be sufficient?
- How should reviewer independence be measured?
- What minimum evidence is required by object type?
- How long should dispute windows remain open?
- How should private evidence be reviewed without exposing sensitive information?
- How should multilingual review and translation quality be handled?
- How should automated checks be used without creating false certainty?
- How should collusion between contributors and reviewers be detected?
- When should a rejected record remain archived for historical transparency?
- How should attestation records be versioned as the protocol evolves?

## 20. Summary

The Attestation Protocol Specification defines how Memory Objects move from claim to reviewed protocol memory. It connects submission context, evidence, reviewers, scoped decisions, authority checks, privacy and disclosure boundaries, lifecycle transitions, disputes, and archival continuity.

This document strengthens Chronicle by making attestation a structured protocol process rather than an informal approval concept. It remains a draft specification candidate and should be refined through future examples, test cases, threat analysis, and reviewer-model research.
