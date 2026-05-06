# Study System — Prompt Comparison

## The Basic Prompt (What Most People Do)

```
Quiz me on cloud computing concepts. Give me 10 questions.
```

**What you get**: 10 random questions across all of cloud computing. Some too easy, some too hard. No targeting. Run it tomorrow — you get a different random 10 with no connection to today's results.

---

## The Structured Prompt (Ch 4: Instruction)

```
I'm studying for the AWS Solutions Architect certification.
My current level: I understand EC2, S3, and basic VPCs but struggle
with IAM policies, cross-region replication, and auto-scaling groups.

Generate 10 quiz questions. Weight them: at least 6 should cover
IAM, replication, or auto-scaling. Each question: 4 multiple-choice
options, one correct answer, and a 2-sentence explanation of why
the correct answer is right and why the most tempting wrong answer
is wrong.

Constraints: Focus on conceptual understanding, not memorizing
specific CLI flags or ARN formats.
```

**What improved**: Questions target stated weak areas. Explanations address common confusions. Format is consistent and useful. But you had to type your weak areas from memory.

---

## The System Prompt (Ch 5+: State-Loaded)

The system reads the CSV state file before generating anything. Here's what the prompt looks like when the system constructs it:

```
[System reads curriculum CSV — finds these rows for Week 5:]

status=CLOSE, gaps="IAM policy evaluation, cross-account roles"
status=GAP, gaps="auto-scaling lifecycle hooks"
status=KNOWN (skip — already mastered)
status=PRIORITY, gaps="S3 replication rules, versioning edge cases"

[System constructs prompt:]

Based on the learner's progress data:
- CLOSE on IAM (has intuition, needs formal vocabulary)
- GAP on auto-scaling lifecycle hooks (needs fundamentals)
- KNOWN on EC2 basics (skip — don't re-test)
- PRIORITY on S3 replication (assigned for focused practice)

Generate 10 quiz questions:
- 3 on IAM policy evaluation (CLOSE level — test vocabulary precision)
- 3 on auto-scaling lifecycle hooks (GAP level — start from fundamentals)
- 3 on S3 replication rules (PRIORITY — focused practice)
- 1 review question connecting IAM to S3 (cross-topic synthesis)

Scoring: For each question, I'll evaluate the answer as:
- KNOWN: Correct with precise vocabulary
- CLOSE: Right direction, imprecise language
- GAP: Wrong or can't answer

After all 10, update the learner's gap list and recommend
next session focus.
```

**What improved over the structured prompt**:
- Weak areas come from data (quiz scores), not the learner's memory
- Difficulty is calibrated per topic (CLOSE gets vocabulary tests, GAP gets fundamentals)
- Mastered topics are automatically skipped — no wasted time
- The system plans the NEXT session based on THIS session's results
- The learner doesn't type any of this — the system constructs it from the CSV

---

## The Improvement at Each Stage

| Aspect | Basic Prompt | Structured (Ch 4) | System (Ch 5+) |
|--------|-------------|-------------------|----------------|
| Topic targeting | Random | Manual (you type weak areas) | Automatic (from quiz data) |
| Difficulty calibration | AI guesses | You state your level | Per-topic from scores |
| Mastered topics | Re-tested | You tell it to skip | Auto-skipped |
| Session continuity | None | You paste notes | CSV carries forward |
| Next session planning | None | None | Auto-generated from gaps |
| Maintenance effort | None | You update notes each time | System updates CSV |
| Scales to 20+ sessions | No | Collapses under manual overhead | Gets MORE useful with data |
