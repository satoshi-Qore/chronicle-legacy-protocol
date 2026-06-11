# Related Work

## Overview

This document reviews existing systems and research areas related to Chronicle / Legacy Protocol. The goal is not to rank these systems, but to understand how contribution tracking, reputation, attestations, governance archives, knowledge preservation, and collective intelligence have been approached elsewhere.

Chronicle / Legacy Protocol is currently a documentation and research-stage project. It does not claim to implement or replace any of the systems discussed below. Instead, it studies the unresolved gap between verified contribution, contextual reputation, governance memory, knowledge inheritance, and long-term ecosystem history.

## Comparison Dimensions

| Dimension | Research Question |
|---|---|
| Contribution Tracking | How are human contributions identified, recorded, and evaluated? |
| Reputation Systems | How are contributor signals interpreted without reducing people to simplistic scores? |
| Attestation Frameworks | How are claims verified, signed, reviewed, or made portable? |
| Governance Archives | How are proposals, discussions, votes, and decisions preserved over time? |
| Knowledge Preservation | How does an ecosystem retain lessons, operational knowledge, and historical reasoning? |
| Collective Intelligence | How do communities combine human and machine intelligence for better decisions? |

## Gitcoin

### Goals

Gitcoin is closely associated with open-source funding, public goods support, grants, and mechanisms for coordinating support around ecosystem work. Its broader relevance to Chronicle lies in how it makes contribution and public goods activity visible to communities.

### Strengths

- Provides recognizable infrastructure around open-source and public goods contribution.
- Creates structured contexts where contributors, projects, and supporters can interact.
- Helps surface work that might otherwise remain invisible in fragmented ecosystems.
- Demonstrates the importance of contribution discovery and community support.

### Limitations

- The primary orientation is support and funding coordination rather than long-term protocol memory.
- Contribution history may remain tied to campaign periods, project pages, or funding rounds.
- It does not fully solve historical reasoning, governance memory, or knowledge inheritance.
- It may capture visibility around projects without preserving deep contributor context.

### Relevance to Chronicle

Gitcoin illustrates why contribution visibility matters. Chronicle extends the research question from contribution support toward contribution memory: how contributions are documented, attested, contextualized, corrected, and inherited over time.

## Ethereum Attestation Service (EAS)

### Goals

Ethereum Attestation Service provides infrastructure for creating, verifying, and using attestations. It is relevant to Chronicle because verified contribution records may require structured attestations rather than informal claims.

### Strengths

- Provides a general-purpose model for making claims through attestations.
- Supports schema-based data structures that can make attestations more interpretable.
- Encourages portability of signed claims across applications.
- Helps separate claim issuance from later interpretation.

### Limitations

- Attestation infrastructure does not by itself determine whether a contribution is meaningful.
- Schema design and reviewer authority remain application-specific problems.
- Attestations can preserve claims without solving social interpretation, disputes, or historical context.
- A valid attestation may still be biased, incomplete, outdated, or low quality.

### Relevance to Chronicle

EAS is relevant as a technical and conceptual reference for verifiable claims. Chronicle is concerned with what happens around and after attestation: review quality, dispute handling, contribution context, governance memory, and knowledge inheritance.

## SourceCred

### Goals

SourceCred explored ways to measure and recognize open-source contribution through contribution graphs and community-defined weights. It is one of the most directly relevant systems for contribution recognition and reputation analysis.

### Strengths

- Treats contribution as a graph rather than a single isolated event.
- Recognizes that value can emerge from code, discussion, review, and community interaction.
- Makes contribution flows more visible across open-source communities.
- Demonstrates the difficulty of modeling contribution fairly.

### Limitations

- Graph-based contribution models can be sensitive to weighting choices.
- Quantification may create incentives for gaming or optimization around measured signals.
- Reputation output can be misunderstood as objective or complete.
- Long-term governance memory and decision context are not the primary focus.

### Relevance to Chronicle

SourceCred is important because it shows both the promise and risk of contribution graphs. Chronicle attempts to preserve contribution memory without reducing contributor value to a universal score.

## Optimism Collective

### Goals

The Optimism Collective includes public governance processes, proposal forums, grants, roles, feedback categories, and historical discussions. It is relevant as an example of a large ecosystem preserving governance activity in public forums.

### Strengths

- Maintains visible governance categories, proposal discussions, policies, and templates.
- Provides a public archive of governance deliberation and ecosystem updates.
- Demonstrates the value of structured community governance records.
- Shows how governance forums can preserve discussion history beyond final outcomes.

### Limitations

- Forum archives may be difficult for new contributors to navigate.
- Decision reasoning can remain distributed across many posts and categories.
- Contributor input may be visible but not always structured into durable memory records.
- Retrospective links between decisions and later outcomes may require manual reconstruction.

### Relevance to Chronicle

Optimism demonstrates the importance of governance archives. Chronicle studies how governance memory can become more structured, source-linked, dispute-aware, and useful for future contributors.

## Aragon

### Goals

Aragon provides governance infrastructure and modular tooling for organizations that coordinate onchain. Its relevance to Chronicle is strongest in governance design, permissioning, modularity, and organizational coordination.

### Strengths

- Provides modular governance tooling and frameworks.
- Emphasizes adaptable organizational governance rather than a single fixed model.
- Supports different governance plugins and permission structures.
- Offers a useful reference point for governance system design.

### Limitations

- Governance tooling does not automatically preserve cultural memory or historical reasoning.
- Permission systems define who can act, but not necessarily why decisions were made.
- Contributor reputation, decision retrospectives, and knowledge inheritance require additional layers.
- Institutional memory can remain outside the core governance tooling.

### Relevance to Chronicle

Aragon is relevant as governance infrastructure. Chronicle focuses on the memory and interpretation layer around governance: decision context, contribution evidence, retrospective review, and knowledge transfer.

## Human Passport / Gitcoin Passport

### Goals

Human Passport, formerly associated with Gitcoin Passport, focuses on identity verification and Sybil resistance. It is relevant to Chronicle because contribution memory systems must consider fake accounts, duplicate identities, and manipulation.

### Strengths

- Provides a practical model for Sybil resistance and human verification.
- Uses multiple credentials or signals rather than a single identity check.
- Supports developer integrations for communities that require higher confidence in participant uniqueness.
- Highlights the need for privacy-preserving verification options.

### Limitations

- Human uniqueness is not the same as contribution quality.
- Identity verification does not determine whether work is meaningful, accurate, or useful.
- Strong identity checks may create access, privacy, or regional participation concerns.
- Sybil resistance is only one part of contribution memory.

### Relevance to Chronicle

Chronicle can learn from Sybil-resistance systems while keeping identity distinct from contribution quality. A verified human account still requires evidence, attestation, and contextual review.

## Snapshot

### Goals

Snapshot is widely used for governance signaling, offchain voting, and proposal-based coordination. It is relevant because governance memory often begins with proposals, votes, and community signaling.

### Strengths

- Provides accessible governance proposal and voting infrastructure.
- Creates public records of proposals and voting outcomes.
- Supports many communities with relatively low operational overhead.
- Helps standardize governance participation records.

### Limitations

- Voting records alone do not preserve the full reasoning behind decisions.
- Discussions, objections, evidence, and later outcomes may live outside the voting record.
- Proposal archives can become difficult to interpret without contextual summaries.
- It does not directly solve contribution memory or knowledge inheritance.

### Relevance to Chronicle

Snapshot-like systems preserve governance actions. Chronicle is interested in preserving the wider decision context: why a proposal existed, what evidence mattered, who contributed meaningfully, and what happened afterward.

## DAO and Governance Forums

### Goals

Many decentralized communities use forums, issue trackers, Discord-like platforms, GitHub discussions, and governance portals to coordinate decisions. These systems act as informal archives of collective reasoning.

### Strengths

- Preserve raw discussion history.
- Support open participation and asynchronous deliberation.
- Allow communities to surface concerns, proposals, and implementation feedback.
- Provide useful evidence for later governance analysis.

### Limitations

- Information is often fragmented, repetitive, or difficult to search.
- Important context may be buried in long threads.
- Informal discussion does not automatically become structured memory.
- Off-platform knowledge may disappear or become inaccessible.

### Relevance to Chronicle

Chronicle treats forums and discussions as important evidence sources, but not as sufficient memory systems. The research challenge is to turn fragmented discussion into structured, reviewable, and revisable decision memory.

## Academic Reputation Systems

### Goals

Academic and peer-to-peer reputation systems study how trust, credibility, and reliability can be inferred from past behavior, network relationships, or peer evaluation. Examples include EigenTrust-style peer reputation and later contributor reputation research in software ecosystems.

### Strengths

- Provide formal models for trust propagation and reputation analysis.
- Identify the risks of malicious actors, fake identities, and unreliable participants.
- Offer methods for studying reputation as a networked phenomenon.
- Help clarify why simple scoring can be misleading.

### Limitations

- Formal trust models may not capture qualitative human contribution.
- Global scores can flatten context and create hierarchy.
- Reputation derived from network position may reinforce existing visibility advantages.
- Academic models often require adaptation before use in open governance systems.

### Relevance to Chronicle

Chronicle benefits from reputation research but rejects the idea that contribution history should become a universal score. It instead emphasizes contextual reputation, evidence quality, and memory with correction mechanisms.

## Collective Intelligence Systems

### Goals

Collective intelligence research studies how groups of people and machines can collaborate to solve problems, make decisions, and build shared knowledge. This includes research from institutions such as the MIT Center for Collective Intelligence and broader work on knowledge-building communities.

### Strengths

- Provides a theoretical foundation for human-machine collaboration.
- Helps analyze how groups aggregate knowledge, judgment, and expertise.
- Supports the idea that communities require memory, coordination, and feedback loops.
- Offers useful framing for AI-assisted ecosystem learning.

### Limitations

- Collective intelligence research is broad and not specific to blockchain governance.
- It does not automatically provide contribution verification or attestation structures.
- AI-assisted summaries can distort history if sources, uncertainty, and disagreement are not preserved.
- Collective intelligence systems require careful governance to avoid manipulation and group bias.

### Relevance to Chronicle

Chronicle applies collective intelligence questions to decentralized ecosystems: how communities preserve knowledge, transmit contributor experience, summarize history, and avoid losing institutional memory.

## Summary Comparison

| System / Area | Primary Focus | Strength | Limitation | Chronicle Relevance |
|---|---|---|---|---|
| Gitcoin | Public goods and contribution support | Makes ecosystem work visible | Not primarily a long-term memory layer | Contribution discovery and public goods context |
| EAS | Attestation infrastructure | Structured verifiable claims | Meaning and review are application-specific | Attestation model reference |
| SourceCred | Contribution graph and reputation | Recognizes diverse contribution signals | Risk of over-quantification | Contextual contribution memory |
| Optimism Collective | Governance forum and public processes | Strong public governance archive | Context remains distributed | Governance memory model |
| Aragon | DAO governance tooling | Modular governance design | Memory layer not primary focus | Governance infrastructure comparison |
| Human Passport | Sybil resistance and identity signals | Helps distinguish humans from duplicates | Identity is not contribution quality | Anti-Sybil reference |
| Snapshot | Proposal and voting records | Accessible governance signaling | Limited decision context | Governance action archive |
| Academic reputation systems | Trust and reputation models | Formal analysis of trust | Can flatten context | Reputation safeguards |
| Collective intelligence | Human-machine knowledge systems | Strong theory for group intelligence | Broad and not blockchain-specific | Knowledge inheritance and AI mentor framing |

## Research Gap and Opportunity

Existing systems address important parts of the problem space, but they do not fully solve the combined challenge Chronicle / Legacy Protocol is examining.

Contribution platforms can surface work, but they do not necessarily preserve long-term contributor memory. Attestation systems can verify claims, but they do not decide whether a contribution was meaningful or how it should be interpreted later. Reputation systems can model activity, but they risk turning human work into simplified scores. Governance tools can record proposals and votes, but they often leave decision reasoning scattered across discussions. Collective intelligence systems can help explain group learning, but they do not directly provide protocol-level contribution memory for decentralized ecosystems.

Chronicle attempts to study the gap between these areas:

- verified contribution records;
- evidence-aware attestations;
- contextual reputation without permanent hierarchy;
- governance memory beyond vote outcomes;
- decision records with dispute and retrospective support;
- knowledge inheritance across contributor generations;
- AI-assisted retrieval that preserves sources and uncertainty;
- long-term ecosystem memory without reward farming as the central design goal.

The opportunity is to define a Protocol Memory Layer that treats contribution, governance, knowledge, and reputation as connected but distinct research domains. Chronicle does not claim to implement this layer yet. Its current role is to make the design space clearer, identify risks, and define research questions for future specification work.

## References and Further Reading

- Gitcoin: https://www.gitcoin.co/
- Ethereum Attestation Service: https://attest.org/
- SourceCred: https://sourcecred.io/
- Optimism Collective governance forum: https://gov.optimism.io/
- Aragon documentation: https://docs.aragon.org/
- Human Passport documentation: https://docs.passport.human.tech/
- Snapshot: https://snapshot.box/
- MIT Center for Collective Intelligence: https://cci.mit.edu/
- EigenTrust: Kamvar, Schlosser, and Garcia-Molina, "The EigenTrust Algorithm for Reputation Management in P2P Networks," WWW 2003.
- Contributor reputation in software ecosystems: Hamer et al., "Trusting code in the wild: Exploring contributor reputation measures to review dependencies in the Rust ecosystem," 2024.