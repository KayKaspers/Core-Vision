# Core Vision Technology Evaluation

## 1. Purpose

This document records the technology-evaluation baseline for CV-WP-007 Part 5.

It freezes:

- evaluation date
- architecture requirement baseline
- hard-gate precedence
- weighted evaluation dimensions
- weights
- candidate roles
- candidate set
- current primary-source evidence
- evidence confidence
- known evidence gaps
- intentionally excluded baseline infrastructure

Scoring occurs only after this baseline is frozen.

Technology selection remains UNSELECTED.

Implementation remains NOT AUTHORIZED.

## 2. Evaluation snapshot

Research date:

2026-08-09

Architecture requirement baseline:

189 unique CV-AR requirements.

Architecture state:

MODULAR GOVERNANCE MONOLITH
RECOMMENDED / NOT YET FORMALLY ADOPTED

Runtime state:

SERVER-PRIMARY
RECOMMENDED / NOT YET FORMALLY ADOPTED

Technology Selection:

UNSELECTED

## 3. Evaluation invariant

Technology must fit the architecture.

The architecture must preserve governance.

A candidate must not receive architectural authority merely because it:

- stores data
- executes policy
- hosts identity
- runs AI
- renders UI
- operates deployment

Knowledge can be centralized, authority not.

## 4. Evaluation process

Technology evaluation uses two layers.

### Layer 1 — HARD gates

Applicable HARD CV-AR requirements are evaluated first.

Material HARD failure cannot be offset by weighted scoring.

Candidate result may be:

- HARD-GATE PASS
- HARD-GATE PASS WITH CONDITIONS
- HARD-GATE FAIL
- INSUFFICIENT EVIDENCE

### Layer 2 — Weighted scoring

Only candidates that survive applicable HARD gates proceed to weighted comparison.

The scoring scale is:

- 5 = excellent fit
- 4 = strong fit
- 3 = acceptable fit
- 2 = material weakness
- 1 = poor fit
- 0 = does not satisfy the evaluated dimension

UNKNOWN evidence is not automatically scored as 3, 4 or 5.

## 5. Frozen weighted dimensions

The following weights are frozen before candidate scoring.

| Dimension | Weight |
|---|---:|
| Architectural Fit | 14 |
| Security | 9 |
| Data Integrity | 8 |
| Auditability | 7 |
| Maintainability | 8 |
| Human Maintainer Operability | 8 |
| Portability | 6 |
| Ecosystem Lock-In Risk | 5 |
| Technology Maturity | 5 |
| Documentation Quality | 4 |
| Operational Complexity | 6 |
| Resource Efficiency | 4 |
| Testing Support | 4 |
| Integration Flexibility | 4 |
| AI Neutrality | 3 |
| Migration / Exit Capability | 5 |
| **Total** | **100** |

These weights must not be changed after candidate scoring begins unless:

- a material architecture requirement was omitted
- the reason is documented
- all candidates are rescored using the same revised weights
- the revision is explicitly reviewed

## 6. Weight rationale

Architectural Fit has the highest weight because Core Vision contains unusual authority, mutation and evidence semantics.

Security, Data Integrity and Auditability receive high weight because canonical governance state must remain trustworthy.

Maintainability and Human Maintainer Operability receive high weight because Core Vision should remain understandable and operable without a large platform team.

Operational Complexity receives meaningful weight because unnecessary distributed infrastructure conflicts with the current Modular Governance Monolith recommendation.

AI Neutrality has a smaller standalone weight because provider neutrality is also enforced through HARD requirements.

Hard gates remain more important than every weighted dimension.

## 7. Candidate-role principle

Candidates are evaluated by architecture role.

One product does not need to solve every concern.

The initial candidate roles are:

1. Primary Application Runtime / Backend
2. Canonical Persistence
3. Data Access / Migration
4. Human-facing UI
5. Authentication / Identity
6. Deterministic Rules
7. AI Provider Abstraction
8. Observability
9. Background Execution
10. Deployment Packaging
11. Search / Retrieval Baseline

## 8. Role 1 — Primary Application Runtime / Backend candidates

### APP-A — .NET 10 / ASP.NET Core 10

Evidence state:

VERIFIED

Current evidence snapshot:

- .NET 10 is an active LTS release.
- Current verified .NET 10 patch at research time: 10.0.10.
- .NET 10 support ends 2028-11-14.
- ASP.NET Core follows the .NET lifecycle.
- Cross-platform server operation is supported.

Primary evidence:

- https://dotnet.microsoft.com/en-us/platform/support/policy
- https://dotnet.microsoft.com/en-us/platform/support/policy/dotnet-core
- https://github.com/dotnet/aspnetcore

### APP-B — Python 3.14 / Django 5.2 LTS

Evidence state:

VERIFIED

Current evidence snapshot:

- Current verified Python 3 release: 3.14.6.
- Python 3.14.6 release date: 2026-06-10.
- Django 5.2 is an LTS series.
- Current verified Django 5.2 patch at research time: 5.2.16.
- Django 5.2 extended support ends April 2028.

Primary evidence:

- https://www.python.org/downloads/
- https://www.python.org/downloads/release/python-3146/
- https://www.djangoproject.com/download/
- https://github.com/django/django

### APP-C — Node.js 24 LTS / NestJS 11

Evidence state:

VERIFIED

Current evidence snapshot:

- Node.js 24 is an LTS line.
- Current verified Node.js 24 LTS release at research time: 24.18.0.
- Current verified NestJS release at research time: 11.1.24.
- NestJS is open source under the MIT license.

Primary evidence:

- https://nodejs.org/en/download
- https://nodejs.org/en/blog/release/v24.18.0
- https://github.com/nestjs/nest/releases
- https://github.com/nestjs/nest

### APP-D — Java 25 / Spring Boot 4.1

Evidence state:

PARTIALLY VERIFIED

Current evidence snapshot:

- Java 25 is an LTS release in Oracle's Java SE roadmap.
- Oracle's commercial Premier Support roadmap for Java 25 runs to September 2030.
- Spring Boot 4.1.0 is the current verified stable Spring Boot release at research time.
- Exact production JDK distribution and its licensing/support policy remain intentionally unselected.

Evidence gap:

The Java ecosystem candidate cannot receive a final support/licensing score until the JDK distribution is selected.

Primary evidence:

- https://www.oracle.com/java/technologies/java-se-support-roadmap.html
- https://spring.io/projects/spring-boot/
- https://spring.io/blog/2026/06/10/spring-boot-4/
- https://github.com/spring-projects/spring-boot

## 9. Role 2 — Canonical Persistence candidates

### DB-A — PostgreSQL 18

Evidence state:

VERIFIED

Current evidence snapshot:

- Current verified PostgreSQL 18 minor: 18.4.
- PostgreSQL 18 is supported.
- PostgreSQL 18 final support date: 2030-11-14.
- PostgreSQL major versions receive approximately five years of support.
- PostgreSQL uses the PostgreSQL License.

Primary evidence:

- https://www.postgresql.org/support/versioning/
- https://www.postgresql.org/docs/release/18.4/
- https://www.postgresql.org/about/licence/

### DB-B — MariaDB 12.3 LTS

Evidence state:

PARTIALLY VERIFIED

Current evidence snapshot:

- MariaDB 12.3 is designated LTS.
- Current verified stable release: 12.3.2.
- MariaDB Community LTS policy states three years of community binaries for new LTS lines.
- The official maintenance table currently lists the specific 12.3 GA and EOL dates as TBC.

Evidence gap:

Concrete 12.3 Community support dates remain not fully published in the official maintenance table.

This gap must not receive a favorable maintenance-horizon score until resolved.

Primary evidence:

- https://mariadb.org/mariadb-server-12-3-lts-released/
- https://mariadb.org/about/
- https://mariadb.org/mariadb/all-releases/

### DB-C — SQLite 3.53

Evidence state:

VERIFIED

Current evidence snapshot:

- Current verified release: SQLite 3.53.4, released 2026-07-24.
- SQLite is intentionally optimized for embedded/local application storage.
- SQLite permits multiple readers but only one writer at a time per database file.
- SQLite's own guidance recommends client/server database systems where many concurrent writers are required.

Evaluation note:

SQLite is retained as a control candidate because it provides exceptional operational simplicity.

Its suitability for the server-primary canonical multi-actor governance role must be determined by HARD-gate evaluation rather than assumption.

Primary evidence:

- https://sqlite.org/changes.html
- https://sqlite.org/whentouse.html

## 10. Role 3 — Data Access / Migration candidates

Data-access technology is coupled to the selected application runtime and persistence combination.

### DAL-A — EF Core 10 + Npgsql EF Core Provider

Applicable combination:

APP-A + DB-A

Evidence state:

VERIFIED

Current evidence snapshot:

- EF Core 10 is LTS.
- EF Core 10 support ends 2028-11-10.
- EF Core 10 requires .NET 10.
- Current verified Npgsql EF Core provider release: 10.0.2.
- Npgsql provides the EF Core provider for PostgreSQL.

Primary evidence:

- https://learn.microsoft.com/en-us/ef/core/what-is-new/ef-core-10.0/whatsnew
- https://github.com/npgsql/efcore.pg

### DAL-B — Django ORM / migrations

Applicable combination:

APP-B with supported relational persistence.

Evidence state:

VERIFIED AT FRAMEWORK LEVEL

Exact database-driver compatibility must be revalidated for the final persistence combination.

Primary evidence:

- https://docs.djangoproject.com/en/5.2/topics/db/
- https://docs.djangoproject.com/en/5.2/topics/migrations/

### DAL-C — Java persistence stack

Applicable combination:

APP-D

Evidence state:

DEFERRED

The exact JPA / ORM / migration combination is intentionally deferred until APP-D survives backend hard gates.

### DAL-D — Node persistence stack

Applicable combination:

APP-C

Evidence state:

DEFERRED

The exact Node ORM / query / migration combination is intentionally deferred until APP-C survives backend hard gates.

## 11. Role 4 — Human-facing UI candidates

### UI-A — Blazor Web App / Razor Components on .NET 10

Evidence state:

VERIFIED

Current evidence snapshot:

Blazor Web Apps support:

- Static Server rendering
- Interactive Server rendering
- Interactive WebAssembly
- Interactive Auto

The architecture may therefore use server-oriented interaction without requiring a separate JavaScript SPA architecture.

Primary evidence:

- https://learn.microsoft.com/en-us/aspnet/core/blazor/components/render-modes?view=aspnetcore-10.0
- https://learn.microsoft.com/en-us/aspnet/core/blazor/fundamentals/?view=aspnetcore-10.0

### UI-B — React 19.2

Evidence state:

VERIFIED AT MAJOR/MINOR LEVEL

Current evidence snapshot:

- Current official React documentation line: 19.2.

Exact framework/tooling composition around React is not yet selected.

Primary evidence:

- https://react.dev/versions

### UI-C — Framework-native server-rendered UI

Evidence state:

VIABLE CONCEPT / ROLE-DEPENDENT

This candidate represents a minimal server-rendered application UI using capabilities native to the selected backend ecosystem.

Exact technology depends on the backend winner.

It is retained to ensure a separate SPA framework is not treated as mandatory.

## 12. Role 5 — Authentication / Identity candidates

### IAM-A — Application-native identity

For APP-A, the primary concrete candidate is ASP.NET Core Identity.

Evidence state:

VERIFIED FOR .NET CANDIDATE

ASP.NET Core Identity supports application-managed concepts including:

- users
- roles
- claims
- tokens
- logins

ASP.NET Core also supports OpenID Connect integration with trusted external identity providers.

Governance authority remains Core Vision domain logic and must not be delegated to a generic identity role automatically.

Primary evidence:

- https://learn.microsoft.com/en-us/aspnet/core/security/authentication/customize-identity-model?view=aspnetcore-10.0
- https://learn.microsoft.com/en-us/aspnet/core/security/authentication/claims?view=aspnetcore-10.0
- https://learn.microsoft.com/en-us/aspnet/core/security/authorization/roles?view=aspnetcore-10.0

### IAM-B — Keycloak 26.7

Evidence state:

VERIFIED

Current verified release:

26.7.0, released 2026-07-09.

Keycloak is retained as the primary dedicated external identity-platform candidate.

Architecture concern:

Making a dedicated identity service mandatory adds a separately operated bootstrap dependency.

Hard-gate and weighted evaluation must decide whether that complexity is justified for initial Core Vision operation.

Primary evidence:

- https://www.keycloak.org/2026/07/keycloak-2670-released
- https://www.keycloak.org/documentation

### IAM-C — External OIDC-compatible identity provider boundary

Evidence state:

ARCHITECTURE APPROACH

Core Vision should remain capable of consuming a standards-based external identity provider later.

No specific hosted or external identity vendor is selected.

## 13. Role 6 — Deterministic Rules candidates

### RULE-A — Core Vision application-native deterministic rule module

Evidence state:

ARCHITECTURE-NATIVE CANDIDATE

Rules remain explicit Core Vision domain concepts implemented within the selected application runtime.

This candidate minimizes additional runtime dependencies.

It must still satisfy:

- rule identity
- revision
- lifecycle
- authority basis
- deterministic output
- explainability
- testability
- UNKNOWN
- blocking semantics
- exception semantics

### RULE-B — Open Policy Agent 1.17

Evidence state:

VERIFIED

Current verified release:

OPA 1.17.0.

OPA is a general-purpose policy engine and uses policy-as-code semantics.

Evaluation must determine whether an external policy engine improves Core Vision's governance rules enough to justify:

- another policy language
- another execution model
- additional contract mapping
- additional operational complexity

Primary evidence:

- https://github.com/open-policy-agent/opa/releases
- https://www.openpolicyagent.org/docs/latest/

### RULE-C — NRules

Evidence state:

PARTIALLY VERIFIED

Current project evidence confirms:

- open-source .NET rules engine
- Rete-based inference engine
- C# fluent DSL
- rule-model and testing capabilities
- MIT license

Exact current package release/version has not yet been verified from a sufficiently clear primary release source.

Evaluation note:

NRules inference and conflict-resolution semantics must not be assumed to match Core Vision's deterministic validation model.

Primary evidence:

- https://nrules.net/
- https://nrules.net/api/
- https://nrules.net/articles/getting-started.html

## 14. Role 7 — AI Provider Abstraction candidates

### AI-A — Core Vision-owned AI provider port

Evidence state:

ARCHITECTURE-NATIVE CANDIDATE

Core Vision defines its own narrow AI abstraction based on its semantic requirements.

Provider SDKs or libraries remain behind the Core Vision-owned boundary.

This candidate provides maximum protection against provider semantics leaking into canonical governance.

### AI-B — Core Vision port backed by Microsoft.Extensions.AI

Evidence state:

VERIFIED WITH MATURITY CAVEAT

Current verified Microsoft.Extensions.AI package release:

10.8.3, released 2026-07-27.

Microsoft.Extensions.AI provides abstractions intended to improve portability between AI services and models.

The current package line still contains some explicitly experimental APIs.

Architecture posture:

Even if selected, Microsoft.Extensions.AI would remain behind a Core Vision-owned AI boundary.

Core Vision canonical contracts must not directly depend on provider-specific or experimental AI semantics.

Primary evidence:

- https://github.com/dotnet/extensions/releases
- https://learn.microsoft.com/en-us/dotnet/ai/microsoft-extensions-ai
- https://dotnet.microsoft.com/en-us/platform/support/policy/extensions

### AI-C — Direct provider SDK coupling

Evidence state:

CONTROL CANDIDATE

This candidate directly couples Core Vision application semantics to a selected AI-provider SDK.

It is retained primarily to test the CV-AR-AI and CV-AR-PRT hard gates.

No AI provider is selected.

## 15. Role 8 — Observability candidates

### OBS-A — Framework-native health + OpenTelemetry

Evidence state:

VERIFIED CONCEPTUAL FIT

OpenTelemetry provides vendor-neutral telemetry concepts.

The .NET implementation provides tracing, metrics and logging support.

Framework-native health mechanisms may supplement OpenTelemetry for application health.

Primary evidence:

- https://opentelemetry.io/docs/languages/dotnet/
- https://learn.microsoft.com/en-us/aspnet/core/host-and-deploy/health-checks?view=aspnetcore-10.0

### OBS-B — Vendor-specific APM as primary dependency

Evidence state:

CONTROL CANDIDATE

No vendor is selected.

This candidate exists to evaluate whether a proprietary observability dependency would create unnecessary lock-in.

## 16. Role 9 — Background Execution candidates

### BG-A — In-process bounded background execution

Evidence state:

ARCHITECTURE-NATIVE CANDIDATE

Suitable candidate for:

- scheduled validation
- evidence refresh
- report generation
- bounded maintenance tasks

The selected runtime must provide safe lifecycle and cancellation handling.

### BG-B — Separately deployable auxiliary worker

Evidence state:

CONDITIONAL ARCHITECTURE CANDIDATE

Permitted only when justified by:

- workload isolation
- security isolation
- reliability isolation
- long-running execution
- scheduling
- independent scaling

No worker is justified merely because the application is modular.

### BG-C — Message-broker-based distributed execution

Evidence state:

DEFERRED / NOT BASELINE

No current HARD requirement requires a message broker.

A broker enters the candidate set only if a later architectural requirement demonstrates concrete value.

## 17. Role 10 — Deployment Packaging candidates

### PKG-A — OCI-compatible container image

Evidence state:

VERIFIED

Current verified OCI Image Specification release:

1.1.1.

OCI defines an open container image format independent of one particular container engine.

Selecting OCI-compatible packaging does not select:

- Docker
- Podman
- Kubernetes
- another runtime

Primary evidence:

- https://github.com/opencontainers/image-spec
- https://github.com/opencontainers/image-spec/releases

### PKG-B — Native host process / service

Evidence state:

VIABLE

A directly hosted server process remains a viable packaging comparison candidate.

### PKG-C — Kubernetes / orchestration cluster

Evidence state:

NOT BASELINE

No current Core Vision HARD requirement inherently requires a cluster orchestrator.

It must not enter the preferred initial stack solely because it is common in distributed systems.

## 18. Role 11 — Search / Retrieval Baseline

### SEARCH-A — Canonical persistence-native query/search

Evidence state:

BASELINE CANDIDATE

Use the capabilities of the canonical persistence and application query model first where sufficient.

### SEARCH-B — Dedicated search engine

Evidence state:

DEFERRED

No current HARD requirement proves a need for an independently operated search server.

### RETRIEVAL-A — Governance-native contextual retrieval

Evidence state:

BASELINE CANDIDATE

AI context is prepared from governed canonical state, evidence references and application queries.

### RETRIEVAL-B — Vector database

Evidence state:

DEFERRED

No current HARD requirement requires vector persistence.

A vector representation may later become a derived retrieval store.

It must never become canonical governance authority.

### RETRIEVAL-C — Graph database

Evidence state:

DEFERRED

The domain is relationship-rich.

Relationship richness alone does not prove that a graph database is required.

## 19. Primary-source registry

The following primary sources were reviewed for the 2026-08-09 evaluation snapshot.

| ID | Technology / concern | Primary source |
|---|---|---|
| SRC-001 | .NET support lifecycle | https://dotnet.microsoft.com/en-us/platform/support/policy |
| SRC-002 | .NET lifecycle details | https://dotnet.microsoft.com/en-us/platform/support/policy/dotnet-core |
| SRC-003 | ASP.NET Core source/license | https://github.com/dotnet/aspnetcore |
| SRC-004 | EF Core 10 | https://learn.microsoft.com/en-us/ef/core/what-is-new/ef-core-10.0/whatsnew |
| SRC-005 | Npgsql EF provider | https://github.com/npgsql/efcore.pg |
| SRC-006 | Blazor render modes | https://learn.microsoft.com/en-us/aspnet/core/blazor/components/render-modes?view=aspnetcore-10.0 |
| SRC-007 | ASP.NET Identity model | https://learn.microsoft.com/en-us/aspnet/core/security/authentication/customize-identity-model?view=aspnetcore-10.0 |
| SRC-008 | ASP.NET claims/OIDC | https://learn.microsoft.com/en-us/aspnet/core/security/authentication/claims?view=aspnetcore-10.0 |
| SRC-009 | Microsoft.Extensions.AI releases | https://github.com/dotnet/extensions/releases |
| SRC-010 | Microsoft.Extensions.AI docs | https://learn.microsoft.com/en-us/dotnet/ai/microsoft-extensions-ai |
| SRC-011 | PostgreSQL version policy | https://www.postgresql.org/support/versioning/ |
| SRC-012 | PostgreSQL 18.4 release | https://www.postgresql.org/docs/release/18.4/ |
| SRC-013 | PostgreSQL license | https://www.postgresql.org/about/licence/ |
| SRC-014 | MariaDB 12.3 LTS | https://mariadb.org/mariadb-server-12-3-lts-released/ |
| SRC-015 | MariaDB maintenance policy | https://mariadb.org/about/ |
| SRC-016 | SQLite release history | https://sqlite.org/changes.html |
| SRC-017 | SQLite appropriate uses | https://sqlite.org/whentouse.html |
| SRC-018 | Python releases | https://www.python.org/downloads/ |
| SRC-019 | Python 3.14.6 | https://www.python.org/downloads/release/python-3146/ |
| SRC-020 | Django downloads/support | https://www.djangoproject.com/download/ |
| SRC-021 | Node.js releases | https://nodejs.org/en/download |
| SRC-022 | Node.js 24.18.0 | https://nodejs.org/en/blog/release/v24.18.0 |
| SRC-023 | NestJS releases | https://github.com/nestjs/nest/releases |
| SRC-024 | Java SE roadmap | https://www.oracle.com/java/technologies/java-se-support-roadmap.html |
| SRC-025 | Spring Boot | https://spring.io/projects/spring-boot/ |
| SRC-026 | React versions | https://react.dev/versions |
| SRC-027 | Keycloak 26.7 | https://www.keycloak.org/2026/07/keycloak-2670-released |
| SRC-028 | OPA releases | https://github.com/open-policy-agent/opa/releases |
| SRC-029 | NRules | https://nrules.net/ |
| SRC-030 | OpenTelemetry .NET | https://opentelemetry.io/docs/languages/dotnet/ |
| SRC-031 | OCI Image Specification | https://github.com/opencontainers/image-spec/releases |

## 20. Evidence gaps

The following material gaps remain explicit before scoring.

### GAP-001 — Java runtime distribution

Java 25 is a valid architecture candidate.

A concrete JDK distribution is not yet selected.

Licensing and support scoring must therefore remain conditional.

### GAP-002 — MariaDB 12.3 support end date

MariaDB 12.3 is designated LTS.

The MariaDB Foundation maintenance table currently lists concrete 12.3 dates as TBC.

Long-term maintenance scoring must preserve this uncertainty.

### GAP-003 — NRules current package release

Current project documentation and licensing are available.

A sufficiently clear current official release-version record has not yet been established.

Version/maintenance scoring remains conditional.

### GAP-004 — Node data-access implementation

APP-C may survive application-runtime scoring.

Its final persistence-access/migration candidate must then be explicitly selected and verified.

### GAP-005 — Java data-access implementation

APP-D may survive application-runtime scoring.

Its final persistence-access/migration candidate must then be explicitly selected and verified.

### GAP-006 — Quantitative production load

Core Vision does not yet have evidence-backed values for:

- concurrent Human actors
- peak writes
- evidence volume
- AI volume
- latency SLO
- RPO
- RTO
- CPU budget
- memory budget

Candidates must not receive fabricated scale requirements.

## 21. Baseline exclusions

The following technologies are intentionally not treated as required initial stack components.

### Message broker

No current HARD requirement establishes a need.

### Distributed cache

No current HARD requirement establishes a need.

### Vector database

No current HARD requirement establishes a need.

### Graph database

Relationship density alone is insufficient justification.

### Dedicated search server

Canonical persistence-native search/query capabilities should be evaluated first.

### Kubernetes or similar orchestration cluster

No current HARD requirement requires distributed orchestration.

### Separate rule service

Logical rule separation does not require network distribution.

### Mandatory dedicated identity server

A dedicated IdP remains a candidate, not a bootstrap requirement.

## 22. Candidate-set freeze

The candidate set is frozen for initial Part-5 scoring.

New candidates may be added only when:

- an existing role lacks a viable candidate
- new primary evidence reveals a materially better option
- a HARD requirement exposes a missing capability
- the addition is documented before comparing final totals

Adding a candidate must not alter previously frozen weights.

## 23. No scoring yet

No candidate in this document has yet received a weighted architecture score.

Terms such as:

- candidate
- viable
- control candidate
- baseline candidate

do not constitute final recommendation.

No technology is selected by Part 5A.

## 24. Expected Part-5B evaluation sequence

Part 5B should proceed in the following order.

### 24.1 Primary application runtime

Apply applicable HARD gates to:

- APP-A
- APP-B
- APP-C
- APP-D

Then score surviving candidates using the frozen weights.

### 24.2 Canonical persistence

Apply HARD gates to:

- DB-A
- DB-B
- DB-C

### 24.3 Coherent application / persistence combinations

Evaluate combinations rather than isolated popularity.

### 24.4 UI

Evaluate whether:

- UI-A
- UI-B
- UI-C

best satisfies the selected architecture without unnecessary stack expansion.

### 24.5 Identity

Compare application-native identity with IAM-B and future external OIDC compatibility.

Governance authority remains application-domain semantics.

### 24.6 Deterministic rules

Compare:

- RULE-A
- RULE-B
- RULE-C

against reproducibility, explainability, authority-basis and operational-complexity requirements.

### 24.7 AI abstraction

Compare:

- AI-A
- AI-B
- AI-C

against provider-neutrality and canonical-authority requirements.

### 24.8 Supporting roles

Evaluate:

- observability
- background work
- packaging
- search/retrieval

using the smallest coherent stack principle.

## 25. Expected outputs from Part 5B

Part 5B must produce:

- hard-gate results by candidate
- score by weighted dimension
- weighted total
- evidence confidence
- material risks
- unresolved unknowns
- role recommendation
- coherent stack recommendation
- rejected unnecessary infrastructure
- ADR-candidate list

No implementation authorization may be issued by Part 5B.

## 26. Architecture state after Part 5A

Modular Governance Monolith:

RECOMMENDED / NOT YET FORMALLY ADOPTED

Server-primary:

RECOMMENDED / NOT YET FORMALLY ADOPTED

Technology Selection:

UNSELECTED

Implementation:

NOT AUTHORIZED

Weights:

FROZEN BEFORE SCORING

Candidate Set:

FROZEN FOR INITIAL EVALUATION

Primary-source snapshot:

2026-08-09

## 27. Conclusion

Core Vision technology evaluation now has:

- 189 architecture requirements
- explicit HARD gates
- fixed evaluation dimensions
- fixed weights totaling 100
- role-specific candidate sets
- current primary-source evidence
- explicit evidence gaps
- explicit baseline exclusions

Part 5B may now score candidates without changing the rules after seeing the result.

Technology must fit the architecture.

The architecture must preserve governance.

Knowledge can be centralized, authority not.
