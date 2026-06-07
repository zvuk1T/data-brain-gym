# Captain's Log — Stardate 20260605
**Date:** 5 June 2026  
**Project:** data-brain-gym  
**Session:** SQL for Business Analysts — Track Setup + Local Data Infrastructure

---

## 🎯 SESSION GOAL

Build the complete structure for the DataCamp SQL for Business Analysts track — backbone notebooks, data folders, local DuckDB setup.

---

## ✅ WHAT WE ACCOMPLISHED TODAY

### Track structure
- Created `datacamp/sql-for-business-analysts/` folder as container for the entire track
- Added `datacamp/` entry to `.gitignore` (copyright protection)
- Moved and renamed the EDA notebook with `01-` prefix

### Backbone notebooks — 6 courses
Created the complete backbone for the entire track:

| # | Notebook | Exercises | Dataset |
|---|----------|-----------|---------|
| `00` | `data-manipulation-in-sql` | 55 | European Soccer DB |
| `01` | `exploratory-data-analysis-in-sql` | 57 | Fortune500, SO, Evanston |
| `02` | `data-driven-decision-making-in-sql` | 54 | MovieNow |
| `03` | `applying-sql-to-real-world-problems` | 47 | Pagila |
| `04` | `analyzing-business-data-in-sql` | 46 | Delivr |
| `05` | `reporting-in-sql` | 54 | Olympics |

Each notebook: title cell + Table of Contents + Chapter headers + Markdown/Code pair for every exercise.

### Data infrastructure
- Created `data/` folder with a subfolder for each course
- Created `data/README.md` — dataset inventory with download links
- For `01-eda-sql` — complete local setup:
  - `create-database.sql` — PostgreSQL schema (reference)
  - `evanston311.csv` — 36,431 rows (curl from DataCamp CDN)
  - `fortune500.csv` — 500 rows (curl from DataCamp CDN)
  - `stackoverflow.csv` — 45,238 rows (curl from DataCamp CDN)
  - `erd.md` — ERD + JOIN cheatsheet (from DataCamp Resources)
  - `Exploratory Data Analysis in SQL.pdf` — Course Glossary

### DuckDB local setup
- `duckdb` installed into shared `.venv`
- Setup cell added to the top of the `01-` notebook (cell 3)
- Resolved path issue — `Path().resolve()` instead of relative paths
- Tested and confirmed: all 3 tables loaded, Exercise 3 executed ✅

### Exercise 3 — Count missing values (populated and executed)
```sql
-- Missing ticker values → 32
SELECT count(*) - count(ticker) AS missing FROM fortune500;

-- Missing industry values → 13
SELECT count(*) - count(industry) AS missing FROM fortune500;
```

---

## 🧠 DECISIONS AND REASONING

| Decision | Reason |
|----------|--------|
| `00-` prefix for prerequisite course | Alphabetical sort = visual learning order |
| DuckDB instead of PostgreSQL for notebooks | Zero friction — `import duckdb`, no server needed |
| `data/` folder inside `datacamp/` | Auto-gitignored, Cookiecutter DS convention |
| `erd.md` instead of raw PNG | Searchable, versioned, JOIN cheatsheet built in |
| SQL as triple-quoted strings (`sql_1 = """..."""`) | Executable, syntax highlighted, not buried in comments |

---

## 🌱 DISCUSSION — Analytics Engineering and dbt

> *"When dbt enabled analysts to run data transformations using SQL and Git, a new kind of job was born..."*

### What is dbt?
**dbt = Data Build Tool** — organises and runs SQL transformations on data that already exists in a data warehouse.

It bridges three worlds:
- **Data Analyst** — knows SQL
- **Data Engineer** — knows infrastructure
- **Software Engineer** — knows Git and testing

```
DATA WAREHOUSE → RAW DATA → dbt MODELS → Tests / Documentation / Lineage → CLEAN DATA → BI tools
```

### Why dbt is NOT the next step right now

dbt models are literally CTEs:
```sql
-- dbt model: fct_revenue.sql
WITH orders AS (
    SELECT * FROM {{ ref('stg_orders') }}
)
SELECT ...
```

Course `00` (Data Manipulation in SQL) has an entire chapter on CTEs.
Course `04` (Analyzing Business Data) builds profit/revenue models — same pattern.

**Conclusion:** The SQL track builds exactly the understanding dbt requires.
After the track → dbt Core → dbt + DuckDB locally → Analytics Engineer portfolio.

---

## 🔜 NEXT STEPS

1. **Immediately:** Continue populating the `01-` notebook — screenshot by screenshot
2. **When available:** Download datasets for `02`, `04`, `05` from DataCamp Resources panel
3. **In parallel:** Download European Soccer DB (`00`) from Kaggle + Pagila (`03`) from GitHub
4. **Long-term:** dbt Core course after completing the SQL track
