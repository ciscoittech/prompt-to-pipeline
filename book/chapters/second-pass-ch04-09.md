# Second-Pass Continuity Edit: Chapters 4-9

**Date:** 2026-05-06
**Scope:** Cross-chapter consistency, bridges, terminology, file paths, AI tells

---

## Changes Made

### Chapter 5 (State Files)

**1. Terminology fix — "instruction file" replaced with "CLAUDE.md"**
- Line 123 (original): "The instruction file orchestrates the state file."
- Changed to: "CLAUDE.md orchestrates the state file."
- Reason: The book uses "CLAUDE.md" as the consistent name for the project instructions file. "Instruction file" is a generic descriptor that could confuse readers who've been learning the specific filename.

---

### Chapter 8 (Connections)

**2. Skill file paths — flat files corrected to directory-based format**
- Lines 351-355 (What You Built directory listing): Skills were listed as flat files (`editorial-voice.md`, `content-standards.md`, etc.)
- Changed to directory-based format: `editorial-voice/SKILL.md`, `content-standards/SKILL.md`, etc.
- Reason: Chapter 6 established the canonical format as `skills/skill-name/SKILL.md` (directory containing SKILL.md). Chapters 6 and 7 use this format correctly. Ch 8 had regressed to flat files.

---

### Chapter 9 (Pipelines)

**3. Skill file paths — flat files corrected to directory-based format**
- Lines 401-405 (What You Built directory listing): Same flat-file regression as Ch 8.
- Changed to directory-based format matching Ch 6/7.

**4. Hook filenames — corrected to match Ch 7's actual builds**
- Lines 407-413 (What You Built directory listing): Listed 7 hooks with names that don't match Ch 7:
  - `check-duplicate-application.sh` -> `check-duplicate.sh`
  - `verify-quiz-answers.sh` -> `check-quiz-format.sh`
  - `check-weak-area-focus.sh` -> removed (never built in Ch 7)
  - `verify-status-consistency.sh` -> removed (never built in Ch 7)
  - `check-audience-format.sh` -> removed (never built in Ch 7)
  - `verify-content-quality.sh` -> `check-content-quality.sh`
- Reason: Ch 7 built exactly 5 hooks: verify-cover-letter.sh, check-duplicate.sh, check-quiz-format.sh, check-status-dates.sh, check-content-quality.sh. The Ch 9 listing invented 2 extra hooks and renamed 3 others.

**5. Hook count — corrected from 7 to 5**
- Line 437 (original): "Five skills. Seven hooks."
- Changed to: "Five skills. Five hooks."
- Reason: Matches the corrected directory listing (5 hooks built in Ch 7).

**6. Hook name in narrative — "verify-content-quality" corrected throughout**
- Lines 192, 235, 289: Three occurrences of "verify-content-quality.sh" / "verify-content-quality hook" changed to "check-content-quality.sh" / "check-content-quality hook"
- Reason: Ch 7 names this hook `check-content-quality.sh`. Ch 9 was using a different name.

**7. Hook name in Study pipeline — "verify-quiz-answers" corrected**
- Line 324: "Hook fires: verify-quiz-answers checks format." changed to "Hook fires: check-quiz-format checks structure."
- Reason: Ch 7 names this hook `check-quiz-format.sh`, not `verify-quiz-answers.sh`.

**8. Missing bridge to Ch 10 — added closing paragraph**
- End of chapter (after "How to Know It's Clicking"): Ch 9 ended without teasing Ch 10.
- Added: bridge paragraph mentioning Ch 10 (Production Case Study) as the next destination, noting it shows all six components under real pressure with real stakes.
- Reason: Every other chapter (4-8) ends with a bridge to the next chapter. Ch 9 was the only one missing this.

---

## Issues Checked and Found Clean

### Chapter cross-references
All "Chapter X" and "Ch X" references across Ch 4-9 point to correct content for the 15-chapter structure. Verified:
- Ch 1-3 references (Act 1 concepts) are correct
- Ch 4-9 cross-references between build chapters are correct
- Forward references to Ch 7, Ch 8, Ch 9 from earlier chapters are correct

### Bridge consistency
- Ch 4 ending -> mentions Ch 5 (State): correct
- Ch 5 ending -> mentions skills/next chapter: correct
- Ch 6 ending -> mentions "hooks fix in Chapter 7": correct
- Ch 7 ending -> mentions "connections -- next chapter": correct
- Ch 8 ending -> mentions "Chapter 9 breaks work into stages": correct
- Ch 9 ending -> NOW mentions Ch 10 (added in fix #8)

### Components Used checklist
All six chapters have correct, progressively growing component lists:
- Ch 4: `[Prompt (CLAUDE.md)]`
- Ch 5: `[Prompt (CLAUDE.md)] + [State (NEW)]`
- Ch 6: `[Prompt (CLAUDE.md)] + [State] + [Skill (NEW)]`
- Ch 7: `[Prompt (CLAUDE.md)] + [State] + [Skill] + [Hook (NEW)]`
- Ch 8: `[Prompt (CLAUDE.md)] + [State] + [Skill] + [Hook] + [Connection (NEW)]`
- Ch 9: `[Prompt (CLAUDE.md)] + [State] + [Skill] + [Hook] + [Connection] + [Pipeline (NEW)]`

### AI tells
No banned phrases found in prose. All matches were inside quoted examples, CLAUDE.md templates, or hook scripts (where banned words are being demonstrated/checked-for, not used as prose).

### Terminology consistency
- "State file" used consistently (no "memory file" or "tracker" as a synonym)
- "Skill" used consistently (Ch 6 uses "knowledge document" once in the definitional passage explaining what skills are -- this is appropriate as a one-time plain-language translation)
- "Hook" used consistently (no "check script" or "guard rail script")
- "CLAUDE.md" used consistently after the Ch 5 fix

### @import wiring
State file wiring uses `@filename.md` format consistently across Ch 5-9.

### stdin JSON pattern for hooks
All hooks use `INPUT=$(cat)` + `jq` extraction pattern consistently.

---

## Items NOT Changed (Noted for Awareness)

### PM pipeline references unbuilt hooks
Ch 9's Project Management pipeline extension (lines 353-354) references `check-audience-format` and `verify-status-consistency` hooks that were never built in Ch 7. These are in the "Extend It" section, which is aspirational/exercise content. The reader is expected to build these as part of extending their system. Consistent with how other extension sections reference skills and state files the reader builds themselves.

### Ch 4 "instruction files" in terminal comparison
Ch 4 line 15 uses "instruction files" in the general comparison between terminal and GUI: "In a graphical tool, your instruction files are hidden behind menus." This is descriptive/generic and appropriate in context (before CLAUDE.md has been introduced as a specific term).
