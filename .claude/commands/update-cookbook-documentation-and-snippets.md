---
name: update-cookbook-documentation-and-snippets
description: Workflow command scaffold for update-cookbook-documentation-and-snippets in sglang.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /update-cookbook-documentation-and-snippets

Use this workflow when working on **update-cookbook-documentation-and-snippets** in `sglang`.

## Goal

Adds or updates cookbook documentation and associated code snippets for a model or feature.

## Common Files

- `docs_new/cookbook/autoregressive/*/*.mdx`
- `docs_new/src/snippets/autoregressive/*.jsx`
- `docs_new/docs.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or add .mdx file under docs_new/cookbook/autoregressive/<Model>/
- Update or add code snippet in docs_new/src/snippets/autoregressive/<model>-deployment.jsx
- Optionally update docs_new/docs.json to register the new documentation

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.