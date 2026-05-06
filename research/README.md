# Research & Evaluation

This section backs up every claim in the book with evidence. If a chapter says "structured prompts produce better output," there's a notebook here that shows the before and after. If a chapter says "state files improve multi-session work," there's a production system here that proves it.

## What's Here

### [Methodology](METHODOLOGY.md)
How we evaluate prompts and systems. Short and practical — not an academic paper.

### [Prompt Evals](evals/)
Jupyter notebooks comparing baseline prompts against the book's approaches. Each notebook maps to a specific chapter and shows the measurable improvement.

| Notebook | Book Chapter | What It Tests |
|----------|-------------|---------------|
| [00-setup](evals/notebooks/00-setup.ipynb) | — | API wrapper, helpers, rubric scoring |
| [01-prompt-structure](evals/notebooks/01-prompt-structure.ipynb) | Ch 4 | Basic vs structured prompts |
| [02-state-impact](evals/notebooks/02-state-impact.ipynb) | Ch 5 | With/without state across sessions |
| [03-skill-loading](evals/notebooks/03-skill-loading.ipynb) | Ch 7 | With/without voice skill loaded |
| [04-hook-detection](evals/notebooks/04-hook-detection.ipynb) | Ch 8 | Error catch rate with automated checks |
| [05-pipeline-vs-oneshot](evals/notebooks/05-pipeline-vs-oneshot.ipynb) | Ch 11 | Multi-stage pipeline vs single prompt |

### [Production Systems](systems/)
Three real systems the author built and uses in production. Each one maps to the book's throughline systems and demonstrates the 6-component framework at scale.

| System | Book Throughline | Key Evidence |
|--------|-----------------|-------------|
| [Study System](systems/study-system/) | Study | 127-item curriculum, quiz scoring, gap tracking, adaptive sessions |
| [Work System](systems/work-system/) | Project Management | 15 agents, 15 skills, 80K+ doc RAG, per-context configuration |
| [Content System](systems/content-system/) | Content | 7-stage pipeline, quality gates, 26 published posts tracked |

## How to Use This

**If you're a reader**: Run the notebooks to verify the book's claims yourself. Swap in your own topic and see the difference.

**If you're a critic**: Every chapter claim maps to evidence here. The methodology doc explains how we measured, and the notebooks are reproducible.

**If you're building on this**: The notebooks are a starting point. Fork them, change the prompts, try different rubrics. The framework is designed to be extended.
