# Captain's Log — Stardate 20260607
**Date:** 7 June 2026
**Project:** data-brain-gym + know-thyself-data
**Session:** Language Rule Enforcement — Audit + Infrastructure Fix

---

## 🎯 SESSION GOAL

Audit all captain's log files across both repos for language compliance, enforce the existing Language Rule, and add structural safeguards to prevent the same violation from recurring.

---

## ✅ WHAT WE ACCOMPLISHED TODAY

### Trigger
Data noticed that `captains-log-stardate-20260605.md` was written in Serbian/Croatian — a direct violation of the Language Rule already defined in `data-spock-core.instructions.md`. This opened a broader question: how to prevent recurrence, not just fix the symptom.

### Root cause analysis
The Language Rule existed in `data-spock-core.instructions.md` but only as passive text. It was read once at session start and then drifted out of active context. No automatic enforcement mechanism was in place.

### Fix 1 — Scoped instruction files (automatic enforcement)
Created `captains-log.instructions.md` with `applyTo: 'captains-log/**'` in both repos:
- `data-brain-gym/.github/captains-log.instructions.md` ← new
- `know-thyself-data/.github/captains-log.instructions.md` ← new

VS Code Copilot loads these automatically whenever any file in `captains-log/` is touched. The rule fires at the folder level — not from memory.

### Fix 2 — Strengthened core instructions
Updated `data-spock-core.instructions.md` (in `know-thyself-data/copilot/`):
- Language Rule upgraded to `⚠️ HARD RULE` with explicit examples (`captains-log/`, table cells, bullet points)
- Added to **Forbidden Behavior** list: *"Write any `.md` file content in a language other than English"*

### Fix 3 — Full audit of all captain's log files

| Repo | File | Status | Action taken |
|------|------|--------|--------------|
| `data-brain-gym` | `20260527-mock-interviews.md` | ✅ English | None |
| `data-brain-gym` | `20260528-manufacturing.md` | ✅ English | None |
| `data-brain-gym` | `20260529.md` | ⚠️ One word | "krovni" → "umbrella" |
| `data-brain-gym` | `20260531.md` | ❌ Mixed | Full BONUS section translated |
| `data-brain-gym` | `20260605.md` | ❌ All Serbian | Full translation + subheading fix |
| `know-thyself-data` | `20260527.md` | ✅ English | None |
| `know-thyself-data` | `20260528.md` | ✅ English | None |
| `know-thyself-data` | `20260529.md` | ✅ English | None |

---

## 🧠 DECISIONS AND REASONING

| Decision | Reason |
|----------|--------|
| Scoped `.instructions.md` over timed re-reads | Automatic, not memory-dependent — fires at folder level every time |
| Both repos get the scoped file | Both have `captains-log/` folders — same rule, same mechanism |
| Strengthen core + add scoped | Two-layer defence: core as policy, scoped as enforcement |
| Audit all logs before committing | Commit checklist principle — verify before staging |

---

## ✅ WHAT WE ACCOMPLISHED TODAY — PART 2 (Notebook + Documentation)

### Exercise 2 — Explore table sizes (populated + executed)
Populated the markdown and code cells for Exercise 2 in `01-exploratory-data-analysis-in-sql.ipynb`.
- Discovered that `company`, `tag_company`, `tag_type` are not available as CSV downloads from DataCamp Resources
- These 3 tables exist only inside DataCamp's PostgreSQL environment — no export available

### Full local database — all 6 tables now available
Resolved the missing tables by reading `create-database.sql`, which contains full `INSERT` statements for the 3 small lookup tables.
Updated the DuckDB setup cell to create all 6 tables:

| Table | Rows | Source |
|-------|------|--------|
| `fortune500` | 500 | CSV |
| `evanston311` | 36,431 | CSV |
| `stackoverflow` | 45,238 | CSV |
| `company` | 14 | `create-database.sql` INSERT statements |
| `tag_company` | 56 | `create-database.sql` INSERT statements |
| `tag_type` | 59 | `create-database.sql` INSERT statements |

All 6 tables verified and loaded. JOIN exercises that use `company`, `tag_company`, and `tag_type` are now fully executable locally.

### Notes for Students added to `create-database.sql`
Added a `✅ NOTES FOR STUDENTS` block at the bottom of the SQL script explaining:
- What each of the 6 tables represents
- Why foreign keys matter and how they connect the tables
- The difference between DuckDB (no FK enforcement) and PostgreSQL (hard FK enforcement)
- The most important mental model: schema as a map, every JOIN is a path

### Notebook Exercise Standard added to `data-spock-core.instructions.md`
Added **Notebook Exercise Standard** rule to the Student-Friendly Documentation Rule section:
- Every populated exercise markdown cell must include: task description, instructions, Hint (SQL pattern), **Why this matters** (one sentence on the concept), and Note (local setup differences)
- Goal stated explicitly: *"The notebook must function as a self-contained mini-course"*

---

## 🧠 DECISIONS AND REASONING — PART 2

| Decision | Reason |
|----------|--------|
| Read INSERT statements from `create-database.sql` instead of creating new CSVs | Cleanest solution — data already exists in the repo, no new files needed |
| Execute INSERT statements directly in DuckDB setup cell | DuckDB accepts standard SQL — no parsing layer needed |
| Notes for Students in SQL file, not just in notebook | The SQL file is itself a learning resource — a student reading it should understand the schema |
| Notebook Exercise Standard added to core instructions | Without an explicit rule, exercise cells risk becoming "copy the query" exercises with no conceptual explanation |

---

## 🔜 NEXT STEPS

1. Commit updated `data-spock-core.instructions.md` in `know-thyself-data`
2. Continue populating `01-exploratory-data-analysis-in-sql.ipynb` — Exercise 4 onwards (Exercise 2 + 3 done)
3. Note: `datacamp/` is gitignored — notebook changes are local only (copyright protection)

---

## ✅ Notes for Students

Two things to take away from today's infrastructure work:

**1. Always read the schema script before querying.**
`create-database.sql` told us everything: which tables exist, how they connect, and — crucially — that the data for 3 of them was already there in INSERT statements. If you open a new database and feel lost, find the schema script first. It is the map.

**2. Documentation is part of the work, not extra work.**
The notebook exercise cells, the SQL notes, the captain's log — these are not decoration. They are how you will remember what you did and why, six months from now. And they are how anyone else can pick up where you left off without needing to ask questions. Write as if the next reader is a student who has never seen this project. That student might be you.
