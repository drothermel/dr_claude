# dr_claude

A Python ML project template with Claude AI integration and modern development practices.

## Overview

`dr_claude` is an opinionated Python project template specifically designed for machine learning development with Claude AI assistance. It combines strict code quality standards with ML-specific optimizations and comprehensive AI assistant instructions.

## Key Features

### 🤖 Claude AI Integration
- Pre-configured Claude AI instructions for consistent, productive assistance
- Optimized workflows for AI-human collaboration
- Permission settings that balance safety with productivity
- Task management integration for complex workflows

### 🚀 ML-Optimized Configuration
- Performance-focused practices (assertions over exceptions)
- ML-specific testing utilities (pytest-pytorch)
- Higher complexity thresholds for ML functions
- Ready for Hydra configuration system
- Excludes notebooks and outputs from linting

### ✨ Modern Python Tooling
- **Python 3.12+** with full type safety
- **UV** package manager for fast, reliable dependency management
- **Ruff** linting with 50+ rule sets enabled
- **MyPy** in strict mode for comprehensive type checking
- **Pytest** with parallel execution and ML extensions

### 📊 Code Quality Standards
- Google-style docstrings
- 88-character line length
- Security and performance linting
- Comprehensive test coverage tracking
- Automated formatting and fixes

## Getting Started

### Prerequisites
- Python 3.12 or higher
- UV package manager ([installation guide](https://github.com/astral-sh/uv))

### Setup

1. Clone the repository:
```bash
git clone <repository-url>
cd dr_claude
```

2. Install dependencies:
```bash
uv sync --group all
```

3. Verify setup:
```bash
uv run ruff check .
uv run mypy src/
uv run pytest
```

## Development Workflow

### Common Commands

| Command | Description |
|---------|-------------|
| `uv sync --group all` | Install all dependencies |
| `uv run ruff check --fix .` | Lint code with autofixes |
| `uv run ruff format .` | Format code |
| `uv run mypy src/` | Type check source code |
| `uv run pytest` | Run tests with parallel execution |
| `uv run pytest --cov=src` | Run tests with coverage report |

### Performance Guidelines

For ML code optimization, use assertions instead of exceptions:

```python
# ✅ GOOD - Assertions are optimized out in production
assert tensor.shape[0] == batch_size, f"Expected {batch_size}, got {tensor.shape[0]}"

# ❌ AVOID - Exceptions have runtime overhead
if tensor.shape[0] != batch_size:
    raise ValueError(f"Expected {batch_size}, got {tensor.shape[0]}")
```

### Project Structure

```
dr_claude/
├── src/dr_claude/      # Main package code
│   ├── __init__.py
│   └── py.typed        # Type hint support marker
├── tests/              # Test files (when added)
├── scripts/            # Training/utility scripts (when added)
├── configs/            # Hydra configs (when added)
├── CLAUDE.md           # Claude AI instructions
└── pyproject.toml      # Project configuration
```

## Testing

The project uses pytest with several extensions:

- **pytest-xdist**: Parallel test execution
- **pytest-cov**: Coverage reporting
- **pytest-timeout**: Prevent hanging tests
- **pytest-benchmark**: Performance testing
- **pytest-pytorch**: ML-specific utilities

Custom test markers:
- `@pytest.mark.slow` - Long-running tests
- `@pytest.mark.serial` - Tests that must run serially
- `@pytest.mark.integration` - Integration tests

## Configuration

### Linting (Ruff)
- 50+ rule sets for comprehensive checking
- ML-friendly complexity thresholds
- Security and performance rules enabled
- Automatic fixes where possible

### Type Checking (MyPy)
- Strict mode enabled
- No implicit Any types
- Full function annotations required
- Performance optimized with caching

### Testing (Pytest)
- Parallel execution by default
- Coverage tracking with ML-specific exclusions
- Comprehensive test markers
- Clean output with optional logging

## Claude AI Integration

This repository includes comprehensive Claude AI instructions in `CLAUDE.md` that:
- Define essential commands and workflows
- Establish code quality standards
- Provide ML-specific guidelines
- Enable productive AI-assisted development

When using Claude AI with this repository, it will automatically understand the project structure, conventions, and best practices.

## Contributing

When contributing to this project:
1. Follow the established code style and conventions
2. Ensure all quality checks pass before committing
3. Use descriptive commit messages
4. Add tests for new functionality
5. Update documentation as needed

## License

[Add license information here]

## Acknowledgments

Built with modern Python tooling:
- [UV](https://github.com/astral-sh/uv) - Fast Python package manager
- [Ruff](https://github.com/astral-sh/ruff) - Fast Python linter
- [MyPy](https://mypy-lang.org/) - Static type checker
- [Pytest](https://pytest.org/) - Testing framework