# Chapter Structure Reference — From Prompts to Pipelines (v3)

Two acts, different templates. Match the structure to the chapter type before drafting.

## Act 1 Chapters (Ch 1-3): Universal, Tool-Agnostic

| Section | Target Length | Purpose |
|---------|--------------|---------|
| Hook | 300-700 words | Scenario the reader recognizes — open mid-scene |
| Concept / Framework | 600-1,200 words | Teach the concept with non-AI examples first, then AI |
| Reader Exercise | 500-1,000 words | The reader DOES something in any AI tool |
| Feel the Limitation | 200-500 words | The manual approach breaks — name why |
| Assessment | 200-400 words | "How to Know It's Clicking" — self-verifiable checks |

**Total**: 3,000-4,500 words per chapter.

**Act 1 rules**:
- No specific tool required — "any AI tool"
- The Study System is the throughline (Sessions 1-5 across Ch 1-2)
- Ch 3 adds patterns (Loop, Gate, Router) and the napkin sketch — no new sessions
- Reference production evidence where it strengthens claims

---

## Act 2 Chapters: CLI-Demonstrated

### Component Chapters (Ch 4, 5, 7, 8, 10, 11)

| Section | Target Length | Purpose |
|---------|--------------|---------|
| The Problem | 200-400 words | What fails WITHOUT this component — specific scenario |
| See the System | 100-200 words + diagram ref | Current system + the gap |
| The New Component | 200-400 words | What it is, what failure it prevents (one sentence) |
| Build It — Deep | 1,200-2,000 words | Step-by-step on PRIMARY system, all files shown, CLI commands |
| Extend It | 400-800 words | Shorter walkthrough extending to other 3 systems |
| Maintain It | 200-400 words | How to keep this component healthy (state hygiene, skill versioning, etc.) |
| System Diagram | 50-100 words + Mermaid ref | Updated diagram showing new component |
| Break It on Purpose | 100-200 words | Feed bad input, verify the component catches it |
| Quality Gate | 100-200 words | 3-5 concrete, verifiable checks |

**Total**: 3,000-4,500 words per chapter.

**Component chapter rules**:
- "Components Used" checklist at top of "Build It"
- Show terminal commands and file contents inline
- Say "If you prefer a graphical interface, these same files work in Cowork or VS Code"
- Each step starts with a verb: Open, Create, Type, Run, Review
- Include what the AI does at each step (what the reader sees)
- "Maintain It" section is mandatory — NOT deferred to Ch 12

### Deepening Chapters (Ch 6)

Same structure as component chapters but WITHOUT "The New Component" section. The reader applies existing components (Prompt + State) in a new domain to prove the concepts transfer.

**Total**: 2,500-4,000 words.

### Integration Chapters (Ch 9)

| Section | Target Length | Purpose |
|---------|--------------|---------|
| What You Have | 200-400 words | Full inventory of components built so far |
| How They Connect | 300-500 words + diagram | Data flow, component interactions |
| Build It (Integration) | 1,200-2,000 words | Combine prior components — NO new component |
| Design Principles | 200-400 words | 3-5 rules ("if removing a component doesn't break anything, remove it") |
| Quality Gate | 150-300 words | End-to-end check + multi-component "break it on purpose" |

**Total**: 2,500-4,000 words.

### Mastery Chapters (Ch 12-13)

| Section | Target Length | Purpose |
|---------|--------------|---------|
| Framework | 400-800 words | The debugging protocol (Ch 12) or composition patterns (Ch 13) |
| Apply to Systems | 1,000-1,800 words | Walk through all 4 systems |
| Reader Does It | 400-800 words | Reader applies the framework to their own system |
| Quality Gate | 200-400 words | Verifiable check |

**Total**: 3,000-4,500 words.

---

## CLI Example Format

Show terminal interactions like this:

```
$ claude "your prompt here"
```

Or for file creation:

```
Create a file called `study-state.md` in your project folder:
```

Then show the file contents in a code block.

For multi-step builds, number the steps:

```
Step 1: Create the state file
Step 2: Update the prompt to read state at start
Step 3: Run the system
Step 4: Check the state file — it should now contain...
```

---

## System Diagram Format

Diagrams are Mermaid source files rendered to SVG + PNG. See `references/diagrams.md` for the full system.

In chapter text, reference the diagram:
> "Here's what your system looks like now — see Figure X or open `book/diagrams/png/ch05-state-system.png`"

In-text ASCII diagrams are still acceptable for simple inline flows:
```
[Input] → [Prompt + State read] → [AI] → [Output + State write]
```

---

## Cross-Chapter References

- **Allowed**: "Using the prompt structure from Chapter 4..." — back-reference
- **Allowed**: Brief reminder: "Remember the 4-part formula? Same structure here."
- **Allowed**: Forward teaser for motivation: "In Ch 8, you'll add automated checks"
- **Forbidden**: Forward-teaching — explaining HOW something works before its chapter
- **Forbidden**: Using a component before its introduction chapter
