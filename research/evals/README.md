# Prompt Evals

Jupyter notebooks comparing baseline prompts against the book's system approaches. Each notebook maps to a chapter and shows the measurable improvement.

## How It Works

Each notebook runs the same task two ways:
1. **Baseline**: The prompt most people would write
2. **Treatment**: The book's approach (structured prompt, state-loaded, skill-loaded, etc.)

Both outputs get scored on a simple rubric. The difference is the evidence.

## Observability

Evals are traced through **Langfuse** (our production observability platform). Every API call, every scoring decision, and every comparison is logged as a trace with:
- Session ID linking all calls in one eval run
- Input/output pairs for each prompt variant
- Rubric scores as observation metadata
- Cost tracking per eval

This means eval results are auditable — you can inspect exactly what was sent, what came back, and how it was scored.

## Prerequisites

```bash
pip install openai anthropic langfuse pandas jupyter
```

## API Setup

The notebooks use a provider-agnostic wrapper. Set one of these:

```bash
# Option 1: Anthropic
export ANTHROPIC_API_KEY=your-key

# Option 2: OpenAI
export OPENAI_API_KEY=your-key

# Langfuse (for tracing)
export LANGFUSE_PUBLIC_KEY=your-key
export LANGFUSE_SECRET_KEY=your-key
export LANGFUSE_HOST=https://langfuse.your-domain.com
```

## Notebooks

| # | Notebook | Chapter | What It Tests | Status |
|---|---------|---------|---------------|--------|
| 00 | [setup](notebooks/00-setup.ipynb) | — | API wrapper, helpers, Langfuse tracing | TODO |
| 01 | [prompt-structure](notebooks/01-prompt-structure.ipynb) | Ch 4 | Basic vs structured prompt | TODO |
| 02 | [state-impact](notebooks/02-state-impact.ipynb) | Ch 5 | With/without state across sessions | TODO |
| 03 | [skill-loading](notebooks/03-skill-loading.ipynb) | Ch 7 | With/without voice skill | TODO |
| 04 | [hook-detection](notebooks/04-hook-detection.ipynb) | Ch 8 | Error catch rate with hooks | TODO |
| 05 | [pipeline-vs-oneshot](notebooks/05-pipeline-vs-oneshot.ipynb) | Ch 11 | Multi-stage vs single prompt | TODO |

## Estimated Cost

Under $5 total to run all notebooks. Each notebook makes 5-15 API calls. The setup notebook includes a cost estimator.

## Extending

To add a new eval:
1. Copy any existing notebook as a template
2. Define: hypothesis, task, baseline, treatment, rubric
3. Use the `run_comparison()` helper from `00-setup.ipynb`
4. Langfuse tracing is automatic via the helper functions
