# Captain's Log — Stardate 20260720
**Date:** 20 July 2026
**Project:** data-brain-gym — Course 5: Introduction to Data Culture
**Session:** Reconciliation — recover uncommitted Chapter 1 Lessons 1–7

---

## 🎯 SESSION GOAL

Session bootstrap surfaced a discrepancy: the Course 5 Markdown file was ahead of
the captain's log. Fix the neusklađenost (reconcile file ↔ log ↔ git) before
resuming new lesson work.

---

## 🔍 DISCREPANCY FOUND (at bootstrap)

The `20260629` log recorded Course 5 as "backbone only — no lessons yet." On
restore, the file `05-introduction-to-data-culture.md` already contained
**Chapter 1 Lessons 1–7**, written in an unlogged session and left **uncommitted**
in the working tree. Three problems:

1. Lessons 1–7 present in the file but not committed (working tree modified since `d75edfd`).
2. The `### 📊 Course Progress` table was stale — still `0/23 · 0/1,500 · 0%`.
3. No captain's log covered the session that wrote those lessons.

Per bootstrap rule: **the source file is treated as source of truth** — the
lessons are real work; the log was simply missing.

---

## ✅ RECONCILIATION ACTIONS

| Step | Action |
|------|--------|
| 1 | Verified via `git diff` that the uncommitted change was exactly Lessons 1–7 + the progress table + Knowledge Map placeholder — no unexpected edits. |
| 2 | Synced the `### 📊 Course Progress` table: Ch1 → **7/10 · 400/600 · 🔄**, Total → **7/23 · 400/1,500 · 27%**. |
| 3 | Committed as `d97f1fa` — "Add Course 5 Chapter 1 Lessons 1-7 + sync progress table". |
| 4 | Wrote this log to close the record gap. |

### XP math (verification)
7 lessons: L1 50 + L2 50 + L3 50 + L4 50 + L5 50 + L6 100 + L7 50 = **400 XP** of Ch1's 600. Checks out.

---

## SESSION PART 2 — Chapter 1 Lessons 8–10 + Chapter 1 Complete (Screenshot-Verified)

| Lesson | Type | XP | Topic | Trap captured |
|--------|------|-----|-------|---------------|
| **L8** | Exercise | 50 | People challenges unfolded | Ethics-blind "more data" — collecting customer social data without consent is a privacy/trust violation |
| **L9** | Exercise | 50 | The process matters | Failure-as-fix — options phrased as the *absence* of a safeguard (no validation/encryption/authorization) are risks, not remedies |
| **L10** | Exercise | 100 | Anything dubious? | Automation-as-red-flag — judging "automation" by the word, not its stated effect (quality + efficiency) |

**Block subtotal: 200 XP.** L10 carries a `Common Mistake` block from the wrong-attempt (drag-into-buckets) screenshot; L8 and L9 were correct on first try → no `Common Mistake` block, per template.

### Wisdom extracted
- **L8:** Data ethics is a *people* challenge (L7's "softer" family). One test for a bad initiative: does it collect data without consent? If yes, it invades privacy and burns trust — fatal for an insurer.
- **L9:** The mirror of L8 — the *process* family (quality/privacy/security). The tell: an option stating a safeguard's *absence* is the failure it's meant to prevent, never the fix.
- **L10:** Capstone blending L3's myths, L4's levers, L7's challenges. Inaccurate claims share a signature — absolutism ("won't need any revision") and tech-worship ("as many technologies as possible"). Judge automation by effect, not by the word.

### Chapter 1 closed
Added the `### Chapter 1 — Recap` cell (mental-shift + 600/600 XP). Synced the progress table to Ch1 10/10 · 600/600 ✅ and Total 10/23 · 600/1,500 · 40%. Committed as `d278e3e`.

---

## 📊 COURSE PROGRESS

| Chapter | Lessons | XP | Status |
|---------|---------|-----|--------|
| Ch1: Getting to Know Data Culture | 10/10 | 600/600 | ✅ |
| Ch2: Data Culture in Depth | 0/13 | 0/900 | ⬜ |
| **Total** | **10/23** | **600/1,500** | **40%** |

---

## 🔜 NEXT STEP

- **Course 5, Chapter 1 — COMPLETE.** All 10 lessons populated, recap cell added, tables synced, committed (`d278e3e`).
- **Next lesson:** Chapter 2 — Lesson 1: Assessing capabilities *(Video / 50 XP)* — needs a screenshot before any content is written.
- **Deferred:** codify the MD course-header template in `datacamp.instructions.md` once lessons validate the format.

**Paused at:** Chapter 1 committed, working tree clean; standing by for the Chapter 2 — Lesson 1 screenshot.

---

## 📁 FILES TOUCHED

**data-brain-gym:**
- `datacamp/true-story-data/data-literacy-professional/05-introduction-to-data-culture.md` — committed previously-uncommitted Lessons 1–7 + synced table (`d97f1fa`); added Lessons 8–10 + Chapter 1 Recap; synced table to 40% and committed Chapter 1 (`d278e3e`)
- `captains-log/captains-log-stardate-20260720.md` — this log

---

## SESSION PART 3 — Chapter 2 Opened: Lesson 1 (Assessing capabilities)

Later the same day, resumed Course 5 at Chapter 1 complete and opened **Chapter 2:
Data Culture in Depth**. Session cut short — Data switching to another project —
so closed cleanly at Lesson 1.

| Lesson | Type | XP | Topic | Key content |
|--------|------|-----|-------|-------------|
| **Ch2 L1** | Video | 50 | Assessing capabilities | The **maturity model** — five levels for measuring data-culture progress |

### The five-level maturity model (course's own, not Gartner/IBM)
Awareness → Adoption → Standardization → Optimization → Innovation.
- **Awareness:** data matters, no plan.
- **Adoption:** some data-informed decisions, limited/siloed.
- **Standardization:** silos broken, one unified vision.
- **Optimization:** efficiency via coordinating groups + data streams.
- **Innovation:** data's value realized at every level; data drives innovation.

Models are customizable (Gartner, IBM = same end, different names); none is
complete → course builds its own five-level model. Case study **Shine & Glow**
(organic skincare): Awareness overall, uneven pockets (marketing robust, product
dev on gut feeling); bridge gaps via roadmap + reuse marketing's data platform
for research (breaks infrastructure silos); no one-size-fits-all — start with an
honest assessment.

### Wisdom extracted
- **L1:** You can't improve what you can't measure — the maturity model turns "are
  we data-driven?" into a specific level + a concrete next step. Assessment is
  rarely uniform: find strong pockets, make them models for the rest.

### Connections drawn
- Standardization (level 3) = L7's "breaking data silos" as a maturity milestone.
- Optimization (level 4) = L4's efficiency levers operationalized (coordinating
  groups + data streams).

### ⚠️ Process note — RULE 1 violation, corrected
This session first wrote the work into a new `captains-log-stardate-20260720b.md`
— a `-b` variant, violating HARD RULE 1 (one log per day). Data caught it. The
`-b` file was deleted and the content merged here as SESSION PART 3, where it
belongs. Same mistake as the documented `20260610` and `20260619` cases — the fix
is always: `file_search` the date first, then append a `## SESSION PART`.

### Progress after this session

| Chapter | Lessons | XP | Status |
|---------|---------|-----|--------|
| Ch1: Getting to Know Data Culture | 10/10 | 600/600 | ✅ |
| Ch2: Data Culture in Depth | 1/13 | 50/900 | 🔄 |
| **Total** | **11/23** | **650/1,500** | **43%** |

### Next step
- **Course 5, Chapter 2 — IN PROGRESS.** Lesson 1 committed (`edefc16`, WIP checkpoint — not the chapter-close commit).
- **Next lesson:** Chapter 2 — Lesson 2: Maturity model basics *(Exercise / 50 XP)* — needs a screenshot.
- No `Chapter 2 — Recap` cell yet; add only when all 13 lessons are done.

**Paused at:** Chapter 2 Lesson 1 committed; standing by for the Chapter 2 — Lesson 2 screenshot. Data switching to another project.

### Files touched (this part)
- `datacamp/true-story-data/data-literacy-professional/05-introduction-to-data-culture.md` — added Chapter 2 Lesson 1 + synced progress table to 43% (`edefc16`)
- `captains-log/captains-log-stardate-20260720.md` — appended this SESSION PART 3

🖖 *Live long and prosper, Data.*

---

## SESSION PART 4 — Chapter 2 Lessons 2–10 (Screenshot-Verified)

Resumed Course 5 Chapter 2 at Lesson 2. Completed Lessons 2–10, cleaned up fabricated Lessons 4–13 discovered in the file, and synced the progress table after each verified lesson.

| Lesson | Type | XP | Topic | Trap captured |
|--------|------|-----|-------|---------------|
| **Ch2 L2** | Exercise | 50 | Maturity model basics | Absolutism — "all companies must start at the bottom" treats a diagnostic as a mandatory ladder |
| **Ch2 L3** | Exercise | 100 | Assessing data culture maturity | Keyword conflation — "standard tool" ≠ "optimized use"; listen to each level's vocabulary |
| **Ch2 L4** | Video | 50 | The power of leadership and buy-in | Data leaders ≠ executives; both are needed for buy-in |
| **Ch2 L5** | Exercise | 50 | The value of data leaders | Executive-only + usage-over-strategy traps |
| **Ch2 L6** | Exercise | 100 | What makes a good data leader | Force-without-support and title-chasing are irrelevant |
| **Ch2 L7** | Video | 50 | Becoming sustainable | Sustainable data culture = regular + environmental/social/economic + ethics + long-term planning |
| **Ch2 L8** | Exercise | 50 | Why we strive for sustainability | "Solely environmental" narrows sustainability too much |
| **Ch2 L9** | Exercise | 100 | Way to build a sustainable data culture | Cloud/energy-reduction sounds general but is a sustainability signal |
| **Ch2 L10** | Video | 50 | Leaping into a data culture | Four stakeholder groups and their concrete actions |

**Block subtotal: 550 XP.** Lessons 2, 3, 6, 8, 9 had wrong-attempt screenshots → `Common Mistake` blocks included where applicable. Lessons 4, 5, 7, 10 were correct on first try / transcript-based → no `Common Mistake` block.

### Cleanup performed
- Discovered fabricated content for Chapter 2 Lessons 4–13 in the file (invented scenarios, partial cells, invented "Congratulations!" content).
- Rewrote Lesson 4 from transcript and Lesson 5 from screenshot.
- Removed fabricated Lessons 6–13; re-added Lessons 6–10 from screenshots/transcript as verified.
- Progress table now reflects only verified lessons.

### Progress after this session

| Chapter | Lessons | XP | Status |
|---------|---------|-----|--------|
| Ch1: Getting to Know Data Culture | 10/10 | 600/600 | ✅ |
| Ch2: Data Culture in Depth | 10/13 | 650/900 | 🔄 |
| **Total** | **20/23** | **1,250/1,500** | **83%** |

### Next step
- **Course 5, Chapter 2 — IN PROGRESS.** Lessons 1–10 populated, 3 lessons remain.
- **Next lesson:** Chapter 2 — Lesson 11: Identify the stakeholders *(Exercise / 100 XP)* — needs a screenshot.
- No `Chapter 2 — Recap` cell yet; add only when all 13 lessons are done.

**Paused at:** Chapter 2 Lesson 10 committed; standing by for the Chapter 2 — Lesson 11 screenshot. Data switching to another project.

### Files touched (this part)
- `datacamp/true-story-data/data-literacy-professional/05-introduction-to-data-culture.md` — added Lessons 2–10, removed fabricated Lessons 4–13, synced progress table to 83%
- `captains-log/captains-log-stardate-20260720.md` — appended this SESSION PART 4

🖖 *Live long and prosper, Data.*
