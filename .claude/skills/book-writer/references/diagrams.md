# Diagram System — From Prompts to Pipelines (v3)

## How Diagrams Work

Diagrams are written as Mermaid source files and rendered to SVG + PNG.

**Source**: `book/diagrams/src/*.mmd`
**Rendered**: `book/diagrams/svg/` (web/ebook) + `book/diagrams/png/` (print/GitHub)
**Render all**: `bash book/diagrams/render.sh`

## When to Create Diagrams

Every Act 2 chapter (Ch 4-13) gets at least one diagram showing the system at that chapter's state. Act 1 chapters have diagrams for concepts and patterns.

## What Exists (Act 1)

| File | Chapter | What It Shows |
|------|---------|---------------|
| `ch01-prompt-only.mmd` | Ch 1 | Input → Prompt → AI → Output (no feedback) |
| `ch01-four-concepts.mmd` | Ch 1 | 1 present (Instruction), 3 missing |
| `ch02-session-progression.mmd` | Ch 2 | Sessions 1→5, concept accumulation |
| `ch02-manual-overhead.mmd` | Ch 2 | YOU do 80% of the work |
| `ch02-eval-comparison.mmd` | Ch 2 | Eval data: 11/20 vs 20/20 |
| `ch03-loop.mmd` | Ch 3 | Pattern 1: Process → Check → Improve → Repeat |
| `ch03-gate.mmd` | Ch 3 | Pattern 2: Stage → Quality Check → Pass/Rework |
| `ch03-router.mmd` | Ch 3 | Pattern 3: Decision → Path A/B/C |
| `ch03-napkin-sketch.mmd` | Ch 3 | Full Study System, all 3 patterns |

## What to Build for Act 2

Each chapter needs a system diagram showing all components up to that point:

| Chapter | Diagram Shows | Components Visible |
|---------|--------------|-------------------|
| Ch 4 | Study System v1 (prompt only, CLI) | `[Prompt]` |
| Ch 5 | Job Hunting v2 (with state, feedback loop appears) | `[Prompt] + [State]` |
| Ch 6 | Meal Planner (same pattern, new domain) | `[Prompt] + [State]` |
| Ch 7 | Content System v3 (skill loads before work) | `[Prompt] + [State] + [Skill]` |
| Ch 8 | Job Hunting v4 (hook between output and save) | `[Prompt] + [State] + [Skill] + [Hook]` |
| Ch 9 | Job Hunting full (4 components, integration) | All 4 working together |
| Ch 10 | Study System v5 (external data input) | `+ [Connection]` |
| Ch 11 | Content Pipeline (multi-stage with gates) | All 6 components |
| Ch 12 | Failure taxonomy (symptom → component mapping) | Debugging flow |
| Ch 13 | Composed system (multiple systems, shared state/skills) | Meta-architecture |

## Mermaid Style Guide

- Use `flowchart TB` (top-to-bottom) for system flows
- Use `flowchart LR` (left-to-right) for simple before/after comparisons
- Color scheme:
  - Blue (`#4A90D9`) for process steps
  - Gold (`#FFC107`) for decision points (Router, Gate, Loop check)
  - Green (`#4CAF50`) for success/done/pass
  - Red (`#EF5350`) for failure/flag/block
  - Orange (`#FB8C00`) for "you" / manual effort
  - Light green/orange/red for Router intensity paths
- Label components in all caps: `MEMORY`, `CONTROL`, `GATE`, `ROUTER`, `LOOP`
- Use subgraphs for grouping (e.g., "Your Manual System" vs "What AI Does")

## Authoring Rules

1. **One primary diagram per chapter.** The system-state diagram at the end.
2. **Don't show components not yet introduced.** Ch 5 diagram has no hooks.
3. **Show feedback loops explicitly.** If state is read AND written, show both arrows.
4. **Label what's new.** Use `<-- NEW this chapter` annotations.
5. **Keep it readable.** If a diagram has more than 15 nodes, simplify.
