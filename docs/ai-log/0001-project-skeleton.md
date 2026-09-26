# 0001 – Initialise the project skeleton

- **Date:** 2026-09-26
- **Assistant:** Claude Code (Claude Opus 5.5)
- **PR:** `chore/project-skeleton` → `main`

## Instruction

> Let's initialise this repository. It will be a python library. We'll want a gitignore, claude
> repo instructions file, source code, tests and documentation sections. In the docs section I'll
> want to keep a log of significant AI instructions and a summary of their response so you can use
> this prompt as the first entry there.
>
> You can prepare the project skeleton in a PR against main. gitignore, claude instructions can be
> basic, generic Python centric instructions.
> We'll want pytest and linting as a starting point. we may want github actions for CI

## Response summary

Created the project skeleton on branch `chore/project-skeleton`:

- **Packaging:** `pyproject.toml` (hatchling backend), package `lane-task-manager` / import name
  `lane_task_manager`, `src/` layout, Python 3.10+. Dev extras: `pytest`, `pytest-cov`, `ruff`.
- **Source:** `src/lane_task_manager/__init__.py` with `__version__`.
- **Tests:** `tests/test_package.py` placeholder test; pytest configured in `pyproject.toml`.
- **Linting:** ruff for linting and formatting (rules E, W, F, I, B, UP, SIM; line length 100).
- **CI:** `.github/workflows/ci.yml` runs ruff lint/format checks and pytest on Python 3.10–3.14
  for pushes to `main` and all PRs.
- **Repo files:** Python-centric `.gitignore`, `CLAUDE.md` with setup, commands and conventions
  (including keeping this log up to date), `Readme.md` renamed to `README.md` and expanded.
- **Docs:** `docs/README.md` index and `docs/ai-log/` with a format guide and this first entry.

Notes: the machine's default `python` was 3.6; after the user upgraded to Python 3.14.7, the local
`.venv` was rebuilt on 3.14 and lint and tests re-verified, and 3.14 was added to the CI matrix.
The GitHub CLI isn't installed, so the branch was pushed and the PR opened via GitHub's web UI.
