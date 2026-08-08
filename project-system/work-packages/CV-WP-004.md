# CV-WP-004 — Project Lifecycle, Intake & Cross-Project Governance

## Type

docs-only / governance

## Priority

P0

## Status

COMPLETE

## Objective

Define how projects enter, move through, change within and leave the Core ecosystem, and define how cross-project governance decisions are initiated, reviewed and authorized.

## Inputs

CV-WP-004 builds on:

- CV-WP-001 Core Vision Foundation
- CV-WP-002 Ecosystem Inventory & Classification
- CV-WP-003 Ecosystem Architecture & Boundaries
- established Human Maintainer authority
- established project authority boundaries

## Required outputs

- project lifecycle model
- portfolio intake model
- cross-project governance model

## Core governance rules

1. Repository existence does not grant portfolio membership.
2. Portfolio membership and lifecycle state are separate concepts.
3. Project admission requires explicit Core Vision / Human Maintainer decision.
4. Project-specific implementation authority remains with the project.
5. Cross-project governance does not silently transfer domain authority.
6. Conditional exploration does not equal permanent portfolio admission.
7. Evidence must be distinguishable from decisions.
8. Human Maintainer authority remains binding for irreversible decisions.

## Allowed scope

- project lifecycle states
- lifecycle transition rules
- project intake criteria
- intake evidence requirements
- portfolio admission
- conditional exploration
- pause, retirement and archival governance
- cross-project governance triggers
- escalation rules
- decision ownership
- authority-preserving coordination

## Out of scope

- software implementation
- Web UI
- database design
- APIs
- automation implementation
- direct modification of other Core repositories
- product-specific development workflow
- replacing NDF governance
- runtime operations

## Acceptance criteria

1. Lifecycle state and portfolio membership are explicitly separated.
2. Intake is evidence-based and fail-closed on material uncertainty.
3. Repository discovery alone cannot admit a project.
4. Conditional Exploration is explicitly non-permanent.
5. Permanent portfolio admission requires explicit approval.
6. Projects retain their own implementation authority.
7. Cross-project decisions identify an authoritative owner.
8. Consultation does not imply shared authority.
9. Retirement and archival do not silently delete historical evidence.
10. NDF development governance remains separate from Core Vision portfolio governance.
11. Core Vision does not become project implementation authority.
12. Human Maintainer authority remains preserved.

## Human authority

The Human Maintainer retains final authority over:

- permanent portfolio admission
- permanent portfolio removal
- irreversible authority transfers
- repository publication decisions
- commits, pushes, tags and releases

AI systems may analyze, prepare, compare and recommend.

They do not independently perform irreversible governance decisions.

## Completion

CV-WP-004 completed after lifecycle, portfolio intake and cross-project governance definition followed by final governance and CV-WP-003 regression review.

Final governance state:

- Portfolio relationship and project lifecycle are separate governance axes.
- Observed Candidate, Conditional Exploration and Confirmed portfolio relationships are explicitly distinguished.
- Planned, Active, Paused, Retiring, Retired and Archived lifecycle states are defined.
- Repository existence, discovery, deployment or engineering activity do not independently grant portfolio membership.
- Portfolio intake follows evidence collection, identity resolution, classification, overlap review, recommendation and explicit Human decision.
- Material identity, authority and dependency uncertainty fails closed for permanent admission.
- Conditional Exploration remains non-permanent.
- Cross-project governance requires an explicit Decision Owner.
- Consultation, evidence provision and implementation participation do not imply authority.
- Authority collisions fail closed pending explicit resolution.
- Capability overlap does not automatically imply authority collision.
- Cross-project changes are classified as Local, Consultative, Cross-Project Architecture or Portfolio / Authority.
- Project-local authority remains with the authorized project or domain owner.
- NDF remains development-governance authority within its scope.
- Core Brain remains the Knowledge & Evidence Plane without decision super-authority.
- CDS remains authoritative only within its accepted normative design-system scope.
- Core-Dev remains Engineering Control Plane.
- CoreOps remains Operations Control Plane.
- Products retain product-specific behavior and domain-semantic authority.
- Human Maintainer authority remains preserved for irreversible ecosystem decisions.
- Knowledge can be centralized, authority not.

Final Governance Review R1: PASS.
