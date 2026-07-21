---
mode: 'agent'
description: "Update the captain's log for today before committing."
---

First inspect `captains-log/` read-only for today's date.

- If today's file exists, identify the exact file and sections that would be updated.
- If it does not exist, identify the exact filename and say that it would be created from the
  standard template.
- Never propose an A/B/C or suffixed variant. One calendar day has one log file.

Prepare a concise change packet for:

1. **WHAT WE ACCOMPLISHED TODAY** — the durable work from this session;
2. **WHERE WE STOPPED** — the verified stopping point; and
3. **NEXT STEP** — one concrete next action.

Show the exact target file, summarize the intended additions or replacements, and stop for Data's
explicit approval before creating or editing the log. Do not update the file in the same response
as the proposal.

After an approved update, show the diff and verification, then stop. Log-edit approval does not
authorize staging or commit. Before committing, show repository status, diff summary, and proposed
commit message and wait for separate approval. Push requires another separate approval.
