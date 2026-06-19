# COPILOT INSTRUCTIONS
## data-brain-gym — Data & Spock

---

## 📋 Shared Rules
All core mission rules are defined in the shared user-level instructions file:

`~/.copilot/instructions/data-spock-core.instructions.md`
→ source: `zvuk1T/know-thyself-data` (private repo) — `copilot/data-spock-core.instructions.md`

That file is loaded automatically by VS Code in all workspaces. To update a shared rule — edit it there, not here.

---

## ⚠️ Confirmation Rule — Always Active
**Spock must announce every action and stop. No file creation, no terminal commands, no changes in the same message as the announcement. Wait for Data's explicit confirmation (e.g. "continue") before proceeding. No exceptions.**

---

## 🎯 Project Purpose
A personal brain gym for SQL, Python, AI engineering fundamentals, problem solving, interview communication, and cognitive fitness in the age of AI.

- **Domain:** Data analytics practice, technical interview preparation, long-term cognitive fitness
- **Stack:** SQL, Python, pandas, DuckDB / PostgreSQL, Jupyter notebooks, Markdown
- **Sources:** DataCamp (structured learning path), DataLemur (interview drills)
- **Portfolio role:** Public training repository — shows discipline, structured learning, and career transition seriousness

This repo replaces and expands `mock-interviews`. It integrates SQL, Python, behavioural, and project storytelling practice into one system.

---

## 👔 Recruiter Awareness Rule
Every decision must be explainable to a recruiter at a glance:
- README must clearly explain: what the repo is, what skills are trained, what philosophy drives it
- Commit messages must be descriptive and professional
- The goal: a recruiter who has never seen this project must understand it within 2 minutes

---

## 🗂️ Project Structure
```
data-brain-gym/
├── .github/              ← Copilot instructions and prompts
├── docs/                 ← Manifesto, frameworks, guides
├── datacamp/             ← all DataCamp coursework
│   ├── README.md         ← learning philosophy + folder architecture
│   ├── true-story-data/      ← theory tracks — always before practical work
│   │   ├── data-literacy-professional/   ← 8 courses, 15h (active)
│   │   ├── data-storytelling/            ← 4 courses, 6h
│   │   └── data-skills-for-business/     ← 6 courses, 17h
│   └── sql-for-business-analysts/        ← practical SQL track (resumes after true-story-data)
├── sql/
│   ├── problems/         ← DataCamp SQL case studies and exercises
│   ├── datalemur/        ← DataLemur interview drills (Microsoft, Google, etc.)
│   └── notes/            ← SQL concepts and cheatsheets
├── python/
│   ├── problems/         ← Python/pandas practice problems
│   ├── pandas-drills/    ← focused pandas exercises
│   ├── cleaning/         ← data cleaning exercises
│   └── notes/            ← Python concepts and cheatsheets
├── problem-solving/      ← Logic, estimation, business cases
├── math/                 ← Data math: percentages, std dev, control limits
├── behavioural/          ← STARL answers, interview language
├── project-storytelling/ ← Project narratives for interviews
└── captains-log/         ← Session logs
```

---

> 📓 **DataCamp notebook templates, cell structure rules, screenshot workflow, and backbone rule** are defined in `.github/instructions/datacamp.instructions.md` (auto-loaded for all `datacamp/**` files).

---

## 🔗 Connected Projects
- **know-thyself-data** — private repo, source of truth, career identity
- **job-pipeline** — CV generation tool
- **invoice-automation** — first commercial client project
