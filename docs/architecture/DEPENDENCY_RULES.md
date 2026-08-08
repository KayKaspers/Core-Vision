# Core Ecosystem Dependency Rules

**Status:** Foundation Draft

## Purpose

This document defines allowed and prohibited dependency patterns across the Core ecosystem.

The goal is interoperability without hidden coupling, implicit trust or authority transfer.

## 1. Standalone First

A Core project should provide its defined core capability without requiring unrelated optional Core projects.

Examples:

- SpeakCore must not require Core Vision merely to start.
- CoreOps must not require Core Brain for basic operational capability.
- Core-Dev must not require CoreOps for development readiness checks.
- NDF must not require a running Core Vision service to govern projects.
- Products must not require Core Brain unless the knowledge capability is explicitly part of their defined core architecture.

Optional integrations may enhance functionality.

They must not silently become mandatory dependencies.

## 2. Public Interface First

Preferred cross-project integration mechanisms include:

- documented APIs
- documented event contracts
- documented file contracts
- stable CLI contracts
- versioned schemas
- published artifacts

Internal Core integrations should use the same stable interfaces available to external consumers where practical.

Private implementation details are not integration contracts.

## 3. Hidden database coupling

Direct cross-project access to private databases is prohibited by default.

A consumer must not depend on:

- private database tables
- undocumented storage layout
- private ORM models
- internal migration state
- implementation-specific database credentials

If data must cross a project boundary, it should be exposed through a governed interface or artifact contract.

## 4. No Implicit First-Party Trust

Core affiliation does not automatically grant:

- authentication
- authorization
- administrative privilege
- secret access
- database access
- infrastructure access
- private user-data access

Trust must be explicit.

Access should follow least privilege.

## 5. Graceful Absence

Optional dependencies must define behavior when the provider is unavailable.

Valid patterns may include:

- degraded mode
- cached mode
- read-only mode
- delayed synchronization
- feature-disabled mode
- explicit unavailable state

Absence of an optional provider must not silently corrupt local state or authority.

## 6. No Bootstrap Cycles

Mandatory circular startup dependencies are prohibited.

The following pattern is invalid:

A requires B to start.

B requires C to start.

C requires A to start.

Architecture reviews must reject new mandatory bootstrap cycles.

Optional asynchronous integration does not automatically create a bootstrap cycle.

## 7. Authority Preservation

Receiving information from another project does not transfer authority.

Examples:

- Core Brain may store CoreOps evidence, while CoreOps remains authoritative for current operational state.
- Core Vision may consume strategic project summaries without becoming project implementation authority.
- CoreOps may consume Core-Dev release-readiness information without becoming development-governance authority.
- Core-Dev may consume NDF governance rules without becoming the owner of NDF governance.

Knowledge can be centralized, authority not.

## 8. Core Vision dependencies

Core Vision may consume strategic information from projects.

Core Vision should prefer:

- health summaries
- milestone state
- strategic risk state
- release status
- aggregate operational indicators
- architecture metadata

Core Vision should not require unrestricted access to:

- raw secrets
- operational credentials
- complete private infrastructure inventories
- unrelated private product data
- internal databases of other projects

Core Vision must not become a mandatory runtime dependency for unrelated Core products.

## 9. NDF dependencies

NDF governance may be consumed as:

- documentation
- templates
- schemas
- workflow rules
- skills
- validation contracts

NDF must not require a mandatory Core Vision runtime service.

NDF does not gain ecosystem strategy authority through adoption.

## 10. Core Brain dependencies

Core Brain may provide optional knowledge and evidence services.

Consumers must preserve provenance and source authority.

Core Brain must not automatically become:

- operational truth authority
- product authority
- development authority
- ecosystem strategy authority

Core Brain failure must not automatically prevent unrelated standalone project operation.

## 11. Core-Dev dependencies

Core-Dev may consume:

- NDF governance
- project metadata
- build state
- test results
- release-readiness evidence

Core-Dev may produce:

- engineering health
- readiness state
- release-ready artifacts
- Human Maintainer engineering views

Core-Dev does not replace CoreOps.

Production runtime operation remains outside the Core-Dev authority domain.

## 12. CoreOps dependencies

CoreOps may consume:

- authorized release artifacts
- deployment manifests
- operational configuration
- readiness information
- documented integrations

CoreOps owns operational execution and current runtime state within its domain.

CoreOps must not redefine:

- NDF development governance
- Core Vision strategy
- product functionality

## 13. Product dependencies

Products retain their product-specific authority.

A product may integrate with Core foundations or control planes.

Such integration must not automatically:

- revoke standalone capability
- expose private product data
- transfer product authority
- grant administrator access
- create hidden runtime coupling

## 14. CDS dependencies

CDS may provide accepted design-system foundations such as:

- brand and identity artifacts
- design tokens
- interaction foundations
- components and patterns
- presentation foundations
- channel and communication design artifacts

Consumers should use published, versioned or otherwise governed CDS artifacts where available.

CDS adoption does not automatically transfer:

- product behavior authority
- product-domain semantics
- business-rule authority
- runtime authority
- development governance
- ecosystem strategy authority
- document-domain semantic or schema authority

Document presentation and document semantics are separate authority concerns.

CDS may govern accepted presentation foundations for documents without becoming authoritative for the semantic meaning, schema, lifecycle or business rules of those documents.

If document-domain semantic or schema authority is later assigned to another explicitly authorized Core project, that authority remains separate from CDS presentation authority.

Registration of a CDS capability domain is not evidence that a stable or consumable implementation already exists.
## 15. Conditional projects

Core Document Framework remains Conditional Exploration.

No Core project may treat CDF as a mandatory permanent ecosystem dependency until permanent portfolio admission and architecture authority are explicitly approved.

OrgaCore and AirCore remain observed candidates and receive no mandatory dependency role.

## 16. Dependency classes

Allowed dependency classes include:

### Governance dependency

Conformance to governance without requiring a runtime service.

### Artifact dependency

Consumption of versioned and documented artifacts.

### Optional service dependency

Enhancement through another project with graceful-absence behavior.

### Evidence dependency

Consumption of evidence while preserving provenance and authority.

### Explicit runtime dependency

A runtime dependency may exist when it is part of the consuming project's approved architecture.

It must be documented and must not create prohibited coupling or bootstrap cycles.

## 17. Prohibited patterns

The following are prohibited by default:

- hidden cross-project database access
- undocumented private API dependency
- hard-coded shared credentials
- first-party authentication bypass
- unrestricted cross-project administrator trust
- mandatory circular startup dependencies
- authority transfer through synchronization
- one project directly mutating another project's private internal state
- Core Vision acting as mandatory runtime parent for unrelated products
- Core Brain acting as universal truth authority
- Core-Dev replacing CoreOps
- CoreOps replacing NDF
- product authority silently moving into a shared control plane

## 18. Review rule

New cross-project dependencies should be evaluated for:

- standalone impact
- trust boundary
- authority impact
- bootstrap-cycle risk
- graceful-absence behavior
- interface stability
- data minimization
- security implications

Permanent ecosystem-level dependency changes require Core Vision architecture review where applicable.
