---
applyTo: "datacamp/**"
---

# Haiku Working Instructions
## data-brain-gym — AI assistant rules for DataCamp notebook work

> These instructions apply to any AI assistant (including Claude Haiku, GPT, or similar) working on DataCamp notebook files in `datacamp/**`. They define what a valid lesson cell looks like, where to insert it, and what is strictly off-limits without a screenshot.
>
> They do not replace `datacamp.instructions.md` — they complement it. Read both before building any cell.

---

## � Session Start Protocol — Do This First, Every Time

When a new session begins, before doing anything else:

1. **Read this file fully** — from start to finish. Do not skim.
2. **Read `datacamp/true-story-data/data-literacy-professional/04-introduction-to-statistics.ipynb`** — identify the last completed lesson cell (last cell whose heading is `#### Chapter X — Lesson N:`).
3. **State the next lesson** — chapter number, lesson number, title, type (Video / Exercise / Practice), and XP.
4. **Stop and wait** — do not generate any content. Say:

   > *"Ready. Next lesson is Chapter X, Lesson N: [Title] (Type / XP). Send the screenshot when ready."*

5. **Wait for a screenshot** before writing a single word of lesson content.

**If the notebook cannot be found or read:** say so clearly and list the `.ipynb` files visible in `datacamp/**`. Do not guess the stopping point.

**If the last cell is a mastery statement (not a lesson cell):** the chapter is complete. State which chapter is next and which lesson within it is first.

---

## �🚫 Screenshot Rule — Hard Stop

**Never generate lesson content without a screenshot from the user.**

DataCamp lesson content is proprietary. Every lesson cell must be built from what the screenshot shows — not inferred from the lesson title, prior knowledge, or the course outline.

If no screenshot has been provided:
1. Identify which lesson is next (from the course header cell or the last completed cell)
2. State the lesson title and type
3. Say: "Screenshot required before I can build this cell."
4. Stop. Do not generate content.

A half-built cell that looks complete but is based on inference is worse than no cell.

---

## 📐 Lesson Cell Template — Required Structure

Every lesson cell must follow this exact structure. Do not add sections. Do not remove sections. Do not reorder them.

```
#### Chapter X — Lesson N: [Title] *(Type / XP)*

---

**🎯 GOAL — What does this [lesson/exercise/practice] test?**
[One or two sentences. Must state what skill is being tested — not a topic summary.]

---

**📋 Scenario** (Exercise / Practice only — omit for Video lessons)
[The scenario text from the screenshot, verbatim or close paraphrase.]

**Task:** [What DataCamp asks the student to do.]

---

**✅ Solution**
[Solution table or answer. See table format rules below.]

**Common Mistake** (if the user sent a wrong-answer screenshot)
[Name the trap. One sentence. Then the wisdom line.]
**→** *[Action-oriented wisdom statement.]*

---

**💡 Why this matters** (Video lessons: replace with inline prose under the concept)
[One concrete business scenario where this concept changes a decision. Not a generic claim.]

**→** *[Bold action-oriented wisdom statement.]*

**✅ RECAP**
[4–6 bullets. Concepts only. No restatement of the scenario.]*

**🔗 Connection**
[2–4 bullets linking this lesson to adjacent lessons. Explain WHY the link exists, not just the lesson titles.]
```

---

## 📋 Solution Table Format — Exercise / Practice Lessons

Show **all answer options**, not just the correct one.

| Option | Answer | Verdict | Why / Trap Explanation |
|--------|--------|---------|------------------------|
| 1 | [text] | ❌ Wrong | [Why someone would choose this — name the trap] |
| 2 | [text] | ✅ Correct | [Why this is correct] |
| 3 | [text] | ❌ Wrong | [Why someone would choose this] |

If the user sent a wrong-answer screenshot, add a row or note:

> **Your choice:** Option X — [Why you chose it] → [What the error reveals]

---

## 🎬 Video Lesson Format

Video lessons do not have a scenario or solution table. Use this structure instead:

```
#### Chapter X — Lesson N: [Title] *(Video / XP)*

> 🎬 [Watch on DataCamp](URL) *(requires login)*

---

**🎯 GOAL — What is this lesson about?**
[One sentence: the concept the video introduces.]

---

[Concept explanation: ASCII maps, tables, examples from the video transcript or slides.]

---

**💡 Why this matters**
[One concrete business application.]

**→** *[Wisdom statement.]*

**✅ RECAP**
[4–6 bullets.]

**🔗 Connection**
[2–4 bullets.]
```

---

## 📏 Lesson Cell Heading — Exact Format

```
#### Chapter X — Lesson N: [Exact Title from DataCamp] *(Type / XP)*
```

- `Chapter X` — chapter number (1, 2, 3, 4)
- `Lesson N` — lesson number within the chapter (1, 2, 3...)
- `Type` — one of: `Video`, `Exercise`, `Practice`
- `XP` — the XP value shown on DataCamp (e.g., `50 XP`, `100 XP`)

**Examples:**
```
#### Chapter 3 — Lesson 4: Identifying n and p *(Exercise / 50 XP)*
#### Chapter 3 — Lesson 5: The normal distribution *(Video / 50 XP)*
```

---

## 📍 Cell Insertion Rule — Where New Cells Go

New lesson cells must be inserted **immediately after the last completed lesson cell for the active chapter**.

**Never append to the bottom of the notebook** unless the active chapter's last cell is already at the bottom.

**How to verify the correct insertion point:**
1. Find the last cell whose heading matches the current chapter (e.g., `#### Chapter 3 —`)
2. Insert the new cell directly after it
3. Mastery statements go after the last lesson of the chapter — not before Chapter 3 begins

**Wrong:** Adding a Chapter 2 cell after Chapter 3 cells have already been written.
**Correct:** Chapter 2 cells → Chapter 2 mastery → Chapter 3 cells → Chapter 3 mastery.

---

## 📊 Mastery Statement Rules

A mastery statement is written **after all lessons in a chapter are complete** — not before, not during.

**Maximum length:** ~20 lines.

**Required content (4 elements only):**

1. **One framing sentence** — what mental model the chapter built
2. **Concept bullets (4–5 max)** — what was established; no restatement of individual lesson wisdom
3. **One mental shift sentence** — the key change in thinking the chapter produced
4. **XP scoreboard table** — course progress at chapter close

**What to exclude:**
- Wisdom statement lists (those already live in each lesson cell)
- Interview readiness checklists (those live in `docs/recruiting-lens-framework.md`)
- Verbose concept re-explanations (those live in the lesson cells)
- Any content that duplicates what is already in the lesson cells

**Format:**

```markdown
## 📊 CHAPTER X MASTERY STATEMENT

**Chapter X built [one-sentence framing].**

[Optional: 1–2 sentence context on how lessons connected.]

**What this chapter established:**
- [concept bullet]
- [concept bullet]
- [concept bullet]
- [concept bullet]

**The key mental shift:** [One sentence — from X thinking to Y thinking.]
Chapter X+1 builds on this by [one line].

---

**Chapter X complete: XP / XP ✅**

| Chapter | Lessons | XP | Status |
|---|---|---|---|
| Ch1: ... | x/x | x/x | ✅ |
| Ch2: ... | x/x | x/x | ✅ |
| Ch3: ... | x/x | x/x | 🔄 |
| Ch4: ... | x/x | x/x | ⏳ |
| **Total** | **x/x** | **x/x** | **x%** |
```

---

## 🔗 Recruiter Signals — Do Not Duplicate

The recruiting perspective is already documented in `docs/recruiting-lens-framework.md`.

Do not add interview scripts, signal analysis, or recruiter commentary to:
- Lesson cells (beyond the standard "Why this matters" paragraph and one interview-readiness example)
- Mastery statements
- Chapter recap cells

If a lesson warrants a new interview scenario or signal example, note it in the captain's log for later. The framework document is updated at chapter boundaries, not per lesson.

---

## 🔄 Error-Driven Learning — When User Sends Wrong Answer

When the user shares a screenshot showing an incorrect answer:

1. **Identify** which option they chose
2. **Name the trap** — the specific false reasoning pattern (not "you made a mistake")
3. **Add to the solution table** — include their error in the "Your choice" row
4. **Write the Common Mistake section** — trap name + wisdom line
5. **Integrate into RECAP** — one bullet that guards against this trap in future

**Trap naming examples (from Course 4):**
- "Visual misclassification — partial feature matching" (peak ≠ uniform)
- "Direction reversal — applying correct principle the wrong way" (law of large numbers)
- "Dimension confusion — mental model overrides data reality" (time feels discrete)
- "Normalization omission — calculated window but forgot the denominator"

Do not say "you were wrong" or "you confused X with Y" without naming the underlying pattern.

---

## ✅ Before Submitting Any Cell — Quality Checklist

- [ ] Built from a screenshot (not inferred)
- [ ] Heading format exact: `#### Chapter X — Lesson N: [Title] *(Type / XP)*`
- [ ] All required sections present in correct order
- [ ] Solution table shows all options (Exercise/Practice)
- [ ] GOAL states what is being tested — not a topic summary
- [ ] Why This Matters has a concrete scenario — not a generic claim
- [ ] Wisdom line is action-oriented and starts with `**→**`
- [ ] No wisdom list or interview checklist in mastery statements
- [ ] Cell inserted after the correct last lesson cell for this chapter
