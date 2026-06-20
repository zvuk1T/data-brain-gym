# 🤖🖖 Data–Spock Learning Methodology
### Version 2 · 20 June 2026

> **What this is:** How Data (Žarko Vuković) and Spock actually learn together — distilled
> from one year of real practice, not designed in advance.
>
> **Who it is for:** Data first. Any future collaborator second. Any recruiter who wants to
> see *how* this person thinks about learning, third.
>
> **Supersedes:** the July 2025 methodology (`data-spock-learning-methodology.md`, archived in
> `invoice-automation/old_friends_folder/`). That version was tied to a dead context (a
> Terraform internship mission) and grew to 633 lines of ceremony. This version keeps only
> what survived contact with real work.

---

## 1. Why a version 2 exists

The first methodology was written **before** the work, for a project that no longer exists.
It described badges, "mastery" levels, and a Hall of Fame — motivational scenery, not a
learning process. It was 633 lines long, which is the clearest sign it was never used: a
method you cannot read in five minutes will not guide a single session.

This version is the opposite. Every principle below was **observed in practice first**, then
named. If a rule is here, it earned its place by being used — usually after a mistake made it
necessary.

> **Design rule for this document:** if it does not fit on a few screens, it is too long.
> Lean is a feature, not a limitation.

---

## 2. One year of evolution

| Dimension | July 2025 (v1) | June 2026 (v2) |
|---|---|---|
| Origin | Designed up front, before work | Distilled from work already done |
| Length | 633 lines of ceremony | A few screens, used daily |
| Structure | Mission badges, mastery levels | Principles + one learning loop |
| Content source | Plausible-sounding theory | Empirical — rules born from real mistakes |
| Context | Tied to one dead project | Project-independent, portable |
| Synthesis timing | Summary written first | Synthesis deferred until work is complete |

The shift in one sentence: **from ceremony designed in advance, to principles distilled from practice.**

---

## 3. Philosophy

The whole method rests on one value, and that value is not a slogan — it is a description of
how Data actually works best: **understanding before speed.**

Data's strongest professional pattern is *deep understanding* — observing a system, finding the
mechanism underneath, and turning that into a useful output. Depth gives energy; mechanical
throughput drains it. The methodology is simply that identity turned into a process. We learn
slowly and completely on purpose, because a thing understood once does not need to be relearned
ten times.

> **→** The goal is never to finish the lesson. The goal is to understand the system the lesson
> is a window into.

---

## 4. Core principles

Eleven principles, each one line, each already in use across `data-brain-gym` and the
`invoice-automation` project.

| # | Principle | Why it exists |
|---|---|---|
| 1 | **Understanding before operating** — theory before code; WHY before HOW | Running SQL without knowing the question is technician work, not analyst work |
| 2 | **Source-grounded** — build only from a real source (screenshot, file), never from a title | Content invented from a lesson title sounds right and is unverifiable |
| 3 | **Practice → Pattern → Principle** — do the work, see the pattern, then name the rule | Defining the rule before the practice is procrastination dressed as planning |
| 4 | **Deferred synthesis** — write intros, recaps, summaries only after the work is done | A recap written early is a guess; written late it is a synthesis |
| 5 | **The 5-block standard** — GOAL → APPROACH → SOLUTION → WALKTHROUGH → RECAP | Makes every artifact a self-contained mini-lesson, readable with no external resource |
| 6 | **Map-as-primary** — the map *is* the explanation (ASCII in chat, Mermaid in files) | A structure seen is remembered; prose alone is forgotten |
| 7 | **Context hygiene** — one thing per message; small steps; prevent overload | Protects depth and avoids context-window crashes (the 413 lesson) |
| 8 | **Verify, don't assume** — *"Vertrauen ist gut, Kontrolle ist besser"* | Checking is engineering discipline, not distrust |
| 9 | **Document as a first-class output** — logs, guides, Notes for Students | What is not written down did not happen; the log is itself a learning resource |
| 10 | **Career-anchored** — every exercise answers: what question, who asks, what decision | Turns a query into an insight and a portfolio into a narrative |
| 11 | **Two voices** — Spock (logic) and Troi (psychology) are both always present | Skill grows with logic; it sticks when the emotional pattern is understood too |

---

## 5. The learning loop

There are two loops, nested. The outer one builds the method; the inner one builds each artifact.

**Outer loop — how the method itself grows (meta):**

```
Do real work  →  Notice a repeated pattern  →  Name it as one principle  →  Add to the method
```

This is principle #3 applied to the methodology itself. The "Mistakes to Never Repeat" table in
`datacamp.instructions.md` is this loop made visible: every row is a rule that a real mistake
forced into existence.

**Inner loop — how each lesson or exercise is built (the 5-block standard):**

```
🎯 GOAL        →  what are we solving, and why does it matter?
🔧 APPROACH    →  what pattern or technique will we use?
💡 SOLUTION    →  the actual code, query, or answer
🔍 WALKTHROUGH →  every step explained — WHY it exists, not just what it does
✅ RECAP       →  key concept · most common mistake · what to remember next time
```

Every notebook cell, SQL script, and guide in the system follows the inner loop. The method
itself is built by the outer loop. Same shape at both scales: do first, name after.

---

## 6. The three voices

Learning here is never a solo monologue. Three roles are always in the room:

```
Data   →  the student and owner — asks, decides, documents, owns the workspace
Spock  →  logic and structure — explains WHY, verifies, gives honest critical assessment
Troi   →  the psychology layer — notices the pattern beneath the question
```

- **Spock** never flatters. Honest critique is a feature: a flawed idea is named directly, with
  the reason. Disagreement, when technically justified, is part of the job.
- **Troi** asks the question beneath the question. Example: noticing when "let's design a course"
  is really avoidance of a harder, messier task. The method is meant to keep the work honest,
  not just correct.
- **Data** holds final authority. Nothing is created, moved, or committed without explicit
  confirmation. The student controls the pace; understanding sets the speed, not the clock.

---

## 7. How a learning session runs

The rhythm is deliberately small and repetitive. It is the same whether the work is a DataCamp
notebook, a SQL drill, or a client project.

```
1. Orient   →  read the latest captain's log + the active file; state where we are
2. Announce →  one next step, described in one message — then STOP
3. Confirm  →  Data approves ("ok") before anything is created or run
4. Do       →  one thing — one cell, one command, one file
5. Verify   →  check the result; never assume it worked
6. Document →  update the captain's log; add Notes for Students when something was learned
7. Commit   →  one logical unit, descriptive message, log committed with the code
```

> **The boundary rule:** one chapter / one logical unit = one natural commit boundary = one
> chat session. When context starts to fill (responses shorten, old facts are forgotten),
> close cleanly: finish the current unit, commit, update the log, then open a fresh session.

---

## 8. For a future collaborator

If you are joining Data on a project and using this method for the first time, here is the
whole thing in five sentences:

1. **Read before you act** — the captain's log and the relevant files, completely, before doing anything.
2. **One step at a time** — announce it, wait for an explicit "ok", then do exactly one thing.
3. **Explain WHY before HOW** — and build only from a real source, never from a guess.
4. **Write it down** — the log and the guides are part of the work, not an afterthought.
5. **Do the work before you name the rule** — patterns earn their way into the method; they are not declared up front.

If you internalize those five, the rest of this document is just the detail.

---

## 9. What we rejected — and why

A method is defined as much by what it refuses as by what it does. These anti-patterns were
tried and discarded:

| Rejected | Why we dropped it |
|---|---|
| **Ceremony** (badges, mastery levels, Hall of Fame) | Motivational scenery does not deepen understanding — it inflates the document |
| **Premature synthesis** (intros/recaps written first) | A summary written before the work is a guess that later proves wrong |
| **Ungrounded content** (building from a title or memory) | It sounds plausible and is unverifiable — the worst combination |
| **One giant file** (a single notebook or doc for everything) | Context runs out before the work is done; recovery becomes impossible |
| **Scope creep** (learning + work + infra in one document) | A document that covers everything is used for nothing; this file covers learning only |
| **Speed over depth** | It contradicts the one value the whole method rests on |

---

> *"The more you learn, the more you understand. The more you understand, the less you fear."*
> — Science Officer Spock

*Methodology v2 · distilled by Spock · owned by Lieutenant Commander Data (zvuk1T) · 20 June 2026*
*Next revision: when practice reveals the next principle — not before.*
