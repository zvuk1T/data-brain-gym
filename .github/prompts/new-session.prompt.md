---
mode: 'agent'
description: "Restore the current learning context from public repository instructions and verified artifacts."
---

# New Session Bootstrap

Restore enough context to continue safely and efficiently. Do not depend on a private repository,
user-level instruction path, or remembered chat history.

## 1. Load the applicable rules

Read completely, in this order:

1. `AGENTS.md`;
2. `.github/copilot-instructions.md`;
3. every matching scoped file in `.github/instructions/`;
4. the relevant public README.

For work under `datacamp/**`, always read
`.github/instructions/datacamp.instructions.md` and `datacamp/README.md`.

## 2. Identify the active work

Use the current user request first. Then inspect the relevant course artifact, repository status,
and recent history as needed.

A captain's log is optional recovery evidence. Read it only when it is relevant and does not
duplicate a clearer current artifact.

For DataCamp work:

- treat DataCamp as authoritative for current platform position and progress;
- treat the companion course as authoritative for recorded understanding;
- never infer unseen lesson content from a title;
- support both theory `.md` files and executable `.ipynb` files.

## 3. Verify the stopping point

Read enough of the active artifact to identify:

- the course or project;
- the last durable learning unit recorded;
- the next likely unit;
- unresolved misconceptions, decisions, or blockers;
- whether the source and artifact disagree.

For notebooks, inspect cells and executable state with the available notebook tools. For Markdown,
inspect headings, links, the last completed lesson section, and chapter synthesis.

## 4. Report the restored state

Use this compact structure:

**📍 Where we are:** current project, course, chapter, or task  
**✅ Last durable unit:** last verified lesson, exercise, or decision  
**🔜 Next step:** exact next bounded action  
**📚 Context loaded:** rules and artifacts actually read  
**⚠️ Open questions or discrepancies:** “None” when there are none

## 5. Propose the next action, then stop

Session restoration is read-only. Do not create, modify, rename, or delete files, run
state-changing commands, stage changes, commit, or push during the bootstrap.

If the user has requested work, follow the restored-state report with a proposed change packet:

- exact intended outcome;
- exact files affected;
- exact commands or tool actions that can change state;
- planned verification; and
- whether later commit or push stages are expected.

Then stop and wait for explicit approval. Do not perform the proposal and the mutation in the same
response. The initial request itself is not approval for mutation.

After approval, remain inside the approved packet and provide concise progress updates. Stop again
before any scope expansion. Staging, commit, and push require separate explicit approvals under
`AGENTS.md`.
