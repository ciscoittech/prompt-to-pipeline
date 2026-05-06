# From Prompts to Pipelines

### A Systems-Based Approach to Prompt Engineering and Agentic Workflows

You've used AI a hundred times. Sometimes it's magic. Sometimes it's useless. You re-explain your background every session. You manually check every output. You paste the same context into a new chat window and hope for the best.

**The problem isn't the AI. The problem is you're writing prompts when you should be building systems.**

A prompt is one input. A system is the whole loop — instruction, memory, control, and flow. This book teaches you to see the system, then build it. You'll go from one-shot prompts that work once to full pipelines that run reliably, remember what happened, catch their own mistakes, and get better over time.

> *"We tested this. Same AI, same task. Vague prompt: 11 out of 20. Structured prompt: 20 out of 20. Every run."*
> — [Eval notebook with full results](research/evals/notebooks/01-prompt-structure.ipynb)

---

## What You'll Build

Four real systems that grow across the entire book. Each starts as a basic prompt and ends as a full 6-component pipeline.

| System | You Start With | You End With |
|--------|---------------|-------------|
| **Study** | "Quiz me on cloud computing" | An adaptive learning system that tracks your weak areas, adjusts difficulty, verifies its own answers, pulls live data, and plans your next session automatically |
| **Job Hunting** | "Write me a cover letter" | A career campaign system that tracks every application, tailors materials from your loaded career profile, catches fabricated details before you send, and learns which approaches get callbacks |
| **Project Management** | "Help me plan this project" | A project operations system that pulls live data from your tools, generates status updates for different audiences, flags risks, and never loses track of what's been done |
| **Content** | "Write a blog post about X" | A content pipeline that researches, drafts in your voice, fact-checks against sources, enforces quality gates, and distributes across platforms |

These aren't hypothetical. The author runs all four in production. [See the evidence.](research/systems/)

---

## What Makes This Different

**Every other AI book teaches prompts. This one teaches systems.**

Most books stop at "write better prompts." That's one component. This book teaches six:

```
PROMPT → STATE → SKILL → HOOK → CONNECTION → PIPELINE
(what you    (what it    (loaded     (automated   (live external   (multi-stage
 tell it)    remembers)   expertise)   checks)      data)            workflows)
```

Each chapter adds one component. By the end, your systems have all six working together.

**It's not tied to one tool.** The concepts work in Claude Code, OpenAI Codex, Kimi CLI, Cursor, or whatever ships next year. The tools change. The framework doesn't.

**Every claim is backed by evidence.** Not "trust me" — [here's the data](research/METHODOLOGY.md). Eval notebooks you can run yourself. Three production systems documented with real metrics. A 127-item study curriculum with actual quiz scores. A content pipeline that's produced 26 posts with quality scoring.

---

## Read It Now (Free)

**Act 1 is free.** Three chapters, ~11,000 words. You'll run 5 hands-on sessions in any AI tool and walk away understanding why your prompts break — and what to do about it.

### [Read Act 1 →](book/published/act1-beta-draft.md)

Or read chapter by chapter:

1. **[You're Already Building Systems](book/chapters/ch01-draft.md)** — The opener. You run a study quiz, get great results, then watch it forget everything. The four concepts: Instruction, Memory, Control, Flow.

2. **[Going Deeper](book/chapters/ch02-draft.md)** — You push through 3 more sessions, manually patching each concept. Each one helps. Each one breaks under its own overhead.

3. **[Design Patterns](book/chapters/ch03-draft.md)** — Loop, Gate, Router — three shapes that describe every AI system. You design yours on a napkin.

![The Study System — Napkin Sketch](book/diagrams/png/ch03-napkin-sketch.png)
*By Chapter 3, you can design a system on paper. Act 2 builds it for real.*

---

## The Evidence

This book shows its work.

| Evidence | What It Proves |
|----------|---------------|
| [Prompt Eval: 11/20 → 20/20](research/evals/notebooks/01-prompt-structure.ipynb) | Structured prompts aren't marginally better — they're categorically better |
| [Study System (production)](research/systems/study-system/) | 127 items, quiz scoring, gap detection — this is what a real state file looks like |
| [Work System (production)](research/systems/work-system/) | 15 agents, 15 skills, 80K+ reference docs — this is what skills at scale look like |
| [Content System (production)](research/systems/content-system/) | 7-stage pipeline, 26 posts, 24/30 quality gate — this is what pipelines do |
| [Evaluation Methodology](research/METHODOLOGY.md) | How we test, how we score, how to reproduce |

---

## The Framework

**4 Universal Concepts** — tool-agnostic, work everywhere:

| Concept | The Failure It Prevents |
|---------|------------------------|
| **Instruction** | "It didn't do what I wanted" |
| **Memory** | "I have to re-explain everything every time" |
| **Control** | "It gave me confident garbage" |
| **Flow** | "It tried to do everything at once" |

**6 Implementation Components** — what you build:

| Component | Chapter | What It Does |
|-----------|---------|-------------|
| Prompt | Ch 4 | Persistent project instructions (CLAUDE.md / AGENTS.md) |
| State | Ch 5 | Files that track what happened across sessions |
| Skill | Ch 6 | Reusable expertise docs loaded on demand |
| Hook | Ch 7 | Automated checks that catch mistakes |
| Connection | Ch 8 | Live data from external tools and APIs |
| Pipeline | Ch 9 | Multi-stage workflows with quality gates |

**3 Design Patterns** — how components connect:

| Pattern | When to Use It |
|---------|---------------|
| **Loop** | Output can be measured and improved (draft → review → revise) |
| **Gate** | Bad output costs more than checking it (cover letter → verify → send) |
| **Router** | Different inputs need different handling (CEO gets summary, team gets details) |

---

## Full Book Outline

| Ch | Title | What You Build |
|----|-------|---------------|
| 1 | You're Already Building Systems | Recognize the invisible manual system you're running |
| 2 | Going Deeper | Push each concept manually, feel why it breaks |
| 3 | Design Patterns | Loop, Gate, Router — design your system on a napkin |
| 4 | Structured Prompts | CLAUDE.md — the file that makes AI remember your project |
| 5 | State Files | A tracker that carries forward what happened |
| 6 | Skills | Loaded expertise — your voice, your rules, on demand |
| 7 | Hooks | Automated checks that refuse to let bad output through |
| 8 | Connections | Live data from the outside world |
| 9 | Pipelines | Multi-stage workflows with quality gates |
| 10 | When Systems Break | Every failure maps to a component — diagnose and fix |
| 11 | Composing Systems | Wire your systems together into a personal AI OS |
| 12 | Designing New Systems | Build one from scratch, for a problem the book never covered |
| 13 | What's Next | The framework outlasts every tool |

[Full detailed outline →](book/outline-v3.md)

---

## Get Involved

**Read Act 1 and tell us what you think.** Leave feedback as [GitHub Issues](../../issues) — what clicked, what confused you, what's missing.

**Run the evals yourself.** The [notebooks](research/evals/) work with any AI API (OpenRouter, OpenAI, Anthropic). See the difference between prompts and systems with your own data.

**Follow the build.** This book is being written in public. The [dev docs](dev/) show how every chapter is planned, drafted, reviewed, and scored. The production pipeline is the same systems-thinking approach the book teaches.

---

## About

Written by a network engineer who builds AI systems in production — not a researcher writing about theory. Three real systems (study, work, content) run daily and inform every chapter. The research repository contains the evidence. The eval notebooks are reproducible.

The book is CLI-demonstrated (terminal-first, because you need to see the system's parts) and interface-agnostic (same patterns work in Claude Code, Codex, Kimi CLI, Cursor, or whatever ships next).

**[Start reading →](book/published/act1-beta-draft.md)**
