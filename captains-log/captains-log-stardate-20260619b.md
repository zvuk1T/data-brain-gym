# Captain's Log — Stardate 20260619b
**Date:** 19 June 2026 (second session)
**Project:** data-brain-gym
**Session:** Course 3, Chapter 3 — Working with and Analyzing Data (L7–L16 + Recap)

---

## 🎯 SESSION GOAL

Continue Chapter 3 of Course 3 (*Introduction to Data Literacy*) from where the previous session ended. Ch3 L1–L6 were already complete. Goal: complete Chapter 3 in full and commit.

---

## ✅ WHAT WE ACCOMPLISHED TODAY

### Part 1 — Session recovery

Read `captains-log-stardate-20260619.md` to confirm position. Verified notebook state via grep. Confirmed stopping point: Ch3 L6 (*Finding causes*) was the last written lesson.

---

### Part 2 — Chapter 3 completed: Working with and Analyzing Data

All 16 lessons written from screenshots and transcripts provided by Data. Chapter 3 Recap written after all lessons were complete (deferred synthesis rule).

| Lesson | Type | XP | Status |
|--------|------|----|--------|
| L1 — Descriptive analytics | 🎬 Video | 50 | ✅ (previous session) |
| L2 — Reasons (not) to use descriptive analytics | 📝 Exercise | 50 | ✅ (previous session) |
| L3 — Exploring the data | 🔁 Practice | 50 | ✅ (previous session) |
| L4 — Exploring connections | 🔁 Practice | 50 | ✅ (previous session) |
| L5 — Diagnostic analytics | 🎬 Video | 50 | ✅ (previous session) |
| L6 — Finding causes | 📝 Exercise | 50 | ✅ (previous session) |
| L7 — Root cause analysis steps | 📝 Exercise | 100 | ✅ |
| L8 — Descriptive vs. diagnostic analytics | 📝 Exercise | 100 | ✅ |
| L9 — Predictive analytics | 🎬 Video | 50 | ✅ |
| L10 — Are we predicting yet? | 🔁 Practice | 50 | ✅ |
| L11 — Building a predictive model | 📝 Exercise | 100 | ✅ |
| L12 — Looking into the future | 🔁 Practice | 50 | ✅ |
| L13 — Prescriptive analytics | 🎬 Video | 50 | ✅ |
| L14 — Characteristics of prescriptive analytics | 📝 Exercise | 50 | ✅ |
| L15 — Predictive vs. prescriptive analytics | 📝 Exercise | 100 | ✅ |
| L16 — Matching use cases to the type of analytics | 📝 Exercise | 100 | ✅ |

**Total Chapter 3 XP: 950**
**Committed:** `7d29e21`

---

## 🧠 KEY CONCEPTS COVERED

| Concept | Lesson | Core principle |
|---------|--------|----------------|
| RCA 5-step sequence | L7 | Define → Collect → Contributing factors → Root causes → Recommend. Sequence is a dependency chain, not a checklist |
| Descriptive vs. diagnostic classification | L8 | EDA = descriptive · drill-down/root cause = diagnostic · output format does not determine analytics type |
| Predictive analytics framework | L9 | 4 techniques (classification/regression/time series/text) · 5-step workflow · uncertainty inherent |
| Sentiment analysis = predictive | L10 | A model-produced label is a prediction — the table format makes it look descriptive; the process makes it predictive |
| Predictive modelling workflow | L11 | Define first — Step 1 determines all other steps. Train/test split is structural |
| Uncertainty grows with horizon | L12 | 6 months → 145% wider · 12 months → 246% wider — non-linear, must be shown alongside the forecast |
| Prescriptive analytics framework | L13 | Builds on predictive · 4 techniques · recommendation engine · fraud case study |
| Not a hierarchy | L14 | Prescriptive does not provide "better insights" — 4 types are complementary, each answers a different question |
| Predictive vs. prescriptive boundary | L15 | Shared: looks at future · uncertainty. Predictive only: outcomes, "what will happen?". Prescriptive only: actions, "what should we do?" |
| Question → type decision rule | L16 | The question determines the analytics type — not the domain, data, or tool |

---

## 🧠 DECISIONS AND REASONING

| Decision | Reason |
|----------|--------|
| Two traps documented in L15 with DataCamp feedback verbatim | Data got both wrong ("Looks at the future" and "Suggests possible outcomes") — traps are worth preserving exactly as DataCamp framed them |
| Chapter 3 Recap written with "8 traps" table | Chapter 3 had an unusually high number of deliberate traps — the recap table captures them in one place for future reference |
| Single-root workspace adopted this session | Removed `know-thyself-data` from context — it was loading automatically and consuming context budget without contributing to DataCamp work |

---

## ⚠️ WHERE WE STOPPED

Chapter 3 complete and committed. Chapter 4 (*Data Visualizations and Storytelling*, 10 lessons) not yet started.

**Files modified this session:**
- `datacamp/true-story-data/data-literacy-professional/03-introduction-to-data-literacy.ipynb` — Chapter 3 complete ✅ committed `7d29e21` ✅

**Current notebook state:**
- `01-introduction-to-data.ipynb`: Course 1 complete (31 lessons, 2000 XP)
- `02-communicating-data-insights.ipynb`: Course 2 complete (38 lessons, 2600 XP)
- `03-introduction-to-data-literacy.ipynb`:
  - Ch1 complete (13 lessons, 800 XP) ✅
  - Ch2 complete (16 lessons, 1050 XP) ✅
  - Ch3 complete (16 lessons, 950 XP) ✅
  - **Ch4 not yet started**

---

## 🔜 NEXT STEPS

1. ✅ Ch3 L7–L16 complete
2. ✅ Chapter 3 Recap written
3. ✅ Committed `7d29e21`
4. ✅ Captain's Log written
5. ⏳ **New chat — Chapter 4: Data Visualizations and Storytelling**
   - Send screenshot for Ch4 L1 to begin
