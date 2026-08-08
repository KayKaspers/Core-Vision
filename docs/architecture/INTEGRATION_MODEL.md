# Core Integration Model

## 1. Purpose

This document defines the technology-independent integration model for interaction between Core projects.

It specifies:

- integration classes
- optional and mandatory integration
- public-contract expectations
- interface ownership
- compatibility expectations
- authority-preserving interaction rules

It does not select concrete transport protocols, API frameworks, message brokers, databases or implementation technologies.

## 2. Integration invariant

Integration enables interaction.

Integration does not transfer authority.

A system may:

- expose information
- receive information
- request work
- execute authorized work
- publish events
- retain evidence
- replicate selected data
- consume shared artifacts

without becoming authoritative for the source domain.

Knowledge can be centralized, authority not.

## 3. Standalone baseline

Standalone operation is the default architectural posture.

A Core project should remain useful without another Core project unless a mandatory dependency has been explicitly governed and justified.

First-party ecosystem membership is not sufficient justification for mandatory coupling.

An integration must therefore be classified as either:

- optional
- mandatory

before it is treated as an architectural dependency.

## 4. Optional integration

Optional integration enhances capability without being required for the provider or consumer to perform its fundamental standalone role.

An optional integration must define:

- provider unavailable behavior
- consumer unavailable behavior where relevant
- timeout or interruption expectations at a conceptual level
- recovery expectations
- stale-data behavior where relevant
- whether local operation continues
- whether functionality is reduced
- whether cached or previously obtained information may be used
- which authority remains authoritative during absence

Optional absence must not silently become a fatal bootstrap dependency.

## 5. Mandatory integration

A mandatory integration means one project cannot fulfill an explicitly authorized responsibility without another project.

Mandatory Core-to-Core integration is exceptional.

It requires explicit architectural justification.

The justification must identify:

- why standalone operation is insufficient
- why optional integration is insufficient
- provider
- consumer
- contract owner
- authority owner
- dependency direction
- startup implications
- failure implications
- security implications
- graceful-degradation limits
- bootstrap-cycle analysis
- replacement or migration implications

A mandatory integration must not be created merely for convenience, implementation reuse or first-party preference.

## 6. Integration classes

The Core ecosystem recognizes the following technology-independent integration classes.

### 6.1 Query Integration

A consumer requests information from a provider.

Examples:

- current status
- metadata
- inventory information
- readiness information
- policy information
- knowledge retrieval

The provider owns the public interface contract it exposes.

The source-domain authority remains with the authoritative domain owner.

Query access does not grant mutation authority.

### 6.2 Command Integration

A consumer requests that a provider perform an action within the provider's authorized domain.

Examples:

- deployment request
- controlled automation request
- evidence collection request
- validation request

A command request does not give the caller direct authority over the provider's internal implementation.

The provider remains responsible for:

- authorization
- validation
- policy enforcement
- safe execution
- result reporting

A request is not equivalent to successful execution.

### 6.3 Event Integration

A provider publishes that something relevant occurred or changed.

Examples:

- state-change notification
- deployment result
- readiness change
- lifecycle-relevant observation
- evidence availability notification

Events communicate observations or domain-owned state changes.

An event does not automatically instruct a consumer to change its own authoritative state.

Consumers remain responsible for interpreting events within their own authority domain.

### 6.4 Artifact Integration

A provider publishes a governed artifact intended for consumption by another project.

Examples:

- design-system artifact
- schema
- policy artifact
- signed evidence package
- generated report
- compatibility definition

Artifact consumption does not transfer the producing project's broader authority.

Consumers must treat the artifact according to its defined contract and scope.

### 6.5 Evidence Integration

Evidence Integration transfers or exposes evidence while preserving source provenance and decision ownership.

Evidence may include:

- operational evidence
- engineering evidence
- governance evidence
- knowledge evidence
- test evidence
- security evidence

The receiving system may:

- retain
- index
- relate
- search
- summarize
- evaluate

the evidence within its authorized role.

Receiving evidence does not make the receiver authoritative for the source domain.

### 6.6 Reference Integration

A project references another project's stable public identifier, artifact, contract or externally meaningful state without requiring private implementation access.

Reference Integration is preferred over duplication where a stable governed reference exists.

References must not create hidden runtime dependencies unless explicitly classified as such.

### 6.7 Replication Integration

Selected information is copied from one project to another for an explicitly governed purpose.

Replication may support:

- availability
- search
- analytics
- evidence preservation
- local processing
- offline operation

Replication does not create co-ownership of source authority.

A replicated copy must not silently outrank the authoritative source.

Conflict behavior must be defined before replicated information can influence binding decisions.

### 6.8 Shared Foundation Consumption

A project consumes a governed foundation owned by another Core project.

Examples may include:

- NDF development-governance artifacts
- CDS design-system artifacts
- future explicitly admitted foundation capabilities

Consumption is bounded to the foundation's authorized scope.

Using a foundation does not give the foundation authority over unrelated consumer domains.

## 7. Public Interface First

Cross-project interaction must use an intentionally governed public contract wherever practical.

Projects must not rely on another project's private implementation details merely because both are Core projects.

Prohibited implicit contracts include direct dependence on:

- private database tables
- undocumented internal files
- private object layouts
- internal cache structure
- undocumented directory structure
- private implementation classes
- incidental command output
- internal service topology

If another project must depend on information or behavior, that dependency should be represented through a deliberate contract.

## 8. Public contract

A public integration contract defines the stable boundary between provider and consumer.

At minimum, a material contract should identify:

- provider
- intended consumers
- integration class
- purpose
- input or request semantics where applicable
- output or response semantics where applicable
- authoritative meaning
- authentication expectation
- authorization expectation
- failure semantics
- compatibility policy
- lifecycle or deprecation expectations
- whether the integration is optional or mandatory

The contract may later be implemented through different technologies without changing its architectural meaning.

## 9. Contract ownership

The provider normally owns the public interface contract it exposes.

Contract ownership includes responsibility for:

- defining supported behavior
- documenting semantics
- compatibility governance
- deprecation governance
- identifying authoritative fields or meanings where relevant

Contract ownership does not imply ownership of every domain represented in the payload.

For example:

Core Brain may own a knowledge-retrieval interface.

That does not make Core Brain authoritative for operational facts originating from CoreOps.

## 10. Interface ownership versus domain authority

Interface ownership and domain authority are separate.

An interface owner controls the contract boundary.

A domain authority controls the binding meaning or authoritative state of its domain.

These roles may belong to different projects.

Any integration specification that makes this distinction unclear must fail closed pending governance review.

## 11. Consumer responsibilities

A consumer must:

- use the public contract as defined
- authenticate where required
- request only authorized operations
- respect provider failure semantics
- respect compatibility requirements
- preserve source provenance where required
- avoid promoting non-authoritative data into authoritative state without an authorized rule

A consumer must not assume that first-party integration grants unrestricted access.

## 12. Provider responsibilities

A provider must:

- expose only intentionally governed public behavior
- validate requests
- authenticate callers where appropriate
- authorize operations
- preserve its own authority boundary
- provide meaningful failure behavior
- distinguish accepted requests from completed outcomes
- avoid exposing private implementation as an accidental contract

## 13. Authentication and authorization

No Implicit First-Party Trust applies to all Core integrations.

A component being part of the Core ecosystem does not automatically grant:

- identity
- trust
- read access
- write access
- command authority
- administrative authority

Authentication answers:

> Who is the caller?

Authorization answers:

> What may that caller do?

Both concerns remain required where the integration risk requires them.

## 14. Read versus mutation

Read access and mutation authority must remain separate.

A system authorized to retrieve:

- data
- evidence
- status
- metadata

does not automatically gain permission to modify the source.

Mutation requires an explicit authorized contract.

Direct mutation of another project's private storage is prohibited.

## 15. Command authority

Command Integration requires particular care.

The caller may be authorized to request an operation.

The provider remains responsible for deciding whether that request is valid under its own governing rules.

For example:

Core-Dev may determine that software is ready for deployment.

CoreOps may accept an authorized deployment request.

CoreOps remains responsible for runtime deployment execution and operational controls.

Core-Dev does not gain direct runtime authority merely because it initiates the request.

## 16. Event authority

An event is not automatically a command.

An event may describe:

- something observed
- something completed
- something changed
- evidence becoming available

The consumer must not interpret an informational event as authorization for an irreversible action unless an explicit contract says otherwise.

## 17. Data authority

Possession of data does not imply authority over the represented domain.

The authoritative owner must remain identifiable for data that influences binding decisions.

Derived data should distinguish where practical between:

- source fact
- copied fact
- transformed fact
- inferred value
- recommendation
- decision

Integration must not collapse these categories into an indistinguishable truth state.

## 18. Evidence authority

Evidence retains its provenance when crossing project boundaries.

The receiving project may become authoritative for:

- how it stores the evidence
- how it indexes the evidence
- how it relates the evidence
- how it presents the evidence within its own contract

It does not thereby become authoritative for the source-domain fact represented by the evidence.

## 19. Compatibility

Material public contracts require an explicit compatibility posture.

Compatibility governance should define, as appropriate:

- compatible change
- incompatible change
- version identification
- deprecation
- transition period
- consumer migration expectations

A provider must not silently change the meaning of an existing public contract in a way that can cause consumers to misinterpret authoritative state.

## 20. Version independence

The ecosystem does not require every Core project to share one global software version.

Each project may evolve independently within its own governance.

Integration compatibility must therefore be based on governed contracts rather than assumptions that all Core projects are updated simultaneously.

## 21. Contract evolution

Contract changes should be classified as:

- compatible
- conditionally compatible
- breaking

Breaking changes require explicit migration handling.

If a breaking change affects multiple authority domains or creates a new mandatory dependency, it becomes a Core Vision cross-project governance concern.

## 22. Deprecation

Public contracts must not disappear silently when active consumers are known.

Deprecation should identify:

- deprecated contract
- replacement where applicable
- affected consumers
- migration expectation
- end-of-support condition
- authority impact where relevant

Deprecation does not authorize consumers to access private implementation as a workaround.

## 23. Private implementation boundary

Private implementation remains private even between first-party projects.

A Core project must not depend on another project's private internals unless that dependency is explicitly converted into a governed public contract.

This applies regardless of:

- common ownership
- shared maintainers
- repository visibility
- deployment environment
- organizational trust

## 24. Core Brain integration boundary

Core Brain may participate through:

- Query Integration
- Evidence Integration
- Event Integration
- Reference Integration
- governed Artifact Integration

Core Brain may centralize knowledge and evidence access.

It does not become authoritative for the underlying source domains.

## 25. CDS integration boundary

CDS may primarily provide governed Artifact Integration and referenceable public design-system contracts.

Consumers may adopt accepted CDS artifacts.

CDS integration does not transfer:

- product behavior authority
- product-domain semantic authority
- runtime authority
- development governance

## 26. Core-Dev integration boundary

Core-Dev may participate through:

- Query Integration
- Command Integration
- Event Integration
- Evidence Integration
- Artifact Integration

Core-Dev may provide engineering and readiness evidence.

Core-Dev determines whether software is ready to be deployed within its authorized scope.

It does not thereby perform or own runtime deployment authority.

## 27. CoreOps integration boundary

CoreOps may participate through:

- Query Integration
- Command Integration
- Event Integration
- Evidence Integration
- Artifact Integration

CoreOps remains authoritative for current operational state and runtime deployment execution within its authorized scope.

Operational integration does not make CoreOps authoritative for:

- development methodology
- engineering readiness
- product-domain semantics
- ecosystem strategy

## 28. Product integration boundary

Products retain authority for:

- product-specific behavior
- business rules
- product-domain semantics
- product-domain data authority where defined

Products may consume shared Core contracts without surrendering those authorities.

Shared services may support product operation.

They do not silently become product owners.

## 29. Core Vision integration boundary

Core Vision governs ecosystem integration architecture.

Core Vision must not become the mandatory runtime router, message hub, data bus or orchestration dependency for all Core projects.

Future Core Vision software may consume governed information for analysis and governance.

That does not require runtime traffic between projects to pass through Core Vision.

## 30. Technology neutrality

This model intentionally does not prescribe:

- REST
- GraphQL
- gRPC
- WebSocket
- MQTT
- AMQP
- Kafka
- NATS
- database replication technology
- file exchange technology
- specific identity provider
- specific service mesh

Technology selection belongs to later architecture work at the appropriate authority level.

Any selected technology must conform to the governance rules in this model.

## 31. Human authority

The Human Maintainer retains final authority for ecosystem-level exceptions that create:

- new mandatory Core-wide coupling
- irreversible authority transfer
- ecosystem-wide trust assumptions
- exceptions to bootstrap-cycle protections
- irreversible public-contract commitments

AI systems may design, compare and review integration contracts.

They do not independently authorize irreversible ecosystem coupling.
