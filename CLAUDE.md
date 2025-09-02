# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Python project called "log-llm-analyzer" that appears to be in early development stages. The project uses modern Python tooling with `uv` as the package manager and requires Python 3.13+.

## Development Environment

### Package Management
- **Package Manager**: `uv` (modern Python package manager)
- **Python Version**: 3.13+
- **Lock File**: `uv.lock` contains dependency specifications

### Project Structure
- `main.py`: Entry point with basic "Hello World" functionality
- `doc/`: Contains Claude Code Python SDK documentation
- `pyproject.toml`: Project configuration and dependencies

## Common Commands

### Running the Application
```bash
python main.py
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

# Run Python with uv
uv run python main.py
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

## Development Notes

- The project is currently in a minimal state with just a basic main.py file
- Comprehensive linting, formatting, and type checking tools are configured in pyproject.toml
- The `doc/claude-sdk.md` file contains comprehensive documentation for integrating Claude Code Python SDK, which may be relevant for future development

## Architecture

The current architecture is minimal:
- Single entry point in `main.py`
- No established patterns or modules yet
- Ready for expansion based on log analysis requirements

Since this project appears to be focused on log analysis with LLMs, future development will likely involve:
- Log parsing and processing modules
- LLM integration for analysis
- Data structures for representing log insights
- Potentially CLI interfaces for log analysis workflows