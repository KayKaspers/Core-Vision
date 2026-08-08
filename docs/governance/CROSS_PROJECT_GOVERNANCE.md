# Core Cross-Project Governance

## 1. Purpose

This document defines when a matter becomes a Core Vision cross-project governance concern and how such matters are coordinated without transferring authority away from the projects and domains that legitimately own it.

Core Vision is an ecosystem governance layer.

It is not a universal implementation, development, design, knowledge, engineering, operational or product authority.

## 2. Core principle

Cross-project coordination does not imply shared authority.

Consultation does not imply approval authority.

Evidence does not imply decision authority.

Integration does not imply authority transfer.

Knowledge can be centralized, authority not.

## 3. When Core Vision governance applies

A matter should enter Core Vision cross-project governance when it materially affects one or more of the following:

- ecosystem strategy
- portfolio composition
- project admission or removal
- project tiering
- cross-project architecture
- capability ownership between projects
- authority ownership between projects
- mandatory dependencies between projects
- ecosystem-wide interface expectations
- bootstrap-cycle risk
- first-party trust assumptions
- shared strategic constraints
- authority transfer between projects
- retirement with ecosystem-wide consequences
- conflicting claims between projects
- creation of a new Core-wide control plane or foundation

A change inside a single project's established authority domain should normally remain project-local.

## 4. Matters that remain project-local

Core Vision should not intervene merely because a project:

- changes implementation details
- refactors internal code
- modifies internal schemas
- changes project-local tests
- executes normal Work Packages
- makes project-local ADRs within existing authority
- changes internal deployment mechanics within authorized boundaries
- updates product-specific functionality
- changes internal UI behavior
- performs routine runtime operations

Project-local governance remains authoritative unless the change crosses an established ecosystem boundary.

## 5. Governance trigger test

Before escalating a matter to Core Vision, ask:

1. Does this change affect another project's authority?
2. Does it create or change a mandatory cross-project dependency?
3. Does it alter portfolio membership or tiering?
4. Does it create a new ecosystem-wide capability owner?
5. Does it transfer authority between projects?
6. Does it create a bootstrap cycle?
7. Does it require another project to trust a first-party component implicitly?
8. Does it change a shared architectural rule?
9. Does it materially constrain multiple Core projects?
10. Does it create ambiguity about which project is authoritative?

If all answers are no, the matter should normally remain project-local.

## 6. Cross-project governance participants

A governance case may involve:

- Core Vision
- Human Maintainer
- affected project owners
- NDF
- Core Brain
- Core Design System
- Core-Dev
- CoreOps
- affected product projects
- conditional or candidate projects where relevant

Participation does not make every participant a decision owner.

## 7. Decision Owner

Every cross-project governance matter must identify a Decision Owner.

The Decision Owner is the authority that owns the decision domain.

Examples:

| Decision domain | Primary Decision Owner |
|---|---|
| Ecosystem strategy | Core Vision / Human Maintainer |
| Portfolio admission | Core Vision / Human Maintainer |
| Project tiering | Core Vision / Human Maintainer |
| Cross-project architecture | Core Vision / Human Maintainer |
| Development governance methodology | NDF within its authorized scope |
| Knowledge/evidence system behavior | Core Brain within its authorized scope |
| Accepted design-system normative artifacts | CDS within its authorized scope |
| Engineering readiness | Core-Dev within its authorized scope |
| Operational state and deployment execution | CoreOps within its authorized scope |
| Product behavior and domain semantics | Individual product/domain owner |
| Irreversible authority transfer | Human Maintainer |

Cross-project involvement does not automatically move the decision to Core Vision.

## 8. Consultation versus authority

A project may be:

- consulted
- informed
- evidence provider
- implementation participant
- consumer
- affected party
- reviewer

without becoming the Decision Owner.

Consultation rights and decision rights must remain distinguishable.

A consulted project's objection may be material evidence.

It does not automatically become a veto unless that project owns an affected authority domain.

## 9. Authority collision

An authority collision exists when two or more projects appear to claim binding authority over the same decision domain.

Examples include:

- two projects claiming operational Source of Truth
- two projects claiming product-domain semantic authority
- two projects claiming ecosystem-wide development governance
- two projects claiming ownership of the same mandatory interface contract
- a shared service attempting to override its source-domain authority

Authority collisions must fail closed.

No project may silently win an authority collision through:

- implementation precedence
- deployment precedence
- data replication
- repository age
- integration popularity
- first-party status
- AI recommendation

The collision must be resolved through explicit governance.

## 10. Capability overlap

Capability overlap is not automatically an authority collision.

Multiple projects may possess similar technical capabilities for different purposes.

For example:

- Core Brain and CoreOps may both handle evidence
- Core-Dev and CoreOps may both execute automation
- CDS and products may both contain UI-related artifacts

The governance question is not only:

> Who can perform this capability?

The stronger question is:

> Who is authoritative for the decision domain in which the capability is being used?

Capability ownership and authority ownership must remain distinguishable.

## 11. Cross-project change classes

### 11.1 Class A — Local

A change remains fully within one project's established authority and does not materially affect another project.

Default handling:

Project-local governance.

### 11.2 Class B — Consultative

A change remains owned by one project but materially affects consumers or neighboring projects.

Default handling:

- Decision Owner remains unchanged
- affected projects are consulted
- compatibility and dependency impact are documented

### 11.3 Class C — Cross-Project Architecture

A change affects shared architecture, mandatory interfaces, capability boundaries or multiple authority domains.

Default handling:

- Core Vision review
- explicit Decision Owner
- affected-project consultation
- authority-impact analysis
- architecture-principle review

### 11.4 Class D — Portfolio / Authority

A change affects:

- portfolio admission
- portfolio removal
- tier assignment
- ecosystem authority ownership
- irreversible authority transfer
- creation or removal of a Core-wide foundation or control plane

Default handling:

Explicit Human Maintainer authorization is required.

## 12. Required governance case information

A material cross-project governance case should identify:

- issue or proposed change
- triggering project
- affected projects
- decision domain
- Decision Owner
- evidence
- assumptions
- unresolved unknowns
- capability impact
- authority impact
- dependency impact
- lifecycle impact where relevant
- portfolio impact where relevant
- security or trust impact where relevant
- recommended outcome
- final authorized decision

Unknown material information must not be silently invented.

## 13. Evidence and recommendations

Evidence may come from:

- project documentation
- repositories
- tests
- operational systems
- CoreOps
- Core-Dev
- Core Brain
- CDS
- NDF
- product systems
- Human Maintainer input
- external research

Evidence providers do not automatically become decision authorities.

Recommendations must be labeled as recommendations.

An AI-generated recommendation is not an authorized decision.

## 14. Conflict handling

When affected projects disagree, governance should first determine whether the disagreement concerns:

- facts
- implementation preference
- compatibility
- capability ownership
- authority ownership
- strategic direction

Different disagreement types require different resolution.

A factual conflict requires better evidence.

An implementation disagreement normally remains with the project-local owner.

A compatibility conflict requires coordination between affected parties.

An authority conflict requires explicit governance resolution.

A strategic ecosystem conflict belongs to Core Vision / Human Maintainer.

## 15. Fail-closed governance

A cross-project decision must fail closed when material uncertainty exists about:

- Decision Owner
- authority ownership
- irreversible authority transfer
- mandatory dependency direction
- bootstrap-cycle creation
- portfolio status
- security-critical trust assumptions

Fail-closed means the binding ecosystem change is withheld.

It does not mean all project-local work must stop unless that local work would violate the unresolved boundary.

## 16. Authority transfer

Authority transfer between Core projects is an exceptional governance event.

A valid transfer must identify:

- current authority owner
- future authority owner
- exact decision domain
- migration boundary
- affected consumers
- historical evidence handling
- effective transition point
- rollback or contingency requirements where applicable
- Human Maintainer authorization

Authority must not transfer implicitly because another system:

- stores the data
- deploys the component
- exposes the UI
- executes the automation
- becomes more widely used
- contains a newer implementation

## 17. Dependency governance

A new mandatory cross-project dependency requires explicit review.

The review must consider:

- Standalone First
- Public Interface First
- No Implicit First-Party Trust
- Graceful Absence
- No Bootstrap Cycles
- Authority Preservation

Optional integration should remain preferred where permanent mandatory coupling is not justified.

No project may access another project's private implementation merely because both are first-party Core projects.

## 18. Foundation changes

Changes to a T1 foundation require special attention when they alter assumptions used by multiple downstream projects.

A foundation change does not automatically require Core Vision approval.

Core Vision review becomes appropriate when the change:

- alters ecosystem authority boundaries
- creates mandatory cross-project coupling
- changes a shared architectural principle
- materially affects multiple tiers
- changes the foundation's ecosystem role

The foundation remains authoritative inside its established domain.

## 19. Control-plane changes

Core-Dev and CoreOps have separate control-plane roles.

Core-Dev determines engineering and release readiness within its authorized scope.

CoreOps performs and operates runtime deployment and operational control within its authorized scope.

A cross-project governance review is required if either control plane attempts to assume the other's authority.

Core Vision coordinates the boundary.

It does not replace either control plane.

## 20. Product changes

Products retain authority over their product-specific behavior and domain semantics.

Shared foundations and control planes may constrain interfaces, readiness, design artifacts or operations within their own authorized domains.

They do not automatically become product-domain authorities.

Core Vision should intervene only when a product change becomes an ecosystem-level architecture, authority, dependency or portfolio concern.

## 21. Relationship to NDF

NDF remains authoritative for development governance within its defined scope.

Core Vision does not replace:

- NDF Work Package governance
- project-local Decision processes
- project-local ADR governance
- project-local review mechanics
- release methodology

NDF governance may produce evidence for a cross-project governance case.

That evidence does not transfer the affected domain authority to Core Vision.

## 22. Relationship to Core Brain

Core Brain may retain, relate and retrieve cross-project governance evidence and decisions.

Core Brain does not become the Decision Owner merely because it stores or retrieves the information.

Source-domain authority remains external to the knowledge system.

## 23. Relationship to CDS

CDS remains authoritative for accepted normative CDS artifacts within its established design-system scope.

A product consuming CDS does not transfer product-domain authority to CDS.

CDS participation in a governance case is authoritative only for the CDS-owned decision domain.

## 24. Relationship to Core-Dev

Core-Dev may provide:

- engineering health
- test evidence
- build evidence
- readiness evidence

Core-Dev may decide engineering readiness within its authorized scope.

It does not independently decide:

- portfolio membership
- ecosystem strategy
- runtime operational authority
- product semantics

## 25. Relationship to CoreOps

CoreOps may provide:

- operational state
- deployment state
- runtime evidence
- operational provenance
- infrastructure evidence

CoreOps remains authoritative for current operational state within its authorized scope.

It does not independently decide:

- portfolio membership
- development governance
- product semantics
- ecosystem strategy

## 26. Conditional projects

Projects in Conditional Exploration may participate in bounded governance analysis.

They do not gain permanent authority through participation.

Core Vision must not make an existing confirmed project dependent on a conditional project unless that dependency is separately and explicitly authorized.

## 27. Human authority

The Human Maintainer retains final authority over irreversible ecosystem-level decisions, including:

- permanent project admission
- permanent project removal
- tier reassignment with ecosystem consequences
- creation of new Core-wide authority domains
- irreversible authority transfers
- binding resolution of unresolved cross-project authority collisions

AI systems may:

- identify governance triggers
- collect evidence
- compare authority claims
- identify conflicts
- classify change scope
- prepare recommendations

AI systems do not independently perform irreversible ecosystem governance actions.
