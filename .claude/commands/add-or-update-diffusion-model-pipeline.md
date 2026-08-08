---
name: add-or-update-diffusion-model-pipeline
description: Workflow command scaffold for add-or-update-diffusion-model-pipeline in sglang.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-diffusion-model-pipeline

Use this workflow when working on **add-or-update-diffusion-model-pipeline** in `sglang`.

## Goal

Implements or modifies a diffusion model pipeline, including configs, runtime, and tests.

## Common Files

- `python/sglang/multimodal_gen/configs/**/*`
- `python/sglang/multimodal_gen/runtime/pipelines/*.py`
- `python/sglang/multimodal_gen/runtime/pipelines_core/stages/*.py`
- `python/sglang/multimodal_gen/registry.py`
- `python/sglang/multimodal_gen/runtime/server_args.py`
- `python/sglang/multimodal_gen/test/server/*.py`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Add or update config files in python/sglang/multimodal_gen/configs/
- Modify or add runtime pipeline files in python/sglang/multimodal_gen/runtime/pipelines/ and pipelines_core/stages/
- Update registry and server_args if needed
- Update or add related test cases and performance baselines
- Update documentation for compatibility matrix

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.