# CV-WP-007 — Core Vision Software Architecture Definition & Technology Evaluation

## Type

architecture-definition / technology-evaluation

## Priority

P0

## Status

COMPLETE

## Objective

Convert the CV-WP-006 Software Architecture Discovery into a formal, implementable Core Vision software architecture definition and evaluate current candidate technologies against the established governance, authority, security, operability, portability and maintainability requirements.

CV-WP-007 may produce explicit architecture decisions and ADR candidates.

CV-WP-007 does not authorize implementation until its architecture decisions and material technology choices have passed the required governance review and Human Maintainer authorization.

## Starting position

CV-WP-006 established the following discovery recommendation:

Preferred Architecture:

MODULAR GOVERNANCE MONOLITH

Preferred Runtime:

SERVER-PRIMARY

Recommendation State:

RECOMMENDED / NOT IMPLEMENTATION AUTHORIZED

Technology Selection:

UNSELECTED

CV-WP-007 must evaluate and either:

- formally adopt
- refine
- conditionally adopt
- or reject

the discovery recommendation based on explicit architecture-definition evidence.

The discovery recommendation must not become binding merely because it is the starting point.

## Governing principle

Architecture requirements drive technology evaluation.

Technology preference must not rewrite governance semantics.

Knowledge can be centralized, authority not.

## Binding inputs

CV-WP-007 must remain consistent with:

- CV-WP-003 Ecosystem Architecture & Boundaries
- CV-WP-004 Project Lifecycle, Intake & Cross-Project Governance
- CV-WP-005 Integration Model
- CV-WP-006 Software Responsibility Model
- CV-WP-006 Human / Rule / AI Authority Model
- CV-WP-006 Information and State Model
- CV-WP-006 Software Architecture Options

## Architecture principles

The following remain binding:

1. Standalone First
2. Public Interface First
3. No Implicit First-Party Trust
4. Graceful Absence
5. No Bootstrap Cycles
6. Authority Preservation

## Core authority guardrail

Core Vision software may own canonical state only within the legitimate Core Vision governance domain.

CV-WP-007 must not assign Core Vision authority over:

- NDF development governance
- Core-Dev engineering readiness
- CoreOps current operational state
- Core Brain external source-domain facts
- CDS product-domain semantics
- product-specific behavior
- product business state

unless a separate explicit governance decision legitimately changes the established authority model.

No such authority transfer is assumed by CV-WP-007.

## Required architecture-definition outputs

CV-WP-007 must define:

1. formal application component model
2. internal module responsibilities
3. module dependency rules
4. module contract expectations
5. canonical mutation boundary
6. Human authorization boundary
7. deterministic rule boundary
8. AI analysis boundary
9. evidence boundary
10. external integration boundary
11. history and audit boundary
12. UI / application boundary
13. identity and access boundary
14. deployment topology requirements
15. persistence requirements
16. backup / restore requirements
17. portability requirements
18. observability requirements
19. failure and graceful-degradation requirements
20. evolution and extraction rules

## Formal component model requirement

CV-WP-007 must convert the logical responsibility model into an explicit architecture component model.

Candidate component responsibilities derived from CV-WP-006 include:

- Governance Core
- Portfolio / Lifecycle
- Authority / Capability
- Integration Governance
- Deterministic Rule Evaluation
- Governance Cases / Decisions
- Evidence Boundary
- AI Analysis Boundary
- History / Audit
- Projection / Reporting
- Application / UI Boundary
- External Integration Boundary
- Identity / Access
- Administration / Health

These names remain subject to architecture-definition refinement.

Component definition must not automatically imply independently deployable services.

## Modular-monolith decision requirement

CV-WP-006 recommended a Modular Governance Monolith.

CV-WP-007 must explicitly determine whether that recommendation becomes:

- ADOPTED
- ADOPTED WITH CONDITIONS
- REFINED
- REJECTED

The decision must include rationale.

Until that decision exists, Modular Governance Monolith remains a discovery recommendation.

## Runtime decision requirement

CV-WP-006 recommended server-primary operation.

CV-WP-007 must explicitly evaluate:

- server-primary requirements
- Human Maintainer access
- future multi-actor access
- offline read requirements
- offline mutation requirements
- scheduled integration work
- backup and restore
- Core Vision outage behavior

Server-primary remains recommended, not automatically authorized.

## Canonical governance boundary

The architecture must define one explicit authority boundary for Core Vision-owned canonical governance state unless evidence justifies another model without weakening authority semantics.

The architecture must answer:

- which components may request canonical mutation?
- which component validates mutation authority?
- where are deterministic rules evaluated?
- where is Human authorization verified?
- how are proposed effects distinguished from effective state?
- how are exceptions represented?
- how is history preserved?
- how are concurrent or stale decisions prevented from silently applying?

## Mutation guardrail

Technical write access must not automatically equal governance mutation authority.

The architecture must distinguish:

- persistence access
- application write capability
- validated mutation request
- Human authorization
- deterministic non-discretionary effect
- canonical state mutation

AI must not receive unrestricted direct canonical mutation authority.

## Human authorization architecture

The formal architecture must preserve explicit Human authorization where required.

The architecture must distinguish:

- Human identity
- authentication
- authorization
- Decision Owner
- approval action
- resulting governance effect

Authentication alone must not imply governance authority.

Administrative privilege must not silently imply unrestricted governance approval authority.

## Deterministic rule architecture

The architecture must define how deterministic rules remain:

- identifiable
- versioned
- testable
- explainable
- traceable to authority basis
- distinguishable from AI reasoning
- distinguishable from Human decisions

The architecture must distinguish:

- rule definition
- rule activation
- rule execution
- rule result
- blocking effect
- exception handling

Rule-engine technology remains unselected until technology evaluation.

## AI architecture

AI remains an optional analytical capability.

The formal architecture must define:

- AI provider abstraction requirements
- AI input boundary
- AI output classification
- provenance requirements
- privilege limits
- failure behavior
- AI-disabled behavior
- provider replacement behavior
- canonical-write prohibition
- Human review integration

The architecture must remain operable when AI is unavailable.

No AI provider or model is selected at bootstrap.

## Evidence architecture

The architecture must preserve:

- source provenance
- source-domain authority
- freshness
- unknown state
- stale state
- reference versus retained evidence
- externally authoritative state versus Core Vision canonical state

Evidence architecture should remain reference-first unless retention is justified.

Core Vision must not become a universal ecosystem data lake.

## External integration architecture

External integrations must remain governed by CV-WP-005.

The formal architecture must evaluate adapter or equivalent isolation boundaries for:

- Core Brain
- Core-Dev
- CoreOps
- CDS
- products
- repositories
- other evidence providers

First-party integration must not bypass authentication, authorization or public-contract requirements merely because both systems belong to the Core ecosystem.

## Core Brain boundary

Core Brain may provide Knowledge and Evidence Plane capabilities.

Core Brain must remain optional for Core Vision bootstrap unless later explicitly authorized otherwise.

Core Vision canonical governance state must remain recoverable and usable without Core Brain.

Core Vision and Core Brain must not form a mandatory circular bootstrap dependency.

## Core-Dev boundary

Core-Dev remains the Engineering Control Plane.

Core-Dev may provide engineering readiness evidence.

Core Vision must not become engineering readiness authority merely because it consumes or displays that evidence.

## CoreOps boundary

CoreOps remains the Operations Control Plane.

CoreOps may deploy, monitor or operate Core Vision software through an explicitly governed integration.

Operating Core Vision software must not transfer Core Vision governance authority to CoreOps.

Core Vision must not become the runtime deployment control plane merely because it displays operational information.

## CDS boundary

CDS may provide applicable visual and interaction foundations.

CDS must not become required for Core Vision canonical governance bootstrap.

Presentation authority remains distinct from governance authority.

## Product boundary

Product systems remain independently authoritative for their product-specific behavior and domain semantics.

Core Vision must not become a universal product backend.

## Persistence-definition requirements

Before selecting a persistence technology, CV-WP-007 must make requirements implementable for:

- canonical governance state
- historical governance state
- Human decisions
- authority assignments
- exceptions
- rule definitions
- rule evaluations
- evidence references
- retained evidence where required
- AI analyses
- recommendations
- projections
- search or AI retrieval representations
- cache

The architecture must classify which information is:

- canonical
- durable
- historical
- append-oriented in meaning
- mutable
- supersedable
- reconstructable
- cached
- derived

## History and audit requirements

Material governance changes must remain traceable.

The architecture must support reconstruction of material chains such as:

effective state
→ authorized effect
→ Human decision or explicitly authorized deterministic basis
→ governance case
→ relevant rule results
→ evidence
→ analysis / recommendation where material

CV-WP-007 must determine implementable audit requirements without silently assuming a specific event-sourcing product or pattern.

## Security-definition requirements

CV-WP-007 must define implementable security requirements for:

- Human identity
- system identity
- AI identity
- authentication
- authorization
- Decision Owner verification
- least privilege
- secrets
- external integration trust
- canonical mutation
- administrative access
- audit integrity
- backup access
- restore authority

Security product selection remains a later technology-evaluation decision within CV-WP-007.

## Deployment-definition requirements

The formal architecture must define deployment requirements for the preferred runtime posture.

Candidate requirements include:

- server-primary deployment
- browser-capable Human access
- independent Core Vision outage domain
- backup capability
- restore capability
- upgrade capability
- migration capability
- optional background processing
- external integrations
- AI-disabled mode
- local development
- test environment
- future multi-actor operation

No container or orchestration technology is selected at bootstrap.

## Auxiliary worker guardrail

CV-WP-006 identified auxiliary workers as a possible future evolution path.

CV-WP-007 may define extraction seams.

It must not introduce auxiliary workers merely because distributed processing is technically possible.

A separately deployable worker must have a documented justification such as:

- workload isolation
- security isolation
- reliability isolation
- scheduling
- independent scaling
- long-running execution

Canonical governance authority must not be duplicated into workers.

## Distributed-services guardrail

A distributed capability-service architecture remains a future option.

CV-WP-007 must not adopt distributed services without evidence that the modular-monolith or bounded-worker approaches fail material requirements.

Logical modularity alone is insufficient justification for network distribution.

## Technology evaluation requirement

After architecture requirements are formalized, CV-WP-007 must evaluate current real-world candidate technologies.

Technology categories may include:

- programming language
- backend application framework
- frontend / UI approach
- persistence technology
- migration tooling
- rule / policy technology
- API technology
- background-job technology
- search technology
- AI-provider abstraction
- AI retrieval technology
- authentication / identity approach
- authorization approach
- secrets handling
- deployment packaging
- observability
- testing
- backup and restore

Candidates must be evaluated against Core Vision requirements rather than popularity alone.

## Current-source requirement

Material technology evaluation must use current authoritative sources where practical.

Sources should prefer:

- official documentation
- official repositories
- official release information
- primary technical sources

Material version, support, maintenance and licensing facts must be verified at evaluation time.

## Technology evaluation criteria

Candidate technologies should be assessed against criteria including:

- semantic fit
- architectural fit
- maintainability
- security
- auditability
- testability
- portability
- operability
- Human Maintainer usability
- offline capability where relevant
- migration capability
- backup / restore capability
- dependency risk
- ecosystem lock-in risk
- maturity
- maintenance health
- documentation quality
- long-term support posture
- resource requirements
- integration flexibility
- AI-provider neutrality
- licensing
- future evolution path

Weights must be explicit before final scoring.

## Candidate matrix requirement

Technology comparison must use a documented candidate matrix.

The matrix must distinguish:

- hard requirement
- weighted preference
- risk
- unknown
- assumption
- evidence

Unknown material facts must not silently receive a favorable score.

## ADR requirement

Material architecture or technology decisions should produce ADR candidates where appropriate.

Likely ADR subjects include:

- application architecture
- primary runtime posture
- canonical persistence model
- backend language / framework
- UI architecture
- API boundary
- deterministic rule implementation
- identity / authorization architecture
- AI provider abstraction
- deployment packaging

Not every dependency requires an ADR.

ADR scope must follow materiality.

## Decision states

A candidate architecture or technology decision may be classified as:

- PROPOSED
- RECOMMENDED
- RECOMMENDED WITH CONDITIONS
- REJECTED
- DEFERRED
- ADR REQUIRED
- HUMAN DECISION REQUIRED

A recommendation is not authorization.

## Implementation authorization boundary

CV-WP-007 may complete with a formally approved architecture and technology baseline.

Implementation must not begin merely because a technology matrix exists.

Implementation requires:

- required architecture decisions accepted
- material ADRs accepted where required
- blocking unknowns resolved or explicitly deferred
- security boundary accepted
- persistence boundary accepted
- Human Maintainer authorization to proceed

## Out of scope

CV-WP-007 bootstrap does not:

- implement application code
- create production database schemas
- create production APIs
- create UI code
- deploy Core Vision
- install technology dependencies
- modify other Core repositories
- create production credentials
- create mandatory Core-to-Core integrations
- silently authorize the CV-WP-006 preferred architecture

## Work sequence

CV-WP-007 should proceed in controlled stages:

### Part 1 — Bootstrap & Decision Guardrails

Establish architecture-definition scope and decision rules.

### Part 2 — Formal Component Model

Define explicit application components, responsibilities and permitted dependencies.

### Part 3 — Module Contracts & Mutation Boundaries

Define application contracts, canonical write path, Human authorization, rules, evidence, AI and external-integration boundaries.

### Part 4 — Implementable Architecture Requirements

Define concrete requirements for persistence, history, security, identity, deployment, backup, restore, observability and portability.

### Part 5 — Technology Evaluation

Research current candidate technologies and compare them using an explicit weighted evidence-based matrix.

### Part 6 — Architecture Decisions & Final Review

Produce architecture recommendation, ADR candidates, unresolved decisions, technology baseline recommendation and final review.

## Acceptance criteria

1. Formal component architecture is defined.
2. Component responsibilities are explicit.
3. Component dependency rules are explicit.
4. Canonical mutation boundary is explicit.
5. Human authorization boundary is explicit.
6. Deterministic rule boundary is explicit.
7. AI analysis boundary is explicit.
8. Evidence boundary is explicit.
9. External integration boundary is explicit.
10. History and audit requirements are implementable.
11. Persistence requirements are implementable before product selection.
12. Security and identity requirements are implementable.
13. Deployment requirements are implementable.
14. Backup and restore requirements are explicit.
15. Graceful degradation is defined.
16. CV-WP-003 authority boundaries remain preserved.
17. CV-WP-004 governance semantics remain preserved.
18. CV-WP-005 integration semantics remain preserved.
19. CV-WP-006 Human / Rules / AI separation remains preserved.
20. CV-WP-006 information-state semantics remain preserved.
21. Modular Governance Monolith recommendation is explicitly accepted, refined or rejected.
22. Server-primary recommendation is explicitly accepted, refined or rejected.
23. Technology candidates are evaluated from current evidence.
24. Evaluation weights are explicit.
25. Material unknowns remain visible.
26. Material architecture decisions produce ADR candidates where required.
27. No AI provider gains governance authority.
28. No persistence product gains authority by storage location.
29. No worker duplicates canonical governance authority.
30. Core Vision remains outside the mandatory runtime path of other Core projects.
31. Technology choices follow architecture requirements.
32. Human Maintainer retains final authority over material architecture and implementation authorization.

## Decision guardrail

CV-WP-007 is allowed to move beyond discovery.

It may formally recommend architecture and technology choices.

It may prepare ADR candidates.

It may not silently transform a recommendation into implementation authorization.

The distinction between:

- architecture recommendation
- architecture decision
- technology recommendation
- accepted ADR
- implementation authorization

must remain explicit.

## Human authority

The Human Maintainer retains final authority over:

- adoption of the Core Vision software architecture
- material technology choices
- accepted ADRs
- architecture-principle exceptions
- new mandatory ecosystem dependencies
- authority transfers
- AI autonomy expansion
- security-boundary exceptions
- implementation authorization

AI may research, analyze, compare and recommend.

AI does not independently authorize the Core Vision implementation architecture.
## Architecture Adoption

Adoption Date:

2026-08-09

Final Architecture Adoption Review:

PASS

Human Maintainer Authorization:

EXPLICIT

Accepted Decisions:

- CV-ADR-001 — Application Architecture and Runtime Posture
- CV-ADR-002 — Application Platform and Human UI
- CV-ADR-003 — Canonical Persistence and Data Access
- CV-ADR-004 — Identity and Governance Authorization
- CV-ADR-005 — Deterministic Rules and AI Boundary
- CV-ADR-006 — Operations, Packaging and Evolution

Architecture Baseline:

ADOPTED

Technology Baseline:

ADOPTED

Preferred Architecture:

MODULAR GOVERNANCE MONOLITH

Preferred Runtime:

SERVER-PRIMARY

Preferred Application:

.NET 10 / ASP.NET Core 10

Preferred Persistence:

PostgreSQL 18

Preferred Human UI:

Blazor Web App

Preferred Identity:

ASP.NET Core Identity

Governance Authorization:

CORE VISION-OWNED

Preferred Deterministic Rules:

APPLICATION-NATIVE

Preferred AI Contract:

CORE VISION-OWNED PORT

Implementation:

NOT AUTHORIZED

CV-WP-007 remains ACTIVE until the post-adoption closure review confirms:

- accepted decision integrity
- adopted baseline integrity
- exact Work Package completion state
- next Work Package boundary
- queue and Project Brain reconciliation

Architecture adoption does not itself authorize implementation.
## Closure

Closure Date:

2026-08-09

Closure Review:

PASS

Human Architecture Adoption:

COMPLETE

Accepted Architecture Decisions:

- CV-ADR-001 — Application Architecture and Runtime Posture
- CV-ADR-002 — Application Platform and Human UI
- CV-ADR-003 — Canonical Persistence and Data Access
- CV-ADR-004 — Identity and Governance Authorization
- CV-ADR-005 — Deterministic Rules and AI Boundary
- CV-ADR-006 — Operations, Packaging and Evolution

Architecture:

ADOPTED

Runtime:

ADOPTED

Technology Baseline:

ADOPTED

Architecture Requirements:

189 / PRESERVED

Authority Preservation:

PASS

Canonical Mutation Boundary:

PASS

Human Authorization:

PASS

Rule / AI Separation:

PASS

Implementation Gate:

CLOSED

Implementation:

NOT AUTHORIZED

Closure State:

COMPLETE / FROZEN

Next Planned Work Package:

CV-WP-008 — Implementation Bootstrap Definition & Readiness Gates

CV-WP-008 State:

PLANNED

CV-WP-008 Activation:

NOT AUTHORIZED BY THIS CLOSURE

Implementation Activation:

NOT AUTHORIZED BY THIS CLOSURE

Lessons Learned Candidates:

1. Validator assertions should verify semantic invariants rather than brittle exact prose anchors.
2. System.IO file operations in PowerShell governance scripts should use absolute paths when process working-directory ambiguity is possible.

Lessons Learned Backflow:

CANDIDATE / BATCH LATER

No NDF backflow is required as part of this closure.

Knowledge can be centralized, authority not.
