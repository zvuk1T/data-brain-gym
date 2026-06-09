# Captain's Log — Stardate 20260609
**Date:** 9 June 2026
**Project:** data-brain-gym
**Session:** Data Literacy Professional — Course 1, Chapter 1 (L1–L6) + notebook template established

---

## 🎯 SESSION GOAL

Begin populating the `data-literacy-professional.ipynb` notebook with synthesised lesson content for Course 1: Introduction to Data.
Establish the lesson template that will be used for all future DataCamp theory notebooks.

---

## ✅ WHAT WE ACCOMPLISHED TODAY

### Part 1 — Session recovery
The previous chat session (same date, earlier) crashed with a `413 Request Entity Too Large` error — the context window was exhausted.
Data exported the full chat as a JSON file. Spock parsed it using Python (`tail` + `json.load`) to extract all 43 exchanges, identify where the session broke, and resume without losing any progress.

**Recovery method logged here as a repeatable pattern:**
```
# Extract last N characters to find where the chat ended
tail -c 5000 chat-export.json

# Parse all user messages + Spock responses for full session audit
python3 -c "
import json
with open('chat-export.json') as f:
    data = json.load(f)
for i, req in enumerate(data['requests']):
    print(f'[{i}]', req['message']['text'][:200])
"
```

---

### Part 2 — Core philosophy established

This session defined the guiding principle for all DataCamp notebook work:

> *"DataCamp provides the exercise. We provide what DataCamp cannot: your own reason why you know this."*

DataCamp is the base document. We add the retrieval + synthesis layer on top.
Every lesson asks a technical question. Our job is to answer the deeper set:
- Why does this concept exist?
- Who uses it in a real organisation?
- What decision does understanding it enable?

This sentence was also added to `datacamp/README.md`.

---

### Part 3 — Lesson template established

Through building L1–L6 organically from video transcripts and screenshots, we arrived at a stable template.

**Video lesson template:**
```
#### Chapter X — Lesson N: [Title] *(Video / XP)*

> 🎬 [Watch on DataCamp](URL) *(requires login)*

---

**🎯 GOAL — What is this lesson about?**
[1–2 sentence synthesis]

---

**📋 Key concepts covered:**
[numbered list with explanations]

[ASCII mental map — if the concept has a structure worth mapping]

---

**💡 Why this matters**
[business context, 1 paragraph]

**✅ RECAP**
[3–5 bullet points: key concept, common mistake, question to ask]
```

**Exercise / Practice template:**
```
#### Chapter X — Lesson N: [Title] *(Exercise or Practice / XP)*

> 🎬 [Watch on DataCamp](URL) *(requires login)*

---

**📋 Scenario**
[DataCamp scenario text]

**Task:** [What DataCamp asks]

---

**✅ Solution**
[Table: Item | Classification | Why]

---

**🧠 Mental Map** ← only when concept has a tree/hierarchy structure

[ASCII tree]

---

**💡 Why this matters**
[1 paragraph — business relevance]

**✅ RECAP**
[3–5 bullet points]
```

---

### Part 4 — ASCII mental map rule

**Rule:** Mental map only when there is a structure worth mapping.

| Use ASCII map | Skip ASCII map |
|--------------|----------------|
| Hierarchy or tree (Data Context, storage evolution) | Single question with one correct answer |
| Classification into categories (structured/unstructured, quant/qual) | Linear concept with no branches |
| Multi-level relationships between concepts | When the table already captures everything |

**Format rule:** ASCII in notebooks (renders everywhere, no dependencies). Mermaid in `.md` guide files only.

---

### Part 5 — Lessons completed: Course 1, Chapter 1 (ALL 10 ✅)

| # | Lesson | Type | XP | Status |
|---|--------|------|----|--------|
| 1 | Data basics | 🎬 Video | 50 | ✅ Done |
| 2 | Structured vs. unstructured | 📝 Exercise | 100 | ✅ Done |
| 3 | Quantitative vs. qualitative | 📝 Exercise | 100 | ✅ Done |
| 4 | Data context | 🔘 Practice | 50 | ✅ Done |
| 5 | The curious case of data growth | 🎬 Video | 50 | ✅ Done |
| 6 | Data storage capabilities | 📝 Exercise | 100 | ✅ Done |
| 7 | Making the right decisions | 🔘 Practice | 50 | ✅ Done |
| 8 | The value of data | 🎬 Video | 50 | ✅ Done |
| 9 | Data-driven vs. gut feelings | 📝 Exercise | 100 | ✅ Done |
| 10 | Data-driven decision making | 📝 Exercise | 50 | ✅ Done |

Chapter 1 complete. Session recovered after the 413 error — L7 screenshots were resent, L7–L10 added in the second chat session.

---

## 🧠 DECISIONS AND REASONING

| Decision | Reason |
|----------|--------|
| ASCII in notebooks, Mermaid in `.md` files | Mermaid does not render natively in Jupyter markdown cells in VS Code without extensions |
| Mental map per structure, not per exercise | A mental map of a single yes/no question adds noise, not value |
| Theory before code — finish foundations first | Spock recommendation from previous session: foundations give WHY, practical tracks give HOW. Without foundations, every query is just syntax |
| `data-spock-core.instructions.md` — not updated today | All relevant global rules already present. DataCamp-specific template is a project-level concern, not a global rule |
| `data-brain-gym/copilot-instructions.md` — updated | Added `datacamp/` to Project Structure + DataCamp Notebook Standard section |

---

## ⚠️ WHERE WE STOPPED

**Chapter 1 fully complete.** Next: Chapter 2 — Data Wisdom (9 lessons).

---

## 🔜 NEXT STEPS

1. ✅ Captain's log created and updated
2. ✅ `data-brain-gym/.github/copilot-instructions.md` updated
3. ✅ Chapter 1 — all 10 lessons complete
4. ⏳ Start Chapter 2: Data Wisdom — L1: Data wisdom (Video, 50 XP)

---

## ✅ Notes for Students

**On chat context limits:** Language model context windows have a hard size limit. Long sessions with large files (notebooks, JSONs, screenshots) fill the context faster than text-only sessions. When a session breaks with a `413` error, the work is not lost — VS Code exports the full chat history as JSON. Python can parse it in seconds.

**On the lesson template:** The template was not designed upfront — it emerged from doing the work. L1, L2, L3 were built first, patterns became visible, the rule was named after the pattern existed. This is the correct order: practice → pattern → principle. Trying to define the perfect template before writing a single lesson is a form of procrastination dressed as planning.

**On ASCII mental maps:** The goal of a mental map is to let you close your eyes and see the structure. If you can already see it from the table, the map adds nothing. Add it when the structure itself is the lesson.
