```markdown
# sglang Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance for contributing to the `sglang` repository, a Python-based project focused on machine learning model pipelines and documentation. It covers code conventions, structured workflows for updating documentation and model pipelines, and best practices for maintaining code quality and consistency.

## Coding Conventions

- **File Naming:**  
  Use `snake_case` for Python files and directories.  
  *Example:*  
  ```
  python/sglang/multimodal_gen/runtime/pipelines/sample_pipeline.py
  ```

- **Import Style:**  
  Use relative imports within the package.  
  *Example:*  
  ```python
  from .utils import load_config
  from ..core import ModelRegistry
  ```

- **Export Style:**  
  Use named exports (explicitly define what is exported from a module).  
  *Example:*  
  ```python
  __all__ = ["DiffusionPipeline", "load_config"]
  ```

- **Commit Patterns:**  
  - Freeform messages, sometimes prefixed with tags like `[diffusion]`, `[AMD]`, `[codex]`, `[CI]`.
  - Keep commit messages concise and descriptive (average ~57 characters).

## Workflows

### update-cookbook-documentation-and-snippets
**Trigger:** When adding or revising cookbook documentation for a model, including deployment snippets.  
**Command:** `/update-cookbook-docs`

1. Edit or add a `.mdx` file under `docs_new/cookbook/autoregressive/<Model>/`.
2. Update or add the corresponding code snippet in `docs_new/src/snippets/autoregressive/<model>-deployment.jsx`.
3. Optionally, update `docs_new/docs.json` to register the new documentation.

*Example:*
```bash
# Edit documentation
vim docs_new/cookbook/autoregressive/llama2/usage.mdx

# Update deployment snippet
vim docs_new/src/snippets/autoregressive/llama2-deployment.jsx

# Register in docs.json (optional)
vim docs_new/docs.json
```

---

### add-or-update-diffusion-model-pipeline
**Trigger:** When adding support for a new diffusion model or updating an existing pipeline.  
**Command:** `/update-diffusion-pipeline`

1. Add or update config files in `python/sglang/multimodal_gen/configs/`.
2. Modify or add runtime pipeline files in `python/sglang/multimodal_gen/runtime/pipelines/` and `pipelines_core/stages/`.
3. Update `registry.py` and `server_args.py` if needed.
4. Update or add related test cases in `python/sglang/multimodal_gen/test/server/` and performance baselines in `perf_baselines.json`.
5. Update documentation for the compatibility matrix in `docs/diffusion/compatibility_matrix.md` and/or `docs_new/docs/sglang-diffusion/compatibility_matrix.mdx`.

*Example:*
```bash
# Add new config
vim python/sglang/multimodal_gen/configs/new_model.yaml

# Implement runtime pipeline
vim python/sglang/multimodal_gen/runtime/pipelines/new_model.py

# Update registry
vim python/sglang/multimodal_gen/registry.py

# Add test case
vim python/sglang/multimodal_gen/test/server/test_new_model.py

# Update compatibility matrix
vim docs/diffusion/compatibility_matrix.md
```

---

### incremental-cookbook-docs-snippet-update
**Trigger:** When making small, repeated updates to an existing cookbook doc and/or snippet.  
**Command:** `/edit-cookbook-docs`

1. Edit the relevant `.mdx` file under `docs_new/cookbook/autoregressive/<Model>/`.
2. Edit the associated code snippet in `docs_new/src/snippets/autoregressive/<model>-deployment.jsx`.

*Example:*
```bash
vim docs_new/cookbook/autoregressive/llama2/usage.mdx
vim docs_new/src/snippets/autoregressive/llama2-deployment.jsx
```

## Testing Patterns

- **Testing Framework:**  
  Not explicitly detected; test files are mainly Python scripts.
- **Test File Pattern:**  
  Test files are located under `python/sglang/multimodal_gen/test/server/` and named with `.py` extension.
- **Performance Baselines:**  
  Performance metrics are tracked in `perf_baselines.json`.

*Example Test File:*
```python
# python/sglang/multimodal_gen/test/server/test_new_model.py
def test_new_model_inference():
    # Arrange
    from ...runtime.pipelines import NewModelPipeline
    # Act
    result = NewModelPipeline().run(input_data)
    # Assert
    assert result is not None
```

## Commands

| Command                  | Purpose                                                        |
|--------------------------|----------------------------------------------------------------|
| /update-cookbook-docs    | Add or update cookbook documentation and deployment snippets   |
| /update-diffusion-pipeline | Add or update a diffusion model pipeline and related files    |
| /edit-cookbook-docs      | Make incremental updates to existing cookbook docs/snippets    |
```