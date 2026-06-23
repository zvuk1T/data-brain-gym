---
applyTo: "datacamp/**"
---

# Haiku Working Instructions
## data-brain-gym — DataCamp notebook guardrails

---

## 🔴 HARD STOPS — Check Before Every Action

| Forbidden action | No exception |
|-----------------|-------------|
| Call `edit_notebook_file` without a screenshot present in this conversation | None |
| Add more than one lesson cell per message | None |
| Continue to the next lesson without explicit user confirmation | None |
| Generate any cell from a title, prior knowledge, or inference | None |
| Create a new notebook file without explicit user instruction | None |
| Add mastery statement or recap before the chapter is fully complete | None |

### ✅ Pre-edit checklist — run before every `edit_notebook_file` call

If any item fails → state what is missing and stop. Do not call `edit_notebook_file`.

- [ ] Screenshot present in this conversation for this specific lesson?
- [ ] Only one lesson being added?
- [ ] User confirmed to continue (any affirmative response)?
- [ ] Insertion point correct — directly after the last completed lesson cell for this chapter?

---

## 🔵 Session Start Protocol — Do This First, Every Time

1. Read `datacamp/true-story-data/data-literacy-professional/04-introduction-to-statistics.ipynb` — find the last cell whose heading matches `#### Chapter X — Lesson N:`.
2. State: chapter number, lesson number, title, type (Video / Exercise / Practice), XP.
3. Say: *"Ready. Next lesson is Chapter X, Lesson N: [Title] (Type / XP). Send the screenshot when ready."*
4. Stop. Wait for a screenshot before writing any lesson content.

If the notebook cannot be found: list `.ipynb` files in `datacamp/**`. Do not guess.
If the last cell is a mastery statement: the chapter is complete — state the next chapter and first lesson.

---

## 🚫 Screenshot Rule

Never generate lesson content without a screenshot. Every cell is built from what the screenshot shows — not from the lesson title, prior knowledge, or the course outline.

If no screenshot: state the lesson title and type → say *"Screenshot required before I can build this cell."* → stop.

---

## 📐 Cell structure, templates, quality rules, and format

→ All defined in `datacamp.instructions.md`. Read that file before building any cell.
