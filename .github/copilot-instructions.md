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
│   ├── foundations/      ← theory tracks — always before practical work
│   │   ├── data-literacy-professional/   ← 8 courses, 15h (active)
│   │   ├── data-storytelling/            ← 4 courses, 6h
│   │   └── data-skills-for-business/     ← 6 courses, 17h
│   └── sql-for-business-analysts/        ← practical SQL track (resumes after foundations)
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

## � DataCamp Notebook Standard

All DataCamp theory lessons are stored as Jupyter notebooks with markdown cells only (no code until Course 8).

**Video lesson cell structure:**
```
#### Chapter X — Lesson N: [Title] *(Video / XP)*
> 🎬 [Watch on DataCamp](URL) *(requires login)*
**🎯 GOAL** — 1–2 sentence synthesis
**🧠 Mental Map** — ASCII map as primary explanation (always for video lessons with structure)
> callout annotations — only for what the map cannot show (e.g. bias traps, key definitions)
**💡 Why this matters** — business context
**✅ RECAP** — 3–5 bullets: key concept, common mistake, question to ask
```

> **Template rule:** The map IS the explanation. No numbered prose list. Use `>` callouts only for annotations the map cannot carry (a trap, a definition, a caveat). If a video lesson has no mappable structure, use a short unnumbered prose paragraph instead.

**Exercise / Practice cell structure:**
```
#### Chapter X — Lesson N: [Title] *(Exercise or Practice / XP)*
**📋 Scenario** — DataCamp scenario + task
**✅ Solution** — table: Item | Classification | Why
**🧠 Mental Map** — ASCII tree (only when concept has a hierarchy or classification structure)
**💡 Why this matters** — business relevance
**✅ RECAP** — 3–5 bullets
```

**ASCII mental map rule — add only when:**
- Concept is a hierarchy or tree (e.g. Data Context, storage evolution)
- Concept is a classification into categories (e.g. structured/unstructured, quantitative/qualitative)
- The structure itself is the lesson — closing your eyes, you should be able to see it

**Skip the mental map when:**
- Single question with one correct answer (table is sufficient)
- Linear concept with no branches
- The table already captures the full structure

**Format rule:** ASCII trees in notebooks (render everywhere, no dependencies). Mermaid diagrams in `.md` guide files only.

---

## �🔗 Connected Projects
- **know-thyself-data** — private repo, source of truth, career identity
- **job-pipeline** — CV generation tool
- **invoice-automation** — first commercial client project
