# Contribution Submission Protocol

## Status

**Status:** Draft - Research Framework  
**Scope:** Chronicle / Legacy Protocol contribution intake and candidate Memory Object formation  
**Stage:** Concept and architecture research  
**Purpose:** Define how a contribution enters Chronicle and becomes eligible to be represented as a candidate Memory Object

## Purpose

The Contribution Submission Protocol defines how a contribution, event, decision, knowledge artifact, or mentorship interaction enters the Chronicle / Legacy Protocol research architecture.

This document closes the architectural gap between identity and evidence. It explains how an actor reference becomes associated with a submitted contribution, how initial evidence is collected, and how that submission may become a candidate Memory Object for later review, attestation, lifecycle tracking, archival preservation, reputation context, and knowledge inheritance.

Chronicle records contributions rather than rewards. A submission is therefore not a claim to payment, status, token allocation, or authority. It is a structured request to preserve a contribution or ecosystem event as protocol memory.

## Scope

This document applies to conceptual contribution intake across Chronicle's research architecture, including:

- documentation contributions;
- code or repository contributions;
- governance participation;
- infrastructure operation notes;
- research artifacts;
- educational resources;
- localization work;
- community support records;
- bug reports;
- decision records;
- mentorship interactions;
- archive candidates.

This document does not define production submission forms, blockchain transactions, smart contracts, identity wallets, token mechanics, reward eligibility, automated scoring, or deployed verification infrastructure.

## Design Principles

| Principle | Meaning |
|---|---|
| Memory before rewards | A submission exists to preserve contribution context, not to trigger incentives |
| Evidence at entry | Evidence quality begins at submission time because weak intake creates weak memory |
| Submission is not acceptance | A submitted contribution is only a candidate record until reviewed |
| Identity continuity without exposure | Submissions should reference contributors without requiring real-world identity disclosure by default |
| Context preservation | A submission should explain what happened, why it matters, and where supporting evidence exists |
| Privacy awareness | Sensitive evidence, identity links, and operational details should be handled through disclosure boundaries |
| Duplicate resistance | Repeated, copied, or overlapping submissions should be detected and contextualized |
| Dispute readiness | Submissions should support review, correction, rejection, dispute, and revision |
| Minimal viable structure | A submission should collect enough information for review without becoming a production data model |

## Contribution Submission Overview

A contribution submission is a structured entry describing a contribution or ecosystem event that may be worth preserving as protocol memory.

A submission may include:

- a `submission_id`;
- a `contributor_id` or actor reference;
- a title;
- a contribution type;
- a short description;
- an evidence package;
- timestamps or source dates;
- privacy and disclosure notes;
- related submissions or Memory Objects;
- initial context tags;
- review status;
- duplicate or dispute notes.

A submission is not the contribution itself. It is also not yet a Memory Object. It is the intake layer that prepares a contribution for structured memory formation.

The conceptual flow is:

```text
Identity
↓
Contribution Submission
↓
Evidence Collection
↓
Memory Object Creation
↓
Attestation
↓
Lifecycle
```

In this flow, identity provides actor continuity, submission provides initial context, evidence supports review, Memory Object creation structures the record, attestation evaluates the record, and lifecycle state tracks its status over time.

## Actors and Roles

| Actor | Role in Submission |
|---|---|
| Contributor | Performs or is associated with the original contribution |
| Submitter | Creates the submission record; may or may not be the original contributor |
| Reviewer | Reviews completeness, evidence, scope, duplication, and privacy boundaries |
| Attestor | Issues a structured attestation after Memory Object formation where appropriate |
| Archivist | Helps preserve source context, redaction notes, and historical availability |
| Disputer | Challenges attribution, evidence, scope, duplication, or interpretation |
| Maintainer or Domain Reviewer | Provides domain-specific review where relevant |
| AI Mentor Interface | May later retrieve accepted records but should not approve submissions |

Actor roles may overlap, but Chronicle should distinguish them conceptually. The person who submits a contribution record is not always the person who created the original contribution.

## Submission Lifecycle

A submission may pass through the following conceptual stages:

```text
Draft -> Submitted -> Intake Reviewed -> Evidence Checked -> Candidate Memory Object -> Accepted for Attestation
```

Alternative outcomes may include:

- incomplete;
- needs clarification;
- duplicate;
- disputed;
- rejected;
- withdrawn;
- privacy-restricted;
- merged with related submission;
- deferred for later review.

| Stage | Meaning |
|---|---|
| Draft | Submission is being prepared but has not entered review |
| Submitted | Submission has been provided for intake review |
| Intake Reviewed | Basic structure, actor references, scope, and evidence presence have been checked |
| Evidence Checked | Evidence package has been reviewed for availability, relevance, and limitations |
| Candidate Memory Object | Submission has enough structure to be transformed into a candidate Memory Object |
| Accepted for Attestation | Candidate Memory Object is ready for scoped attestation or further lifecycle review |
| Incomplete | Submission lacks required context or evidence |
| Duplicate | Submission overlaps materially with an existing submission or Memory Object |
| Disputed | Attribution, scope, evidence, or interpretation has been challenged |
| Rejected | Submission does not meet minimum criteria for memory formation |
| Withdrawn | Submitter or contributor requests withdrawal before further processing, subject to archival and privacy rules |

Submission lifecycle is not the same as Memory Object lifecycle. Submission lifecycle governs intake. Memory Object lifecycle governs structured protocol memory after object formation.

## Submission Requirements

A submission should include enough information to determine whether a candidate Memory Object can reasonably exist.

Minimum conceptual requirements include:

| Field | Purpose |
|---|---|
| `submission_id` | Stable reference for the submitted intake record |
| `submitted_by` | Actor reference for the submitter |
| `contributor_id` | Actor reference for the contributor where known |
| `contribution_type` | Category such as documentation, code, governance, research, infrastructure, education, localization, support, or mentorship |
| `title` | Human-readable summary |
| `description` | Explanation of what happened and why it may be relevant |
| `evidence_package` | Set of links, artifacts, notes, screenshots, or references supporting the submission |
| `source_date` | When the contribution or event occurred, if known |
| `submission_date` | When the submission was made |
| `privacy_notes` | Disclosure, consent, redaction, or sensitivity considerations |
| `related_records` | Links to related submissions, Memory Objects, issues, proposals, or documents |
| `initial_status` | Draft, submitted, incomplete, disputed, duplicate, or review-ready |

A submission that lacks evidence, actor reference, contribution type, or meaningful description may remain incomplete and should not become a Memory Object without clarification.

## Evidence Requirements

Evidence begins at submission time because the first evidence package shapes later review quality.

An evidence package may include:

- repository links;
- pull requests;
- issues;
- commits;
- documentation pages;
- governance posts;
- proposal records;
- forum discussions;
- archived links;
- screenshots with context;
- redacted logs;
- published research notes;
- maintainer or reviewer comments;
- educational resources;
- community support records.

Evidence requirements should consider:

| Requirement | Description |
|---|---|
| Availability | Evidence should be accessible or its access limits should be documented |
| Relevance | Evidence should relate directly to the submitted contribution |
| Context | Evidence should explain what the contribution was and why it matters |
| Durability | Evidence should resist link rot where possible through durable sources or archive references |
| Integrity | Evidence should avoid unsupported edits, cropped context, or misleading presentation |
| Privacy | Evidence should not expose sensitive information unnecessarily |
| Attribution | Evidence should support the claimed contributor relationship where possible |
| Limitations | Weak, partial, redacted, or disputed evidence should be labeled as such |

A submission can proceed with imperfect evidence, but weak evidence should limit confidence, review depth, attestation scope, and later reputation interpretation.

## Submission Review Process

Submission review is an intake process, not final attestation.

A reviewer may check:

1. Whether the submission has a clear contribution type.
2. Whether `submitted_by` and `contributor_id` are distinguishable where necessary.
3. Whether the description matches the evidence package.
4. Whether the evidence is accessible, relevant, and privacy-safe.
5. Whether the submission duplicates an existing record.
6. Whether attribution is disputed or unclear.
7. Whether the contribution should become a candidate Memory Object.
8. Whether more information is required.

Review outcomes may include:

| Outcome | Meaning |
|---|---|
| Ready for Memory Object | Submission has enough structure and evidence to become a candidate Memory Object |
| Needs clarification | Submission requires additional context, evidence, or privacy review |
| Duplicate | Submission overlaps with an existing submission or Memory Object |
| Disputed | Attribution, evidence, or interpretation is contested |
| Privacy restricted | Submission may proceed only with redaction or restricted disclosure |
| Rejected | Submission does not meet minimum requirements or is out of scope |

Submission review should remain conservative. It should not assign broad reputation, issue final truth claims, or imply future rewards.

## Relationship to Memory Objects

A submission differs from a Memory Object.

| Submission | Memory Object |
|---|---|
| Intake record | Structured protocol memory record |
| May be incomplete | Should meet minimum object requirements |
| May contain unreviewed claims | Should include reviewable evidence and context |
| Used to decide whether memory should be formed | Used as the record Chronicle preserves, reviews, indexes, links, archives, and inherits |
| Can be rejected or merged before object formation | Can move through lifecycle states after formation |

A Memory Object should not exist until a submission has enough identity context, contribution description, evidence package, and privacy review to support structured memory.

A candidate Memory Object is an intermediate state. It indicates that the submission has enough structure to be transformed into protocol memory, but it may still require attestation, lifecycle review, and archive handling.

## Relationship to Evidence Quality

The [Evidence Quality Framework](./Evidence_Quality_Framework.md) begins influencing the process during submission.

Submission-time evidence quality affects:

- whether the submission is complete;
- whether review can proceed;
- what type of Memory Object may be formed;
- how much uncertainty should be attached;
- whether privacy review is required;
- whether attestation should be limited in scope;
- whether the record can later influence reputation context;
- whether the record can be safely retrieved by an AI mentor interface.

Evidence quality should not be converted directly into value, rank, reward, or authority. It describes confidence and limitations.

## Relationship to Attestation

The [Attestation Model](./Attestation_Model.md) and [Attestation Protocol Specification](./Attestation_Protocol_Specification.md) operate after a submission becomes a candidate Memory Object.

Submission review asks: "Is this contribution sufficiently described and evidenced to become a candidate Memory Object?"

Attestation asks: "What scoped statement can a reviewer make about the candidate Memory Object, its evidence, attribution, relevance, or interpretation?"

This separation matters because not every submission deserves attestation. Some submissions are incomplete, duplicate, disputed, private, out of scope, or too weakly evidenced.

## Relationship to Identity and Pseudonymity

The [Identity and Pseudonymity Model](./Identity_and_Pseudonymity_Model.md) defines actor references used during submission.

Submission may involve:

- a `submitted_by` actor;
- a `contributor_id` actor;
- a reviewer identity;
- a disputed attribution reference;
- a pseudonymous contributor;
- a contributor-declared cross-platform identity link;
- a privacy-restricted identity reference.

Chronicle should distinguish identity continuity from real-world identity verification. A submission may preserve contributor continuity without exposing a contributor's legal identity.

## Relationship to Privacy and Disclosure

The [Privacy and Disclosure Framework](./Privacy_and_Disclosure_Framework.md) applies at submission time.

Privacy review should consider:

- whether evidence contains personal information;
- whether operational logs expose sensitive infrastructure details;
- whether screenshots reveal private conversations;
- whether identity links require consent-aware handling;
- whether a submission should be public, restricted, or redacted;
- whether AI retrieval should later exclude or limit sensitive evidence.

Privacy should not be postponed until after archival. Once sensitive material enters a memory system, it may become difficult to remove or reinterpret.

## Submission Risks and Abuse Scenarios

| Risk | Description | Possible Mitigation Approach |
|---|---|---|
| False contribution claim | A submitter claims work they did not perform | Require attribution evidence and dispute handling |
| Evidence manipulation | Evidence is cropped, edited, incomplete, or misleading | Require source links, context, reviewer notes, and limitation labels |
| Spam submissions | Low-quality or repetitive submissions overload review | Minimum requirements, duplicate detection, and rate-sensitive review policies |
| Reputation farming | Submissions are created only to inflate visibility or status | Keep submission separate from reputation and require evidence-aware review |
| Privacy leakage | Evidence exposes personal, operational, or sensitive data | Redaction, disclosure levels, and consent-aware handling |
| Duplicate claims | Multiple submissions describe the same contribution | Duplicate detection and related-record linking |
| Identity impersonation | Submitter uses another contributor's identity or reviewer identity | Stable actor references, attribution evidence, and dispute process |
| Reviewer overload | Too many incomplete submissions make review difficult | Intake completeness checks and clarification outcomes |
| AI over-reliance | AI summaries are treated as primary evidence | Require source-linked evidence and human review boundaries |

## Duplicate Submission Considerations

Duplicate detection is important because protocol memory can become noisy if the same contribution is submitted repeatedly.

A duplicate may occur when:

- the same contributor submits the same artifact multiple times;
- different submitters submit the same contribution;
- a contribution overlaps with an existing Memory Object;
- a later tutorial repeats an earlier guide without adding new context;
- a screenshot-based submission duplicates a source-linked submission;
- a contribution is split into many small submissions to inflate activity.

Duplicate handling may include:

- marking the later submission as duplicate;
- linking related submissions;
- merging evidence packages;
- superseding weaker records with stronger source-linked records;
- preserving the duplicate as an abuse or dispute signal where relevant;
- requesting clarification when overlap is uncertain.

Duplicate does not always mean malicious. It may reflect fragmented platforms, contributor turnover, localization, or improved evidence. Reviewers should distinguish harmful duplication from legitimate extension or inheritance.

## Non-Goals

This document does not define:

- blockchain-specific transactions;
- smart contract submission flows;
- token mechanics;
- reward eligibility;
- airdrop or incentive rules;
- production APIs;
- authentication systems;
- legal identity verification;
- automated scoring;
- final governance authority;
- a deployed moderation system;
- implementation code.

The goal is to define the conceptual intake layer for protocol memory research.

## Open Research Questions

1. What minimum fields should be required before a submission can become a candidate Memory Object?
2. How should Chronicle distinguish submitter identity from contributor identity?
3. What evidence package is sufficient for different contribution types?
4. How should incomplete submissions be preserved, rejected, or revised?
5. When should duplicate submissions be merged, linked, superseded, or rejected?
6. How should privacy-restricted evidence be reviewed without overexposure?
7. What review threshold is needed before submission becomes candidate Memory Object?
8. How should disputed submissions affect later lifecycle states?
9. How should submission review remain useful without becoming centralized gatekeeping?
10. How should AI-assisted tools help organize submissions without becoming evidence or attestation sources?
11. How can submission spam be reduced while preserving open participation?
12. How should submission metadata support future archive, reputation, and knowledge inheritance layers?

## Summary

The Contribution Submission Protocol defines the intake layer between identity and evidence.

It clarifies that a contribution is not automatically protocol memory. A contribution must first be submitted with actor context, evidence, privacy awareness, and reviewable scope. Only then can it become a candidate Memory Object for attestation, lifecycle tracking, archival preservation, reputation interpretation, and knowledge inheritance.

This keeps Chronicle focused on durable contribution memory rather than reward farming, activity counting, or unsupported reputation claims.
