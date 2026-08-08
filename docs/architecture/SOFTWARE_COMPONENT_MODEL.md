# Core Vision Software Component Model

## 1. Purpose

This document defines the formal logical component model for the future Core Vision application.

It translates the responsibility model discovered by CV-WP-006 into explicit application components, responsibility boundaries and dependency rules.

The model is designed to evaluate and refine the CV-WP-006 recommendation of a Modular Governance Monolith.

This document does not yet constitute final adoption of that architecture.

It does not select:

- programming language
- backend framework
- frontend framework
- persistence product
- API protocol
- rule engine
- AI provider
- identity provider
- deployment platform

Components defined here are logical application components.

They are not independently deployable services by default.

## 2. Architecture status

CV-WP-006 recommended:

- Modular Governance Monolith
- server-primary runtime

The recommendation remains:

RECOMMENDED / NOT YET FORMALLY ADOPTED

CV-WP-007 Part 2 defines a reference component topology against which the architecture can be evaluated.

Final architecture adoption remains subject to later CV-WP-007 decision and Human Maintainer authorization.

## 3. Governing architecture principle

The component model must preserve governance semantics.

Component structure must not create authority.

Technical dependency must not create authority.

Storage ownership must not create authority.

Operational ownership must not create authority.

Knowledge can be centralized, authority not.

## 4. Component model overview

The formal reference model contains the following logical components:

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

These components define semantic and dependency boundaries.

They do not define process or network boundaries.

## 5. Canonical Governance Core

### Purpose

The Canonical Governance Core is the authoritative application boundary for Core Vision-owned canonical governance state.

It is the only logical component permitted to apply an effective mutation to canonical Core Vision governance state.

Other components may:

- request a mutation
- prepare a mutation
- validate a mutation
- analyze a mutation
- authorize a mutation where they own the relevant authorization responsibility
- observe the resulting state

They must not bypass the Canonical Governance Core when an effective canonical state change is required.

### Responsibilities

Candidate responsibilities include:

- receive validated mutation requests
- verify required mutation preconditions
- verify required authorization evidence
- verify applicable blocking state
- apply authorized state effects
- expose current canonical governance state
- preserve state invariants
- coordinate required history recording
- reject unauthorized direct mutation
- preserve current-versus-proposed distinction

### Canonical domains

The Canonical Governance Core may maintain Core Vision-owned state such as:

- portfolio relationship
- Core Vision lifecycle state
- accepted ecosystem tier
- accepted capability assignment
- accepted authority assignment
- registered integration governance state
- accepted exception state
- accepted Core Vision governance decisions
- other explicitly authorized Core Vision governance state

It must not become authoritative for external source domains.

## 6. Canonical mutation rule

The component model establishes the following architecture invariant:

> Every effective mutation of Core Vision-owned canonical governance state must cross the Canonical Governance Core boundary.

This does not mean the component independently decides whether a mutation is legitimate.

Decision authority may belong to:

- Human Maintainer
- another explicitly authorized Decision Owner
- an already-authorized non-discretionary deterministic governance rule

The Canonical Governance Core applies legitimate effects.

It does not invent their authority.

## 7. Canonical mutation input

A canonical mutation request should conceptually contain or reference enough information to determine:

- target governance object
- intended effect
- initiating context
- applicable governance case where required
- authority basis
- Decision Owner where required
- Human authorization where required
- deterministic rule results where required
- active exception where applicable
- expected current state where concurrency or stale-state protection matters

The precise contract is defined in CV-WP-007 Part 3.

## 8. Canonical mutation prohibition

The following logical components must not independently apply canonical state effects:

- AI Analysis Boundary
- Evidence & Provenance Boundary
- Projection & Reporting
- Application / Human Interaction Boundary
- External Integration Boundary
- Administration & Health

Other governance components may define domain policy or request changes.

They still must use the Canonical Governance Core mutation boundary.

## 9. Portfolio & Lifecycle Governance

### Purpose

Own Core Vision application semantics for:

- portfolio relationship
- project lifecycle
- valid lifecycle transitions
- portfolio/lifecycle consistency

### Responsibilities

- interpret portfolio relationship semantics
- interpret lifecycle semantics
- validate candidate transitions
- expose domain-specific queries
- prepare mutation requests
- provide deterministic domain rules where appropriate

### Non-responsibilities

This component does not:

- auto-admit projects
- infer membership from repository existence
- independently authorize Human-governed transitions
- directly persist effective canonical changes outside the Canonical Governance Core

## 10. Authority & Capability Governance

### Purpose

Represent and govern:

- capability definitions
- authority domains
- authority assignments
- capability assignments
- conflicts between capability and authority claims

### Responsibilities

- validate authority-assignment semantics
- validate capability-assignment semantics
- detect conflicting authority claims
- preserve capability-versus-authority distinction
- prepare proposed authority changes
- expose current authority maps

### Non-responsibilities

This component must not infer authority from:

- implementation capability
- data possession
- deployment responsibility
- integration ownership
- technical administration

Authority transfer requires legitimate governance authority.

## 11. Integration Governance

### Purpose

Represent governed integration relationships established by CV-WP-005.

### Responsibilities

- provider / consumer model
- integration class
- optional / mandatory state
- dependency direction
- lifecycle
- contract ownership
- authority ownership
- compatibility metadata
- trust-boundary metadata
- integration exception semantics

### Non-responsibilities

This component does not:

- route runtime traffic
- proxy requests
- broker messages
- deploy integrations
- issue runtime credentials
- become service discovery

It governs integration metadata.

It does not operate the integrations.

## 12. Deterministic Rule Evaluation

### Purpose

Evaluate explicitly governed deterministic rules.

### Responsibilities

- load applicable active rule definitions
- evaluate governed inputs
- produce reproducible results
- preserve rule revision
- expose PASS / FAIL / BLOCKED / WARNING / UNKNOWN or other governed semantics
- explain deterministic result basis
- identify blocking rules
- preserve distinction between rule evaluation and Human decision

### Dependency constraints

Rule Evaluation may read:

- canonical state
- relevant evidence
- explicit rule definitions
- active exception state

It may not:

- use AI output as a replacement for deterministic rule truth
- activate its own rules
- silently modify canonical state
- silently authorize an exception

## 13. Governance Case & Decision Coordination

### Purpose

Coordinate structured governance work from issue through authorized decision.

### Responsibilities

- create and manage governance cases
- resolve required Decision Owner
- associate evidence
- request deterministic evaluation
- request AI analysis where useful
- collect consultation
- maintain recommendation state
- prepare proposed governance effects
- collect explicit Human decision
- prepare authorized mutation request for Canonical Governance Core

### Authority posture

This component coordinates authority.

It does not manufacture authority.

A case becoming READY FOR DECISION must not automatically make the proposed effect effective.

## 14. Human decision path

The preferred logical path for a Human-governed mutation is:

Human Interaction
→ Governance Case & Decision Coordination
→ Identity & Access validation
→ Deterministic Rule Evaluation
→ explicit Human authorization
→ Canonical Governance Core
→ History & Audit
→ updated projections

The exact ordering may vary by use case.

The mandatory semantic properties are:

- authorization is explicit
- blocking rules cannot be silently bypassed
- canonical mutation crosses the Canonical Governance Core
- history remains reconstructable

## 15. Evidence & Provenance Boundary

### Purpose

Provide governed access to evidence while preserving source-domain authority.

### Responsibilities

- evidence references
- evidence retrieval
- provenance
- freshness
- stale-state representation
- unknown-state representation
- bounded retention
- integrity metadata
- evidence transformation metadata where applicable

### Authority posture

Evidence is not canonical Core Vision governance state merely because Core Vision stores or retrieves it.

This component must preserve whether information is:

- externally authoritative
- copied
- cached
- retained
- derived
- unknown
- stale

## 16. Evidence dependency posture

Other components may consume evidence through this boundary.

They should not depend directly on private external-system storage.

The Evidence Boundary may use the External Integration Boundary to obtain evidence.

Core Brain may be one evidence source.

It must not become a mandatory bootstrap dependency.

## 17. AI Analysis Boundary

### Purpose

Isolate AI-assisted reasoning from canonical governance authority.

### Responsibilities

- prepare bounded AI context
- invoke an available AI provider
- classify AI output
- record AI provenance where material
- return summaries
- return hypotheses
- return recommendations
- return rationale drafts
- report AI unavailable state

### Authority prohibition

AI Analysis must not:

- directly mutate canonical governance state
- create Human approval
- activate deterministic rules
- fabricate evidence
- convert UNKNOWN to a fabricated fact
- overrule a blocking invariant
- assign itself Decision Owner authority

## 18. AI provider independence

The component boundary should allow AI execution to be:

- disabled
- unavailable
- local
- remote
- replaced
- multi-provider in the future

without changing the semantic contracts of canonical Core Vision governance.

AI provider details remain technology decisions for later CV-WP-007 work.

## 19. History & Audit

### Purpose

Preserve material governance history and explainability.

### Responsibilities

- record material state transitions
- record Human decisions
- record authorized effects
- record rule-evaluation context where material
- record exception lifecycle
- preserve authority-assignment history
- support reconstruction of material decision chains
- preserve historical meaning after later changes

### Write posture

History recording is part of authoritative governance processing.

However, History & Audit must not independently reinterpret current canonical state.

Current canonical state remains the responsibility of the Canonical Governance Core.

## 20. Audit chain

Material effects should be traceable conceptually through:

effective state
→ authorized effect
→ authority basis
→ Human decision or explicitly authorized deterministic basis
→ governance case
→ applicable rule results
→ evidence
→ analysis / recommendation where material

Not every case requires every element.

Material governance meaning must remain reconstructable.

## 21. Projection & Reporting

### Purpose

Provide purpose-specific read models and Human-readable outputs.

### Responsibilities

- portfolio views
- lifecycle views
- authority maps
- capability maps
- integration maps
- governance backlog
- rule-result views
- decision history
- dashboards
- reports
- search-oriented projections

### Authority posture

A projection is not canonical authority.

A report is not canonical authority.

A search result is not canonical authority.

Projection loss should not normally destroy canonical governance state.

## 22. Application / Human Interaction Boundary

### Purpose

Provide the Human-facing application entry boundary.

### Responsibilities

- Human interaction
- command/request intake
- query intake
- governance-case interaction
- evidence inspection
- rule-result inspection
- AI-analysis inspection
- recommendation review
- Human authorization interaction
- administration interaction where permitted

### Prohibition

The Human Interaction Boundary must not:

- access canonical persistence directly as an undocumented client
- infer approval from UI activity
- turn administrator UI privilege into governance authority
- bypass application authorization
- directly rewrite historical state

## 23. Application command path

A state-changing Human request should conceptually flow through explicit application capabilities.

The UI must not know how canonical persistence is physically implemented.

This enables:

- technology replacement
- authorization consistency
- auditability
- testability
- future alternative clients

No API protocol is selected by this model.

## 24. External Integration Boundary

### Purpose

Isolate Core Vision from external systems and project-specific implementation details.

### Responsibilities

- governed external contracts
- authentication context
- authorization context where relevant
- external identifier mapping
- request/response adaptation
- event adaptation where later required
- failure isolation
- availability state
- compatibility handling

### Candidate integrations

- Core Brain
- Core-Dev
- CoreOps
- CDS
- products
- repositories
- future external evidence sources

### Prohibition

External integrations must not directly mutate Core Vision canonical persistence.

External input enters through governed application contracts.

## 25. Anti-corruption requirement

The External Integration Boundary must prevent external private schemas from becoming Core Vision's internal governance model by accident.

Core Vision concepts must remain defined by Core Vision governance semantics.

The final implementation pattern remains subject to Part 3 and later technology selection.

## 26. Identity & Access Boundary

### Purpose

Represent and validate identity and application authorization requirements.

### Responsibilities

- Human identity context
- system identity context
- AI identity context
- authenticated actor context
- application permissions
- Decision Owner eligibility support
- mutation authorization prerequisites
- administrative-access distinction

### Required distinction

The component model must distinguish:

identity
≠ authentication
≠ application permission
≠ governance authority
≠ Decision Owner
≠ Human approval

A valid authenticated identity does not automatically possess governance decision authority.

## 27. Administration & Health

### Purpose

Support operation of the Core Vision application itself.

### Responsibilities

- configuration visibility
- application health
- integration health
- storage health
- migration state
- backup readiness
- restore readiness
- AI availability
- rule-set health
- background-task health
- diagnostics

### Authority posture

Administration privilege does not automatically create governance authority.

This component must not become an unrestricted canonical mutation bypass.

## 28. Component dependency principles

The architecture establishes the following dependency principles.

### 28.1 Canonical state direction

Domain components depend on canonical governance contracts.

They do not own independent competing canonical copies.

### 28.2 Mutation direction

All effective canonical mutations terminate at the Canonical Governance Core.

### 28.3 AI direction

Governance components may request AI analysis.

Canonical governance semantics must not depend on AI implementation details.

### 28.4 Evidence direction

Governance components consume governed evidence through the Evidence & Provenance Boundary.

### 28.5 External-system direction

External system access crosses the External Integration Boundary.

### 28.6 Presentation direction

UI and reporting depend on application/query contracts.

Canonical governance components must not depend on UI implementation.

### 28.7 Infrastructure direction

Future infrastructure implementations support component contracts.

Component governance semantics must not depend on a specific database, transport or framework.

## 29. Allowed dependency model

The reference architecture permits conceptual dependencies such as:

Application / Human Interaction
→ Governance Case & Decision Coordination

Application / Human Interaction
→ Projection & Reporting

Governance Case & Decision Coordination
→ Identity & Access Boundary

Governance Case & Decision Coordination
→ Deterministic Rule Evaluation

Governance Case & Decision Coordination
→ Evidence & Provenance Boundary

Governance Case & Decision Coordination
→ AI Analysis Boundary

Governance Case & Decision Coordination
→ Canonical Governance Core

Canonical Governance Core
→ Portfolio & Lifecycle Governance

Canonical Governance Core
→ Authority & Capability Governance

Canonical Governance Core
→ Integration Governance

Canonical Governance Core
→ History & Audit

Deterministic Rule Evaluation
→ governed canonical read contracts

Deterministic Rule Evaluation
→ Evidence & Provenance Boundary

Evidence & Provenance Boundary
→ External Integration Boundary

AI Analysis Boundary
→ bounded governed read context

Projection & Reporting
→ canonical read contracts

Projection & Reporting
→ History & Audit read contracts

Administration & Health
→ operational health contracts

These arrows describe permitted conceptual dependencies.

They do not prescribe programming-language imports or network calls.

## 30. Forbidden dependency model

The following dependency patterns are forbidden by default:

AI Analysis Boundary
→ direct canonical mutation

Application / Human Interaction
→ direct persistence mutation

Projection & Reporting
→ canonical mutation

External Integration Boundary
→ direct canonical mutation

Administration & Health
→ undocumented canonical mutation bypass

External project
→ Core Vision private persistence

Core Vision domain component
→ external project private database

Canonical Governance Core
→ AI provider implementation

Canonical Governance Core
→ UI framework

Canonical Governance Core
→ Core Brain availability for bootstrap

Core Vision
→ CoreOps availability for governance bootstrap

These constraints protect standalone operation and authority boundaries.

## 31. Read versus write dependencies

Read and write capabilities must remain distinguishable.

A component allowed to read canonical state does not automatically receive mutation capability.

Examples:

Projection & Reporting may require broad read access.

It does not therefore receive canonical write authority.

AI Analysis may receive bounded read context.

It does not therefore receive canonical write authority.

External integrations may provide evidence.

They do not therefore receive canonical write authority.

## 32. Domain policy versus state authority

Portfolio, lifecycle, authority, capability and integration components may own domain policy semantics.

The Canonical Governance Core owns the application boundary that applies effective Core Vision governance state changes.

This distinction prevents a single technical module from becoming both:

- unquestioned policy source
- unquestioned authority source
- unrestricted persistence writer

Authority remains grounded in accepted governance and legitimate Decision Owners.

## 33. Component-local state

Components may later require component-local technical state.

Examples may include:

- AI request status
- external integration cursor
- transient job status
- cache state
- projection build state

Component-local technical state must not silently become canonical governance state.

The concrete persistence strategy is deferred.

## 34. Private persistence boundary

No component may treat another component's private persistence representation as a public contract.

If multiple logical components later share one physical database, that physical sharing must not erase logical ownership boundaries.

A shared physical store does not imply unrestricted cross-component writes.

## 35. Public internal contracts

Material interactions between components should use explicit internal contracts.

A contract should define at least:

- purpose
- caller
- provider
- accepted inputs
- output semantics
- authority implications
- failure semantics

Detailed module contracts are defined in CV-WP-007 Part 3.

## 36. Circular dependency rule

Logical component dependencies should remain acyclic where practical.

A required bootstrap cycle is prohibited.

Where two responsibilities need mutual interaction, architecture definition should prefer:

- coordination through a higher-level application component
- explicit contract inversion
- event or notification semantics where later justified
- read-only references

rather than hidden circular initialization dependencies.

No event technology is selected here.

## 37. Failure isolation

Component failure semantics must preserve governance meaning.

Examples:

If AI Analysis fails:

- deterministic rules remain usable
- Human review remains usable
- canonical state remains available

If Evidence retrieval fails:

- evidence may become unavailable or UNKNOWN
- canonical state remains available

If Projection fails:

- canonical state remains available

If an external integration fails:

- that source becomes unavailable or stale
- Core Vision does not silently invent replacement evidence

## 38. Core Brain absence

If Core Brain is unavailable:

- Knowledge and Evidence Plane enhancements may be reduced
- evidence retrieval through Core Brain may fail
- Core Vision canonical governance state remains usable
- Core Vision Human governance remains available where required evidence is otherwise sufficient
- unresolved required evidence remains UNKNOWN or BLOCKED according to governance

No bootstrap cycle is permitted.

## 39. Core-Dev absence

If Core-Dev is unavailable:

- current engineering readiness evidence may be unavailable
- existing Core Vision canonical state remains usable
- decisions requiring current engineering readiness may become UNKNOWN or BLOCKED

Core Vision must not invent engineering readiness.

## 40. CoreOps absence

If CoreOps is unavailable:

- current operational evidence may be unavailable
- existing Core Vision canonical governance state remains usable
- decisions requiring current operational evidence may become UNKNOWN or BLOCKED

Core Vision must not become the substitute operational Source of Truth.

## 41. CDS absence

If CDS is unavailable:

- adopted presentation assets may continue where locally available
- UI presentation may degrade according to later implementation rules
- canonical governance logic remains available

CDS must not become a governance bootstrap dependency.

## 42. AI absence

If AI is unavailable:

- AI summaries are unavailable
- AI recommendations are unavailable
- deterministic rules remain available
- Human decision workflows remain available
- canonical state remains available
- history remains available

AI is an enhancement boundary.

It is not the governing execution core.

## 43. Transactional consistency boundary

The architecture requires a clearly defined consistency boundary around material canonical mutations.

A material effect should not become partially effective across Core Vision canonical state.

For example, an authority reassignment should not leave the system in a state where:

- new authority appears active
- old authority remains simultaneously active contrary to governance
- history is missing
- decision linkage is missing

The implementation mechanism remains deferred.

## 44. Mutation atomicity requirement

Where one authorized governance effect changes multiple canonical facts that are semantically one decision, architecture implementation should preserve the effect as one consistent governance mutation boundary.

This is a requirement.

It is not a database-product decision.

## 45. History coupling requirement

Successful material canonical mutation should have sufficient history/audit linkage.

The architecture must avoid a state where canonical mutation succeeds permanently while required governance history silently fails and is discarded.

The exact consistency mechanism is defined later.

## 46. Query posture

Read queries should normally avoid requiring mutation-capable interfaces.

The architecture should support explicit read contracts suitable for:

- UI
- reporting
- deterministic rules
- bounded AI context
- integrations where authorized

Read models may differ from mutation models.

No CQRS architecture is selected by this statement.

## 47. Application coordination

Governance Case & Decision Coordination acts as the primary workflow-oriented coordinator for discretionary governance cases.

It may orchestrate:

- evidence acquisition
- rule evaluation
- AI analysis
- consultation
- Human authorization
- mutation request submission

It must not become an independent alternative canonical state store.

## 48. Non-case mutations

Not every future canonical mutation necessarily requires a Governance Case.

A narrowly bounded, already-authorized, non-discretionary deterministic effect may later use another explicit application path.

Such a path must still:

- have authority basis
- use deterministic validation
- cross the Canonical Governance Core
- produce required history

CV-WP-007 Part 2 does not authorize any specific automatic mutation.

## 49. Server-primary compatibility

The component model is compatible with the CV-WP-006 server-primary recommendation.

A server-primary implementation could host these logical components within one application deployment boundary.

This is architectural compatibility.

It is not yet the final runtime adoption decision.

## 50. Modular-monolith compatibility

The component model is intentionally compatible with a Modular Governance Monolith.

The model demonstrates that:

- meaningful domain boundaries can exist without network distribution
- authority boundaries can be explicit without independent services
- AI can be isolated logically
- external integrations can be isolated logically
- canonical mutation can remain centralized
- future extraction seams can remain visible

This supports the CV-WP-006 recommendation.

It does not yet formally adopt it.

## 51. Auxiliary-worker extraction seams

Potential future extraction seams include:

- AI Analysis Boundary
- long-running Evidence acquisition
- external integration polling
- heavy Projection generation
- report generation
- notifications

Extraction must preserve:

- canonical state authority
- public contracts
- failure semantics
- idempotency where applicable
- auditability
- graceful absence

A worker must not own an independent competing canonical governance store.

## 52. Components that should normally remain authority-central

The following responsibilities should not be casually extracted into independently authoritative services:

- canonical governance mutation
- Human authorization semantics
- effective authority assignment
- effective portfolio/lifecycle state
- effective exception state

Technical distribution may later be possible.

Authority duplication is not.

## 53. Deployment independence versus semantic independence

A component may be semantically independent without being separately deployed.

A separately deployed component is not automatically more architecturally correct.

Distribution must follow evidence.

The default reference topology remains one application deployment boundary.

## 54. Security boundaries

Logical component boundaries also inform least privilege.

Examples:

AI Analysis should not require canonical write privilege.

Projection & Reporting should not require canonical write privilege.

External integrations should not require unrestricted canonical write privilege.

Administration should not imply Governance Decision Owner authority.

Detailed identity and authorization contracts follow in Part 3 and Part 4.

## 55. Testability requirements

The component architecture should support independent testing of:

- domain policy
- deterministic rules
- canonical mutation authorization
- Human authorization workflow
- AI-disabled behavior
- external integration failure
- stale evidence behavior
- UNKNOWN behavior
- history linkage
- authority-boundary preservation

Technology selection should favor architectures that make these tests practical.

## 56. Architecture fitness rules

A later implementation architecture should fail review if:

- UI can bypass application mutation contracts
- AI can directly write canonical governance state
- external integrations can directly write canonical governance state
- projections become the only source of canonical meaning
- component private storage becomes a cross-component public contract
- canonical mutation can occur without authority basis
- Human authorization cannot be distinguished from technical authentication
- history cannot explain material state changes
- Core Brain becomes mandatory for Core Vision bootstrap
- CoreOps becomes mandatory for Core Vision governance bootstrap
- component extraction duplicates canonical authority

## 57. Component model summary

| Component | Primary responsibility | Canonical write authority |
|---|---|---|
| Canonical Governance Core | Effective Core Vision governance state | YES, through authorized mutation boundary |
| Portfolio & Lifecycle Governance | Portfolio and lifecycle policy | NO direct effect |
| Authority & Capability Governance | Authority/capability policy | NO direct effect |
| Integration Governance | Governed integration semantics | NO direct effect |
| Deterministic Rule Evaluation | Reproducible rule evaluation | NO direct effect by default |
| Governance Case & Decision Coordination | Decision preparation and orchestration | REQUEST ONLY |
| Evidence & Provenance Boundary | Evidence access/provenance | NO |
| AI Analysis Boundary | AI analysis/recommendation | NO |
| History & Audit | Historical governance record | NO independent canonical-current-state mutation |
| Projection & Reporting | Read models/reports | NO |
| Application / Human Interaction | Human interaction | NO direct persistence mutation |
| External Integration Boundary | External-system isolation | NO |
| Identity & Access Boundary | Identity/authorization support | NO governance effect by itself |
| Administration & Health | Application operation | NO governance bypass |

## 58. Reference dependency summary

The preferred logical flow is:

Human / external request
→ Application Boundary
→ Governance Case & Decision Coordination
→ required Identity / Evidence / Rules / AI analysis
→ explicit authority resolution
→ Canonical Governance Core
→ domain policy validation
→ effective canonical state
→ History & Audit
→ Projection & Reporting

The flow does not imply that every operation requires every component.

Read-only operations may use dedicated governed query paths.

## 59. Architecture recommendation evidence

The component model strengthens the CV-WP-006 Modular Governance Monolith recommendation because it shows that Core Vision can maintain:

- explicit module boundaries
- one canonical mutation boundary
- optional AI
- bounded external integrations
- explicit Human authorization
- deterministic rules
- auditability
- future extraction seams

without immediately requiring distributed services.

## 60. Architecture status after Part 2

After this component definition:

Modular Governance Monolith remains:

RECOMMENDED / NOT YET FORMALLY ADOPTED

Server-primary remains:

RECOMMENDED / NOT YET FORMALLY ADOPTED

The formal architecture decision remains deferred to later CV-WP-007 review.

## 61. Part 3 handoff

CV-WP-007 Part 3 must convert these component boundaries into explicit contracts.

Part 3 must define at least:

- canonical mutation contract
- Human authorization contract
- deterministic rule evaluation contract
- evidence contract
- AI analysis contract
- external integration contract
- query contract
- history/audit contract
- failure semantics
- allowed caller/provider relationships

The contracts must remain technology-neutral.

## 62. Conclusion

The Core Vision reference component model uses one authoritative canonical governance mutation boundary surrounded by explicit logical modules.

The architecture separates:

- domain policy
- canonical state
- deterministic validation
- Human authorization
- evidence
- AI analysis
- history
- projection
- external integration
- presentation
- administration

This structure is compatible with a Modular Governance Monolith while preserving future extraction seams.

It reduces the risk that technical access, AI capability, integration ownership, UI privilege or storage location silently becomes governance authority.

Knowledge can be centralized, authority not.
