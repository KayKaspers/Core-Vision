# Core Integration Governance

## 1. Purpose

This document defines how Core integrations and cross-project dependencies are introduced, changed, deprecated and removed.

It connects:

- the Core Integration Model
- the Core Data and Evidence Flow model
- the Core Cross-Project Governance model

Integration governance must preserve project autonomy, explicit contracts, trust boundaries, graceful degradation and established authority ownership.

## 2. Core rule

An integration is not justified merely because it is technically possible.

A cross-project dependency must have:

- an explicit purpose
- an explicit provider
- an explicit consumer
- a defined integration class
- a defined contract owner
- a defined authority owner
- a defined optional or mandatory classification
- a defined failure posture
- a defined lifecycle

Integration does not imply authority transfer.

Knowledge can be centralized, authority not.

## 3. Dependency direction

Every cross-project dependency must have a defined direction.

The direction identifies:

- provider
- consumer
- contract owner
- dependency owner
- authoritative domain

Dependency direction and information-flow direction are not always identical.

For example:

A consumer may depend on a provider's public contract while information flows in both directions.

Bidirectional information flow does not automatically create bidirectional authority.

## 4. Optional dependency

Optional integration is the preferred default where useful standalone operation remains possible.

An optional dependency must define safe behavior when the provider is:

- unavailable
- degraded
- incompatible
- unauthorized
- stale
- returning unknown state

Optional integration must not become de facto mandatory through undocumented assumptions.

## 5. Mandatory dependency

Mandatory Core-to-Core dependencies are exceptional.

A proposed mandatory dependency requires explicit review of:

- architectural necessity
- standalone impact
- failure impact
- security impact
- trust assumptions
- bootstrap implications
- provider availability assumptions
- replacement options
- migration cost
- authority implications

Convenience alone is insufficient justification.

## 6. Mandatory dependency authorization

A mandatory dependency may be authorized only when:

- the responsibility cannot reasonably be fulfilled standalone
- optional integration is insufficient
- dependency direction is explicit
- public contract ownership is explicit
- authority ownership remains explicit
- failure semantics are defined
- bootstrap cycles are absent
- trust assumptions are governed
- migration or replacement implications are understood

A mandatory ecosystem-level dependency with material irreversible consequences requires Human Maintainer authorization.

## 7. No bootstrap cycles

Mandatory circular startup dependencies are prohibited.

Examples of prohibited architecture include:

- Project A cannot start without Project B
- Project B cannot start without Project A

or longer cycles such as:

- A requires B
- B requires C
- C requires A

A project may consume another project after startup without creating a bootstrap cycle if safe standalone startup and degradation remain possible.

Bootstrap-cycle exceptions require explicit Human Maintainer authorization and must be treated as exceptional architecture.

## 8. No hidden dependencies

A dependency must not hide inside:

- private database access
- undocumented files
- internal directories
- shared writable storage
- incidental command output
- undocumented environment assumptions
- internal object models
- implementation-specific network topology

Material cross-project dependencies must be visible as governed contracts.

## 9. First-party neutrality

Core projects must be treated as independently governed systems at integration boundaries.

First-party status does not grant:

- implicit trust
- unrestricted read access
- unrestricted mutation
- command authority
- administrative privileges
- private implementation access

Authentication and authorization requirements are determined by risk and contract semantics, not by Core branding.

## 10. Contract registration

A material cross-project integration should be registered at the appropriate authority level.

A registration should identify at least:

- integration name
- provider
- consumer
- integration class
- purpose
- contract owner
- authoritative domain
- optional or mandatory status
- compatibility posture
- failure posture
- lifecycle status

Registration documents the dependency.

Registration does not change authority ownership.

## 11. Contract lifecycle

A governed integration contract may progress through states such as:

- Proposed
- Experimental
- Active
- Deprecated
- Retiring
- Retired

These integration-contract states are separate from project lifecycle state.

A project may remain Active while one of its contracts is Deprecated or Retired.

## 12. Proposed

Proposed means the integration is under design or review.

It must not be treated as a stable dependency.

Consumers must not build irreversible ecosystem assumptions on a merely Proposed contract.

## 13. Experimental

Experimental means bounded implementation or evaluation is permitted.

Experimental contracts:

- may change
- may be incomplete
- may not be suitable for mandatory dependency
- require explicit consumer awareness

Experimental status does not establish permanent compatibility commitments.

## 14. Active

Active means the contract is accepted for governed consumption within its documented scope.

Active does not mean:

- globally mandatory
- universally supported
- authority-transferring
- permanently immutable

The contract remains governed by its compatibility and lifecycle policy.

## 15. Deprecated

Deprecated means new consumption should normally stop unless explicitly justified.

Deprecation must identify:

- affected consumers
- replacement where applicable
- migration expectation
- compatibility window
- intended retirement condition

Deprecation must not silently force consumers onto private implementation details.

## 16. Retiring

Retiring means active migration or controlled dependency removal is underway.

The provider and affected consumers should identify:

- remaining consumers
- migration blockers
- authority implications
- evidence preservation requirements
- target retirement condition

## 17. Retired

Retired means the contract is no longer supported as an active integration boundary.

Historical documentation and relevant evidence should remain preserved.

A retired contract must not silently regain Active status without a new governed decision.

## 18. Integration introduction

A new integration should be evaluated for:

- purpose
- integration class
- authority impact
- dependency direction
- optional or mandatory status
- public contract
- security and trust
- failure handling
- data/evidence semantics
- compatibility
- lifecycle

The smallest sufficient integration should be preferred.

## 19. Integration expansion

An existing integration requires renewed review when its scope expands materially.

Examples include:

- read-only becomes mutation-capable
- optional becomes mandatory
- evidence flow becomes command flow
- one consumer becomes ecosystem-wide consumption
- public metadata expands into sensitive data
- informational events begin triggering irreversible actions
- one-way dependency becomes bidirectional dependency

A larger implementation is not automatically the same governance scope.

## 20. Integration reduction

Removing integration capability should preserve:

- consumer migration
- authority clarity
- historical evidence
- contract deprecation semantics
- safe degraded behavior where needed

Removing an integration must not create hidden fallbacks to private implementation access.

## 21. Optional to mandatory transition

Changing an integration from optional to mandatory is a material architecture change.

It requires review of:

- standalone loss
- provider criticality
- failure domain expansion
- bootstrap impact
- security assumptions
- migration consequences
- authority implications

This transition must not occur implicitly because all current deployments happen to use the integration.

## 22. Mandatory to optional transition

Changing a dependency from mandatory to optional is normally architecturally favorable when safe standalone behavior can be restored.

The transition must still define:

- degraded behavior
- data freshness
- authority during provider absence
- compatibility with existing consumers

## 23. Integration removal

Before removing a governed integration, determine:

- whether active consumers remain
- whether replacement exists
- whether historical evidence must remain
- whether authority moves
- whether operational dependencies remain
- whether project lifecycle is affected

Removing a transport path does not itself transfer authority.

## 24. Compatibility governance

Material public contracts must define compatibility expectations.

Changes should be classified as:

- compatible
- conditionally compatible
- breaking

A breaking change requires explicit migration handling.

Breaking changes that materially affect multiple projects should be treated as cross-project governance matters.

## 25. Versioning independence

Core projects evolve independently.

A consumer must not assume compatibility merely because provider and consumer are both on their respective latest versions.

Compatibility must derive from the public contract.

The ecosystem must not require synchronized global upgrades unless explicitly governed.

## 26. Deprecation governance

Deprecation is a lifecycle action, not an undocumented implementation choice.

A provider should not silently remove a known active public contract.

Where consumers cannot migrate immediately, the governance case should identify:

- risk
- temporary compatibility need
- migration owner
- retirement target

## 27. Trust changes

A change that weakens or broadens an integration trust boundary is material.

Examples include:

- anonymous access added
- broader credentials accepted
- write privileges added
- administrative actions exposed
- validation reduced
- authorization moved from provider to caller

Material trust changes require explicit security and authority review.

## 28. Data-flow changes

A data-flow change becomes material when it changes:

- authoritative meaning
- sensitivity
- provenance
- freshness expectation
- replication behavior
- mutation capability
- conflict resolution
- decision impact

Adding more fields is not necessarily minor if those fields affect authority or trust.

## 29. Evidence-flow changes

Evidence Integration must preserve provenance and source authority.

A change that causes evidence to become the direct basis for automated binding action requires review of:

- source authority
- freshness
- validation
- conflict handling
- authorization
- Decision Owner

Evidence availability alone must not authorize irreversible action.

## 30. Command-flow changes

Command Integration requires explicit authorization semantics.

A change that adds a new command capability must identify:

- caller
- provider
- requested action
- authorization boundary
- provider-side validation
- completion semantics
- retry safety
- irreversible side effects

Caller intent and provider-confirmed completion remain separate.

## 31. Event-flow changes

An informational event becoming action-triggering is a material semantic change.

Consumers must not silently reinterpret an event from:

- observation

into:

- authorization

without an explicitly governed contract change.

## 32. Integration Change Class A — Local

Use Class A when a change:

- stays inside one project's private implementation
- does not change a public contract
- does not affect another project's authority
- does not create new cross-project dependency

Handling:

Project-local governance.

## 33. Integration Change Class B — Consultative

Use Class B when:

- one project remains contract owner
- compatibility affects known consumers
- authority does not change
- mandatory dependency status does not change

Handling:

- provider retains Decision Owner role
- consumers are consulted
- compatibility and migration impact are documented

## 34. Integration Change Class C — Cross-Project Architecture

Use Class C when a change affects:

- mandatory public contracts
- multiple consumers
- integration class semantics
- dependency direction
- trust boundary
- cross-project data authority interpretation
- bootstrap behavior
- shared architecture assumptions

Handling:

Core Vision cross-project architecture review is required.

The legitimate domain authority remains Decision Owner for its domain.

## 35. Integration Change Class D — Portfolio / Authority

Use Class D when a change creates:

- new Core-wide mandatory dependency
- new ecosystem-wide trust assumption
- irreversible authority transfer
- new Core-wide integration hub
- removal of an authority-owning project
- permanent reassignment of an authority domain

Handling:

Explicit Human Maintainer authorization is required.

## 36. Escalation

Integration review must escalate when the original change class is no longer sufficient.

Examples:

- Class A reveals public-contract impact
- Class B introduces mandatory dependency
- Class B creates trust-boundary change
- Class C reveals irreversible authority transfer

Governance classification follows actual impact, not original intent.

## 37. Decision Owner

Every material integration governance case must identify a Decision Owner.

Examples:

- provider owns its public contract
- Core-Dev owns engineering readiness
- CoreOps owns current operational state
- CDS owns accepted normative CDS artifacts
- a product owns product-domain semantics
- Core Vision / Human Maintainer owns ecosystem architecture or portfolio decisions

Integration coordination does not erase these boundaries.

## 38. Core Brain governance boundary

Core Brain may consume and expose governed evidence and knowledge integrations.

Core Brain does not gain source-domain authority through:

- indexing
- retention
- search
- summarization
- correlation
- replication

If a Core Brain integration begins making binding decisions in another project's authority domain, the change requires explicit governance and normally represents an authority-boundary violation unless separately authorized.

## 39. Core-Dev governance boundary

Core-Dev may integrate with projects and CoreOps for:

- engineering evidence
- test evidence
- build evidence
- release readiness
- authorized deployment handoff

Core-Dev determines whether software is ready to be deployed within its authorized scope.

CoreOps performs and operates runtime deployment.

An integration must not collapse these two authorities.

## 40. CoreOps governance boundary

CoreOps may integrate with projects for:

- deployment
- operational state
- runtime automation
- infrastructure
- monitoring
- operational evidence

CoreOps remains authoritative for current operational state within its scope.

Operational integration does not transfer:

- development-governance authority
- engineering-readiness authority
- product-domain authority
- ecosystem-strategy authority

## 41. CDS governance boundary

CDS integration may distribute accepted normative design-system artifacts.

Consumption of CDS artifacts does not transfer:

- product semantics
- product behavior
- runtime authority
- development governance

Contract changes inside the CDS authority domain remain CDS-owned unless they create a cross-project architecture concern.

## 42. Product governance boundary

Products retain authority for product-specific behavior and domain semantics.

A shared integration may support a product.

Support does not transfer product ownership to the provider.

A product remains responsible for how external information is interpreted inside its own authoritative domain unless another explicit authority rule applies.

## 43. Core Vision governance boundary

Core Vision governs ecosystem-level integration architecture.

Core Vision may:

- classify integration impact
- identify authority conflicts
- review mandatory dependencies
- review trust assumptions
- review bootstrap risks
- coordinate cross-project architecture

Core Vision must not become:

- mandatory runtime router
- universal message broker
- universal data bus
- universal service registry
- universal operational authority

unless a future explicit governance decision creates and justifies such a role.

No such role is created by CV-WP-005.

## 44. Integration inventory

Future Core Vision software may maintain a structured inventory of governed integrations.

Such an inventory may describe:

- provider
- consumer
- contract
- integration class
- dependency type
- status
- compatibility
- authority owner

The inventory is descriptive governance state.

It does not become runtime control merely because it records integration relationships.

## 45. Failure review

Repeated integration failures may trigger governance review when they indicate:

- an optional dependency is effectively mandatory
- a provider is an ecosystem single point of failure
- stale information is being treated as current
- a trust model is insufficient
- a bootstrap cycle exists
- consumers depend on private implementation
- authority ownership is unclear

Operational failure itself does not automatically change governance state.

## 46. Exceptions

Exceptions to integration principles must be:

- explicit
- bounded
- documented
- justified
- reviewed
- assigned an owner

An exception must not silently become the new default.

## 47. Human authority

The Human Maintainer retains final authority over:

- new Core-wide mandatory dependencies
- irreversible authority transfers
- exceptions creating bootstrap cycles
- ecosystem-wide trust changes
- creation of new universal integration control planes
- irreversible removal of critical integration boundaries

AI systems may:

- classify integration changes
- identify dependency risks
- detect hidden coupling
- compare contracts
- identify authority ambiguity
- recommend migration

AI systems do not independently authorize irreversible ecosystem integration changes.
