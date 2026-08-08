# Core Project Lifecycle

## 1. Purpose

This document defines how Core Vision represents the lifecycle of projects without confusing lifecycle state with portfolio membership.

The model is governance-oriented.

It does not replace project-local development governance, runtime operations or product ownership.

## 2. Two-axis model

Every governed project must be understood through two separate axes:

1. Portfolio relationship
2. Lifecycle state

These axes answer different questions.

Portfolio relationship answers:

> What relationship does this project currently have to the Core ecosystem?

Lifecycle state answers:

> What is the current lifecycle condition of the project itself?

A project may change on either axis without automatically changing on the other.

## 3. Portfolio relationship

### 3.1 Observed Candidate

An Observed Candidate is known to Core Vision but is not a Core portfolio member.

Examples include:

- discovered repositories
- externally inspired project concepts
- placeholder repositories
- experimental ideas
- projects awaiting identification or classification

Repository existence alone is insufficient for admission.

Observed Candidate does not grant:

- Core authority
- Core branding entitlement
- mandatory integration status
- dependency rights
- architectural authority

### 3.2 Conditional Exploration

Conditional Exploration is a governed evaluation relationship.

It permits structured investigation without permanent portfolio admission.

A Conditional Exploration project:

- may be assessed against Core strategy
- may receive provisional classification
- may participate in bounded architecture analysis
- may be compared with existing Core capabilities
- may be rejected without becoming a permanent Core project

Conditional Exploration does not imply:

- confirmed portfolio membership
- production commitment
- roadmap commitment
- permanent tier assignment
- permanent authority ownership
- mandatory dependency status

Transition from Conditional Exploration to Confirmed requires an explicit Core Vision / Human Maintainer admission decision.

### 3.3 Confirmed

Confirmed means that the project has been explicitly admitted to the Core portfolio.

Confirmation establishes portfolio membership.

It does not automatically establish:

- lifecycle state
- production readiness
- implementation completeness
- runtime deployment
- release status

A Confirmed project remains governed by its own authorized project authority boundaries.

## 4. Lifecycle states

Lifecycle states are independent from portfolio relationship.

### 4.1 Planned

The project is intentionally accepted for future or preparatory work but is not yet under active execution.

Typical characteristics:

- scope exists at a governance level
- work may be queued
- implementation may not have started
- project-local governance may still require bootstrap

### 4.2 Active

The project is under authorized current work.

Active does not mean:

- production-ready
- deployed
- released
- operationally healthy

Those meanings belong to project-local engineering and operational authorities.

### 4.3 Paused

Authorized work is intentionally suspended.

A paused project:

- retains its historical decisions
- retains its authority boundaries
- retains its portfolio relationship unless separately changed
- must not be treated as abandoned merely because work is suspended

Resumption requires an explicit governance decision at the appropriate authority level.

### 4.4 Retiring

The project is in a controlled transition toward retirement.

Retiring may include:

- migration planning
- consumer transition
- dependency removal
- authority reassignment
- evidence preservation
- replacement planning

Retiring does not permit silent transfer of authority to another project.

Any authority transfer must be explicit.

### 4.5 Retired

The project is no longer an active development target.

Historical governance records, decisions, provenance and relevant evidence remain preserved.

Retired does not mean deleted.

A retired project may remain:

- documented
- inspectable
- referenceable
- historically authoritative for past decisions

Current authority must be explicitly reassigned where necessary.

### 4.6 Archived

Archived is the terminal preservation state for projects no longer expected to return to active work.

Archival emphasizes historical preservation.

Archived projects must not silently regain active authority.

Reactivation from Archived requires an explicit new governance decision and should normally be treated as a new lifecycle authorization.

## 5. Allowed lifecycle transitions

The normal lifecycle progression is:

Planned -> Active -> Retiring -> Retired -> Archived

Additional governed transitions include:

- Planned -> Paused
- Active -> Paused
- Paused -> Active
- Paused -> Retiring
- Planned -> Retiring
- Retired -> Archived

Transitions do not occur automatically because of age, repository inactivity or missing releases.

## 6. Non-automatic transitions

The following observations alone do not change lifecycle state:

- repository inactivity
- lack of commits
- lack of releases
- missing deployment
- inactive maintainers
- existence of a replacement project
- project renaming
- repository archival on a hosting platform

Evidence may trigger review.

Evidence does not itself perform the governance transition.

## 7. Portfolio and lifecycle combinations

Valid examples include:

| Portfolio relationship | Lifecycle state | Meaning |
|---|---|---|
| Observed Candidate | Planned | Known candidate, not admitted |
| Conditional Exploration | Planned | Governed exploration before admission |
| Conditional Exploration | Active | Active bounded evaluation, still not permanently admitted |
| Confirmed | Planned | Portfolio member awaiting active work |
| Confirmed | Active | Portfolio member under current work |
| Confirmed | Paused | Portfolio member with suspended work |
| Confirmed | Retiring | Portfolio member undergoing controlled retirement |
| Confirmed | Retired | Former active project retained for governance history |
| Confirmed | Archived | Historical Core project preserved as archive |

The existence of a valid combination does not mean every project must pass through every combination.

## 8. Admission and lifecycle are separate decisions

Permanent portfolio admission is not equivalent to lifecycle activation.

For example:

A project may be:

- Confirmed + Planned
- Confirmed + Paused
- Conditional Exploration + Active

Therefore:

- admission must not automatically set Active
- Active must not automatically grant Confirmed membership
- retirement must not silently remove historical portfolio identity
- archival must not erase provenance

## 9. Authority preservation

Lifecycle transitions must preserve authority clarity.

A transition must identify:

- current authoritative owner
- affected capabilities
- affected consumers
- whether authority changes
- whether dependencies change
- whether historical evidence must remain accessible

If authority ownership becomes unclear, the transition must fail closed pending governance review.

## 10. Relationship to NDF

Core Vision governs ecosystem portfolio lifecycle.

NDF governs how development work is structured and controlled inside participating software projects.

Core Vision lifecycle state must not replace:

- NDF Work Package state
- project-local Decision state
- project-local ADR state
- release readiness
- implementation status

A project being Active in Core Vision does not mean all project-local work is active.

## 11. Relationship to Core-Dev

Core-Dev may expose engineering health and readiness information.

Such information may inform lifecycle review.

Core-Dev does not independently change Core Vision lifecycle state.

## 12. Relationship to CoreOps

CoreOps may provide operational state and deployment evidence.

Operational state may inform lifecycle review.

CoreOps does not independently admit, retire or archive a project in the Core portfolio.

## 13. Relationship to Core Brain

Core Brain may retain and relate lifecycle evidence, decisions and provenance.

Core Brain does not independently perform lifecycle transitions or portfolio admission.

Knowledge can be centralized, authority not.

## 14. Human authority

The Human Maintainer retains binding authority for irreversible ecosystem-level lifecycle decisions, including:

- permanent portfolio admission
- permanent portfolio removal
- irreversible authority transfer
- final retirement where authority must move
- archival decisions with ecosystem consequences

AI systems may prepare evidence, detect inconsistencies and recommend transitions.

They do not independently execute irreversible governance decisions.
