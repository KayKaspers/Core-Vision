# Core Vision Technology Scorecard

## 1. Purpose

This document performs the CV-WP-007 Part-5B HARD-gate and weighted technology evaluation.

It uses:

- the 189-requirement CV-AR baseline
- the Part-5A frozen candidate set
- the Part-5A primary-source evidence snapshot
- the Part-5A frozen 100-point weighting model

No weight or candidate rating was changed after scoring began.

## 2. Evaluation status

Architecture:

RECOMMENDED / NOT YET FORMALLY ADOPTED

Technology Selection:

RECOMMENDATION GENERATED / NOT YET AUTHORIZED

Implementation:

NOT AUTHORIZED

## 3. Scoring method

Candidate ratings use a 0-to-5 architecture-fit scale.

Scores are architecture assessments, not performance benchmarks.

HARD requirements take precedence over every weighted score.

For narrower roles, only materially applicable frozen dimensions are used.

Scores are calculated using decimal arithmetic.

Displayed one-decimal scores use:

MIDPOINT ROUNDING AWAY FROM ZERO

This explicit rule prevents runtime-dependent midpoint ambiguity.

## 4. HARD-gate summary

| Candidate | HARD-gate result | Evidence confidence | Disposition |
|---|---|---|---|
| APP-A .NET 10 / ASP.NET Core 10 | PASS | HIGH | RECOMMENDED |
| APP-B Python 3.14 / Django 5.2 LTS | PASS | HIGH | VIABLE |
| APP-C Node.js 24 LTS / NestJS 11 | PASS WITH CONDITIONS | MEDIUM-HIGH | VIABLE / NOT PREFERRED |
| APP-D Java 25 / Spring Boot 4.1 | PASS WITH CONDITIONS | MEDIUM | VIABLE |
| DB-A PostgreSQL 18 | PASS | HIGH | RECOMMENDED |
| DB-B MariaDB 12.3 LTS | PASS WITH CONDITIONS | MEDIUM | VIABLE |
| DB-C SQLite 3.53 | PASS WITH CONDITIONS | HIGH | BOUNDED USE / NOT PREFERRED PRODUCTION CANONICAL |
| UI-A Blazor Web App | PASS | HIGH | RECOMMENDED WITH APP-A |
| UI-B React 19.2 | PASS | HIGH | VIABLE |
| IAM-A Application-native identity | PASS | HIGH | RECOMMENDED INITIAL |
| IAM-B Keycloak 26.7 | PASS | HIGH | VIABLE FUTURE |
| RULE-A Application-native deterministic rules | PASS | ARCHITECTURE-NATIVE | RECOMMENDED |
| RULE-B Open Policy Agent 1.17 | PASS | HIGH | VIABLE |
| RULE-C NRules | PASS WITH CONDITIONS | MEDIUM-LOW | NOT PREFERRED |
| AI-A Core Vision-owned AI provider port | PASS | ARCHITECTURE-NATIVE | RECOMMENDED CONTRACT |
| AI-B Microsoft.Extensions.AI behind Core Vision port | PASS WITH CONDITIONS | MEDIUM-HIGH | RECOMMENDED ADAPTER CANDIDATE |
| AI-C Direct provider SDK coupling | FAIL | ROLE-DEPENDENT | REJECTED |
| OBS-A Health Checks + OpenTelemetry | PASS | HIGH | RECOMMENDED |
| BG-A In-process bounded background execution | PASS | ARCHITECTURE-NATIVE | RECOMMENDED INITIAL |
| BG-B Auxiliary worker | PASS WITH CONDITIONS | TRIGGER-DEPENDENT | DEFER UNTIL JUSTIFIED |
| BG-C Broker-based distributed execution | NO CURRENT NEED | N/A | DEFERRED |
| PKG-A OCI-compatible container image | PASS | HIGH | RECOMMENDED |
| PKG-B Native host process / service | PASS | HIGH | VIABLE |
| PKG-C Kubernetes / orchestration cluster | NO CURRENT NEED | N/A | NOT BASELINE |
| SEARCH-A Persistence-native query/search | PASS | ROLE-DEPENDENT | RECOMMENDED INITIAL |
| RETRIEVAL-A Governance-native contextual retrieval | PASS | ARCHITECTURE-NATIVE | RECOMMENDED INITIAL |
| RETRIEVAL-B Vector database | NO CURRENT NEED | N/A | DEFERRED |
| RETRIEVAL-C Graph database | NO CURRENT NEED | N/A | DEFERRED |

## 5. Application runtime weighted evaluation

| Dimension | Weight | APP-A | APP-B | APP-C | APP-D |
|---|---:|---:|---:|---:|---:|
| Architectural Fit | 14 | 5.00 | 4.50 | 4.25 | 4.75 |
| Security | 9 | 5.00 | 5.00 | 4.25 | 5.00 |
| Data Integrity | 8 | 5.00 | 4.50 | 4.00 | 5.00 |
| Auditability | 7 | 5.00 | 4.50 | 4.00 | 5.00 |
| Maintainability | 8 | 5.00 | 4.50 | 4.00 | 4.25 |
| Human Maintainer Operability | 8 | 5.00 | 4.50 | 4.00 | 3.50 |
| Portability | 6 | 5.00 | 5.00 | 5.00 | 5.00 |
| Ecosystem Lock-In Risk | 5 | 4.50 | 5.00 | 5.00 | 4.50 |
| Technology Maturity | 5 | 5.00 | 5.00 | 4.50 | 5.00 |
| Documentation Quality | 4 | 5.00 | 5.00 | 4.50 | 5.00 |
| Operational Complexity | 6 | 5.00 | 4.50 | 4.00 | 3.50 |
| Resource Efficiency | 4 | 4.00 | 4.50 | 4.50 | 3.00 |
| Testing Support | 4 | 5.00 | 5.00 | 4.50 | 5.00 |
| Integration Flexibility | 4 | 5.00 | 4.50 | 5.00 | 5.00 |
| AI Neutrality | 3 | 4.50 | 5.00 | 5.00 | 5.00 |
| Migration / Exit Capability | 5 | 4.50 | 4.50 | 4.00 | 4.50 |
| **Normalized weighted score** | **100** | **97.9** | **93.6** | **86.5** | **91.3** |

Ranking:

1. APP-A — 97.9
2. APP-B — 93.6
3. APP-D — 91.3
4. APP-C — 86.5

Recommendation:

APP-A — .NET 10 / ASP.NET Core 10.

APP-B remains the strongest alternative.

APP-D remains technically strong but requires more initial stack and operational decisions.

APP-C remains viable but has more unresolved supporting-stack decisions.

## 6. Canonical persistence weighted evaluation

| Dimension | Weight | DB-A | DB-B | DB-C |
|---|---:|---:|---:|---:|
| Architectural Fit | 14 | 5.00 | 4.50 | 3.50 |
| Security | 9 | 5.00 | 4.50 | 3.75 |
| Data Integrity | 8 | 5.00 | 4.75 | 4.25 |
| Auditability | 7 | 5.00 | 4.50 | 4.00 |
| Maintainability | 8 | 4.75 | 4.00 | 5.00 |
| Human Maintainer Operability | 8 | 4.50 | 4.50 | 5.00 |
| Portability | 6 | 5.00 | 5.00 | 5.00 |
| Ecosystem Lock-In Risk | 5 | 5.00 | 5.00 | 5.00 |
| Technology Maturity | 5 | 5.00 | 5.00 | 5.00 |
| Documentation Quality | 4 | 5.00 | 4.25 | 5.00 |
| Operational Complexity | 6 | 4.25 | 4.25 | 5.00 |
| Resource Efficiency | 4 | 4.00 | 4.25 | 5.00 |
| Testing Support | 4 | 5.00 | 4.75 | 5.00 |
| Integration Flexibility | 4 | 5.00 | 4.50 | 4.00 |
| AI Neutrality | 3 | 5.00 | 5.00 | 5.00 |
| Migration / Exit Capability | 5 | 5.00 | 4.75 | 4.50 |
| **Normalized weighted score** | **100** | **97.1** | **91.3** | **89.7** |

Ranking:

1. DB-A — 97.1
2. DB-B — 91.3
3. DB-C — 89.7

Recommendation:

DB-A — PostgreSQL 18.

DB-B remains viable with explicit maintenance-horizon evidence conditions.

DB-C remains useful for bounded roles and testing but is not preferred as the server-primary production canonical baseline.

## 7. Data access and migration

Preferred combination:

EF Core 10
+ Npgsql EF Core provider
+ PostgreSQL 18

Status:

RECOMMENDED WITH APP-A + DB-A

Architecture requirements include:

- explicit versioned migrations
- migration review
- controlled deployment execution
- pre-migration validation
- post-migration validation
- rollback or forward-recovery planning
- optimistic concurrency support where required
- transactional consistency for material canonical effects

## 8. Human-facing UI evaluation

| Dimension | Weight | UI-A | UI-B |
|---|---:|---:|---:|
| Architectural Fit | 14 | 5.00 | 4.00 |
| Security | 9 | 4.75 | 4.25 |
| Maintainability | 8 | 5.00 | 4.25 |
| Human Maintainer Operability | 8 | 5.00 | 3.75 |
| Portability | 6 | 5.00 | 5.00 |
| Ecosystem Lock-In Risk | 5 | 4.25 | 5.00 |
| Technology Maturity | 5 | 4.75 | 5.00 |
| Documentation Quality | 4 | 5.00 | 5.00 |
| Operational Complexity | 6 | 5.00 | 3.50 |
| Resource Efficiency | 4 | 4.25 | 4.25 |
| Testing Support | 4 | 4.50 | 5.00 |
| Integration Flexibility | 4 | 4.75 | 5.00 |
| Migration / Exit Capability | 5 | 4.00 | 4.50 |
| **Normalized weighted score** | **82** | **95.5** | **87.5** |

Ranking:

1. UI-A — 95.5
2. UI-B — 87.5

Recommendation:

UI-A — Blazor Web App with APP-A.

Preferred posture:

- server-primary
- server rendering baseline
- interactive server behavior where justified
- client-side execution only when requirements justify it

React remains a viable alternative if later UI evidence demonstrates a material limitation.

## 9. Identity evaluation

| Dimension | Weight | IAM-A | IAM-B |
|---|---:|---:|---:|
| Architectural Fit | 14 | 5.00 | 3.75 |
| Security | 9 | 4.75 | 5.00 |
| Auditability | 7 | 4.50 | 5.00 |
| Maintainability | 8 | 5.00 | 4.00 |
| Human Maintainer Operability | 8 | 5.00 | 3.00 |
| Portability | 6 | 5.00 | 5.00 |
| Ecosystem Lock-In Risk | 5 | 4.25 | 5.00 |
| Technology Maturity | 5 | 5.00 | 5.00 |
| Documentation Quality | 4 | 5.00 | 4.75 |
| Operational Complexity | 6 | 5.00 | 2.50 |
| Testing Support | 4 | 5.00 | 4.50 |
| Integration Flexibility | 4 | 4.50 | 5.00 |
| Migration / Exit Capability | 5 | 4.00 | 4.50 |
| **Normalized weighted score** | **85** | **96.1** | **85.4** |

Ranking:

1. IAM-A — 96.1
2. IAM-B — 85.4

Recommendation:

Initial application-native authentication through ASP.NET Core Identity.

Core Vision governance authorization remains Core Vision-owned domain logic.

Authentication must not determine:

- authority domain
- Decision Owner
- governance approval
- canonical effect

An external OIDC-compatible seam remains required for future evolution.

Keycloak remains viable if future federation or ecosystem-wide SSO requirements justify the additional service.

## 10. Deterministic-rule evaluation

| Dimension | Weight | RULE-A | RULE-B | RULE-C |
|---|---:|---:|---:|---:|
| Architectural Fit | 14 | 5.00 | 3.75 | 4.00 |
| Security | 9 | 5.00 | 4.75 | 4.25 |
| Data Integrity | 8 | 5.00 | 4.50 | 4.50 |
| Auditability | 7 | 5.00 | 4.75 | 4.25 |
| Maintainability | 8 | 5.00 | 4.00 | 4.00 |
| Human Maintainer Operability | 8 | 5.00 | 3.00 | 4.00 |
| Portability | 6 | 5.00 | 5.00 | 5.00 |
| Ecosystem Lock-In Risk | 5 | 5.00 | 5.00 | 4.50 |
| Technology Maturity | 5 | 4.50 | 5.00 | 4.00 |
| Documentation Quality | 4 | 4.00 | 4.75 | 3.75 |
| Operational Complexity | 6 | 5.00 | 2.75 | 4.25 |
| Resource Efficiency | 4 | 5.00 | 4.00 | 4.00 |
| Testing Support | 4 | 5.00 | 5.00 | 4.50 |
| Integration Flexibility | 4 | 4.50 | 5.00 | 4.00 |
| Migration / Exit Capability | 5 | 5.00 | 4.25 | 4.00 |
| **Normalized weighted score** | **97** | **98.2** | **85.2** | **83.9** |

Ranking:

1. RULE-A — 98.2
2. RULE-B — 85.2
3. RULE-C — 83.9

Recommendation:

Core Vision application-native deterministic rule module.

Required semantics include:

- stable rule identity
- revision
- lifecycle
- authority basis
- deterministic evaluation
- PASS
- FAIL
- BLOCKED
- WARNING
- UNKNOWN
- exception semantics
- explainability
- Human-approval separation

OPA remains a viable future candidate if independent policy distribution becomes a demonstrated requirement.

## 11. AI abstraction evaluation

| Dimension | Weight | AI-A | AI-B |
|---|---:|---:|---:|
| Architectural Fit | 14 | 5.00 | 5.00 |
| Security | 9 | 5.00 | 4.75 |
| Maintainability | 8 | 5.00 | 4.75 |
| Human Maintainer Operability | 8 | 4.50 | 5.00 |
| Portability | 6 | 5.00 | 5.00 |
| Ecosystem Lock-In Risk | 5 | 5.00 | 4.75 |
| Technology Maturity | 5 | 4.00 | 4.00 |
| Documentation Quality | 4 | 4.00 | 4.50 |
| Operational Complexity | 6 | 5.00 | 4.75 |
| Resource Efficiency | 4 | 5.00 | 4.50 |
| Testing Support | 4 | 5.00 | 5.00 |
| Integration Flexibility | 4 | 4.50 | 5.00 |
| AI Neutrality | 3 | 5.00 | 5.00 |
| Migration / Exit Capability | 5 | 5.00 | 4.75 |
| **Normalized weighted score** | **85** | **96.5** | **95.9** |

Ranking:

1. AI-A — 96.5
2. AI-B — 95.9

AI-C does not proceed because direct provider coupling fails the Core Vision provider-boundary requirement.

Recommended architecture:

Core Vision-owned AI provider port
→ optional adapter
→ AI provider / model

Preferred current adapter candidate for APP-A:

Microsoft.Extensions.AI

Provider-specific and experimental semantics must remain behind the Core Vision-owned boundary.

## 12. Observability

Recommended baseline:

- ASP.NET Core Health Checks
- OpenTelemetry

Governance Audit remains distinct from operational telemetry.

No proprietary APM backend becomes an architectural requirement.

## 13. Background execution

Recommended initial baseline:

bounded in-process background execution.

Candidate workloads include:

- scheduled governance validation
- evidence refresh
- report preparation
- projection refresh
- bounded housekeeping

Auxiliary workers remain future extraction seams.

Worker extraction requires measurable evidence.

No message broker is selected initially.

## 14. Deployment packaging

Recommended:

OCI-compatible container image.

This selects a portable packaging standard.

It does not select:

- mandatory Docker runtime
- mandatory Podman runtime
- Kubernetes
- cloud provider

Native host execution remains viable for development, diagnostics or bounded deployment cases.

## 15. Search and retrieval

Recommended initial search:

canonical persistence-native and application-native query capabilities.

Recommended initial AI context:

governed contextual retrieval from:

- canonical state
- governed projections
- evidence references
- application query contracts

Deferred:

- dedicated search server
- graph database
- vector database

Derived retrieval stores remain non-authoritative if introduced later.

## 16. Preferred coherent technology baseline

Architecture:

MODULAR GOVERNANCE MONOLITH

Runtime:

SERVER-PRIMARY

Primary application:

.NET 10
ASP.NET Core 10

Canonical persistence:

PostgreSQL 18

Data access / migration:

EF Core 10
Npgsql EF Core provider

Human UI:

Blazor Web App

Identity:

ASP.NET Core Identity initially

Governance authorization:

Core Vision-owned application/domain authorization

External identity evolution:

OIDC-compatible seam preserved

Deterministic rules:

Core Vision application-native rule module

AI:

Core Vision-owned AI provider port

Optional current adapter candidate:

Microsoft.Extensions.AI

Observability:

ASP.NET Core Health Checks
OpenTelemetry

Background execution:

In-process initially
Auxiliary workers only when justified

Packaging:

OCI-compatible image

Search:

Persistence/application native initially

## 17. Explicit non-selections

The initial baseline does not select:

- Kubernetes
- microservices
- mandatory auxiliary worker
- message broker
- distributed cache
- dedicated search server
- graph database
- vector database
- external policy engine
- mandatory Keycloak
- mandatory separate JavaScript SPA runtime
- direct domain-facing AI-provider SDK coupling

These are evidence-deferred rather than permanently prohibited.

## 18. Alternative coherent stack

Strongest alternative:

Python 3.14
+ Django 5.2 LTS
+ PostgreSQL 18
+ Django ORM / migrations
+ framework-native Human UI
+ application-native authentication
+ Core Vision application-native deterministic rules
+ Core Vision-owned AI provider boundary
+ OpenTelemetry-compatible observability
+ OCI packaging

Status:

VIABLE / NOT PREFERRED

No HARD governance requirement rejects this alternative.

## 19. Java / Spring alternative

Java 25 + Spring Boot 4.1 + PostgreSQL:

VIABLE WITH CONDITIONS

Open conditions include:

- JDK distribution
- support/licensing evidence
- persistence/migration composition
- UI composition
- identity composition

## 20. Node / Nest alternative

Node.js 24 LTS + NestJS 11:

VIABLE WITH CONDITIONS / NOT PREFERRED

Open composition decisions include:

- canonical data-access layer
- migrations
- initial identity implementation
- integrated server/UI posture

No HARD governance requirement rejects it.

## 21. Architecture recommendation

Modular Governance Monolith:

RECOMMENDED FOR FORMAL ADOPTION IN PART 6

Server-primary:

RECOMMENDED FOR FORMAL ADOPTION IN PART 6

Part 5B does not itself formally adopt either decision.

## 22. Technology recommendation

Technology State:

RECOMMENDED / NOT YET AUTHORIZED

Preferred baseline:

.NET 10 / ASP.NET Core 10
+ PostgreSQL 18
+ EF Core 10 / Npgsql
+ Blazor Web App
+ ASP.NET Core Identity
+ Core Vision application-native deterministic rules
+ Core Vision-owned AI provider port
+ optional Microsoft.Extensions.AI adapter
+ ASP.NET Core Health Checks
+ OpenTelemetry
+ in-process background execution
+ OCI-compatible packaging
+ persistence-native search initially

## 23. Architecture decision gates

Gate A — Authority Integrity:

PASS

Gate B — State Integrity:

PASS

Gate C — Auditability:

PASS

Gate D — Security:

PASS WITH IMPLEMENTATION CONDITIONS

Gate E — Recoverability:

PASS WITH IMPLEMENTATION CONDITIONS

Gate F — Standalone Operation:

PASS

Gate G — Technology Evidence:

PASS WITH CONDITIONS

No gate authorizes implementation by itself.

## 24. Material unresolved implementation conditions

Still unresolved by design:

- exact PostgreSQL backup mechanism
- exact secret-store implementation
- exact HTTPS / certificate termination topology
- exact external OIDC provider
- exact Human permission model
- exact canonical schema
- exact EF Core entity model
- exact migration execution procedure
- exact AI provider
- exact AI model
- exact AI credential mechanism
- exact OpenTelemetry backend
- exact OCI runtime
- exact reverse proxy
- RPO
- RTO
- concrete latency target
- CPU budget
- memory budget
- storage budget

These remain implementation-definition concerns unless Part 6 classifies one as architecture-blocking.

## 25. ADR candidates

### ADR Candidate A

Adopt Modular Governance Monolith.

### ADR Candidate B

Adopt server-primary runtime.

### ADR Candidate C

Adopt .NET 10 / ASP.NET Core 10.

### ADR Candidate D

Adopt PostgreSQL 18 canonical persistence.

### ADR Candidate E

Adopt EF Core 10 + Npgsql.

### ADR Candidate F

Adopt Blazor Web App.

### ADR Candidate G

Adopt application-native authentication through ASP.NET Core Identity while preserving external OIDC compatibility.

### ADR Candidate H

Keep Core Vision governance authorization distinct from generic identity roles.

### ADR Candidate I

Use application-native deterministic governance rules initially.

### ADR Candidate J

Adopt Core Vision-owned AI provider abstraction.

### ADR Candidate K

Permit Microsoft.Extensions.AI as an optional adapter behind that abstraction.

### ADR Candidate L

Adopt Health Checks + OpenTelemetry observability baseline.

### ADR Candidate M

Use bounded in-process background execution initially and require evidence before worker extraction.

### ADR Candidate N

Use OCI-compatible packaging without adopting Kubernetes.

### ADR Candidate O

Defer dedicated search, graph and vector infrastructure until justified.

Related ADR candidates may be consolidated during Part 6 when consolidation improves governance clarity.

## 26. Implementation boundary

Part 5B does not authorize:

- application source-code implementation
- database schema implementation
- dependency installation
- production migration
- container deployment
- production environment creation
- production credentials
- AI-provider credentials
- external integration activation

Implementation remains:

NOT AUTHORIZED

## 27. Part 6 handoff

Part 6 must:

1. review architecture adoption
2. review server-primary adoption
3. review preferred technology baseline
4. consolidate ADR materiality
5. preserve rejected alternatives
6. preserve deferred infrastructure
7. review unresolved conditions
8. regress against CV-WP-003 through CV-WP-006
9. verify architecture principles
10. verify Human Maintainer authority
11. decide CV-WP-007 completion state
12. recommend first implementation/bootstrap WP

## 28. Conclusion

The frozen evaluation method produces the following leading results:

APP-A:

97.9

DB-A:

97.1

UI-A:

95.5

IAM-A:

96.1

RULE-A:

98.2

AI-A:

96.5

The preferred architecture and technology baseline are sufficiently evidenced for Part-6 formal decision review.

They remain not implementation-authorized.

Knowledge can be centralized, authority not.
