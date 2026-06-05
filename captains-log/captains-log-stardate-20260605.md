# Captain's Log — Stardate 20260605
**Date:** 5 June 2026  
**Project:** data-brain-gym  
**Session:** SQL for Business Analysts — Track Setup + Local Data Infrastructure

---

## 🎯 SESSION GOAL

Izgraditi kompletnu strukturu za DataCamp SQL for Business Analysts trek — backbone notebooke, data foldere, lokalni DuckDB setup.

---

## ✅ ŠTA SMO POSTIGLI DANAS

### Track struktura
- Kreiran `datacamp/sql-for-business-analysts/` folder kao kontejner za cijeli trek
- Kreiran `datacamp/` entry u `.gitignore` (copyright zaštita)
- Premješten i preimenovan EDA notebook sa `01-` prefiksom

### Backbone notebooke — 6 kurseva
Kreirana kompletna kičma za cijeli trek:

| # | Notebook | Exercises | Dataset |
|---|----------|-----------|---------|
| `00` | `data-manipulation-in-sql` | 55 | European Soccer DB |
| `01` | `exploratory-data-analysis-in-sql` | 57 | Fortune500, SO, Evanston |
| `02` | `data-driven-decision-making-in-sql` | 54 | MovieNow |
| `03` | `applying-sql-to-real-world-problems` | 47 | Pagila |
| `04` | `analyzing-business-data-in-sql` | 46 | Delivr |
| `05` | `reporting-in-sql` | 54 | Olympics |

Svaki notebook: title cell + Table of Contents + Chapter headers + Markdown/Code par za svaki exercise.

### Data infrastruktura
- Kreiran `data/` folder sa podfolderom za svaki kurs
- Kreiran `data/README.md` — inventar svih dataseta s download linkovima
- Za `01-eda-sql` — kompletan lokalni setup:
  - `create-database.sql` — PostgreSQL schema (referenca)
  - `evanston311.csv` — 36,431 redova (curl sa DataCamp CDN)
  - `fortune500.csv` — 500 redova (curl sa DataCamp CDN)
  - `stackoverflow.csv` — 45,238 redova (curl sa DataCamp CDN)
  - `erd.md` — ERD + JOIN cheatsheet (iz DataCamp Resources)
  - `Exploratory Data Analysis in SQL.pdf` — Course Glossary

### DuckDB lokalni setup
- `duckdb` instaliran u zajednički `.venv`
- Setup ćelija dodana na vrh notebooka `01-` (ćelija 3)
- Riješen path problem — `Path().resolve()` umjesto relativnih putanja
- Testirano i potvrđeno: sve 3 tabele učitane, Exercise 3 izvršen ✅

### Exercise 3 — Count missing values (populiran i pokrenut)
```sql
-- Missing ticker values → 32
SELECT count(*) - count(ticker) AS missing FROM fortune500;

-- Missing industry values → 13
SELECT count(*) - count(industry) AS missing FROM fortune500;
```

---

## 🧠 ODLUKE I RAZLOZI

| Odluka | Razlog |
|--------|--------|
| `00-` prefix za prerequisite kurs | Alphabetical sort = vizualni redoslijed učenja |
| DuckDB umjesto PostgreSQL za notebooks | Zero friction — `import duckdb`, bez servera |
| `data/` folder unutar `datacamp/` | Gitignored automatski, Cookiecutter DS konvencija |
| `erd.md` umjesto raw PNG | Pretraživo, verzionisano, JOIN cheatsheet ugrađen |
| SQL kao triple-quoted strings (`sql_1 = """..."""`) | Executable, syntax highlighted, ne kao komentari |

---

## 🌱 RAZGOVOR — Analytics Engineering i dbt

> *"Kada je dbt omogućio analitičarima da rade transformacije podataka koristeći SQL i Git, nastala je nova vrsta posla..."*

### Šta je dbt?
**dbt = Data Build Tool** — organizuje i pokreće SQL transformacije nad podacima koji već postoje u data warehouse-u.

Spaja tri svijeta:
- **Data Analyst** — zna SQL
- **Data Engineer** — zna infrastrukturu  
- **Software Engineer** — zna Git i testiranje

```
DATA WAREHOUSE → RAW PODACI → dbt MODELI → Testovi / Dokumentacija / Lineage → ČISTI PODACI → BI alati
```

### Zašto dbt NIJE sljedeći korak sada

dbt modeli su bukvalno CTEs:
```sql
-- dbt model: fct_revenue.sql
WITH orders AS (
    SELECT * FROM {{ ref('stg_orders') }}
)
SELECT ...
```

Kurs `00` (Data Manipulation in SQL) ima cijelo poglavlje o CTEs.  
Kurs `04` (Analyzing Business Data) gradi profit/revenue modele — isti pattern.

**Zaključak:** SQL track gradi tačno razumijevanje koje dbt zahtijeva.  
Nakon tracka → dbt Core → dbt + DuckDB lokalno → Analytics Engineer portfolio.

---

## 🔜 SLJEDEĆI KORACI

1. **Odmah:** Nastaviti populirati `01-` notebook — screenshot po screenshot
2. **Kada dostupno:** Preuzeti datasete za `02`, `04`, `05` iz DataCamp Resources panela
3. **Paralelno:** Preuzeti European Soccer DB (`00`) sa Kaggle + Pagila (`03`) sa GitHub
4. **Dugoročno:** dbt Core kurs nakon završetka SQL tracka
