# Captain's Log — Stardate 20260619
**Date:** 19 June 2026
**Project:** data-brain-gym
**Session:** Folder restructure + Course 3 notebook creation + know-thyself update

---

## 🎯 SESSION GOAL

1. Create Course 3 notebook (`03-introduction-to-data-literacy.ipynb`) with course header and Knowledge Map
2. Reorganise the `datacamp/foundations/` folder — rename and clean up structure
3. Update `know-thyself.md` to reflect the new `true-story-data` philosophy

---

## ✅ WHAT WE ACCOMPLISHED TODAY

### Part 1 — Course 3 notebook created

- Extracted text from all 4 chapter PDFs for Course 3 (*Introduction to Data Literacy*)
- Created `03-introduction-to-data-literacy.ipynb` with:
  - **Cell 1 — Course header:** metadata, 5 learning objectives (Assess / Define / Differentiate / Identify / Recognize), chapter tables for all 4 chapters (61 lessons, 4000 XP)
  - **Cell 2 — Course Knowledge Map:** full ASCII synthesis from all 4 PDFs
    - Ch1: data literacy definition, DIKW pyramid, data-driven decision making
    - Ch2: data sources, structured/unstructured, quantitative/qualitative, managing data, dirty data
    - Ch3: 4 analytics types (descriptive / diagnostic / predictive / prescriptive) with decision rule
    - Ch4: visualizations, McCandless technique, storytelling components, 3 keys framework
- Committed: `4c5487d`

---

### Part 2 — Folder rename: `foundations/` → `true-story-data/`

**What changed:**
- `datacamp/foundations/` → `datacamp/true-story-data/` (via `git mv` — history preserved)
- `03-introduction-to-data-literacy/` → `03-introduction-to-data-literacy-assets/` (consistent naming pattern, gitignored)
- Updated references in:
  - `datacamp/README.md` — folder map + section heading
  - `.github/copilot-instructions.md` — sidebar structure
  - `.github/instructions/datacamp.instructions.md` — folder map + naming example
- Committed: `a4808f6`

**Rationale for the name:**
`true-story-data` — inspired by "based on a true story". The 3 theory tracks are the real story behind all data work. Before writing a single SQL query, you understand what data is, how it is read, how it is communicated, what it means inside an organisation. Theory before code is not a soft preference — it is a hard architectural rule.

The name also reflects the storytelling-first philosophy: data without a narrative is noise. Storytelling was Data's primary motivation for these tracks, and the folder name reflects that.

---

### Part 3 — `know-thyself.md` updated

Two changes committed to `know-thyself-data` (commit `26fcbc0`):

1. **Section 0G table** — `data-brain-gym` description updated to reflect `true-story-data` architecture and learning philosophy
2. **DataCamp strategy section** — new `true-story-data` philosophy block added:
   - What the name means and where it comes from
   - Why theory precedes code (hard architectural rule, not preference)
   - Connection to Žarko's core working pattern: understand the system before operating it
   - Storytelling-first philosophy: data without narrative = noise

---

## 🧠 DECISIONS AND REASONING

| Decision | Reason |
|----------|--------|
| Rename `foundations/` → `true-story-data/` | "foundations" sounds hierarchical/academic; "true-story-data" sounds like identity + reflects storytelling-first philosophy |
| Assets naming pattern `*-assets/` (Option B — distributed) | PDFs sit next to their notebook; one gitignore rule; already consistent with Course 2 |
| No stub notebooks created today | Agreed: stubs are created one course at a time, just before the session that needs them — not all upfront |
| `know-thyself.md` update: 2 targeted edits | true-story-data philosophy belongs in the private source of truth, not in processing instructions |
| `data-spock-core.instructions.md` — no changes | Philosophy is architectural/identity, not a process rule — wrong file |

---

## ⚠️ WHERE WE STOPPED

All commits done. Chat is full — closing this session and opening a new one.

**Files modified this session:**
- `datacamp/true-story-data/data-literacy-professional/03-introduction-to-data-literacy.ipynb` — created ✅ committed ✅
- `datacamp/true-story-data/data-literacy-professional/03-introduction-to-data-literacy-assets/` — folder renamed ✅
- `datacamp/README.md` — updated ✅ committed ✅
- `.github/copilot-instructions.md` — updated ✅ committed ✅
- `.github/instructions/datacamp.instructions.md` — updated ✅ committed ✅
- `know-thyself-data/source-of-truth/know-thyself.md` — updated ✅ committed ✅
- `captains-log/captains-log-stardate-20260619.md` — this file

**Current notebook state:**
- `01-introduction-to-data.ipynb`: Course 1 complete (31 lessons, 2000 XP) — Ch intro/recap cells deferred
- `02-communicating-data-insights.ipynb`: Course 2 complete (38 lessons, 2600 XP) ✅
- `03-introduction-to-data-literacy.ipynb`: Course header + Knowledge Map ready. **No lesson cells yet.** 🔄

---

## 🔜 NEXT STEPS

1. ✅ Create Course 3 notebook with header + Knowledge Map
2. ✅ Rename `foundations/` → `true-story-data/`
3. ✅ Update `know-thyself.md`
4. ✅ Write captain's log
5. ⏳ **Open new chat — start Course 3, Chapter 1**
   - Next lesson: **Chapter 1 — Lesson 1: Why data literacy is an essential skill** *(Video / 50 XP)*
   - Workflow: Data sends PDF(s) for that course → Spock pre-loads Knowledge Map → Data sends screenshot of lesson → Spock builds cell
   - Note: for Course 3, the Knowledge Map is already in the notebook (Cell 2). PDFs were pre-loaded today.
   - So: next session starts directly with L1 screenshot — no PDF step needed for Course 3.

---

## 📋 AGREED WORKFLOW FOR FUTURE COURSES (backbone rule)

> Before each new course: Data sends PDF slide decks → Spock extracts content → builds Course Knowledge Map cell → THEN screenshots begin.

This is the backbone. Not done for all courses in advance — done one course at a time, just before that course starts.

- Course 3 backbone: ✅ done today (Knowledge Map in notebook)
- Course 4 backbone: ⏳ when Course 3 is complete — Data sends PDF(s), Spock builds map, then screenshots begin
