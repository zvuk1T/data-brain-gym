# Captain's Log — Stardate 20260608
**Date:** 8 June 2026
**Project:** data-brain-gym + know-thyself-data
**Session:** Problem-Solving Standard — Universal Learning Frame

---

## 🎯 SESSION GOAL

Define and formalise a universal problem-solving structure that applies to every file in the project — SQL scripts, notebook exercises, and `.md` guides — so that each file functions as a self-contained mini-lesson.

---

## ✅ WHAT WE ACCOMPLISHED TODAY

### Trigger
Data observed that `create-database.sql` had documentation (Notes for Students) but no structured learning frame at the top. The broader question: do we have a consistent standard for how to approach and document any problem — regardless of file type?

### Audit of existing rules
Found that relevant rules were already present but fragmented across 4 separate sections in `data-spock-core.instructions.md`:
- `📚 Learning Rules` — WHY before HOW, line-by-line, Mental Model
- `🗺️ Mental Map Rule` — ASCII tree / Mermaid after complex explanations
- `📖 Student-Friendly Documentation Rule` — guide format with Notes for Students
- `Notebook Exercise Standard` — task, instructions, Hint, Why this matters (added 7 June)

None of these explicitly defined how to open a file — what comes first, what structure to follow.

### Decision — terminology
Adopted the term **Problem-Solving Standard** (also known in pedagogy as a Learning Frame, and in engineering as Definition of Done). Named it `📐 Problem-Solving Standard — Universal Learning Frame` in core instructions.

### New section added to `data-spock-core.instructions.md`
Added `📐 Problem-Solving Standard` between `Mental Map Rule` and `Code & Command Rules`.

**The 5 blocks — applies to all file types:**

| Block | Purpose |
|-------|---------|
| 🎯 GOAL | What are we solving and why does it matter? |
| 🔧 APPROACH | What tools, technique, or SQL pattern will we use? |
| 💡 SOLUTION | The actual code / query |
| 🔍 WALKTHROUGH | Every step explained briefly (WHY, not just WHAT) |
| ✅ RECAP | Key concept + most common mistake + what to remember |

**Mapping to file types:**

| File type | Implementation |
|-----------|---------------|
| `.ipynb` notebook | Markdown cell: GOAL + APPROACH + hints; Code cell: SOLUTION + inline comments; follow-up markdown: RECAP |
| `.sql` script | Header comment: GOAL + APPROACH; inline comments: WALKTHROUGH; footer comment: RECAP / Notes for Students |
| `.md` guide | Full sections: What (GOAL), Method (APPROACH), Steps (SOLUTION + WALKTHROUGH), Notes for Students (RECAP) |

### `create-database.sql` updated
Added `🎯 GOAL` and `🔧 APPROACH` blocks to the file header — the file now opens with a learning frame, not just a technical comment.

---

## 🧠 DECISIONS AND REASONING

| Decision | Reason |
|----------|--------|
| Single universal standard, not per-file-type rules | Consistency — same mental model regardless of what you open |
| 5 blocks, not more | Enough to be complete; few enough to remember without looking up |
| WALKTHROUGH explains WHY, not just WHAT | The most common failure in documentation is describing steps without explaining reasoning |
| Standard described as "umbrella" over existing rules | Existing rules (Mental Map, Notes for Students, etc.) are still valid — the Standard frames them |
| `create-database.sql` is in `datacamp/` (gitignored) | File is local-only — copyright protection. Notes are for local learning, not for public commit |

---

## 🔜 NEXT STEPS

1. Commit `data-spock-core.instructions.md` in `know-thyself-data`
2. Apply the 5-block standard retroactively to Exercise 2 and 3 markdown cells in the notebook (add GOAL + APPROACH + RECAP where missing)
3. Continue populating exercises from screenshot — Exercise 4 onwards

---

## ✅ Notes for Students

The Problem-Solving Standard is not bureaucracy. It is a forcing function.

When you write the GOAL block first, you have to be able to state in one or two sentences what you are actually trying to do. If you cannot do that, you are not ready to write the query yet. The GOAL forces clarity before effort.

The WALKTHROUGH block forces you to explain WHY each line exists. This is the difference between a solution and a lesson. Anyone can copy a working query. Understanding why each clause is there — that is the skill that transfers to the next problem.

The RECAP is the most skipped block in real projects. It is also the most valuable one six months later. Write it as if you are leaving a note for the version of yourself who will read this file again and remember nothing.
