# Core Data and Evidence Flow

## 1. Purpose

This document defines how data, evidence, state and derived information may cross Core project boundaries while preserving provenance, authority, trust boundaries and safe behavior during failure or provider absence.

It complements the Core Integration Model.

It does not define concrete transport protocols, databases, brokers, cache technologies or identity products.

## 2. Core invariant

Availability is not authority.

Possession is not authority.

Replication is not authority.

Caching is not authority.

Transformation is not authority.

Inference is not authority.

Integration may move information between projects.

It must not silently move the authority that gives that information binding meaning.

Knowledge can be centralized, authority not.

## 3. Information classes

Cross-project information should be distinguishable by meaning.

Relevant classes include:

### 3.1 Source Fact

A Source Fact is information asserted by the project or domain that is authoritative for that fact.

The authoritative source must remain identifiable.

### 3.2 Replicated Fact

A Replicated Fact is a copy of information obtained from an authoritative source.

Replication does not make the receiver co-authoritative.

### 3.3 Cached Fact

A Cached Fact is a temporarily retained copy intended to improve availability, performance or offline behavior.

A cache must not silently present stale information as current authoritative state.

### 3.4 Derived Fact

A Derived Fact is calculated or transformed from one or more source inputs.

Its derivation and source basis should remain identifiable where material.

### 3.5 Inference

An Inference is an interpreted or probabilistic conclusion.

An inference must not be represented as an observed source fact.

### 3.6 Recommendation

A Recommendation proposes an action or decision.

It is not an authorized decision.

### 3.7 Decision

A Decision is an authorized governance, engineering, operational or product-domain determination made by the legitimate Decision Owner.

A decision remains distinct from the evidence that informed it.

## 4. Source-of-Truth semantics

A Source of Truth is authoritative only within its governed domain.

The term must not be interpreted as global authority over every representation of related information.

Examples:

- CoreOps may be authoritative for current operational state.
- Core-Dev may be authoritative for engineering readiness within its scope.
- a product may be authoritative for product-domain semantics.
- Core Brain may be authoritative for its own knowledge records, evidence relationships and retrieval behavior.

Core Brain storing operational evidence does not replace CoreOps as operational authority.

CoreOps storing deployment metadata does not make CoreOps authoritative for product semantics.

## 5. Authority metadata

Information that may affect binding decisions should preserve enough context to determine, where applicable:

- source project
- source domain
- authoritative owner
- observation or production time
- retrieval or receipt time
- version or revision
- evidence provenance
- transformation status
- freshness status
- confidence or uncertainty where relevant
- whether the information is authoritative, replicated, cached, derived or inferred

Not every payload requires every field.

The contract must preserve enough information to prevent authority ambiguity.

## 6. Provenance

Provenance describes where information came from and how it reached its current representation.

Material evidence provenance should not be discarded when information crosses project boundaries.

Provenance may include:

- originating project
- originating component
- source identifier
- collection method
- original timestamp
- transformation steps
- replication path
- validation result
- evidence revision

A receiver may add provenance about its own processing.

It must not overwrite source provenance in a way that obscures origin.

## 7. Data flow direction

Every governed cross-project data flow should have an explicit direction.

A flow should identify:

- producer
- consumer
- information class
- authoritative domain
- integration class
- optional or mandatory status
- allowed purpose

Bidirectional exchange does not imply shared authority.

Two-way synchronization requires separate authority rules for each direction.

## 8. Read flow

A read flow exposes information without granting mutation rights.

A consumer may retrieve information for an authorized purpose.

Read access must not automatically grant:

- write access
- command authority
- administrative authority
- ownership
- authority over the represented domain

## 9. Command result flow

A command request and its result are separate facts.

A request may be:

- received
- rejected
- authorized
- accepted
- executing
- completed
- failed

The caller must not treat request submission as proof of successful completion.

Binding state should follow the authoritative provider's result contract.

## 10. Event flow

Events communicate observations or domain-owned state changes.

An event should identify enough semantic context for consumers to determine what it means.

Event delivery alone must not silently authorize an irreversible action.

Consumers remain responsible for applying their own authorized policy before changing local authoritative state.

## 11. Evidence flow

Evidence may cross project boundaries for:

- review
- audit
- governance
- search
- knowledge retrieval
- engineering analysis
- operational analysis
- security analysis

The receiver may become authoritative for its evidence-record handling.

It does not become authoritative for the source-domain fact merely by receiving the evidence.

## 12. Replication

Replication may be used for:

- offline capability
- resilience
- search
- analytics
- historical preservation
- bounded local processing

A replicated copy must retain an identifiable relationship to its source.

Replication must define:

- source
- destination
- replication direction
- freshness expectations
- conflict behavior
- authority behavior during source absence
- resynchronization behavior at a conceptual level

Replication does not create co-ownership of source authority.

## 13. Cache semantics

A cache is an availability or performance mechanism.

A cache must have an explicit freshness model where stale information can materially affect behavior.

Relevant states may include:

- current
- stale but usable
- stale and non-authoritative
- expired
- unknown

A consumer must not silently treat expired or unknown data as current authoritative state.

## 14. Freshness

Freshness is domain-dependent.

A single ecosystem-wide freshness duration is not required.

The public contract should define freshness expectations where they matter.

Freshness assessment may consider:

- source timestamp
- retrieval timestamp
- domain volatility
- maximum acceptable age
- provider availability
- decision criticality

A value being recently received does not prove that the underlying source fact is current unless the source contract supports that meaning.

## 15. Staleness

Staleness must be visible when it can affect a material decision.

When stale information remains usable, the consumer should know:

- that it is stale
- when it was last known current
- whether it may support read-only behavior
- whether it may support binding decisions
- whether confirmation from the source is required

Stale operational evidence must not silently become current operational state.

## 16. Unknown state

Unknown is a legitimate state.

Systems must not convert unknown into:

- healthy
- unhealthy
- approved
- denied
- current
- complete

unless an explicit domain rule defines that conversion.

Where authority-critical information is unknown, the binding action should normally fail closed.

## 17. Provider unavailable

An integration must define behavior when the provider is unavailable.

Possible governed behaviors include:

- continue standalone
- continue with reduced capability
- use a bounded stale cache
- operate read-only
- queue a non-destructive request
- defer an action
- fail closed
- surface unknown state

Provider absence must not automatically cause authority to move to the consumer.

## 18. Consumer unavailable

A provider should not assume that every consumer is always available.

Where possible, provider operation should remain independent from optional consumers.

An optional consumer outage must not become a provider outage merely because integration exists.

## 19. Graceful degradation

Graceful degradation means preserving safe useful behavior when an optional dependency becomes unavailable.

Degradation must be explicit.

It must not silently:

- weaken authentication
- weaken authorization
- bypass policy
- grant broader access
- promote cached information to current truth
- transfer authority
- convert unknown into success
- create a hidden mandatory dependency

Reduced functionality is preferable to unsafe authority substitution.

## 20. Offline behavior

Offline capability may use previously obtained information.

Offline operation must distinguish between:

- information available locally
- information known to be current
- information authoritative for a binding decision

These are not equivalent.

Offline operation may continue where the domain contract permits it.

An authority-critical action requiring current external confirmation must fail closed when that confirmation is unavailable.

## 21. Conflict detection

A conflict exists when two relevant representations cannot simultaneously be treated as the same authoritative fact.

Conflicts may arise from:

- stale replicas
- concurrent changes
- delayed events
- divergent caches
- manual overrides
- different source revisions
- transformation errors

Conflict detection should preserve the competing values and provenance where material.

A system must not silently choose a winner when authority is ambiguous.

## 22. Conflict resolution

Conflict resolution must follow authority ownership.

Where one source is explicitly authoritative, a replica or cache must not override it merely because it is newer locally.

Where authority is genuinely ambiguous, the binding action must fail closed pending resolution.

Resolution may require:

- source refresh
- contract-specific precedence
- Human Maintainer decision
- domain-owner decision
- cross-project governance review

Timestamp recency alone does not establish authority.

## 23. Resynchronization

After an outage or offline period, resynchronization must not assume that local and remote state can be merged without authority rules.

Resynchronization should conceptually consider:

- source authority
- local changes
- source changes
- conflicting revisions
- stale evidence
- rejected operations
- operations that never completed

Resynchronization must not convert unconfirmed local intent into confirmed remote state.

## 24. Retry behavior

Retry may improve resilience.

Retry must not create duplicate irreversible actions.

Where repeated commands can produce material side effects, the integration contract must define duplicate-handling or equivalent safety semantics.

The technology-specific mechanism is deferred.

The architectural requirement is that retries must not silently change the meaning of an operation.

## 25. Partial failure

Distributed integration may produce partial failure.

Examples include:

- request delivered but result unavailable
- action completed but event delivery failed
- evidence stored but index update failed
- source updated but replica synchronization failed

Partial failure must not be represented as complete success unless the authoritative contract supports that conclusion.

Unknown completion status must remain unknown until resolved.

## 26. Trust boundary

Every project boundary remains a trust boundary unless explicitly governed otherwise.

First-party status does not eliminate the need to evaluate:

- identity
- authentication
- authorization
- input validation
- output validation
- least privilege
- replay or duplicate risk
- integrity
- confidentiality where applicable
- provenance

Trust must be deliberate.

## 27. Authentication

Authentication establishes the identity of a caller or peer where required.

Identity must not be inferred solely from:

- network location
- repository ownership
- Core branding
- shared deployment environment
- first-party status

The concrete identity technology is deferred.

## 28. Authorization

Authorization determines which actions an authenticated identity may perform.

Authorization should follow least privilege.

Read, write, command, administration and governance privileges must remain distinguishable.

Authentication does not imply authorization.

## 29. Integrity

Information used for binding decisions must have integrity appropriate to its risk.

A receiving system should be able to determine whether information is:

- accepted under the contract
- malformed
- unsupported
- unverifiable
- rejected

Invalid information must not silently enter authoritative state.

## 30. Confidentiality

Cross-project integration must respect the sensitivity of the information being exchanged.

Core ecosystem membership does not imply unrestricted information sharing.

The integration contract should expose only information required for the authorized purpose.

## 31. Least information

Consumers should receive the information needed for the governed integration purpose.

They should not automatically receive private implementation data simply because such data is available.

This reduces:

- coupling
- security exposure
- privacy exposure
- accidental authority ambiguity

## 32. Core Brain boundary

Core Brain may retain, relate, retrieve and summarize evidence from other projects.

Core Brain must preserve source-domain provenance and authority.

Core Brain may be authoritative for its own:

- evidence records
- knowledge relationships
- indexing
- retrieval behavior

It is not thereby authoritative for the external source-domain fact.

## 33. Core-Dev boundary

Core-Dev may provide engineering evidence such as:

- test state
- build state
- engineering health
- release readiness

Core-Dev remains authoritative for engineering readiness within its authorized scope.

Operational state remains with CoreOps.

A cached Core-Dev readiness result must not silently become proof that current runtime deployment succeeded.

## 34. CoreOps boundary

CoreOps remains authoritative for current operational state within its authorized scope.

CoreOps may expose:

- runtime state
- deployment state
- operational evidence
- infrastructure evidence
- operational provenance

Copies of this information elsewhere do not replace CoreOps as current operational authority.

If CoreOps is unavailable, consumers may expose the last known state as stale where permitted.

They must not silently label it current.

## 35. CDS boundary

CDS may provide governed design-system artifacts and metadata.

A cached or replicated CDS artifact does not transfer product-domain authority to CDS or to the consumer.

Artifact version and compatibility should remain identifiable where material.

## 36. Product boundary

Products retain product-specific behavior, business rules and domain semantics.

Shared Core systems may retain copies or evidence related to product data where explicitly authorized.

Those copies do not silently become the product-domain Source of Truth.

## 37. Core Vision boundary

Core Vision may consume governed information for:

- portfolio analysis
- architecture review
- governance evidence
- lifecycle assessment
- strategic analysis

Core Vision must not become a runtime Source of Truth merely because it aggregates ecosystem information.

Core Vision software must be able to distinguish evidence, observation, recommendation and authorized decision.

## 38. Fail-closed conditions

A binding cross-project action should fail closed when material uncertainty exists about:

- identity
- authorization
- authoritative source
- provenance
- currentness where currentness is required
- conflict resolution
- completion state
- authority ownership
- mandatory dependency availability where no safe degraded mode exists

Fail-closed means the binding action is withheld.

It does not mean all read-only or unrelated local functionality must stop.

## 39. Observability

Material integrations should expose enough state to determine whether the integration is:

- available
- degraded
- unavailable
- stale
- conflicting
- unauthorized
- incompatible
- recovering

Observability must not be confused with authority.

A monitoring system observing a condition does not automatically become authoritative for the observed domain.

## 40. Technology neutrality

This document intentionally does not choose:

- cache products
- database systems
- replication engines
- message brokers
- identity providers
- cryptographic implementations
- retry libraries
- synchronization frameworks

Technology selection belongs to later implementation and architecture decisions.

The selected implementation must preserve the semantics defined here.

## 41. Human authority

The Human Maintainer retains final authority for ecosystem-level exceptions involving:

- irreversible authority transfer
- unsafe degradation exceptions
- new mandatory trust assumptions
- authority-critical conflict policies spanning multiple projects
- mandatory integration exceptions with ecosystem-wide consequences

AI systems may:

- detect stale information
- compare provenance
- detect conflicts
- identify authority ambiguity
- recommend resolution

AI systems do not independently redefine authoritative ownership.
