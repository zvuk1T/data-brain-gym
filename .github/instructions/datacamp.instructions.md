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
[1–2 sentences: core wisdom — what changes when you know this]

**Interview readiness:**
Recruiter: *"[realistic question about this concept]"*
**Your answer:** "[2–3 sentences, confident and precise]"

**✅ RECAP**
- [3–4 concept bullets]

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
[1–2 sentences: core wisdom — what changes when you know this]

**Interview readiness:**
Recruiter: *"[realistic question about this concept]"*
**Your answer:** "[2–3 sentences, confident and precise]"

**✅ RECAP**
- [3–4 concept bullets]

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

## �️ Chapter Structure — Separators, Recaps, Progress Table

**Three structural cells frame the lessons of each course notebook.**

### 1. Chapter separator — before each chapter's first lesson

```markdown
### Chapter X: [Exact Chapter Title from DataCamp]
```

One line, no body. This is what makes the VS Code outline nest `####` lessons under `###` chapters. One separator per chapter.

### 2. Chapter recap — after all lessons in a chapter are complete

```markdown
### Chapter X — Recap

*Mental shift: [from X thinking to Y thinking — one italic sentence].*

**Chapter X complete: XP / XP ✅**
```

A separate cell — never appended to the last lesson cell. Two parts only: one mental-shift sentence + the chapter's own XP line. Nothing else.

Exclude: "what this chapter established" bullet lists, wisdom lists, interview checklists, re-explanations of lesson content, cross-chapter cumulative tables.

### 3. Course progress table — one only, directly after the course header (Cell 1)

```markdown
### 📊 Course Progress

| Chapter | Lessons | XP | Status |
|---|---|---|---|
| Ch1: ... | x/x | x/x | ✅ |
| ... | ... | ... | ... |
| **Total** | **x/x** | **x/x** | **x%** |
```

The cumulative table lives here and nowhere else. Update it when a chapter completes. Never duplicate it inside recap cells — duplicated tables drift out of sync.

---

## 🗂️ Format Rules

| Format | Used in | When |
|--------|---------|------|
| Prose | All lessons | Linear concepts, definitions |
| Markdown table | Classification lessons | 2–4 categories to compare |
| Mermaid diagram | `.md` files only | Chapter concept map — after chapter complete |

**No ASCII trees in notebooks.**

**`🔗 Connection`:** max 3 bullets, genuine cross-chapter/course links only. Skip if none.

**Chapter mental-shift line:** one italic sentence, lives in the `### Chapter X — Recap` cell — not the header, not a lesson cell.

---

## ✅ Cell Quality Checklist

Before inserting any cell into the notebook:

- [ ] Built from a screenshot (not inferred from title or prior knowledge)
- [ ] Heading format exact: `#### Chapter X — Lesson N: [Title] *(Type / XP)*`
- [ ] All required sections present in correct order
- [ ] `🎯 GOAL` = pedagogical purpose, not a topic summary
- [ ] `💡 Why this matters` = 1–2 sentences wisdom + Recruiter Q&A (3–4 lines total)
- [ ] `✅ RECAP` = max 4 bullets
- [ ] Solution table shows ALL options (Exercise/Practice)
- [ ] `**→**` wisdom line is action-oriented and trap-specific
- [ ] `🎬` link present in Video; absent in Exercise/Practice
- [ ] Cell inserted directly after the last completed lesson cell for this chapter
- [ ] Cell length: Video ≤ 40 lines · Exercise/Practice ≤ 50 lines

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
| Chapter separator or recap written mid-chapter | Separator goes in when the chapter starts; recap only after all lessons complete |
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
