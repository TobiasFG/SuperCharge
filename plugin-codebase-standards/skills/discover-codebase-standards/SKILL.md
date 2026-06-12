---
name: discover-codebase-standards
description: Discover, document, and persist this repository's coding standards, architecture, tooling, and workflows into a project-local `codebase-standards` skill. Use when the user asks to "discover codebase standards", "audit repository conventions", "document repo standards", or initializes standards for a new project.
---

# Discover codebase standards

Entry point for the codebase-standards discovery workflow. Bootstraps a project-local `codebase-standards` skill at `<project-root>/.claude/skills/codebase-standards/`, then populates its `references/` from observed patterns.

## When to use

- User explicitly requests standards discovery for the current repo.
- Project has no existing `.claude/skills/codebase-standards/` skill, or user wants to refresh it.

## Workflow

Delegate to the `orchestrator` subagent. The orchestrator handles:

1. Bootstrap project-local skill by copying `<plugin>/src/codebase-standards/` into `<project-root>/.claude/skills/codebase-standards/`.
2. Run prerequisite questionnaire to capture high-level context.
3. Fan out `discoverer` subagents per category/topic to observe patterns.
4. Fan out `persister` subagents to write findings into `<project-root>/.claude/skills/codebase-standards/references/[category]/[topic].md`.
5. Tear down temporary working directory.

Spawn the orchestrator and pass the user's invocation verbatim. Do not run discovery inline on the main thread.

## Notes

- Discovery is observational only — record what exists, do not invent standards.
- Workflow is idempotent: re-running refreshes references without destroying the skill scaffold.
