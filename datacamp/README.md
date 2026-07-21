# DataCamp — Companion Courses for Durable Learning

This folder contains the DataCamp work inside `data-brain-gym`. DataCamp supplies structured
lessons and practice; these artifacts turn that material into durable, transferable understanding.

## 🧭 The core idea

Course artifacts are **companion courses**, not copies and not progress dashboards.

DataCamp remains the source of truth for completion, XP, lesson inventory, and full course material.
The repository preserves what improves learning:

- essential source links and notes;
- Data's reasoning and corrected mental models;
- useful mistakes and recurring traps;
- mental maps and other purposeful visuals;
- retrieval prompts and evidence of transfer;
- translation between business questions and technical questions.

The learning spine is:

```text
Outcome → Evidence → Practice → Feedback → Retrieval → Transfer
```

Business context and storytelling are added when they clarify a real audience or decision, not as
mandatory ceremony in every lesson.

## 🗂️ Stable folder map

```text
datacamp/
├── true-story-data/
│   ├── data-literacy-professional/
│   ├── data-storytelling/
│   └── data-skills-for-business/
└── sql-for-business-analysts/
```

- **Data Literacy Professional** develops the ability to read, question, analyze, and communicate
  with data.
- **Data Storytelling** develops audience-aware explanation, narrative, and visual judgment.
- **Data Skills for Business** develops the governance, ethics, AI, and organizational context
  around data work.
- **SQL for Business Analysts** turns those foundations into executable analytical practice.

DataCamp is authoritative for the current catalog and course progress, so this README does not
duplicate changing course counts, XP totals, or completion tables.

## 📐 Foundations and practice

The current learning strategy builds enough theory to understand the question, then tests that
understanding through practice. Foundations should make later SQL and Python work meaningful rather
than mechanical.

This ordering is a deliberate strategy, not an untouchable rule. Change it when learning evidence
or an explicit decision shows that interleaving practical work would be better.

## 📝 How course work is documented

Theory courses normally use Markdown. SQL, Python, and other executable courses normally use
notebooks. Keep source material visibly separate from interpretation, and record only what improves
reasoning, retrieval, or transfer.

The detailed conventions live in:

- the repository [working agreement](../AGENTS.md);
- the [DataCamp learning playbook](../.github/instructions/datacamp.instructions.md).

A typical theory lesson keeps an official link, concise source-faithful notes, Data's explanation,
and one retrieval cue. An exercise additionally preserves the exact question and options when they
are needed to diagnose the reasoning.

At a chapter boundary, the companion course should add a compact mental map and a fresh transfer
case. It should not add another progress table.

## 🧠 What success looks like

Success means being able to:

1. reconstruct an idea without opening the notes;
2. explain why it works and distinguish it from a plausible alternative;
3. apply it to a meaningfully different case;
4. translate it accurately between business and technical language; and
5. use it to improve a question, decision, or data story.

Course completion, document length, and portfolio polish are secondary evidence—not mastery.

## ⚠️ Practical-course local setup

For executable work:

- data and recordings may remain gitignored when licensing or size requires it;
- use committed setup scripts or small reproducible samples where appropriate;
- document meaningful differences between the local environment and DataCamp;
- verify SQL, Python, outputs, and dependencies before treating an exercise as complete.

## 🔄 Session continuity

Start with root [`AGENTS.md`](../AGENTS.md), then read the
[DataCamp playbook](../.github/instructions/datacamp.instructions.md) and the active course
artifact. Use DataCamp to verify the current platform position. Never infer unseen lesson content
from a title.

A new task should be able to continue from these public files without access to private
repositories or machine-specific instructions.
