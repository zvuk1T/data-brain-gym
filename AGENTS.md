# Agent Guide — Data Brain Gym

## Purpose

Data Brain Gym is a public learning repository for durable understanding, analytical thinking,
SQL, Python, problem solving, and clear business ↔ technical communication.

AI supports the learner's reasoning. It does not replace the learner's first attempt.

## Instruction order

Follow, from highest to lowest priority:

1. the current user's request;
2. this repository-wide guide;
3. the most specific matching file in `.github/instructions/`;
4. public READMEs and older project notes.

If two written rules conflict, use the higher-priority and more specific current rule. Never depend
on a private repository or machine-specific file to understand this public repository.

## Learning partnership

- Data may attempt first when independent reasoning is the goal; when Data asks for a verified
  answer, provide it directly.
- Do not use question-by-question Socratic dialogue in Morning Gym or other short course sessions.
- Explain directly when a prerequisite fact is missing or Data asks for the answer.
- Diagnose why an answer was chosen, including what was partly right.
- Turn useful mistakes into reusable principles; do not preserve unimportant interaction history.
- Optimize for reconstruction, explanation, transfer, and decision quality—not note volume.
- Career and portfolio value are useful secondary evidence, not the learning objective.

## Artifact and source boundaries

- Keep source material, Data's interpretation, and assistant synthesis visibly distinct.
- Use direct source links and verified source material. Never invent missing lesson content.
- Preserve exact exercise wording and options only when they matter to reasoning or verification.
- Do not reproduce complete copyrighted transcripts or duplicate a provider's progress dashboard.
- Keep this public repository free of secrets, credentials, private paths, private-repository content,
  and sensitive personal information.

## Working discipline

- Read the applicable instructions before changing a file.
- Inspect the current file and repository state; preserve unrelated work.
- Make the smallest coherent change that achieves the requested outcome.
- Verify links, structure, syntax, and changed content in proportion to risk.
- Do not create logs, trackers, templates, or duplicate artifacts unless they add durable value.
- Never treat file length, commit count, course completion, or polished formatting as proof of mastery.

## Control and approval protocol — mandatory for VS Code agents

Read-only inspection may proceed without prior approval. An initial task request authorizes
investigation and planning; it does not authorize workspace mutation.

Before creating, editing, renaming, or deleting a file; applying a code change; running a
state-changing terminal command; installing software; or making an external write, the agent must:

1. inspect the relevant state read-only;
2. explain the intended outcome;
3. list every file that will be created, changed, renamed, or deleted;
4. list the exact terminal commands or tool actions that can change state;
5. state how the result will be verified; and
6. stop and wait for Data's explicit approval.

The proposal and the mutation must not happen in the same response. A general request such as
“fix,” “change,” or “create” is not approval until the exact change packet has been shown.

Approval covers only the named change packet. While executing it, the agent must:

- stay inside the approved files, commands, and outcome;
- give concise progress updates during multi-step work;
- ask rather than guess when the intent, source, or desired result is unclear;
- stop and request new approval before adding a file, command, dependency, or broader objective; and
- report what changed and how it was verified.

### Commit and push gates

Approval to edit does not authorize staging or a commit.

Before committing, show the repository status, summarize the diff, provide the proposed commit
message, and stop for explicit approval.

Approval to commit does not authorize a push.

Before pushing, state the repository, branch, remote, and exact commit or commits to be pushed,
then stop for separate explicit approval.

Never use a tool that implicitly commits or publishes as a shortcut around these gates.

### Stewardship of existing work

Treat existing rules, prompts, workflows, source-of-truth files, and learner-authored content as
intentional until their purpose is understood.

Before deleting, weakening, renaming, replacing, or “modernizing” content not created during the
current approved task, the agent must:

1. inspect its history, references, and surrounding context;
2. explain its likely original purpose;
3. identify what behavior or protection could be lost;
4. present retain, revise, and remove options; and
5. stop for Data's explicit decision.

If the purpose remains uncertain, preserve the content and ask. “It looks outdated” is not
sufficient justification for changing it.

## Git

- Check status and recent history before local Git work.
- Do not discard or overwrite unrelated changes.
- Avoid destructive history operations.
- Use small, descriptive commits grouped by a real learning or documentation unit.
- Editing approval never implies `git add`, commit, push, or direct work on `main`.

## Scoped workflows

Work under `datacamp/**` also follows
[`.github/instructions/datacamp.instructions.md`](.github/instructions/datacamp.instructions.md).
