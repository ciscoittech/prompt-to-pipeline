# Appendix D: Glossary

Plain-language definitions. One sentence each. No jargon in the definitions.

*Populated as terms are introduced in chapters.*

---

## Universal Concepts (Act 1)

**Instruction** — What you tell the AI to do, and how precisely you tell it.

**Memory** — Anything that persists between sessions — files, logs, trackers that carry context forward.

**Control** — Checks, rules, and constraints that catch mistakes before they reach you.

**Flow** — Multi-step sequences where each stage's output feeds the next.

## Design Patterns (Ch 3)

**Loop** — A pattern where the system processes, checks, improves, and repeats until the output is good enough.

**Gate** — A checkpoint between stages that decides "continue" or "go back and fix it."

**Router** — A decision point where the system chooses a different process based on what it sees in the input.

**Napkin Test** — If you can't sketch your system on a napkin, it's too complicated.

## Implementation Components (Act 2)

**Prompt** — A structured request with four parts: Context, Input, Output, Constraints. Saved as a file, not pasted into a chat.

**State** — A file the system reads at the start of every session and writes to at the end. Carries forward what happened — scores, decisions, progress, what's next.

**Skill** — A reusable knowledge document loaded before the AI works. Contains rules, examples, and expertise for a specific domain.

**Hook** — An automated check that runs before or after the AI acts. Catches errors, enforces rules, refuses to let bad output through.

**Connection** — A way for the AI to reach outside your local files — web search, plugins for other tools, APIs.

**Pipeline** — A multi-stage workflow where each stage has entry criteria, exit criteria, and a quality gate between stages.

## Tools (Act 2)

**Terminal** — A text-based window where you type commands and see results. Where you build and run your systems.

**Warp** — A free, open-source terminal recommended in this book. Supports Claude Code, Codex, Kimi CLI, and other AI tools.

**Claude Code** — Anthropic's AI tool that runs in the terminal. The primary tool used in this book's examples.

**CLI** — Command Line Interface. Working in the terminal by typing commands instead of clicking buttons.

**MCP Server** — A plugin that gives your AI tool access to another service (Google Drive, Notion, databases, etc.).

## Other Terms

*To be populated as chapters introduce new vocabulary.*
