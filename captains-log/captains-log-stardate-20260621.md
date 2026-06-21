# Captain's Log — Stardate 20260621
**Date:** 21 June 2026
**Project:** data-brain-gym
**Session:** Course 4 backbone — notebook creation + Knowledge Map

---

## 🎯 SESSION GOAL

Create Course 4 notebook (`04-introduction-to-statistics.ipynb`) with course header and Knowledge Map — the backbone work needed before screenshots begin.

---

## ✅ WHAT WE ACCOMPLISHED TODAY

### Part 1 — Session recovery

Ran the new-session prompt (`@.github/prompts/new-session.prompt.md`). Loaded:
- `.github/copilot-instructions.md` — project rules
- `.github/instructions/datacamp.instructions.md` — DataCamp-specific rules
- Two latest captain's logs (20260618, 20260619)

**Confirmed stopping point:** Course 3 fully complete. Next step: Course 4 backbone — PDF extraction → notebook creation → Knowledge Map.

---

### Part 2 — Course 4 notebook created

Data confirmed the assets folder contained everything needed:

`datacamp/true-story-data/data-literacy-professional/04-introduction-to-statistics-assets/`
- `chapter1.pdf` · `chapter2.pdf` · `chapter3.pdf` · `chapter4.pdf`
- 6 screenshots (course outline / overview pages)

**PDF extraction performed** using `pdftotext -layout` on all 4 chapter PDFs.

**Created `04-introduction-to-statistics.ipynb`** with:

- **Cell 1 — Course header:** metadata, 5 learning objectives, chapter tables for all 4 chapters (64 lessons, XP TBD)
  - Ch1: What is Statistics? (16 lessons)
  - Ch2: What are the Chances? (16 lessons)
  - Ch3: Key Probability Distributions (16 lessons)
  - Ch4: Hypothesis Testing and Correlation (16 lessons)

- **Cell 2 — Course Knowledge Map:** full ASCII synthesis from all 4 PDFs
  - Ch1: data types (numeric/categorical), descriptive vs. inferential, measures of center (mean/median/mode), measures of spread (range/variance/std dev/IQR/box plots) — London crime data running example
  - Ch2: probability, independent/dependent events, conditional probability, discrete/continuous distributions, law of large numbers — online retail sales running example
  - Ch3: binomial distribution, normal distribution (68-95-99.7 rule, skewness, kurtosis), central limit theorem, Poisson distribution (λ) — coin flips/die rolls running example
  - Ch4: hypothesis testing workflow, null/alternative hypotheses, RCT vs. A/B testing, Pearson correlation, p-values, significance level (α), Type I/II errors — vitamin C / Chicago vs. Bangkok running example

- **Course arc:** Ch1 (foundation) → Ch2 (probability) → Ch3 (distributions) → Ch4 (hypothesis testing)

**Instructor:** George Boorman, Curriculum Manager at DataCamp
**Next course in track:** Understanding Data Science

- Committed: `577c68c`

---

## 🧠 DECISIONS AND REASONING

| Decision | Reason |
|----------|--------|
| 16 lessons per chapter | PDF slides show 4 sub-topics per chapter × ~4 slides each → natural 4-block arc per chapter |
| Chapter 3 named "Key Probability Distributions" | The PDF covers 3 distributions (binomial, normal, Poisson) + CLT — "Key Probability Distributions" is more descriptive than the PDF's section titles |
| Lesson XP set to TBD | Actual XP values will be confirmed from screenshots during lesson creation |
| Knowledge Map uses running examples from PDFs | London crime data (Ch1), online retail (Ch2), coin flips/die rolls (Ch3), vitamin C + life expectancy (Ch4) — all extracted from PDF content |
| No Mermaid chapter maps created yet | Per deferred synthesis rule — created after each chapter's lessons are complete |

---

## ⚠️ WHERE WE STOPPED

Course 4 notebook created and committed. Knowledge Map pre-loaded. Ready for screenshots.

**Files modified this session:**
- `datacamp/true-story-data/data-literacy-professional/04-introduction-to-statistics.ipynb` — created ✅ committed ✅
- `captains-log/captains-log-stardate-20260621.md` — this file

**Current notebook state:**
- `01-introduction-to-data.ipynb`: Course 1 complete (31 lessons, 2000 XP) ✅
- `02-communicating-data-insights.ipynb`: Course 2 complete (38 lessons, 2600 XP) ✅
- `03-introduction-to-data-literacy.ipynb`: Course 3 complete (61 lessons, 4000 XP) ✅
- `04-introduction-to-statistics.ipynb`: Course 4 backbone created ✅ — no lessons yet

---

## SESSION UPDATE — 21 June 2026 (continued)
**What was done in this chat**

- Added Lesson 3 (Identifying data types, Exercise / 100 XP) to `datacamp/true-story-data/data-literacy-professional/04-introduction-to-statistics.ipynb` — GOAL, Task, Hint, Expected answer, Walkthrough, Solution, Common mistakes included.
- Added Lesson 4 (Descriptive vs. Inferential statistics, Exercise / 100 XP) to the same notebook — GOAL, Task, Hint, Expected answers, Walkthrough and RECAP included.
- Removed temporary "Next step" lines from Lesson 3 and Lesson 4 cells to keep lesson cells focused on teaching content.

**Next step (ask Data)**

- Send screenshot for Chapter 1 — Lesson 5 (Measures of center) so Lesson 5 can be written.

**Files edited in this chat (not yet committed)**

- `datacamp/true-story-data/data-literacy-professional/04-introduction-to-statistics.ipynb` — Lesson 3 + Lesson 4 content inserted; minor cleanup (removed transient notes).

**Notes**

- No git commit was made in this chat. Per the chapter commit boundary rule, we will commit when Chapter 1 is complete (or sooner if you instruct otherwise).

---

## SESSION UPDATE — 21 June 2026 (session 3 — repo audit + cleanup)
**What was done in this chat**

### Part 1 — Session recovery (new-session prompt)
- Ran `@.github/prompts/new-session.prompt.md` (Extended version)
- Loaded: `copilot-instructions.md`, `datacamp.instructions.md`, captain's logs 20260619 + 20260621
- Used `copilot_getNotebookSummary` to verify `04-introduction-to-statistics.ipynb`
- **Discrepancy found:** captain's log said next step was Ch1 L5 — notebook already had L1–L9 written by cheaper model. Notebook treated as source of truth.

### Part 2 — Course 4 notebook audit + reset
- Compared `03-introduction-to-data-literacy.ipynb` (our work) vs `04-introduction-to-statistics.ipynb` (cheaper model)
- Problems found in cheaper model's L1–L9:
  - Wrong `🎬` link format in L9 (plain text URL instead of Markdown link)
  - Non-template `� Walkthrough` section in L3, L4, L6, L7
  - `*Source screenshot:*` and `*Image credit:*` attributions not in template
  - Inconsistent `🎯 GOAL` heading wording across cells
  - L7 Solution not a table — single text line instead of `Item | Verdict | Why`
  - Unknown screenshot provenance — some cells appear generated from prior knowledge, not screenshots (violates screenshot rule)
- **Decision:** delete L1–L9, keep Cell 1 (course header) and Cell 2 (Knowledge Map)
- **Rationale:** 9 cells with mixed template errors + unknown screenshot source not worth auditing; clean rebuild with correct template for all 55 remaining lessons
- Deleted cells 3–11 from notebook ✅

### Part 3 — Instruction file audit
- Checked which files the cheaper model had touched: `new-session.prompt.md`, `datacamp.instructions.md`, `data-spock-learning-methodology.md`
- `data-spock-learning-methodology.md` — clean, cheaper model did not touch it ✅
- `new-session.prompt.md`:
  - `886941c` (cheaper model, origin/main): expanded from 5-line prompt to full Step 1–4 structure — content solid, kept ✅
  - Today's uncommitted diff (our work): Extended version — added `copilot_getNotebookSummary`, notebook-aware Step 3, Implementation notes — kept ✅
- `datacamp.instructions.md`:
  - Uncommitted diff contained **duplicate** `🗂️ Course Backbone Rule` block (identical to existing `🦴 Course Backbone Rule` at line 74, different emoji only)
  - Duplicate removed ✅
  - `Current state` date in original Backbone Rule updated from `20260619` (Course 3) to `20260621` (Course 4) ✅
  - `Preference` one-liner and `Agent behaviour preference — commit prompts` section kept ✅

**Files modified this session:**
- `datacamp/true-story-data/data-literacy-professional/04-introduction-to-statistics.ipynb` — L1–L9 deleted; back to 2-cell backbone ✅
- `.github/instructions/datacamp.instructions.md` — duplicate Backbone Rule removed; Current state date updated ✅
- `.github/prompts/new-session.prompt.md` — Extended version retained ✅
- `captains-log/captains-log-stardate-20260621.md` — this file ✅

**Current notebook state:**
- `01-introduction-to-data.ipynb`: Course 1 complete (31 lessons, 2000 XP) ✅
- `02-communicating-data-insights.ipynb`: Course 2 complete (38 lessons, 2600 XP) ✅
- `03-introduction-to-data-literacy.ipynb`: Course 3 complete (61 lessons, 4000 XP) ✅
- `04-introduction-to-statistics.ipynb`: Backbone only (Cell 1 + Cell 2) ✅ — L1–L9 deleted, clean slate

---

## �🔜 NEXT STEP

New chat → Course 4 Chapter 1: What is Statistics? → send screenshot for Ch1 L1 to begin lesson creation from scratch, with correct template.