# CV-WP-006 — Core Vision Software Architecture Discovery

## Type

docs-only / architecture-discovery

## Priority

P0

## Status

COMPLETE

## Objective

Discover what future Core Vision software must be responsible for, which responsibilities must remain outside it, how deterministic governance logic, AI-assisted analysis, evidence, human approval, user interaction and persistent governance state should relate, and which architecture options should later be evaluated.

This Work Package performs architecture discovery.

It does not select or authorize an implementation stack.

## Inputs

CV-WP-006 builds on:

- CV-WP-002 Ecosystem Inventory & Classification
- CV-WP-003 Ecosystem Architecture & Boundaries
- CV-WP-004 Project Lifecycle, Intake & Cross-Project Governance
- CV-WP-005 Integration Model
- established capability ownership
- established authority ownership
- established Human Maintainer authority

## Required outputs

- software responsibility model
- Human / AI authority model
- governance-state and evidence separation model
- deterministic-rules discovery
- AI analyst role discovery
- information and persistence model discovery
- UI responsibility discovery
- runtime and deployment posture discovery
- architecture option set
- explicit deferred technology decisions
- recommendation for the next architecture-definition Work Package

## Discovery principle

The software architecture must follow the governance model.

The governance model must not be rewritten merely to make software implementation easier.

## Core software posture

Future Core Vision software may support:

- ecosystem portfolio visibility
- lifecycle governance
- architecture governance
- capability and authority mapping
- integration governance
- governance-case preparation
- evidence aggregation
- conflict detection
- deterministic rule evaluation
- AI-assisted analysis
- recommendation preparation
- Human approval workflows
- governance history
- strategic reporting

Supporting a governance function does not automatically make the software the authority for that function.

## Human authority

The Human Maintainer remains authoritative for irreversible ecosystem-level decisions established by previous Core Vision governance.

Software may:

- collect
- validate
- correlate
- classify
- calculate
- detect
- explain
- recommend
- prepare
- record authorized decisions

Software must not silently convert analysis or recommendations into irreversible authority decisions.

## AI posture

Nova or another AI analyst may support Core Vision software.

AI may potentially:

- identify inconsistencies
- compare projects
- detect overlaps
- classify governance impact
- summarize evidence
- identify missing evidence
- prepare recommendations
- explain rule results
- propose governance actions

AI output remains distinct from:

- observed evidence
- deterministic rule results
- Human-authorized decisions

AI must not become the hidden source of binding governance state.

## Deterministic governance posture

Discovery must examine which governance rules should be deterministically evaluable.

Candidate examples include:

- invalid lifecycle transitions
- missing Decision Owner
- conflicting authority claims
- prohibited mandatory bootstrap cycles
- missing required integration metadata
- inconsistent portfolio state
- authority transfer without authorization
- conditional projects receiving permanent authority
- mandatory dependency without required approval

Deterministic rules and AI reasoning must remain distinguishable.

AI must not be required to reinterpret deterministic governance invariants on every execution.

## Information-state separation

Discovery must distinguish at least:

- authoritative governance state
- source evidence
- replicated evidence
- derived analysis
- AI inference
- recommendation
- pending Human decision
- authorized decision
- historical decision
- unknown state

These categories must not collapse into one generic truth store.

## Source-domain authority

Core Vision software may consume governed information from other projects.

It does not thereby become authoritative for:

- current operational state owned by CoreOps
- engineering readiness owned by Core-Dev
- knowledge source-domain facts merely stored by Core Brain
- CDS-owned normative design-system artifacts
- product-specific behavior or domain semantics

Knowledge can be centralized, authority not.

## Core Brain relationship

Discovery must evaluate how Core Vision may use Core Brain for knowledge and evidence capabilities without:

- making Core Brain mandatory for basic Core Vision bootstrap
- making Core Vision mandatory for Core Brain bootstrap
- creating circular authority
- transferring source-domain authority into the knowledge layer

Core Brain integration should remain replaceable and gracefully absent unless a later explicit architecture decision justifies otherwise.

## Core-Dev relationship

Discovery must evaluate how future Core Vision software may consume engineering evidence from Core-Dev.

Core-Dev remains the Engineering Control Plane.

Core Vision must not become the implementation or release-readiness authority merely because it displays or analyzes Core-Dev evidence.

## CoreOps relationship

Discovery must evaluate how future Core Vision software may consume operational evidence from CoreOps.

CoreOps remains the Operations Control Plane and current operational authority within its scope.

Core Vision must not become an operational control plane merely because it aggregates operational evidence.

## CDS relationship

Future Core Vision user-facing software should be capable of consuming governed CDS artifacts when available and appropriate.

CDS absence must not block governance logic or server-side bootstrap unless a later explicit architecture decision justifies such coupling.

Presentation authority and governance authority remain separate.

## Product relationship

Products remain independently authoritative within their product-specific domains.

Core Vision software may display, analyze and govern ecosystem relationships.

It must not become a universal product backend.

## Runtime posture

Core Vision must remain outside the mandatory runtime path of other Core projects.

An outage of Core Vision software must not automatically stop:

- CoreOps runtime operations
- Core-Dev engineering activity
- Core Brain operation
- CDS consumption already available to consumers
- normal product runtime operation

unless a future explicitly governed exception exists.

## UI posture

Discovery must determine what a Core Vision UI should enable.

Candidate responsibilities include:

- portfolio overview
- project lifecycle view
- capability ownership view
- authority matrix view
- integration map
- governance-case review
- evidence inspection
- deterministic validation results
- AI analysis
- recommendation review
- Human approval actions
- governance history

The UI must not become the sole storage location or authority mechanism.

## Persistence posture

Persistent storage will likely be required for structured governance state.

CV-WP-006 does not select the storage technology.

Discovery must instead define:

- what information requires durable canonical storage
- what information may be reconstructed
- what information is externally authoritative
- what information is cached
- what information is historical
- what information requires provenance
- what information requires immutable or append-oriented history

## Deployment posture

Discovery must compare plausible deployment shapes without selecting one prematurely.

Candidate dimensions include:

- single-process versus separated services
- local versus server-hosted
- single-user versus future multi-user
- online versus offline-capable
- optional external integrations
- AI locally hosted versus externally provided
- embedded versus external persistence
- monolith versus modular architecture

These are discovery dimensions, not decisions.

## Security posture

Architecture discovery must consider:

- identity
- authentication
- authorization
- least privilege
- Human approval boundaries
- AI privilege boundaries
- auditability
- evidence provenance
- secret handling
- external integration trust
- offline behavior
- tamper resistance for governance history

Concrete security technologies remain deferred.

## Architecture principles

The following remain binding:

1. Standalone First
2. Public Interface First
3. No Implicit First-Party Trust
4. Graceful Absence
5. No Bootstrap Cycles
6. Authority Preservation

## Out of scope

CV-WP-006 must not select:

- programming language
- application framework
- frontend framework
- database product
- ORM
- message broker
- API protocol
- container platform
- cloud provider
- identity provider
- AI model vendor
- vector database
- graph database
- specific LLM runtime

CV-WP-006 must also not:

- implement software
- create production schemas
- create APIs
- create UI code
- deploy services
- change another Core repository
- create mandatory integrations
- transfer project authority

## Architecture option requirement

The discovery must end with more than one viable architecture option unless evidence shows only one option satisfies the governance constraints.

Options must be compared using explicit criteria.

A preferred option may be recommended.

Recommendation is not implementation authorization.

## Acceptance criteria

1. Future Core Vision software responsibilities are explicitly bounded.
2. Responsibilities that remain outside Core Vision software are explicit.
3. Human, deterministic-rule and AI roles are separated.
4. Authoritative governance state is separated from evidence, inference and recommendation.
5. Source-domain authority remains external where established by CV-WP-003.
6. Core Vision remains outside other projects' mandatory runtime path.
7. Core Brain integration cannot create a bootstrap cycle.
8. Core-Dev and CoreOps authority boundaries remain preserved.
9. CDS presentation integration cannot become governance authority.
10. Products retain product-domain authority.
11. UI responsibility is separated from storage and authority.
12. Persistence requirements are discovered before storage technology selection.
13. Deployment dimensions are evaluated without stack preselection.
14. Security concerns are identified without prematurely selecting security products.
15. Multiple viable architecture options are compared where possible.
16. Deferred technology decisions are explicitly documented.
17. The next architecture-definition step is identified.
18. Human Maintainer authority remains preserved.

## Decision guardrail

CV-WP-006 may produce:

- findings
- constraints
- candidate architectures
- trade-off analysis
- recommendations

CV-WP-006 must not silently produce binding implementation-stack decisions.

Technology selection requires a later explicitly authorized decision.

## Human authority

The Human Maintainer retains final authority over:

- adoption of a preferred architecture
- implementation-stack selection
- new mandatory ecosystem dependencies
- irreversible authority transfers
- AI autonomy expansion
- security-boundary exceptions
- deployment commitments with ecosystem-wide consequences

AI systems may analyze and recommend.

They do not independently authorize the future Core Vision software architecture.

## Completion

CV-WP-006 completed after Software Architecture Discovery and Final Discovery Review R2.

Final discovery findings:

- Core Vision software is governance-centered rather than a universal ecosystem control runtime.
- Core Vision may own canonical state only within its legitimate governance domain.
- External source-domain authority remains external.
- Software responsibilities are semantically separated without forcing deployable-service decomposition.
- Deterministic rules enforce already-authorized governance and must not create policy.
- AI remains an analytical and recommendation capability without binding approval authority.
- Human authorization remains explicit for governance-defined discretionary decisions.
- Canonical governance state, evidence, deterministic results, AI analysis, recommendations, proposed effects, decisions, effective state and history remain semantically distinct.
- UNKNOWN, absence, staleness and external-authority semantics remain explicit.
- Evidence handling remains provenance-preserving and reference-first where appropriate.
- Core Brain remains an optional Knowledge and Evidence Plane integration and does not become Core Vision's sole canonical governance store.
- Core-Dev remains authoritative for engineering readiness within its scope.
- CoreOps remains authoritative for current operational state and runtime deployment within its scope.
- CDS remains presentation/design authority within its governed scope and does not become Core Vision governance authority.
- Products retain their product-specific authority.
- Core Vision remains outside the mandatory runtime path of other Core projects.
- The preferred initial software architecture discovered by CV-WP-006 is a Modular Governance Monolith.
- The preferred runtime posture discovered by CV-WP-006 is server-primary.
- The preferred architecture is RECOMMENDED only.
- The preferred architecture is NOT IMPLEMENTATION AUTHORIZED by CV-WP-006.
- No programming language, framework, database, rule engine, API protocol, AI provider, AI model, container platform or other implementation stack is selected by CV-WP-006.
- Selected non-authoritative workloads may later evolve into auxiliary workers only when evidence justifies extraction.
- A distributed capability-service architecture remains a future option and is not currently justified.
- Technology selection must follow the architecture requirements rather than redefine governance semantics.
- Human Maintainer authority remains preserved.
- Knowledge can be centralized, authority not.

Final Discovery Review R2: PASS.

### Discovery recommendation status

Preferred Architecture:

MODULAR GOVERNANCE MONOLITH

Preferred Runtime:

SERVER-PRIMARY

Recommendation State:

RECOMMENDED / NOT IMPLEMENTATION AUTHORIZED

Technology Selection:

UNSELECTED

Next Architecture Step:

CV-WP-007 — Core Vision Software Architecture Definition & Technology Evaluation
