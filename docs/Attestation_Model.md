# Attestation Model

## Overview

The Attestation Model defines how contribution claims may be reviewed, contextualized, accepted, disputed, revised, or rejected within Chronicle / Legacy Protocol. It is the bridge between raw contribution evidence and durable protocol memory.

An attestation is not simply a like, badge, or approval signal. In this research context, an attestation is a structured statement that a contribution claim has been examined under defined criteria and assigned an evidence-aware status.

Reviewer authority, scope, and accountability are further described in the [Attestation Authority Model](./Attestation_Authority_Model.md).

## Purpose

The purpose of an attestation model is to prevent the Protocol Memory Layer from becoming a collection of unverified claims. Without review, memory systems can become vulnerable to spam, duplication, low-effort activity, reputation farming, and misleading historical records.

A credible attestation model should support:

- evidence-based review;
- category-specific contribution standards;
- dispute and correction mechanisms;
- transparency around reviewer authority;
- protection against low-quality or automated claims;
- contextual interpretation rather than universal scoring.

## Contribution Claim Lifecycle

A contribution claim may move through several states.

| State | Meaning |
|---|---|
| Submitted | A contributor has created a claim with supporting evidence |
| Under Review | The claim is being evaluated by reviewers, maintainers, governance participants, or other approved attestators |
| Accepted | The claim is considered valid within its defined scope |
| Partially Accepted | Some parts of the claim are valid, but scope, impact, or evidence is limited |
| Needs Revision | The claim requires clearer evidence, better description, or additional context |
| Disputed | One or more participants challenge the claim, evidence, authorship, usefulness, or interpretation |
| Rejected | The claim does not meet the required evidence or contribution criteria |
| Archived | The claim is preserved as historical context, including its final status and review history |

These states should be treated as research categories rather than final protocol rules.

## Evidence Types

Different contribution categories require different forms of evidence.

| Contribution Type | Possible Evidence | Review Considerations |
|---|---|---|
| Code | Pull requests, commits, issue references, review comments | Was the change merged, reviewed, tested, or used? |
| Documentation | Guides, README updates, tutorials, issue responses | Is the content accurate, useful, and maintained? |
| Governance | Proposals, voting records, discussion summaries | Did the contribution improve decision-making context? |
| Infrastructure | Node operation records, monitoring notes, incident reports | Is the evidence verifiable without exposing sensitive data? |
| Education | Articles, videos, workshops, onboarding materials | Does the material improve understanding for others? |
| Localization | Translations, regional guides, language-specific explainers | Is the translation accurate and context-aware? |
| Research | Papers, analysis notes, comparative studies | Are sources, assumptions, and limitations clearly stated? |
| Community Support | Public answers, troubleshooting, moderation, onboarding | Is the support useful, respectful, and evidence-linked? |

No single evidence type should be treated as universally sufficient. The quality of evidence depends on context.

## Attestor Roles

An attestation system may involve different reviewer roles.

| Role | Function |
|---|---|
| Maintainer | Reviews contributions related to repositories, documentation, or technical changes |
| Governance Participant | Reviews contributions connected to proposals, voting, or public decision-making |
| Domain Reviewer | Evaluates specialized work such as security, infrastructure, translation, or research |
| Community Reviewer | Provides contextual assessment of educational or support contributions |
| Self-Declarer | Submits contribution claims but should not be the sole source of validation |
| Automated Checker | Supports review by verifying links, timestamps, duplication, or metadata, but should not replace human judgment |

Attestor authority should be transparent and limited by domain. A reviewer qualified to evaluate documentation may not be qualified to evaluate validator operations or security research.

## Attestation Criteria

A contribution may be reviewed across several dimensions.

| Criterion | Question |
|---|---|
| Evidence Quality | Is the supporting material accessible, specific, and relevant? |
| Authorship | Can the contribution reasonably be linked to the claimed contributor? |
| Usefulness | Did the contribution provide meaningful ecosystem value? |
| Originality | Is the work original, adapted with attribution, or duplicated? |
| Scope Accuracy | Does the claim avoid exaggerating its impact? |
| Durability | Is the contribution likely to remain useful beyond a short-term campaign? |
| Reviewability | Can other participants inspect or challenge the claim? |
| Privacy Safety | Does the evidence avoid exposing sensitive or personal information? |

The model should favor accurate limited claims over broad unsupported claims.

## Disputes and Corrections

A protocol memory system must allow correction. Historical records become less trustworthy if they cannot represent disagreement, uncertainty, or revision.

Possible dispute reasons include:

- incorrect authorship;
- duplicated contribution claims;
- misleading impact description;
- broken or unverifiable evidence;
- plagiarism or unattributed copying;
- privacy concerns;
- outdated technical information;
- disputed usefulness or relevance.

A mature attestation model should preserve both the original claim and the correction history. This allows the system to maintain memory without pretending that all records are final.

## Anti-Farming Considerations

Because contribution systems can be gamed, an attestation model should distinguish between activity volume and contribution quality.

Potential safeguards include:

- duplicate detection;
- rate limits for similar claims;
- category-specific evidence standards;
- human review for high-impact records;
- penalties or flags for repeated misleading claims;
- separation between contribution memory and direct rewards;
- requirement that large claims include stronger evidence;
- preservation of rejected or disputed claim history when appropriate.

The goal is not to make contribution difficult to record. The goal is to make low-quality reputation extraction less effective.

## Manual Review and Protocol-Level Attestation

Manual review is flexible but inconsistent. Protocol-level attestation is structured but may become rigid. A practical system may require both.

| Review Mode | Strength | Limitation |
|---|---|---|
| Manual Review | Context-aware and adaptable | May be inconsistent or biased |
| Automated Verification | Fast and scalable for metadata | Cannot evaluate usefulness or meaning alone |
| Community Attestation | Reflects broader social context | May be influenced by popularity or coordination |
| Maintainer Attestation | Strong for accepted technical work | Limited to specific repositories or domains |
| Governance Attestation | Useful for historical decisions | May reflect political dynamics |
| Hybrid Attestation | Balances structure and judgment | Requires careful governance design |

Chronicle / Legacy Protocol should treat attestation as a layered process rather than a single approval button.

## Privacy and Disclosure

Contribution evidence may contain sensitive information. Infrastructure logs, wallet addresses, operational notes, private moderation work, or support conversations should not automatically become public records.

A future attestation model should explore:

- public evidence;
- redacted evidence;
- private reviewer-only evidence;
- hashed evidence references;
- contributor-controlled disclosure;
- time-limited visibility;
- removal or correction processes for harmful exposure.

Memory should not come at the cost of contributor safety.

## Research Questions

1. Which contribution categories require human review, and which can be partially automated?
2. How should reviewer authority be assigned, limited, and audited?
3. What evidence standards are appropriate for different contribution types?
4. How can disputes be represented without erasing historical context?
5. How can anti-farming mechanisms avoid excluding small but meaningful contributors?
6. What privacy-preserving evidence models are suitable for infrastructure and governance work?
7. How should attestation interact with reputation without becoming a transferable scoring system?

## Conclusion

The Attestation Model is essential for transforming contribution claims into credible protocol memory. It provides the review logic needed to distinguish evidence-backed contribution from raw activity, spam, or unsupported reputation claims.

For Chronicle / Legacy Protocol, attestation should remain contextual, reviewable, privacy-aware, and open to correction. Its value lies not in creating permanent status, but in preserving trustworthy ecosystem memory over time.