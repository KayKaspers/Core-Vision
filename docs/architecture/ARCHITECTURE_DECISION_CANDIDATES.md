# Core Vision Architecture Decision Candidates

## 1. Purpose

This document consolidates the fifteen CV-WP-007 Part-5B ADR candidates into a smaller set of material architecture decisions.

The consolidation prevents unnecessary ADR fragmentation while preserving all material decisions.

These were the decision candidates reviewed by CV-WP-007.

They were adopted through CV-ADR-001 through CV-ADR-006 after successful final review and explicit Human Maintainer authorization.

Decision State:

ADOPTED

Implementation:

NOT AUTHORIZED

## 2. Decision materiality principle

A separate architecture decision is justified where a choice materially affects one or more of:

- Core Vision architecture
- governance authority
- canonical state integrity
- security boundary
- major technology baseline
- operational topology
- migration or exit strategy

Closely coupled choices may be consolidated when separate records would create governance noise without improving traceability.

## 3. Consolidation result

The fifteen Part-5B ADR candidates are consolidated into six material decision candidates:

1. CV-AD-CAND-001 — Application Architecture and Runtime Posture
2. CV-AD-CAND-002 — Application Platform and Human UI
3. CV-AD-CAND-003 — Canonical Persistence and Data Access
4. CV-AD-CAND-004 — Identity and Governance Authorization
5. CV-AD-CAND-005 — Deterministic Rules and AI Boundary
6. CV-AD-CAND-006 — Operations, Packaging and Evolution

## 4. CV-AD-CAND-001 — Application Architecture and Runtime Posture

### Proposed decision

Adopt:

MODULAR GOVERNANCE MONOLITH

as the initial Core Vision application architecture.

Adopt:

SERVER-PRIMARY

as the initial Core Vision runtime posture.

### Rationale

The architecture requirements do not currently justify distributed capability services.

The component and contract models demonstrate that Core Vision can preserve:

- module boundaries
- one canonical mutation boundary
- explicit Human authorization
- deterministic rule isolation
- AI isolation
- evidence provenance
- external integration boundaries
- durable history
- future worker extraction seams

inside one primary application deployment boundary.

Server-primary operation supports:

- durable canonical state
- centralized authorization
- browser-capable Human access
- backup
- audit history
- scheduled governance work
- future multi-actor access

### Constraints

The Modular Governance Monolith must not become an unstructured monolith.

Logical module contracts remain mandatory.

Core Vision must remain outside the mandatory runtime path of other Core systems.

### Rejected initial alternative

Distributed capability services.

Reason:

No current HARD requirement justifies the added:

- network boundaries
- distributed consistency
- retry complexity
- deployment complexity
- authority-duplication risk

### Evolution

Selected workloads may later be extracted into auxiliary workers when evidence demonstrates:

- workload isolation
- security isolation
- reliability isolation
- long-running execution
- scheduling constraints
- independent scaling

Canonical authority must remain preserved.

### Part-5B mapping

Consolidates:

- ADR Candidate A
- ADR Candidate B
- relevant architecture portion of ADR Candidate M

## 5. CV-AD-CAND-002 — Application Platform and Human UI

### Proposed decision

Adopt:

.NET 10 LTS

and:

ASP.NET Core 10

as the initial primary application platform.

Adopt:

Blazor Web App

as the initial Human-facing UI technology.

### Evidence

Part-5B application runtime ranking:

1. APP-A — 97.9
2. APP-B — 93.6
3. APP-D — 91.3
4. APP-C — 86.5

Part-5B UI ranking:

1. UI-A — 95.5
2. UI-B — 87.5

### Rationale

The preferred platform provides a cohesive architecture for:

- server application
- module boundaries
- Human-facing UI
- authentication
- authorization extension points
- health
- background execution
- testing
- persistence integration
- AI adapter integration

This reduces unnecessary initial stack breadth.

### UI posture

Prefer:

- server-primary rendering
- interactive server behavior where useful
- client-side execution only where justified

A separate JavaScript SPA runtime is not currently required.

### Alternative retained

Python 3.14 + Django 5.2 LTS remains:

VIABLE / NOT PREFERRED

No HARD governance requirement rejects it.

### Conditional alternatives

Java 25 + Spring Boot 4.1:

VIABLE WITH CONDITIONS

Node.js 24 LTS + NestJS 11:

VIABLE WITH CONDITIONS / NOT PREFERRED

### Part-5B mapping

Consolidates:

- ADR Candidate C
- ADR Candidate F

## 6. CV-AD-CAND-003 — Canonical Persistence and Data Access

### Proposed decision

Adopt:

PostgreSQL 18

as the initial canonical persistence technology.

Adopt:

EF Core 10

with:

Npgsql EF Core provider

as the initial data-access and migration baseline.

### Evidence

Part-5B persistence ranking:

1. DB-A — 97.1
2. DB-B — 91.3
3. DB-C — 89.7

### Rationale

The combination provides a credible implementation path for:

- durable canonical state
- atomic governance effects
- integrity constraints
- concurrency detection
- relationship-rich queries
- migration
- backup and restore
- portability
- self-hosting

### Migration posture

Production persistence evolution must use:

- version-controlled migrations
- review
- pre-migration validation
- controlled execution
- post-migration validation
- rollback or forward-recovery planning

Uncontrolled arbitrary production schema mutation at application startup is not the governance baseline.

### Alternative retained

MariaDB 12.3 LTS:

VIABLE WITH CONDITIONS

Its Part-5A support-horizon evidence gap remains visible.

### Bounded-use alternative

SQLite remains suitable for bounded roles such as:

- tests
- tools
- possibly local non-production workloads

It is not the preferred server-primary canonical production baseline.

### Explicit non-selection

No graph database is required initially.

No vector database is required initially.

No dedicated search persistence is required initially.

### Part-5B mapping

Consolidates:

- ADR Candidate D
- ADR Candidate E
- persistence/search portion of ADR Candidate O

## 7. CV-AD-CAND-004 — Identity and Governance Authorization

### Proposed decision

Adopt:

ASP.NET Core Identity

as the initial application-native authentication and identity baseline.

Preserve:

external OIDC-compatible authentication integration

as an explicit future evolution seam.

Keep:

Core Vision governance authorization

separate from generic identity and application roles.

### Evidence

Part-5B identity ranking:

1. IAM-A — 96.1
2. IAM-B — 85.4

### Binding distinction

The architecture must preserve:

identity
≠ authentication
≠ application permission
≠ governance authority
≠ Decision Owner
≠ Human approval

A generic identity role must not silently grant Core Vision governance authority.

### Keycloak posture

Keycloak remains:

VIABLE FUTURE OPTION

It may become justified by:

- federation
- ecosystem-wide SSO
- directory integration
- multiple applications
- centralized identity lifecycle

It is not required for initial Core Vision bootstrap.

### Part-5B mapping

Consolidates:

- ADR Candidate G
- ADR Candidate H

## 8. CV-AD-CAND-005 — Deterministic Rules and AI Boundary

### Proposed deterministic-rule decision

Implement deterministic Core Vision governance rules as an application-native rule module initially.

Do not adopt an external rule or policy service initially.

### Evidence

Part-5B rule ranking:

1. RULE-A — 98.2
2. RULE-B — 85.2
3. RULE-C — 83.9

### Required rule semantics

The rule module must preserve:

- rule identity
- revision
- lifecycle
- authority basis
- PASS
- FAIL
- BLOCKED
- WARNING
- UNKNOWN
- exception semantics
- deterministic reproducibility
- explainability
- Human-approval separation

### OPA posture

Open Policy Agent remains:

VIABLE FUTURE OPTION

if later evidence demonstrates need for:

- independent policy distribution
- cross-application policy use
- separately governed policy execution

### Proposed AI decision

Adopt:

Core Vision-owned AI provider port

as the binding AI architecture.

Permit:

Microsoft.Extensions.AI

as an optional current .NET adapter candidate behind that Core Vision-owned boundary.

### Evidence

Part-5B AI ranking:

1. AI-A — 96.5
2. AI-B — 95.9

Direct provider SDK coupling into governance modules is rejected.

### AI authority guardrail

AI remains:

- optional
- replaceable
- non-authoritative
- unable to directly mutate canonical governance state
- unable to impersonate Human approval
- unable to replace deterministic rule truth

### Part-5B mapping

Consolidates:

- ADR Candidate I
- ADR Candidate J
- ADR Candidate K

## 9. CV-AD-CAND-006 — Operations, Packaging and Evolution

### Proposed observability decision

Adopt:

ASP.NET Core Health Checks
+ OpenTelemetry

as the initial observability baseline.

Governance Audit remains separate from operational telemetry.

### Proposed background-execution decision

Use:

bounded in-process background execution

initially.

Do not require auxiliary workers initially.

Worker extraction remains evidence-driven.

### Proposed packaging decision

Adopt:

OCI-compatible container image

as the preferred production packaging format.

This does not select a mandatory container engine.

This does not select Kubernetes.

### Initial non-selections

Do not initially require:

- Kubernetes
- microservices
- message broker
- distributed cache
- dedicated search server
- graph database
- vector database
- mandatory auxiliary worker
- mandatory dedicated identity server
- external policy service

### Search posture

Use:

persistence-native
and
application-native

query capabilities initially.

### Evolution principle

New infrastructure must have a demonstrated purpose.

Technology must not be added merely because it is common in modern stacks.

### Part-5B mapping

Consolidates:

- ADR Candidate L
- ADR Candidate M
- ADR Candidate N
- ADR Candidate O

## 10. Candidate decision dependencies

The six decisions have dependencies but do not transfer authority among one another.

CV-AD-CAND-001 establishes application topology.

CV-AD-CAND-002 selects the primary application platform compatible with that topology.

CV-AD-CAND-003 selects canonical persistence and access technology.

CV-AD-CAND-004 establishes authentication architecture while preserving governance authorization.

CV-AD-CAND-005 establishes deterministic-rule and AI boundaries.

CV-AD-CAND-006 establishes initial operational posture and evidence-driven evolution constraints.

## 11. Rejected assumptions

The decision set explicitly rejects the assumptions that:

- modular architecture requires microservices
- server operation requires Kubernetes
- background work requires a message broker
- relationship-rich data requires a graph database
- AI requires a vector database
- web UI requires a separate JavaScript SPA
- authentication requires a dedicated external identity server
- deterministic governance requires an external policy engine
- AI integration may directly define Core Vision governance contracts

## 12. Human decision boundary

These candidates may become accepted architecture decisions only after:

1. final regression review
2. architecture-principle review
3. authority-boundary review
4. technology-evidence review
5. unresolved-condition review
6. explicit Human Maintainer authorization

Silence is not adoption.

Execution of this preparation script is not itself formal adoption.

## 13. Implementation boundary

Even if all six decisions are later accepted, implementation remains a separate authorization boundary.

Architecture adoption does not itself authorize:

- source-code implementation
- database schema creation
- dependency installation
- production deployment
- production credentials
- external integration activation

## 14. Decision state

CV-AD-CAND-001:

ADOPTED

CV-AD-CAND-002:

ADOPTED

CV-AD-CAND-003:

ADOPTED

CV-AD-CAND-004:

ADOPTED

CV-AD-CAND-005:

ADOPTED

CV-AD-CAND-006:

ADOPTED

Implementation:

NOT AUTHORIZED

## 15. Conclusion

The fifteen Part-5B ADR candidates can be represented without material loss by six architecture decisions.

This provides sufficient decision granularity without creating unnecessary governance fragmentation.

No candidate is accepted merely because it is technically preferred.

Human authorization remains required.

Knowledge can be centralized, authority not.
## 16. Adoption Result

Adoption Date:

2026-08-09

Human Maintainer Authorization:

EXPLICIT

Final Adoption Review:

PASS

Candidate-to-Decision mapping:

| Candidate | Accepted decision |
|---|---|
| CV-AD-CAND-001 | CV-ADR-001 |
| CV-AD-CAND-002 | CV-ADR-002 |
| CV-AD-CAND-003 | CV-ADR-003 |
| CV-AD-CAND-004 | CV-ADR-004 |
| CV-AD-CAND-005 | CV-ADR-005 |
| CV-AD-CAND-006 | CV-ADR-006 |

Architecture Adoption:

ADOPTED

Technology Baseline:

ADOPTED

Implementation:

NOT AUTHORIZED

The candidate record is retained as decision provenance.

The accepted authoritative architecture decision record is:

`docs/architecture/ARCHITECTURE_DECISIONS.md`
