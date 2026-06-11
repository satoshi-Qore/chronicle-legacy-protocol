# Threat Model

## Overview

This document presents a research-stage threat model for Chronicle / Legacy Protocol. It focuses on risks that may affect a Protocol Memory Layer designed to preserve verified contribution, contextual reputation, governance history, ecosystem knowledge, and long-term institutional memory.

Chronicle is currently a documentation and architecture research project. This document does not claim that any production implementation exists. Its purpose is to identify risks, describe possible attack scenarios, and define open research questions that should be addressed before any future specification or prototype work.

## Scope

The threat model covers risks related to:

- contribution claims;
- evidence references;
- attestation processes;
- contributor reputation;
- governance memory;
- decision records;
- archival integrity;
- AI-assisted retrieval and interpretation;
- dispute and correction mechanisms.

The following areas are outside the current scope:

- smart contract implementation vulnerabilities;
- production infrastructure security;
- chain-specific deployment risks;
- financial incentives or token mechanics;
- formal cryptographic protocol proofs.

## Threat Summary

| Threat | Target Area | Primary Risk | Research Priority |
|---|---|---|---|
| Sybil attacks | Contribution identity and participation | Artificially increasing apparent contributor presence | High |
| Fake contributions | Contribution records | Preserving false or low-quality claims as valid memory | High |
| Attestation collusion | Review and verification | Groups mutually validating weak or false claims | High |
| Reputation inflation | Contributor reputation | Turning visibility or volume into misleading authority | High |
| Governance capture | Governance memory and decision records | Dominant groups controlling historical interpretation | High |
| Historical record manipulation | Archives and legacy records | Altering, suppressing, or selectively framing ecosystem history | High |
| Evidence link rot | External references | Loss of source material supporting contribution claims | Medium |
| Privacy leakage | Contributor records | Overexposing personal or sensitive contributor history | Medium |
| AI-assisted misinterpretation | Knowledge retrieval | Producing inaccurate summaries of historical records | Medium |

## Sybil Attacks

### Description

A Sybil attack occurs when one actor controls multiple identities in order to appear as many independent contributors. In a protocol memory system, Sybil behavior may distort contribution history, governance participation records, attestation activity, and perceived community consensus.

### Attack Scenario

An actor creates several accounts that submit small contribution claims, endorse each other, participate in governance discussions, and create the appearance of broad support for a proposal or interpretation of history. Over time, these accounts may accumulate contextual reputation and influence future records.

### Possible Mitigation Approaches

- Use evidence quality levels rather than raw account counts.
- Distinguish contributor identity from contribution validity.
- Require multiple forms of evidence for high-impact records.
- Introduce reviewer diversity for sensitive attestations.
- Track relationship patterns between attestors and claimants.
- Preserve uncertainty labels where identity confidence is limited.
- Consider optional privacy-preserving human verification for specific contexts.

### Open Research Questions

- How can a memory layer resist Sybil behavior without excluding pseudonymous contributors?
- Which contribution categories require stronger identity confidence?
- How should systems distinguish coordinated contributors from malicious identity multiplication?
- What level of identity assurance is appropriate for historical records?

## Fake Contributions

### Description

Fake contributions are claims about work that was not performed, was copied from others, was generated without meaningful review, or was presented with misleading evidence. A memory layer that records fake contributions risks damaging long-term trust.

### Attack Scenario

A contributor submits a record claiming to have authored documentation, supported users, or influenced a governance decision. The evidence consists of weak links, incomplete screenshots, copied content, or unverifiable social posts. If accepted, the record becomes part of the archive and may influence reputation later.

### Possible Mitigation Approaches

- Define minimum evidence standards for each contribution type.
- Separate submitted claims from accepted or verified records.
- Require source links, timestamps, and reviewer notes where possible.
- Preserve rejected and disputed records with appropriate labels.
- Use plagiarism checks for text-heavy contributions.
- Allow later correction when stronger evidence becomes available.

### Open Research Questions

- How should low-evidence contributions be archived without treating them as verified?
- What evidence is sufficient for community support or educational work?
- How can review avoid becoming too burdensome for small but real contributions?
- Should unverifiable contributions be excluded or preserved as unverified claims?

## Attestation Collusion

### Description

Attestation collusion occurs when a group of actors mutually validate each other's claims regardless of quality or truth. This can create false confidence in contribution records and distort reputation.

### Attack Scenario

A small group repeatedly attests to each other's contributions. They use legitimate-looking review language and create a dense network of mutual endorsements. Later readers may interpret the number of attestations as independent evidence, even though the attestations are not meaningfully independent.

### Possible Mitigation Approaches

- Track attestation relationships and repeated patterns.
- Weight attestation quality by reviewer domain context rather than count alone.
- Require independent review for high-impact records.
- Add conflict-of-interest disclosure fields.
- Preserve reviewer rationale instead of only binary approvals.
- Support dispute mechanisms for suspicious attestation clusters.

### Open Research Questions

- How can collusion be detected without assuming all repeated collaboration is malicious?
- What makes an attestation independent enough to increase confidence?
- Should attestor reputation be domain-specific rather than global?
- How can social trust be represented without creating permanent reviewer elites?

## Reputation Inflation

### Description

Reputation inflation occurs when a contributor's perceived value grows through volume, visibility, or repetitive activity rather than meaningful contribution. In a memory layer, this may produce distorted historical importance.

### Attack Scenario

A user performs many low-impact actions, comments frequently, generates repetitive documentation, or creates numerous minor records. The system records this activity and future readers interpret it as high contribution, even though the actual value may be limited.

### Possible Mitigation Approaches

- Avoid universal reputation scores.
- Separate activity volume from contribution significance.
- Use contextual reputation categories such as research, infrastructure, documentation, governance, and education.
- Include reviewer notes explaining contribution quality.
- Apply diminishing returns to repetitive contribution patterns in future models.
- Preserve evidence quality and impact context alongside contribution records.

### Open Research Questions

- How can meaningful contribution be recognized without creating a ranking system?
- What signals indicate durable contribution value rather than activity volume?
- How can the system avoid disadvantaging quiet but high-impact contributors?
- How should reputation decay, revision, or contextual limitation be handled?

## Governance Capture

### Description

Governance capture occurs when a dominant group gains control over decision-making or historical interpretation. In Chronicle, the risk is not only capture of decisions, but capture of how decisions are remembered.

### Attack Scenario

A group with strong governance influence frames past decisions in a way that benefits its preferred narrative. Alternative views, minority objections, and unresolved concerns are omitted from decision records. Future contributors inherit a simplified and biased version of ecosystem history.

### Possible Mitigation Approaches

- Preserve minority opinions and unresolved objections.
- Require decision records to include alternatives considered.
- Include retrospective review sections after outcomes are observed.
- Maintain source-linked governance context rather than final summaries alone.
- Support dispute labels and revision history.
- Encourage multiple reviewers for historically significant records.

### Open Research Questions

- How can governance memory remain useful without becoming politically captured?
- Who should be allowed to revise historical decision records?
- How should disputed interpretations be displayed to future readers?
- What process should determine when a decision record is considered stable?

## Historical Record Manipulation

### Description

Historical record manipulation involves altering, deleting, selectively preserving, or misleadingly summarizing past contributions and decisions. A protocol memory system must treat archival integrity as a central research problem.

### Attack Scenario

An actor edits an archive to remove inconvenient evidence, changes the framing of an earlier decision, or highlights only favorable contributions. Even if original sources still exist elsewhere, future users may rely on the curated memory layer and miss the manipulation.

### Possible Mitigation Approaches

- Maintain revision history for important records.
- Preserve links to original sources and timestamps.
- Mark summaries as interpretations rather than primary evidence.
- Support archival checksums or content-addressed references in future specifications.
- Require change notes for edits to historical records.
- Separate primary evidence from editorial summaries.

### Open Research Questions

- What level of immutability is appropriate for records that may need correction?
- How can a memory system support both preservation and legitimate revision?
- Should historical records support competing interpretations?
- How should missing or deleted external sources be represented?

## Evidence Link Rot and External Dependency Failure

### Description

Many contribution records depend on external URLs, social posts, forum threads, screenshots, repositories, or governance pages. These references may disappear, change, become private, or lose context.

### Attack Scenario

A contribution record points to a forum thread or social post that later becomes unavailable. The memory layer still references the contribution, but reviewers can no longer verify the underlying evidence.

### Possible Mitigation Approaches

- Store metadata about evidence at the time of review.
- Include archived copies or hashes where legally and ethically appropriate.
- Require short evidence summaries alongside external links.
- Mark records when source material becomes unavailable.
- Encourage redundant evidence for high-impact records.

### Open Research Questions

- Which evidence types should be archived directly?
- How should the system handle copyright, privacy, and consent concerns?
- Can source availability be monitored without excessive infrastructure requirements?
- What confidence level remains when evidence links fail?

## Privacy Leakage

### Description

Contribution memory may expose personal history, location, social relationships, governance positions, or work patterns. Long-term archives can create risks for contributors if privacy is not considered from the beginning.

### Attack Scenario

A contributor's old governance comments, support activity, or identity-linked attestations are preserved permanently. Years later, the information is used out of context or combined with other data to profile the contributor.

### Possible Mitigation Approaches

- Separate public contribution records from sensitive personal details.
- Support redaction requests where appropriate.
- Use privacy-preserving verification when possible.
- Avoid unnecessary identity linkage.
- Define retention policies for sensitive evidence.
- Label records that contain personal or context-sensitive material.

### Open Research Questions

- What rights should contributors have over historical records about them?
- How can accountability and privacy be balanced?
- Which records should be permanent, revisable, or removable?
- How should pseudonymous contribution histories be protected?

## AI-Assisted Misinterpretation

### Description

Chronicle includes the concept of an AI Mentor Layer for knowledge retrieval and learning support. AI systems can help summarize archives, but they can also misrepresent uncertainty, omit disputes, or create false confidence.

### Attack Scenario

A future AI assistant summarizes a governance history and presents a contested decision as universally accepted. It omits minority concerns and cites incomplete records. New contributors rely on the summary and inherit a distorted interpretation.

### Possible Mitigation Approaches

- Require source-linked AI summaries.
- Preserve uncertainty labels and disputed points.
- Separate machine-generated summaries from primary records.
- Include retrieval logs or citation trails in future designs.
- Allow human review of important AI-generated historical summaries.
- Avoid treating AI output as authoritative memory.

### Open Research Questions

- How should AI assistants represent uncertainty and disagreement?
- What records are safe for AI summarization?
- How can hallucination risk be reduced in historical archives?
- Should AI mentor responses be auditable or versioned?

## Mitigation Design Principles

The following principles should guide future Chronicle research:

1. Evidence should be classified by quality, source, and review status.
2. Reputation should remain contextual rather than universal.
3. Attestations should preserve reviewer rationale, not only approval status.
4. Decision records should include alternatives, objections, and retrospective updates.
5. Historical summaries should remain linked to primary sources.
6. Dispute and correction mechanisms should be part of the memory model.
7. Privacy and pseudonymity should be treated as design requirements.
8. AI-assisted retrieval should be source-linked, uncertainty-aware, and reviewable.

## Residual Risks

No memory system can fully remove social, political, or interpretive risk. A Protocol Memory Layer may reduce fragmentation and improve accountability, but it can also become a new site of influence. The system must therefore avoid presenting archived memory as absolute truth. Records should preserve evidence, context, uncertainty, and disagreement where relevant.

## Open Research Agenda

Future research should define:

- evidence quality levels for different contribution types;
- reviewer role models and conflict-of-interest disclosures;
- dispute resolution and record correction workflows;
- privacy-preserving contribution verification methods;
- archival strategies for external evidence;
- AI summary governance and citation requirements;
- methods for detecting collusion and reputation manipulation;
- criteria for distinguishing historical memory from reputation scoring.

## Conclusion

Chronicle / Legacy Protocol depends on trust in contribution records, attestations, governance context, and historical interpretation. The main threats are not only technical. They are social, archival, and epistemic. A credible Protocol Memory Layer must therefore combine evidence standards, contextual reputation, dispute processes, privacy safeguards, and transparent archival practices.

This threat model should be treated as an early research document. It should evolve as the Chronicle design space becomes more precise and as future specifications define concrete data structures, review workflows, and implementation boundaries.
