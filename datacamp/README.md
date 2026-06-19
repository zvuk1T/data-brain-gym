# DataCamp — Learning Architecture

This folder contains all DataCamp coursework for the `data-brain-gym` project.
It is not a collection of completed exercises — it is a structured learning system built on a deliberate philosophy.

---

## 🧭 The Core Idea

DataCamp provides exercises. We provide **meaning**.

Every DataCamp exercise asks a technical question.
Our job is to answer a deeper set of questions before we write a single line of SQL or Python:

- **Why does this question exist?**
- **Who is asking it in a real organisation?**
- **What decision does the answer enable?**
- **What would a data story built from this answer look like?**

This is the difference between a technician who runs queries and an analyst who understands their impact.

DataCamp provides the exercise. We provide what DataCamp cannot: **your own reason why you know this.**

---

## 🗂️ Folder Structure

```
datacamp/
├── README.md                          ← this file
│
├── true-story-data/                   ← theory tracks — based on a true story
│   ├── data-literacy-professional/    ← 8 courses, 15h — what data is and how to reason with it
│   ├── data-storytelling/             ← 4 courses, 6h — how to communicate insights
│   └── data-skills-for-business/      ← 6 courses, 17h — governance, ethics, AI, management
│
└── sql-for-business-analysts/         ← practical track — resumes after true-story-data
    ├── 01-exploratory-data-analysis-in-sql.ipynb
    ├── 02-data-driven-decision-making-in-sql.ipynb
    ├── ...
    ├── data/                          ← gitignored CSVs (download from DataCamp)
    └── recordings/                    ← gitignored videos and PDFs
```

---

## 📐 Why Theory Before Code

The practical courses (EDA, Data-Driven Decision Making, etc.) teach **how** to query data.
The foundations tracks teach **why** the question matters, **who** owns the answer, and **what** to do with it.

Without the foundations:
- Every `GROUP BY` is a technical exercise
- Every `JOIN` is a syntax problem
- Every result is a table, not an insight

With the foundations:
- Every query answers a business question
- Every result has an audience and a purpose
- Every exercise is a data story waiting to be told

**The rule:** `true-story-data` tracks are completed before returning to practical exercises.
**The exception:** there isn't one.

---

## 📋 The 3 True-Story-Data Tracks

### 1. Data Literacy Professional *(15h | 8 courses)*
The broadest foundation. Covers what data is, how to read and interpret it, basic statistics,
how to form analytical questions, and how to communicate insights. Ends with a real case study.

| # | Course | Key question it answers |
|---|--------|------------------------|
| 1 | Introduction to Data | What is data and why does it have value? |
| 2 | Communicating Data Insights ✅ | How do I share what I found? |
| 3 | Introduction to Data Literacy | How do I read, work with, analyze and communicate data? |
| 4 | Introduction to Statistics | How do I describe and compare distributions? |
| 5 | Introduction to Data Culture | How do organisations build trust in data? |
| 6 | Forming Analytical Questions | How do I turn a business problem into a data question? |
| 7 | Data Storytelling Concepts | How do I build a narrative around an insight? |
| 8 | Data Literacy Case Study: Remote Working Analysis | Can I apply all of this to a real dataset? |

### 2. Data Storytelling *(6h | 4 courses)*
The communication layer. Covers the principles of data storytelling, narrative structure,
visualization choices, and two hands-on case studies with real datasets.

| # | Course | Type |
|---|--------|------|
| 1 | Communicating Data Insights | Theory |
| 2 | Data Storytelling Concepts | Theory |
| 3 | Case Study: College Majors | Python + CSV |
| 4 | Case Study: Green Businesses | Python + CSV |

### 3. Data Skills for Business *(17h | 6 courses)*
The organisational layer. Covers data governance, ethics, AI in the workplace,
and data management — the context in which every analyst actually works.

| # | Course | Key question it answers |
|---|--------|------------------------|
| 1 | Introduction to Data | What is data and why does it have value? |
| 2 | Introduction to Data Literacy | How do I read and communicate data? |
| 3 | Introduction to AI for Work | How does AI change how I work? |
| 4 | Data Governance Concepts | Who owns data and how is it managed? |
| 5 | Introduction to Data Ethics | What are my responsibilities with data? |
| 6 | Data Management Concepts | How is data stored, maintained and governed at scale? |

---

## 🔗 Cross-Track Map — Shared Courses

Several courses appear in multiple tracks. They are learned once and applied across all contexts.

| Course | Data Literacy Professional | Data Storytelling | Data Skills for Business |
|--------|---------------------------|-------------------|--------------------------|
| Introduction to Data | ✅ (1) | — | ✅ (1) |
| Communicating Data Insights | ✅ (2) | ✅ (1) | — |
| Introduction to Data Literacy | ✅ (3) | — | ✅ (2) |
| Data Storytelling Concepts | ✅ (7) | ✅ (2) | — |

---

## 📝 How We Document Exercises

Every exercise notebook follows the **Problem-Solving Standard** defined in `data-spock-core.instructions.md`.

The 5-block structure applied to every exercise:

```
1. 🎯 GOAL        — What are we solving and why does it matter?
2. 🔧 APPROACH    — What pattern or technique will we use?
3. 💡 SOLUTION    — The actual code or query
4. 🔍 WALKTHROUGH — Every step explained (line-by-line or block-by-block)
5. ✅ RECAP       — Key concept, most common mistake, what to remember next time
```

### Practical exercise notebook (SQL/Python) — cell format:

```
📝 Markdown cell
   - Exercise title and XP value
   - GOAL block
   - APPROACH block
   - Original instructions from DataCamp
   - Hint (pattern explanation)
   - Why this matters (one sentence — the concept, not the syntax)
   - Note (local setup) — if local environment differs from DataCamp

💻 Code cell
   - SOLUTION with inline WALKTHROUGH comments
   - display() or print() for output

📖 Story block (added after foundations are complete)
   - Business question this analysis answers
   - Who would ask this question in a real organisation?
   - What decision does the answer enable?
   - One-sentence data story built from the result
```

### Video exercise cell format:

```
📝 Markdown cell only — no code cell
   > 🎬 [Watch on DataCamp](URL) *(requires login)*
   - 1–2 sentence summary of what the video covers
```

---

## 📖 The Story Block — Why It Exists

The story block is the bridge between technical exercise and analytical thinking.
It is added to every exercise after the foundations tracks are complete.

It prevents the most common mistake in data education:
**learning the syntax without learning the question.**

A SELECT statement is not an answer. It is a tool. The story block forces the question:
**what is this tool answering, and for whom?**

---

## ⚠️ Local Setup Notes

- **Data files** (`data/` folders) — gitignored. Download from the DataCamp Resources panel.
- **Recordings** (`recordings/` folders) — gitignored. Videos and PDFs are DataCamp property.
- **Database engine** — DuckDB (in-memory). Replaces DataCamp's PostgreSQL for local execution.
- **Schema files** (`create-database.sql`) — committed. Small lookup tables are reproduced via INSERT statements directly in the setup cell.

---

## 🔄 Session Continuity

When starting a new session on any DataCamp notebook:
1. Read this README
2. Read the latest `captains-log/` entry
3. Open the active notebook and check which exercises are populated vs empty
4. Confirm the current position with Data before proceeding

The foundations notebooks are populated exercise by exercise, following the same screenshot-driven workflow as the practical notebooks.

---

## 🎯 Why This System Exists — Career Context

This is not a casual learning log. It is a structured preparation system for a specific career path.

**Target path (locked):**
`SQL for Business Analysts → dbt Core → Analytics Engineer → AI Engineering`

Every track in this repo serves that path directly:
- **Data Literacy Professional** — builds the analytical reasoning layer that separates analysts from query runners
- **Data Storytelling** — builds the communication layer that makes technical work visible and trusted by business stakeholders
- **Data Skills for Business** — builds the organisational context layer (governance, ethics, AI, management) required at Analytics Engineer level
- **SQL for Business Analysts** — the first practical track, returned to after foundations are solid

**Why foundations before code:**
The working pattern here is: understand the system before operating it.
Running SQL without understanding what a business question is, who owns the answer, or what decision it enables — is technician work, not analyst work.
The foundations tracks install that context first. The practical tracks are then meaningful, not mechanical.

**What success looks like:**
Every completed exercise in this repo answers three questions beyond the DataCamp prompt:
1. What business question does this analysis answer?
2. Who in a real organisation would ask it?
3. What decision does the result enable?

That is the standard. Technical correctness is the floor, not the ceiling.
