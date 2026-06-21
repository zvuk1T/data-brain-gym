---
applyTo: "datacamp/**"
---

# DataCamp Folder Instructions
## data-brain-gym — Spock working in `datacamp/`

> These instructions apply automatically to all files inside `datacamp/`. They do not load for SQL drills, behavioural exercises, or Python problems. Rules here are DataCamp-specific — global project rules remain in `.github/copilot-instructions.md` and `~/.copilot/instructions/data-spock-core.instructions.md`.

---

## 🎯 Purpose of This Folder

`datacamp/` contains all DataCamp coursework — structured as a layered learning system, not a collection of completed exercises.

**Three theory tracks before any practical work:**
```
true-story-data/
├── data-literacy-professional/   ← 8 courses, 15h — what data is and how to reason with it
├── data-storytelling/             ← 4 courses, 6h  — how to communicate insights
└── data-skills-for-business/      ← 6 courses, 17h — governance, ethics, AI, management

sql-for-business-analysts/         ← practical track — resumes AFTER true-story-data is complete
```

**Rule:** No practical track work until all 3 true-story-data tracks are complete. There are no exceptions.

---

## 📂 Notebook File Naming

One notebook per course. Named by course number within the track.

```
true-story-data/data-literacy-professional/
├── 01-introduction-to-data.ipynb
├── 02-communicating-data-insights.ipynb
├── 03-introduction-to-data-literacy.ipynb
...
```

**Why per-course, not per-track:** A single file for all 8 courses would exceed 5,000+ lines. The model's context window would be exhausted before Course 3. Per-course files keep context manageable and enable recovery without re-reading the entire track.

---

## 📖 Pre-Session Workflow — Before Any Screenshot

**Step 1 — Read the course outline**
Open the course header cell (Cell 1) in the active notebook. Confirm which chapter and lesson is next.

**Step 2 — Check for PDF slide decks**
Look in the course's `-assets/` folder (e.g. `02-communicating-data-insights-assets/`). If PDF slide decks are present, they have been pre-loaded into a **Course Knowledge Map** cell (Cell 2 in the notebook). Read it before any screenshot arrives.

**Step 3 — PDF pre-loading (if not yet done)**
If PDFs exist but no Course Knowledge Map cell exists yet:
```bash
python3 -c "
import subprocess
for pdf in ['chapter1.pdf', 'chapter2.pdf', ...]:
    result = subprocess.run(['pdftotext', '-layout', pdf, '-'], capture_output=True, text=True)
    print(result.stdout)
"
```
Parse all chapter PDFs. Build a Course Knowledge Map cell. Add it as Cell 2, immediately after the course header, before any lesson cell.

**Step 4 — Confirm position**
Tell Data exactly which lesson is next and wait for confirmation before requesting a screenshot.

**Why this matters:**
When a screenshot arrives cold (no pre-loaded context), Spock builds the cell from scratch — more messages, shallower synthesis, higher risk of 413. With a Course Knowledge Map loaded, the screenshot is a confirmation pass, not a discovery pass. Depth increases, session length decreases.

---

## 🦴 Course Backbone Rule — One Course at a Time

Before starting any new course, Data sends PDF slide decks **for that course only**.
Spock extracts the content → builds the **Course Knowledge Map** cell (Cell 2) → THEN screenshots begin.

**Do NOT pre-build Knowledge Maps for multiple courses upfront.** One course at a time, just before that course starts.

Why: pre-loading all courses in one session wastes context, loses freshness, and creates a false sense of readiness. The backbone is built when the course is ready to begin — not as a batch operation.

**Current state (as of 20260621):**
- Course 4 Chapter 1 complete — all 12 lessons written, 750 XP achieved
- Lessons 1–12: header + Knowledge Map + full lesson cells with trap-based error analysis
- Course 4 Chapter 2 backbone: ready for screenshots (Knowledge Map pre-loaded from PDFs)
- Course 5+ backbones: build when each course starts

---

## 📸 Screenshot Workflow — The Only Source

**Spock never generates lesson content without a screenshot.**

DataCamp lesson content is proprietary. Our synthesis layer (GOAL, mental map, Why it matters, RECAP) is built on top of what the screenshot shows — never guessed from lesson titles or prior knowledge.

**What a complete screenshot set looks like per lesson:**
- **Video lesson:** transcript slide(s) — all visible text from the video
- **Exercise / Practice:** scenario text + task + hint (if available)

**If a screenshot is incomplete or missing:**
Spock announces what is missing and asks for it. No partial cells — a half-built cell is worse than no cell because it looks complete but isn't.

**One cell at a time.** Do not request multiple screenshots or build multiple cells in one message. Build, verify, then proceed.

---

## 📓 Lesson Cell Templates

All DataCamp theory notebooks contain **markdown cells only** (no code cells until Course 8 case study).

---

### 🎬 Video Lesson Template

```markdown
#### Chapter X — Lesson N: [Title] *(Video / XP)*

> 🎬 [Watch on DataCamp](URL) *(requires login)*

---

**🎯 GOAL — What is this lesson about?**
[1–2 sentence synthesis of the lesson's core argument]

---

[Prose explanation — 2–4 sentences covering the core concept. For classification/comparison concepts, use a Markdown table instead (see table rules below).]

---

**💡 Why this matters**
[One paragraph: business or professional context. Answers: why would a data analyst need to know this?]

**✅ RECAP**
- [Key concept]
- [Common mistake or trap]
- [What to remember next time]

**🔗 Connection**
- [How this concept links to another chapter, course, or real-world pattern — max 3 bullets]
- [Skip this section entirely if there is no genuine connection to make]
```

**Rules:**
- `🎬` link appears ONLY in video lessons — never in exercise or practice cells.
- No ASCII trees. Prose or Markdown table only.
- `🔗 Connection` is for genuine cross-chapter or cross-course links only — not a restatement of the RECAP.

---

### 📝 Exercise / 🔘 Practice Template

```markdown
#### Chapter X — Lesson N: [Title] *(Exercise or Practice / XP)*

---

**🎯 GOAL — What does this exercise test?**
[One sentence: what concept or skill is being tested — not the scenario, the pedagogical purpose]

---

**📋 Scenario**
[DataCamp scenario text — verbatim or closely paraphrased from screenshot]

**Task:** [What DataCamp asks — exact task statement]

---

**✅ Solution**
[Table: Item | Classification | Why  — or  Option | Verdict | Why]

---

**💡 Why this matters**
[One paragraph: business relevance]

**✅ RECAP**
- [3–5 bullets]

**🔗 Connection**
- [Only when a genuine link exists — skip otherwise]
```

**Rules:**
- NO `🎬` link in exercise or practice cells.
- `🎯 GOAL` is mandatory in every exercise and practice cell — one sentence, pedagogical purpose, not a restatement of the scenario.
- No ASCII trees. Solution table is the structural element.

---

### 🔴 Error-Driven Solution Table — When User Sends Wrong Answer Screenshot

This follows the **Error-Driven Learning Rule** (see `data-spock-core.instructions.md`).

**When building an exercise or practice lesson cell where Data sent screenshots showing both correct AND incorrect attempts:**

1. **Show all options** — do not hide the wrong answers
2. **Solution table format:**
   ```
   | Option | Verdict | Explanation | Why This Trap (if incorrect) |
   |--------|---------|-------------|---------------------------|
   | [Option A text] | ✅ Correct | [Why it works] | — |
   | [Option B text] | ❌ Wrong | [Why it fails] | Pattern: [Trap name]. You chose this because [specific misconception]. |
   | [Option C text] | ❌ Wrong | [Why it fails] | Name: [Trap name]. The confusion: [what looks like logic but isn't]. |
   ```

3. **Add "Common Mistake" section** — placed AFTER the solution table, BEFORE "Why This Matters":
   ```
   **Common Mistake**
   [Trap name]. [Root cause of misconception]. 
   **→** *[Wisdom statement: the shift in thinking this error teaches]*
   ```

4. **Wisdom statement rules:**
   - One bold sentence starting with `**→**`
   - Action-oriented: "here is how you will think differently next time"
   - Specific to the trap, not generic advice
   - Example: `**→** *Histogram x-axis width measures spread; y-axis measures frequency. Always verify axes first.*`

**Example: Course 4, Lesson 8 — "Most Frequent Crimes"**

When Data selected the wrong option (ranked position instead of maximum frequency):

| Option | Verdict | Explanation | Why This Trap |
|--------|---------|-------------|---------------|
| Rank 1: Theft | ✅ Correct | Theft has the highest frequency (mode = maximum). | — |
| Rank 3: Robbery | ❌ Wrong | Has lower frequency than Theft; only third-most frequent. | **Trap: Ranking confusion.** You thought mode meant "middle-ranked typical value", not "highest magnitude". Mode = max, always. |
| Rank 5: Other | ❌ Wrong | Lowest frequency; least common crime in dataset. | **Trap: Inversion.** Opposite of correct — chose the rarest instead of most common. |

**Common Mistake**
Confusing mode (maximum frequency) with a ranked position or "typical middle" value. Mode in statistics is not soft or average — it is the single highest-frequency category, identical to maximum for categorical data.
**→** *When you see "mode" in statistics, translate it to "maximum". Mode = max. The highest-frequency category, nothing more.*

---

**Rules:**
- `🎬` link appears ONLY in video lesson cells.
- No ASCII trees. Prose or Markdown table only.
- `🔗 Connection` is for genuine cross-chapter or cross-course links only — not a restatement of the RECAP.

---

## 🗂️ Three-Tier Format System

Notebooks use **three formats** — each for a specific purpose:

| Format | Used in | When to use |
|--------|---------|-------------|
| **Prose** | Notebooks — all lessons | Linear concepts, definitions, introductory explanations |
| **Markdown table** | Notebooks — classification lessons | 2–4 named categories to compare (types, variants, vs. questions) |
| **Mermaid diagram** | `.md` files only — one per chapter | Full chapter concept map — visual, rendered, permanent reference |

**No ASCII trees in notebooks.** They require monospace to look right, have no visual weight, and render as raw code blocks. Tables and prose serve the same purpose and render cleanly.

**Markdown table rules:**
- Use when the lesson is a classification or comparison: `Type A vs. Type B`, `4 analytics types`, `3 keys framework`
- Columns: Name · Core question/definition · Example (or similar — match the concept)
- Do not force a table when prose is clearer

**Mermaid chapter map rules:**
- One `.md` file per chapter, created after all lessons in that chapter are complete (deferred synthesis rule)
- Lives in the course `-assets/` folder: `03-introduction-to-data-literacy-assets/ch1-concept-map.md`
- Shows how chapter concepts connect — not a list of lesson titles
- Built after the chapter recap, not before

**`🔗 Connection` rules:**
- Max 3 bullets
- Only genuine cross-chapter, cross-course, or real-world pattern links
- If there is nothing genuine to connect → skip the section entirely
- NOT a restatement of the RECAP in different words

---

## 💡 "Why This Matters" Rules

- Present in EVERY lesson cell — both video and exercise.
- One paragraph. Connects the concept to a real business or professional context.
- Answers: *why would someone in a data analyst role need to know this?*
- NOT a summary of the lesson — a reason to care about it.
- NOT "this is important because DataCamp says so" — a concrete scenario where this knowledge changes a decision.

**Optional closing line — the Wisdom layer:**
After the paragraph, optionally add one bold `→` sentence:
> **→** *[One sentence: the shift in thinking or action this knowledge produces.]*

Write it only when it genuinely lands — when there is a clear "therefore, act differently" conclusion. If it doesn't land, skip it. No filler. This is the DIKW Wisdom layer: not a summary of what was learned, but the proactive action it enables.

---

## 🗂️ Chapter Structure Rules — Deferred Intro/Recap

**Chapter intro format: compact arc line in the course header cell — NOT a separate cell.**

Add a single italic arc line directly below each chapter's italic description in Cell 1 (course header):
```
*In this chapter, you will learn about...*
*Arc: L1–4 → communication types · L5–7 → insight framework · L8–11 → audience analysis*
```

**Why compact arc, not a separate intro cell:** A separate intro cell written after the chapter is a synthesis — but it is also redundant. The course header already describes the chapter. The arc line adds the one thing the description lacks: the internal structure. One line is sufficient.

**Do NOT write chapter recap cells mid-chapter.**
**Write recap cells AFTER all lessons in that chapter are complete — with full context in hand.**

Reason: A recap written without knowing the full chapter is a guess. A recap written after is a synthesis.
The same principle applies at course level: course recap/summary written only after all chapters are complete.

**When to write them:**
- Chapter arc line: add to course header after the last lesson cell of that chapter is verified
- Chapter recap: after the last lesson cell of that chapter is verified
- Course summary: after all chapter recaps are written

---

## ❌ Mistakes to Never Repeat

These were discovered in practice — documented here so they are not repeated.

| Mistake | What happened | Rule |
|---------|---------------|------|
| `🎬` link in exercise cells | Video lesson link was copied into exercise and practice cell templates | `🎬` link appears ONLY in video lesson cells |
| ASCII map on a single-answer question | Map was added to yes/no practice questions where the table already showed the full structure | Skip map when table is sufficient |
| Numbered prose list + map | Early video cells had both a numbered list AND a map — the same content twice | Map is the primary explanation. No numbered list alongside it |
| Chapter intro written mid-chapter | Intro written after L1 — without knowing what L5–L10 would cover | Defer all intros/recaps until chapter is complete |
| Building a cell from lesson title alone | Without a screenshot, the cell contained plausible-sounding but unverified content | Screenshots are the only source. Never synthesise from titles |
| One giant notebook for entire track | Course 1 alone = 1467 lines. One file for 8 courses would be unmanageable | One notebook per course |
| Template defined before any work existed | Trying to design the perfect template before writing any lesson | Practice → Pattern → Principle. Template emerges from doing, not planning |
| Continuing forward with format drift unresolved | Discovered that Ch1 L1, L5, L8 in Course 1 used old numbered prose format while all later cells used the Mental Map standard | When format drift is discovered in existing notebooks, standardise before continuing with new content. Methodology consistency is higher priority than lesson throughput |
| ASCII trees in notebook cells | Used throughout Courses 1–2 — raw text blocks with no visual weight, no rendering advantage | No ASCII trees in notebooks. Prose for linear concepts, Markdown tables for classification. Mermaid in `.md` files only |

---

## 📊 Course Knowledge Map Cell

Every course notebook should have a **Course Knowledge Map** as Cell 2.

**What it contains:**
- Course arc: how the chapters build on each other (ASCII tree, chapter by chapter)
- Key concepts per video lesson, extracted from PDF slide decks
- Running examples documented as named anchors (e.g. "Buildingsway", "Emma at DataPrint", "Harold")
- Any recurring characters or scenarios that appear across chapters

**How to build it:**
1. Parse the instructor's PDF slide decks using `pdftotext`
2. Extract: course arc, video lesson key concepts, examples, best practices
3. Add as Cell 2 in the notebook, immediately after the course header cell
4. Label it clearly: `## 📖 Course Knowledge Map — Pre-loaded from PDF Slides`

**When PDFs are not available:** Skip the map cell. Build lessons from screenshots only. Do not fabricate course content.

---

## 🔁 Running Examples — How to Document

Some courses use a consistent character or company across multiple lessons (e.g. Buildingsway across Course 2 Ch1 and Ch3; Emma at DataPrint across Course 1).

**Rule:** When a running example appears, name it in the Course Knowledge Map. When it appears in a lesson cell, reference its name in the Scenario block so the connection is visible.

This prevents the question "who is Emma again?" mid-session.

---

## ⚠️ Context Management — 413 Prevention

A 413 error means the request exceeded the model's context window. It is not a data loss event — it is a size event. All work written to notebooks survives.

**Prevention:**
- One lesson cell per message — do not request multiple screenshots at once
- One chapter per session — do not attempt to build a full course in a single session
- After completing each chapter: announce completion, stop, wait for confirmation before continuing

**If a 413 occurs:**
1. Spock reads git status and notebook cell summary to reconstruct the stopping point
2. Spock reads the last cell of the active notebook to confirm the exact lesson completed
3. Session resumes from the next lesson — no content is lost

**Warning signs that context is filling up:**
- Responses getting slower
- Spock asking for clarification on things already established
- Response quality dropping

When these appear: announce current position, update the captain's log, commit, then continue in a fresh session.

---

## � Chat Closing & Opening Protocol

### ⚠️ Warning signs — act before the crash

| Signal | What it means | Action |
|--------|--------------|--------|
| Responses getting shorter without reason | Context compression has started | Finish current lesson, then close |
| Spock asks for clarification on things already established | Old messages have fallen out of the window | Close after current lesson |
| Spock asks for a screenshot already sent | Early context is gone | Close immediately |
| 413 error / conversation won't load | Hard limit hit | New chat, recover from captain's log |

### 🔒 Closing a chat (mandatory steps — in order)

1. **Finish the current lesson cell** — do not close mid-cell
2. **Commit all completed lesson cells** — `git add` + `git commit` with correct message format
3. **Update the captain's log** — stopping point (last lesson completed) + next step (next lesson number and title)
4. **Commit the captain's log**
5. Close the chat

### 🚀 Opening a new chat (mandatory steps — in order)

1. **Run `#file:new-session.prompt.md`** — reads the two latest captain's logs, gives position summary
2. **Get notebook summary** — `copilot_getNotebookSummary` to confirm current cell count and state
3. **Read the last written lesson cell** — confirm exact stopping point (lesson title, chapter)
4. **Announce the next lesson** — state lesson number, title, type (Video/Exercise/Practice) and XP
5. **Wait for Data's confirmation** before requesting a screenshot

**The commit boundary rule:**
> One chapter = one natural commit boundary = one chat session.
> Do not push into the next chapter in the same chat. If a chapter is long (15+ lessons), commit after a logical thematic block.

---

## �📅 Session End Checklist

After each DataCamp working session:

1. ✅ All lesson cells for the session are written and verified
2. ✅ Captain's log updated with: lessons completed, decisions made, next step
3. ✅ `git status` checked — no unintended files staged
4. ✅ Commit covers one logical unit: `"Complete Course N Chapter X — N lessons"`

**Commit message format for DataCamp notebooks:**
```
Complete Course 2 Chapter 1: Communicating Information — 11 lessons

- Ch1 L1–L11 all cells written and verified
- Course Knowledge Map pre-loaded from PDF slide decks
- Running example: Harold / Buildingsway documented
```

---

## 🔗 Cross-Track Awareness

Some courses appear in multiple DataCamp tracks. If a course is shared:
- It is learned once (in whichever track is active first)
- The notebook lives in the folder of the track where it was first completed
- A note is added to the other track's README pointing to the completed notebook

Shared courses as of June 2026:
| Course | Data Literacy Professional | Data Storytelling | Data Skills for Business |
|--------|---------------------------|-------------------|--------------------------|
| Introduction to Data | ✅ (1) — done | — | ✅ (1) — shared |
| Communicating Data Insights | ✅ (2) — active | ✅ (1) — shared | — |
| Introduction to Data Literacy | ✅ (3) | — | ✅ (2) — shared |
| Data Storytelling Concepts | ✅ (7) | ✅ (2) — shared | — |

---

**Preference:** When referencing a lesson in conversation, always state the full lesson title.

---

**Agent behaviour preference — commit prompts**

- Spock will not ask for a commit after every lesson. Commits for DataCamp notebook work follow the established commit-boundary rule: one chapter = one natural commit boundary. Spock will only prompt for a commit when a full chapter is complete (or when you explicitly request it).
- Spock will continue to announce actions and wait for your explicit confirmation before making any file edits or running terminal commands that modify the workspace. This preference only suppresses repetitive "commit now?" prompts after individual lessons.
