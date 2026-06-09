# Captain's Log — Stardate 20260609
**Date:** 9 June 2026
**Project:** data-brain-gym
**Session:** Data Literacy Professional — Course 1, Chapter 1 complete + Chapter 2 complete + templates refined

---

## 🎯 SESSION GOAL

Begin populating the `data-literacy-professional.ipynb` notebook with synthesised lesson content for Course 1: Introduction to Data.
Establish the lesson template that will be used for all future DataCamp theory notebooks.

---

## ✅ WHAT WE ACCOMPLISHED TODAY

### Part 1 — Session recovery
The previous chat session (same date, earlier) crashed with a `413 Request Entity Too Large` error — the context window was exhausted.
Data exported the full chat as a JSON file. Spock parsed it using Python (`tail` + `json.load`) to extract all 43 exchanges, identify where the session broke, and resume without losing any progress.

**Recovery method logged here as a repeatable pattern:**
```
# Extract last N characters to find where the chat ended
tail -c 5000 chat-export.json

# Parse all user messages + Spock responses for full session audit
python3 -c "
import json
with open('chat-export.json') as f:
    data = json.load(f)
for i, req in enumerate(data['requests']):
    print(f'[{i}]', req['message']['text'][:200])
"
```

---

### Part 2 — Core philosophy established

This session defined the guiding principle for all DataCamp notebook work:

> *"DataCamp provides the exercise. We provide what DataCamp cannot: your own reason why you know this."*

DataCamp is the base document. We add the retrieval + synthesis layer on top.
Every lesson asks a technical question. Our job is to answer the deeper set:
- Why does this concept exist?
- Who uses it in a real organisation?
- What decision does understanding it enable?

This sentence was also added to `datacamp/README.md`.

---

### Part 3 — Lesson template established

Through building L1–L6 organically from video transcripts and screenshots, we arrived at a stable template.

**Video lesson template:**
```
#### Chapter X — Lesson N: [Title] *(Video / XP)*

> 🎬 [Watch on DataCamp](URL) *(requires login)*

---

**🎯 GOAL — What is this lesson about?**
[1–2 sentence synthesis]

---

**📋 Key concepts covered:**
[numbered list with explanations]

[ASCII mental map — if the concept has a structure worth mapping]

---

**💡 Why this matters**
[business context, 1 paragraph]

**✅ RECAP**
[3–5 bullet points: key concept, common mistake, question to ask]
```

**Exercise / Practice template:**
```
#### Chapter X — Lesson N: [Title] *(Exercise or Practice / XP)*

> 🎬 [Watch on DataCamp](URL) *(requires login)*

---

**📋 Scenario**
[DataCamp scenario text]

**Task:** [What DataCamp asks]

---

**✅ Solution**
[Table: Item | Classification | Why]

---

**🧠 Mental Map** ← only when concept has a tree/hierarchy structure

[ASCII tree]

---

**💡 Why this matters**
[1 paragraph — business relevance]

**✅ RECAP**
[3–5 bullet points]
```

---

### Part 4 — ASCII mental map rule

**Rule:** Mental map only when there is a structure worth mapping.

| Use ASCII map | Skip ASCII map |
|--------------|----------------|
| Hierarchy or tree (Data Context, storage evolution) | Single question with one correct answer |
| Classification into categories (structured/unstructured, quant/qual) | Linear concept with no branches |
| Multi-level relationships between concepts | When the table already captures everything |

**Format rule:** ASCII in notebooks (renders everywhere, no dependencies). Mermaid in `.md` guide files only.

---

### Part 5 — Lessons completed: Course 1, Chapter 1 (ALL 10 ✅)

| # | Lesson | Type | XP | Status |
|---|--------|------|----|--------|
| 1 | Data basics | 🎬 Video | 50 | ✅ Done |
| 2 | Structured vs. unstructured | 📝 Exercise | 100 | ✅ Done |
| 3 | Quantitative vs. qualitative | 📝 Exercise | 100 | ✅ Done |
| 4 | Data context | 🔘 Practice | 50 | ✅ Done |
| 5 | The curious case of data growth | 🎬 Video | 50 | ✅ Done |
| 6 | Data storage capabilities | 📝 Exercise | 100 | ✅ Done |
| 7 | Making the right decisions | 🔘 Practice | 50 | ✅ Done |
| 8 | The value of data | 🎬 Video | 50 | ✅ Done |
| 9 | Data-driven vs. gut feelings | 📝 Exercise | 100 | ✅ Done |
| 10 | Data-driven decision making | 📝 Exercise | 50 | ✅ Done |

Chapter 1 complete. Session recovered after the 413 error — L7 screenshots were resent, L7–L10 added in the second chat session.

---

### Part 6 — Chapter 2 complete: all 9 lessons

| # | Lesson | Type | XP | Status |
|---|--------|------|----|--------|
| 1 | Data wisdom | 🎬 Video | 50 | ✅ Done |
| 2 | Managing mental models | 🔘 Practice | 50 | ✅ Done |
| 3 | DIKW steps | 📝 Exercise | 100 | ✅ Done |
| 4 | Data in decision making | 🎬 Video | 50 | ✅ Done |
| 5 | The right decision | 📝 Exercise | 100 | ✅ Done |
| 6 | Being data-driven | 🔘 Practice | 50 | ✅ Done |
| 7 | Data as a resource | 🎬 Video | 50 | ✅ Done |
| 8 | Aggregating information | 🔘 Practice | 50 | ✅ Done |
| 9 | Data management | 📝 Exercise | 100 | ✅ Done |

---

### Part 7 — Video lesson template refined

Through building Chapter 2 L1, we identified a structural redundancy in the previous video lesson template: the numbered prose list and the ASCII map said the same thing twice.

**Old pattern:** GOAL → numbered prose list → ASCII map → Why this matters → RECAP

**New pattern:** GOAL → ASCII map as primary explanation → `>` callouts for annotations the map can't show → Why this matters → RECAP

**Rule:** The map is the explanation. Prose only for what the map cannot show (e.g. the unconscious bias trap, a definition that needs a sentence).

Also fixed in this session: `🎬` video links were incorrectly present on all exercise and practice cells. Removed from all 8 non-video cells in the notebook. Template in `copilot-instructions.md` corrected — link line now only in the video lesson template.

---

## 🧠 DECISIONS AND REASONING

| Decision | Reason |
|----------|--------|
| ASCII in notebooks, Mermaid in `.md` files | Mermaid does not render natively in Jupyter markdown cells in VS Code without extensions |
| Mental map per structure, not per exercise | A mental map of a single yes/no question adds noise, not value |
| Theory before code — finish foundations first | Spock recommendation from previous session: foundations give WHY, practical tracks give HOW. Without foundations, every query is just syntax |
| `data-spock-core.instructions.md` — not updated today | All relevant global rules already present. DataCamp-specific template is a project-level concern, not a global rule |
| `data-brain-gym/copilot-instructions.md` — updated | Added `datacamp/` to Project Structure + DataCamp Notebook Standard section |
| Video lesson template refined — prose list removed | The ASCII map is the explanation. Numbered prose list was redundant. `>` callouts added for what the map cannot show. `copilot-instructions.md` updated to reflect new standard |

---

---

### Part 8 — Chapter 3 complete: all 12 lessons

| # | Lesson | Type | XP | Status |
|---|--------|------|----|--------|
| 1 | Data ethics and privacy | 🎬 Video | 50 | ✅ Done |
| 2 | Ethical decisions | 🔘 Practice | 50 | ✅ Done |
| 3 | Ethics and privacy | 📝 Exercise | 100 | ✅ Done |
| 4 | Privacy concerns | 📝 Exercise | 50 | ✅ Done |
| 5 | Data life cycle | 🎬 Video | 50 | ✅ Done |
| 6 | The data life cycle | 🔘 Practice | 50 | ✅ Done |
| 7 | Applying the data life cycle | 📝 Exercise | 50 | ✅ Done |
| 8 | Ordering the data life cycle | 📝 Exercise | 100 | ✅ Done |
| 9 | Common data mistakes | 🎬 Video | 50 | ✅ Done |
| 10 | Lack of explanation | 🔘 Practice | 50 | ✅ Done |
| 11 | Spot the mistakes | 📝 Exercise | 50 | ✅ Done |
| 12 | Wrap-up | 🎬 Video | 50 | ✅ Done |

**Course 1: Introduction to Data — fully complete.**

| Chapter | Lessons | XP |
|---------|---------|-----|
| Ch1 — Data Basics | 10 | 700 |
| Ch2 — Data Wisdom | 9 | 600 |
| Ch3 — Data In-depth | 12 | 700 |
| **Total** | **31** | **2000** |

---

### Part 9 — Methodological analysis: what we evolved vs. what is in core instructions

After completing Course 1, we conducted a review of our DataCamp notebook methodology against `data-spock-core.instructions.md`.

**What core instructions document:**
- 5-block Problem-Solving Standard: `GOAL → APPROACH → SOLUTION → WALKTHROUGH → RECAP`
- Learning Rules: WHY before HOW, mental model after every important step
- Mental map rule: ASCII in chat/notebooks, Mermaid in `.md` files

**What our DataCamp notebook template does (current state):**
- Video: `GOAL → ASCII map → callouts → Why this matters → RECAP`
- Exercise: `Scenario → Solution table → Why this matters → RECAP`

**Gaps and evolutions identified:**

| Pattern | Status | Notes |
|---------|--------|-------|
| `APPROACH` block | Missing from notebook template | Core instructions prescribes it; for theory notebooks it may not be needed, but the absence is intentional and should be documented |
| `WALKTHROUGH` block | Partially replaced by ASCII map | Map shows structure; walkthrough explains steps — not identical. For theory notebooks, the map is sufficient |
| "Map IS the explanation" | Our evolution | Core instructions says "mental map after every step" — we refined to "map as primary, prose only for what map cannot carry." Emerged organically through Ch2 L1 |
| `Why this matters` section | Our addition | Not in 5-block standard. Connects concept to business context. Present in every lesson |
| Callout (`>`) rule | Our addition | Not documented anywhere before today. Rule: `>` callouts only for annotations the map cannot carry — traps, definitions, caveats |
| "Practice → Pattern → Principle" | Our named meta-principle | Implicit in core instructions ("WHY before HOW") but not formulated this way. Emerged from reflecting on how the template itself was built |
| Deferred intro/recap | Decision made today | Do not write chapter intro before completing all lessons. Write it with full context in hand. Logical application of "WHY before HOW" to notebook structure itself |

**Action taken:** `data-brain-gym/.github/copilot-instructions.md` and `data-spock-core.instructions.md` updated to document these evolutions.

---

## 🧠 DECISIONS AND REASONING

| Decision | Reason |
|----------|--------|
| ASCII in notebooks, Mermaid in `.md` files | Mermaid does not render natively in Jupyter markdown cells in VS Code without extensions |
| Mental map per structure, not per exercise | A mental map of a single yes/no question adds noise, not value |
| Theory before code — finish foundations first | Spock recommendation from previous session: foundations give WHY, practical tracks give HOW. Without foundations, every query is just syntax |
| `data-spock-core.instructions.md` — updated today | Added "Practice → Pattern → Principle" meta-principle + callout rule + map-as-primary evolution |
| `data-brain-gym/copilot-instructions.md` — updated today | Callout rule formalised, `Why this matters` added to template, deferred intro/recap principle added |
| Video lesson template refined — prose list removed | The ASCII map is the explanation. Numbered prose list was redundant. `>` callouts added for what the map cannot show |
| Chapter intro/recap deferred | Do not write chapter intro before completing all lessons. Full context = better synthesis |
| Course 1 fully complete before writing chapter intros | Same principle: practice → pattern → principle. Write the intro when you know what was in the chapter |

---

## ⚠️ WHERE WE STOPPED

**Course 1: Introduction to Data — fully complete. All 31 lessons, 2000 XP.**
Methodology documented. Documentation files updated.
Next: chapter intro cells (Ch1, Ch2, Ch3) + chapter recap cells, now that full context is available.

---

## 🔜 NEXT STEPS

1. ✅ Captain's log created and updated
2. ✅ `data-brain-gym/.github/copilot-instructions.md` updated
3. ✅ Chapter 1 — all 10 lessons complete
4. ✅ Chapter 2 — all 9 lessons complete
5. ✅ Chapter 3 — all 12 lessons complete
6. ✅ Course 1 — fully complete (31 lessons, 2000 XP)
7. ✅ Video lesson template refined — map is primary, callout rule formalised
8. ✅ Methodological analysis — evolutions documented in core instructions + project instructions
9. ⏳ Chapter intro cells — Ch1, Ch2, Ch3 (write with full context)
10. ⏳ Chapter recap cells — Ch1, Ch2, Ch3 (synthesis, not list)
11. ⏳ Course 1 intro cell (optional — after all chapter intros done)
12. ⏳ Commit all changes

---

## ✅ Notes for Students

**On chat context limits:** Language model context windows have a hard size limit. Long sessions with large files (notebooks, JSONs, screenshots) fill the context faster than text-only sessions. When a session breaks with a `413` error, the work is not lost — VS Code exports the full chat history as JSON. Python can parse it in seconds.

**On the lesson template:** The template was not designed upfront — it emerged from doing the work. L1, L2, L3 were built first, patterns became visible, the rule was named after the pattern existed. This is the correct order: practice → pattern → principle. Trying to define the perfect template before writing a single lesson is a form of procrastination dressed as planning.

**On ASCII mental maps:** The goal of a mental map is to let you close your eyes and see the structure. If you can already see it from the table, the map adds nothing. Add it when the structure itself is the lesson.

**On methodology documentation:** Every time you identify a pattern you have been using implicitly, name it and write it down. Unnamed patterns disappear. Named patterns compound. The "Practice → Pattern → Principle" rule, the callout rule, the deferred intro decision — none of these were designed in advance. They were discovered, named, and documented. That is the correct order.
