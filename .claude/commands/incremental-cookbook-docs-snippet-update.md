---
name: incremental-cookbook-docs-snippet-update
description: Workflow command scaffold for incremental-cookbook-docs-snippet-update in sglang.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /incremental-cookbook-docs-snippet-update

Use this workflow when working on **incremental-cookbook-docs-snippet-update** in `sglang`.

## Goal

Makes small, repeated updates to an existing cookbook documentation and its associated code snippet.

## Common Files

- `docs_new/cookbook/autoregressive/*/*.mdx`
- `docs_new/src/snippets/autoregressive/*.jsx`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit .mdx file under docs_new/cookbook/autoregressive/<Model>/
- Edit code snippet in docs_new/src/snippets/autoregressive/<model>-deployment.jsx

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.