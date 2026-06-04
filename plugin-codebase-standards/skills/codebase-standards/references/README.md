# Reference Documentation Structure

This directory contains discovered and documented codebase standards, patterns, and conventions.

## How It's Organized

Each subdirectory represents a category of standards:

```
references/
├── architecture/                        — code organization, layering, modularity
├── contracts-and-types/                 — data structures, APIs, validation
├── data-access/                         — databases, queries, persistence
├── delivery-and-operations/              — CI/CD, deployments, operations
├── documentation-and-maintenance/        — naming, docs, maintainability
├── domain-and-business-rules/           — business logic, workflows, invariants
├── errors-and-observability/            — errors, logging, metrics, tracing
├── external-communication/              — HTTP calls, API clients, integrations
├── frontend/                            — UI components, state management
├── performance-and-scalability/         — caching, batching, concurrency
├── runtime-and-configuration/           — environment, config, secrets, startup
├── security-and-privacy/                — auth, authorization, secrets, PII
└── testing-and-quality/                 — tests, mocks, quality gates
```

Within each category, create topic-specific files like:
- `authentication-and-authorization.md`
- `error-handling.md`
- `module-boundaries.md`

See [_TEMPLATE.md](_TEMPLATE.md) for file format.

## How Files Get Here

Use the [Discover codebase standards skill](../SKILL.md) to systematically discover patterns and conventions. When ready, send findings to the [persister agent](../../agents/persister.md), which automatically routes and files them based on [categorization logic](../discover-codebase-standards/references/categorization-guide.md).

## Using These References

When working in the codebase, use these files as the source of truth:
1. Identify which reference categories are relevant to your task
2. Read the relevant files in those categories
3. Apply discovered standards over generic best practices

See [codebase-standards skill](../SKILL.md) for workflow.

## Contributing

When you discover a new standard or find an outdated reference:
1. Document it in a discovery tool or temp file
2. Send to persister agent for routing
3. Persister creates/updates files in appropriate categories

The goal: keep living documentation that evolves as conventions change.
