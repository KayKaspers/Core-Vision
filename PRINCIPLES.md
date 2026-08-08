# Core Ecosystem Principles

Status: FOUNDATION DRAFT

These principles are initial architecture invariants for formal review during CV-WP-003.

## CV-P-001 — Standalone First

A separately published Core product must provide its defined core functionality without requiring optional Core ecosystem components.

Ecosystem integration must not become ecosystem lock-in.

## CV-P-002 — Public Interface First

Core-to-Core integrations should prefer stable, documented, versioned APIs, events, exports, imports, or machine interfaces that are suitable for external consumers where practical.

Internal Core products should dogfood public product interfaces.

## CV-P-003 — No Implicit First-Party Trust

A Core product does not receive automatic trust, authorization, disclosure, or security bypass privileges merely because it belongs to the Core ecosystem.

Least privilege and explicit authorization remain applicable.

## CV-P-004 — Graceful Absence

Optional ecosystem integrations must be able to be unavailable without destroying the defined standalone core functionality of the consuming product.

## CV-P-005 — No Bootstrap Cycles

Core products must not create circular mandatory dependency chains for bootstrap or basic operation.

## CV-P-006 — Authority Preservation

Knowledge, integration, aggregation, or retrieval does not implicitly transfer domain authority.

Current authority model:

- Core Vision — ecosystem strategy, portfolio and cross-project architecture
- NDF — development governance
- Core-Dev — engineering orchestration
- Core Brain — knowledge, evidence, provenance and retrieval
- CoreOps — operational and runtime authority
