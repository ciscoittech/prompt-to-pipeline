# Skill Progression Map — From Prompts to Pipelines (v3)

## Component Introduction Schedule

One component per chapter. Never introduce two in one chapter.

| Chapter | New Component | Primary System | Reader Can Now... |
|---------|--------------|---------------|-------------------|
| 1 | (none) | — | Name the 4 concepts and the failure each prevents |
| 2 | (none) | — | Push each concept manually, feel why it doesn't scale |
| 3 | (none) | — | Design a system on paper with 3 patterns |
| 4 | **Prompt** | Study | Write structured prompts in the CLI, get targeted results |
| 5 | **State** | Job Hunting | Build a system that remembers across sessions |
| 6 | (deepening) | Meal Planner | Apply Prompt + State in a new domain, prove transfer |
| 7 | **Skill** | Content | Load expertise that persists across tasks |
| 8 | **Hook** | Job Hunting | Build automated checks that catch mistakes |
| 9 | (integration) | Job Hunting | Combine 4 components into a real working system |
| 10 | **Connection** | Study | Pull live external data into the system |
| 11 | **Pipeline** | Content | Build multi-stage workflows with quality gates |
| 12 | (debugging) | All | Diagnose failures by component, fix without adding complexity |
| 13 | (composition) | All | Wire multiple systems together with shared state and skills |

## 4 Throughline Systems — Growth Across Chapters

| Chapter | Study | Job Hunting | Project Mgmt | Content |
|---------|-------|-------------|--------------|---------|
| 1-3 | "before" prompt | "before" prompt | "before" prompt | "before" prompt |
| 4 | **v1: prompt (deep)** | v1: prompt | v1: prompt | v1: prompt |
| 5 | v2: + state | **v2: + state (deep)** | v2: + state | v2: + state |
| 6 | — | — | — | — (Meal Planner gets deep) |
| 7 | v3: + skill | v3: + skill | v3: + skill | **v3: + skill (deep)** |
| 8 | v4: + hook | **v4: + hook (deep)** | v4: + hook | v4: + hook |
| 9 | — | **integration (deep)** | — | — |
| 10 | **v5: + connection (deep)** | v5: + connection | v5: + connection | v5: + connection |
| 11 | v6: + pipeline | v6: + pipeline | v6: + pipeline | **v6: + pipeline (deep)** |
| 12-13 | debugged + composed | debugged + composed | debugged + composed | debugged + composed |

**(deep)** = primary build with full walkthrough. Others get shorter "extend it" treatment.

## Difficulty Ramp

| Level | Chapters | What's New | Reader Handles |
|-------|----------|-----------|---------------|
| Conceptual | 1-3 | 4 concepts, 3 patterns, design on paper | Exercises in any AI tool |
| ★☆☆☆☆ | 4 | CLI + first structured prompt | Open terminal, create a file, run a prompt |
| ★★☆☆☆ | 5-6 | State files | Read/write a tracking file across sessions |
| ★★★☆☆ | 7-8 | Skills + hooks | Create knowledge docs and validation scripts |
| ★★★★☆ | 9-11 | Integration + connections + pipelines | Design multi-stage flows with external data |
| ★★★★★ | 12-13 | Debugging + composition | Wire multiple systems, diagnose cross-component failures |

## Concept Ramp

| Part | Concepts | Reader Learns |
|------|---------|---------------|
| Act 1 (I) | 4 universal concepts + 3 patterns | Systems thinking — tool-agnostic |
| Act 2 (II) | Instruction + Memory | Structured prompts + persistent state |
| Act 2 (III) | Instruction (advanced) + Control | Loaded expertise + automated guard rails |
| Act 2 (IV) | Flow (external + staged) | External data + multi-stage pipelines |
| Act 2 (V) | All combined | Debugging + system composition |

## Maintenance Teaching Schedule

Maintenance is taught per-component, not deferred:

| Chapter | Maintenance Topic |
|---------|------------------|
| 5 | State hygiene — when to archive, keeping active state lean |
| 7 | Skill versioning — note what changed, roll back if worse |
| 8 | Hook tuning — thresholds, false positives, calibration |
| 10 | Connection health — check sources still work, handle failures |
| 11 | Pipeline bottlenecks — find the slowest stage, fix that one |
| 12 | Debugging protocol (NOT maintenance — fixing what breaks) |
