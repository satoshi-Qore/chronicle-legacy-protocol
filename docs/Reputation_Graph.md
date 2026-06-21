# Reputation Graph

## Overview

The Reputation Graph defines how Chronicle / Legacy Protocol can represent contributor reputation as contextual relationships between contributions, Memory Objects, attestations, reviewers, domains, disputes, and inherited knowledge.

This document is conceptual and architecture-focused. It does not define a token, market asset, universal score, ranking system, or production database schema. Its purpose is to clarify how reputation can be derived from evidence-aware memory without reducing contributors to a single number.

## 1. Purpose

Decentralized ecosystems often remember visible activity more easily than meaningful contribution. A contributor may be recognized for social presence, seniority, or repeated participation, while less visible work such as documentation, infrastructure support, research, localization, or governance context may be forgotten.

A Reputation Graph helps address this problem by preserving the relationships that explain how reputation was formed.

The purpose of the Reputation Graph is to:

- connect reputation to evidence-backed contribution history;
- preserve domain-specific contributor context;
- prevent reputation from becoming a universal score;
- distinguish accepted, disputed, deprecated, and inherited records;
- support knowledge inheritance without creating permanent hierarchy;
- provide AI mentor systems with source-linked context rather than authority shortcuts;
- make reputation reviewable, correctable, and explainable over time.

## 2. Definition

A **Reputation Graph** is a contextual relationship layer built from Memory Objects, attestations, contribution records, reviewer actions, evidence quality, lifecycle states, and domain-specific interpretation.

It is not the contributor's identity. It is not a transferable credential. It is not a leaderboard. It is a graph of relationships that helps future participants understand where a contributor has provided meaningful, reviewed, or historically relevant work.

In Chronicle terms:

```text
Contribution -> Memory Object -> Attestation -> Contextual Reputation Signal
```

Reputation should emerge from the structure and quality of relationships, not from raw activity volume alone.

## 3. Core Concepts

| Concept | Role in the Reputation Graph |
|---|---|
| Contributor Node | Represents a contributor, contributor group, reviewer, maintainer, or participant |
| Memory Object Node | Represents a structured record of contribution, decision, knowledge, governance, or mentorship context |
| Attestation Edge | Connects reviewers or authorities to Memory Objects with scoped review meaning |
| Domain Context | Defines the contribution area, such as documentation, infrastructure, research, governance, or education |
| Evidence Quality | Indicates how strong, durable, and reviewable the supporting evidence is |
| Lifecycle State | Indicates whether the record is draft, reviewed, accepted, verified, disputed, deprecated, inherited, or archived |
| Dispute Status | Preserves objections, corrections, overturned attestations, and unresolved uncertainty |
| Inheritance Link | Shows how earlier records influence later knowledge, guides, decisions, or mentorship material |

## 4. Graph Relationships

The Reputation Graph should make relationships explicit rather than implied.

| Relationship | Meaning |
|---|---|
| `contributed_to` | A contributor is associated with a Memory Object or contribution record |
| `submitted_by` | A contributor submitted a Memory Object or contribution claim |
| `attested_by` | A reviewer, maintainer, governance participant, or authority attested to a Memory Object |
| `reviewed_by` | A reviewer examined the record without necessarily issuing a strong attestation |
| `disputed_by` | A participant challenged authorship, evidence, usefulness, scope, or interpretation |
| `corrected_by` | A contributor or reviewer supplied a correction, revision, or clarification |
| `inherited_by` | A later Memory Object reused, extended, or learned from an earlier record |
| `superseded_by` | A later record replaced earlier guidance or interpretation |
| `cited_by` | A record was used as source context by another document, decision, guide, or AI mentor response |

These relationships allow reputation to be interpreted through context. For example, a merged documentation contribution, a useful bug report, and a disputed governance claim should not produce the same reputation signal.

## 5. Contextual Reputation Domains

Reputation should be domain-scoped. A contributor may be highly trusted in one area and still require review in another.

Possible domains include:

- documentation;
- protocol research;
- infrastructure operation;
- governance participation;
- education and onboarding;
- localization and translation;
- security review;
- community support;
- archive maintenance;
- mentorship.

A single universal reputation score would hide these differences. Chronicle should instead preserve domain-specific context so that later users can ask more precise questions:

- Has this contributor produced useful documentation?
- Has this reviewer made accurate attestations in this domain?
- Has this contributor helped preserve governance reasoning?
- Has this record influenced later learning material?
- Is this reputation signal current, historical, disputed, or deprecated?

## 6. Reputation Interpretation Rules

The Reputation Graph should follow conservative interpretation rules.

### Evidence-Aware

Reputation signals should be connected to evidence quality. Weak, broken, private, or unverifiable evidence should not carry the same weight as durable, reviewable, source-linked evidence.

### Domain-Scoped

Reputation should be interpreted within contribution domains. Documentation reputation should not automatically imply security review authority, validator expertise, or governance authority.

### Lifecycle-Aware

The lifecycle state of the Memory Object matters. Accepted, verified, disputed, deprecated, archived, and inherited records should be interpreted differently.

### Non-Transferable

Contributor reputation should not be bought, sold, delegated, or transferred. It should remain tied to contribution history and review context.

### Non-Universal

The graph should avoid reducing reputation to a single global score. Summaries may be useful, but they should remain explainable through underlying records and relationships.

### Dispute-Sensitive

Disputed or overturned records should remain visible as part of history, but they should not be treated as clean positive reputation signals.

## 7. Relationship to Memory Objects

Memory Objects are the primary evidence-bearing nodes of the Reputation Graph. They preserve contribution context, evidence links, attesters, lifecycle status, related objects, and contextual relevance.

A Reputation Graph should not create reputation independently from Memory Objects. Instead, it should interpret Memory Objects and their relationships.

| Memory Object Property | Reputation Graph Use |
|---|---|
| `contributor_id` | Connects contributor identity or pseudonym to contribution history |
| `contribution_type` | Places the record in a domain context |
| `evidence_quality` | Helps determine confidence in the reputation signal |
| `attesters` | Links reviewers and authority context |
| `attestation_scope` | Clarifies what was actually confirmed |
| `lifecycle_status` | Prevents outdated or disputed records from being treated as current |
| `related_objects` | Enables inheritance, citation, correction, and supersession relationships |

## 8. Relationship to Attestation

Attestation is the review mechanism that helps transform contribution records into credible reputation context.

A positive attestation should not automatically create universal reputation. It should create a scoped signal:

```text
Reviewer X attested that Memory Object Y is accurate/useful/relevant within Domain Z.
```

The scope matters. An attestation may confirm authorship, technical accuracy, educational usefulness, governance relevance, or historical importance. These should not be collapsed into one generic approval.

Disputed, partial, or overturned attestations should remain part of the graph because they preserve accountability and correction history.

## 9. Relationship to Attestation Authority

Attestation Authority describes who can issue attestations and how reviewer authority is earned, limited, reduced, or revoked. The Reputation Graph describes how those reviewer actions become part of longer-term reputation context.

The two layers should remain distinct:

| Layer | Primary Question |
|---|---|
| Attestation Authority | How much weight should a reviewer have when assessing records? |
| Reputation Graph | What contextual contribution and review history exists around a participant? |

A reviewer may have authority in one domain but not another. Likewise, a contributor may have strong reputation as an educator without having authority as a security reviewer.

## 10. Relationship to Knowledge Inheritance

Knowledge Inheritance explains how Memory Objects are referenced, extended, superseded, and reused across contributor generations. The Reputation Graph records how those inheritance relationships affect attribution and continuity.

For example:

```text
Bug Report -> Fix -> Documentation -> Tutorial -> Community Adoption
```

In this chain, reputation context may attach to several contributors:

- the person who identified the issue;
- the person who fixed it;
- the person who documented it;
- the person who translated or taught it;
- the reviewers who confirmed its usefulness.

The graph should preserve the full lineage instead of assigning all recognition to only the final visible artifact.

## 11. Relationship to AI Mentor

The AI Mentor Layer may use the Reputation Graph as contextual metadata, but it should not treat reputation as automatic authority.

AI mentor systems should:

- prefer source-linked Memory Objects over contributor status;
- show evidence quality and lifecycle state where relevant;
- avoid ranking contributors as final truth sources;
- distinguish current guidance from historical contribution;
- avoid amplifying popularity bias;
- explain when reputation context is incomplete, disputed, or domain-limited.

A high-reputation contributor can still produce outdated or incorrect material. A new contributor can still produce strong evidence. AI retrieval should therefore use reputation as context, not as proof.

## 12. Risks and Safeguards

| Risk | Description | Possible Safeguard |
|---|---|---|
| Reputation farming | Participants optimize for visible activity rather than meaningful contribution | Require evidence quality, attestation scope, and lifecycle review |
| Score reductionism | Complex contribution becomes flattened into a single number | Use contextual domains and explainable relationships |
| Reviewer capture | A small group controls recognition | Domain limits, dispute processes, and reviewer accountability |
| Popularity bias | Well-known contributors are over-weighted | Prioritize evidence and lifecycle state over identity |
| Sybil activity | Multiple accounts attempt to simulate contribution history | Require durable evidence, attestation quality, and relationship analysis |
| Collusion rings | Groups repeatedly attest to each other | Pattern detection, dispute review, and authority limits |
| Privacy exposure | Reputation graph reveals sensitive contributor history | Redaction, privacy levels, and limited visibility rules |
| Permanent hierarchy | Early contributors become permanently authoritative | Recency context, dispute history, and supersession relationships |
| AI overconfidence | AI presents reputation as proof | Source grounding and confidence labels |

## 13. Open Research Questions

1. What is the minimum data needed to represent reputation without creating a universal score?
2. How should disputed or overturned Memory Objects affect reputation context?
3. Should reputation signals decay over time, or should they remain historical but marked by recency?
4. How can Chronicle preserve attribution without creating permanent hierarchy?
5. What graph relationships should be public, private, redacted, or consent-dependent?
6. How should contributor pseudonyms be handled across multiple ecosystems?
7. Can domain-specific reputation be summarized without hiding uncertainty?
8. How should inherited knowledge distribute attribution across a lineage?
9. What safeguards are needed against collusion or reviewer capture?
10. How should AI mentor systems expose reputation context without creating authority shortcuts?

## 14. Conclusion

The Reputation Graph is the contextual layer that connects contribution memory, attestation, reviewer authority, knowledge inheritance, and AI-assisted retrieval. It allows Chronicle / Legacy Protocol to remember meaningful human contribution without reducing contributors to a single score.

A mature Reputation Graph should be evidence-aware, domain-scoped, lifecycle-aware, non-transferable, dispute-sensitive, and privacy-conscious. Its purpose is not to rank people. Its purpose is to preserve explainable context around how contribution, trust, review, and knowledge continuity emerge over time.
