# Core Vision Human, Rule and AI Authority Model

## 1. Purpose

This document defines the semantic separation between:

- authoritative Human decisions
- deterministic governance rules
- AI-assisted analysis and recommendation
- evidence
- proposed governance effects
- effective governance state

The goal is to ensure that automation increases consistency and analytical quality without silently creating new authority.

This model is technology-independent.

It does not define:

- workflow products
- AI vendors
- AI models
- rule-engine products
- databases
- authentication products
- frontend frameworks
- deployment architecture

## 2. Core authority principle

Core Vision software may automate governance support.

Automation does not create authority.

Authority derives from the established governance model.

A deterministic rule may enforce an already authorized governance constraint.

An AI system may analyze and recommend within its authorized analytical role.

A Human actor may authorize decisions only within the authority granted by the governance model.

Knowledge can be centralized, authority not.

## 3. Three distinct reasoning roles

Future Core Vision software must distinguish three reasoning and decision roles:

### 3.1 Deterministic Rule Evaluation

Deterministic rules evaluate explicit governance conditions.

They should produce reproducible results for the same:

- rule revision
- governed inputs
- relevant state

### 3.2 AI Analysis

AI interprets evidence and context where deterministic rules alone are insufficient.

AI may:

- explain
- compare
- summarize
- identify uncertainty
- identify contradiction
- propose classifications
- prepare recommendations

### 3.3 Human Authorization

Human authorization represents an explicit decision by an actor who owns or has been granted the relevant authority.

These roles must remain distinguishable in data, workflow and presentation.

## 4. Evidence is not a decision role

Evidence may influence:

- rules
- analysis
- recommendations
- decisions

Evidence does not authorize itself.

The existence of evidence does not automatically determine a governance outcome unless an already authorized deterministic rule explicitly defines that effect.

## 5. Deterministic rule purpose

Deterministic rules exist to make explicit governance constraints:

- consistently evaluable
- explainable
- repeatable
- auditable
- less dependent on ad hoc interpretation

Rules should encode established governance.

Rules must not silently create new governance policy.

## 6. Rule authority source

Every material deterministic rule should have an identifiable authority basis.

Possible authority bases include:

- accepted Core Vision governance rule
- accepted architecture principle
- accepted authority assignment
- accepted lifecycle rule
- accepted integration rule
- Human-authorized exception policy
- other explicitly governed Core Vision decision

A rule without an identifiable authority basis must not silently block a binding governance action.

## 7. Rule classes

Core Vision discovery recognizes the following semantic rule classes.

### 7.1 Validation Rule

A Validation Rule checks whether structured information satisfies a defined contract.

Examples:

- required field missing
- invalid lifecycle value
- unknown integration class
- malformed authority assignment

Possible outcomes include:

- PASS
- FAIL
- UNKNOWN
- NOT APPLICABLE

### 7.2 Consistency Rule

A Consistency Rule detects incompatible or contradictory governed information.

Examples:

- two exclusive authority owners recorded
- lifecycle state inconsistent with required predecessor
- integration marked both Retired and Active
- project classified as non-member but assigned permanent portfolio authority

A consistency failure identifies a conflict.

It does not invent the resolution.

### 7.3 Invariant Rule

An Invariant Rule enforces a binding governance constraint already established by authorized governance.

Examples:

- mandatory bootstrap cycles prohibited
- hidden authority transfer prohibited
- permanent authority cannot arise solely from Conditional Exploration
- required Human approval missing
- source-domain authority cannot transfer through replication alone

A failed binding Invariant Rule may block the proposed governance effect.

### 7.4 Eligibility Rule

An Eligibility Rule determines whether a proposed action has satisfied defined prerequisites.

Examples:

- admission evidence incomplete
- Decision Owner unresolved
- mandatory integration review incomplete
- required consultation missing
- authority-impact analysis missing

Eligibility may produce:

- ELIGIBLE
- INELIGIBLE
- BLOCKED
- UNKNOWN

Eligibility does not itself authorize the action.

### 7.5 Derived-State Rule

A Derived-State Rule calculates a non-authoritative derived representation from canonical inputs.

Examples may include:

- risk indicator
- unresolved dependency count
- stale-evidence indicator
- governance completeness score

Derived state must remain distinguishable from canonical authoritative state.

### 7.6 Advisory Rule

An Advisory Rule identifies a condition worth Human or AI review without independently blocking an action.

Examples:

- unusually high coupling
- growing number of exceptions
- repeated provider outages
- large unresolved governance backlog

Advisory results are not decisions.

## 8. Rule result semantics

Rule results must not collapse into a single generic boolean where governance meaning differs.

Candidate semantic outcomes include:

- PASS
- FAIL
- BLOCKED
- WARNING
- UNKNOWN
- NOT APPLICABLE
- ELIGIBLE
- INELIGIBLE

The exact implementation representation remains deferred.

## 9. Deterministic blocking

A deterministic rule may block a proposed governance effect only when:

- the rule represents an already authorized binding constraint
- the evaluated inputs are sufficiently known for that rule
- the rule revision is identifiable
- the rule applies to the proposed action
- no already-authorized exception applies

Blocking is enforcement of existing governance.

Blocking is not creation of new authority.

## 10. Block versus decision

A deterministic BLOCK means:

> The proposed effect may not proceed under the currently effective governance conditions.

It does not automatically mean:

- permanently rejected
- malicious
- strategically wrong
- impossible to reconsider
- Human decision already made

A blocked proposal may require:

- corrected data
- missing evidence
- different proposal
- explicit governance review
- an authorized exception path where one exists

## 11. Unknown versus fail

UNKNOWN must remain distinct from FAIL.

UNKNOWN means the system lacks sufficient governed information to produce the required conclusion.

Where current authoritative information is required for an irreversible effect, UNKNOWN may cause the effect to be withheld.

That is fail-closed behavior.

It does not convert UNKNOWN into a fabricated negative fact.

## 12. Rule transparency

A material rule result should be explainable.

A future system should be capable of identifying:

- rule identifier
- rule purpose
- rule revision
- authority basis
- relevant inputs
- result
- reason
- blocking effect if any

AI may help explain the result.

AI must not alter the deterministic result merely to produce a more convenient answer.

## 13. Rule versioning

Rules may evolve as governance evolves.

A material rule result should remain associated with the rule revision that produced it.

A later rule revision must not silently rewrite the historical meaning of an earlier evaluation.

This does not yet prescribe a rule storage or versioning technology.

## 14. AI purpose

AI exists primarily for analytical work that benefits from contextual reasoning and natural-language interpretation.

Candidate AI responsibilities include:

- evidence summarization
- inconsistency explanation
- missing-evidence identification
- architectural comparison
- capability-overlap analysis
- authority-collision hypothesis generation
- governance-impact classification proposals
- risk explanation
- recommendation preparation
- draft rationale preparation
- next-action proposals

AI is decision support.

AI is not the default binding decision authority.

## 15. AI output classes

AI-generated material should remain semantically distinguishable.

Candidate classes include:

- summary
- observation
- hypothesis
- inference
- classification proposal
- risk assessment
- recommendation
- rationale draft
- governance-action proposal

AI output must not be stored as an authorized decision merely because it is structured or confident.

## 16. AI confidence

AI confidence is not authority.

A highly confident AI recommendation does not override:

- deterministic binding rules
- Human approval requirements
- source-domain authority
- governance constraints
- unresolved material uncertainty

AI confidence may support prioritization or review.

It must not become an authorization mechanism.

## 17. AI and deterministic rules

AI may:

- explain a deterministic result
- identify evidence relevant to a rule
- identify likely data-quality problems
- suggest how a blocked proposal could become compliant
- propose an exception case for Human review where governance permits exceptions

AI must not:

- silently change rule inputs
- silently ignore a failed binding rule
- rewrite the rule result
- declare an unauthorized exception
- represent BLOCKED as PASS
- treat an advisory recommendation as a binding invariant

Deterministic rule output and AI interpretation must remain separately visible.

## 18. AI and missing evidence

AI may identify missing evidence.

AI may suggest likely evidence sources.

AI must not fabricate missing evidence.

AI-generated inference must not be relabeled as observed evidence.

Where required evidence remains unavailable, the system must preserve the resulting UNKNOWN or BLOCKED state as required by governance.

## 19. AI and source-domain authority

AI may reason across information from:

- Core Vision
- Core Brain
- Core-Dev
- CoreOps
- CDS
- products
- repositories
- Human-provided material

AI reasoning does not transfer source-domain authority.

An AI synthesis of CoreOps evidence does not become operational Source of Truth.

An AI interpretation of Core-Dev evidence does not become engineering readiness authority.

## 20. AI mutation boundary

AI should not directly mutate authoritative Core Vision governance state merely because it produced a recommendation.

A future architecture should distinguish:

- AI proposes a change
- deterministic checks evaluate the proposal
- required Human authorization occurs
- an authorized effect applies to canonical state

Some low-risk administrative or non-authoritative automation may later be delegated.

Such delegation requires explicit authorization and must not be inferred from this discovery document.

## 21. Human role

Human actors perform governance functions according to their assigned authority.

The Human Maintainer retains the ecosystem-level authority already defined by Core Vision governance.

Other future Human roles may exist.

CV-WP-006 does not yet define a multi-user role model.

## 22. Human decision actions

Candidate explicit Human decision actions include:

- APPROVE
- REJECT
- DEFER
- RETURN FOR REWORK
- REQUEST EVIDENCE
- ACCEPT EXCEPTION
- REVOKE EXCEPTION

The available actions depend on the governing case and authority domain.

These names are discovery semantics, not an API contract.

## 23. Human approval is explicit

Human approval must require a distinguishable authorized action.

Approval must not be inferred merely from:

- viewing a page
- opening a case
- reading an AI recommendation
- inactivity
- system timeout
- AI confidence
- rule PASS
- deployment success
- repository activity

Silence is not approval unless a future explicit governance rule narrowly defines such semantics.

No such rule is created here.

## 24. Human identity and authority

A future approval action must be attributable to an authenticated Human identity or equivalent explicitly governed authority representation.

Identity alone is insufficient.

The system must also determine whether that actor is authorized for the decision domain.

Authentication and authority are separate concerns.

## 25. Human decision evidence

A material Human decision should be capable of retaining:

- actor identity
- decision authority
- decision
- time
- affected governance domain
- relevant case
- rule results
- relevant evidence references
- rationale where required
- exception metadata where applicable

The concrete persistence representation remains deferred.

## 26. Human override semantics

A Human decision must not be modeled as an undocumented override button.

Where governance permits an exception, the system should represent it as an explicit governed exception.

Where no exception mechanism exists, the system must not silently turn Human UI privilege into an implicit exception mechanism.

## 27. Exception authority

An exception requires an identifiable authority capable of authorizing that exception.

An exception should identify, where material:

- governing rule
- scope
- rationale
- authorizing actor
- affected projects
- effective condition
- expiry or review condition where appropriate
- rollback or revocation condition where appropriate

Exception handling must remain explicit.

## 28. Exception versus rule deletion

Authorizing an exception does not automatically invalidate the underlying rule.

The system must distinguish:

- rule remains effective generally
- bounded exception applies to a defined case

This prevents one exception from silently becoming ecosystem-wide policy.

## 29. Exception expiry

Some exceptions may need:

- expiry
- review date
- lifecycle condition
- explicit revocation

CV-WP-006 does not require every exception to expire.

It requires that exception duration semantics be explicit where relevant.

## 30. Exception history

Historical exceptions should remain inspectable even after:

- expiry
- revocation
- replacement
- project retirement

Historical preservation does not make an expired exception currently effective.

## 31. Decision preparation flow

A candidate governance flow may be:

1. identify proposed governance action
2. resolve governing context
3. collect or reference evidence
4. identify unknowns
5. evaluate deterministic rules
6. obtain AI analysis where useful
7. prepare recommendation
8. identify Decision Owner
9. obtain explicit Human authorization where required
10. apply authorized governance effect
11. record resulting state and history

This flow is semantic.

It does not mandate a workflow engine.

## 32. Decision state separation

The system should distinguish at least:

- DRAFT
- UNDER REVIEW
- BLOCKED
- READY FOR DECISION
- APPROVED
- REJECTED
- DEFERRED
- SUPERSEDED

These are discovery-level case or decision states.

They must not be confused with project lifecycle states.

## 33. Proposed effect versus effective state

A proposed governance change and an effective governance change are separate.

Example:

A proposal may request:

> Admit Project X.

Before authorization, portfolio state remains unchanged.

Only an authorized decision may produce the effective portfolio change.

The proposal must not become canonical state merely because it exists in the same database.

## 34. Decision effect validation

Before applying an authorized effect, the system may need to verify:

- authorization still valid
- relevant blocking rule has not changed
- required state has not materially changed
- target object still exists
- concurrent decision has not superseded the proposal

The exact concurrency mechanism remains deferred.

## 35. Time-of-check versus time-of-effect

A governance case may be reviewed over time.

Evidence or canonical state may change between:

- analysis
- approval
- effect application

Future architecture must consider whether authority-critical decisions require revalidation immediately before effect.

This is a semantic requirement discovery.

It does not yet select transaction technology.

## 36. Stale approval context

An approval based on materially stale context must not silently apply as though nothing changed.

Possible future behavior may include:

- revalidation
- return to review
- explicit Human reconfirmation
- fail closed

The exact policy depends on the decision domain.

## 37. Decision Owner resolution

Decision Owner resolution must occur before a binding decision is applied.

If Decision Owner is materially ambiguous:

- AI may identify candidate owners
- deterministic rules may identify the ambiguity
- the case may be blocked

The software must not choose an owner merely because one project initiated the case.

## 38. Cross-project decisions

A cross-project governance case may involve many participants.

Participation does not create shared authority automatically.

The system must distinguish:

- evidence provider
- consulted project
- affected project
- contract owner
- domain authority
- Decision Owner
- Human authorizer

These roles may overlap.

They must not be collapsed by default.

## 39. Consultation

Consultation may collect:

- comments
- objections
- evidence
- compatibility concerns
- risk assessments
- implementation implications

Consultation does not equal approval authority.

A consulted participant does not receive a veto unless the participant owns the affected authority domain or an explicit governance rule grants that veto.

## 40. AI in consultation

AI may summarize consultation input.

AI must preserve material disagreement.

AI must not manufacture consensus by suppressing conflicting evidence or minority positions that materially affect governance.

## 41. Automated low-risk actions

Future architecture may identify non-authoritative or reversible actions suitable for automation.

Examples may include:

- refreshing a projection
- recalculating a derived indicator
- checking rule consistency
- collecting public metadata
- preparing a draft case
- notifying about unresolved evidence

Automation of such actions does not imply authority to approve the resulting governance effect.

## 42. Irreversible actions

Actions with irreversible or ecosystem-wide authority consequences require the Human authority defined by governance.

Examples include:

- permanent portfolio admission
- permanent authority reassignment
- new Core-wide mandatory dependency
- new universal trust assumption
- irreversible architecture-principle exception
- expansion of AI autonomy into binding decision authority

AI must not independently authorize these actions.

## 43. Canonical state write boundary

Canonical Core Vision governance state should have an explicit mutation boundary.

A future architecture should not allow arbitrary components to write authoritative state simply because they can access persistence.

Candidate mutation sources may conceptually include:

- validated authorized Human decision
- deterministic application of an already-authorized non-discretionary rule
- bounded administrative maintenance explicitly authorized by governance

The final mutation architecture remains deferred.

## 44. Deterministic non-discretionary effects

Some future governance effects may be fully determined by already-authorized rules.

Example concept:

If an explicitly governed temporary exception reaches its defined expiry condition, the system may be able to mark that exception no longer effective without a fresh discretionary Human decision.

Such automation is only valid when:

- the rule is explicit
- the effect is non-discretionary
- the authority basis is already established
- audit history is preserved

CV-WP-006 does not authorize any specific automated mutation yet.

## 45. AI write separation

AI-generated content may be stored as:

- draft
- analysis
- recommendation
- rationale proposal
- classification proposal

It must remain distinguishable from canonical authorized state.

AI should not require direct unrestricted write access to canonical governance storage.

## 46. Rule write separation

Rule definitions themselves are governance-sensitive artifacts.

The ability to execute a rule must remain distinguishable from the ability to:

- create a rule
- modify a rule
- activate a rule
- retire a rule

A future rule-management process must preserve authority over rule lifecycle.

## 47. Rule activation

A newly authored rule must not become binding merely because it exists in storage.

Binding activation requires the appropriate governance authority.

The architecture should therefore distinguish:

- draft rule
- reviewed rule
- active rule
- retired rule

This remains conceptual discovery.

## 48. AI-generated rule proposals

AI may propose:

- candidate rules
- consistency checks
- new invariant expressions
- refactoring of existing rule language

AI-generated rules are proposals.

They do not become binding until explicitly governed and activated.

## 49. Explainability layers

Future Core Vision should distinguish explanations from authority.

A decision view may need to show:

- source evidence
- deterministic results
- AI analysis
- recommendation
- Human decision
- resulting state effect

This layered explanation helps prevent one reasoning source from impersonating another.

## 50. Audit chain

A material effective governance change should be reconstructable conceptually through a chain such as:

evidence
→ rule evaluation
→ analysis
→ recommendation
→ authorization
→ state effect
→ history

Not every decision requires every step.

The system should preserve whichever steps were materially relevant.

## 51. Failure behavior

If AI fails:

- deterministic rules remain usable
- Human governance remains usable

If deterministic rule evaluation fails unexpectedly:

- AI must not fabricate a PASS
- authority-critical effects should fail closed where required

If evidence integration fails:

- missing evidence remains missing or unknown

If the UI fails:

- canonical governance state must not be lost

If Core Vision software is unavailable:

- other Core projects must remain able to perform their independently authorized standalone roles.

## 52. Security implications

The future architecture must ensure that:

- AI identity is not Human identity
- service identity is not Human approval
- read access is not write access
- write access is not approval authority
- administrative access is not automatically governance authority
- database access is not automatically decision authority

Concrete identity and authorization technology remains deferred.

## 53. No AI super-authority

AI must not become a super-authority by being positioned between every governance operation and the underlying model.

Core Vision must remain usable when AI is absent.

Canonical governance semantics must be represented explicitly enough that they do not depend on one model's hidden reasoning.

## 54. No rule-engine super-authority

A rule engine must not become the source of governance simply because it executes rules.

The authority source remains the accepted governance rule and its legitimate owner.

The rule engine is an enforcement and evaluation mechanism.

It is not an independent governance institution.

## 55. No Human UI super-authority

A privileged UI account must not automatically be capable of violating every governance constraint without explicit exception semantics.

Human authority must remain domain-aware and auditable.

Human Maintainer authority remains binding where already established, but its exercise should be explicit rather than hidden inside technical privilege.

## 56. Architecture implications

Later architecture-option comparison should favor designs that make the following boundaries explicit:

- evidence versus canonical state
- rule result versus decision
- AI output versus authorized state
- proposed effect versus effective state
- Human identity versus Human authority
- exception versus rule deletion
- current state versus historical record

A design that obscures these distinctions creates governance risk.

## 57. Discovery conclusion

Future Core Vision software should combine three forms of governance support:

### Deterministic enforcement

For already-authorized rules that can be evaluated predictably.

### AI-assisted reasoning

For contextual interpretation, comparison and recommendation.

### Explicit Human authority

For discretionary or governance-defined decisions requiring authorized Human judgment.

These layers complement one another.

They must not impersonate one another.

Deterministic rules must not invent policy.

AI must not invent authority.

Technical privilege must not silently become governance authority.

Authorized Human decisions must remain explicit and auditable.
