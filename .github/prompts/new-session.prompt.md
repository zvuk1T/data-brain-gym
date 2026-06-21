---
mode: 'agent'
description: "Start a new working session — restore context, verify the stopping point, and wait for confirmation."
---

# New Session Bootstrap

Work in read-only mode until I explicitly confirm the next action.

Do not create, modify, rename, delete, commit, or push files.
Do not run commands that change the environment.

---

## Step 1 — Load project rules

Read:

1. `.github/copilot-instructions.md`
2. Any applicable instruction file under `.github/instructions/` for the active working folder

If the current work is inside `datacamp/`, also read:

- `.github/instructions/datacamp.instructions.md`

Treat these files as the source of truth for project rules, workflow, formatting, and confirmation requirements.

---

## Step 2 — Restore recent session context

Read the two latest files from `captains-log/`, determined by the two highest stardate numbers.

Read the older one first, then the newer one.

Extract:

- the active project, track, course, and chapter;
- the last completed task or lesson;
- the exact next step;
- unresolved decisions, warnings, or open questions;
- the active file or notebook mentioned in the latest log.

Do not rely only on the captain’s log. Use it as a recovery map, then verify the current state against the source files.

---

## Step 3 — Verify the active source file

Identify the active file mentioned in the latest captain’s log and inspect it directly.

For DataCamp work:

1. Read the course header in the active notebook.
2. Confirm the active course and chapter.
3. Identify the exact last completed lesson cell.
4. Confirm the exact next unfinished lesson.
5. Check whether the Course Knowledge Map already exists.
6. Confirm whether the next lesson is a Video, Exercise, or Practice lesson.
7. Include the lesson XP when available.
8. Do not create lesson content without the required screenshot source.

If the captain’s log and the notebook disagree, treat the notebook as the source of truth and clearly report the discrepancy.

---

## Step 4 — Report the restored state

Respond only in this format:

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

---

After the summary, stop and wait for my explicit confirmation before doing anything else.
