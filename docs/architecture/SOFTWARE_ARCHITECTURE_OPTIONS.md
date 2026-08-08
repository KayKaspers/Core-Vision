# Core Vision Software Architecture Options

## 1. Purpose

This document concludes CV-WP-006 architecture discovery by comparing viable technology-independent architecture shapes for future Core Vision software.

It evaluates:

- application shape
- logical module boundaries
- runtime posture
- UI posture
- persistence posture
- integration posture
- AI placement
- rule evaluation placement
- deployment posture
- offline behavior
- security implications
- operational complexity
- evolution paths

This document may recommend a preferred architecture.

A recommendation is not implementation authorization.

No implementation stack is selected here.

## 2. Discovery inputs

The architecture options must satisfy the findings established by:

- CV-WP-003 Ecosystem Architecture & Boundaries
- CV-WP-004 Project Lifecycle, Intake & Cross-Project Governance
- CV-WP-005 Integration Model
- CV-WP-006 Software Responsibility Model
- CV-WP-006 Human / Rule / AI Authority Model
- CV-WP-006 Information and State Model

The software architecture must follow these governance semantics.

The governance semantics must not be rewritten merely to fit a preferred software architecture.

## 3. Binding architecture constraints

Any viable architecture must preserve:

1. Standalone First
2. Public Interface First
3. No Implicit First-Party Trust
4. Graceful Absence
5. No Bootstrap Cycles
6. Authority Preservation

Any option that violates these principles is not viable.

## 4. Core authority constraint

Core Vision software may become authoritative for legitimate Core Vision governance state.

It must not become authoritative for:

- CoreOps current operational state
- Core-Dev engineering readiness
- NDF development governance
- external source-domain facts retained by Core Brain
- CDS product-domain semantics
- product-specific behavior
- product business state

Knowledge can be centralized, authority not.

## 5. Application-shape criteria

Architecture options are compared using the following criteria:

- semantic clarity
- governance-authority safety
- deterministic-rule reliability
- Human-approval integrity
- AI isolation
- auditability
- consistency of canonical governance state
- offline capability
- graceful absence
- external integration isolation
- security-boundary clarity
- deployment simplicity
- operational simplicity
- backup and restore simplicity
- migration portability
- testability
- future multi-user readiness
- evolution capability
- avoidable distributed-system complexity
- implementation risk

## 6. Architecture Option A — Modular Governance Monolith

Option A uses one primary deployable Core Vision application boundary.

Inside that application, responsibilities remain explicitly modular.

Candidate logical modules include:

### Governance Core

- canonical governance state
- portfolio governance
- lifecycle governance
- authority governance
- capability governance
- integration governance

### Rule Evaluation

- rule definitions
- deterministic evaluations
- blocking and advisory results
- rule revision handling

### Governance Cases and Decisions

- governance cases
- recommendations
- Decision Owner
- Human decisions
- proposed effects
- exceptions
- authorized effects

### Evidence Boundary

- evidence references
- evidence retrieval
- bounded evidence retention
- provenance
- freshness handling

### AI Analysis Boundary

- AI requests
- context preparation
- AI analysis
- recommendation drafting
- AI provenance
- AI availability state

### History and Audit

- material governance history
- decision linkage
- state transition history
- rule-evaluation history
- exception history

### Projection and Reporting

- portfolio views
- authority maps
- integration maps
- dashboards
- reports
- historical projections

### User Interaction

- Human Maintainer interface
- governance case review
- evidence inspection
- rule-result inspection
- AI-analysis inspection
- Human authorization

### External Integration Boundary

- Core Brain adapter
- Core-Dev adapter
- CoreOps adapter
- CDS adapter
- product adapters
- repository or external-source adapters

These are internal responsibility boundaries.

They are not independently deployable services by default.

## 7. Option A canonical-state posture

Option A places Core Vision canonical governance state behind one primary application authority boundary.

Only explicitly authorized application paths may mutate canonical state.

Logical modules must not gain unrestricted write authority merely because they exist in the same process or deployment unit.

The architecture must preserve semantic write boundaries even when technical deployment is consolidated.

## 8. Option A AI posture

AI remains optional and replaceable.

The modular application may invoke AI through a bounded AI Analysis Boundary.

AI may be:

- unavailable
- disabled
- replaced
- externally provided
- locally provided

without changing canonical governance semantics.

AI must not require unrestricted direct access to canonical persistence.

AI output enters Core Vision as analysis or recommendation.

It does not enter directly as authorized state.

## 9. Option A deterministic-rule posture

Deterministic rule evaluation remains logically separate from:

- AI analysis
- Human decision
- presentation

Rule execution may initially reside inside the primary application boundary.

Rule lifecycle and rule activation remain governed separately from rule execution.

## 10. Option A integration posture

All external Core integrations enter through governed integration boundaries.

The primary application must not allow other Core projects to depend on:

- private persistence
- internal object models
- undocumented files
- internal UI endpoints

External contracts remain intentional and replaceable where practical.

## 11. Option A strengths

Strengths include:

- strong consistency around canonical governance state
- comparatively simple authorization boundaries
- comparatively simple transactional reasoning
- comparatively simple backup and restore
- easier offline-capable deployment
- lower operational overhead
- easier initial auditability
- simpler end-to-end testing
- lower bootstrap complexity
- reduced distributed failure modes
- lower risk of accidental authority duplication
- easier Human Maintainer operation

## 12. Option A risks

Risks include:

- internal module boundaries may erode without discipline
- one deployment unit may grow large
- long-running AI or integration work may interfere with interactive work if poorly isolated
- future independent scaling may require extraction
- future larger teams may create pressure for stronger technical boundaries

These risks are manageable through explicit modular architecture and evolution triggers.

## 13. Architecture Option B — Governance Core with Auxiliary Workers

Option B retains a primary authoritative Governance Core but allows selected responsibilities to execute in separately deployable auxiliary workers.

Candidate auxiliary responsibilities may include:

- AI analysis
- evidence synchronization
- repository scanning
- long-running reports
- expensive projections
- integration polling
- asynchronous notifications

The Governance Core remains the only primary canonical governance authority boundary.

## 14. Option B authority posture

Workers must not independently own canonical governance authority.

A worker may:

- retrieve
- analyze
- calculate
- prepare
- report

A worker may submit:

- analysis
- evidence
- recommendation
- proposed change

Canonical mutation remains governed through the Governance Core.

## 15. Option B strengths

Strengths include:

- stronger workload isolation
- AI failures can be isolated
- expensive integrations can be isolated
- long-running tasks need not block interactive work
- selected components can scale independently
- privilege boundaries can be narrower
- external integrations can be operationally separated

## 16. Option B risks

Risks include:

- increased deployment complexity
- asynchronous consistency concerns
- retry and duplicate-handling complexity
- additional health monitoring
- more complex backup and recovery reasoning
- more complex debugging
- increased operational dependencies
- greater risk of hidden mandatory worker dependencies

Option B therefore requires disciplined graceful-absence behavior.

## 17. Option B suitability

Option B becomes attractive if evidence later shows that:

- AI workloads need strong isolation
- integration workloads are materially long-running
- external adapters require different trust boundaries
- background processing materially affects primary responsiveness
- selected workloads need independent scaling
- security requires process-level or deployment-level isolation

These conditions are evolution triggers.

They are not assumed today.

## 18. Architecture Option C — Distributed Capability Services

Option C separates major Core Vision responsibilities into independently deployable services.

Possible service domains could include:

- governance-state service
- authority service
- integration-governance service
- rule service
- governance-case service
- evidence service
- AI-analysis service
- history service
- reporting service
- UI backend

This is the most distributed architecture option considered.

## 19. Option C strengths

Potential strengths include:

- independent scaling
- stronger deployment isolation
- independent release cadence
- narrow technical ownership boundaries
- independent failure containment where well designed
- future organizational scalability

## 20. Option C risks

Risks include:

- distributed-state complexity
- cross-service transaction complexity
- consistency challenges
- significantly higher operational cost
- more authentication surfaces
- more authorization surfaces
- more version compatibility requirements
- more failure states
- more retry and idempotency requirements
- increased bootstrap-cycle risk
- increased audit reconstruction complexity
- increased risk of authority appearing duplicated across services

## 21. Option C suitability

Option C is not justified merely because Core Vision has multiple logical responsibilities.

Logical separation does not require deployment separation.

Option C would require evidence of architectural pressure that cannot reasonably be addressed by Options A or B.

No such evidence currently exists in CV-WP-006.

## 22. Option comparison

| Criterion | Option A Modular Monolith | Option B Core + Workers | Option C Distributed Services |
|---|---|---|---|
| Governance-state consistency | Strong | Strong if Core remains authoritative | Complex |
| Authority-boundary clarity | Strong | Strong with disciplined worker boundary | Harder across services |
| Human approval integrity | Simple | Simple to moderate | More distributed |
| AI isolation | Logical | Strong technical isolation | Strong |
| Operational complexity | Low | Medium | High |
| Deployment complexity | Low | Medium | High |
| Offline capability | Strong candidate | Moderate | Difficult |
| Backup / restore | Comparatively simple | Moderate | Complex |
| Distributed failure modes | Low | Medium | High |
| Initial implementation risk | Lowest | Medium | Highest |
| Independent scaling | Limited initially | Selective | Strong |
| Evolution capability | Strong with modular discipline | Strong | Strong |
| Current evidence of need | Strong | Conditional | Weak |

## 23. Preferred application architecture

The preferred discovery recommendation is:

> Option A — Modular Governance Monolith.

This is a recommendation for the initial Core Vision software architecture.

It is not implementation authorization.

The recommendation is based on the current governance and operational requirements rather than on fashion or framework preference.

## 24. Preferred architecture rationale

Option A is preferred because Core Vision's primary architectural challenge is:

- semantic integrity
- authority preservation
- deterministic governance
- Human approval
- auditability
- relationship-rich governance data

rather than:

- extreme throughput
- massive horizontal scale
- independent high-volume public services
- globally distributed runtime processing

A consolidated authority boundary reduces unnecessary distributed-system complexity during the initial architecture lifecycle.

## 25. Modular-monolith requirement

The recommendation is specifically for a modular monolith.

It is not a recommendation for an unstructured monolith.

Internal boundaries should remain explicit around:

- Governance Core
- Rule Evaluation
- Cases and Decisions
- Evidence
- AI Analysis
- History and Audit
- Reporting
- UI/application interaction
- External Integrations
- Identity and Access

A future implementation should make these boundaries testable and inspectable.

## 26. Evolution posture

Option A should be designed so that selected responsibilities may later be extracted if evidence justifies it.

Likely extraction candidates include:

- AI processing
- expensive evidence synchronization
- long-running external integration work
- heavy reporting or projection generation

Canonical governance authority should remain intentionally centralized even if auxiliary responsibilities later become distributed.

## 27. Evolution from A to B

The expected first evolution path is:

> Modular Governance Monolith
> → Governance Core with selected Auxiliary Workers

Extraction should occur only when a measurable requirement justifies it.

Examples include:

- workload isolation
- reliability isolation
- security isolation
- performance
- operational scheduling
- independent scaling

Premature extraction should be avoided.

## 28. Evolution toward C

A fully distributed capability-service architecture should require stronger evidence.

Possible future triggers include:

- materially larger development organization
- independently governed deployment teams
- major scaling differences between capabilities
- strong regulatory isolation requirements
- availability requirements incompatible with a consolidated application
- independently consumed external Core Vision capabilities

CV-WP-006 does not establish these conditions.

## 29. Runtime posture options

The discovery considers three broad runtime postures:

### Local-primary

Core Vision runs primarily on a Human Maintainer workstation.

### Server-primary

Core Vision runs as a persistent server-side application and is accessed by a Human-facing client or browser interface.

### Hybrid

A server retains canonical governance state while selected local capabilities support offline or disconnected workflows.

## 30. Local-primary assessment

Potential advantages:

- simple personal operation
- strong local control
- straightforward initial setup
- possible offline use

Potential disadvantages:

- availability depends on one workstation
- weaker persistent-service posture
- harder remote access
- future multi-user evolution may require larger redesign
- backup discipline may depend on workstation operation

Local-primary remains viable for development or bounded standalone use.

It is not the preferred long-term primary posture.

## 31. Server-primary assessment

Potential advantages:

- durable always-available governance state
- centralized backup target
- consistent canonical authority boundary
- browser-based multi-device access becomes feasible
- easier future multi-user evolution
- easier integration polling and scheduled governance checks
- cleaner separation between Human client and governance state

Potential disadvantages:

- requires server operation
- requires authentication boundary
- offline use requires explicit design
- server availability becomes relevant to Core Vision itself

Core Vision server unavailability must still not stop other Core projects.

## 32. Hybrid assessment

Hybrid architecture may later provide:

- server-side canonical governance state
- local read capability
- selected cached evidence
- offline case preparation
- deferred synchronization

Hybrid operation creates additional complexity around:

- freshness
- proposed state
- conflict resolution
- stale approval context
- synchronization

Hybrid capability should therefore be added only when a concrete offline requirement justifies it.

## 33. Preferred runtime posture

The preferred discovery recommendation is:

> Server-primary Core Vision application with optional future offline-capable extensions.

Reasons include:

- persistent governance state
- centralized audit history
- consistent Human approval boundary
- future multi-device access
- integration scheduling
- future multi-user readiness
- easier operational backup

This is an architecture recommendation.

No server technology or deployment platform is selected.

## 34. Single-user versus multi-user posture

Initial Core Vision operation may remain Human-Maintainer-centered.

The information and authority model should not permanently hard-code:

> exactly one user can ever exist.

The preferred posture is therefore:

> single-authority-first, multi-actor-ready.

This means:

- initial workflow may optimize for one Human Maintainer
- actor identity remains explicit
- Decision Owner remains explicit
- authority remains domain-aware
- future consultation or delegated roles remain possible

CV-WP-006 does not define a full RBAC or multi-user product model.

## 35. UI posture

The preferred UI posture is a Human-facing web-capable application interface over explicit application boundaries.

The UI should support:

- portfolio view
- project view
- lifecycle view
- authority map
- capability map
- integration map
- governance-case review
- evidence inspection
- rule-result inspection
- AI analysis
- recommendation review
- Human decision
- history
- administration

The UI must not access canonical persistence as an undocumented direct client.

## 36. UI architecture boundary

The UI should interact with application capabilities through an explicit application boundary.

The exact technology may later be:

- server-rendered
- browser application
- another client model
- combination

No frontend architecture is selected by CV-WP-006.

## 37. CDS posture

Core Vision UI should consume applicable CDS foundations when mature and available.

CDS integration should be optional for Core Vision governance bootstrap.

If CDS is temporarily unavailable:

- existing adopted design artifacts may continue to be used
- governance logic remains available
- canonical governance state remains available

CDS does not become governance authority.

## 38. API posture

Future Core Vision software will likely require explicit application and integration boundaries.

CV-WP-006 does not select an API protocol.

The architecture should distinguish:

### Human-facing application boundary

Used by Core Vision UI or future authorized clients.

### External integration boundary

Used for governed interaction with other systems.

### Internal module boundary

Used to preserve responsibility separation inside the application.

These boundaries may use different technical mechanisms later.

## 39. Persistence posture

The preferred persistence posture is:

> one canonical governance authority boundary with semantically separated current state, history, evidence references and derived representations.

This does not require one physical database.

It does not prohibit one physical database.

Physical storage design remains deferred.

## 40. Canonical persistence

Canonical persistence must support:

- Core Vision-owned governance state
- authorized mutation
- Decision Owner linkage
- Human decision linkage
- rule linkage
- exception semantics
- lifecycle semantics
- authority semantics

Canonical persistence should not be designed around AI retrieval requirements.

## 41. Historical persistence

History must preserve material governance meaning.

Architecture definition must later evaluate whether current state and history should use:

- the same physical store
- separate logical structures
- append-oriented records
- snapshots
- another auditable approach

No choice is made in CV-WP-006.

## 42. Evidence persistence

The default posture should favor:

- governed evidence references

over:

- indiscriminate copying of all external evidence.

Durable local evidence retention should be used when justified by:

- audit
- resilience
- historical preservation
- availability
- governance requirement

## 43. Derived representations

Derived representations may later include:

- search index
- AI retrieval index
- projections
- cached external state
- generated reports
- calculated indicators

Derived representations must be reconstructable where practical.

Loss of a derived representation should not normally destroy canonical governance authority.

## 44. AI runtime posture

AI is an optional analytical capability.

The architecture should support an AI provider boundary rather than embedding one vendor's semantics into canonical governance state.

Possible future AI execution models include:

- remote provider
- local model
- self-hosted service
- multiple providers
- AI-disabled mode

CV-WP-006 does not select among them.

## 45. AI failure posture

If AI is unavailable:

- canonical governance state remains accessible
- deterministic rules remain usable
- Human decisions remain possible
- historical records remain accessible
- manual evidence review remains possible

AI availability must not become a bootstrap requirement.

## 46. AI privilege posture

AI should normally receive:

- bounded read context
- explicit analysis task
- minimum necessary evidence

AI should normally produce:

- analysis
- recommendation
- proposed material

AI should not receive unrestricted canonical mutation capability.

## 47. Rule-engine posture

Deterministic rules should be represented explicitly enough to be:

- versioned
- tested
- explainable
- traceable to authority basis

The rule evaluation mechanism may initially live inside the modular application boundary.

CV-WP-006 does not select:

- rules DSL
- policy engine
- programming-language implementation
- external rules product

## 48. External integration posture

External integrations should be isolated behind governed boundaries.

A specific integration should not reshape Core Vision's canonical information model around the external system's private schema.

Adapters or equivalent anti-corruption boundaries should be evaluated during architecture definition.

The exact pattern remains to be defined.

## 49. Core Brain posture

Core Brain is an optional Knowledge and Evidence Plane integration.

Core Vision may use it for:

- evidence retrieval
- knowledge relationships
- historical context
- contextual search

Core Vision canonical governance state must not depend on Core Brain being available.

Core Vision and Core Brain must not form a bootstrap cycle.

## 50. Core-Dev posture

Core Vision may consume Core-Dev engineering evidence.

Core-Dev remains authoritative for engineering readiness.

Core Vision may use that evidence for:

- governance review
- lifecycle analysis
- architecture assessment
- release-related ecosystem visibility

Core Vision does not become engineering execution authority.

## 51. CoreOps posture

Core Vision may consume CoreOps operational evidence.

CoreOps remains authoritative for:

- current operational state
- runtime deployment execution
- operational evidence within its scope

Core Vision may visualize or analyze this information.

It does not become runtime control merely because it displays an operational dashboard.

## 52. Deployment responsibility

Future Core Vision software may itself be deployed and operated by:

- Human Maintainer directly
- CoreOps through an authorized integration
- another explicitly authorized operational mechanism

Who operates Core Vision software does not determine who owns Core Vision governance authority.

## 53. Core Vision outage posture

A Core Vision outage may temporarily prevent:

- governance review
- new Human approvals
- portfolio updates
- Core Vision analysis
- Core Vision reporting

A Core Vision outage must not automatically prevent:

- CoreOps runtime operation
- Core-Dev engineering work
- Core Brain operation
- CDS use by existing consumers
- normal product runtime

This preserves Core Vision outside the ecosystem runtime critical path.

## 54. Offline posture

The preferred initial architecture should preserve the option for:

- backup inspection
- exports
- local recovery
- selected cached read views
- later offline case preparation

Full multi-master offline mutation is not an initial requirement.

Offline write synchronization would materially increase conflict and authority complexity.

## 55. Backup and restore posture

Canonical governance state and material history require reliable backup and restore.

Architecture definition should prioritize:

- consistent backup
- inspectable backup
- validated restore
- portability
- history preservation
- authority-linkage preservation

Backup technology remains deferred.

## 56. Export posture

Material governance information should be exportable in a form suitable for:

- review
- backup
- migration
- audit
- future tooling

Export must not silently become the new canonical authority.

No export format is selected here.

## 57. Security posture

The preferred architecture must support explicit boundaries for:

- Human identity
- Human authorization
- system identity
- AI identity
- external integrations
- read access
- mutation access
- approval authority
- administration

Technical administrator privilege must not silently equal governance authority.

## 58. Secret posture

Core Vision should avoid becoming a universal ecosystem secret store.

It may require credentials for its own integrations.

Credentials should be:

- purpose-bounded
- least-privilege
- replaceable
- isolated from AI where unnecessary

Secret-management technology remains deferred.

## 59. Observability posture

Core Vision needs observability for its own operation.

Candidate observability includes:

- application health
- persistence health
- integration health
- stale external evidence
- rule-evaluation failures
- AI availability
- background-task health
- backup readiness

Observability does not become governance authority.

## 60. Architecture decision matrix

| Area | Preferred discovery posture |
|---|---|
| Application shape | Modular Governance Monolith |
| Canonical authority | One primary Governance Core boundary |
| Runtime | Server-primary |
| Initial user posture | Human-Maintainer-centered |
| Future user posture | Multi-actor-ready |
| UI | Web-capable Human-facing interface |
| UI authority | None independently |
| Deterministic rules | Explicit internal logical boundary |
| AI | Optional, replaceable analytical boundary |
| AI canonical writes | Not allowed directly |
| External integrations | Governed adapter boundaries |
| Core Brain | Optional evidence/knowledge integration |
| Core-Dev | External engineering authority |
| CoreOps | External operational authority |
| CDS | Optional presentation foundation |
| Products | External product-domain authorities |
| Canonical persistence | Central governance authority boundary |
| Evidence | Reference-first, retain when justified |
| History | Durable and semantically distinct |
| Search / AI retrieval | Derived representation |
| Offline mutation | Not initial requirement |
| Service decomposition | Deferred until evidence justifies |
| Technology stack | Deferred |

## 61. Why not Microservices First

Core Vision currently lacks evidence requiring a distributed-service architecture.

Starting distributed would introduce complexity in exactly the areas Core Vision must keep trustworthy:

- authority
- state consistency
- Human decisions
- audit history
- rule execution
- proposed-versus-effective state

Microservices are therefore not rejected forever.

They are rejected as an unjustified initial default.

## 62. Why not AI-Centric Architecture

Core Vision is not an AI application with governance added around it.

Core Vision is a governance system that may use AI.

Therefore:

- canonical state must be independently understandable
- deterministic rules must operate without AI
- Human authorization must operate without AI
- history must remain inspectable without AI
- AI retrieval structures remain secondary

AI should improve reasoning.

AI should not define the ontology of authority.

## 63. Why not Core Brain as the canonical database

Core Brain has a different architectural responsibility.

Core Brain may centralize:

- knowledge
- evidence
- relationships
- retrieval

Core Vision must own its legitimate governance state independently.

Using Core Brain as the only canonical Core Vision persistence layer would risk:

- bootstrap coupling
- authority ambiguity
- knowledge-state versus governance-state collapse

Therefore Core Brain should remain an integration option, not the sole Core Vision governance store.

## 64. Why not CoreOps as the control backend

CoreOps operates runtime and infrastructure.

Core Vision governs ecosystem strategy and architecture.

Using CoreOps as the canonical Core Vision governance backend would blur:

- operational authority
- ecosystem governance authority

CoreOps may deploy or operate Core Vision software.

It must not thereby own Core Vision governance semantics.

## 65. Why not Core-Dev as the governance backend

Core-Dev owns engineering readiness and engineering control functions.

Core Vision has broader ecosystem governance responsibilities.

Core-Dev may supply:

- engineering evidence
- release-readiness information
- engineering status

It must not become the canonical authority for Core Vision portfolio and architecture governance.

## 66. Architecture fitness tests

A future architecture definition should be rejected if it cannot answer clearly:

- Where is canonical Core Vision governance state?
- Who may mutate it?
- How is Human authorization represented?
- How are deterministic rules distinguished from AI?
- How is AI output distinguished from decisions?
- How are external authority domains represented?
- How does the system behave when AI is unavailable?
- How does it behave when Core Brain is unavailable?
- How does it behave when CoreOps is unavailable?
- How does it behave when Core-Dev is unavailable?
- How is history preserved?
- How are exceptions represented?
- How are stale external facts represented?
- How is a proposed effect prevented from becoming state before authorization?

## 67. Evolution triggers

Architecture should be reconsidered when evidence shows:

- primary application workload cannot be isolated adequately
- AI workload causes unacceptable availability or security risk
- external integrations require stronger runtime isolation
- multi-user concurrency materially changes governance needs
- availability requirements exceed the current deployment shape
- data volume invalidates current persistence assumptions
- independent teams require independent deployment ownership
- regulatory isolation becomes mandatory
- offline mutation becomes a real requirement
- external consumers require independently scalable Core Vision capabilities

Architecture evolution must be evidence-driven.

## 68. Deferred technology decisions

CV-WP-006 explicitly leaves the following undecided:

- programming language
- backend framework
- frontend framework
- database product
- relational versus document implementation
- graph storage
- vector storage
- search engine
- ORM
- rule engine
- policy language
- API protocol
- asynchronous messaging technology
- background-job technology
- identity provider
- authorization product
- secrets product
- AI vendor
- AI model
- AI orchestration framework
- container technology
- orchestration platform
- hosting platform
- backup product
- observability product

These decisions require later explicit evaluation.

## 69. Preferred architecture recommendation

The preferred discovery recommendation is:

> Build Core Vision initially as a server-primary Modular Governance Monolith with one explicit canonical governance authority boundary, strong internal semantic modules, governed external integration boundaries, deterministic rules separated from AI reasoning, explicit Human authorization, durable governance history, and optional replaceable AI assistance.

The architecture should be capable of evolving selected non-authoritative workloads into auxiliary workers if evidence later justifies extraction.

A distributed-service architecture should remain a future option rather than the initial default.

## 70. Recommendation status

The preferred architecture is:

RECOMMENDED

It is not:

- IMPLEMENTATION AUTHORIZED
- TECHNOLOGY SELECTED
- STACK APPROVED
- DEPLOYMENT APPROVED

A later explicitly authorized architecture-definition decision is required before implementation begins.

## 71. Recommended next architecture Work Package

After CV-WP-006 closure, Core Vision should create the next architecture-definition Work Package.

Recommended scope:

> Core Vision Software Architecture Definition and Technology Evaluation

That Work Package should:

1. convert the preferred discovery architecture into a formal component model
2. define explicit module contracts
3. define canonical mutation boundaries
4. define persistence requirements in implementable terms
5. define security and identity requirements
6. define deployment topology requirements
7. define AI provider abstraction requirements
8. define external adapter contracts
9. compare candidate technology stacks against the architecture requirements
10. produce explicit ADR candidates for material technology choices

Technology evaluation must follow architecture requirements.

Technology preference must not rewrite governance semantics.

## 72. Technology evaluation criteria for the next phase

Future technology candidates should be evaluated using criteria such as:

- semantic fit
- maintainability
- Human Maintainer operability
- ecosystem neutrality
- portability
- security
- auditability
- offline capability
- migration capability
- testing quality
- documentation quality
- dependency risk
- maturity
- community health
- long-term support
- AI integration flexibility
- integration-contract support
- operational burden
- resource requirements

Technology popularity alone is insufficient.

## 73. Architecture Discovery conclusion

CV-WP-006 discovery indicates that Core Vision should be designed primarily as a trustworthy governance system.

Its architecture should optimize first for:

- explicit authority
- semantic integrity
- Human control
- deterministic governance
- auditable decisions
- replaceable AI assistance
- bounded external integrations
- operational simplicity
- evolution without premature distribution

The recommended starting architecture is therefore a Modular Governance Monolith rather than a distributed control plane.

Core Vision should centralize governance knowledge where useful.

It must not centralize unrelated project authority.

Knowledge can be centralized, authority not.
