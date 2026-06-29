# Captain's Log — Stardate 20260629
**Date:** 29 June 2026
**Project:** data-brain-gym — Course 4: Introduction to Statistics
**Session:** Chapter 4 Lessons 6–12 + instruction-system cleanup

---

## 🎯 SESSION GOAL

Advance Chapter 4 (Correlation and Hypothesis Testing) with screenshot-verified
lessons, and harden the instruction system against two recurring frictions: a
non-deterministic notebook-summary cadence rule and an obsolete model-specific
instruction file.

---

## SESSION PART 1 — Chapter 4 Lessons 6–12 (Screenshot-Verified)

| Lesson | Type | XP | Topic | Trap captured |
|--------|------|-----|-------|---------------|
| **L6** | Exercise | 100 | Recognizing controlled trials | Recorded ≠ assigned — smoking survey is observational |
| **L7** | Exercise | 50 | Why use randomization? | "Best describes" = most complete; option 1 is a partial truth |
| **L8** | Video | 50 | Correlation | Pearson r = magnitude (strength) + sign (direction); correlation ≠ causation |
| **L9** | Practice | 50 | Identifying correlation | Visible trendline ≠ strong; 0.66 is moderate |
| **L10** | Exercise | 50 | What can correlation tell you? | "causes" vs. "related to"; DataCamp's own feedback wording was contradictory |
| **L11** | Exercise | 50 | Confounding variables | Confounder needs BOTH tests; matched smoking is controlled |
| **L12** | Video | 50 | Interpreting hypothesis test results | p-value = P(data \| H₀), not P(H₀ true); "fail to reject" ≠ "accept" |

**Block subtotal: 400 XP.** Exercise/Practice cells carry a `Common Mistake`
block where a wrong-attempt screenshot existed (L6, L7, L10, L11). L9 was correct
on first try → no `Common Mistake` block, per template.

### Wisdom extracted
- **L6:** One test for a controlled trial — *did the experimenter assign the treatment?* Historic/observed/self-selected data → observational.
- **L7:** In a "best describes" question, read "best" as "most complete." Option 3 was the CLT, option 5 was blinding — neither is randomization.
- **L8:** A correlation coefficient answers *how linear, which direction* — never *does A cause B.* Reflex on any strong r: *what confounder affects both?*
- **L9:** Two-step decode of any coefficient — sign for direction, magnitude for strength. Scatter is the visual tell that a relationship isn't strong.
- **L10:** Correlation licenses exactly two claims — a relationship exists + its direction. Filter: delete every "causes" option first, then check direction.
- **L11:** A confounder must affect the outcome AND differ between groups. "Similar X across groups" is an explicit controlled-variable flag.
- **L12:** Decision rule p ≤ α → reject H₀. Type I = false positive, Type II = false negative.

### L10 — the dangerous confusion (worth recording)
Data flagged genuine confusion here. Two stacked traps: (1) options 1 and 4
differed by only two words ("causes" vs. "is related to"); (2) DataCamp's
wrong-answer feedback called water cost the "independent" variable, contradicting
L9's own Correlation Explorer axis labels (y-axis = dependent) and the L1 axis
convention. Conclusion: a likely DataCamp typo for *dependent* — the confusion
was their wording, not Data's logic. The lesson cell documents both traps so the
record is honest about the source-side error.

---

## SESSION PART 2 — Instruction-System Cleanup

### Cadence rule made deterministic (`datacamp.instructions.md`)
The notebook-summary cadence rule previously re-fetched "if the injected context
indicates the user reordered or deleted cells" — which relied on judgment to
separate the harness's routine *"potentially reordered"* notice from a real
signal. That judgment failed twice in one session (two redundant summary calls).
Rewrote to two concrete triggers: (a) context **explicitly names** a
reorder/deletion, or (b) the `edit_notebook_file` return value shows unexpected
neighbours. Added an explicit clause that the routine harness notice does **not**,
on its own, count as a trigger. Self-correcting rule fix — same pattern as the
screenshot rule (added after fabrication) and the original cadence rule.

### Deleted `haiku.instructions.md`
Data is no longer working with the Haiku model, so the model-specific guardrail
file (HARD STOPS table, pre-edit checklist, session-start protocol) is redundant.
Audited every rule first: each survives in its canonical home — hard-rules
(screenshot, one-cell, confirm), `datacamp.instructions.md` (Pre-Insertion Gate,
templates), and `new-session.prompt.md` (bootstrap). Zero rule loss. Only
remaining reference is a historical captain's-log note (correct as history).
`.github/instructions/` now holds a single file: `datacamp.instructions.md`.

---

## SESSION PART 3 — Chapter 4 Lessons 13–15 + Course 4 Complete

| Lesson | Type | XP | Topic | Trap captured |
|--------|------|-----|-------|---------------|
| **L13** | Exercise | 100 | Significance levels vs. p-values | α and p are both 0–1 probabilities → bucket by *timing*, not scale |
| **L14** | Exercise | 50 | Type I and type II errors | Heavy overlap = fail to reject; an H₁ tempts you to "confirm" a noise-sized gap |
| **L15** | Video | 50 | Congratulations! | — (course capstone recap) |

**Block subtotal: 200 XP.** L13 and L14 carry a `Common Mistake` block from the
wrong-attempt screenshots. L15 is the closing video → no exercise sections.

### Wisdom extracted
- **L13:** α is the bar set *before* data; the p-value is the number returned *after*. "Set vs. calculated" is the cleanest separator — both being probabilities on the same scale is exactly the trap.
- **L14:** Substantial overlap of sampling distributions → fail to reject H₀. "Fail to reject" ≠ "proven equal." Bonus tell: the faint visible gap here favored Madrid, the opposite of the Berlin-heavier H₁ — so rejecting was wrong twice over.
- **L15:** The course arc in one line — describe (Ch1) → model uncertainty (Ch2–3) → conclude (Ch4). Hypothesis testing is the bridge from sample to population claim.

### Course 4 closed
All 56 lessons populated. Added the `### Chapter 4 — Recap` cell (mental-shift +
950/950 XP). Synced the progress table (Cell 2) to 56/56 · 3,450/3,450 · 100% and
flipped the Cell 1 header status to ✅ Complete. **Introduction to Statistics is
done.**

### New rule — "Naming Lessons in Chat" (`datacamp.instructions.md`)
Added a section requiring lessons to be named with **both number and title** in
chat (e.g. "Chapter 4 — Lesson 13: Significance levels vs. p-values"), never the
bare number — Data locates lessons by title, not index. Self-correcting rule fix,
prompted by Data. NOTE: the section's heading emoji rendered as a broken glyph
through the edit toolchain (same bug as the earlier `🗂️` case) — Data is fixing
the glyph manually.

### Course 5 prep — research only (no files created)
Gathered the full outline for **Course 5: Introduction to Data Culture** (Joanne
Xiong; 2 chapters, 23 lessons = 8 videos + 15 exercises, 1,500 XP). Open design
question raised: convert conceptual `true-story-data` courses to plain `.md`
instead of notebooks (no executable code → notebooks add only overhead). Deferred
pending decision; also noted notebooks 01–04 have no course-header template
codified in the instructions.

---

## SESSION PART 4 — Format Decision + Course 5 Backbone (Markdown)

### Decision resolved — theory courses move to `.md`
The format question deferred in PART 3 is now answered. Conceptual
`true-story-data` courses carry no executable code until Course 8, so the notebook
container adds only overhead (JSON diff noise, heavier GitHub render). Principle
adopted: **format follows content** — theory → `.md`; code → notebook or `.py`
when code actually returns. Markdown wins on git-diff cleanliness, native GitHub
rendering (the side a recruiter sees), and search (plain text vs. JSON-buried cell
text). Validated live: tables, headings, emoji, and the Outline panel render
identically to the notebook — `Cmd+Shift+V` preview confirmed by Data.

### Course 5 backbone scaffolded — `05-introduction-to-data-culture.md`
First true-story-data course built as Markdown. Backbone only — no lessons (hard
rule: no lesson content without a screenshot). Contains: course header (Joanne
Xiong, 2 chapters, 23 lessons, 1,500 XP, 🔄 In Progress), both chapter overview
tables (mirrored from the notebook-04 convention), the single `### 📊 Course
Progress` table (0/23 · 0/1,500 · 0%), and a Knowledge Map placeholder. Chapter 2
description is verbatim from the screenshot; Chapter 1 description and course-level
metadata are honest placeholders pending screenshots.

### Reconciliation — curriculum verified against screenshots
10 + 13 = 23 lessons · 3 + 5 = 8 videos · 600 + 900 = 1,500 XP — all three totals
close against the course header. No fabrication.

### Glyph fix — `datacamp.instructions.md`
The PART 3 "Naming Lessons in Chat" heading emoji (broken `�` through the edit
toolchain) is fixed → `📛`. Root cause confirmed: variation-selector emoji
(`U+FE0F`) corrupt through the toolchain while single-codepoint emoji survive
(`🔄` did). Also restored the adjacent `🔄 Chat Closing` heading the same edit had
damaged. Post-fix glyph scan: clean.

### Open threads recorded (no action)
- **MD template codification** — the MD course-header template is still not
  codified in `datacamp.instructions.md`. Deferred until lessons (not just the
  backbone) validate the format. Notebooks 01–04 likewise still lack a codified
  header template.
- **`.py` for code courses (far)** — when code returns (Course 8), build courses
  as `.py` with `# %%` cells (markdown task text + runnable code + Interactive
  Window), embedding result screenshots as the "frozen output." Principle only;
  validate live before codifying.

---

## 📊 COURSE PROGRESS

| Chapter | Lessons | XP | Status |
|---------|---------|-----|--------|
| Ch1: Summary Statistics | 12/12 | 750/750 | ✅ |
| Ch2: Probability & Distributions | 13/13 | 750/750 | ✅ |
| Ch3: More Distributions & CLT | 16/16 | 1,000/1,000 | ✅ |
| Ch4: Correlation & Hypothesis Testing | 15/15 | 950/950 | ✅ |
| **Total** | **56/56** | **3,450/3,450** | **100% ✅** |

Notebook progress table (Cell 2) and Cell 1 header status synced to match.

---

## 🔜 NEXT STEP

- **Course 4: Introduction to Statistics — COMPLETE.** All 56 lessons populated, recap cell added, tables synced.
- **Course 5: Introduction to Data Culture — backbone scaffolded in Markdown.** Header, chapter tables, and progress table in place; no lessons yet.
- **Next lesson:** Chapter 1 — Lesson 1: What is data culture? *(Video / 50 XP)* — needs a screenshot before any content is written.
- **Deferred:** codify the MD course-header template in `datacamp.instructions.md` once lessons (not just the backbone) validate the format.

**Paused at:** Course 5 backbone committed; standing by for the Chapter 1 — Lesson 1 screenshot.

---

## 📁 FILES TOUCHED

**data-brain-gym:**
- `04-introduction-to-statistics.ipynb` — added Ch4 L6–L15 (10 lessons) + Chapter 4 Recap cell; synced progress table + header status to 100% Complete (55 → 66 cells)
- `.github/instructions/datacamp.instructions.md` — cadence rule made deterministic + new "Naming Lessons in Chat" section; fixed broken heading glyphs (`📛` Naming, restored `🔄`)
- `.github/instructions/haiku.instructions.md` — **deleted** (obsolete; no rule loss)
- `datacamp/true-story-data/data-literacy-professional/05-introduction-to-data-culture.md` — **new**; Course 5 backbone in Markdown (header, chapter tables, progress table, Knowledge Map placeholder)
- `captains-log/captains-log-stardate-20260629.md` — this log

🖖 *Live long and prosper, Data.*

