# Core Portfolio Intake

## 1. Purpose

This document defines how projects, repositories, concepts and candidate capabilities are evaluated for a governed relationship with the Core ecosystem.

Portfolio intake is a governance process.

It does not itself perform software development, repository creation, runtime deployment or product implementation.

## 2. Core intake principle

Discovery is evidence.

Discovery is not admission.

The existence of any of the following does not establish Core portfolio membership:

- a repository
- a local project directory
- a prototype
- a concept document
- a product name
- a GitHub organization relationship
- a dependency on another Core project
- use of Core branding
- an AI recommendation
- implementation activity

Permanent Core portfolio membership requires an explicit governance decision.

## 3. Intake pipeline

The normal intake pipeline is:

1. Discovery
2. Evidence Collection
3. Identity Resolution
4. Classification
5. Strategic Fit Review
6. Capability and Authority Overlap Review
7. Dependency and Risk Review
8. Intake Recommendation
9. Human Decision
10. Portfolio Registration

No earlier stage may silently substitute for a later stage.

## 4. Stage 1 — Discovery

Discovery records that a potentially relevant project, repository, concept or capability exists.

Discovery sources may include:

- Human Maintainer input
- existing Core repositories
- local project inventories
- external repositories
- documentation
- architecture reviews
- product ideas
- ecosystem gap analysis
- AI-assisted research

A discovered item begins without permanent portfolio authority.

Where appropriate, it should initially be treated as an Observed Candidate.

## 5. Stage 2 — Evidence Collection

Material intake decisions require evidence.

Useful evidence may include:

- project purpose
- repository identity
- ownership
- current status
- maturity
- documentation
- implemented capabilities
- planned capabilities
- dependencies
- consumers
- authority claims
- security implications
- lifecycle information
- strategic relevance

Evidence must be distinguishable from:

- assumptions
- proposals
- recommendations
- decisions

Unknown material facts must remain explicitly unknown.

They must not be silently inferred into confirmed facts.

## 6. Stage 3 — Identity Resolution

Before admission review, Core Vision should determine whether the candidate is:

- a distinct project
- a renamed project
- a replacement project
- a fork
- a prototype
- a legacy repository
- a duplicate
- an empty placeholder
- a component of an existing project
- an external dependency rather than a Core project

Identity uncertainty that materially affects authority, ownership or architecture must fail closed.

## 7. Stage 4 — Classification

Classification may include:

- candidate type
- proposed tier
- strategic domain
- likely authority domain
- current portfolio relationship
- lifecycle state where known
- repository status
- maturity
- visibility
- dependency role

Classification is descriptive.

Classification does not by itself grant authority.

A proposed tier is not a confirmed tier until the relevant governance decision accepts it.

## 8. Stage 5 — Strategic Fit Review

The candidate should be evaluated against Core ecosystem strategy.

Questions include:

- Does the candidate solve a real ecosystem problem?
- Is the capability already owned elsewhere?
- Is the capability strategically reusable?
- Is a separate project justified?
- Could the capability remain inside an existing project?
- Would admission simplify or fragment the ecosystem?
- Does the project strengthen clear authority boundaries?
- Does it introduce unnecessary coupling?

Strategic usefulness alone is not sufficient for admission.

## 9. Stage 6 — Capability and Authority Overlap Review

Before permanent admission, Core Vision must identify potential overlap with existing projects.

Review must consider:

- capability ownership
- authority ownership
- data authority
- development governance
- engineering control
- operational control
- design-system authority
- product-domain authority

Overlap is not automatically prohibited.

Unclear authority is prohibited.

If two projects appear to claim the same authoritative domain, permanent admission must fail closed until the boundary is resolved.

## 10. Stage 7 — Dependency and Risk Review

The intake review should identify whether admission would create:

- mandatory coupling
- bootstrap cycles
- hidden database dependencies
- implicit first-party trust
- authority leakage
- duplicate control planes
- operational single points of failure
- unnecessary runtime dependencies
- unclear retirement dependencies

The architecture principles established by Core Vision remain binding:

- Standalone First
- Public Interface First
- No Implicit First-Party Trust
- Graceful Absence
- No Bootstrap Cycles
- Authority Preservation

## 11. Stage 8 — Intake Recommendation

The intake process may produce one of the following recommendations:

### 11.1 Observe

Keep the item as an Observed Candidate.

Use when:

- evidence is insufficient
- strategic relevance is unclear
- no active evaluation is justified

### 11.2 Conditional Exploration

Authorize bounded evaluation without permanent portfolio admission.

Use when:

- the candidate appears strategically relevant
- material questions remain open
- overlap requires further analysis
- architecture implications require exploration

Conditional Exploration does not grant permanent authority.

### 11.3 Admit

Recommend permanent portfolio admission.

This recommendation requires sufficient evidence that:

- project identity is understood
- strategic purpose is justified
- authority boundaries are sufficiently clear
- material overlap is resolved
- dependency risks are acceptable
- governance ownership is identified

Recommendation is not authorization.

### 11.4 Reject

Recommend that the candidate not enter the Core portfolio.

Rejection does not require deletion of historical evidence.

### 11.5 Defer

Suspend the intake decision pending a future dependency, decision or evidence source.

Deferred is not admitted.

## 12. Stage 9 — Human Decision

Permanent portfolio admission requires explicit Human Maintainer approval.

The Human Maintainer may decide:

- OBSERVE
- CONDITIONAL EXPLORATION
- ADMIT
- REJECT
- DEFER

The final decision may differ from the recommendation.

The decision should identify its evidence basis and material unresolved notes.

AI recommendations are advisory.

They are not binding governance decisions.

## 13. Stage 10 — Portfolio Registration

Only after an authorized decision may Core Vision update permanent portfolio records.

Registration should record at least:

- canonical project identity
- portfolio relationship
- tier where decided
- lifecycle state where decided
- authoritative project role
- relevant authority boundaries
- decision reference
- material notes or conditions

Registration must not invent unresolved data merely to complete a schema.

Unknown values remain unknown where governance permits.

## 14. Fail-closed conditions

Permanent admission must not proceed when material uncertainty remains about:

- project identity
- ownership
- authority boundaries
- strategic purpose
- conflicting capability ownership
- mandatory dependency cycles
- irreversible authority transfer
- whether the candidate duplicates an existing authoritative project

The appropriate outcome is normally:

- Observe
- Conditional Exploration
- Defer

Fail-closed does not mean automatic rejection.

It means permanent admission is withheld until the material governance issue is resolved.

## 15. Evidence and decision separation

Core Vision must preserve the distinction between:

- observed fact
- derived assessment
- recommendation
- authorized decision

For example:

A repository existing is an observed fact.

A conclusion that it could solve an ecosystem gap is an assessment.

A proposal to admit it is a recommendation.

Portfolio admission is a decision.

These states must not be collapsed.

## 16. Existing projects

Existing Core projects may be grandfathered into the governed portfolio baseline when their status has already been explicitly established through prior Core Vision work.

Grandfathered status does not exempt them from future:

- authority review
- lifecycle governance
- dependency governance
- architecture review
- retirement governance

Historical admission does not create unlimited future authority.

## 17. External projects and dependencies

A useful external project does not need to become a Core project.

External software may remain:

- inspiration
- dependency
- optional integration
- reference implementation
- comparative benchmark

Core portfolio admission should be reserved for projects that require a governed Core identity and authority role.

## 18. Relationship to NDF

NDF may govern development work after or during project creation.

NDF adoption does not itself grant Core portfolio membership.

Core Vision decides ecosystem portfolio relationship.

NDF governs development methodology within its authorized scope.

## 19. Relationship to Core Brain

Core Brain may retain and relate intake evidence, provenance and decision records.

Core Brain does not decide portfolio admission.

Its knowledge functions must preserve the authority of the original decision owner.

## 20. Relationship to Core-Dev

Core-Dev may provide engineering evidence relevant to intake or maturity assessment.

Engineering readiness does not itself establish portfolio membership.

## 21. Relationship to CoreOps

CoreOps may provide operational evidence relevant to an existing or candidate project.

Deployment or operational presence does not itself establish portfolio membership.

## 22. Human authority

The Human Maintainer retains binding authority over permanent ecosystem admission and removal.

AI systems may:

- discover
- collect evidence
- compare
- classify
- identify overlaps
- detect risks
- prepare recommendations

AI systems do not independently:

- permanently admit a project
- permanently remove a project
- transfer ecosystem authority
- create binding portfolio membership

Knowledge can be centralized, authority not.
