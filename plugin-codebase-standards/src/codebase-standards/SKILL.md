---
name: codebase-standards
description: describes repo standards, design patterns, tooling, and development workflows. use when writing, reviewing, refactoring, or answering questions about code in this codebase.
---

# Codebase standards

Apply repo standards while working in this codebase. Treat the persisted standards docs as the source of truth.

## Workflow

1. Determine which reference files in `references/` are relevant to the task.
2. Read only the relevant reference files.
3. Apply repo standards over generic best practices.
4. If relevant standards are missing, stale, or unclear, stop work and ask over making assumptions.

## References

### `references/architecture/`
file placement, module boundaries, dependency direction, layering

### `references/contracts-and-types/`
models, DTOs, schemas, validation, parsing, type safety

### `references/data-access/`
databases, repositories, queries, transactions, migrations

### `references/delivery-and-operations/`
CI/CD, deployments, background jobs, scheduled tasks, runbooks

### `references/documentation-and-maintenance/`
naming, docs, examples, deprecation, maintainability

### `references/domain-and-business-rules/`
business concepts, domain terminology, workflows, invariants, permissions, state transitions, calculations, product rules, customer-specific behavior, compliance-driven business logic

### `references/errors-and-observability/`
exceptions, error mapping, logging, metrics, tracing

### `references/external-communication/`
HTTP calls, API clients, integrations, retries, timeouts

### `references/frontend/`
components, UI state, forms, accessibility, client-side patterns

### `references/performance-and-scalability/`
caching, batching, pagination, concurrency, resource usage

### `references/runtime-and-configuration/`
environment variables, config loading, secrets access, feature flags, app startup behavior, local/dev/test/prod differences, service discovery, runtime toggles, dependency injection setup, build-time vs runtime settings

### `references/security-and-privacy/`
auth, secrets, PII, input safety, secure coding

### `references/testing-and-quality/`
tests, mocks, fixtures, review checklists, quality gates