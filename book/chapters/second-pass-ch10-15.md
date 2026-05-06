# Second-Pass Continuity Edit: Chapters 10-15

**Date**: 2026-05-06
**Scope**: Cross-chapter consistency, chapter number references, bridges, AI tells, domain abstraction, tone

---

## Changes Made

### Ch 10 (Production Case Study)

**Line 127 — Wrong chapter number for Skills.**
- Was: "Your skills from Chapter 7 gave Claude expertise in one domain at a time."
- Fixed: "Your skills from **Chapter 6** gave Claude expertise..."
- Reason: Skills = Ch 6 in the 15-chapter structure. Ch 7 = Hooks.

**Line 193 — Wrong chapter number for Connections.**
- Was: "Your connections in Chapter 9 pulled data from one or two external sources."
- Fixed: "Your connections in **Chapter 8** pulled data..."
- Reason: Connections = Ch 8. Ch 9 = Pipelines.

### Ch 11 (Cost)

**Line 100 — Wrong chapter number for verify-cover-letter hook.**
- Was: "Chapter 8's verify-cover-letter hook catches fabrication for $0.00."
- Fixed: "**Chapter 7's** verify-cover-letter hook..."
- Reason: Hooks (including verify-cover-letter) were built in Ch 7. Ch 8 = Connections.

**Line 174 — Same wrong chapter number for verify-cover-letter hook.**
- Was: "The verify-cover-letter hook from Chapter 8."
- Fixed: "The verify-cover-letter hook from **Chapter 7**."
- Reason: Same as above.

### Ch 14 (Design)

**Line 187 — Four wrong chapter numbers in maintenance cross-reference.**
- Was: "...state hygiene in Ch 5, skill versioning in Ch 7, hook tuning in Ch 8, connection health in Ch 9, pipeline bottlenecks in Ch 11"
- Fixed: "...state hygiene in Ch 5, skill versioning in **Ch 6**, hook tuning in **Ch 7**, connection health in **Ch 8**, pipeline bottlenecks in **Ch 9**"
- Reason: All four were off by one (Skills, Hooks, Connections) or two (Pipelines). This was the old numbering scheme before the chapter structure expanded from 13 to 15 chapters.

---

## Issues Checked — No Changes Needed

### Bridge Consistency
- Ch 9 ending (line 487) correctly bridges to Ch 10: "Chapter 10 shows you what happens when all six components run together under real pressure"
- Ch 10 ending (line 223) correctly bridges to Ch 11: "what do they cost to run, and how do you spend smart? That's Chapter 11"
- Ch 11 ending (line 215) correctly bridges to Ch 12: "what do you do when they break?" (no explicit chapter number but direction is clear)
- Ch 12 ending (line 206) correctly bridges to Ch 13: "Chapter 13 introduces them to each other"
- Ch 13 ending (line 319) correctly bridges to Ch 14: "That's Chapter 14"
- Ch 14 ending (line 262) has NO bridge to Ch 15. The chapter ends with "Everything else in this book was building toward this." This is a deliberate design choice -- Ch 14 is the reader's solo flight, and the finality of the ending fits. Optional: could add a bridge sentence, but the current ending is strong.

### Correct Chapter References (verified, no changes)
- Ch 10, line 27: "content pipeline from Chapter 9" -- correct (Pipelines)
- Ch 10, line 47: "hooks from Chapter 7" -- correct (Hooks)
- Ch 10, line 107: "CLAUDE.md from Chapter 4" -- correct (Prompts)
- Ch 10, line 171: "In Chapter 5" -- correct (State)
- Ch 10, line 187: "Chapter 5" -- correct (State)
- Ch 11, line 35: "Chapter 9" pipeline -- correct
- Ch 11, line 57: "Chapter 10" production system -- correct
- Ch 11, line 88: "Chapter 5" state -- correct
- Ch 11, line 130: "Chapter 10" -- correct
- Ch 12, line 68: "Chapter 7" hooks -- correct
- Ch 12, line 112: "Chapter 7" -- correct
- Ch 12, line 182: All five chapter refs correct (Ch 5, 6, 7, 8, 9)
- Ch 13, line 17: "Chapter 9" -- correct
- Ch 13, line 23: "Chapter 3" -- correct
- Ch 14, line 75: "Chapter 3" -- correct

### AI Tells Scan
- Scanned all six chapters (Ch 10-15) against the full banned phrases list from voice.md.
- No instances found of: leverage, utilize, delve, navigate, ecosystem, robust, scalable, seamless, game-changing, revolutionary, cutting-edge, landscape, journey, unlock, additionally, moreover, furthermore, key takeaways, let's dive in, in conclusion, as we've seen, or any other banned phrase.
- Clean across all chapters.

### Domain Abstraction (Ch 10)
- Scanned for: hair, wig, beauty, Lagos, Nigeria, Naira, AuraLogical, Telegram, TikTok, Rita.
- No leaks found. All references use the food import domain language (saffron, vanilla, spices, restaurants, caterers).

### Tone Consistency
- All six chapters maintain the casual-competent voice established in earlier chapters.
- No drift to textbook tone or motivational speaker tone detected.
- Ch 15's "Teaching Others" section has a slightly more reflective tone, but this is appropriate for the final chapter and stays within the book's voice.

---

## Summary

**5 edits made** across 3 files (ch10, ch11, ch14), all fixing incorrect chapter number cross-references. The errors follow a consistent pattern: references were using the old 13-chapter numbering where Skills=Ch 7, Hooks=Ch 8, Connections=Ch 9. In the current 15-chapter structure, these are Skills=Ch 6, Hooks=Ch 7, Connections=Ch 8, Pipelines=Ch 9.

No AI tells, no domain leaks, no bridge errors, no tone drift found.
