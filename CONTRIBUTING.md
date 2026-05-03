# Contributing to Projet Résurgence

Thank you for your interest in contributing to Projet Résurgence! This document provides guidelines and instructions for contributing.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Project Structure](#project-structure)
- [Making Changes](#making-changes)
- [Commit Messages](#commit-messages)
- [Pull Requests](#pull-requests)
- [Coding Standards](#coding-standards)
- [Testing](#testing)

---

## Code of Conduct

This project adheres to our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## Getting Started

1. **Fork** the repository you want to contribute to
2. **Clone** your fork locally
3. **Create a branch** for your changes
4. **Make your changes** following our coding standards
5. **Test** your changes
6. **Submit a pull request**

## Development Setup

### Prerequisites

- **Docker** and **Docker Compose** — for running the full stack
- **Python 3.12** — for backend services and bots
- **Node.js 20+** — for OnlineMap
- **PostgreSQL 16** — if running services outside Docker

### Quick Start

```bash
# Clone the monorepo
git clone https://github.com/Projet-Resurgence/ProjetResurgence.git
cd ProjetResurgence

# Configure environment
cp .env.example .env
# Edit .env with your credentials

# Start all services
docker compose up -d

# View logs
docker compose logs -f
```

### Individual Projects

Each project has its own `README.md` and `CLAUDE.md` with specific setup instructions.

## Project Structure

```
ProjetResurgence/
├── PR_API/              # Main REST API (Flask, 37 controllers)
├── PAPA/                # Admin panel (Flask + Bootstrap)
├── Game-Dashboard/      # Player dashboard (Flask + Jinja2)
├── TechPanel/           # Technology creation (Flask + Jinja2)
├── WebCalculator/       # Economy calculator (Flask + Jinja2)
├── Kanbanizer/          # GitHub Kanban board (Flask)
├── OnlineMap/           # Interactive map (React + Vite)
├── LLM_api/             # AI chat wrapper (Flask + llama.cpp)
├── WebAuth-Handler/     # Centralized auth (Flask)
├── resurgence-web/      # Main static website (HTML/CSS/JS)
├── bots/
│   ├── commons/         # Shared library (models, DTOs, utils)
│   ├── CLEA/            # Economy Discord bot
│   └── MARC/            # Military Discord bot
├── MapLib/              # C++ map library
└── docker/              # Infrastructure (nginx, db)
```

## Making Changes

### Branch Naming

Use descriptive branch names:

```
feature/add-technology-export
bugfix/fix-unit-count-display
docs/update-api-reference
refactor/extract-auth-middleware
```

### Commit Messages

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

**Types:**
- `feat` — New feature
- `fix` — Bug fix
- `docs` — Documentation changes
- `style` — Code style (formatting, no logic change)
- `refactor` — Code refactoring
- `test` — Adding or updating tests
- `chore` — Maintenance tasks

**Examples:**
```
feat(pr-api): add country debt management endpoint
fix(game-dashboard): correct unit visibility in summary
docs(readme): update architecture diagram
refactor(techpanel): extract image upload logic
test(common): add DTO validation tests
chore(docker): update nginx config for new subdomain
```

## Pull Requests

1. **Fill out the PR template** — all fields are important
2. **Link related issues** — use `Closes #123` or `Fixes #456`
3. **Keep it focused** — one feature/fix per PR
4. **Write clear descriptions** — explain the "why", not just the "what"
5. **Request reviews** — tag relevant maintainers

### PR Size

- Small PRs (< 200 lines) are preferred and merged faster
- Large PRs should be broken into smaller, logical commits

## Coding Standards

### Python

- Follow [PEP 8](https://pep8.org/)
- Use type hints for function signatures
- Maximum line length: 120 characters
- Use `black` for formatting, `flake8` for linting
- Docstrings for all public functions and classes

```python
def get_country(country_id: int) -> dict | None:
    """Retrieve country data by ID.

    Args:
        country_id: The unique country identifier.

    Returns:
        Country data dict or None if not found.
    """
```

### JavaScript / TypeScript

- Use ES6+ features
- Prefer `const` over `let`, avoid `var`
- Use async/await over raw promises
- Follow the existing project's style (check `.eslintrc` if present)

### HTML / CSS

- Semantic HTML5 elements
- CSS variables for theming
- Mobile-first responsive design
- Follow the existing design system (gold theme: `#D5B654`)

### SQL / Database

- Use Alembic for all schema migrations
- Never modify production data directly
- Add indexes for frequently queried columns

## Testing

### Python

```bash
# Install test dependencies
pip install pytest pytest-flask

# Run tests
pytest -v

# Run with coverage
pytest --cov=src --cov-report=html
```

### Node.js / React

```bash
# Run tests
npm test

# Run with coverage
npm test -- --coverage
```

### Docker

```bash
# Test the full stack
docker compose up -d
docker compose exec pr-api pytest
```

## Critical Rules

1. **Never commit secrets** — use `.env` files, never hardcode credentials
2. **Internal URLs only** — service-to-service calls must use Docker hostnames (`http://pr-api:5000`), NOT external URLs
3. **Shared secrets** — `GAME_DASHBOARD_JWT_SECRET` and `PR_API_JWT_SECRET` are shared between services; never change one without the other
4. **No direct DB access from web apps** — all data goes through PR_API (except PAPA which is admin-only)
5. **French locale** — user-facing text should be in French

## Questions?

- Join our [Discord](https://discord.projet-resurgence.fr) for real-time discussion
- Open a [Question issue](https://github.com/Projet-Resurgence/ProjetResurgence/issues/new?template=question.yml) for async discussion
- Check individual project `CLAUDE.md` files for technical details

---

Thank you for contributing to Projet Résurgence! 🌍
