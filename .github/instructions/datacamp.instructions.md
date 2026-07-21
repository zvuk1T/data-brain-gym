---
applyTo: "datacamp/**"
---

# DataCamp Learning Playbook

This file applies the Data–Spock learning method to DataCamp work. It is an operational playbook,
not a second methodology. Repository-wide boundaries come from [`AGENTS.md`](../../AGENTS.md).

## The two-layer model

DataCamp and the repository have different jobs.

| DataCamp owns | The companion course owns |
|---|---|
| Syllabus, lesson inventory, completion, and XP | Data's mental model and durable understanding |
| Full videos, transcripts, and exercise history | Direct links and essential source-faithful notes |
| Platform grading and feedback | Reasoning, misconceptions, corrected models, and transfer |
| Current platform position | Retrieval prompts and chapter synthesis |

A course `.md` or `.ipynb` is a personalized **companion course**. It is not a transcript archive,
a progress dashboard, or a second copy of DataCamp.

## Artifact choice

- Use `.md` for theory, conceptual reasoning, and courses without executable work.
- Use `.ipynb` when SQL, Python, outputs, or an executable walkthrough are central.
- Prefer one artifact per course unless a real chapter, topic, or technical boundary makes splitting
  clearer.

## Source fidelity

Use the best verified source available: the signed-in DataCamp page, visible transcript, platform
feedback, user-provided text, or screenshots. Never reconstruct unseen content from a title or from
general knowledge.

Keep these voices distinct:

- **DataCamp source** — direct link, exact short prompt, option, or faithful note;
- **Data's reasoning** — the learner's attempt and explanation;
- **Spock synthesis** — diagnosis, principle, connection, or transfer.

For every documented graded exercise, preserve the exact question and all answer options so the
reasoning remains auditable. Record concise, source-faithful video notes rather than complete
transcripts.

## Course opening

A new companion course should begin with only the orientation needed to navigate and learn:

- exact course title and instructor;
- official course link;
- short official course description (verbatim when concise, otherwise a faithful paraphrase);
- the capability the course is meant to build;
- a chapter-level map of the course;
- one Mermaid mental map when relationships are easier to remember visually.

Do not copy learner counts, XP totals, progress tables, or a complete lesson inventory.

## Two working modes

### Morning Gym

Use for a short, bounded session:

1. retrieve one earlier idea without notes;
2. complete one lesson or one meaningful exercise;
3. let Data attempt first when reasoning is being tested;
4. diagnose the reasoning and correct the model;
5. record only the durable source note, insight, trap, and retrieval cue.

A session does not need to produce a large document change to count as learning.

### Deep Dive

Use when a concept remains confusing, evidence conflicts, or several ideas must be synthesized.
Bound the dive to one question and end with a tested explanation, transfer example, conclusion, or
clearly named blocker.

A Morning Gym session may identify a Deep Dive candidate without expanding immediately.

## Lesson patterns

These are defaults, not mandatory forms. Omit a block that adds no learning value.

### Video or concept lesson

```markdown
#### Chapter X — Lesson N: Exact title

> 🎬 [Watch on DataCamp](official lesson URL) *(login required)*

**Essential DataCamp notes**
- Concise, source-faithful ideas needed to reconstruct the lesson.

**Data's understanding**
A short explanation in Data's own words, including the business ↔ technical connection when real.

**Retrieval**
> One question that requires reconstruction rather than recognition.
```

### Exercise or practice

Data answers and clicks first unless he explicitly asks Spock to do it.

```markdown
#### Chapter X — Lesson N: Exact title

> [Open the exercise on DataCamp](official exercise URL) *(login required)*

**Original question**
Exact question and answer options when wording matters.

| Option | Data's choice | Verdict | Why |
|---|---:|---:|---|
| ... | ✓ / — | ✅ / ❌ | Reasoning and, where useful, the trap |

**Reasoning diagnosis**
What Data's choice reveals; what was right, missing, or confused.

**Corrected model**
The shortest reusable principle that resolves the misconception.

**Retrieval**
> One fresh question or prediction.
```

Record all answer options so the distinction between correct, plausible, and wrong reasoning stays
visible. Keep long scenario text concise unless its wording changes the answer.

## Chapter close

Close a chapter after its relevant practice, not in advance. Keep it compact:

1. reconstruct the chapter's mental map;
2. answer two or three retrieval questions without notes;
3. solve one unfamiliar transfer case;
4. explain the central idea once for a business audience and once for a technical audience;
5. interleave at least one earlier concept.

This is the chapter's evidence of learning. A completion badge or XP total is not.

## Visuals and dual coding

Keep mental maps. Choose the visual from the relationship:

- Mermaid mind map for hierarchy and associations;
- flowchart for sequence, choices, and causal flow;
- table for exact comparison;
- timeline for change over time;
- graph for quantitative relationships;
- prose when the logic is linear.

A visual belongs only when it helps Data explain or reconstruct the idea. Decorative graphics do
not count as dual coding.

## Keep the companion course lean

Usually keep:

- official links and essential source notes;
- Data's own explanation;
- reusable misconceptions and traps;
- retrieval prompts;
- chapter mental maps and transfer evidence.

Usually omit:

- progress and XP tables;
- copied full transcripts or duplicated outlines;
- recruiter scripts for every lesson;
- repeated goals, recaps, and connection blocks;
- dated review queues;
- session trivia and mechanical status logs.

DataCamp remains authoritative for course progress. The repository remains authoritative for what
was understood and how that understanding can be used.

## Continuity and verification

At the start of a new task:

1. read root `AGENTS.md`, this playbook, and the active course artifact;
2. use DataCamp to verify the current platform position when needed;
3. never infer missing lesson content;
4. consult a captain's log only when it contains a relevant unresolved decision that the artifacts
   do not reveal.

Before editing a companion-course artifact or running a state-changing command, follow the control
and approval protocol in root `AGENTS.md`. Show the exact lesson or section, files, commands, and
verification plan, then stop for Data's explicit approval. Data answering or clicking an exercise
does not by itself authorize a repository edit.

After an approved edit, verify the changed section, source link, Markdown structure, and any Mermaid
or executable content. Stop again if the approved packet must expand. Approval to edit does not
include staging, commit, or push; each later stage requires its own explicit approval.
