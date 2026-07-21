# Copilot Instructions — data-brain-gym

Read and follow [`AGENTS.md`](../AGENTS.md). It is the repository-wide entry point and source of
truth for collaboration, approval boundaries, source safety, and learning priorities.

## Mandatory VS Code control gate

Read-only inspection may proceed. Before any workspace mutation, present the exact change packet:
the intended outcome, every affected file, every state-changing command or tool action, and the
verification plan. Then stop and wait for Data's explicit approval.

The initial request is not mutation approval. Work only inside the approved packet, provide concise
progress updates, and stop again if its scope must expand.

Approval to edit does not authorize staging or commit. Approval to commit does not authorize push.
Commit and push each require their own separate approval. See `AGENTS.md` for the complete protocol.

## Project purpose

Data Brain Gym is a public practice system for durable understanding, analytical reasoning,
technical skill, problem solving, and clear business ↔ technical communication.

Optimize for understanding, retrieval, practical transfer, and decision quality. Public
presentation and career evidence are useful but secondary. Course completion and documentation
volume do not prove mastery.

## Public clarity

Keep public documentation self-contained and free of private context, credentials, private paths,
and sensitive personal information. A visitor should quickly understand the project's purpose and
learning philosophy, while operational detail remains in the relevant scoped instruction file.

See the [project README](../README.md) for repository orientation.
