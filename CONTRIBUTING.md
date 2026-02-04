# Contributing

This project uses [Conventional Commits](https://www.conventionalcommits.org/).

## Scopes

Scopes can be extended as the project grows. Current scopes:

| Scope | Description | Files |
|-------|-------------|-------|
| `docs` | Documentation content | [`docs/`](docs/) |
| `config` | Configuration files | [`mkdocs.yml`](mkdocs.yml) |
| `theme` | Theme customization | [`docs/stylesheets/`](docs/stylesheets/), [`docs/javascripts/`](docs/javascripts/) |
| `devcontainer` | Dev container setup | [`.devcontainer/`](.devcontainer/) |
| `deps` | Dependencies | `requirements.txt`, `package.json` |

The commit template is configured automatically when using the devcontainer.

For local development:
```bash
git config commit.template .gitmessage
```
