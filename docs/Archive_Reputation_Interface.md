# Archive Reputation Interface

**Status:** Draft — Protocol Reference  
**Scope:** Chronicle / Legacy Protocol — Archive and Reputation Subsystems  
**Stage:** Concept and architecture research  
**Purpose:** Define how Chronicle Archive records inform Reputation interpretation, and explain why Archive and Reputation remain architecturally separate layers

---

## 1. Status

This document is a research-stage architecture specification. It does not define a deployed system, smart contract, token mechanism, production database schema, or scoring algorithm. Its purpose is to close the architectural gap between the Chronicle Archive and the Reputation Graph by defining how information moves between the two layers without collapsing memory into reputation or reputation into rewards.

---

## 2. Purpose

Chronicle / Legacy Protocol depends on two distinct but related layers: the Chronicle Archive and the Reputation Graph. Both layers consume Memory Objects. Both layers are informed by attestation outcomes and lifecycle states. But they serve fundamentally different purposes.

The Archive preserves memory. The Reputation Graph interprets memory.

Without a defined interface between these two layers, the relationship between them remains implicit. Implicit relationships create design risk: the Archive may be treated as a reputation source rather than a memory source, or reputation signals may be assumed to represent archived truth rather than contextual interpretation.

This document makes the Archive–Reputation relationship explicit. It defines what the Archive provides, what the Reputation Graph may derive from it, and what boundaries must remain in place to prevent Archive records from becoming reputation scores and reputation signals from becoming authoritative history.

---

## 3. Scope

This document covers:

- the conceptual interface between the Chronicle Archive and the Reputation Graph;
- the classes of Archive signals that may inform reputation interpretation;
- the Reputation Graph's responsibilities when reading Archive records;
- lifecycle-aware reputation interpretation;
- the downstream flow from Archive and Reputation into Knowledge Inheritance and AI Mentor layers;
- risks and abuse scenarios arising from a poorly defined Archive–Reputation boundary;
- non-goals and research boundaries.

This document does not cover:

- internal Archive architecture (see [Chronicle Archive Model](./Chronicle_Archive_Model.md));
- internal Reputation Graph structure (see [Reputation Graph](./Reputation_Graph.md));
- attestation mechanisms (see [Attestation Model](./Attestation_Model.md));
- Memory Object structure (see [Memory Object Model](./Memory_Object_Model.md));
- AI Mentor retrieval policies (see [AI Mentor Safety Model](./AI_Mentor_Safety_Model.md));
- identity or pseudonymity rules (see [Identity and Pseudonymity Model](./Identity_and_Pseudonymity_Model.md));
- privacy redaction mechanisms (see [Privacy and Disclosure Framework](./Privacy_and_Disclosure_Framework.md)).

---

## 4. Design Principles

**4.1 Archive records are authoritative. Reputation signals are derived.**

An Archive record is a structured preservation of what happened, when it happened, what evidence existed, what attestations were issued, and what the lifecycle status was at a given time. It does not change when reputation changes. Reputation may change as new Archive records appear, as disputes resolve, or as lifecycle states transition. The Archive does not change to reflect reputation.

**4.2 Reputation does not replace memory.**

A contributor's reputation context should always be traceable back to one or more Archive records. If a reputation signal cannot be traced to archived source material, it should be treated as unsupported and excluded from interpretation.

**4.3 Memory precedes reputation.**

No reputation signal should be generated before a Memory Object has been submitted, reviewed, and archived. Unreviewed submissions, draft records, and rejected objects do not generate reputation signals. Reputation is a downstream interpretation of reviewed and preserved memory, not an upstream driver of what gets reviewed.

**4.4 Reputation is contextual, not cumulative.**

Archive records may indicate contribution in documentation, governance, research, infrastructure, education, or community support. The Reputation Graph may derive contextual signals from these records by domain. It must not sum them into a universal contributor score.

**4.5 Disputed and deprecated records remain in the Archive.**

Archive records are not removed when they are disputed or deprecated. They remain as historical context. The Reputation Graph must interpret disputed and deprecated records differently from accepted and verified records. A disputed record is not a negative reputation signal, but it is not a positive one either. It is an uncertain signal with a known source.

**4.6 Privacy constraints are inherited by reputation interpretation.**

If an Archive record has a restricted, redacted, or consent-dependent disclosure level, the Reputation Graph may not use that record to generate publicly visible reputation signals without respecting its privacy constraints. Privacy boundaries defined in the Archive are binding on downstream interpretation.

---

## 5. Archive and Reputation Overview

### Chronicle Archive

The Chronicle Archive is the preservation layer for Memory Objects and their surrounding context. It stores structured records about contributions, decisions, knowledge artifacts, governance events, and mentorship interactions. It tracks source availability, evidence quality, lifecycle transitions, revision history, redaction records, and deprecation status.

The Archive does not evaluate whether a contribution was important. It preserves the record that a contribution occurred, what evidence existed, how it was reviewed, and what its current status is.

### Reputation Graph

The Reputation Graph is a contextual relationship layer built from Memory Objects, attestations, evidence quality assessments, lifecycle states, domain contexts, disputes, and knowledge inheritance relationships. It represents the contribution and review history of ecosystem participants in a way that remains traceable to archived evidence.

The Reputation Graph does not store independent information about contributors. Every signal it holds must correspond to one or more Archive records.

---

## 6. Why Archive and Reputation Are Separate Layers

Conflating the Archive and Reputation layers produces several design failures.

If Archive records automatically generate reputation signals, low-quality records submitted at volume would inflate reputation. If reputation signals could modify Archive records, disputed reputations might erase historical evidence. If the Archive were designed around reputation output rather than memory preservation, it would optimize for legible reputation signals rather than accurate historical records.

Separating the layers allows each to maintain its integrity:

- the Archive can preserve disputed, rejected, and deprecated records without damaging reputation;
- the Reputation Graph can be updated, revised, and reinterpreted as new records appear without altering historical Archive entries;
- a contributor's reputation context may improve or change over time without requiring the Archive to delete older records;
- new readers can always trace a reputation signal back to its Archive source.

---

## 7. Archive Responsibilities

The Archive is responsible for:

- preserving Memory Objects with their lifecycle status, evidence references, attestation records, and revision history;
- tracking evidence availability, including whether source links remain accessible over time;
- maintaining redaction records when sensitive information is removed;
- preserving deprecation records when a Memory Object is superseded;
- preserving dispute records without resolving them;
- maintaining source metadata even when original sources become unavailable;
- providing stable object identifiers that the Reputation Graph and Knowledge Inheritance layer can reference;
- preserving the timestamp context of lifecycle transitions so that reputation interpretation can be time-aware;
- maintaining privacy and disclosure boundaries that downstream layers must respect.

The Archive is not responsible for:

- evaluating whether archived records reflect meaningful contribution;
- computing reputation signals;
- determining how reputation should be interpreted by future contributors or governance processes;
- deciding which records should be surfaced to new contributors.

---

## 8. Reputation Responsibilities

The Reputation Graph is responsible for:

- reading Archive records and deriving contextual relationship signals that describe contributor, reviewer, and domain history;
- respecting lifecycle states when interpreting records;
- respecting privacy and disclosure constraints embedded in Archive records;
- preserving domain-specific reputation context rather than collapsing signals into universal scores;
- tracking dispute history so that disputed reputation signals remain uncertain rather than resolved;
- updating reputation context when new Archive records appear, lifecycle states change, or attestation outcomes are revised;
- providing traceable reputation signals so that future contributors, governance processes, and AI mentor systems can verify the source of any reputation context.

The Reputation Graph is not responsible for:

- preserving original evidence;
- storing Memory Object records;
- making decisions about record validity;
- generating rewards or incentives;
- assigning governance authority.

---

## 9. Archive Signals

The following Archive record properties may be read by the Reputation Graph. These are not automatic triggers. Each type of signal requires interpretation within its lifecycle and privacy context.

| Archive Signal | Description |
|---|---|
| Accepted Memory Object | A Memory Object that reached Accepted lifecycle state with reviewer confirmation |
| Verified Memory Object | A Memory Object with strong, durable, source-linked evidence and limited unresolved disputes |
| Disputed Memory Object | A Memory Object with one or more active challenges to authorship, evidence, scope, or interpretation |
| Archived Memory Object | A Memory Object preserved for historical continuity that may no longer be active guidance |
| Deprecated Memory Object | A Memory Object superseded by a newer record |
| Rejected Memory Object | A Memory Object that did not meet evidence or scope requirements |
| Redacted Archive Record | An Archive record with sensitive fields removed or restricted |
| Revision Event | A lifecycle transition reflecting a correction, update, or reinterpretation |
| Attestation Record | A scoped reviewer statement about a Memory Object, including rationale and scope |
| Dispute Record | A challenge to a Memory Object or attestation, including status and resolution |
| Retrospective Record | A later review of a historical record reflecting updated understanding |
| Lineage Record | A relationship between an earlier and a later Memory Object |

---

## 10. Reputation Signals

The following reputation signals may be derived from Archive records by the Reputation Graph. These signals are contextual and domain-specific. None of them constitute a universal score.

| Reputation Signal | Derivation Source |
|---|---|
| Contribution context in a domain | Accepted or Verified Memory Objects in a specific contribution category |
| Review context in a domain | Accepted or Verified attestations issued by a reviewer, with accurate scope |
| Dispute history | Disputed Memory Objects and unresolved dispute records associated with a contributor or reviewer |
| Correction history | Revision events reflecting corrections made or corrections received |
| Historical contribution trail | A lineage of Memory Objects showing how earlier work informed later knowledge |
| Deprecated contribution context | Memory Objects that were once accepted but are now outdated |
| Inheritance context | Contribution records that later objects inherit, extend, or reference |
| Attestation quality context | The pattern of attestation rationale, scope accuracy, and dispute outcomes over time |

---

## 11. Lifecycle-Aware Reputation Interpretation

Not all Archive records carry the same weight for reputation interpretation. The lifecycle state of a Memory Object determines how the Reputation Graph may read it.

| Lifecycle State | Reputation Interpretation |
|---|---|
| Draft | No reputation signal. Record is not yet submitted for review. |
| Submitted | No positive reputation signal. Record is pending review. |
| Observed | Confirms that activity exists but does not confirm quality or significance. |
| Reviewed | Weak contextual signal. Review occurred but acceptance has not been confirmed. |
| Accepted | May support domain-specific reputation context. Review confirmed scope within stated limits. |
| Verified | May support stronger domain-specific reputation context. Evidence is durable and source-linked. |
| Disputed | Uncertain signal. Active challenge exists. Reputation interpretation should reflect uncertainty. |
| Revised | Depends on revision outcome. A correction that improves the record may carry neutral or positive context. |
| Archived | Historical context. May inform lineage and inheritance but may not reflect current contribution quality. |
| Deprecated | Historical only. Signals that earlier work existed but is no longer active guidance. |
| Rejected | No positive reputation signal. Rejection is not a negative signal by itself, but it is not supportive. |

---

## 12. Relationship to Memory Objects

The Memory Object is the unit of record that the Archive preserves and the Reputation Graph reads.

A Memory Object contains, among other fields:

- a contributor reference;
- a contribution type and domain context;
- evidence links and evidence quality;
- attestation records and attestation scope;
- lifecycle status;
- related objects and lineage relationships;
- privacy and disclosure metadata.

The Archive preserves this structure over time, including its revision history. The Reputation Graph reads the current and historical states of Memory Objects to derive contextual signals.

Neither the Archive nor the Reputation Graph modifies Memory Objects directly. Memory Objects are modified only through documented lifecycle transitions that preserve revision history.

---

## 13. Relationship to Attestation

Attestations are part of Memory Object records. They are preserved in the Archive as structured review statements.

The Reputation Graph may read attestation records to derive reviewer context. A reviewer who has issued many accurate attestations in a domain may carry stronger contextual weight in that domain than a reviewer whose attestations have frequently been disputed or overturned.

However, attestation history is not equivalent to attestation authority. Attestation authority is a separate layer (see [Attestation Authority Model](./Attestation_Authority_Model.md)) that defines scope, accountability, and review weight. The Reputation Graph reads attestation outcomes without redefining attestation authority.

---

## 14. Relationship to Privacy and Disclosure

Archive records may carry privacy and disclosure metadata that restricts how they may be read, inherited, or retrieved.

The Reputation Graph must respect these constraints at the signal derivation step, not only at the display step. If an Archive record has a restricted disclosure level, the Reputation Graph must not derive a publicly visible reputation signal from it without satisfying the disclosure conditions.

Redacted records may still contribute to historical reputation context in a limited form. For example, a record may preserve that an infrastructure contribution occurred without exposing the operational details that were redacted. The reputation signal derived from such a record would reflect that a contribution was made and archived, not what the contribution contained.

Private mentorship records, consent-dependent governance contributions, and sensitive operational records should be handled with additional care. Their presence in the Archive does not automatically make them available for reputation derivation.

---

## 15. Relationship to Identity and Pseudonymity

The Reputation Graph derives signals from Archive records that include contributor references. Contributor references may be pseudonymous. The Reputation Graph must preserve the pseudonymity boundaries defined in the Identity and Pseudonymity Model.

If two Archive records reference the same pseudonymous contributor, the Reputation Graph may treat them as related in the same domain context. If two Archive records cannot be reliably linked to the same contributor, the Reputation Graph must not assume linkage based on similarity of content, timing, or contribution type alone.

Cross-ecosystem identity linkage requires explicit contributor consent or protocol-defined linkage rules, not inference from Archive patterns.

---

## 16. Relationship to Knowledge Inheritance

The Knowledge Inheritance Framework depends on the Archive to provide stable, discoverable records that can be inherited by future contributors.

The Reputation Graph informs Knowledge Inheritance in a limited way: a contributor's reputation context may help future contributors evaluate whether an inherited record came from a source with relevant history. However, reputation context is not a prerequisite for knowledge inheritance. Even a record from a contributor with minimal reputation context may be historically useful and inherit-worthy.

The flow from Archive to Reputation to Knowledge Inheritance is:

```text
Archive
  preserves the Memory Object and its lineage relationships

Reputation Graph
  reads the contributor and reviewer context attached to those objects

Knowledge Inheritance
  selects records for reuse based on content, lifecycle state, and lineage quality
  considers reputation context as supplementary information, not primary selection criteria
```

Knowledge Inheritance must not exclude records solely because their contributor has limited reputation context. A well-evidenced record from a new contributor may be more inherit-worthy than a weakly-evidenced record from a contributor with an extensive reputation trail.

---

## 17. Relationship to AI Mentor

The AI Mentor Layer reads archived records and may surface reputation context as supplementary metadata when helping contributors navigate protocol memory.

The Archive–Reputation interface affects AI Mentor behavior in the following ways:

- the AI mentor should prefer archived records with Verified or Accepted lifecycle status when providing factual guidance;
- the AI mentor should label Disputed records as uncertain rather than omitting them;
- the AI mentor may note that a record came from a contributor with relevant domain context, but must not treat reputation as a substitute for source quality;
- the AI mentor should not amplify reputation signals beyond what the Archive record supports;
- the AI mentor must apply the same privacy and disclosure constraints that the Archive record carries;
- the AI mentor should not infer reputation from patterns in archived records without explicit source links.

The downstream flow is:

```text
Archive ↓
  provides source-linked, lifecycle-aware, privacy-bounded records

Reputation Graph ↓
  provides contextual contributor and reviewer signals derived from those records

Knowledge Inheritance ↓
  provides organized learning paths and lineage references drawn from Archive and informed by Reputation context

AI Mentor
  retrieves and explains source-linked memory using Archive records as primary sources
  treats Reputation and Knowledge Inheritance context as supplementary, not authoritative
```

---

## 18. Conceptual Examples

The following examples illustrate how Archive records and Reputation signals interact across lifecycle and domain contexts. These are not implementation scenarios.

### Example 1: Verified Contribution

A contributor submits a documentation guide. The guide is reviewed by a maintainer, accepted into the Protocol Memory Layer, and later verified with strong evidence links. The Archive preserves the Memory Object with Verified status. The Reputation Graph reads this record and notes that the contributor has a verified documentation contribution in the onboarding domain. This does not give the contributor governance authority. It gives a future reader a traceable reference: this contributor produced this guide, it was reviewed, and the evidence is durable.

### Example 2: Disputed Contribution

A contributor submits a governance participation record. A reviewer disputes the authorship and scope. The Archive preserves both the original record and the dispute record, both marked with their current status. The Reputation Graph reads this situation as an uncertain reputation signal. It notes that a contribution was claimed, evidence was submitted, and a dispute is active. It does not assign a positive or negative reputation signal until the dispute resolves. The AI Mentor, if asked about this contributor's governance history, should surface the uncertainty.

### Example 3: Archived Contribution

A contributor produced infrastructure documentation three years ago. The documentation was accepted and later archived as the infrastructure it described was deprecated. The Archive preserves the record with Archived status. The Reputation Graph reads it as historical contribution context. It may inform a knowledge lineage trail but does not count as current evidence of active contribution. A future contributor who reads about this contributor's infrastructure history should understand that the context is historical.

### Example 4: Inherited Contribution

A contributor wrote an early explanation of a protocol concept. A later contributor extended that explanation into a tutorial. A third contributor translated the tutorial. The Archive preserves all three Memory Objects with lineage relationships. The Reputation Graph may note that the original contributor has an `inherited_from` relationship in the knowledge chain. The Knowledge Inheritance framework sees the full lineage. The AI Mentor may surface all three contributors when explaining how the current tutorial came to exist.

### Example 5: Reputation Interpretation Event

A governance committee is evaluating a research proposal. One reviewer searches for relevant contributor context. The Reputation Graph is queried for the submitter's domain-specific signals in the research and governance categories. It returns a set of Archive references: two accepted research notes, one verified governance discussion record, and one deprecated infrastructure guide. The committee reads the Archive records directly. They treat the reputation signals as navigational context, not as a decision input. The final decision is made by humans reading primary evidence.

### Example 6: Reputation Context with Privacy Constraints

A contributor has three Archive records. Two are public and accepted. One is redacted because it contained sensitive infrastructure information. The Reputation Graph reads all three, derives signals from the two public records, and notes that a third record exists with restricted disclosure. When the AI Mentor is asked about this contributor's history, it notes two accepted records in public context and indicates that additional records exist with restricted visibility. It does not reveal redacted content. Reputation context derived from restricted records is not surfaced beyond what the disclosure level permits.

### Example 7: Historical Contribution Trail

A contributor who helped establish early documentation practices in an ecosystem has fifteen archived Memory Objects spanning five years. Some are Verified. Some are Deprecated. Two are Disputed with unresolved status. The Reputation Graph reads this trail and produces a contextual history: strong early documentation context, some deprecated records from earlier ecosystem phases, and two records where uncertainty remains. A new contributor who wants to understand the ecosystem's documentation history may find this trail useful. The trail does not make the original contributor an authority. It makes their work discoverable and contextually interpretable.

---

## 19. Reputation Interpretation Boundaries

The Reputation Graph must not:

- generate reputation signals from Draft, Submitted, or Rejected Memory Objects;
- treat Archived records as current contribution evidence;
- treat Deprecated records as active guidance;
- convert disputed signals into negative reputation without resolution;
- assign universal scores by summing domain signals;
- use reputation signals as substitutes for direct evidence review;
- bypass privacy or disclosure constraints embedded in Archive records;
- infer contributor identity from Archive patterns without explicit linkage consent;
- treat attestation count as a direct reputation multiplier;
- make governance or review decisions based on reputation signals alone.

---

## 20. Risks and Abuse Scenarios

| Risk | Description | Possible Safeguard |
|---|---|---|
| Volume-driven reputation | Contributors submit many low-quality records to accumulate Archive presence | Lifecycle gating: only Accepted and Verified records contribute to contextual signals |
| Archive reinterpretation | Actors attempt to reframe disputed records as positive reputation context | Lifecycle-aware interpretation rules applied at the Reputation layer |
| Collusion signal laundering | A group submits mutually attesting records to create archive depth | Attestation relationship tracking and reviewer domain limits |
| Privacy boundary bypass | Reputation signals expose information from restricted Archive records | Disclosure-aware signal derivation enforced before signal output |
| Pseudonym linkage inflation | Records from different pseudonyms are assumed to belong to the same contributor | Explicit linkage rules; no inference-based identity linking |
| Historical record as current authority | Old Archived records are used to claim current expertise or governance authority | Lifecycle status surfaced alongside all reputation context |
| Deprecated record omission | Deprecated records are hidden from reputation trails to appear more credible | Reputation trails must include deprecated records with clear labeling |
| Reputation as memory substitute | AI or governance processes use reputation signals instead of reading primary Archive records | Reputation signals must always link back to Archive records; primary review remains required |

---

## 21. Non-Goals

This document is not:

- a scoring model for contributors;
- a formula for computing reputation weights;
- a token or incentive design;
- a smart contract specification;
- a production database schema;
- an authorization model for governance participation;
- a ranking system for identifying important contributors;
- a privacy product design;
- a claim that any Archive-Reputation interface currently exists in deployed form.

The goal of this document is to define the conceptual interface between two Chronicle layers so that future specification work can be grounded in an explicit design rather than an implicit assumption.

---

## 22. Open Research Questions

1. What minimum lifecycle state should be required before an Archive record contributes to any reputation signal?
2. How should the Reputation Graph handle Archive records from contributors who have requested pseudonym separation or identity revision?
3. When a dispute resolves in favor of the original contributor, how should the Reputation Graph update its signals?
4. When a dispute results in rejection, should the Reputation Graph preserve that the record existed, or treat it as invisible?
5. How should the downstream layers — Knowledge Inheritance and AI Mentor — surface the difference between reputation context derived from Verified records versus context derived from Archived or Deprecated records?
6. What privacy review mechanism should determine whether a restricted Archive record may contribute to a domain reputation signal even in limited form?
7. How should the Reputation Graph handle Archive records that are later redacted after initial reputation signals were derived?
8. Can the Archive–Reputation interface support cross-ecosystem contributors without requiring identity linkage across ecosystems?
9. How should the downstream flow change when a Memory Object moves from Archived to Superseded by a newer record?
10. What governance process should define the rules for which Archive signals may be used by which downstream systems?

---

*Chronicle Legacy Protocol — Protocol Reference Documentation*
