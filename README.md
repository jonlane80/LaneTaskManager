# Lane Task Manager

The start of a repo for the multiverse interview test.

## Development

Requires Python 3.10+.

```sh
python -m venv .venv
# Windows: .venv\Scripts\activate    macOS/Linux: source .venv/bin/activate
pip install -e ".[dev]"

pytest            # tests
ruff check .      # lint
ruff format .     # format
```

## Layout

- `src/lane_task_manager/` – library source
- `tests/` – test suite
- `docs/` – documentation, including the [AI instruction log](docs/ai-log/README.md)
