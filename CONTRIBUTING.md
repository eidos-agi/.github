# Contributing to Eidos AGI

Thanks for your interest in contributing to the Eidos AGI ecosystem.

## Quick start

Most repos follow the same pattern:

```bash
git clone https://github.com/eidos-agi/<repo>.git
cd <repo>
pip install -e ".[dev]"
```

## For agent developers

If you're building tools that AI agents will use, pay special attention to:

1. **Tool descriptions** — Every `@tool` decorator must have a description that explains *when* to use it, not just *what* it does.
2. **Parameter descriptions** — Every parameter needs a `description` field. Agents don't have UI tooltips.
3. **Error messages** — When something fails, tell the agent what to do next. "Invalid input" is useless. "Expected ISO 8601 date, got: 'yesterday'" is actionable.
4. **Typed everything** — Type hints on all public functions.

## Code style

We use [ruff](https://docs.astral.sh/ruff/) for linting and formatting:

```bash
ruff check .
ruff format .
```

## Testing

```bash
pytest
```

## Pull requests

- One feature or fix per PR
- Include tests for new functionality
- Update CHANGELOG.md
- Ensure `ruff check .` and `pytest` pass

## Publishing

All packages use PyPI trusted publishers (OIDC). No API tokens. See the [foss-forge trusted publisher rationale](https://github.com/eidos-agi/foss-forge) for why.

## Reporting issues

Open an issue with:
1. What you were trying to do
2. What happened instead
3. Steps to reproduce
