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

🖖 *Live long and prosper, Data.*
