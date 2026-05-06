---
name: cli-researcher
description: Research AI CLI tool features, capabilities, and cross-tool patterns. Covers Claude Code, Codex, Kimi CLI, Warp, and GUI alternatives. Loaded by /research-topic command.
---

# CLI & AI Tool Researcher Skill

## Purpose

Research AI CLI tool capabilities, cross-tool patterns, and implementation details. The book is CLI-demonstrated and interface-agnostic — research must cover how features work across tools, not just one vendor.

## Research Protocol

### Source Priority
1. **Official tool docs** — Claude Code (code.claude.com), Codex (developers.openai.com), Kimi CLI (moonshotai.github.io), Warp (docs.warp.dev)
2. **Cross-tool comparisons** — articles comparing CLI tools, feature matrices
3. **Community guides with tested examples** (GitHub repos, blog posts with real output)
4. **GUI equivalents** — how the same feature works in Cowork, Cursor, VS Code
5. **Blog posts and reviews** — lowest priority, verify claims

### Research Steps

1. **Define the question** — What specific capability or feature are we researching?
2. **Check official docs first** — Search tool-specific documentation
3. **Check cross-tool compatibility** — Does this work in Claude Code AND Codex/Kimi/others?
4. **Check GUI equivalents** — How does this work in Cowork, Cursor, VS Code?
5. **Synthesize** — Write structured notes in `research/synthesized/`
6. **Date everything** — AI tools change fast; every claim gets a source date
7. **Tag portability** — Mark each finding as [PORTABLE] (works across tools) or [TOOL-SPECIFIC]

### Output Format

Write synthesized research to `research/synthesized/{topic}.md`:

```markdown
# [Topic Name]

**Researched**: [YYYY-MM-DD]
**Sources**: [list of URLs checked]

## What It Is
[Plain-language explanation — as if telling the book's reader]

## How It Works
[Step-by-step, what the user sees and does]

## Best Practices
[What works well, from tested examples]

## Limitations
[What doesn't work, common failures]

## Prompts Found
[Any relevant prompts from community sources — raw, to be tested by prompt-curator]

## Open Questions
[Anything unclear or conflicting between sources]
```

### What to Track

- **Confirmed** (in official docs): Mark with [OFFICIAL]
- **Community-reported** (tested but not in docs): Mark with [COMMUNITY]
- **Unverified** (mentioned but not tested): Mark with [UNVERIFIED]

### Date Sensitivity

Cowork features change frequently. Always note:
- When the source was published
- Whether the feature might have changed since
- If the UI described matches current Cowork UI

## References

| File | Contents |
|------|----------|
| `references/anthropic-docs.md` | Key Anthropic documentation links |
| `references/community.md` | Community resources inventory |
