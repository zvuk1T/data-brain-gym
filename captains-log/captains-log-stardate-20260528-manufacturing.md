# Captain's Log — Stardate 20260528
**Date:** 28 May 2026
**Project:** manufacturing-process-sql-analysis
**Session:** #1 — Project Setup

---

## 🎯 SESSION GOAL

Set up the project structure, documentation, and working methodology before writing any SQL.

---

## ✅ WHAT WE ACCOMPLISHED TODAY

- Reviewed the DataCamp project brief: Statistical Process Control (SPC) analysis of manufacturing parts
- Confirmed workflow: DataCamp DataLab (PostgreSQL) as the SQL playground → GitHub repo as the portfolio
- Identified the dataset: `manufacturing_parts` table with fields `item_no`, `length`, `width`, `height`, `operator`
- Set up shared Python venv at `/Users/zeal.v/Desktop/vs_code/.venv` (Python 3.11.11) — pandas, jupyter, ipykernel, psycopg2-binary installed
- Downloaded `parts.csv` (500 rows, 5 columns) and organized into `data/` (gitignored)
- Set up `notebooks/notebook.ipynb` — kernel set to `.venv`, image path fixed, data loaded and explored with pandas
- Data confirmed: 500 rows, columns `item_no`, `length`, `width`, `height`, `operator` (e.g. Op-1, Op-2, ...)
- **Expanded project scope** from single DataCamp task to full portfolio case study across all 5 courses
- Created `docs/learning-map.md` — maps each course to specific analyses, query folders, and datasets
- Created `docs/learning-map-template.md` — reusable template for future projects
- Updated `README.md` to reflect expanded scope: new title, learning map table, expanded skills section, updated status
- Completed `README.md` — project overview, domain connection, folder structure, status
- Created first Captain's Log (this file)

---

## 🧠 DECISIONS MADE

- SQL queries will be developed and tested in DataCamp, then copied to `queries/` with full explanations
- Each SQL file will be numbered and include a header comment explaining what it does and why
- Commits will be made per logical step, with descriptive messages
- Results/screenshots go into `results/`
- **Scope expanded:** This is no longer just a DataCamp task — it's a growing portfolio project covering the entire SQL for Business Analysts track
- `manufacturing_parts` will be used for Courses 1 and 2; additional databases will be introduced for Courses 3–5
- `docs/learning-map.md` created as the master plan — this pattern will be used in all future projects
- `docs/learning-map-template.md` created as a reusable template

---

## 📐 PROJECT CONTEXT

**Goal:** Implement Statistical Process Control (SPC) using SQL window functions.

**Method:**
- Calculate rolling mean and standard deviation per operator (window of last 5 measurements)
- Derive UCL and LCL from those statistics
- Flag any measurement that falls outside the control limits → these are process alerts

**Formulas:**
- `UCL = mean + 3 * (stddev / sqrt(5))`
- `LCL = mean - 3 * (stddev / sqrt(5))`

---

## 🔜 NEXT STEP

Write first SQL query: `queries/01_exploration/01_basic_overview.sql` — basic EDA on `manufacturing_parts` (Course 1 practice).
Then commit all session 1 work to GitHub.

---

## 📝 NOTES

- Terminal had a Git relaunch warning on session start — resolved by opening a new terminal
- DataCamp environment uses PostgreSQL with a `manufacturing_parts` table (not the CSV directly)
- Shared venv pattern established: one `.venv` at `/Users/zeal.v/Desktop/vs_code/.venv` shared across projects
- `docs/learning-map.md` pattern will be reused in all future portfolio projects — template saved
