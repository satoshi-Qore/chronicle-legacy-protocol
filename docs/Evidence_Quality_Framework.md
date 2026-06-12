# Evidence Quality Framework

## Overview

The Evidence Quality Framework defines how Chronicle / Legacy Protocol may classify and interpret evidence attached to memory objects. It is designed to support contribution records, governance records, knowledge records, decision records, archive records, and AI-assisted retrieval.

This document is conceptual and research-oriented. It does not define a production verification system or automated scoring model. Its purpose is to identify evidence categories, quality levels, risks, and interpretation rules for a future Protocol Memory Layer.

## Purpose

A Protocol Memory Layer depends on the quality of its sources. If weak, misleading, incomplete, or disappearing evidence is treated as reliable memory, the entire system can become inaccurate. Evidence quality must therefore be explicit, reviewable, and connected to lifecycle state.

The framework aims to:

- classify different evidence types;
- distinguish existence from significance;
- define evidence quality levels;
- identify evidence risks such as link rot and manipulation;
- support review and dispute workflows;
- guide contributor reputation interpretation;
- help AI mentor systems cite sources responsibly.

## Core Principle

Evidence quality is not the same as contribution value.

A strong source may document a small contribution. A weak source may point to a meaningful contribution that needs more context. Chronicle should therefore avoid converting evidence quality directly into reputation, status, or authority.

Evidence should support interpretation, not replace it.

## Evidence Categories

| Evidence Category | Description | Example |
|---|---|---|
| Repository Evidence | Public development or documentation activity | Pull request, issue, commit, review comment |
| Governance Evidence | Records of proposal creation, discussion, voting, or implementation | Proposal page, forum thread, vote record, decision record |
| Documentation Evidence | Written materials created or improved by contributors | Guide, FAQ, glossary, research note |
| Infrastructure Evidence | Operational or technical proof related to node, server, or network activity | Monitoring screenshot, redacted log, configuration note |
| Educational Evidence | Material that helps users understand the ecosystem | Tutorial, explainer, translation, onboarding article |
| Community Support Evidence | Help provided to users or contributors | Support answer, troubleshooting note, community response |
| External Publication Evidence | Third-party or public-facing publication | Article, report, academic reference, external review |
| Attestation Evidence | Structured claim from reviewer, maintainer, peer, or protocol source | Maintainer comment, signed attestation, accepted review |
| Archive Evidence | Preserved historical material | Snapshot, archived link, saved forum thread, timestamped document |
| Retrospective Evidence | Later review of past outcomes | Post-decision review, incident lesson, implementation reflection |

## Evidence Quality Levels

| Level | Name | Description | Example |
|---|---|---|---|
| 0 | Missing | No evidence is available | Unsupported claim |
| 1 | Weak | Evidence is incomplete, unclear, temporary, or hard to verify | Cropped screenshot without source link |
| 2 | Basic | Evidence confirms that an activity or source exists | Public post, visible issue, accessible document |
| 3 | Contextual | Evidence includes purpose, scope, and relevance | Issue with clear problem statement and discussion |
| 4 | Accepted | Evidence is accepted by a relevant reviewer, maintainer, or process | Merged pull request, accepted governance input |
| 5 | Verified | Evidence is strong, durable, source-linked, and has clear review context | Maintainer-confirmed record with source links and revision history |

These levels should be interpreted as confidence categories, not rewards or rankings.

## Evidence Strength by Record Type

Different memory object types require different evidence expectations.

| Memory Object Type | Minimum Useful Evidence | Stronger Evidence |
|---|---|---|
| Contribution Record | Public artifact or traceable source | Maintainer-accepted work with review context |
| Governance Record | Proposal, discussion, or vote record | Decision rationale, contributor input, implementation status, retrospective |
| Knowledge Record | Source document or explanation | Validated guide linked to source decisions or contributions |
| Decision Record | Problem statement and outcome | Alternatives considered, evidence references, retrospective notes |
| Archive Record | Preserved source or metadata | Archived copy, timestamp, source integrity notes |
| Retrospective Record | Later observation or review | Evidence-linked outcome analysis |
| Dispute Record | Challenge description | Source-backed counter-evidence and reviewer response |

## Evidence Interpretation Rules

Evidence should be interpreted according to the following rules:

1. Evidence confirms a source, not necessarily importance.
2. Screenshots should be treated as weaker than durable public links unless supported by context.
3. Social engagement should not be treated as strong contribution evidence by itself.
4. Maintainer or governance acceptance increases confidence but does not eliminate dispute possibility.
5. Multiple weak sources do not automatically equal one strong source.
6. Evidence quality can change over time if links break, sources are deleted, or new records appear.
7. AI-generated summaries should not be treated as primary evidence.
8. Reviewer notes should identify limitations and uncertainty.

## Screenshot Evidence

Screenshots are useful but limited. They can demonstrate that something occurred, but they are easier to crop, misread, or detach from context.

Screenshots should ideally include:

- visible date or timestamp;
- source platform or URL where possible;
- relevant surrounding context;
- redaction of sensitive information;
- short explanation of what is being shown.

Screenshots should not include:

- private keys;
- seed phrases;
- personal identity information beyond what is necessary;
- unredacted IP addresses or server credentials;
- private conversations without consent.

## Repository Evidence

Repository evidence is often strong because it is public, timestamped, and reviewable.

Examples include:

- pull requests;
- merged commits;
- issue reports;
- review comments;
- file history;
- release notes;
- documentation changes.

However, repository evidence still requires context. A merged change may be small, and an open issue may be meaningful even if it is not merged. Evidence quality should describe what the record proves and what it does not prove.

## Governance Evidence

Governance evidence should preserve more than final outcomes. A vote result alone may show participation, but not reasoning, trade-offs, implementation status, or later consequences.

Strong governance evidence may include:

- proposal text;
- discussion history;
- decision rationale;
- vote or approval record;
- contributor input;
- implementation follow-up;
- retrospective review;
- disputed interpretations.

Governance evidence should avoid converting participation into automatic authority.

## Infrastructure Evidence

Infrastructure evidence can be sensitive. It may include operational logs, monitoring panels, node status, configuration files, or service screenshots.

Infrastructure evidence should be reviewed carefully because it may reveal:

- IP addresses;
- server paths;
- credentials;
- private endpoints;
- operational weaknesses;
- personal account details.

For Chronicle, redacted infrastructure evidence may be acceptable if it preserves the relevant proof while reducing security risk.

## Attestation Evidence

Attestations may improve confidence, but their strength depends on context.

| Attestation Type | Strength Consideration |
|---|---|
| Self-attestation | Useful as initial claim, not independent evidence |
| Peer attestation | Useful if reviewer context and independence are clear |
| Maintainer attestation | Strong for repository or project-scoped contribution |
| Governance attestation | Strong for accepted governance processes, but politically sensitive |
| Protocol-verifiable attestation | Strong when independently verifiable |
| External attestation | Depends on credibility and relevance of external reviewer |

Attestation evidence should include rationale where possible. A bare approval is weaker than an explanation of what was reviewed.

## Link Rot and Source Decay

Evidence can weaken over time when sources disappear, links break, repositories change, or platforms remove content.

Possible safeguards:

- preserve metadata at the time of review;
- include source title, date, and author where appropriate;
- use archived copies when legally and ethically acceptable;
- distinguish original sources from mirrors;
- mark records when source availability changes;
- prefer durable sources for high-impact memory objects.

A record with broken evidence may remain historically useful, but its confidence level should be revisited.

## Evidence Manipulation Risks

| Risk | Description | Possible Safeguard |
|---|---|---|
| Cropped Evidence | Screenshot hides relevant context | Require source link or surrounding context |
| Fake Attribution | Contributor claims work done by others | Check source history and authorship |
| Duplicate Claims | Same activity submitted repeatedly | Link related memory objects |
| Social Metric Inflation | Likes or shares presented as contribution quality | Treat engagement as low-strength evidence |
| Link Rot | Source disappears after review | Preserve metadata or archive references |
| Collusive Attestation | Reviewers validate each other without independence | Track reviewer relationships and rationale |
| AI-Generated Misleading Summaries | Machine summary replaces source evidence | Require primary source references |
| Privacy Leakage | Evidence exposes sensitive details | Use redaction and disclosure levels |

## Relationship to Memory Lifecycle

Evidence quality affects lifecycle transitions.

| Lifecycle Transition | Evidence Requirement |
|---|---|
| Draft -> Submitted | Basic source reference or claim description |
| Submitted -> Observed | Evidence exists and can be inspected |
| Observed -> Reviewed | Reviewer can evaluate source and context |
| Reviewed -> Accepted | Evidence supports the claim within scope |
| Accepted -> Verified | Strong, durable, source-linked evidence with limited dispute |
| Any State -> Disputed | Conflicting evidence or challenge appears |
| Disputed -> Revised | New evidence or correction changes interpretation |
| Any State -> Archived | Historical value remains even if active use changes |
| Any State -> Rejected | Evidence is false, misleading, duplicated, or insufficient |

## Relationship to Contributor Reputation

Contributor reputation should consider evidence quality, but not mechanically convert it into a score.

Suggested interpretation:

| Evidence Level | Reputation Use |
|---|---|
| Missing | No positive reputation signal |
| Weak | Minimal or no reputation signal |
| Basic | Confirms activity, not quality |
| Contextual | Can support weak contextual reputation |
| Accepted | Can support meaningful contextual reputation |
| Verified | Strong contextual evidence, still category-limited |

This prevents raw activity volume from becoming reputation inflation.

## Relationship to AI Mentor Layer

AI mentor systems should use evidence quality to decide how confidently to answer questions.

AI retrieval guidance:

- prefer verified and accepted evidence for factual answers;
- cite source references clearly;
- label weak evidence as uncertain;
- avoid treating social engagement as authoritative;
- include disputed records when disagreement matters;
- avoid using rejected records as valid evidence;
- distinguish primary evidence from summaries or interpretations.

Evidence quality helps prevent AI systems from presenting weak or disputed memory as settled fact.

## Open Research Questions

1. What evidence level should be required for each memory object type?
2. How should evidence quality be updated when sources disappear?
3. Can screenshots be made more reliable without exposing sensitive information?
4. What forms of attestation are sufficiently independent?
5. Should evidence quality be evaluated by humans, protocol rules, or both?
6. How should multilingual evidence be reviewed across different communities?
7. What metadata should be preserved for external sources?
8. How should AI mentor systems communicate weak or conflicting evidence?

## Conclusion

The Evidence Quality Framework is a core part of Chronicle / Legacy Protocol. It helps determine how memory objects move through lifecycle states, how contributor reputation should interpret records, how governance memory remains accountable, and how AI mentor systems cite historical information.

A credible Protocol Memory Layer must preserve evidence, but also preserve the limits of that evidence. Strong memory depends not only on storing records, but on making the quality, context, and uncertainty of those records visible.
