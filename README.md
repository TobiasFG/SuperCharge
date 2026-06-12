# SuperCharge

A Claude Code plugin marketplace.

## Plugins

### `codebase-standards`

Auto-discover and apply repo-specific coding standards, design patterns, tooling, and workflows. Discovery fans out subagents to observe patterns across a repo, then persists findings into a project-local `codebase-standards` skill that Claude consults whenever writing or reviewing code.

## Install

Add the marketplace, then install the plugin:

```
/plugin marketplace add TobiasFG/SuperCharge
/plugin install codebase-standards@supercharge
```

## Usage

After installing, run discovery in any repo:

```
discover codebase standards
```

This bootstraps `<project-root>/.claude/skills/codebase-standards/` and populates its `references/` from observed patterns. From then on, the `codebase-standards` skill applies those standards while you work.

## Develop locally

Test the plugin without installing from the marketplace:

```
claude --plugin-dir plugin-codebase-standards
```

## License

MIT
