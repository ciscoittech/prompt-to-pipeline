# Chapter Dependency Graph — From Prompts to Pipelines (v3)

## Dependency Tree

```
Act 1 (tool-agnostic):
  Ch 1 (4 concepts + Sessions 1-2)
    └── Ch 2 (concepts deep + Sessions 3-5)
         └── Ch 3 (3 patterns + napkin sketch)

Act 2 (CLI-demonstrated):
  Part II — First Builds:
    Ch 3 ──► Ch 4 (Prompt — Study System deep build)
               └── Ch 5 (State — Job Hunting deep build)
                    └── Ch 6 (deepening — Meal Planner)

  Part III — Knowledge & Guard Rails:
    Ch 6 ──► Ch 7 (Skill — Content System deep build)
               └── Ch 8 (Hook — Job Hunting deep build)
                    └── Ch 9 (integration — Job Hunting full system)

  Part IV — Connections & Pipelines:
    Ch 9 ──► Ch 10 (Connection — Study System deep build)
               └── Ch 11 (Pipeline — Content System deep build)

  Part V — Mastery:
    Ch 11 ──► Ch 12 (Debugging — all 4 systems)
                └── Ch 13 (Composition — personal AI OS)
```

## Hard Dependencies

| Chapter | Requires | Why |
|---------|----------|-----|
| 4 | Ch 1-3 | First CLI build — needs all Act 1 concepts + patterns |
| 5 | Ch 4 | State needs structured prompt skills established |
| 7 | Ch 5-6 | Skill needs state context (loads alongside state) |
| 8 | Ch 7 | Hook validates against skills — can't have hooks without loaded knowledge |
| 10 | Ch 8-9 | Connection needs all 4 prior components working together |
| 11 | Ch 10 | Pipeline stages use connections for live data |
| 13 | Ch 11-12 | Composition needs all 6 components + debugging knowledge |

## Drafting Order

Strict sequential — each chapter depends on the previous:
1. Ch 1 → 2 → 3 (Act 1) ✅ DONE
2. Ch 4 → 5 → 6 (Part II: First Builds)
3. Ch 7 → 8 → 9 (Part III: Knowledge & Guard Rails)
4. Ch 10 → 11 (Part IV: Connections & Pipelines) — **MCP research required before Ch 10**
5. Ch 12 → 13 (Part V: Mastery)

## Cross-Reference Rules

### Allowed
- Reference any prior chapter's system: "The Study System from Ch 4 — we're adding state to it"
- Reference prior components with brief reminder: "You already know state files. Skills are the same idea for knowledge instead of memory."
- Brief forward teasers for motivation: "In Ch 8, you'll add automated checks" — but don't teach how

### Forbidden
- Never reference a higher chapter's CONTENT
- Never introduce a component before its chapter
- Never use a component in an example before the reader has built it
- Never say "we'll cover this later" as a crutch for incomplete explanation

### Act 1 → Act 2 References
- Act 1 can tease Act 2 tools briefly ("In Act 2, you'll build this for real")
- Act 2 should reference Act 1 sessions: "Remember Session 3 where you typed your weak areas by hand? That's what this state file replaces."
- Act 2 should reference Act 1 patterns: "This is the Loop pattern from Chapter 3 — but now the system runs it, not you."
