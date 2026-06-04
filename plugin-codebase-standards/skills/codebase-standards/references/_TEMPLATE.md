# Reference File Template

Use this structure for files persisted into `references/[category]/` folders.

```markdown
---
category: [folder-name, e.g., security-and-privacy]
---

# [Topic Name]

[1-2 sentence overview of what this covers]

## [Section Heading]

[Clear explanation of the standard, pattern, or finding]

### Context
Why this matters or what problem it solves.

### Examples
Code snippets, configuration examples, or concrete instances.

### Scope
Where/when this applies:
- Applies everywhere
- Specific to [module/layer/context]
- For [certain types of code]
- Exceptions or special cases

## Related

- [Other Reference](../other-category/other-file.md) — how this connects
- [External Link](https://example.com) — additional context

## Status

- [x] Discovered
- [ ] Validated with team
- [ ] Examples added
```

## Guidelines

- **Keep it discoverable:** Use clear headings that make content searchable
- **Multiple sections OK:** Break complex topics into subsections
- **Link broadly:** Cross-reference related findings in other categories
- **Note uncertainty:** Mark TODOs or incomplete findings explicitly
- **Include examples:** Code snippets, configuration, real instances from repo
- **Document scope:** Be clear where this applies and where it doesn't
- **Frontmatter:** category field helps persister track which folder it was routed to
