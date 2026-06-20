# Attestation Authority Model

**Document:** `docs/Attestation_Authority_Model.md`  
**Status:** Draft — Protocol Reference  
**Scope:** Chronicle Protocol Memory Layer — Attestation Subsystem

---

## 1. Overview

The Chronicle Protocol Memory Layer treats knowledge as a living structure: Memory Objects are proposed, refined, linked, and inherited over time. For this structure to remain reliable, not all voices can carry equal weight in validating knowledge claims. The Attestation Authority Model defines how the right to issue, endorse, or contest attestations is earned, measured, maintained, and — when necessary — curtailed.

An **attestation** is a formal act by which a Reviewer asserts that a Memory Object meets defined quality, accuracy, or contextual standards. The authority to issue such assertions is not granted universally; it is earned through demonstrated engagement, calibrated over time, and subject to review.

This document describes:

- the structural tiers of attestation authority;
- the conditions under which authority is acquired and reduced;
- the metrics used to assess authority quality;
- the reputation mechanisms that tie attestation behaviour to long-term standing;
- the processes for dispute, appeal, and enforcement.

---

## 2. Definitions

| Term | Definition |
|---|---|
| **Memory Object** | A discrete, versioned unit of knowledge stored in the Protocol Memory Layer. |
| **Attestation** | A signed, structured assertion by a Reviewer about the validity, accuracy, or quality of a Memory Object or a specific version thereof. |
| **Reviewer** | A protocol participant with at least a minimal level of earned attestation authority. |
| **Attestation Authority** | The scope and weight of attestations a Reviewer is permitted to issue. |
| **Authority Score** | A computed numeric representation of a Reviewer's current attestation authority level. |
| **Reputation Layer** | The system-wide record of each contributor's cumulative behavioural history, used across multiple protocol subsystems. |
| **Knowledge Inheritance** | The mechanism by which derived or child Memory Objects carry provenance references to their source objects. |
| **Dispute Window** | The time period during which a contested attestation may be formally challenged. |

---

## 3. Principles

**3.1 Authority Is Earned, Not Assigned**

No participant begins with attestation authority. Authority accrues through observable behaviour: contributions, prior attestations that have aged well, domain engagement, and peer review. The protocol does not grant authority by role, title, or identity claim.

**3.2 Authority Is Domain-Scoped**

Authority earned in one knowledge domain does not automatically transfer to another. Cross-domain authority may be inherited in part when domains overlap, but the transfer coefficient is bounded and explicit.

**3.3 Authority Is Probabilistic, Not Absolute**

No attestation carries unconditional weight. Every attestation is treated as a signal with an associated confidence value derived from the issuing Reviewer's Authority Score, domain match, historical calibration, and recency.

**3.4 Authority Is Accountable**

Every attestation creates a persistent, attributable record. A Reviewer's future authority depends in part on the downstream quality of their past attestations.

---

## 4. Attestation Tiers

### Tier 0 — Observer
- **Permissions:** May flag Memory Objects; may submit corrections. Cannot issue attestations.
- **Authority Score Range:** 0 – 99

### Tier 1 — Associate Reviewer
- **Eligibility:** Minimum accepted contributions; at least one valid peer attestation.
- **Permissions:** May issue attestations in established domains. Low base weight.
- **Authority Score Range:** 100 – 299

### Tier 2 — Reviewer
- **Eligibility:** Sustained contribution history; demonstrated calibration accuracy; no active suspension.
- **Permissions:** Standard attestations across established and adjacent domains. May initiate disputes.
- **Authority Score Range:** 300 – 599

### Tier 3 — Senior Reviewer
- **Eligibility:** Longitudinal track record; high calibration score; dispute panel participation.
- **Permissions:** Elevated base weight attestations. Neutral party in Tier-1/2 dispute panels.
- **Authority Score Range:** 600 – 849

### Tier 4 — Principal Reviewer
- **Eligibility:** Sustained Senior Reviewer standing; peer-nominated; no major integrity events.
- **Permissions:** Maximum base weight. High-stakes dispute panels. Co-signs revocation proposals.
- **Authority Score Range:** 850 – 1000

---

## 5. How Attestation Authority Is Earned

### 5.1 Contribution Acceptance
Accepted Memory Objects increase domain-specific authority first; a secondary fraction accrues to the global Authority Score.

### 5.2 Attestation Calibration Over Time
The protocol tracks whether past attestations aged well.

```
Calibration(r, d) = Σ [ weight(a) × outcome(a) ] / Σ weight(a)
```

Where `outcome(a)` is a value in `[-1, 1]` reflecting retrospective accuracy.

### 5.3 Peer Recognition
Attestations endorsed by higher-tier Reviewers as well-reasoned generate a peer recognition bonus.

### 5.4 Dispute Participation
Panel decisions consistent with long-run outcomes generate an authority contribution. Consistent losing positions generate a calibration penalty.

### 5.5 Domain Depth
Sustained domain engagement increases the domain-specific authority multiplier.

---

## 6. Authority Quality Metrics

### 6.1 Volume Score
```
Volume Score = min( accepted_attestation_count, V_cap ) / V_cap × 100
```

### 6.2 Calibration Score
```
Calibration Score = Calibration(r, d) × 300    [range: 0–300]
```

### 6.3 Recency Score
```
Recency Score = 100 × e^( -λ × days_since_last_valid_attestation )
```

### 6.4 Domain Match Score
```
Effective Weight = base_weight × domain_match_coefficient(r, B)
```
`domain_match_coefficient` is 1.0 for established domains, fractional for adjacent, 0.1 for unestablished.

### 6.5 Integrity Score
Starts at maximum; reduced by bad faith findings, withdrawn attestations, and sustained dispute losses.

```
Authority Score = f( Volume Score, Calibration Score, Recency Score, Integrity Score )
```

---

## 7. Reviewer Reputation and the Reputation Layer

### 7.1 Bidirectional Influence
Attestation authority affects Reputation Layer standing, and Reputation Layer standing affects the trust coefficient applied to a Reviewer's attestations.

### 7.2 Knowledge Inheritance and Reputation Propagation
When a Memory Object is inherited into a child object, parent attestations carry forward with a decay coefficient. Parent Reviewers' records are updated when derived object quality is later assessed.

### 7.3 Reputation Recovery
Recovery is not instantaneous. The Reputation Layer applies a weighted moving average; a single run of good attestations does not immediately restore lost standing.

---

## 8. Detection and Limitation of Malicious or Low-Quality Reviewers

### 8.1 Pattern Detection
- **Cluster attacks:** Coordinated attestations on the same object from Reviewers with shared mutual endorsement history.
- **Endorsement rings:** A closed set consistently attesting to each other's contributions.
- **Velocity abuse:** Attestation rate inconsistent with genuine review.
- **Domain inflation:** Repeated attesting outside established domains without accuracy history.

Detected patterns result in **provisionally weighted** attestations with reduced effective weight.

### 8.2 Sybil Resistance
Authority requires genuine engagement over time. Multiple coordinated accounts must each independently build authority through calibrated behaviour.

### 8.3 Automatic Soft Limits
If attestation loss rate exceeds a threshold within a rolling window, a **soft limit** caps attestation weight for a cooling-off period.

### 8.4 Mandatory Review Threshold
Reviewers accumulating contested attestations above a threshold are placed on the **Mandatory Review List** — subsequent attestations route to Tier-3/4 Reviewers before taking effect.

---

## 9. Dispute Handling

### 9.1 Grounds for Dispute
1. **Factual inaccuracy:** Attested object contains demonstrably incorrect claims.
2. **Scope error:** Attestation issued outside the Reviewer's established domain.
3. **Procedural violation:** Issued without adequate review (e.g., during a velocity event).
4. **Conflict of interest:** Documented relationship constituting a conflict under protocol guidelines.
5. **Bad faith:** Evident intent to mislead, suppress knowledge, or manipulate standing.

### 9.2 Dispute Window
Formal disputes must be filed within the defined Dispute Window. After closure, systematic re-evaluation remains possible but individual dispute process is unavailable.

### 9.3 Dispute Process Flow

```
[Dispute Filed]
       |
       v
[Triage: completeness and valid grounds check]
       |
       +-- Invalid --> [Dismissed; Reviewer notified]
       |
       v
[Three-member panel: Tier-3/4 Reviewers not involved in original attestation]
       |
       v
[Evidentiary review: Memory Object, attestation record, Reviewer history]
       |
       v
[Panel majority finding]
       |
       +-- Upheld --> [Challenger receives calibration note]
       |
       +-- Overturned --> [Integrity Score reduced; attestation downweighted or voided]
                 |
                 +-- [Bad faith] --> [Suspension process: Section 10]
```

### 9.4 Appeal
One appeal permitted within a defined period; requires new argument or newly surfaced evidence. Evaluated by a non-overlapping expanded panel.

### 9.5 Effect on Knowledge Inheritance
Overturned attestations cause all inheriting Memory Objects to carry a provisional flag until re-attested or the chain is re-evaluated.

---

## 10. Revocation, Reduction, and Suspension of Authority

### 10.1 Authority Reduction
Automatic outcome of calibration failure. No formal process required. Reversible through improved performance.

### 10.2 Temporary Suspension
Conditions:
- Bad faith finding by a dispute panel.
- Repeated soft-limit triggers within a rolling window.
- Pattern detection identifying participation in a coordinated manipulation event.

During suspension, attestations downweighted to minimum effective weight. Tier classification retained; attestation rights suspended.

### 10.3 Permanent Revocation
Requires:
- Co-signature by a minimum number of Tier-4 Reviewers;
- Full evidentiary panel review;
- Finding of sustained bad faith, systematic manipulation, or single egregious act corrupting significant Knowledge Objects.

Existing attestations retroactively downweighted; contributions flagged. Reputation Layer reflects revocation permanently. Reinstatement requires a new full review and affirmative Tier-4 panel vote after a minimum waiting period.

### 10.4 Domain-Scoped Revocation
Where bad-faith actions were domain-specific: Reviewer retains authority in other domains, permanently excluded from the affected domain.

---

## 11. Interaction with the Reputation Layer

| Event | Attestation Effect | Reputation Layer Effect |
|---|---|---|
| Attestation accepted, ages well | Calibration score increase | Positive signal in knowledge validity dimension |
| Attestation overturned in dispute | Calibration + Integrity Score decrease | Negative signal; permanent dispute record |
| Dispute panel ruling consistent with outcome | Minor authority bonus | Peer trust signal in governance dimension |
| Placed on Mandatory Review List | Secondary sign-off required | Flagged status visible in contributor profile |
| Suspended | Authority non-exercisable for suspension period | Active suspension flag in Reputation Layer |
| Permanently revoked | All attestations retroactively downweighted | Revocation permanently recorded; affects all dimensions |
| Knowledge Inheritance attested | Parent Reviewer receives downstream attribution | Reputation Layer tracks lineage contributions |

---

## 12. Example Scenarios

### Scenario A — Legitimate Authority Accumulation
A participant at Tier 0 submits Memory Objects in computational linguistics. Three are accepted and receive peer attestations. Authority Score crosses 100 (Tier 1). Attestations age well; Calibration Score rises. After 14 months, score reaches 340 (Tier 2). Dispute panel participation aligns with eventual findings. Score continues to rise.

### Scenario B — Domain Boundary Violation
A Tier-3 Reviewer in structural engineering attests to biochemistry objects. Domain match coefficient is 0.15 — effective weight is very low. Pattern detection flags velocity anomalies. Attestations are provisionally weighted pending calibration assessment in that domain.

### Scenario C — Coordinated Ring Detection
Four Tier-1 Reviewers consistently attest to each other's objects within hours of submission. Pattern detection flags the cluster. No attestation history outside the ring is found. All four placed on Mandatory Review; ring-sourced attestations retroactively downweighted.

### Scenario D — Dispute and Overturning
A Tier-2 Reviewer attests to a legal studies object containing a mischaracterised judicial precedent. A Tier-3 Reviewer disputes it with primary source evidence. Panel finds attestation was issued without adequate primary-source review. Overturned. Integrity Score reduced; Authority Score drops from 420 to 381.

### Scenario E — Suspension and Partial Recovery
A Tier-3 Reviewer is found to have suppressed competing Memory Object interpretations. Bad faith finding issued; 90-day suspension. Authority Score drops from 720 to 490 (Tier 2). Over 26 months of accurate, good-faith attestations, score recovers to Tier 3. The bad faith event remains permanently in the Reputation Layer record.

---

## 13. Governance and Evolution of This Model

All parameters — threshold values, score weights, suspension durations, tier boundaries — are defined in the Protocol Specification and subject to the standard governance process. Changes require a proposal, consultation period, and ratification.

Implementors should always consult the versioned Protocol Specification for current parameter values.

---

## 14. Summary

The Attestation Authority Model creates a reliable, self-correcting attestation environment within the Chronicle Protocol Memory Layer:

- Authority is earned through demonstrated, calibrated behaviour over time.
- Attestations carry probabilistic weight, not absolute authority.
- Domain specificity prevents authority earned in one area from being misapplied to another.
- The calibration mechanism holds Reviewers accountable to the long-run quality of their judgements.
- Pattern detection and automatic soft limits contain the impact of bad actors without requiring centralised adjudication for every case.
- Dispute processes provide a structured mechanism for contesting specific attestations.
- The most severe sanctions require formal processes with multiple reviewers involved.
- All outcomes propagate into the Reputation Layer, creating a unified longitudinal record.

The model is conservative by design: it is harder to gain high authority than to lose it, and harder to restore lost authority than to maintain it.

---

*Chronicle Legacy Protocol — Internal Reference Documentation*
