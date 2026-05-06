# Study System — Production Evidence

A real 18-week professional certification study system built with Claude Code. Active since May 2026. This is the system that inspired the book's Study throughline — it was built first, then the book was written to teach others how to build something like it.

## Architecture

```
[Study materials + Progress CSV]
          |
          v
    +-----------+
    | SKILL:    |  344 lines — quiz logic, CSV schema,
    | study-    |  scoring system, command definitions
    | tracker   |
    +-----+-----+
          |
    +-----+-----+
    | COMMANDS:  |  /study quiz [week]
    | 4 entry   |  /study status
    | points    |  /study plan
    |           |  /study update [description]
    +-----+-----+
          |
    +-----+-----+
    | STATE:     |  CSV file — 127 rows, 21 columns
    | curriculum |  status, quiz_score, quiz_date,
    | .csv       |  quiz_notes, gaps
    +-----+-----+
          |
    +-----+-----+
    | HOOKS:     |  skill-suggester: detects "quiz", "study",
    | 2 active  |  "curriculum" → suggests /study commands
    |           |  langfuse-trace: logs every tool call
    +-----+-----+
          |
          v
    [Quiz → Score → Update CSV → Detect Gaps → Plan Next Session → Loop]
```

## Components in Detail

### State: The CSV

The CSV is the single source of truth. 127 rows, 21 columns. Key columns:

| Column | What It Tracks |
|--------|---------------|
| `status` | NOT_STARTED → PRIORITY → IN_PROGRESS → COMPLETED / KNOWN / CLOSE / GAP / SKIP |
| `quiz_score` | KNOWN (nailed it), CLOSE (has intuition, needs vocabulary), GAP (doesn't know) |
| `quiz_date` | When last assessed |
| `quiz_notes` | Free text: "Nailed transformers. Gap: tokenization." |
| `gaps` | Comma-separated keywords: "tokenization,attention vocab,parameter count" |
| `priority` | MUST (core path) vs NICE (optional depth) |
| `deliverable` | What to build/write as proof of understanding |

The CSV carries all state across sessions. The system reads it at session start, writes after every action.

### Skill: study-tracker (344 lines)

Defines:
- **Quiz generation**: 10 questions per week (conceptual, applied, tradeoff, interview-ready)
- **Scoring system**: KNOWN/CLOSE/GAP per resource, with notes and gap extraction
- **CSV update pattern**: Python csv module (never hand-edit), strict enum enforcement
- **Progress computation**: Count by section and status, phase indicators, open gap aggregation
- **Study planning**: Priority-first sort, gap coverage weighting, time estimates

### Hook: Keyword Detection

A shell script that fires on every user prompt. Detects study-related keywords ("quiz", "study", "curriculum", "chapter", "week 3", etc.) and suggests the relevant `/study` command. The user doesn't need to memorize commands — the hook surfaces them contextually.

### Hook: Observability

Every tool call (Read CSV, Run Python, Write CSV) is logged to an external tracing service with session ID, tool name, and context. This means we can see exactly what the system did in every study session — which rows it read, which it updated, how long each step took.

## Real Evidence

**Quiz data from May 3, 2026:**
- Week 1 (AI Stack): 1 KNOWN, 2 PRIORITY, 2 SKIP — the system correctly identified what was already mastered and what to skip
- Week 2 (Foundation Models): 6 resources scored, gaps detected: tokenization, attention vocab, parameter count, top-p/top-k, test-time compute
- The gaps column now drives `/study plan` — next session focuses on resources that close those specific gaps

**What the system does that a prompt can't:**
- Session 3 doesn't re-quiz topics scored KNOWN in Session 1
- Gap detection accumulates across sessions — a concept scored CLOSE twice becomes PRIORITY
- `/study plan` sorts resources by gap coverage × time estimate — short resources that close multiple gaps rise to the top
- The CSV is a permanent record — visible in Excel with color-coded status, hyperlinked URLs, and progress dashboards

## Sample Data

See `curriculum-source.csv` in this directory for the actual curriculum data (127 rows, anonymized topic details retained for structure demonstration).
