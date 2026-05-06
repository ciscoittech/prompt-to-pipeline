# Evaluation Methodology

## Why We Evaluate

Every AI book makes claims. "Better prompts get better results." "Systems outperform one-shots." This book is no different — except we show our work.

This research section exists so that when someone asks "does this actually work?", the answer isn't "trust me" — it's "here's the notebook, run it yourself."

## Three Types of Evidence

### 1. Comparative Evals (Jupyter Notebooks)

Each notebook tests one claim from the book by running the same task two ways:

- **Baseline**: The approach most people use (vague prompt, no context, no checks)
- **Treatment**: The book's approach (structured prompt, state file, skill loaded, hooks, pipeline)

Both outputs get scored on a simple rubric (1-5 per dimension). The difference is the evidence.

The notebooks are provider-agnostic — they work with OpenAI, Anthropic, or local models via Ollama. Total API cost to run all notebooks: under $5.

All eval runs are traced through **Langfuse** — our production observability platform. Every API call, scoring decision, and comparison is logged with session IDs, input/output pairs, and cost tracking. This means eval results are auditable: you can see exactly what was sent, what came back, and how it was scored. The same Langfuse instance that traces our production systems (Study, Work, Content) traces our evals — the research infrastructure is the same as the production infrastructure.

### 2. Production System Evidence

The author built and operates three real AI systems that use every concept in the book:

- **Study System**: An 18-week curriculum tracker with quiz scoring, gap detection, and adaptive session planning. 127 items, 21 tracking columns, active since May 2026.
- **Work System**: A domain operations advisor with 15 specialized agents, 15 knowledge skills, 10 workflow commands, and 80,000+ documents in a vector database. Used for real client work.
- **Content System**: A multi-platform content pipeline with 7 production stages, quality gates (24/30 minimum score to publish), and 26 posts tracked with scores.

These aren't demos built for the book. They're production tools. The system docs in this repo are genericized to remove proprietary details, but the architecture, component counts, and patterns are real.

### 3. Reader Exercises (In the Chapters)

Every chapter includes hands-on exercises where the reader builds and tests the concepts themselves. The exercises are the most important evidence — because they're the reader's own data, not ours.

## How Notebooks Work

Each eval notebook follows the same structure:

```
1. State the hypothesis (what the book claims)
2. Define the task (something concrete and reproducible)
3. Run the baseline (the common approach)
4. Run the treatment (the book's approach)
5. Score both outputs on the same rubric
6. Show the comparison (side-by-side, plain English)
7. State the finding (what improved, by how much)
```

Rubrics use 1-5 scales with anchored descriptions (1 = fails the criterion, 3 = acceptable, 5 = excellent). Dimensions vary per notebook but always measure what the chapter claims to improve.

## How to Reproduce

1. Clone this repo
2. Install dependencies: `pip install openai anthropic pandas jupyter`
3. Set your API key (any provider — see `evals/notebooks/00-setup.ipynb`)
4. Run the notebooks in order

Each notebook is self-contained. You can change the topic, the rubric, or the provider and re-run.

## This Is Living Research

These notebooks and system docs will grow as the book develops. When a new chapter is drafted, its corresponding eval gets built. When we find a better way to measure something, we update the notebook. The research is versioned alongside the book in this repo — every change is tracked.

If you find a flaw in a notebook or a better way to test a claim, open an issue or submit a PR. The goal is evidence that holds up, not evidence that can't be questioned.
