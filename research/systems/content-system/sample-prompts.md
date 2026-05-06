# Content System — Prompt Comparison

## The Basic Prompt (What Most People Do)

```
Write a blog post about using AI for project management.
Make it engaging and informative. About 800 words.
```

**What you get**: Generic AI-voice blog post. "In today's rapidly evolving landscape, leveraging AI for project management has become a game-changing approach..." Reads like every other AI-generated post. No personality, no specific examples, no original angle.

---

## The System Version (All Components Working)

### Stage 0: Discovery (Conversation, Not a Prompt)

```
System: "What's the real version of this, not the blog version?"

Author: "I've been using AI to generate status updates for three
different audiences from the same data."

System: "That's the process. What's the tension? What surprised you,
broke, or made you rethink something?"

Author: "The surprise was that the AI-generated CEO summary was
BETTER than what I'd write manually — because it didn't include
the politics I'd unconsciously filter in."

System: "That's the angle. The AI doesn't play office politics with
status updates. You do. Let's build from there."
```

**Exit criteria met**: Core tension (AI removes political filtering), specific experience (3-audience status generation), angle differs from obvious ("AI helps with project management" → "AI is more honest than you are about project status").

### Stage 1: Research

```
[System searches for supporting evidence on AI-generated reporting,
cognitive bias in status reporting, audience-tailored communication]

Research brief:
- 3 sources on status report bias in organizations
- Author's own experience: 3 audiences, same data, AI version vs manual
- Contrarian angle: honesty isn't a feature you asked for
```

### Stage 3: Draft (with Voice Skill Loaded)

The voice skill enforces:
- No "leverage," "utilize," "game-changing," "landscape"
- Short sentences followed by longer explanations
- Specific numbers ("3 audiences, same data, 4 minutes") not vague claims
- Author's real sentence patterns and word preferences
- Opinion-forward, not balanced-to-death

### Stage 4: Review (Hook Battery)

```
VOICE CHECK: 0 AI tells found ✓
FACT CHECK: All claims traceable to author experience ✓
OPSEC CHECK: No client names, no proprietary details ✓
STRUCTURE CHECK: Argument builds (not lists) ✓
SCORE: Story 4, Voice 4, Heat 4, OPSEC 5, Structure 4, Evidence 4 = 25/30 ✓
GATE: PASS (≥ 24/30) → publish to posts/
```

---

## The Improvement

| Aspect | Basic Prompt | System Pipeline |
|--------|-------------|----------------|
| Angle | Generic ("AI helps PM") | Specific tension ("AI is more honest than you") |
| Voice | AI-default ("leveraging solutions") | Author's voice (short, specific, opinionated) |
| AI tells per post | 3-5 | ~0 |
| Fact basis | Vague claims | Author's specific experience + researched evidence |
| Quality check | None — you read it and hope | 6-dimension scoring with 24/30 gate |
| OPSEC | You remember to check | Automated flag for names, details, identifiers |
| Consistency across 26 posts | Drifts by post 3 | Voice skill keeps every post in range |
| Time to usable | Fast but needs heavy rewriting | Slower pipeline but output is publish-ready |

---

## The Pipeline's Compounding Effect

Post 1: The system produces decent output. You edit some voice issues. Those edits get noted in state.

Post 5: The voice skill has been updated with patterns from your edits. Fewer corrections needed.

Post 15: The system knows your voice well enough that the Review stage catches the same issues you would. The state file tracks which topics you've covered, preventing repetition.

Post 26: The system produces publish-ready content in your voice, fact-checked, OPSEC-scrubbed, with a quality score you can trust. The editorial calendar is maintained. Platform derivatives are generated automatically.

A single prompt can't do this. It's not a prompt problem — it's a system problem.
