# Core Ecosystem Authority Matrix

**Status:** Foundation Draft

## Purpose

Authority defines which project or human authority may make or enforce binding decisions in a domain.

Possession of information does not imply authority over its source domain.

## Authority matrix

| Domain | Authoritative Owner | Non-Authority Principle |
|---|---|---|
| Ecosystem strategy | Core Vision | NDF, Core Brain, Core-Dev and CoreOps do not own ecosystem strategy |
| Portfolio membership | Core Vision / Human Maintainer | Repository existence alone grants no membership |
| Cross-project architecture | Core Vision | Individual projects do not unilaterally redefine ecosystem boundaries |
| Development governance | NDF | Core Vision does not replace NDF workflow governance |
| Project implementation | Individual project | Ecosystem governance does not imply implementation ownership |
| Knowledge/evidence record provenance | Core Brain | Underlying source-domain authority remains with the source owner |
| Knowledge retrieval | Core Brain | Consumers remain responsible for domain decisions |
| Design-system normative artifacts | CDS | Authority applies only to accepted CDS artifacts within their defined design-system scope |
| Document presentation design | CDS where explicitly accepted | Presentation authority does not imply document-domain semantic or schema authority |
| Engineering readiness | Core-Dev | CoreOps does not determine development readiness |
| Production deployment | CoreOps with Human authorization | Core-Dev does not replace operations |
| Runtime operational state | CoreOps | Core Brain may store evidence but is not operational authority |
| Operational evidence and field provenance | CoreOps | Evidence replication does not transfer operational authority |
| Product behavior | Individual product | Other Core systems do not silently control product behavior |
| Product domain data | Individual product | Access requires explicit authorization |
| CDF permanent portfolio admission | Core Vision / Human Maintainer | CDF cannot self-authorize permanent admission |

## Human Maintainer authority

The Human Maintainer remains binding authority for:

- commits
- pushes
- tags
- releases
- irreversible ecosystem decisions
- permanent portfolio admission
- authority transfer
- security-sensitive trust grants

AI systems may:

- analyze
- compare
- retrieve evidence
- recommend
- prepare changes

AI participation does not grant irreversible ecosystem authority.

## Authority preservation

A project may observe another domain without becoming authoritative over that domain.

Examples:

- Core Brain may retain evidence from CoreOps.
- Core Vision may consume strategic summaries from CoreOps.
- Core-Dev may consume NDF governance rules.
- CoreOps may consume release-ready artifacts from Core-Dev.

In every case, the original domain authority remains preserved.

## Strategic information boundary

Core Vision may consume information such as:

- project health summaries
- milestone status
- strategic risks
- release status
- aggregate operational indicators

Core Vision should not require unrestricted access to:

- raw secrets
- operational credentials
- unrelated private product data
- unrestricted infrastructure internals

Strategic governance should consume the minimum information required for its authority domain.

## Core rule

Knowledge can be centralized, authority not.
