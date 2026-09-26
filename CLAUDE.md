# CLAUDE.md

Guidance for Claude Code when working in this repository.

## Project

`lane-task-manager` is a Python library (import name `lane_task_manager`), using a `src/` layout.

```
src/lane_task_manager/   library source
tests/                   pytest test suite
docs/                    documentation
docs/ai-log/             log of significant AI instructions and outcomes
.github/workflows/       CI (lint + tests)
```

## Setup

Requires Python 3.10+.

```sh
python -m venv .venv
# Windows: .venv\Scripts\activate    macOS/Linux: source .venv/bin/activate
pip install -e ".[dev]"
```

## Commands

```sh
pytest                    # run tests
ruff check .              # lint
ruff check . --fix        # lint and auto-fix
ruff format .             # format
```

Run `ruff check .`, `ruff format --check .` and `pytest` before committing; CI runs the same checks.

## Conventions

- Follow PEP 8; ruff config lives in `pyproject.toml` (line length 100).
- Add type hints to public functions and classes; write docstrings for the public API.
- Keep the public API explicit via `src/lane_task_manager/__init__.py`.
- Every behaviour change comes with tests in `tests/`, named `test_<module>.py`.
- Prefer the standard library; add runtime dependencies to `pyproject.toml` only when justified.
- Work on a feature branch and open a PR against `main`; don't commit directly to `main`.

## AI log

After completing a significant piece of work driven by an AI instruction, add an entry to
`docs/ai-log/` following the format in `docs/ai-log/README.md`: the instruction (verbatim)
and a short summary of the response and outcome.
