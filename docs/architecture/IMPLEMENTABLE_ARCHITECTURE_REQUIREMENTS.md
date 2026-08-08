# Core Vision Implementable Architecture Requirements

## 1. Purpose

This document converts the Core Vision architecture discovery, component model and module contracts into implementable technology-neutral requirements.

These requirements form the evaluation baseline for CV-WP-007 Part 5.

Technology candidates must be evaluated against these requirements.

Technology candidates must not redefine these requirements merely to improve their evaluation score.

Knowledge can be centralized, authority not.

## 2. Requirement classes

Every architecture requirement belongs to one of the following classes.

### HARD

A HARD requirement is mandatory.

A technology or architecture candidate that cannot satisfy a HARD requirement without violating established Core Vision governance is not acceptable for the affected role.

### STRONG

A STRONG requirement represents an important architectural preference.

A candidate may remain viable if the requirement is not fully satisfied, but the deficiency must be explicitly scored, justified and risk-assessed.

### DESIRABLE

A DESIRABLE requirement improves maintainability, usability, portability or evolution but is not by itself an architecture gate.

### DEFERRED

A DEFERRED matter requires later evidence or implementation design and must not be silently scored as satisfied.

## 3. Evidence states for technology evaluation

Part 5 must classify technology evidence using explicit states.

Candidate states include:

- VERIFIED
- PARTIALLY VERIFIED
- UNKNOWN
- NOT SUPPORTED
- NOT APPLICABLE

UNKNOWN is not a favorable result.

UNKNOWN must not silently receive the same score as VERIFIED.

## 4. Architecture evaluation principle

Part 5 must use two evaluation layers:

### Layer 1 — Hard-gate evaluation

A candidate is first tested against applicable HARD requirements.

A candidate that materially fails a HARD requirement is:

- rejected for that role
- or explicitly retained only as a conditional comparison candidate with the failure visible

### Layer 2 — Weighted evaluation

Candidates that pass or conditionally survive the hard gates may be compared using weighted quality criteria.

A high weighted score must not override a failed HARD authority or security requirement.

## 5. Canonical architecture baseline

The current reference architecture remains:

- Modular Governance Monolith — RECOMMENDED / NOT YET FORMALLY ADOPTED
- Server-primary — RECOMMENDED / NOT YET FORMALLY ADOPTED
- Technology Selection — UNSELECTED
- Implementation — NOT AUTHORIZED

Part 5 technology evaluation must not silently convert this status into formal adoption.

## 6. Requirement family — Canonical Governance State

### CV-AR-CAN-001 — Single canonical mutation boundary

Class: HARD

Every effective mutation of Core Vision-owned canonical governance state must cross one controlled Canonical Governance Core boundary.

No UI, AI, external integration, projection, worker or administration path may provide an equivalent bypass.

### CV-AR-CAN-002 — Canonical ownership scope

Class: HARD

Canonical persistence must represent only legitimate Core Vision-owned governance state as authoritative.

Storage of external state must not transfer source-domain authority.

### CV-AR-CAN-003 — Proposed versus effective state

Class: HARD

The implementation must distinguish proposed governance effects from effective canonical governance state.

Proposal creation must not itself mutate target state.

### CV-AR-CAN-004 — Atomic governance effect

Class: HARD

A material governance effect that semantically represents one decision must become effective as one consistent state transition.

Partial success must not be reported as successful completion.

### CV-AR-CAN-005 — Expected-state validation

Class: HARD

Material mutations must support verification that expected current canonical state has not materially changed before application.

### CV-AR-CAN-006 — Explicit conflict result

Class: HARD

Conflicting concurrent mutations must produce an explicit conflict outcome rather than silent last-writer-wins behavior unless such behavior is explicitly governed for that domain.

### CV-AR-CAN-007 — Stable canonical identity

Class: HARD

Canonical governance objects require stable identity independent of mutable display names, repository locations or external identifiers.

### CV-AR-CAN-008 — Transactional integrity

Class: HARD

The persistence architecture must support a consistency mechanism sufficient to preserve atomic material governance effects and required linked state changes.

This requirement does not prescribe a specific transaction technology.

## 7. Requirement family — History and Audit

### CV-AR-AUD-001 — Durable material history

Class: HARD

Material governance decisions, authority changes, exceptions and canonical effects require durable history.

### CV-AR-AUD-002 — Decision-to-effect traceability

Class: HARD

The implementation must support reconstruction from material effective state to its legitimate authority basis.

The chain may include:

- effective state
- authorized effect
- Human decision or authorized deterministic basis
- governance case
- rule evaluations
- evidence
- analysis or recommendation where material

### CV-AR-AUD-003 — Audit failure fail-closed

Class: HARD

Where required audit persistence cannot be guaranteed for a material authoritative mutation, the mutation must not silently succeed without the required audit record.

### CV-AR-AUD-004 — Historical meaning preservation

Class: HARD

Historical records must preserve their original governance meaning.

Corrections must not silently rewrite prior history as if the original record never existed.

### CV-AR-AUD-005 — Current versus historical query distinction

Class: HARD

Historical state must remain distinguishable from currently effective canonical state.

### CV-AR-AUD-006 — Rule revision traceability

Class: HARD

Historical deterministic evaluations must identify the rule revision that produced the result.

### CV-AR-AUD-007 — AI provenance traceability

Class: STRONG

Material AI analysis used during governance review should retain sufficient provenance to identify its significant inputs and execution identity where appropriate.

Hidden model reasoning is not required to be persisted.

## 8. Requirement family — Deterministic Rules

### CV-AR-RUL-001 — AI-independent deterministic evaluation

Class: HARD

Deterministic governance rule evaluation must remain functional without AI.

### CV-AR-RUL-002 — Rule definition identity

Class: HARD

Rule definitions require stable identity and revision semantics.

### CV-AR-RUL-003 — Rule lifecycle distinction

Class: HARD

The architecture must distinguish rule definition, review, activation, execution and retirement.

### CV-AR-RUL-004 — Rule authority basis

Class: HARD

A binding rule must be traceable to an accepted governance authority basis.

### CV-AR-RUL-005 — Reproducible evaluation

Class: HARD

The same rule revision and materially equivalent governed inputs should produce the same deterministic result.

### CV-AR-RUL-006 — Explainable result

Class: HARD

A material rule evaluation must expose enough information to explain:

- rule identity
- rule revision
- result
- reason
- authority basis
- relevant inputs
- blocking effect

### CV-AR-RUL-007 — Explicit UNKNOWN

Class: HARD

Missing material information must be representable as UNKNOWN and must not be silently converted into PASS.

### CV-AR-RUL-008 — Rule PASS not approval

Class: HARD

A passing deterministic rule must not replace required Human authorization.

### CV-AR-RUL-009 — Exception-aware evaluation

Class: HARD

Where governance permits exceptions, deterministic evaluation must be able to distinguish a valid governed exception from an undocumented bypass.

## 9. Requirement family — Human Authorization

### CV-AR-HUM-001 — Explicit Human authorization action

Class: HARD

Human approval must be represented as an explicit distinguishable action.

### CV-AR-HUM-002 — Authentication separate from authority

Class: HARD

Authentication must not itself imply governance authority.

### CV-AR-HUM-003 — Decision Owner verification

Class: HARD

The architecture must support verification that the actor is eligible to authorize the relevant decision domain.

### CV-AR-HUM-004 — Authorization-context binding

Class: HARD

Material authorization must be bound to sufficient decision context to prevent replay against unrelated future effects.

### CV-AR-HUM-005 — Stale authorization detection

Class: HARD

The implementation must detect when material canonical state changes invalidate or stale a previously issued authorization before its effect is applied.

### CV-AR-HUM-006 — Administrative privilege separation

Class: HARD

Technical administrator privilege must not automatically imply unrestricted governance decision authority.

### CV-AR-HUM-007 — Human attribution

Class: HARD

Material Human decisions must retain attributable actor identity and authorization context.

## 10. Requirement family — Idempotency and Retry Safety

### CV-AR-IDM-001 — Logical operation identity

Class: HARD

Material mutation operations require stable logical operation or correlation identity.

### CV-AR-IDM-002 — Safe retry

Class: HARD

Retrying the same logical mutation request must not create duplicate governance effects.

### CV-AR-IDM-003 — Ambiguous timeout resolution

Class: HARD

The architecture must support determining whether a timed-out material operation:

- never executed
- failed
- or succeeded but lost its response

### CV-AR-IDM-004 — Duplicate detection

Class: HARD

The Canonical Governance Core must be able to recognize already-applied logical mutation operations where required.

### CV-AR-IDM-005 — Worker retry safety

Class: HARD for separately executing workers

Any future worker that submits proposals, evidence or mutation requests must support retry behavior without duplicating canonical effects.

## 11. Requirement family — Evidence and External Authority

### CV-AR-EVD-001 — Provenance preservation

Class: HARD

Material evidence must retain enough provenance to identify origin and source authority.

### CV-AR-EVD-002 — Reference-first posture

Class: STRONG

External evidence should be referenced rather than indiscriminately copied unless retention is justified.

### CV-AR-EVD-003 — Freshness semantics

Class: HARD

Copied, cached or retrieved external state must support explicit freshness semantics where currentness matters.

### CV-AR-EVD-004 — Stale state visibility

Class: HARD

Stale external information must not silently appear current.

### CV-AR-EVD-005 — Explicit unavailability

Class: HARD

Unavailable required external evidence must remain unavailable or UNKNOWN rather than be fabricated.

### CV-AR-EVD-006 — Integrity state

Class: HARD

Evidence contracts must be capable of representing integrity failure or uncertainty where material.

### CV-AR-EVD-007 — External source authority preservation

Class: HARD

Core Vision possession, transformation or retention of evidence must not transfer authority from the external source domain.

### CV-AR-EVD-008 — Evidence retention policy

Class: STRONG

Retained evidence should have explicit justification and lifecycle semantics.

## 12. Requirement family — AI Architecture

### CV-AR-AI-001 — AI optionality

Class: HARD

Core Vision canonical governance, deterministic rules, Human authorization and history must remain usable without AI.

### CV-AR-AI-002 — AI provider boundary

Class: HARD

AI integration must use an explicit replaceable provider boundary.

### CV-AR-AI-003 — No direct canonical write

Class: HARD

AI must not receive unrestricted direct canonical governance mutation capability.

### CV-AR-AI-004 — Output classification

Class: HARD

AI output must remain distinguishable from:

- evidence
- deterministic result
- recommendation
- Human decision
- effective canonical state

### CV-AR-AI-005 — Bounded context

Class: HARD

AI input should be purpose-bounded and minimize unnecessary information exposure.

### CV-AR-AI-006 — Secret exclusion by default

Class: HARD

AI must not receive secrets by default.

### CV-AR-AI-007 — AI failure isolation

Class: HARD

AI provider failure must degrade AI-assisted capability without corrupting canonical governance operation.

### CV-AR-AI-008 — Provider replacement

Class: STRONG

Changing AI provider or execution model should not require changing canonical governance semantics.

### CV-AR-AI-009 — Local or remote compatibility

Class: DESIRABLE

The AI boundary should not unnecessarily prevent future use of local, remote or self-hosted execution models.

### CV-AR-AI-010 — Retrieval representation secondary

Class: HARD

Vector, semantic or other AI retrieval representations must remain derived from or linked to governed source information and must not become canonical governance authority.

## 13. Requirement family — Identity and Authorization

### CV-AR-IAM-001 — Actor-type distinction

Class: HARD

The architecture must distinguish at least:

- Human actor
- internal system actor
- AI actor
- external system actor

### CV-AR-IAM-002 — Authentication support

Class: HARD

Server-primary operation requires an implementable authentication boundary for Human and system access.

### CV-AR-IAM-003 — Authorization support

Class: HARD

Application permissions and governance authority must be separately enforceable.

### CV-AR-IAM-004 — Least privilege

Class: HARD

Components and actors must receive only the privileges required for their role.

### CV-AR-IAM-005 — Service identity

Class: HARD

External integrations and future workers require attributable system identity.

### CV-AR-IAM-006 — Multi-actor readiness

Class: STRONG

The architecture should permit future multiple Human actors without redefining canonical governance semantics.

### CV-AR-IAM-007 — Session and credential revocation

Class: HARD

The selected identity architecture must support revocation or invalidation of compromised or obsolete credentials and sessions where applicable.

### CV-AR-IAM-008 — Authorization auditability

Class: HARD

Material authorization decisions must be auditable.

## 14. Requirement family — Secrets

### CV-AR-SEC-001 — No universal ecosystem secret store

Class: HARD

Core Vision must not become the universal secret repository for unrelated Core systems.

### CV-AR-SEC-002 — Purpose-bounded secrets

Class: HARD

Credentials retained for Core Vision integrations must be purpose-bounded.

### CV-AR-SEC-003 — Secret-at-rest protection

Class: HARD

Persisted secrets require protection appropriate to their sensitivity.

### CV-AR-SEC-004 — Secret-in-transit protection

Class: HARD

Secrets must not be exposed through unprotected integration transport.

The transport technology remains deferred.

### CV-AR-SEC-005 — Secret logging prohibition

Class: HARD

Secrets must not be written into ordinary application, AI, diagnostic or audit logs.

### CV-AR-SEC-006 — Secret rotation

Class: STRONG

The selected architecture should support credential rotation without redesigning integration contracts.

### CV-AR-SEC-007 — AI secret isolation

Class: HARD

AI processing must not receive integration credentials unless an explicitly justified future use case requires them.

## 15. Requirement family — Application Security

### CV-AR-APPSEC-001 — Input validation

Class: HARD

All state-changing and external-input contracts require validation before authoritative processing.

### CV-AR-APPSEC-002 — Fail-closed authority ambiguity

Class: HARD

Material authority ambiguity must fail closed.

### CV-AR-APPSEC-003 — Explicit trust boundaries

Class: HARD

Every external project or external service boundary must be treated as a trust boundary.

### CV-AR-APPSEC-004 — No implicit first-party trust

Class: HARD

First-party Core integrations must not bypass authentication or authorization solely because they belong to the Core ecosystem.

### CV-AR-APPSEC-005 — Dependency security posture

Class: STRONG

Selected technology should support timely security maintenance and vulnerability remediation.

### CV-AR-APPSEC-006 — Supported release posture

Class: STRONG

Production baseline technologies should have a clear maintained and supported release posture.

### CV-AR-APPSEC-007 — Security update operability

Class: STRONG

The Human Maintainer should be able to update security-sensitive dependencies without excessive architectural disruption.

## 16. Requirement family — Persistence

### CV-AR-PER-001 — Durable canonical storage

Class: HARD

Core Vision-owned canonical governance state requires durable persistence.

### CV-AR-PER-002 — Durable history

Class: HARD

Required material governance history requires durable persistence.

### CV-AR-PER-003 — Atomic mutation support

Class: HARD

The persistence architecture must support the atomicity requirement of material canonical governance effects.

### CV-AR-PER-004 — Concurrency control support

Class: HARD

The persistence architecture must support detection and safe handling of conflicting concurrent canonical changes.

### CV-AR-PER-005 — Integrity constraints

Class: HARD

The persistence solution must support enforcing or reliably implementing material data integrity constraints.

### CV-AR-PER-006 — Migration support

Class: HARD

Schema or model evolution must be manageable through explicit versioned migration procedures.

### CV-AR-PER-007 — Backup compatibility

Class: HARD

Canonical state and history must be backup-capable using a documented, testable process.

### CV-AR-PER-008 — Restore compatibility

Class: HARD

A backup must be restorable into a semantically valid Core Vision state.

### CV-AR-PER-009 — Export capability

Class: STRONG

Material governance information should be exportable for migration, audit or inspection without relying on undocumented proprietary internals.

### CV-AR-PER-010 — Human-inspectable tooling

Class: STRONG

Operational tools should permit Human inspection of persistence health and migration state without requiring AI.

### CV-AR-PER-011 — Relationship-rich query support

Class: STRONG

The persistence architecture should support efficient traversal and querying of relationships among projects, authorities, capabilities, integrations, cases, evidence and decisions.

This requirement does not imply a graph database.

### CV-AR-PER-012 — Derived-store independence

Class: HARD

Loss of search, cache, projection or AI retrieval stores must not destroy canonical governance state.

## 17. Requirement family — Backup and Restore

### CV-AR-BKP-001 — Consistent backup

Class: HARD

Backup must capture a semantically consistent set of canonical state and required history.

### CV-AR-BKP-002 — Restore verification

Class: HARD

Restore procedures must be testable and capable of validation after recovery.

### CV-AR-BKP-003 — Governance semantics preserved

Class: HARD

Restore must not silently:

- reactivate expired exceptions
- convert stale external evidence to current
- lose authority history
- lose Human attribution
- merge proposed state into effective state

### CV-AR-BKP-004 — Backup access control

Class: HARD

Backups containing governance or sensitive information require explicit access control.

### CV-AR-BKP-005 — Recovery objectives

Class: DEFERRED

Concrete Recovery Point Objective and Recovery Time Objective values must be set before production release.

Part 5 must not invent unsupported numeric values merely to score products.

### CV-AR-BKP-006 — Portable recovery

Class: STRONG

Recovery should not unnecessarily depend on one proprietary hosting environment.

## 18. Requirement family — Deployment

### CV-AR-DEP-001 — Server-primary capability

Class: HARD for the current recommended runtime

Candidate technology must support persistent server-primary Core Vision operation.

### CV-AR-DEP-002 — Independent outage domain

Class: HARD

Core Vision failure must not automatically stop CoreOps, Core-Dev, Core Brain, CDS consumers or product runtime.

### CV-AR-DEP-003 — Browser-capable Human access

Class: STRONG

The preferred implementation should support a web-capable Human interface suitable for multi-device administration.

### CV-AR-DEP-004 — Local development

Class: HARD

Developers must be able to run a representative Core Vision development environment locally without requiring the production environment.

### CV-AR-DEP-005 — Test environment

Class: HARD

The architecture must support isolated automated testing without production credentials or production state.

### CV-AR-DEP-006 — Upgrade procedure

Class: HARD

Application and persistence upgrades require a documented controlled procedure.

### CV-AR-DEP-007 — Rollback strategy

Class: HARD

Material deployment changes require a defined rollback or forward-recovery strategy.

### CV-AR-DEP-008 — AI-disabled mode

Class: HARD

Core Vision must support operation without an available AI provider.

### CV-AR-DEP-009 — Optional external integrations

Class: HARD

Core Brain, Core-Dev, CoreOps and CDS must not all be required merely to bootstrap Core Vision.

### CV-AR-DEP-010 — Packaging portability

Class: STRONG

Deployment packaging should remain portable across reasonable self-hosted environments.

### CV-AR-DEP-011 — Resource efficiency

Class: STRONG

The initial deployment should avoid unnecessary distributed-system resource overhead.

## 19. Requirement family — Background Execution and Workers

### CV-AR-WRK-001 — Workers optional initially

Class: HARD

The initial architecture must not require auxiliary workers solely to justify modularity.

### CV-AR-WRK-002 — Worker authority prohibition

Class: HARD

A worker must not own an independent competing canonical governance store.

### CV-AR-WRK-003 — Worker isolation trigger

Class: HARD

Separate worker deployment requires an explicit justification such as:

- workload isolation
- security isolation
- reliability isolation
- long-running work
- scheduling
- independent scaling

### CV-AR-WRK-004 — Worker retry safety

Class: HARD

Workers must be safe under retries and duplicate delivery.

### CV-AR-WRK-005 — Worker outage degradation

Class: HARD

Loss of an optional worker must not silently corrupt canonical governance state.

### CV-AR-WRK-006 — Background scheduling

Class: STRONG

The architecture should support bounded scheduled tasks such as evidence refresh, governance validation or reporting without requiring a distributed service architecture.

## 20. Requirement family — External Integrations

### CV-AR-INT-001 — Explicit adapter boundary

Class: HARD

External integrations must cross an explicit governed integration boundary.

### CV-AR-INT-002 — No private database coupling

Class: HARD

Core Vision must not depend on another project's private database as an application contract.

### CV-AR-INT-003 — No external canonical write

Class: HARD

External integrations must not receive direct canonical Core Vision write access.

### CV-AR-INT-004 — Compatibility handling

Class: HARD

Material external contracts require explicit compatibility and evolution semantics.

### CV-AR-INT-005 — Availability state

Class: HARD

Integration availability and failure must be visible to Core Vision.

### CV-AR-INT-006 — Timeout handling

Class: HARD

External calls must support bounded timeout and failure handling.

### CV-AR-INT-007 — Retry policy

Class: HARD

Retry behavior must be explicit and safe for the relevant integration class.

### CV-AR-INT-008 — Authentication boundary

Class: HARD

Integration authentication must be explicit where the external system requires trust.

### CV-AR-INT-009 — Authorization boundary

Class: HARD

Authentication to an integration must not imply unrestricted authorization.

### CV-AR-INT-010 — Optionality

Class: HARD where integration is classified optional

Failure of an optional integration must degrade capability rather than Core Vision governance bootstrap.

## 21. Requirement family — UI and Human Interaction

### CV-AR-UI-001 — No direct persistence access

Class: HARD

The Human-facing UI must not act as an undocumented direct canonical persistence client.

### CV-AR-UI-002 — Explicit state classes

Class: HARD

The UI must be capable of visibly distinguishing:

- evidence
- deterministic rule result
- AI analysis
- recommendation
- proposed effect
- Human decision
- effective state
- historical state
- UNKNOWN
- stale external state

### CV-AR-UI-003 — Explicit Human approval

Class: HARD

The approval UX must require a distinguishable Human action.

### CV-AR-UI-004 — Block visibility

Class: HARD

Blocking rules and missing evidence must be visible rather than silently hidden.

### CV-AR-UI-005 — AI provenance visibility

Class: STRONG

Material AI-generated content should be identifiable as AI-generated analysis or recommendation.

### CV-AR-UI-006 — Accessibility

Class: STRONG

The chosen UI approach should permit implementation of accessible Human interaction.

### CV-AR-UI-007 — CDS compatibility

Class: STRONG

The UI architecture should permit consumption of applicable CDS foundations without making CDS a governance bootstrap dependency.

### CV-AR-UI-008 — Responsive administration

Class: DESIRABLE

The preferred UI approach should support practical desktop and tablet-sized administrative interaction.

## 22. Requirement family — Observability

### CV-AR-OBS-001 — Application health

Class: HARD

The deployment must expose sufficient health information to determine whether Core Vision is operational.

### CV-AR-OBS-002 — Persistence health

Class: HARD

Persistence availability and migration health must be observable.

### CV-AR-OBS-003 — Integration health

Class: HARD

External integration availability and degradation must be observable.

### CV-AR-OBS-004 — Rule-engine health

Class: HARD

Unexpected deterministic-rule execution failures must be distinguishable from legitimate rule FAIL or BLOCKED results.

### CV-AR-OBS-005 — AI availability

Class: HARD

AI availability and AI provider failure must be distinguishable from governance failure.

### CV-AR-OBS-006 — Background task health

Class: STRONG

Scheduled and long-running tasks should expose execution state and failure information.

### CV-AR-OBS-007 — Backup readiness

Class: STRONG

Backup success and restore-test status should be observable.

### CV-AR-OBS-008 — Correlation

Class: HARD

Material operations should support correlation across application processing, mutation and audit history.

## 23. Requirement family — Logging

### CV-AR-LOG-001 — Structured operational logging

Class: STRONG

Operational logs should be structured enough for reliable filtering and diagnostics.

This does not select a logging format or product.

### CV-AR-LOG-002 — Sensitive-data minimization

Class: HARD

Logs must minimize sensitive governance information and must not contain secrets.

### CV-AR-LOG-003 — Audit versus operational log distinction

Class: HARD

Operational logs must not be treated as the sole authoritative governance audit record.

### CV-AR-LOG-004 — Actor correlation

Class: HARD

Material Human-authorized operations should be correlatable with the relevant authenticated actor and decision without leaking unnecessary sensitive information.

## 24. Requirement family — Portability and Lock-In

### CV-AR-PRT-001 — Self-hosted viability

Class: HARD

The preferred Core Vision architecture must remain viable for self-hosted operation.

### CV-AR-PRT-002 — Exportable governance data

Class: STRONG

Material governance data should be exportable through documented mechanisms.

### CV-AR-PRT-003 — Replaceable AI provider

Class: HARD

Canonical governance semantics must not depend on one proprietary AI provider.

### CV-AR-PRT-004 — Replaceable integration adapters

Class: STRONG

External-system-specific implementation should remain isolated enough to allow adapter replacement.

### CV-AR-PRT-005 — Deployment portability

Class: STRONG

The application should avoid unnecessary dependence on one cloud vendor or proprietary runtime environment.

### CV-AR-PRT-006 — Open standards preference

Class: STRONG

Where architectural fit is comparable, documented open standards and broadly interoperable formats should be preferred.

### CV-AR-PRT-007 — Exit strategy

Class: STRONG

Material technology choices should have a credible migration or exit path.

## 25. Requirement family — Migration and Evolution

### CV-AR-MIG-001 — Versioned schema evolution

Class: HARD

Persistent model evolution must be explicit and version-controlled.

### CV-AR-MIG-002 — Governance semantic preservation

Class: HARD

Migration must preserve authority, decision, evidence and history semantics.

### CV-AR-MIG-003 — Pre-migration validation

Class: HARD

Material migrations require validation before changing production canonical state.

### CV-AR-MIG-004 — Post-migration validation

Class: HARD

Material migrations require validation after completion.

### CV-AR-MIG-005 — Rollback or forward-recovery plan

Class: HARD

Every material persistence migration requires an explicit recovery strategy.

### CV-AR-MIG-006 — Architecture extraction seam

Class: STRONG

Technology choices should not unnecessarily prevent later extraction of justified auxiliary workers.

### CV-AR-MIG-007 — No forced microservice migration

Class: HARD

Architecture evolution must not require distributed services merely because internal modules exist.

## 26. Requirement family — Testing

### CV-AR-TST-001 — Deterministic unit testing

Class: HARD

Domain policy and deterministic rules must be independently testable.

### CV-AR-TST-002 — Mutation-path testing

Class: HARD

Tests must verify that unauthorized mutation paths cannot bypass the Canonical Governance Core.

### CV-AR-TST-003 — Authorization testing

Class: HARD

Tests must cover authentication-versus-authority distinctions and Decision Owner checks.

### CV-AR-TST-004 — Concurrency testing

Class: HARD

The architecture must permit tests for stale authorization and conflicting canonical changes.

### CV-AR-TST-005 — Idempotency testing

Class: HARD

Retry and duplicate-submission behavior must be testable.

### CV-AR-TST-006 — AI-disabled testing

Class: HARD

The complete non-AI governance path must be testable.

### CV-AR-TST-007 — External-failure testing

Class: HARD

Core Brain, Core-Dev, CoreOps and other optional integration failures must be testable.

### CV-AR-TST-008 — Backup / restore testing

Class: HARD

Backup restoration must be testable.

### CV-AR-TST-009 — Migration testing

Class: HARD

Schema or persistence migrations must be testable before production application.

### CV-AR-TST-010 — Architecture-boundary testing

Class: STRONG

Technology choices should make module and contract boundary tests practical.

## 27. Requirement family — Performance and Scale

### CV-AR-PFM-001 — Governance correctness over throughput

Class: HARD

Correctness, authority preservation and auditability take priority over extreme throughput optimization.

### CV-AR-PFM-002 — Interactive Human operations

Class: STRONG

Normal Human-facing governance queries and review operations should remain responsive under expected initial workload.

Concrete latency targets are DEFERRED until representative workload measurements exist.

### CV-AR-PFM-003 — Bounded long-running work

Class: STRONG

Long-running AI, evidence or report tasks should not unnecessarily block interactive Human operations.

### CV-AR-PFM-004 — Relationship query efficiency

Class: STRONG

Architecture should efficiently support relationship-heavy governance queries at expected Core ecosystem scale.

### CV-AR-PFM-005 — Horizontal scale not initial gate

Class: DESIRABLE

Massive horizontal scaling capability is not an initial architecture requirement without evidence.

### CV-AR-PFM-006 — Resource-budget measurement

Class: DEFERRED

Concrete CPU, memory and storage budgets must be measured before production baseline approval.

## 28. Requirement family — Availability and Recovery

### CV-AR-AVL-001 — Core Vision independent failure

Class: HARD

Core Vision failure must remain independent of the mandatory runtime path of other Core projects.

### CV-AR-AVL-002 — AI graceful degradation

Class: HARD

AI failure must not prevent deterministic and Human governance operation.

### CV-AR-AVL-003 — Integration graceful degradation

Class: HARD

Optional integration failure must preserve canonical governance operation.

### CV-AR-AVL-004 — Projection graceful degradation

Class: HARD

Projection failure must not destroy canonical authority.

### CV-AR-AVL-005 — Evidence-aware blocking

Class: HARD

A governance action legitimately requiring unavailable current external evidence may remain BLOCKED or UNKNOWN.

The system must not invent evidence to preserve availability.

### CV-AR-AVL-006 — Recovery validation

Class: HARD

After a significant recovery event, canonical state and history integrity require validation before normal authoritative mutation resumes.

## 29. Requirement family — Maintainability

### CV-AR-MNT-001 — Explicit module boundaries

Class: HARD

Selected technology must permit implementation of explicit internal module boundaries.

### CV-AR-MNT-002 — No framework-owned governance semantics

Class: HARD

Governance semantics must remain represented in Core Vision application concepts rather than being hidden exclusively inside framework configuration.

### CV-AR-MNT-003 — Human Maintainer operability

Class: STRONG

The selected stack should be practical for a Human Maintainer to understand, update, troubleshoot, back up and restore.

### CV-AR-MNT-004 — Documentation quality

Class: STRONG

Major technology choices should have high-quality maintained documentation.

### CV-AR-MNT-005 — Dependency restraint

Class: STRONG

The initial stack should avoid unnecessary dependencies and distributed infrastructure.

### CV-AR-MNT-006 — Long-term maintainability

Class: STRONG

Technology choices should favor credible long-term maintenance over short-lived novelty.

### CV-AR-MNT-007 — Upgrade path

Class: STRONG

Major dependencies should provide a practical upgrade path and documented compatibility information.

## 30. Requirement family — Licensing and Sustainability

### CV-AR-LIC-001 — License verification

Class: HARD

Material technology dependencies require verified licensing before architecture approval.

### CV-AR-LIC-002 — Intended-use compatibility

Class: HARD

Licensing must permit the intended Core Vision use, development, distribution posture and self-hosted operation.

### CV-AR-LIC-003 — Dependency maintenance health

Class: STRONG

Candidate projects should demonstrate credible current maintenance activity or a stable supported maintenance posture.

### CV-AR-LIC-004 — Abandonment risk

Class: STRONG

Technology evaluation must consider abandonment or ecosystem-fragmentation risk.

### CV-AR-LIC-005 — Commercial lock-in visibility

Class: STRONG

Material commercial or hosted-service dependencies must expose their lock-in implications explicitly.

## 31. Architecture decision gates

Before CV-WP-007 may recommend implementation authorization, the architecture baseline must demonstrate satisfaction of the following gates.

### Gate A — Authority Integrity

Must pass all applicable HARD requirements concerning:

- canonical mutation
- Human authorization
- rule authority
- AI non-authority
- external authority preservation
- administration separation

### Gate B — State Integrity

Must pass all applicable HARD requirements concerning:

- persistence
- atomicity
- concurrency
- idempotency
- migration
- historical integrity

### Gate C — Auditability

Must pass all applicable HARD audit and traceability requirements.

### Gate D — Security

Must pass all applicable HARD identity, authorization, secret and trust-boundary requirements.

### Gate E — Recoverability

Must pass all applicable HARD backup, restore and recovery requirements.

### Gate F — Standalone Operation

Must preserve:

- Standalone First
- Graceful Absence
- No Bootstrap Cycles
- Authority Preservation

### Gate G — Technology Evidence

Material selected technologies must have current primary-source evidence for:

- support status
- maintenance posture
- licensing
- required features
- compatibility assumptions

UNKNOWN material facts remain blocking or explicitly conditional.

## 32. Part 5 weighted evaluation dimensions

After hard-gate filtering, surviving candidates should be scored using explicit weighted dimensions.

The initial recommended dimension set is:

- Architectural Fit
- Security
- Data Integrity
- Auditability
- Maintainability
- Human Maintainer Operability
- Portability
- Ecosystem Lock-In Risk
- Technology Maturity
- Documentation Quality
- Operational Complexity
- Resource Efficiency
- Testing Support
- Integration Flexibility
- AI Neutrality
- Migration / Exit Capability

Weights must be explicitly finalized before candidate scoring in Part 5.

## 33. Hard requirement precedence

Weighted scoring must never conceal failure of a HARD requirement.

Example:

A technology with excellent developer experience but no credible way to preserve required canonical transaction integrity cannot win the canonical persistence role through a higher total score.

Hard architecture semantics take precedence over convenience scoring.

## 34. Candidate-role separation

Part 5 must not assume one technology product must solve every architecture concern.

Candidate evaluation should occur by role where appropriate.

Possible roles include:

- primary application language/runtime
- backend application framework
- Human-facing UI approach
- canonical persistence
- migration tooling
- deterministic rule implementation
- application contract/API approach
- authentication/identity
- authorization
- background execution
- AI provider abstraction
- search
- AI retrieval
- observability
- deployment packaging

A technology may be strong for one role and unsuitable for another.

## 35. Technology-stack complexity control

The evaluation should prefer the smallest coherent set of technologies that satisfies the architecture.

Adding a technology must have an explicit purpose.

A technology should not be added merely because it is commonly found in modern stacks.

In particular, Part 5 must not assume automatic need for:

- message broker
- distributed cache
- graph database
- vector database
- separate search server
- orchestration cluster
- multiple application services

Each requires demonstrated architectural value.

## 36. Modular Governance Monolith decision evidence

The requirements in this document remain compatible with the CV-WP-006 Modular Governance Monolith recommendation.

In particular, no current HARD requirement inherently requires distributed services.

The following needs can be satisfied conceptually within one modular application boundary:

- canonical governance state
- deterministic rule evaluation
- Human authorization
- history
- evidence coordination
- optional AI analysis
- projection
- external integration adapters

This strengthens the recommendation but does not yet formally adopt it.

## 37. Server-primary decision evidence

The requirements also remain compatible with server-primary operation.

Server-primary operation is particularly aligned with:

- persistent canonical state
- centralized authorization boundary
- backup
- audit history
- scheduled validation
- future multiple actors
- browser-capable Human access

This strengthens the recommendation but does not yet formally adopt it.

## 38. Deferred quantitative requirements

The following concrete quantitative values remain deferred until representative usage or production planning provides evidence:

- maximum Human-request latency
- maximum concurrent Human actors
- maximum project count
- maximum evidence volume
- maximum rule-evaluation throughput
- AI request volume
- storage growth rate
- RPO
- RTO
- CPU budget
- memory budget
- storage budget

Part 5 must not fabricate these values.

Technology evaluation should identify whether a candidate exposes credible room for expected small-to-medium governance workloads without claiming unsupported scale requirements.

## 39. Current-source requirement for Part 5

Technology evaluation must use current primary sources where practical.

Preferred sources include:

- official documentation
- official product pages
- official repositories
- official release notes
- official support policies
- official security documentation
- official licensing material

Secondary sources may supplement primary evidence but should not override it without explicit justification.

## 40. Version and support verification

Part 5 must verify material facts that can change over time, including:

- current stable release
- supported release line
- maintenance status
- licensing
- security support
- platform support
- major compatibility constraints

Technology versions must not be selected from stale model memory.

## 41. Technology evidence record

For each material candidate, Part 5 should record at least:

- candidate name
- role
- current verified version or release line where material
- source date
- evidence sources
- applicable HARD requirements
- hard-gate result
- weighted-score result
- known risks
- unknowns
- licensing posture
- maintenance posture
- recommendation state

## 42. Recommendation states

Part 5 candidate results may use:

- RECOMMENDED
- RECOMMENDED WITH CONDITIONS
- VIABLE
- NOT PREFERRED
- REJECTED
- DEFERRED
- INSUFFICIENT EVIDENCE

A recommendation is not implementation authorization.

## 43. Architecture status after Part 4

After establishing these implementable requirements:

Modular Governance Monolith remains:

RECOMMENDED / NOT YET FORMALLY ADOPTED

Server-primary remains:

RECOMMENDED / NOT YET FORMALLY ADOPTED

Technology Selection remains:

UNSELECTED

Implementation remains:

NOT AUTHORIZED

## 44. Part 5 handoff

CV-WP-007 Part 5 must now perform current technology research.

Part 5 must:

1. finalize weighted evaluation dimensions and weights before scoring
2. identify viable technology candidates by architecture role
3. use current primary-source evidence
4. apply HARD requirement gates first
5. score surviving candidates
6. preserve UNKNOWN material facts
7. identify licensing and maintenance risks
8. compare coherent stack combinations
9. identify ADR-worthy decisions
10. produce recommendations without implementation authorization

Part 5 must not weaken these requirements merely because a preferred technology fails them.

## 45. Conclusion

Core Vision technology evaluation now has an explicit architecture contract.

The key decision is no longer:

> Which technology is most popular?

The decision becomes:

> Which technology most cleanly satisfies Core Vision's authority, state-integrity, auditability, security, recoverability, portability and maintainability requirements with the least unnecessary complexity?

This requirement baseline preserves:

- one controlled canonical mutation boundary
- explicit Human authorization
- deterministic rule integrity
- AI optionality
- external authority preservation
- provenance
- history
- retry safety
- concurrency safety
- recoverability
- standalone operation
- future evolution

Technology must fit the architecture.

The architecture must preserve governance.

Knowledge can be centralized, authority not.
