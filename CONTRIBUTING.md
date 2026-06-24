# Contributing to Stock-Price-Sales-Forecasting-Engine

Thank you for your interest in contributing! This document outlines the process for contributing code, reporting issues, and proposing enhancements.

## Getting Started

1. Fork the repository and clone your fork
2. Set up the development environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts\activate
   pip install -r requirements.txt
   cp .env.example .env
   ```
3. Install pre-commit hooks:
   ```bash
   pip install pre-commit
   pre-commit install
   ```
4. Start local infrastructure:
   ```bash
   docker-compose up -d postgres redis
   python scripts/init_db.py
   alembic upgrade head
   ```

## Development Workflow

1. Create a feature branch from `develop`: `git checkout -b feature/your-feature-name`
2. Make your changes, following the code style enforced by Black/Ruff (run automatically via pre-commit)
3. Add or update tests for any new functionality — target 80%+ coverage on new code
4. Run the test suite locally:
   ```bash
   pytest tests/unit -v
   pytest tests/integration -v
   pytest --cov=backend --cov-report=term-missing
   ```
5. Run linting manually if needed:
   ```bash
   black backend/ ml/ tests/
   ruff check backend/ ml/ tests/ --fix
   mypy backend/ --ignore-missing-imports
   ```
6. Commit using clear, descriptive messages (conventional commits style preferred: `feat:`, `fix:`, `docs:`, `refactor:`, `test:`)
7. Push and open a Pull Request against `develop`

## Pull Request Guidelines

- Keep PRs focused on a single concern — large multi-feature PRs are harder to review
- Include a clear description of *what* changed and *why*
- Link any related issues
- Ensure CI passes (lint, test, build, security scan jobs in `.github/workflows/ci-cd.yml`)
- Add documentation updates alongside code changes (docstrings, `docs/*.md`, README sections as relevant)

## Code Style

- **Formatting**: Black with 100-character line length (see `pyproject.toml`)
- **Linting**: Ruff with rules `E, F, W, I, N, UP, B`
- **Type hints**: Encouraged throughout, especially in service-layer and model code; mypy runs in non-blocking mode currently but contributions with full type coverage are appreciated
- **Docstrings**: Google-style docstrings for all public classes and functions, especially in `backend/models/` and `backend/services/` where architectural context (paper citations, design rationale) is valuable

## Adding a New Forecasting Model

1. Implement the model in the appropriate subdirectory under `backend/models/` (e.g., `backend/models/stock/` for new stock forecasters)
2. Follow the existing pattern: a model class with `fit()`/`predict()` (or PyTorch `nn.Module` + a paired `Trainer` class for deep learning models)
3. Register the model name in `AdaptiveEnsemble`'s `model_names` list within `StockForecastService.__init__`
4. Add a training pipeline script in `ml/pipelines/train_{model_name}.py`
5. Document the model's architecture and design rationale in `docs/model_documentation.md`
6. Add unit tests in `tests/unit/test_models/`

## Adding a New API Endpoint

1. Define request/response Pydantic schemas in `backend/api/schemas/schemas.py`
2. Implement the endpoint in the relevant router under `backend/api/endpoints/`
3. Keep business logic in a service class under `backend/services/` — endpoints should be thin
4. Register the router in `backend/main.py` if creating a new router file
5. Document the endpoint in `docs/api_reference.md`
6. Add integration tests in `tests/integration/`

## Reporting Bugs

Open a GitHub issue including:
- A clear title and description
- Steps to reproduce
- Expected vs. actual behavior
- Environment details (OS, Python version, Docker vs. local)
- Relevant logs or stack traces

## Proposing Features

Open a GitHub issue tagged `enhancement` describing the use case and proposed approach before starting significant implementation work, so we can align on design before code is written.

## Code of Conduct

Be respectful and constructive. We're building this together — assume good intent, give specific actionable feedback in reviews, and keep discussions focused on the technical merits of a contribution.

## Questions?

Open a GitHub Discussion or issue tagged `question`. We're happy to help you get oriented in the codebase.
