# Captain's Log — Stardate 20260527

**Mission:** mock-interviews — founding session
**Officer:** Lieutenant Commander Data (zvuk1T)
**Science Officer:** Spock

---

## WHERE WE STARTED

New repo. First entry. All decisions made today in conversation before a single file was written.

---

## WHAT WE ACCOMPLISHED TODAY

**Repo created — decisions documented:**
- Name chosen: `mock-interviews` — clear to any recruiter, professional, standard term in hiring
- Separate repo from `job-pipeline` — clean separation of concerns, independently visible on GitHub
- Folder structure defined and created
- README written — explains purpose, structure, sources, daily habit

**Learning strategy defined:**
- SQL problems from DataLemur — interview-focused, real company questions, free
- Python from DataCamp — already subscribed, format matches learning style
- Each SQL problem also solved in Python/Pandas — forces conceptual understanding over syntax
- When SQL is the better tool: documented explicitly — this distinction is itself a learning outcome
- DataCamp courses identified: "Cleaning Data in Python" + "Data Manipulation with pandas"

**Daily habit structure:**
- Monday / Wednesday / Friday — SQL (DataLemur, 1 problem)
- Tuesday / Thursday — Python/Pandas (DataCamp)
- Saturday — case study or behavioural (Tell me about yourself)
- Sunday — free or weekly review
- Time: 30–45 minutes per session

**Problem documentation standard:**
- `problem.md` — statement, source, difficulty
- `solution.sql` — SQL solution + line-by-line explanation
- `solution.py` — Python/Pandas solution + explanation
- `notes.md` — when to use which tool, key concepts, ✅ Notes for Students

---

## WHERE WE STOPPED

Repo created, structure in place, first commit pending.

---

## NEXT STEP

1. Create `copilot-instructions.md` for this repo
2. First commit — push to GitHub
3. First problem — SQL, medium difficulty, DataLemur

---

## DECISIONS MADE TODAY

| Decision | Reason |
|---|---|
| Repo name: `mock-interviews` | Standard recruiter term, clear at a glance |
| Separate from job-pipeline | Independent visibility, clean separation |
| DataLemur for SQL | Interview-focused, real questions, free |
| DataCamp for Python | Already subscribed, format works |
| Dual solution per problem | Conceptual understanding over syntax |
| Start at medium difficulty | Easy problems do not reflect real interviews |

---

## ✅ Notes for Students

Starting a new learning project is easy. Maintaining it is not. The structure we built today — fixed days, fixed time, fixed format — exists for one reason: to remove daily decision-making. When the system decides what you do, you only have to show up.

The dual SQL + Python approach is not about doing twice the work. It is about understanding that tools are interchangeable when the concept is clear. A student who understands GROUP BY will have no trouble with `.groupby()`. The concept transfers. The syntax is just syntax.

Start at medium difficulty. Easy problems feel productive but do not prepare you for real interviews. Discomfort at medium difficulty means you are learning something. That is the point.

Document everything as you go — not after. A solution without explanation is just an answer. An answer with explanation is a teaching resource. Build for the next student, even when that student is your future self.

---
---

## SESSION 2 — Architecture and Infrastructure

---

## WHAT WE ACCOMPLISHED TODAY

**Confirmation Rule — strengthened across all repos:**
- Rule 1 in `data-spock-core.instructions.md` updated: announce and stop, no action in same message
- `⚠️ Confirmation Rule` block added to `copilot-instructions.md` in all repos
- "continue" established as standard confirmation keyword

**Prompt infrastructure — deployed across all repos:**

| Prompt | mock-interviews | job-pipeline | know-thyself-data | know-thyself-bot | invoice-automation |
|---|---|---|---|---|---|
| `new-session` | ✅ | ✅ | ✅ | ✅ | ✅ |
| `update-captains-log` | ✅ | ✅ | ✅ | ✅ | ✅ |
| `new-problem` | ✅ | — | — | — | — |
| `new-month` | — | — | — | — | ✅ |

**`invoice-automation` and `know-thyself-bot` — synced with shared architecture:**
- `copilot-instructions.md` slimmed down, `⚠️ Confirmation Rule` added, prompts created

**`repo-architecture.md` — created:**
- Location: `know-thyself-data/docs/repo-architecture.md`
- Documents: four-repo ecosystem, symlink mechanics, instructions vs prompts, manual sync rules

**`know-thyself-data` folder structure — reorganized:**
- `documents/` renamed to `source-of-truth/`
- Empty `evidence/` folder removed

**`chat-exports/` subfolder — standardized across all repos:**
- `captains-log/chat-exports/` gitignored in all five repos
- Chat transcripts are private, never go to GitHub

---

## WHERE WE STOPPED

Full infrastructure complete. All five repos synced, committed, and pushed.

---

## NEXT STEP

1. Open `mock-interviews` workspace
2. Run `#new-session.prompt.md` — verify it works
3. Run `#new-problem.prompt.md` — first SQL problem, medium difficulty, DataLemur

---

## ✅ Notes for Students

Today's session was not about writing code. It was about building the infrastructure that makes every future session faster and safer.

The most important lesson: **a rule that is too abstract will be broken.** "Announce, wait for Continue" sounds clear — but leaves room for interpretation. "Do not create files in the same message as the announcement" is a binary check. Either you did it or you didn't. When writing rules for automated systems, prefer binary checks over abstract principles.

Second lesson: **gitignore before you commit.** Chat exports, personal documents, salary information — these things end up in the wrong place exactly once. After that, the damage is done. The habit of checking `git status` before every commit is not paranoia. It is engineering discipline.
