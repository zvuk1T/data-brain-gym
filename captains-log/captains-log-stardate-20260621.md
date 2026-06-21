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

## 🔜 NEXT STEP

New chat → Course 4 Chapter 1: What is Statistics? → send screenshot for Ch1 L1 to begin lesson creation.