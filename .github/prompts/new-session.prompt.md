---
mode: 'agent'
description: "Start a new working session — restore context, verify the stopping point, and wait for confirmation. This version also loads user-level instructions and scoped instruction files, then verifies the active notebook via copilot_getNotebookSummary."
---

# New Session Bootstrap (Extended)

Work in read-only mode until I explicitly confirm the next action.

Do not create, modify, rename, delete, commit, or push files.
Do not run commands that change the environment.

---

## Step 1 — Load project and user rules (source-of-truth)

Read, in this exact order:

1. User-level instructions (always present via symlink):
   - `~/.copilot/instructions/data-spock-core.instructions.md`

2. Project-level instructions for the current workspace:
   - `<repo>/.github/copilot-instructions.md`

3. All folder-scoped instruction files inside the repo:
   - `<repo>/.github/instructions/*.instructions.md`
   - Load each file whose frontmatter `applyTo` matches the active file path.

If the current active file is inside `datacamp/`, also read:

- `.github/instructions/datacamp.instructions.md`

Treat these files as the source of truth for project rules, workflow, formatting, confirmation requirements, and folder-specific templates.

Note: Read each file from start to finish. Do not summarise until all required files are fully read.

---

## Step 2 — Restore recent session context (captain's logs)

Read the two latest files from `captains-log/`, determined by the two highest stardate numbers. Read the older one first, then the newer one.

Extract:

- the active project, track, course, and chapter;
- the last completed task or lesson;
- the exact next step;
- unresolved decisions, warnings, or open questions;
- the active file or notebook mentioned in the latest log.

Do not rely only on the captain’s log. Use it as a recovery map, then verify the current state against the source files.

---

## Step 3 — Verify the active source file (notebook-aware)

If the active file from the captain's log is a DataCamp notebook, do the following verification steps.

1. Identify the active notebook path mentioned in the latest log. If none is specified, find the most recently modified notebook in `datacamp/**`.

2. Use the `copilot_getNotebookSummary` tool on the identified notebook. Extract the summary including number of cells, types, and the last-written cells.

3. Read the course header (Cell 1) in the notebook and confirm:
   - Course title, instructor, chapters, and overall XP/status.
   - Whether a Course Knowledge Map (Cell 2) exists and contains PDF-extracted anchors.

4. Identify the exact last completed lesson cell (the last lesson-style markdown cell written). Read that cell fully.

5. Confirm the exact next unfinished lesson (title, lesson type: Video / Exercise / Practice, XP when available).

6. Confirm whether the next lesson requires a screenshot (exercises/practices always require screenshots; video lessons require a transcript or video slide screenshot if available).

If the captain's log and the notebook disagree, treat the notebook as the source of truth and clearly report the discrepancy.

---

## Step 4 — Report the restored state (strict format)

Respond only in this format (no additional prose):

**📍 Where we are:**  
[Current project, track, course, chapter, and overall status]

**✅ Last completed:**  
[Exact last completed lesson or task]

**🔜 Next step:**  
[Exact next lesson or task, including lesson type and XP when applicable]

**📚 Context loaded:**  
[List the instruction files, captain’s logs, and active source file that were read]

**⚠️ Open questions or discrepancies:**  
[List unresolved issues or differences between the captain’s log and source files. Write “None” if there are none.]


After the summary, stop and wait for my explicit confirmation before doing anything else. Any affirmative response — in any language — indicates readiness to proceed. No need for specific words.

---

## Implementation notes for agents

- Always read user-level instructions first — they contain HARD RULES (confirmation, captain's log rule, language rules).
- Always call `copilot_getNotebookSummary` when working with notebooks referenced in the captain's logs — do not skip this step.
- If `copilot_getNotebookSummary` returns an error or the notebook cannot be found, clearly state the problem and list candidate notebooks by recent modification time in `datacamp/**`.
- Do not create lesson content without a screenshot. If the next lesson requires a screenshot, request it and stop.
