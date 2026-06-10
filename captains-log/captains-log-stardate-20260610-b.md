# Captain's Log — Stardate 20260610-b
**Date:** 10 June 2026
**Project:** data-brain-gym
**Session:** Format standardisation + Course 2 Chapter 1 (first 3 lessons)

---

## 🎯 SESSION GOAL

Resume Course 2 (*Communicating Data Insights*) from Ch1 L2. Before new content, discovered format drift in Course 1 — resolved first.

---

## ✅ WHAT WE ACCOMPLISHED TODAY

### Part 1 — Format drift discovered and resolved

During pre-session review of `01-introduction-to-data.ipynb`, a format inconsistency was identified:

**3 cells used the old format (numbered prose, no Mental Map as primary):**
- Ch1 L1 — Data basics *(Video)*
- Ch1 L5 — The curious case of data growth *(Video)*
- Ch1 L8 — The value of data *(Video)*

**All other cells (Ch2, Ch3, and all exercise cells) already used the new standard.**

**Decision made:** Standardise before continuing with new content. Methodology consistency is higher priority than lesson throughput.

**Changes made per cell:**

| Cell | Change |
|------|--------|
| Ch1 L1 — Data basics | Replaced `📋 Key concepts covered:` + numbered prose with `🧠 Mental Map` (two-axis classification tree) + callout for metadata |
| Ch1 L5 — Data growth | Promoted the storage ASCII tree from inside a numbered section to a proper `🧠 Mental Map` header; ice cream table moved below |
| Ch1 L8 — Value of data | Concept is linear (4 sectors, no hierarchy) → per instructions: replaced numbered prose with short unnumbered prose paragraphs |

**Rule added to `datacamp.instructions.md`** — new row in ❌ Mistakes to Never Repeat:
> *"When format drift is discovered in existing notebooks, standardise before continuing with new content. Methodology consistency is higher priority than lesson throughput."*

---

### Part 2 — Course 2, Chapter 1: first 3 lessons written

**Notebook:** `02-communicating-data-insights.ipynb`

| Lesson | Type | XP | Status |
|--------|------|----|--------|
| Ch1 L1 — How is knowledge shared | 🎬 Video | 50 | ✅ (written previous session) |
| Ch1 L2 — Communication types | 📝 Exercise | 50 | ✅ written today |
| Ch1 L3 — Communication journey | 📝 Exercise | 100 | ✅ written today |

**Ch1 L2 — Communication types** (single-answer, 50 XP)
- Question: which is NOT an accurate summary of a communication type?
- Correct answer: "Visual communication isn't formal enough to be taken seriously on its own"
- Key trap: confusing *"can be paired with others"* (true) with *"requires others to be taken seriously"* (false)

**Ch1 L3 — Communication journey** (drag-to-order, 100 XP)
- Tyler's story: video call → non-verbal cues → chart email → written report
- Correct order: Verbal → Non-verbal → Visual → Written
- Key insight: non-verbal was not Tyler's tool — it was Matt's signal that Tyler *read* to change strategy

---

## 🧠 DECISIONS AND REASONING

| Decision | Reason |
|----------|--------|
| Standardise format drift before new content | Inconsistent format across notebooks reduces value as a learning resource — a reader (or future Spock) encountering the old format mid-notebook loses context about what the standard is |
| Ch1 L8 — prose paragraphs, not a map | Value of data across 4 sectors is a linear enumeration — no hierarchy, no classification tree. Forcing a map would create a fake structure. Per instructions: *"if a concept has no mappable structure, use a short unnumbered prose paragraph"* |
| Document methodology rule immediately | The format drift lesson is most valuable when captured right after it happens, not reconstructed later |

---

## ⚠️ WHERE WE STOPPED

Session ended mid-chapter. Ch1 has 11 lessons total — 3 done, 8 remaining.

**Current state:**
- `01-introduction-to-data.ipynb` — fully standardised ✅
- `02-communicating-data-insights.ipynb` — Ch1 L1–L3 complete, Ch1 L4–L11 not yet written

**Files modified this session:**
- `data-brain-gym/datacamp/foundations/data-literacy-professional/01-introduction-to-data.ipynb` — 3 cells reformatted
- `data-brain-gym/datacamp/foundations/data-literacy-professional/02-communicating-data-insights.ipynb` — 2 new lesson cells added
- `data-brain-gym/.github/instructions/datacamp.instructions.md` — 1 new row added to ❌ Mistakes table
- `data-brain-gym/captains-log/captains-log-stardate-20260610-b.md` — this file

---

## 🔜 NEXT STEPS

1. ⏳ Continue Course 2, Chapter 1 — Lesson 4: Becoming a more effective communicator *(Exercise / 50 XP)*
2. ⏳ Complete Ch1 L4–L11 (8 lessons remaining)
3. ⏳ Write Ch1 intro + recap cells (deferred until chapter complete)
4. ⏳ Continue Ch2 and Ch3

---

## ✅ Notes for Students

**On methodology over throughput:**
The instinct when resuming a course is to pick up where you left off and keep moving. But if the format drifts — even slightly — across multiple notebooks, the resource degrades. A reader encountering cell 3 in a different format than cell 20 loses orientation. The fix costs 20 minutes. The accumulated confusion costs far more. Standardising before continuing is not perfectionism — it is maintenance, and maintenance is always cheaper before the gap grows.

**On the "why this matters" discipline:**
Every lesson cell ends with *"Why this matters."* This is not politeness — it is an anchor. Without it, the lesson stays theoretical. With it, the concept connects to a real situation where someone made a better decision because they understood it. The discipline of writing it every time builds the habit of asking it every time.
