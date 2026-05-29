# SQL for Business Analysts — Portfolio Project

![Manufacturing Process](assets/manufacturing.jpg)

A growing SQL portfolio project built alongside the **SQL for Business Analysts** track on DataCamp. Each analysis connects real-world business questions to SQL techniques learned in the course — demonstrated on manufacturing, rental, and business datasets.

## Project Overview

This project started as a DataCamp task — Statistical Process Control (SPC) analysis of manufacturing parts — and expanded into a full portfolio case study covering exploratory analysis, business decision making, trend analysis, and reporting.

The core dataset is `manufacturing_parts` (500 rows, 5 columns: `item_no`, `length`, `width`, `height`, `operator`). Additional databases will be introduced as the track progresses.

See `docs/learning-map.md` for the full plan of what is analysed where and why.

## Domain Connection

My background includes 10+ years in industrial environments — electronics, sensor calibration, and measurement at Emerson Process Management. This project connects that experience directly to data analytics: the same quality-control thinking that applies to physical sensor calibration applies to statistical process monitoring in SQL.

## Stack

- SQL (PostgreSQL / SQLite)
- DataCamp DataLab (project environment)

## Project Source

This project is built alongside the DataCamp track **SQL for Business Analysts**. The starting point is the DataCamp project **Evaluate a Manufacturing Process**. All analysis, SQL explanations, documentation, and extensions beyond the original task were completed independently as part of my SQL and business analytics portfolio.

## Learning Map

The full course-to-analysis mapping is documented in `docs/learning-map.md`. Summary:

| Course | Status | Analysis |
|--------|--------|----------|
| Exploratory Data Analysis in SQL | 🟡 89% | EDA on `manufacturing_parts` |
| Data-Driven Decision Making in SQL | ⬜ 0% | SPC analysis, operator comparison, trends |
| Applying SQL to Real-World Problems | ⬜ 0% | DVD Rental database |
| Analyzing Business Data in SQL | 🟡 33% | Business/financial dataset (TBD) |
| Reporting in SQL | ⬜ 0% | Final summary reports |

## Skills Demonstrated

- SQL window functions (AVG, STDDEV over rolling windows)
- Statistical Process Control concepts (UCL, LCL)
- Exploratory data analysis in SQL
- Business decision making with SQL
- OLAP and aggregation queries
- Writing maintainable, well-documented SQL
- Industrial domain knowledge applied to analytics

## Project Structure

```
manufacturing-process-sql-analysis/
├── .github/              ← Copilot instructions and prompt files
├── assets/               ← Images and static resources
├── captains-log/         ← Session logs (what was done, decisions made)
├── data/                 ← [gitignored] raw data files (parts.csv)
├── notebooks/            ← Jupyter notebook files
├── queries/              ← SQL queries with explanations
├── results/              ← Query outputs and screenshots
├── docs/                 ← Methodology notes and project rationale
└── README.md
```

## How to Read This Project

1. Start with this README for context
2. Read `queries/` files in numbered order — each builds on the previous
3. Check `results/` for outputs and visual confirmation
4. `captains-log/` shows the thinking process session by session

## Status

🟡 In progress — Session 1 complete: project setup, data exploration, learning map defined
