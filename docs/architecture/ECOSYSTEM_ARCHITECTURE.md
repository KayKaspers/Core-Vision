# Core Ecosystem Architecture

**Status:** Foundation Draft

## 1. Purpose

The Core ecosystem is a federation of independently usable projects with explicit ownership, authority boundaries and controlled interoperability.

Core Vision governs ecosystem strategy and cross-project architecture.

Core Vision is not a mandatory runtime parent for Core projects.

## 2. Logical tier model

T0 — Ecosystem Governance

- Core Vision

T1 — Shared Foundations

- Nova Development Framework
- Core Brain
- Core Design System

T2 — Engineering

- Core-Dev

T3 — Operations

- CoreOps

T4 — Products

- SpeakCore
- CastCore
- SC-OrgaBase
- future products

The tier model describes architectural responsibility.

It is not a mandatory runtime call chain or startup sequence.

## 3. Core Vision

Core Vision owns:

- ecosystem strategy
- portfolio governance
- cross-project architecture
- capability-boundary governance
- strategic technology assessment
- strategic risk governance
- cross-project strategic decisions
- ecosystem roadmap alignment

Core Vision does not own:

- individual project implementation
- development workflow execution
- knowledge truth
- runtime operations
- deployment execution
- infrastructure management
- product-specific runtime authority

## 4. Nova Development Framework

NDF owns development governance.

This includes methods for:

- work packages
- gates
- Decisions
- ADRs
- Risks
- reviews
- release governance
- Lessons Learned

NDF does not own:

- ecosystem portfolio strategy
- runtime infrastructure
- product-specific authority

NDF governance should not require a running Core Vision service.

## 5. Core Brain

Core Brain is the Knowledge & Evidence Plane.

It may own knowledge and evidence capabilities such as:

- knowledge/evidence record provenance
- evidence storage
- retrieval
- context construction
- evidence relationships
- conflict detection

These capabilities govern Core Brain records, evidence relationships and retrieval behavior.

They do not make Core Brain authoritative for the underlying source domain.

Core Brain may provide knowledge about another authority.

It does not become that authority.

Example:

Core Brain may retain and relate evidence supplied by CoreOps about a service state.

CoreOps remains authoritative for current operational state.
## 6. Core Design System

Core Design System is the shared Design System Foundation for the Core ecosystem.

Its registered long-term design-system scope may include:

- brand and identity
- experience and interaction
- foundations and tokens
- components and patterns
- channels and communication
- design-system governance and enablement

CDS may also define presentation foundations for documents and multi-channel communication where explicitly accepted.

Registration of a capability domain does not mean that a concrete artifact, technology, visual design, component or compatibility commitment already exists.

CDS authority applies to accepted normative CDS artifacts.

CDS does not automatically own:

- product-specific behavior
- product-domain semantics
- business rules
- runtime operations
- development governance
- ecosystem strategy
- document-domain semantics belonging to another explicitly authorized project

Consumer projects retain authority over their product-specific domain.

CDS adoption does not transfer product or runtime authority.
## 7. Core-Dev

Core-Dev is the Engineering Control Plane.

Its intended responsibility includes:

- engineering workflow orchestration
- development cockpit functions
- development health
- test readiness
- build readiness
- release readiness
- Human Maintainer engineering workflows
- future engineering Web UI

Core-Dev determines whether software is ready to be deployed.

Core-Dev does not replace CoreOps.

Core-Dev does not own production runtime operation.

## 8. CoreOps

CoreOps is the Operations Control Plane.

Its operational responsibility may include:

- infrastructure discovery
- runtime inventory
- operational Source of Truth
- observed, desired and effective operational state
- operational evidence and field provenance
- deployment execution
- operational health
- monitoring
- automation
- recovery
- operational security
- infrastructure compliance evidence

CoreOps may consume release-ready artifacts from engineering workflows.

CoreOps remains authoritative for current operational state within its domain.

Core Brain may retain, relate or retrieve CoreOps evidence without replacing CoreOps authority.

CoreOps does not own development governance or ecosystem strategy.
## 9. Products

Products retain authority over their product-specific domains and user-facing functionality.

Current confirmed product examples include:

- SpeakCore
- CastCore
- SC-OrgaBase

Products may integrate with other Core components.

Such integrations must not silently transfer product authority.

Standalone core functionality should remain available without unrelated optional Core services unless an explicit architecture decision states otherwise.

## 10. Conditional and observed projects

Core Document Framework remains Conditional Exploration.

It receives no permanent ecosystem authority through this architecture draft.

OrgaCore and AirCore remain observed candidates.

Repository existence alone does not establish portfolio authority.

## 11. Architectural invariants

### Standalone First

A Core project should provide its defined core capability without mandatory presence of unrelated optional Core projects.

### Public Interface First

Cross-project integrations should use stable and documented interfaces usable externally where practical.

### No Implicit First-Party Trust

Core affiliation does not automatically grant trust, authentication, authorization or privileged access.

### Graceful Absence

Optional Core components may be unavailable without breaking unrelated standalone functionality.

### No Bootstrap Cycles

Mandatory circular startup or runtime dependencies are prohibited.

### Authority Preservation

Information exchange, evidence sharing and integration do not transfer domain authority.

## 12. Human authority

Human Maintainer authority remains binding for irreversible ecosystem decisions, authority transfers and permanent architecture assignments.

AI systems may analyze and recommend.

They do not gain irreversible ecosystem authority.

## 13. Core rule

Knowledge can be centralized, authority not.
