# Captain's Log — Stardate 20260624
**Date:** 24 June 2026
**Project:** data-brain-gym — Course 4: Introduction to Statistics
**Session:** Chapter 4 Lessons 2–5 + instruction-file maintenance

---

## 🎯 SESSION GOAL

Continue Chapter 4 (Correlation and Hypothesis Testing) with screenshot-verified
lessons, and tighten the instruction-file system against the official GitHub +
VS Code documentation.

---

## SESSION PART 1 — Chapter 4 Lessons 2–5 (Screenshot-Verified)

| Lesson | Type | XP | Topic | Trap captured |
|--------|------|-----|-------|---------------|
| **L2** | Exercise | 100 | Sunshine and sleep — classify H₀ vs. H₁ | Sorting by topic instead of logical form |
| **L3** | Exercise | 100 | The hypothesis testing workflow — order 6 steps | Placing the alternative before the null |
| **L4** | Exercise | 50 | Independent and dependent variables | Selecting an independent variable as the dependent |
| **L5** | Video | 50 | Experiments — treatment/control, randomization, blinding | — (Video; RCT = A/B testing) |

**Block subtotal: 300 XP.** Each Exercise cell includes a `Common Mistake` block
built from the wrong-attempt screenshot.

### Wisdom extracted
- **L2:** Read the verb, not the subject. "No / no difference / no effect" = null;
  "relationship / associated / affects" = alternative. Topic is a distractor.
- **L3:** Null always comes first; the alternative is defined against it.
- **L4:** Ask "what depends on what?" — the variable that changes in response is dependent.
- **L5:** Fewer chances for bias = more reliable causal claims; an RCT is just A/B testing.

---

## SESSION PART 2 — Instruction-File Maintenance

### Cadence rule added (`datacamp.instructions.md`)
`copilot_getNotebookSummary` now runs only at **chapter start/end** and session
bootstrap. Between lessons, trust the `edit_notebook_file` return value. Stops
redundant summary calls every lesson.

### New reference doc (`know-thyself-data/docs/copilot-instructions-best-practices.md`)
A summarized digest of the official GitHub + VS Code custom-instructions docs, so
we stop re-fetching the web mid-session. Covers: file types, `applyTo` globs,
length rule, writing tips, priority order, troubleshooting, decision guide.

### `datacamp.instructions.md` de-duplication (Option 1)
Verified against the docs that the file was ~2× our north star and repeated rules
2–3×. Trimmed **258 → 237 lines** with zero loss of reasoning:
- Fixed a double `---` separator and a corrupted emoji (`�️` → `🗂️`).
- Replaced the 12-item Quality Checklist with a 4-item mechanical Pre-Insertion Gate.
- Removed the Mistakes table (all five rules already stated in the templates).
- Confirmed via `grep` each removed rule still survives in its canonical home.

### Question answered (no change)
Why two `copilot-instructions.md` files load: multi-root workspace auto-injects
both project files. Cost is marginal (~65 idle lines); shared rules load via the
symlink regardless. Recommendation: leave it — architecture already optimizes this.

---

## 📊 COURSE PROGRESS

| Chapter | Lessons | XP | Status |
|---------|---------|-----|--------|
| Ch1: Summary Statistics | 12/12 | 750/750 | ✅ |
| Ch2: Probability & Distributions | 13/13 | 750/750 | ✅ |
| Ch3: More Distributions & CLT | 16/16 | 1,000/1,000 | ✅ |
| Ch4: Correlation & Hypothesis Testing | 5/15 | 350/950 | 🔄 |
| **Total** | **46/56** | **2,850/3,450** | **83%** |

---

## 🔜 NEXT STEP

- Next DataCamp lesson: **Ch4 L6 — Recognizing controlled trials** *(Exercise / 100 XP)* — needs screenshot.
- Dropped task (by Data's call): Ch1+Ch2 retrofit of `Interview readiness:` blocks.

**Paused at:** Chapter 4, Lesson 6 — ready for screenshot in next session.

---

## 📁 FILES TOUCHED

**data-brain-gym:**
- `04-introduction-to-statistics.ipynb` — added Ch4 L2–L5; updated progress table (51 → 55 cells)
- `.github/instructions/datacamp.instructions.md` — cadence rule + de-duplication trim

**know-thyself-data:**
- `docs/copilot-instructions-best-practices.md` — new summarized reference doc

🖖 *Live long and prosper, Data.*
