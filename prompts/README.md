# Prompt Library

Prompt templates and the 4-part formula used throughout the book.

## Structure

```
prompts/
└── templates/           # The 4-part formula templates
    ├── basic-task.md        # Simple single-task prompt
    ├── document-creation.md # Document generation prompt
    ├── analysis-task.md     # Analysis/evaluation prompt
    └── multi-step-workflow.md # Multi-stage pipeline prompt
```

## The 4-Part Formula

Every prompt in this book follows the same structure:

| Part | Purpose | Example |
|------|---------|---------|
| **Context** | Who you are, what you're working on | "I'm studying for the AWS SA cert, intermediate level" |
| **Input** | What the AI should read or work with | "Here are my notes from today" |
| **Output** | Exactly what the finished work looks like | "10 quiz questions, 4 options each, explanations" |
| **Constraints** | What NOT to do | "No memorization questions, flag ambiguity" |

## Where Prompts Live

Prompt files are created in each system's folder as the reader builds through Act 2:

```
my-ai-systems/
├── study-system/study-prompt.md       (Ch 4)
├── job-hunting/job-prompt.md          (Ch 4)
├── project-mgmt/pm-prompt.md         (Ch 4)
└── content/content-prompt.md          (Ch 4)
```

Each prompt file evolves across chapters as components are added.
Complete final versions are collected in Appendix B: Complete System Files.
