# Core Vision Software Architecture Baseline

## 1. Status

ADOPTED

Implementation:

NOT AUTHORIZED

## 2. Purpose

This document defines the candidate Core Vision software architecture baseline resulting from CV-WP-006 and CV-WP-007.

The baseline combines:

- software responsibility discovery
- Human / Rule / AI authority model
- information-state model
- architecture-option analysis
- formal component model
- module contracts
- canonical mutation boundaries
- 189 implementable architecture requirements
- current technology research
- HARD-gate evaluation
- frozen weighted technology scoring
- consolidated architecture decision candidates

This baseline remains non-effective until final review and explicit Human Maintainer authorization.

## 3. Candidate architecture

Application Architecture:

MODULAR GOVERNANCE MONOLITH

Runtime:

SERVER-PRIMARY

Canonical Governance Boundary:

ONE CONTROLLED CANONICAL GOVERNANCE CORE

Human Interaction:

WEB-CAPABLE

Initial Actor Posture:

SINGLE-AUTHORITY-FIRST / MULTI-ACTOR-READY

## 4. Formal component model

The candidate application architecture contains fourteen logical components:

1. Canonical Governance Core
2. Portfolio & Lifecycle Governance
3. Authority & Capability Governance
4. Integration Governance
5. Deterministic Rule Evaluation
6. Governance Case & Decision Coordination
7. Evidence & Provenance Boundary
8. AI Analysis Boundary
9. History & Audit
10. Projection & Reporting
11. Application / Human Interaction Boundary
12. External Integration Boundary
13. Identity & Access Boundary
14. Administration & Health

These are logical components.

They are not separate services by default.

## 5. Canonical mutation invariant

Every effective mutation of Core Vision-owned canonical governance state must cross the Canonical Governance Core.

No equivalent bypass is permitted through:

- UI
- AI
- projection
- external integration
- worker
- administration
- private persistence access

The Canonical Governance Core applies legitimate effects.

It does not invent their authority.

## 6. Candidate technology baseline

### Primary application platform

.NET 10 LTS

ASP.NET Core 10

### Canonical persistence

PostgreSQL 18

### Data access and migrations

EF Core 10

Npgsql EF Core provider

### Human-facing UI

Blazor Web App

Preferred initial posture:

server-primary rendering with interactive server behavior where justified.

### Identity

ASP.NET Core Identity

External OIDC-compatible authentication seam preserved.

### Governance authorization

Core Vision-owned application/domain authorization.

Generic identity roles do not become governance authority automatically.

### Deterministic rules

Core Vision application-native deterministic rule module.

### AI

Core Vision-owned AI provider port.

Microsoft.Extensions.AI may be used as an optional adapter behind the Core Vision-owned boundary.

No AI provider is itself governance authority.

### Observability

ASP.NET Core Health Checks.

OpenTelemetry.

### Background execution

Bounded in-process execution initially.

Auxiliary worker extraction only when evidence justifies it.

### Deployment packaging

OCI-compatible image.

No mandatory container engine selected by this architecture decision.

### Search

PostgreSQL / application-native query capability initially.

## 7. Technology score evidence

Part-5B leading results:

| Role | Preferred candidate | Score |
|---|---|---:|
| Application Runtime | APP-A .NET 10 / ASP.NET Core 10 | 97.9 |
| Canonical Persistence | DB-A PostgreSQL 18 | 97.1 |
| Human UI | UI-A Blazor Web App | 95.5 |
| Identity | IAM-A Application-native Identity | 96.1 |
| Deterministic Rules | RULE-A Application-native Rules | 98.2 |
| AI Contract | AI-A Core Vision-owned AI Port | 96.5 |

The scoring model used:

- 189 architecture requirements
- HARD gates before weighted scoring
- fixed weights totaling 100
- unchanged candidate ratings
- decimal score calculation
- explicit midpoint rounding away from zero

Weighted scores cannot override HARD-gate failures.

## 8. Alternative application baseline

The strongest alternative application baseline remains:

Python 3.14
+ Django 5.2 LTS
+ PostgreSQL 18

Status:

VIABLE / NOT PREFERRED

It is not rejected on governance grounds.

## 9. Other retained alternatives

Java 25 + Spring Boot 4.1:

VIABLE WITH CONDITIONS

Node.js 24 LTS + NestJS 11:

VIABLE WITH CONDITIONS / NOT PREFERRED

MariaDB 12.3 LTS:

VIABLE WITH CONDITIONS

SQLite:

BOUNDED USE / NOT PREFERRED AS INITIAL PRODUCTION CANONICAL STORE

Keycloak:

VIABLE FUTURE OPTION

Open Policy Agent:

VIABLE FUTURE OPTION

React:

VIABLE UI ALTERNATIVE

## 10. Initial explicit non-selections

The candidate baseline does not initially select:

- microservices
- Kubernetes
- mandatory auxiliary worker
- message broker
- distributed cache
- dedicated search service
- graph database
- vector database
- external policy engine
- mandatory Keycloak
- mandatory separate JavaScript SPA
- direct AI-provider SDK coupling into governance modules

These technologies are not permanently prohibited.

They require evidence before adoption.

## 11. Authority model

### Core Vision

Owns accepted T0 Core Vision governance state within its legitimate authority domain.

### NDF

Remains development-governance authority.

### Core Brain

Remains Knowledge and Evidence Plane.

Core Brain does not become Core Vision canonical governance authority.

### Core-Dev

Remains Engineering Control Plane and engineering-readiness authority.

### CoreOps

Remains Operations Control Plane and current operational-state authority.

CoreOps may later operate Core Vision software without receiving Core Vision governance authority.

### CDS

Remains scoped design and presentation authority.

CDS does not become Core Vision governance authority.

### Products

Retain product-specific authority.

## 12. Human / Rule / AI model

Deterministic rules:

- derive authority from accepted governance
- do not silently create policy
- do not replace required Human authorization

AI:

- analyzes
- explains
- classifies
- recommends
- prepares proposals

AI does not:

- fabricate evidence
- override binding deterministic failures
- create Human approval
- directly mutate canonical governance state

Human authorization:

- remains explicit
- remains attributable
- remains Decision-Owner-aware
- remains context-bound

## 13. State model

The architecture preserves distinction among:

- canonical Core Vision governance state
- external authoritative state
- source evidence
- evidence reference
- retained evidence
- derived analysis
- deterministic rule result
- AI analysis
- recommendation
- proposed governance effect
- pending Human decision
- authorized decision
- effective state
- exception
- historical state
- UNKNOWN

Storage location does not determine authority.

## 14. Consistency requirements

Material canonical mutations require:

- expected-state validation
- conflict detection
- atomic effect semantics
- idempotency
- retry safety
- correlation identity
- stale authorization detection
- pre-effect revalidation
- required audit linkage

Silent last-writer-wins behavior is not an architecture default.

## 15. History and audit

Material governance state must remain explainable through sufficient historical linkage.

Operational logging is not the sole Governance Audit.

Required audit history must not silently disappear while canonical mutation reports success.

## 16. External integration posture

Public Interface First remains binding.

External projects must not depend on Core Vision private persistence.

Core Vision must not depend on other projects' private persistence.

External events do not automatically command Core Vision canonical mutation.

First-party integrations do not receive implicit trust.

## 17. AI posture

The AI boundary must remain usable with:

- no AI
- local AI
- remote AI
- self-hosted AI
- replacement provider
- future multiple providers

Canonical Core Vision governance semantics must remain independent of the selected provider.

## 18. Persistence posture

Canonical persistence is relational in the proposed baseline.

Relationship-rich governance semantics do not require a graph database initially.

AI retrieval does not require a vector database initially.

Derived stores remain non-authoritative.

## 19. Deployment posture

Initial deployment is server-primary.

Core Vision must remain independently unavailable without stopping the mandatory runtime of:

- CoreOps
- Core-Dev
- Core Brain
- CDS
- products

Core Vision remains an ecosystem governance application.

It does not become an ecosystem runtime dependency.

## 20. Recovery posture

Production implementation must later define:

- backup procedure
- restore procedure
- restore verification
- migration recovery
- RPO
- RTO

RPO and RTO remain intentionally unresolved until evidence exists.

## 21. Security posture

The architecture requires:

- Human identity
- system identity
- AI identity
- authentication
- separate authorization
- Decision Owner verification
- least privilege
- secret isolation
- external trust boundaries
- canonical mutation protection
- audit integrity
- administrative-access separation

Technical administration does not equal governance approval authority.

## 22. Deferred implementation details

The architecture baseline does not yet select:

- exact canonical database schema
- exact entity model
- exact authorization-policy representation
- exact secret store
- exact reverse proxy
- exact certificate topology
- exact PostgreSQL backup mechanism
- exact OpenTelemetry backend
- exact OCI runtime
- exact external OIDC provider
- exact AI provider
- exact AI model
- exact AI credential mechanism
- quantitative performance targets
- RPO
- RTO
- CPU budget
- memory budget
- storage budget

These are implementation-definition or production-readiness decisions unless later classified as architecture material.

## 23. Architecture principles

The candidate baseline preserves all six binding principles:

1. Standalone First
2. Public Interface First
3. No Implicit First-Party Trust
4. Graceful Absence
5. No Bootstrap Cycles
6. Authority Preservation

## 24. Architecture fitness failures

A future implementation fails this baseline if, among other violations:

- AI can directly mutate canonical governance state
- UI can bypass application mutation contracts
- external systems can directly write canonical governance state
- administrator privilege becomes governance authority
- deterministic rule PASS replaces required Human approval
- Core Brain becomes mandatory canonical bootstrap
- CoreOps becomes Core Vision governance authority
- Core-Dev becomes Core Vision governance authority
- history cannot explain material state transitions
- retry creates duplicate effects
- stale Human authorization silently applies
- derived search or AI stores become canonical authority

## 25. Proposed decision state

Application Architecture:

ADOPTED

Runtime:

ADOPTED

Technology Baseline:

ADOPTED

Architecture Decision Candidates:

6

Implementation:

NOT AUTHORIZED

## 26. Human authorization boundary

The baseline becomes authoritative only after:

- final architecture regression review
- final requirement review
- final decision-candidate review
- explicit Human Maintainer authorization

The Human Maintainer retains final authority over:

- architecture adoption
- technology-baseline adoption
- accepted ADRs
- architecture exceptions
- implementation authorization

## 27. Next step

Perform:

CV-WP-007 FINAL ARCHITECTURE ADOPTION REVIEW

The review must remain read-only.

If it passes, Nova may recommend:

GO — HUMAN ARCHITECTURE ADOPTION

That decision remains separate from:

GO — IMPLEMENTATION AUTHORIZED

## 28. Conclusion

The candidate Core Vision architecture is now sufficiently defined to undergo formal adoption review.

The preferred result is a deliberately compact server-primary Modular Governance Monolith built on:

.NET 10
ASP.NET Core 10
PostgreSQL 18
EF Core 10 / Npgsql
Blazor Web App
ASP.NET Core Identity
application-native deterministic governance rules
Core Vision-owned AI provider abstraction
OpenTelemetry
bounded in-process background execution
OCI-compatible packaging

The architecture preserves explicit seams for future evolution without paying distributed-system complexity before evidence justifies it.

Implementation remains unauthorized.

Knowledge can be centralized, authority not.
## 29. Adoption Record

Adoption Date:

2026-08-09

Final Architecture Adoption Review:

PASS

Human Maintainer Authorization:

EXPLICIT

Accepted Decision Record:

`docs/architecture/ARCHITECTURE_DECISIONS.md`

Architecture:

ADOPTED

Runtime:

ADOPTED

Technology Baseline:

ADOPTED

Implementation:

NOT AUTHORIZED

Architecture adoption does not itself authorize implementation.

A separate governed Work Package and explicit authorization are required before source-code implementation begins.
