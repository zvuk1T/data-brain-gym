# Captain's Log — Stardate 20260610
**Date:** 10 June 2026
**Project:** data-brain-gym
**Session:** Session recovery + PDF pre-loading pattern + notebook restrukturiranje + scoped folder instructions

---

## 🎯 SESSION GOAL

Resume from the 413 crash of the previous session. Recover context, understand what was done, and establish better structural patterns before continuing Course 2 lesson work.

---

## ✅ WHAT WE ACCOMPLISHED TODAY

### Part 1 — Session recovery after 413 crash

The previous chat session (same date, Stardate 20260609 continuation) crashed with a `413 Request Entity Too Large` error. The notebook was in an intermediate state — Course 2 had been started but only 1 lesson was complete.

Recovery method: Spock read git status, read notebook cell summaries, and read the last cell of both notebooks to reconstruct exactly where the session ended.

**State found after crash:**
- `data-literacy-professional.ipynb` — deleted (restrukturiranje happened in the crashed session)
- `01-introduction-to-data.ipynb` — 33 cells, Course 1 fully complete (31 lessons, 2000 XP)
- `02-communicating-data-insights.ipynb` — 2 cells: course header + Ch1 L1 only
- All changes unstaged, none committed

**Exact stopping point:** Course 2, Chapter 1, Lesson 1 complete. Next: Ch1 L2.

---

### Part 2 — PDF pre-loading pattern established

Instead of starting lesson work immediately, Data proposed a structural improvement: read the instructor's slide decks (PDF format) before any screenshot arrives. This creates pre-loaded context for the entire course.

**Method used:**
```bash
python3 -c "
import subprocess
for pdf in ['chapter1.pdf', 'chapter2.pdf', 'chapter3 (1).pdf']:
    result = subprocess.run(['pdftotext', '-layout', pdf, '-'], capture_output=True, text=True)
    print(result.stdout)
"
```

Three PDF slide decks for Course 2 were parsed: Chapter 1 (4 video lessons), Chapter 2 (4 video lessons), Chapter 3 (4 video lessons). All key concepts, examples, best practices, and the Buildingsway running example were extracted and understood before any screenshot was provided.

**Pattern name:** PDF pre-loading as course-level RAG.

The pre-loaded knowledge was added to the notebook as a **Course Knowledge Map** cell — a dedicated cell placed immediately after the course header, before any lesson cell. It contains:
- Course arc: how the 3 chapters build on each other
- Key concepts per video lesson, extracted from slides
- Running example (Buildingsway) documented as a named anchor

**Why this matters:**
- When a screenshot arrives, Spock already knows what is in the lesson — the screenshot confirms details and adds exercises, it does not have to build context from scratch
- Reduces session length (fewer back-and-forth messages to establish context)
- Reduces the risk of another 413 crash mid-chapter
- Makes the notebook self-documenting — a reader can understand the course arc from the Knowledge Map alone

---

### Part 3 — Scoped folder instructions pattern identified

While discussing where to place DataCamp-specific Copilot instructions, a VS Code best practice was identified and named:

**Pattern:** Scoped folder instructions via `.github/instructions/<name>.instructions.md` with `applyTo: "<folder>/**"`

```
.github/instructions/datacamp.instructions.md
---
applyTo: "datacamp/**"
---
```

VS Code automatically loads this file only when the active file is inside the `datacamp/` folder. It does not pollute the context when working on SQL drills, behavioural exercises, or Python problems.

**Why this is better than the global copilot-instructions.md:**
- Global `.github/copilot-instructions.md` loads for every file in the workspace
- DataCamp notebook template rules (screenshot workflow, PDF pre-loading, chapter deferred intro/recap) are irrelevant outside `datacamp/`
- Scoped instructions keep each folder's context clean and relevant
- Same VS Code mechanism already used for user-level shared instructions — this applies it at the project-subfolder level

**Decision logged:** The `datacamp/` folder will have its own `.github/instructions/datacamp.instructions.md`. Creation deferred — DataCamp-specific rules are currently in the global copilot-instructions.md and will be migrated when the content stabilises.

---

### Part 4 — `datacamp.instructions.md` created

`data-brain-gym/.github/instructions/datacamp.instructions.md` created with `applyTo: "datacamp/**"`.

Content built from three sources: real notebook cells (Course 1 practice), both instructions files, and DataCamp README. It is designed as a complete operational manual for DataCamp work — not a list of rules but a system.

Key sections:
- **Pre-Session Workflow** — what to do before any screenshot arrives (read course outline, check for PDFs, confirm position)
- **Screenshot Workflow** — the only source of lesson content; what a complete screenshot set looks like; what to do when missing
- **Video / Exercise Templates** — complete templates with all rules inline
- **ASCII Map Rules** and **Callout Rules** — precise, conditional
- **Why This Matters Rules** — not a summary, a reason to care
- **Deferred Intro/Recap Rule** — never write chapter intro before all lessons are complete
- **❌ Mistakes to Never Repeat** — table of every mistake discovered during Course 1 with the corrective rule alongside it
- **413 Prevention** — symptoms, prevention, recovery
- **Session End Checklist** — commit format, what to verify

The `❌ Mistakes` section directly addresses the need to not repeat the same errors: `🎬` link in exercise cells, map on single-answer questions, numbered list alongside a map, chapter intro written mid-chapter, building cells from lesson titles without screenshots.

---

### Part 5 — Where does the scoped instructions documentation live?

Question raised: should the scoped folder instructions pattern be documented in `datacamp.instructions.md`, `copilot-instructions.md`, or `docs/`?

**Answer:** `know-thyself-data/docs/repo-architecture.md` — and it was already there.

Reasoning:
- `repo-architecture.md` already had a section "How File-Scoped Instructions Work" with the `applyTo: '**/know-thyself.md'` example
- Our pattern today (`applyTo: 'datacamp/**'`) is the same mechanism, broader scope — Variant B of the same concept
- `instructions.md` files are operational rules for the model; `docs/` files are architectural documentation for humans
- The docs/ home means the pattern is accessible in any future project setup, not buried inside one repo's instructions

---

### Part 6 — `repo-architecture.md` updated in `know-thyself-data`

`know-thyself-data/docs/repo-architecture.md` updated to document both variants of the scoped instructions pattern:

**What changed:**
- Section renamed from "How File-Scoped Instructions Work" → "How File-Scoped and Folder-Scoped Instructions Work"
- Variant A (file-scoped): unchanged — `applyTo: '**/know-thyself.md'`
- Variant B (folder-scoped) added: `applyTo: 'datacamp/**'` — with concrete example, when to use, and mental model
- Mental model added showing the three-layer hierarchy:
  ```
  ~/.copilot/instructions/*.instructions.md   → ALL workspaces, ALL files
  .github/copilot-instructions.md             → ALL files in THIS repo
  .github/instructions/<name>.instructions.md → ONLY where applyTo matches
  ```
- Final `.github/` structure diagram updated — `datacamp.instructions.md` added with `applyTo` annotation
- Manual sync table updated — folder-scoped added as separate row

This change lives in `know-thyself-data` (private repo) and needs its own commit there.

---

## 🧠 DECISIONS AND REASONING

| Decision | Reason |
|----------|--------|
| PDF pre-loading before screenshots | Reduces context load per session; pre-loads course arc; enables faster, higher-quality synthesis when screenshot arrives |
| Course Knowledge Map as dedicated notebook cell | Visible to both Spock and Data in the notebook; survives session crashes; does not depend on chat history |
| Per-course notebook files (`01-...`, `02-...`) instead of one monolithic file | Course 1 notebook alone is 1467 lines. One file for all 8 courses would hit context limits before Course 3. Per-course files keep context manageable |
| Scoped folder instructions over global | Global instructions load for every file — DataCamp rules are not relevant outside datacamp/. Scoped loading keeps context clean |
| Principle added to data-spock-core.instructions.md | This pattern is not DataCamp-specific — it applies to any project where different subfolders have different workflows. Must be documented at the global level |
| Scoped instructions documented in repo-architecture.md, not in instructions files | Instructions files are operational rules for the model. Architecture documentation belongs in docs/ — accessible for any future project, not buried in one repo's instructions |
| `datacamp.instructions.md` is a complete operational manual, not a rule list | Built from three sources: real notebook cells, instructions files, README. The ❌ Mistakes section is the most valuable — it documents what went wrong in practice, not what we planned in theory |

---

## ⚠️ WHERE WE STOPPED

Session focused entirely on architecture, documentation, and pattern work. No new lesson cells added today.

**Files created/updated this session:**
- `data-brain-gym/.github/instructions/datacamp.instructions.md` — created ✅ committed ✅
- `data-brain-gym/captains-log/captains-log-stardate-20260610.md` — created ✅ committed ✅ (this file, updated after commit)
- `know-thyself-data/docs/repo-architecture.md` — updated, **needs commit in know-thyself-data**
- `know-thyself-data/copilot/data-spock-core.instructions.md` — updated (scoped instructions table row), **needs commit in know-thyself-data**

**Current state of notebooks:**
- `01-introduction-to-data.ipynb`: Course 1 fully complete (31 lessons, 2000 XP) — chapter intro/recap cells not yet written
- `02-communicating-data-insights.ipynb`: Course header + Course Knowledge Map + Ch1 L1 — Ch1 L2 onwards not yet written

---

## 🔜 NEXT STEPS

1. ✅ Create `data-brain-gym/.github/instructions/datacamp.instructions.md`
2. ✅ Commit all data-brain-gym changes
3. ⏳ Commit `know-thyself-data` changes — `repo-architecture.md` + `data-spock-core.instructions.md`
4. ⏳ Continue Course 2, Chapter 1 — Lesson 2: Communication types *(Exercise / 50 XP)*
5. ⏳ Chapter intro/recap cells for Course 1 (Ch1, Ch2, Ch3) — deferred per deferred synthesis rule
6. ⏳ Continue Course 2 through all 3 chapters + chapter intro/recap cells

---

## ✅ Notes for Students

**On pre-loading course content from PDFs before screenshotting:**
The instinct is to start immediately — take a screenshot, paste it, get the cell. That works, but it means every screenshot arrives cold: Spock has no course context, must infer from the slide what the lesson is about, and the synthesis is shallower. Pre-loading the PDF slide decks inverts this. The course arc is understood before the first screenshot. Each screenshot then becomes a confirmation pass, not a discovery pass. The depth of synthesis increases, and the session is shorter because less context needs to be re-established per lesson.

**On scoped folder instructions:**
VS Code's `applyTo` frontmatter in `.github/instructions/` files is a mechanism for context hygiene. Not every rule applies everywhere. A rule that says "always ask for a screenshot before writing lesson content" is irrelevant in a SQL drill notebook. Scoping instructions to the folder where they apply keeps the model focused and reduces the risk of applying the wrong workflow to the wrong task. The principle: every folder that has a distinct workflow deserves its own instruction file.

**On session crashes (413 errors):**
A 413 crash means the request exceeded the model's context window. It is not a data loss event — it is a size event. All work written to files survives. The recovery is: read git status, read notebook summaries, read the last cell, and reconstruct the stopping point. This takes 2-3 minutes. The only unrecoverable thing is the in-context reasoning from the crashed session — which is why decisions must always be written into files (captain's logs, instruction files) and not left only in chat.
