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
- `03-introduction-to-data-literacy.ipynb`: Ch1 complete (13 lessons, 800 XP) ✅ · **Ch2 complete (16 lessons, 1050 XP) ✅** — Ch3 not started

**Lesson status — Ch1 as of last chat break:**

| # | Lesson | Type | XP | Status |
|---|--------|------|----|--------|
| L1 | Why data literacy is an essential skill | 🎬 Video | 50 | ✅ |
| L2 | Defining data literacy | 📝 Exercise | 50 | ✅ |
| L3 | The data literacy toolbox | 📝 Exercise | 100 | ✅ |
| L4 | Data literacy in action | 🔁 Practice | 50 | ✅ |
| L5 | From data to insights | 🎬 Video | 50 | ✅ |
| L6 | DIKW pyramid as a process | 📝 Exercise | 100 | ✅ |
| L7 | What is insight? | 📝 Exercise | 50 | ✅ |
| L8 | The DIKW journey | 🔁 Practice | 50 | ⏳ next |
| L9 | Data-driven decision making | 🎬 Video | 50 | ⏳ |
| L10 | Becoming data-driven | 📝 Exercise | 50 | ⏳ |
| L11 | Facts & myths about being data-driven | 📝 Exercise | 100 | ⏳ |
| L12 | The data-driven process | 🔁 Practice | 50 | ⏳ |
| L13 | Fitting the problem statement | 🔁 Practice | 50 | ⏳ |

**Chapter 1 XP: 800 / 800 ✅**

| # | Lesson | Type | XP | Status |
|---|--------|------|----|--------|
| L8 | The DIKW journey | 🔁 Practice | 50 | ✅ |
| L9 | Data-driven decision making | 🎬 Video | 50 | ✅ |
| L10 | Becoming data-driven | 📝 Exercise | 50 | ✅ |
| L11 | Facts & myths about being data-driven | 📝 Exercise | 100 | ✅ |
| L12 | The data-driven process | 🔁 Practice | 50 | ✅ |
| L13 | Fitting the problem statement | 🔁 Practice | 50 | ✅ |
| — | **Chapter 1 Recap** | 🧠 Synthesis | — | ✅ |

---

## 🔜 NEXT STEPS

1. ✅ Create Course 3 notebook with header + Knowledge Map
2. ✅ Rename `foundations/` → `true-story-data/`
3. ✅ Update `know-thyself.md`
4. ✅ Write captain's log
5. ✅ **New chat opened — Course 3, Chapter 1 started**
   - Chat from 19 June (Part 1) broke after completing all admin (Course 3 notebook creation, folder rename, know-thyself update)
   - New chat opened same day — recovered via captain's log + notebook summary
   - Ch1 L1–L7 written and verified in the new chat session
   - **Chat broke again after L7** — new chat opened (this note)

6. ✅ **Ch1 L8–L13 completed + Chapter 1 Recap written** — new chat opened (this note)
   - L8: The DIKW journey · L9: Data-driven decision making · L10: Becoming data-driven
   - L11: Facts & myths about being data-driven · L12: The data-driven process · L13: Fitting the problem statement
   - Chapter 1 Recap written after L13 (deferred synthesis rule)
   - **Chapter 1 fully complete: 13 lessons, 800 XP ✅**

7. ✅ **Chapter 2 fully complete: 16 lessons, 1050 XP**
   - L1–L4 (data sources): open vs. internal · text as valid data · Eurostat as open data · classification exercise
   - L5–L8 (data types): structured/unstructured · quantitative/qualitative · mixed datasets
   - L9–L12 (managing data): DBMS · warehouse vs. lake · cloud trade-off · ETL pipeline · SQL · dashboards · tool classification
   - L13–L16 (data problems): dirty data · errors/missing/bias · consequences · Data Detective · cleaning myths
   - Chapter 2 Recap written after L16 (deferred synthesis rule)
   - **Chapter 2 fully complete: 16 lessons, 1050 XP ✅**

8. ✅ **Chapter 3 started — L1–L4 complete (descriptive analytics block)**
   - L1: Descriptive analytics (Video) — 4-type framework table + EDA deep dive + ice cream case study
   - L2: Reasons (not) to use descriptive analytics (Exercise) — hypothesis testing is NOT a use case
   - L3: Exploring the data (Practice) — EDA Explorer, student performance dataset, outlier detection
   - L4: Exploring connections (Practice) — Scatterplot Explorer, reading↔writing correlation, causality trap
   - All 4 cells written and verified ✅
   - **Chat context filling — new chat opened**

9. ⏳ **Next: Ch3 L5 — Diagnostic analytics (Video)**
   - Send screenshot for L5 in new chat to continue

---

## 📋 AGREED WORKFLOW FOR FUTURE COURSES (backbone rule)

> Before each new course: Data sends PDF slide decks → Spock extracts content → builds Course Knowledge Map cell → THEN screenshots begin.

This is the backbone. Not done for all courses in advance — done one course at a time, just before that course starts.

- Course 3 backbone: ✅ done today (Knowledge Map in notebook)
- Course 4 backbone: ⏳ when Course 3 is complete — Data sends PDF(s), Spock builds map, then screenshots begin

---

## 🏗️ ARCHITECTURE NOTE — Instruction Scoping (`applyTo`)

*Written end-of-session, 19 June 2026 — why `datacamp.instructions.md` does NOT load for DataLemur or Python practice.*

### The question
> "Why doesn't `datacamp.instructions.md` load when we work on DataLemur SQL drills or Python interview practice? Maybe it should?"

### The answer
The `applyTo: "datacamp/**"` glob in `datacamp.instructions.md` is architecturally correct — and intentional.

**Where each type of work lives:**

| Work type | Folder | `datacamp.instructions.md` loads? |
|-----------|--------|-----------------------------------|
| DataCamp coursework | `datacamp/**` | ✅ Yes |
| DataLemur SQL drills | `sql/datalemur/` | ❌ No — correct |
| Python interview practice | `python/problems/` | ❌ No — correct |
| Behavioural prep | `behavioural/` | ❌ No — correct |

**Why this is correct:**
`datacamp.instructions.md` contains rules that are 100% DataCamp-specific:
- Notebook cell structure for DataCamp lessons
- Screenshot → cell workflow
- PDF slide deck pre-loading rule (backbone rule)
- Course Knowledge Map format
- DataCamp XP / lesson metadata conventions

None of those rules apply to DataLemur drills or Python problems. If `datacamp.instructions.md` loaded everywhere, Spock would be carrying DataCamp-specific rules into contexts where they are irrelevant — wasting context budget and risking confusion.

**The only edge case:**
If DataCamp work were ever created *outside* `datacamp/` — that would contradict the folder architecture. The rule and the structure are aligned on purpose.

**In short:**
- `datacamp.instructions.md` + `applyTo: "datacamp/**"` = the right tool, in the right place, only when needed.
- DataLemur and Python practice have their own folder home. If they ever need scoped rules, a separate `datalemur.instructions.md` or `python.instructions.md` can be created the same way.

---

## 🔄 CONTEXT WINDOW MANAGEMENT — Why Chats Break and How to Prevent It

*Written 19 June 2026 — after three chat breaks in one day.*

### Why it happens
Every chat session has a finite context window — a token limit for how much text the model can hold in memory at once. In DataCamp sessions, this fills faster than average because:
- Each lesson cell is 400–800 words of structured content
- Screenshots add visual context on top
- Session recovery (reading notebook summaries, captain's logs) consumes tokens before the first lesson is written
- By lesson 7–10, the oldest messages start falling out — Spock begins compressing, missing details, eventually hitting the hard limit (413 error)

### Warning signs — act before the crash
| Signal | What it means | Action |
|--------|--------------|--------|
| Spock skips a detail it preserved earlier | Context compression has started | Finish the current lesson, then commit + new chat |
| Answers get shorter without reason | Old messages have fallen out of the window | Same — don't push further |
| Spock asks for a screenshot already sent | Early context is gone | Commit immediately, new chat |
| 413 error / conversation won't load | Context is full — hard limit hit | New chat, recover from captain's log |

### Prevention — the commit boundary rule
> **One chapter = one natural commit boundary = one chat session.**

- After every chapter is complete → commit → open new chat
- Do NOT push into the next chapter in the same chat
- If a chapter is long (15+ lessons), consider committing mid-chapter after a logical cluster (e.g., after a thematic block)

### Recovery protocol — when a new chat opens mid-chapter
1. Run the **new-session prompt** (`#file:new-session.prompt.md`) — reads the two latest captain's logs
2. Use `copilot_getNotebookSummary` to confirm which cells exist
3. Read the last written cell to confirm exact stopping point
4. Announce the next lesson and wait for confirmation before proceeding

This is faster than re-reading everything manually and costs fewer tokens than a full file read.

### The trade-off — why we don't just split every lesson into its own chat
Opening a new chat costs tokens for recovery (reading logs, reading notebook state). For 1–2 lessons, the recovery overhead can exceed the work. The right unit is a chapter or a meaningful thematic block — large enough to justify the recovery cost, small enough to complete before the window fills.

