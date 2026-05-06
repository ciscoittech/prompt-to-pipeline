# Production Systems

Three real systems the author built and uses in production. Each one demonstrates the book's 6-component framework at different scales. They're genericized here to remove proprietary details — the architecture, patterns, and scale are real.

## How They Map to the Book

| System | Book Throughline | Components Used | Scale |
|--------|-----------------|----------------|-------|
| [Study System](study-system/) | Study (Ch 4-5, 10) | Prompt, State, Skill, Hook, Connection | 127 items, 21 columns, active quiz data |
| [Work System](work-system/) | Project Management (Ch 7-9) | All 6 | 15 agents, 15 skills, 80K+ docs |
| [Content System](content-system/) | Content (Ch 7, 9, 11) | Prompt, State, Skill, Hook, Pipeline | 7-stage pipeline, 26 posts tracked |

## Component Coverage

| Component | Study | Work | Content |
|-----------|-------|------|---------|
| **Prompt** | Structured quiz generation | Per-command entry points | 7-stage pipeline prompts |
| **State** | CSV with 21 columns per item | Per-context project files | Post tracker + editorial calendar |
| **Skill** | 344-line study-tracker skill | 15 domain skills (up to 518 lines each) | 5 skills (voice, platform-specific) |
| **Hook** | Keyword detection, observability tracing | File protection, security checks | Quality gates (24/30 minimum) |
| **Connection** | Web search for current resources | MCP/RAG with 80K+ doc chunks | Web scraping + engagement analysis |
| **Pipeline** | Quiz → Score → Update → Gap detect → Plan | Methodology-driven workflows (5-step) | 7-stage: Discovery → Research → Draft → Review → Polish → Distribute |

## What's Genericized

- **Removed**: Customer names, API keys, proprietary business logic, personal details
- **Kept**: Architecture diagrams, component counts, file structures, workflow patterns, real metrics
- **Renamed**: Domain-specific terms replaced with generic equivalents (e.g., "CUCM" → "domain platform")

The point isn't to share our exact systems. It's to prove that the concepts in this book work at production scale — not just in tutorials.
