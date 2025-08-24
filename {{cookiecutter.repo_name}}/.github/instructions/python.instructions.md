---
description: Python coding guidance tailored to this repo
applyTo: "*.py"
---
# Role

You assist with Python code in this repository, following `README.md` and `.github/copilot-instructions.md` for structure, tooling, and workflow.

# Repository Context

- Python 3.12; package root at `src/{{cookiecutter.repo_name}}`.
- Tooling: `uv` for env, `ruff` for lint, `pytest` (+cov), `pydoclint` for docstrings, `marimo` for interactive notebooks, `quartodoc` for API docs.

# Coding Standards

- Type hints: required for public APIs; prefer precise types over `Any`. Use `collections.abc` for callables/iterables; include return types.
  - Example:
    ```python
    def pairwise_dist(x: np.ndarray, y: np.ndarray) -> float: ...
    ```
- Docstrings: Google style (enforced by `pydoclint`). Include `Args`, `Returns`, and `Raises` when applicable. Keep summaries in imperative mood.
- Let `ruff` handle sorting (isort integration).
- Style: 4-space indentation; small, single‑purpose functions; avoid hidden side effects. Preserve existing patterns (e.g., `attrs` usage in `config.py`).

# Testing Policy

- Framework: `pytest`. Tests live in `tests/` and mirror `src/` structure. Name files `test_*.py`.
- Coverage: enabled by default via `pyproject.toml` (branch coverage on `src`).

# Marimo Guidance

- Keep interactive notebooks under `docs/notebooks/`.
- Launch editors with `uv run marimo edit <path>`; run with `uv run marimo run <path>`.

# Constraints

- Do not add dependencies or modify `uv.lock` without approval.
- Never commit secrets; use `.env` (gitignored).
- Keep diffs minimal; align with surrounding code and existing imports.

For concrete examples and prompts, see `.github/copilot-instructions.md`.\\\