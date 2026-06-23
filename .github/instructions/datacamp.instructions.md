---
applyTo: "datacamp/**"
---

# DataCamp Folder Instructions
## data-brain-gym — Spock working in `datacamp/`

---

## 🗂️ Folder Structure

```
true-story-data/
├── data-literacy-professional/   ← 8 courses, 15h
├── data-storytelling/            ← 4 courses, 6h
└── data-skills-for-business/     ← 6 courses, 17h
sql-for-business-analysts/        ← resumes AFTER true-story-data complete
```

**Rule:** No practical track work until all 3 true-story-data tracks are complete.

One notebook per course. Named by course number: `01-introduction-to-data.ipynb`, `02-communicating-data-insights.ipynb`, etc.

---

## 📸 Screenshot Rule — The Only Source

Never generate lesson content without a screenshot. Build from what the screenshot shows — never from lesson titles, prior knowledge, or the course outline.

One cell at a time. No partial cells.

---

## 🦴 Course Backbone Rule

Before starting any new course: parse PDF slide decks → build Course Knowledge Map cell (Cell 2) → then screenshots begin. One course at a time, just before that course starts.

**Current state (as of 20260623):**
- Course 4 Chapters 1–3 complete: 41 lessons, 2,500 / 3,450 XP ✅
- Chapter 4 next: Hypothesis Testing & Correlation (15 lessons, 950 XP)

---

## 📓 Lesson Cell Templates

All DataCamp theory notebooks: markdown cells only (no code cells until Course 8).

### Heading format — exact, no variation

```
#### Chapter X — Lesson N: [Exact Title from DataCamp] *(Type / XP)*
```

Type = one of: `Video`, `Exercise`, `Practice`

---

### 🎬 Video Lesson

```markdown
#### Chapter X — Lesson N: [Title] *(Video / XP)*

> 🎬 [Watch on DataCamp](URL) *(requires login)*

---

**🎯 GOAL — What is this lesson about?**
[1–2 sentences: the concept the video introduces]

---

[Prose or Markdown table explanation — 2–4 sentences or comparison table]

---

**💡 Why this matters**
[One paragraph: specific business scenario where this concept changes a decision]

**✅ RECAP**
- [4–6 concept bullets]

**🔗 Connection**
- [Only genuine cross-chapter or cross-course links — skip if none]
```

---

### 📝 Exercise / 🔘 Practice

```markdown
#### Chapter X — Lesson N: [Title] *(Exercise or Practice / XP)*

---

**🎯 GOAL — What does this exercise test?**
[One sentence: pedagogical purpose — not a restatement of the scenario]

---

**📋 Scenario**
[DataCamp scenario text — verbatim or close paraphrase]

**Task:** [Exact task statement]

---

**✅ Solution**

| Option | Verdict | Explanation | Why This Trap |
|--------|---------|-------------|---------------|
| [text] | ✅ Correct | [Why correct] | — |
| [text] | ❌ Wrong | [Why wrong] | [Trap name + misconception] |

**Common Mistake** *(include when user sent wrong-answer screenshot)*
[Trap name. Root cause.]
**→** *[Wisdom statement: action-oriented, specific to this trap]*

---

**💡 Why this matters**
[One paragraph: specific business scenario]

**✅ RECAP**
- [3–5 concept bullets]

**🔗 Connection**
- [Only genuine links — skip if none]
```

**Rules:**
- `🎬` link → Video cells ONLY. Never in Exercise or Practice.
- `📋 Scenario` → Exercise / Practice ONLY. Never in Video.
- `✅ Solution` table → Exercise / Practice ONLY.
- Show ALL answer options in the table, not just the correct one.
- `🎯 GOAL` → mandatory in every cell. Pedagogical purpose, not topic summary.

---

## 📊 Mastery Statement — after all lessons in a chapter are complete

```markdown
## 📊 CHAPTER X MASTERY STATEMENT

**Chapter X built [one-sentence framing].**

**What this chapter established:**
- [concept bullet]
- [concept bullet]
- [concept bullet]
- [concept bullet]

**The key mental shift:** [From X thinking to Y thinking.]
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

Exclude: wisdom lists, interview checklists, re-explanations of lesson content.

---

## 🗂️ Format Rules

| Format | Used in | When |
|--------|---------|------|
| Prose | All lessons | Linear concepts, definitions |
| Markdown table | Classification lessons | 2–4 categories to compare |
| Mermaid diagram | `.md` files only | Chapter concept map — after chapter complete |

**No ASCII trees in notebooks.**

**`🔗 Connection`:** max 3 bullets, genuine cross-chapter/course links only. Skip if none.

**Chapter arc line:** one italic line added to course header cell (Cell 1) after chapter is complete — not a separate cell.

---

## ✅ Cell Quality Checklist

Before inserting any cell into the notebook:

- [ ] Built from a screenshot (not inferred from title or prior knowledge)
- [ ] Heading format exact: `#### Chapter X — Lesson N: [Title] *(Type / XP)*`
- [ ] All required sections present in correct order
- [ ] `🎯 GOAL` = pedagogical purpose, not a topic summary
- [ ] `💡 Why This Matters` = concrete scenario, not a generic claim
- [ ] Solution table shows ALL options (Exercise/Practice)
- [ ] `**→**` wisdom line is action-oriented and trap-specific
- [ ] `🎬` link present in Video; absent in Exercise/Practice
- [ ] Cell inserted directly after the last completed lesson cell for this chapter

---

## 🔄 Chat Closing & Opening

### Closing (in order)
1. Finish current lesson cell
2. `git add` + `git commit` — one chapter = one commit
3. Update captain's log: last lesson completed + next lesson
4. Commit captain's log

**Commit format:**
```
Complete Course N Chapter X: [Title] — N lessons
```

### Opening — run `#file:new-session.prompt.md`

---

## ❌ Mistakes to Never Repeat

| Mistake | Rule |
|---------|------|
| `🎬` link in exercise/practice cells | Video cells only |
| Building a cell from lesson title alone | Screenshot required — always |
| Chapter intro or mastery written mid-chapter | Defer until chapter is complete |
| Multiple lesson cells in one message | One cell per message |
| ASCII trees in notebook cells | Prose or Markdown table only |

---

## 🔗 Cross-Track Shared Courses (as of June 2026)

| Course | Data Literacy Professional | Data Storytelling | Data Skills for Business |
|--------|---------------------------|-------------------|--------------------------|
| Introduction to Data | ✅ (1) done | — | shared |
| Communicating Data Insights | ✅ (2) done | shared | — |
| Introduction to Data Literacy | ✅ (3) done | — | shared |
| Data Storytelling Concepts | ✅ (7) | shared | — |

Shared courses: learned once, notebook lives in the first track, other track README points to it.
