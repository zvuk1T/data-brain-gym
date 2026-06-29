# Captain's Log — Stardate 20260629
**Date:** 29 June 2026
**Project:** data-brain-gym — Course 4: Introduction to Statistics
**Session:** Chapter 4 Lessons 6–12 + instruction-system cleanup

---

## 🎯 SESSION GOAL

Advance Chapter 4 (Correlation and Hypothesis Testing) with screenshot-verified
lessons, and harden the instruction system against two recurring frictions: a
non-deterministic notebook-summary cadence rule and an obsolete model-specific
instruction file.

---

## SESSION PART 1 — Chapter 4 Lessons 6–12 (Screenshot-Verified)

| Lesson | Type | XP | Topic | Trap captured |
|--------|------|-----|-------|---------------|
| **L6** | Exercise | 100 | Recognizing controlled trials | Recorded ≠ assigned — smoking survey is observational |
| **L7** | Exercise | 50 | Why use randomization? | "Best describes" = most complete; option 1 is a partial truth |
| **L8** | Video | 50 | Correlation | Pearson r = magnitude (strength) + sign (direction); correlation ≠ causation |
| **L9** | Practice | 50 | Identifying correlation | Visible trendline ≠ strong; 0.66 is moderate |
| **L10** | Exercise | 50 | What can correlation tell you? | "causes" vs. "related to"; DataCamp's own feedback wording was contradictory |
| **L11** | Exercise | 50 | Confounding variables | Confounder needs BOTH tests; matched smoking is controlled |
| **L12** | Video | 50 | Interpreting hypothesis test results | p-value = P(data \| H₀), not P(H₀ true); "fail to reject" ≠ "accept" |

**Block subtotal: 400 XP.** Exercise/Practice cells carry a `Common Mistake`
block where a wrong-attempt screenshot existed (L6, L7, L10, L11). L9 was correct
on first try → no `Common Mistake` block, per template.

### Wisdom extracted
- **L6:** One test for a controlled trial — *did the experimenter assign the treatment?* Historic/observed/self-selected data → observational.
- **L7:** In a "best describes" question, read "best" as "most complete." Option 3 was the CLT, option 5 was blinding — neither is randomization.
- **L8:** A correlation coefficient answers *how linear, which direction* — never *does A cause B.* Reflex on any strong r: *what confounder affects both?*
- **L9:** Two-step decode of any coefficient — sign for direction, magnitude for strength. Scatter is the visual tell that a relationship isn't strong.
- **L10:** Correlation licenses exactly two claims — a relationship exists + its direction. Filter: delete every "causes" option first, then check direction.
- **L11:** A confounder must affect the outcome AND differ between groups. "Similar X across groups" is an explicit controlled-variable flag.
- **L12:** Decision rule p ≤ α → reject H₀. Type I = false positive, Type II = false negative.

### L10 — the dangerous confusion (worth recording)
Data flagged genuine confusion here. Two stacked traps: (1) options 1 and 4
differed by only two words ("causes" vs. "is related to"); (2) DataCamp's
wrong-answer feedback called water cost the "independent" variable, contradicting
L9's own Correlation Explorer axis labels (y-axis = dependent) and the L1 axis
convention. Conclusion: a likely DataCamp typo for *dependent* — the confusion
was their wording, not Data's logic. The lesson cell documents both traps so the
record is honest about the source-side error.

---

## SESSION PART 2 — Instruction-System Cleanup

### Cadence rule made deterministic (`datacamp.instructions.md`)
The notebook-summary cadence rule previously re-fetched "if the injected context
indicates the user reordered or deleted cells" — which relied on judgment to
separate the harness's routine *"potentially reordered"* notice from a real
signal. That judgment failed twice in one session (two redundant summary calls).
Rewrote to two concrete triggers: (a) context **explicitly names** a
reorder/deletion, or (b) the `edit_notebook_file` return value shows unexpected
neighbours. Added an explicit clause that the routine harness notice does **not**,
on its own, count as a trigger. Self-correcting rule fix — same pattern as the
screenshot rule (added after fabrication) and the original cadence rule.

### Deleted `haiku.instructions.md`
Data is no longer working with the Haiku model, so the model-specific guardrail
file (HARD STOPS table, pre-edit checklist, session-start protocol) is redundant.
Audited every rule first: each survives in its canonical home — hard-rules
(screenshot, one-cell, confirm), `datacamp.instructions.md` (Pre-Insertion Gate,
templates), and `new-session.prompt.md` (bootstrap). Zero rule loss. Only
remaining reference is a historical captain's-log note (correct as history).
`.github/instructions/` now holds a single file: `datacamp.instructions.md`.

---

## 📊 COURSE PROGRESS

| Chapter | Lessons | XP | Status |
|---------|---------|-----|--------|
| Ch1: Summary Statistics | 12/12 | 750/750 | ✅ |
| Ch2: Probability & Distributions | 13/13 | 750/750 | ✅ |
| Ch3: More Distributions & CLT | 16/16 | 1,000/1,000 | ✅ |
| Ch4: Correlation & Hypothesis Testing | 12/15 | 750/950 | 🔄 |
| **Total** | **53/56** | **3,250/3,450** | **94%** |

Notebook progress table (Cell 2) synced to match this state.

---

## 🔜 NEXT STEP

- Next DataCamp lesson: **Ch4 L13 — Significance levels vs. p-values** *(Exercise / 100 XP)* — needs screenshot.
- Then L14 (Type I and type II errors, Exercise / 50 XP) and L15 (Congratulations!, Video / 50 XP) — L15 completes the course → trigger Chapter 4 recap cell + final progress sync.

**Paused at:** Chapter 4, Lesson 13 — chat hit the image limit (could not attach
new screenshots). Continue in a new chat via `#file:new-session.prompt.md`.

---

## 📁 FILES TOUCHED

**data-brain-gym:**
- `04-introduction-to-statistics.ipynb` — added Ch4 L6–L12 (7 lessons); synced progress table (55 → 62 cells)
- `.github/instructions/datacamp.instructions.md` — cadence rule made deterministic
- `.github/instructions/haiku.instructions.md` — **deleted** (obsolete; no rule loss)
- `captains-log/captains-log-stardate-20260629.md` — this log

🖖 *Live long and prosper, Data.*
