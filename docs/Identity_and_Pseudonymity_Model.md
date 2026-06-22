# Identity and Pseudonymity Model

**Status:** Draft - Research Framework  
**Scope:** Chronicle / Legacy Protocol contributor, reviewer, mentor, and actor identity representation  
**Stage:** Concept and architecture research  
**Purpose:** Define how actors are represented within Chronicle while preserving privacy, portability, pseudonymity, and long-term reputation continuity

## 1. Purpose

The Identity and Pseudonymity Model defines how Chronicle / Legacy Protocol should represent contributors, reviewers, mentors, archivists, governance participants, and other actors without requiring real-world identity verification by default.

Protocol memory depends on continuity. If contribution records, attestations, disputes, reviews, and knowledge lineage cannot be connected to stable actor references, then reputation context and historical continuity become difficult to interpret. At the same time, decentralized ecosystems often rely on pseudonymous participation, and a protocol memory system should not assume that every contributor must reveal a legal name or real-world identity.

This document defines identity as a continuity and attribution problem, not as a real-world identity verification product.

## 2. Scope

This model applies to identity references used across Chronicle's research architecture:

- contributor records;
- reviewer and attestor records;
- Memory Objects;
- evidence references;
- reputation graph relationships;
- knowledge inheritance paths;
- governance context;
- mentorship records;
- archive entries;
- AI mentor retrieval and explanation boundaries.

This document is conceptual. It does not define wallet-based identity, decentralized identifiers, credentials, account recovery systems, KYC, legal identity, biometric identity, or production authentication infrastructure.

## 3. Design Principles

| Principle | Meaning |
|---|---|
| Identity continuity over identity exposure | Chronicle should preserve stable contribution context without requiring unnecessary disclosure of real-world identity |
| Pseudonymity by default | Contributors should be able to participate through durable pseudonymous references |
| Contextual identity | Identity references should be interpreted within specific ecosystems, domains, and contribution histories |
| Portability | Actor references should be able to move across repositories, archives, and ecosystems without depending on one platform |
| Privacy-aware linking | Linking multiple accounts, pseudonyms, or ecosystems should require caution and consent-aware handling |
| Separation from authority | Identity continuity does not automatically grant reviewer authority or reputation |
| Dispute-aware attribution | Actor references should support correction, dispute, and revision when attribution is contested |
| Minimal disclosure | The model should preserve only the identity information needed for memory, review, attribution, and continuity |

## 4. Identity in Chronicle

Chronicle identifies protocol memory actors, not real-world persons by default.

Chronicle may identify:

- that a contribution was associated with a `contributor_id`;
- that a review was issued by a `reviewer_id`;
- that an attestation was created under a declared scope;
- that a Memory Object was submitted by a specific pseudonymous actor;
- that multiple Memory Objects are connected to the same actor reference;
- that a contributor has continuity across a domain, repository, ecosystem, or research context;
- that an actor's role is contributor, reviewer, attestor, archivist, mentor, governance participant, or learner.

Chronicle does not identify by default:

- legal name;
- government identity;
- biometric identity;
- physical location;
- private contact information;
- real-world employer or affiliation;
- wallet ownership as a universal identity truth;
- hidden links between pseudonyms;
- personal identity behind a pseudonymous contributor.

The purpose is to preserve contribution continuity and review accountability, not to expose private identity.

## 5. Pseudonymity vs Real-World Identity

Pseudonymity allows a contributor to build durable history without revealing their real-world identity. A pseudonymous contributor may still have stable contribution history, domain-specific reputation, accepted Memory Objects, reviewer history, and knowledge lineage.

Real-world identity verification asks a different question: whether a pseudonym maps to a legal or physical person. Chronicle does not require that question to be answered for most protocol memory functions.

| Concept | Chronicle Interpretation |
|---|---|
| Pseudonymous contributor | A stable actor reference associated with contribution history, without requiring legal identity |
| Real-world identity | Legal, personal, or externally verified identity outside the base Chronicle model |
| Identity continuity | Ability to link records over time to the same actor reference |
| Identity verification | External process for proving who someone is in the real world; not a default Chronicle requirement |
| Identity disclosure | Revealing additional identity information; should be consent-aware and purpose-limited |

Identity continuity is necessary for protocol memory. Real-world identity verification is not always necessary and may create privacy risk.

## 6. Contributor Identity Model

A contributor identity reference represents the actor associated with a contribution, Memory Object, knowledge artifact, governance input, documentation update, infrastructure note, or mentorship interaction.

Example conceptual field:

```text
contributor_id: pseudonymous or role-based actor reference
```

A contributor record may include:

| Field | Purpose |
|---|---|
| `contributor_id` | Stable reference for the contributor within a namespace |
| `identity_type` | Pseudonymous, organizational, role-based, public personal, or unknown |
| `display_name` | Human-readable name where safe and appropriate |
| `ecosystem_scope` | Ecosystem, repository, project, or community where the identity is used |
| `domain_context` | Contribution areas such as documentation, governance, infrastructure, research, education, or localization |
| `evidence_refs` | Public or restricted evidence linking the actor to contributions |
| `privacy_level` | Disclosure boundary for identity-related information |
| `continuity_refs` | Optional links to related identities, accounts, or ecosystem contexts |
| `dispute_status` | Whether attribution or identity linkage is contested |

A contributor identity reference does not need to prove legal identity. It needs to preserve enough continuity for attribution, review, lineage, and contextual reputation.

## 7. Reviewer Identity Model

Reviewer identity requires additional accountability because reviewers may affect attestation, lifecycle state, evidence interpretation, and reputation context.

Example conceptual field:

```text
reviewer_id: scoped reviewer or attestor reference
```

A reviewer record may include:

| Field | Purpose |
|---|---|
| `reviewer_id` | Stable reference for the reviewer or attestor |
| `reviewer_role` | Maintainer, domain reviewer, governance reviewer, community reviewer, archivist, or other role |
| `authority_scope` | Area where the reviewer is allowed or expected to review |
| `attestation_history` | Prior attestations or review actions |
| `domain_context` | Reviewer expertise or review domain |
| `conflict_notes` | Known conflict or limitation notes where relevant |
| `privacy_level` | Disclosure boundary for reviewer identity or notes |
| `dispute_status` | Whether review authority, scope, or behavior is contested |

Reviewer identity should be more accountable than general contributor identity, but it still does not require real-world identity by default. A pseudonymous reviewer can be accountable through consistent review history, scoped authority, dispute records, and attestation quality.

## 8. Identity Continuity

Identity continuity means that Chronicle can recognize a stable actor reference across multiple records over time.

Continuity matters because:

- contribution history requires attribution;
- reviewer history requires accountability;
- reputation context depends on repeated evidence-linked activity;
- knowledge inheritance may need to preserve original contributor context;
- disputes may need to refer to prior behavior;
- AI mentor systems need to avoid treating disconnected records as identical or unrelated without evidence.

Identity continuity is not the same as identity exposure. Chronicle may preserve that `contributor_id: satoshi-qore` created multiple public research documents without needing to know the contributor's legal identity.

Continuity should be interpreted through declared scope and available evidence.

## 9. Identity Portability Across Ecosystems

Chronicle aims to study protocol memory across decentralized ecosystems, not only within one repository or platform. Therefore, identity references should be portable where possible.

Multi-ecosystem identity continuity may involve:

- the same pseudonym used across multiple repositories;
- linked public profiles;
- contributor-declared cross-links;
- organization-level references;
- role-based identities within different communities;
- ecosystem-specific contributor IDs;
- restricted or consent-based links between identities.

Portability should remain cautious. A shared username across platforms is not always proof of shared identity. Linking identities across ecosystems may create privacy and safety risks.

A future model may distinguish:

| Portability Type | Meaning |
|---|---|
| `self_declared` | Contributor declares that two identities are connected |
| `publicly_linked` | Public profiles link to one another |
| `evidence_supported` | Repository, governance, or archive evidence supports continuity |
| `reviewer_confirmed` | A reviewer confirms continuity within a limited scope |
| `restricted_link` | Link exists but should not be public |
| `unverified_similarity` | Similar names or patterns exist but should not be treated as identity continuity |

## 10. Relationship to Memory Objects

Memory Objects should reference actors through stable identity fields without requiring unnecessary personal information.

Relevant Memory Object fields may include:

- `contributor_refs`;
- `reviewer_refs`;
- `attestation_refs`;
- `submitted_by`;
- `reviewed_by`;
- `attested_by`;
- `disputed_by`;
- `privacy_level`;
- `redaction_status`.

A Memory Object should distinguish between:

- the contributor who created the original artifact;
- the submitter who created the Memory Object;
- the reviewer who evaluated it;
- the attestor who issued a scoped statement;
- the archivist who preserved it;
- the mentor or AI interface that later retrieved it.

These roles may overlap, but they should not be collapsed automatically.

## 11. Relationship to Reputation

The [Reputation Graph](./Reputation_Graph.md) depends on identity continuity, but it should not require real-world identity disclosure.

Reputation in Chronicle should attach to contextual actor references, not to exposed personal identity.

Important rules:

- a `contributor_id` can accumulate domain-specific reputation without revealing legal identity;
- a `reviewer_id` can build review accountability through attestation history;
- reputation should remain contextual and non-transferable;
- linking multiple identities may change reputation interpretation and should be consent-aware;
- disputed attribution should weaken or qualify reputation signals;
- privacy-restricted identity links should not become public reputation shortcuts.

Identity continuity gives reputation memory. It should not become invasive identity surveillance.

## 12. Relationship to Attestation

The [Attestation Protocol Specification](./Attestation_Protocol_Specification.md) requires reviewer and attestor references. Attestations should identify who or what issued the review statement within a defined scope.

Identity-related attestation questions include:

- Who submitted the Memory Object?
- Who reviewed the evidence?
- Who issued the attestation?
- Is the reviewer operating within a declared authority scope?
- Is there a conflict of interest?
- Is the attribution to the contributor disputed?
- Is identity evidence public, restricted, or redacted?

Attestation can confirm attribution within a scope, but it should not automatically reveal real-world identity.

## 13. Relationship to Privacy and Disclosure

The [Privacy and Disclosure Framework](./Privacy_and_Disclosure_Framework.md) defines how identity-related information should be exposed, restricted, redacted, or consent-limited.

Identity data is often sensitive because it can connect records across time, ecosystems, roles, and social contexts.

Privacy-aware identity handling should:

- minimize unnecessary identity disclosure;
- avoid linking pseudonyms without evidence and consent-sensitive review;
- distinguish public identity references from restricted identity references;
- preserve redaction status for sensitive identity links;
- avoid exposing personal details through AI mentor retrieval;
- allow contributor safety to shape disclosure decisions.

Identity continuity should support memory. It should not force unwanted deanonymization.

## 14. Identity Risks and Threats

| Risk | Description | Possible Safeguard |
|---|---|---|
| Deanonymization | Pseudonymous contributor is linked to real-world identity without consent | Minimize identity fields and restrict sensitive links |
| False attribution | A contribution is assigned to the wrong actor | Require evidence and dispute handling |
| Identity fragmentation | Same contributor appears as unrelated actors across records | Support cautious self-declared or evidence-supported continuity |
| Identity over-linking | Separate pseudonyms are incorrectly merged | Treat similarity as insufficient evidence |
| Reviewer impersonation | Actor claims reviewer identity or authority they do not hold | Require stable reviewer references and attestation history |
| Reputation transfer abuse | Actor tries to move reputation from one identity to another without evidence | Keep reputation contextual and non-transferable |
| Privacy leakage | Identity metadata reveals personal or operational context | Use disclosure levels, redaction, and consent-aware handling |
| AI identity inference | AI mentor infers identity links from patterns rather than evidence | Restrict inference and require source-linked identity claims |

## 15. Sybil Considerations

Sybil resistance is relevant to Chronicle, but Chronicle should not confuse Sybil resistance with real-world identity verification.

A Sybil attack occurs when one actor controls multiple identities to simulate many independent contributors, reviewers, or governance participants. This can distort contribution memory, attestation independence, and reputation context.

Possible Sybil-aware design approaches:

- require stronger evidence for high-impact Memory Objects;
- track repeated attestation clusters;
- separate identity count from contribution quality;
- avoid raw account-number metrics;
- use domain-specific reviewer history;
- preserve conflict-of-interest and relationship notes;
- require independent review for sensitive or high-impact records;
- support pseudonymity while limiting reputation inflation from unreviewed activity.

Chronicle should allow pseudonymous participation while making artificial identity multiplication less useful for reputation manipulation.

## 16. Non-Goals

This model does not define:

- legal identity verification;
- KYC or compliance systems;
- biometric identity;
- government identity documents;
- wallet-based identity as a universal requirement;
- decentralized identifier implementation details;
- credential issuance protocols;
- identity recovery mechanisms;
- production authentication or authorization systems;
- token mechanics;
- reward eligibility rules;
- a deployed identity product.

The goal is to define research-stage identity representation for protocol memory.

## 17. Open Research Questions

1. What minimum identity information is required for a valid Memory Object?
2. How should Chronicle distinguish contributor, submitter, reviewer, attestor, archivist, and mentor identities?
3. How should pseudonymous contributors maintain continuity across ecosystems without exposing private identity?
4. When should identity links between platforms be public, restricted, or rejected?
5. What evidence is sufficient to connect two pseudonymous identities?
6. How should disputed attribution affect lifecycle state and reputation context?
7. How should reviewer identity be accountable without requiring legal identity disclosure?
8. What Sybil-resistance methods preserve pseudonymity while reducing manipulation?
9. How should AI mentor systems handle identity questions without making unsupported inferences?
10. What privacy controls are needed for identity-related archive entries?
11. Can identity continuity be portable without becoming surveillance?
12. How should contributors withdraw, redact, or limit identity links while preserving historical integrity?

## 18. Summary

The Identity and Pseudonymity Model defines how Chronicle can preserve actor continuity without requiring real-world identity exposure.

Chronicle identifies contribution actors, reviewer roles, attestation sources, and historical relationships. It does not identify legal persons by default. This distinction is essential: protocol memory requires continuity, attribution, accountability, and reputation context, but those goals can often be supported through stable pseudonymous references rather than real-world identity verification.

A mature Chronicle identity model should support privacy, portability, pseudonymity, dispute handling, and long-term reputation continuity without becoming an identity surveillance system.
