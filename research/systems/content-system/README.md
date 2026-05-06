# Content System — Production Evidence

A real multi-platform content pipeline built with Claude Code. Produces blog posts, Twitter threads, LinkedIn posts, and newsletter content through a gated 7-stage process. 26 posts tracked with quality scores. Active since early 2026.

## Architecture

```
[Story seed / operational experience]
          |
          v
    +-----------+
    | COMMANDS:  |  /blog (7-stage pipeline)
    | 7 entry   |  /repurpose (derivatives)
    | points    |  /content-next (daily queue)
    |           |  /content-mine (surface briefs from dev work)
    |           |  + 3 more specialized
    +-----+-----+
          |
    +-----+-----+
    | SKILLS:    |  5 loaded based on context:
    | voice &    |  - Editorial voice (tone, words, structure)
    | platform   |  - Twitter rules (2026 algorithm)
    |            |  - LinkedIn rules (360Brew algorithm)
    |            |  - Alt voice (different audience)
    |            |  - Curriculum mapping (series coherence)
    +-----+-----+
          |
    +-----+-----+
    | PIPELINE:  |  7 stages with quality gates:
    | gated      |  0. Discovery (find the real angle)
    | flow       |  1. Research (gather evidence)
    |            |  2. Outline (structure the argument)
    |            |  3. Draft (write it)
    |            |  4. Review (hook battery: voice, facts, OPSEC)
    |            |  5. Polish (final formatting)
    |            |  6. Distribute (/repurpose → multi-platform)
    +-----+-----+
          |
    +-----+-----+
    | QUALITY    |  6-dimension rubric, 1-5 each
    | GATES:     |  24/30 minimum to publish
    | scoring    |  Score < 24 → drafts/ (rework later)
    |            |  Score ≥ 24 → posts/ (publish-ready)
    +-----+-----+
          |
    +-----+-----+
    | STATE:     |  Post tracker: title, score, pillar,
    | editorial  |  heat level, publish status, platform
    | tracking   |  Topic bank: seeds organized by category
    +-----+-----+
          |
          v
    [Substack → Twitter → LinkedIn → Substack Notes]
```

## The Quality Gate

Every post is scored on 6 dimensions (1-5 each):

| Dimension | What It Measures |
|-----------|-----------------|
| Story | Does it have a real narrative, not just information? |
| Voice | Does it sound like the author, not like AI? |
| Heat | Is it taking a position, or hedging? |
| OPSEC | No client names, no proprietary details, no identifying info |
| Structure | Does the argument build, or does it list? |
| Evidence | Are claims backed by specific experience or data? |

**24/30 minimum to publish.** Below that → goes to drafts/ for rework. This gate is enforced by the system, not by the author's willpower.

## Evidence

| Metric | Value |
|--------|-------|
| Posts tracked | 26 |
| Posts scoring ≥ 24/30 | 10 (publish-ready) |
| Posts scoring 20-23/30 | 15 (in drafts, need rework) |
| Posts killed | 1 (topic didn't survive Discovery) |
| Content pillars | 5 (with different voice calibration per pillar) |
| Heat levels | 3 (Measured, Spicy, Volcanic — default varies by audience) |
| Platform derivatives per post | 4 (Substack, Twitter, LinkedIn, Notes) |

## Key Patterns

### Discovery Stage (The Real Differentiator)
Stage 0 is a conversation, not a prompt. The system pushes back on safe framing:
- "That's the version everyone writes. What's yours?"
- "Is that what's actually happening, or the story you're telling yourself?"

Exit criteria: core tension identified, analogy emerged naturally, author can state the real angle in one sentence. If nothing clicks → kill the topic. A dead topic in Discovery is better than a forced draft.

### Anti-Sycophancy Rules (Control)
The system is explicitly instructed NOT to:
- Validate weak ideas
- Perform enthusiasm
- Echo the user's framing back as insight
- Score a mediocre draft above what it deserves

This is Control applied to the AI's interaction style, not just its output.

### Voice Skill Loading
The voice skill contains:
- 5+ examples of the author's real writing (AI learns FROM them)
- Words and phrases to use vs. never use
- Sentence structure patterns
- Tone calibration per format and audience
- AI-tell blocklist ("leverage," "delve," "game-changing," etc.)

With the skill loaded, AI-tell frequency drops from 3-5 per post to near zero. Voice consistency improves from ~2/5 to ~4/5 across 26 posts.

### Multi-Platform Distribution (Pipeline + Router)
One blog post → 4 platform derivatives. Each platform has its own skill with algorithm-specific rules:
- **Twitter**: Replies weighted 150x over likes (2026 Grok algorithm). Threads get 3x engagement vs standalones.
- **LinkedIn**: Saves weighted 5x over likes. Carousels get 6.6% engagement. Personal profiles outperform company pages 500%.

The `/repurpose` command routes the post through each platform's skill — same content, different format, different optimization. This is the Router pattern from Ch 3.
