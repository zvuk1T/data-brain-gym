# Learning Map — SQL for Business Analysts
**Track:** SQL for Business Analysts (DataCamp)
**Project:** manufacturing-process-sql-analysis
**Last updated:** 2026-05-28

---

## 🗺️ Course → Analysis Mapping

### Course 1 — Exploratory Data Analysis in SQL
**Status:** 🟡 89% complete
**Topics:**
- What's in the database (tables, keys, missing values)
- Numeric aggregations, variance, correlation, binning
- Categorical data and string operations
- Dates and timestamps

**Practice on this project:**
- `queries/01_exploration/` — basic data exploration of `manufacturing_parts`
- Count rows, check nulls, explore distributions
- Summarize `height`, `length`, `width` per operator

---

### Course 2 — Data-Driven Decision Making in SQL
**Status:** ⬜ 0%
**Topics:**
- Business Intelligence concepts
- Simple queries for business questions
- Advanced queries (subqueries, CTEs)
- OLAP queries (multidimensional aggregations)

**Practice on this project:**
- `queries/02_spc_analysis/` — UCL/LCL calculation (DataCamp project task)
- `queries/03_operator_comparison/` — which operator performs best?
- `queries/04_trend_analysis/` — does quality change over time?

---

### Course 3 — Applying SQL to Real-World Problems
**Status:** ⬜ 0%
**Topics:**
- Finding tables in unfamiliar databases
- Creating and managing views
- Writing maintainable, readable SQL
- Best practices

**Practice database:** DVD Rental (download from DataCamp course resources)
**New folder:** `databases/dvd_rental/`

---

### Course 4 — Analyzing Business Data in SQL
**Status:** 🟡 33% complete
**Topics:**
- Revenue analysis, KPI metrics
- Cohort analysis
- Customer lifetime value

**Practice database:** TBD — business/financial dataset
**New folder:** `databases/business_data/`

---

### Course 5 — Reporting in SQL
**Status:** ⬜ 0%
**Topics:**
- Final reports and dashboards
- Views and summary queries
- Communicating insights

**Practice on this project:**
- `queries/05_reports/` — final summary report across all operators

---

## 📁 Planned Query Structure

```
queries/
├── 01_exploration/         ← Course 1 — EDA
├── 02_spc_analysis/        ← Course 2 — SPC / DataCamp task
├── 03_operator_comparison/ ← Course 2 — Business decisions
├── 04_trend_analysis/      ← Course 2 — Trends over time
└── 05_reports/             ← Course 5 — Final reporting
```

---

## 🗄️ Databases Used

| Database | Source | Used in |
|----------|--------|---------|
| `manufacturing_parts` | DataCamp project / `parts.csv` | Courses 1, 2, 5 |
| `dvd_rental` | DataCamp Course 3 resources | Course 3 |
| TBD | TBD | Course 4 |
