# Dependency Management

This project uses [uv](https://docs.astral.sh/uv/) for Python package management.

## Installing Dependencies

```bash
uv sync
```

Installs all dependencies from the locked `uv.lock` file.

## Adding Dependencies

```bash
uv add <package-name>
```

Updates both `pyproject.toml` and `uv.lock`.

## Updating Dependencies

```bash
uv lock --upgrade
```

Updates all dependencies to their latest compatible versions and refreshes `uv.lock`.