# CV-WP-003 — Core Ecosystem Architecture & Boundaries

## Type

docs-only / architecture

## Priority

P0

## Status

COMPLETE

## Objective

Define the first explicit Core ecosystem architecture, capability ownership model, authority boundaries and dependency rules.

## Inputs

CV-WP-003 builds on:

- CV-WP-001 Core Vision Foundation
- CV-WP-002 Core Ecosystem Inventory & Classification
- completed Core Vision alignment reviews
- the six Core Vision architecture principles

## Binding principles

1. Standalone First
2. Public Interface First
3. No Implicit First-Party Trust
4. Graceful Absence
5. No Bootstrap Cycles
6. Authority Preservation

## Core rule

Knowledge can be centralized, authority not.

## Allowed scope

- ecosystem layer model
- capability ownership
- authority ownership
- cross-project responsibility boundaries
- allowed dependency directions
- prohibited coupling
- graceful-absence requirements
- bootstrap-cycle prevention
- strategic information-flow boundaries

## Out of scope

- API schema design
- protocol selection
- database selection
- application implementation
- Web UI implementation
- deployment implementation
- mandatory integrations
- changing another Core repository

## Required outputs

- ecosystem architecture model
- capability ownership model
- authority matrix
- dependency rules

## Acceptance criteria

1. Core Vision and NDF authority remain separate.
2. Core Brain does not become a domain super-authority.
3. Core-Dev remains the Engineering Control Plane.
4. CoreOps remains the Operations Control Plane.
5. Products retain product-specific authority.
6. Optional Core components remain optional where possible.
7. No mandatory bootstrap cycles are introduced.
8. First-party identity grants no implicit trust.
9. Hidden cross-project database coupling is prohibited.
10. Internal integration should use stable documented interfaces where practical.
11. Authority is preserved across evidence and information exchange.
12. Human Maintainer reviews boundaries before commit.

## Human authority

Architecture ownership, authority transfer and permanent cross-project responsibility assignments require explicit Human Maintainer / Core Vision approval.

## Completion

CV-WP-003 completed after architecture bootstrap, cross-project review and bounded rework.

Final architecture state:

- Core Vision owns ecosystem strategy, portfolio governance and cross-project architecture.
- NDF owns development governance.
- Core Brain is the Knowledge & Evidence Plane without source-domain super-authority.
- CDS owns accepted normative design-system artifacts within its defined design-system scope.
- Core-Dev is the Engineering Control Plane and owns engineering/release readiness.
- CoreOps is the Operations Control Plane and owns operational Source of Truth, operational state and operational provenance.
- Products retain product-specific behavior and domain authority.
- CDF remains Conditional Exploration without permanent ecosystem authority.
- Standalone First, Public Interface First, No Implicit First-Party Trust, Graceful Absence, No Bootstrap Cycles and Authority Preservation are binding architecture principles.
- Hidden cross-project database coupling and silent authority transfer are prohibited.
- Human Maintainer authority remains preserved.

Final Review: PASS.
