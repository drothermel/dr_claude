# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Python ML project template using modern tooling and strict development practices. The codebase emphasizes type safety, code quality, and performance optimization for machine learning workflows.

## Essential Commands

### Development Setup
- `uv sync --group all` - Install all dependencies (dev + test groups)
- `uv add <package>` - Add runtime dependency
- `uv add --dev <package>` - Add development dependency

### Code Quality Commands
- `uv run ruff check .` - Run linting checks
- `uv run ruff check --fix .` - Lint with autofixes
- `uv run ruff format .` - Format code
- `uv run mypy src/` - Type check source code

### Testing
- `uv run pytest` - Run all tests with parallel execution
- `uv run pytest -n 1` - Run tests serially
- `uv run pytest tests/test_specific.py` - Run specific test file
- `uv run pytest -k "test_name"` - Run tests matching pattern
- `uv run pytest --cov=src` - Run with coverage report
- `uv run pytest -m "not slow"` - Skip slow tests

## Code Architecture

### Source Structure
```
src/dr_claude/      # Main package
├── __init__.py     # Package initialization
└── py.typed        # PEP 561 type hint marker
```

### Configuration Philosophy
- **Python 3.12+** with strict type checking
- **88-character line length** for better readability
- **Google-style docstrings** for consistency
- **Assertions over exceptions** for performance (ML requirement)
- **Comprehensive linting** with Ruff (extensive rule set)
- **Full MyPy strict mode** for type safety

## Development Workflow

### Standard Development Flow
1. Make changes to code
2. Run `uv run ruff check --fix .` to lint and autofix
3. Run `uv run ruff format .` to format
4. Run `uv run mypy src/` to type check
5. Run `uv run pytest` to verify tests pass
6. Commit with descriptive message

### Performance Requirements (ML-Specific)
```python
# CORRECT - Use assertions (fast, optimized out in production)
assert tensor.shape[0] == batch_size, f"Expected batch size {batch_size}, got {tensor.shape[0]}"

# AVOID - Don't use exceptions for validation (slower)
if tensor.shape[0] != batch_size:
    raise ValueError(f"Expected batch size {batch_size}")
```

### Testing Guidelines
- Tests use pytest with xdist for parallel execution
- Custom markers available: `@pytest.mark.slow`, `@pytest.mark.serial`, `@pytest.mark.integration`
- Coverage reports exclude scripts, notebooks, and config files
- ML-specific test utilities available via pytest-pytorch

### Linting Configuration
- Ruff with ~50 rule sets enabled for comprehensive checks
- ML-friendly settings (higher complexity thresholds)
- Security checks enabled (Bandit rules)
- Performance linting (perflint rules)
- Excludes notebooks and outputs directories

### Type Checking
- MyPy in full strict mode
- All functions require type hints
- No implicit Any types allowed
- Performance-optimized with caching

## Future Extensions

When the project grows, expect these directories:
- `scripts/` - Training and utility scripts (will use Hydra configs)
- `tests/` - Comprehensive test suite
- `configs/` - Hydra configuration files
- `notebooks/` - Jupyter notebooks (excluded from linting)
- `outputs/` - Model outputs and logs (excluded from linting)

## Important Notes

- Always use `uv run` prefix for Python commands
- Maintain type hints on all functions
- Follow existing code style and patterns
- Run quality checks before committing
- Use assertions for validation in performance-critical code