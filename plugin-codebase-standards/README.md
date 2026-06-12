# codebase-standards

Auto-discover and apply repo-specific coding standards, design patterns, tooling, and workflows.

## What it does

Run `discover-codebase-standards` (e.g. "discover codebase standards") and the plugin:

1. Bootstraps a project-local skill at `<project-root>/.claude/skills/codebase-standards/`.
2. Asks a short questionnaire about the repo.
3. Fans out `discoverer` subagents (one per category/topic) to observe patterns.
4. Fans out `persister` subagents to write clean reference docs under `references/`.
5. Tears down its temporary working directory.

## Permissions (required)

The `discoverer` and `persister` subagents run with `background: true`. Background
subagents **auto-deny any tool call that would otherwise prompt** — so without a
pre-approval rule their `Write`/`Edit` calls fail silently and discovery produces no
files. This is a permission-prompt fallback, **not** a sandbox.

To avoid this, the plugin ships a `settings.json` at its root that pre-approves writes
to the two directories the workflow owns:

```json
{
  "permissions": {
    "allow": [
      "Write(.claude/skills/codebase-standards/**)",
      "Edit(.claude/skills/codebase-standards/**)",
      "Write(.temp-codebase-standards/**)",
      "Edit(.temp-codebase-standards/**)"
    ]
  }
}
```

These rules are scoped to the plugin's own output paths (relative to the project root),
so they grant nothing beyond what discovery needs and require no per-repo editing.

### If discovery still writes nothing

If your Claude Code version does not apply a plugin's bundled `settings.json`
permissions, add the same four rules to the consuming repo's
`.claude/settings.local.json` once:

```json
{
  "permissions": {
    "allow": [
      "Write(.claude/skills/codebase-standards/**)",
      "Edit(.claude/skills/codebase-standards/**)",
      "Write(.temp-codebase-standards/**)",
      "Edit(.temp-codebase-standards/**)"
    ]
  }
}
```

The orchestrator runs `background: false`, so directory creation and teardown surface
interactive prompts normally and need no extra rules.

## Layout

- `agents/orchestrator.md` — foreground coordinator; bootstraps, runs the questionnaire, routes findings, tears down.
- `agents/discoverer.md` — observes patterns for one category/topic, writes findings to the temp dir.
- `agents/persister.md` — rewrites findings into a clean reference doc under `references/`.
- `skills/discover-codebase-standards/` — entry-point skill.
- `src/codebase-standards/` — the project-local skill scaffold copied into consuming repos.
