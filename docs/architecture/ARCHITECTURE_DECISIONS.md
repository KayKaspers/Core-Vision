# Core Vision Architecture Decisions

## 1. Status

ACCEPTED

Adoption Date:

2026-08-09

Authorization:

EXPLICIT HUMAN MAINTAINER AUTHORIZATION

Implementation:

NOT AUTHORIZED

## 2. Purpose

This document records the accepted software-architecture decisions resulting from CV-WP-007.

The decisions were derived from:

- CV-WP-006 architecture discovery
- formal software component modeling
- module and canonical mutation contracts
- 189 implementable architecture requirements
- current technology research
- HARD-gate evaluation
- frozen weighted scoring
- final architecture adoption review
- explicit Human Maintainer authorization

Architecture adoption and implementation authorization remain separate governance actions.

## 3. CV-ADR-001 — Application Architecture and Runtime Posture

Status:

ACCEPTED

Decision:

Adopt the Modular Governance Monolith as the initial Core Vision application architecture.

Adopt server-primary as the initial Core Vision runtime posture.

Rationale:

The current requirement baseline does not justify distributed capability services.

The architecture can preserve explicit logical modules, one canonical mutation boundary, Human authorization, deterministic rules, AI isolation, evidence provenance and durable history inside one primary application deployment boundary.

Consequences:

- logical module boundaries are mandatory
- logical modules are not services by default
- distributed extraction requires evidence
- Core Vision remains outside the mandatory runtime path of other Core systems
- canonical authority must not be duplicated by future workers

Rejected initial alternative:

Distributed capability services / microservices.

Reconsideration triggers:

- measurable independent scaling requirement
- security-isolation requirement
- reliability-isolation requirement
- long-running workload isolation
- deployment-independence requirement

## 4. CV-ADR-002 — Application Platform and Human UI

Status:

ACCEPTED

Decision:

Adopt .NET 10 LTS and ASP.NET Core 10 as the initial Core Vision application platform.

Adopt Blazor Web App as the initial Human-facing UI technology.

Preferred UI posture:

- server-primary
- server rendering baseline
- interactive server behavior where justified
- client-side execution only where requirements justify it

Evidence:

Application runtime weighted score:

APP-A .NET 10 / ASP.NET Core 10 — 97.9

Human UI weighted score:

UI-A Blazor Web App — 95.5

Consequences:

- one cohesive primary application technology stack is preferred initially
- a separate JavaScript SPA is not mandatory
- framework implementation must not absorb Core Vision governance semantics
- public external contracts remain independent of UI implementation details

Retained alternative:

Python 3.14 + Django 5.2 LTS remains viable but not preferred.

## 5. CV-ADR-003 — Canonical Persistence and Data Access

Status:

ACCEPTED

Decision:

Adopt PostgreSQL 18 as the initial Core Vision canonical persistence technology.

Adopt EF Core 10 with the Npgsql EF Core provider as the initial data-access and migration baseline.

Evidence:

Canonical persistence weighted score:

DB-A PostgreSQL 18 — 97.1

Consequences:

The implementation must preserve:

- durable canonical state
- atomic governance effects
- integrity constraints
- concurrency detection
- versioned migrations
- backup and restore
- historical linkage
- migration validation
- recovery planning

Production schema evolution must be controlled.

Unreviewed arbitrary schema mutation at application startup is not the governance baseline.

Retained alternatives:

- MariaDB 12.3 LTS — viable with conditions
- SQLite — bounded use, testing and specialized roles

Explicit non-selection:

- graph database
- vector database
- dedicated canonical search store

## 6. CV-ADR-004 — Identity and Governance Authorization

Status:

ACCEPTED

Decision:

Adopt ASP.NET Core Identity as the initial application-native authentication and identity baseline.

Preserve an external OIDC-compatible authentication seam.

Keep Core Vision governance authorization separate from generic identity and application roles.

Binding distinction:

identity
≠ authentication
≠ application permission
≠ governance authority
≠ Decision Owner
≠ Human approval

Evidence:

IAM-A weighted score:

96.1

Consequences:

- successful authentication does not grant governance authority
- technical administrator privilege does not grant governance approval authority
- Decision Owner eligibility remains a Core Vision governance concern
- future external identity providers remain replaceable
- Keycloak remains a future option, not an initial bootstrap dependency

## 7. CV-ADR-005 — Deterministic Rules and AI Boundary

Status:

ACCEPTED

Decision A:

Implement deterministic governance rules as a Core Vision application-native rule module initially.

Do not require an external policy engine initially.

Evidence:

RULE-A weighted score:

98.2

Required rule semantics include:

- stable identity
- revision
- lifecycle
- authority basis
- deterministic execution
- PASS
- FAIL
- BLOCKED
- WARNING
- UNKNOWN
- exception semantics
- explainability
- Human-approval separation

Decision B:

Adopt a Core Vision-owned AI provider port as the binding AI architecture.

Evidence:

AI-A weighted score:

96.5

Permit Microsoft.Extensions.AI as an optional adapter behind that Core Vision-owned abstraction.

Binding AI constraints:

- AI remains optional
- AI remains replaceable
- AI remains non-authoritative
- AI does not directly mutate canonical governance state
- AI does not fabricate evidence
- AI does not replace deterministic rule truth
- AI does not impersonate Human authorization

Direct domain-facing AI-provider SDK coupling is rejected.

Open Policy Agent remains a future option if independent policy distribution later becomes justified.

## 8. CV-ADR-006 — Operations, Packaging and Evolution

Status:

ACCEPTED

Decision:

Adopt the following initial operational architecture posture:

Observability:

ASP.NET Core Health Checks
+ OpenTelemetry

Background execution:

bounded in-process execution initially

Packaging:

OCI-compatible application image

Search:

persistence-native and application-native querying initially

Evolution:

auxiliary workers only when justified by evidence

Initial explicit non-selections:

- Kubernetes
- microservices
- mandatory auxiliary worker
- message broker
- distributed cache
- dedicated search server
- graph database
- vector database
- mandatory dedicated identity server
- external policy service

Consequences:

The initial architecture favors the smallest coherent operational stack satisfying the Core Vision requirements.

New infrastructure requires an identifiable architectural purpose.

OCI packaging does not select a mandatory container engine.

Operational telemetry does not replace Governance Audit.

## 9. Cross-decision invariants

All six decisions remain subject to the following binding invariants.

### Canonical mutation

Every effective mutation of Core Vision-owned canonical governance state crosses one controlled Canonical Governance Core boundary.

### Human authority

Required Human authorization remains explicit and attributable.

### Rule authority

Deterministic rules derive authority from accepted governance.

### AI authority

AI remains non-authoritative.

### External authority

Possession or replication of external evidence does not transfer external source-domain authority.

### Runtime independence

Core Vision remains outside the mandatory runtime path of other Core systems.

### Administration

Technical administration does not equal governance authority.

### Knowledge

Knowledge can be centralized, authority not.

## 10. Ecosystem authority preservation

NDF remains Development Governance Framework authority.

Core Brain remains Knowledge and Evidence Plane.

Core-Dev remains Engineering Control Plane and engineering-readiness authority.

CoreOps remains Operations Control Plane and operational-state authority.

CDS remains scoped design and presentation authority.

Products retain product-specific authority.

Core Vision owns only legitimate T0 ecosystem-governance state within its accepted domain.

## 11. Conditions carried forward

Architecture adoption does not close implementation conditions.

The following remain unresolved and must be addressed by later governed work:

- exact canonical database schema
- exact EF Core entity model
- exact Human permission model
- exact authorization policy representation
- exact secret-store implementation
- exact HTTPS / certificate topology
- exact PostgreSQL backup mechanism
- exact migration execution procedure
- exact external OIDC provider
- exact AI provider
- exact AI model
- exact AI credential mechanism
- exact OpenTelemetry backend
- exact OCI runtime
- exact reverse proxy
- RPO
- RTO
- latency objectives
- CPU budget
- memory budget
- storage budget

These unresolved implementation details do not invalidate the accepted architecture baseline.

## 12. Implementation authorization boundary

These architecture decisions do not authorize:

- application source-code implementation
- database schema implementation
- dependency installation
- production migration
- production deployment
- production environment creation
- production credentials
- AI-provider credentials
- external integration activation

Implementation State:

NOT AUTHORIZED

A later explicit governance decision is required to open implementation work.

## 13. Decision authority

These architecture decisions became effective through explicit Human Maintainer authorization after successful completion of the CV-WP-007 Final Architecture Adoption Review.

Authorization Date:

2026-08-09

Decision State:

ACCEPTED

Implementation State:

NOT AUTHORIZED

## 14. Conclusion

Core Vision now has an accepted software-architecture and technology baseline.

The architecture is intentionally compact, authority-preserving and evolution-ready.

Future technology changes must preserve the accepted architecture invariants or be processed as material architecture changes.

Knowledge can be centralized, authority not.
