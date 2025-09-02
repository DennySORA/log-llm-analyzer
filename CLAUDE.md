# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Python project called "log-llm-analyzer" focused on log analysis using LLMs. The project uses modern Python tooling with `uv` as the package manager, requires Python 3.13+, and includes the Claude Code SDK for AI-powered development workflows.

## Development Environment

### Package Management
- **Package Manager**: `uv` (modern Python package manager)
- **Python Version**: 3.13+
- **Lock File**: `uv.lock` contains dependency specifications

### Project Structure
- `src/log-llm-analyzer/`: Main package directory
  - `main.py`: Entry point with basic "Hello World" functionality
  - `py.typed`: Indicates type hint support for the package
- `doc/`: Contains Claude Code Python SDK documentation
- `pyproject.toml`: Comprehensive project configuration with dependencies and tooling setup
- `LICENSE`: MIT License file
- `README.md`: Project documentation
- `CLAUDE.md`: Development guidance for Claude Code

## Common Commands

### Running the Application
```bash
# Run with uv (recommended)
uv run python src/log-llm-analyzer/main.py

# Or activate virtual environment and run
source .venv/bin/activate
python src/log-llm-analyzer/main.py
```

### Package Management
```bash
# Install dependencies
uv sync

# Add new dependency
uv add <package-name>

# Update dependencies  
uv lock --upgrade
```

### Python Environment
```bash
# Activate virtual environment (if using uv's built-in venv)
source .venv/bin/activate

# Run Python with uv (recommended)
uv run python src/log-llm-analyzer/main.py

# Install development dependencies
uv sync
```

## Core Development Rules

**CRITICAL: Always follow these rules when writing code for this project:**

1. **Documentation First**: Before writing any code, ALWAYS consult the documentation in the `doc/` directory first. The technology is cutting-edge and requires accurate reference to ensure proper implementation.

2. **Environment & Package Management**: 
   - Use `uv` and the generated `.venv` for Python execution
   - Install packages with `uv add <package-name>`
   - Never use pip or other package managers

3. **Code Quality Standards**:
   - Strictly follow SOLID principles and Clean Code practices
   - Keep each file under 300 lines maximum
   - Use interface abstraction and dependency injection
   - Design for testability and maintainability

4. **Type Annotations**:
   - ALL functions must have complete Python type annotations
   - Use built-in types: `list`, `dict`, `set`, `tuple` (not `typing.List`, `typing.Dict`)
   - Leverage Python 3.13+ type system features

5. **Mandatory Code Quality Checks**:
   After every development session, run these commands and ensure no errors:
   ```bash
   ruff format ./src
   ruff check --fix ./src  
   mypy ./src
   ```
   Code is not considered complete until all these checks pass.

## Dependencies & Tools

### Core Dependencies
- **claude-code-sdk>=0.0.20**: Claude Code SDK for AI-powered development
- **pydantic>=2.11.7**: Data validation and settings management
- **pydantic-settings>=2.10.1**: Configuration management

### Development Tools
- **ruff>=0.12.11**: Fast Python linter and formatter (replaces flake8, isort, etc.)
- **mypy>=1.17.1**: Static type checker with strict configuration
- **bandit[toml]>=1.8.6**: Security-focused static analysis

### Build System
- **hatchling**: Modern Python build backend
- Configured for `src/` layout with proper package structure

## Development Notes

- Project follows `src/` layout structure with proper Python packaging
- Comprehensive tooling configuration in pyproject.toml with strict quality standards
- Type hints are fully supported with `py.typed` marker file
- The `doc/claude-sdk.md` file contains comprehensive documentation for integrating Claude Code Python SDK

## Architecture

The project follows Python packaging best practices:
- **Package Structure**: `src/log-llm-analyzer/` layout for clean separation
- **Entry Point**: `src/log-llm-analyzer/main.py` with basic functionality
- **Type Safety**: Full type hint support with `py.typed` marker
- **Build System**: Modern hatchling-based build configuration

### Planned Architecture
As a log analysis tool with LLM integration, the architecture will likely expand to include:
- **Log Processing**: Parsers for various log formats
- **LLM Integration**: Claude Code SDK integration for intelligent analysis
- **Data Models**: Pydantic models for log structures and analysis results
- **Configuration**: Pydantic Settings for application configuration
- **CLI Interface**: Command-line tools for log analysis workflows
- **Security**: Bandit-compliant secure coding practices