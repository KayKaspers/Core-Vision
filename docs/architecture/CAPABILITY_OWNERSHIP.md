# Core Ecosystem Capability Ownership

**Status:** Foundation Draft

## Purpose

This document assigns primary ownership for ecosystem capability domains.

Primary ownership defines responsibility.

It does not create unrestricted authority over cooperating projects.

## Capability matrix

| Capability | Primary Owner | Typical Partners / Consumers |
|---|---|---|
| Ecosystem strategy | Core Vision | All Core projects |
| Portfolio governance | Core Vision | All Core projects |
| Cross-project architecture | Core Vision | All Core projects |
| Capability-boundary governance | Core Vision | All Core projects |
| Technology radar | Core Vision | All Core projects |
| Strategic roadmap alignment | Core Vision | All Core projects |
| Development governance | NDF | Software projects |
| Work-package governance | NDF | NDF-governed projects |
| ADR, Decision and Risk method | NDF | NDF-governed projects |
| Release-governance method | NDF | Core-Dev, products |
| Lessons Learned process | NDF | NDF-governed projects |
| Knowledge/evidence record provenance | Core Brain | Authorized consumers; source-domain authority remains external |
| Knowledge retrieval | Core Brain | Authorized consumers |
| Context construction | Core Brain | Authorized consumers |
| Evidence conflict detection | Core Brain | Authorized consumers |
| Design-system foundation | CDS | Core projects where adopted |
| Brand and identity foundation | CDS | Core projects where adopted |
| Experience and interaction foundation | CDS | Core projects where adopted |
| Foundations and tokens | CDS | Core projects where adopted |
| Components and patterns | CDS | Core projects where adopted |
| Channels and communication design | CDS | Core projects where adopted |
| Engineering orchestration | Core-Dev | Human Maintainer, developers |
| Development cockpit | Core-Dev | Human Maintainer |
| Development health | Core-Dev | Engineering workflows |
| Test readiness | Core-Dev | Engineering workflows |
| Build readiness | Core-Dev | Engineering workflows |
| Release readiness | Core-Dev | Human Maintainer, CoreOps |
| Infrastructure discovery | CoreOps | Operators, strategic summaries |
| Runtime inventory | CoreOps | Operators |
| Operational Source of Truth | CoreOps | Operators, authorized strategic consumers |
| Operational evidence and field provenance | CoreOps | Operators, authorized evidence consumers |
| Deployment execution | CoreOps | Authorized deployment workflows |
| Operational health | CoreOps | Operators, strategic summaries |
| Monitoring | CoreOps | Operators |
| Recovery | CoreOps | Operators |
| Runtime automation | CoreOps | Operators |
| Product functionality | Individual product | Product users |
| Product domain data | Individual product | Explicitly authorized integrations |

## Ownership rules

When projects cooperate:

1. one domain retains a primary owner;
2. supporting projects provide capabilities or evidence;
3. data access does not transfer authority;
4. integration does not create unrestricted shared ownership;
5. Human Maintainer authority remains binding where required.

## Release and deployment example

NDF defines release-governance methodology.

Core-Dev evaluates engineering and release readiness.

The Human Maintainer authorizes binding release or deployment actions.

CoreOps performs and operates production deployment where applicable.

These responsibilities must remain distinguishable.

## Boundary rule

Core-Dev determines whether software is ready to be deployed.

CoreOps performs and operates runtime deployment.

Neither role replaces the other.
