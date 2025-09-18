# Agent Instructions for Python Projects

This document outlines best practices for working with this Python project. Adhering to these guidelines will ensure code quality, maintainability, and consistency.

## 1. Dependency Management with `uv`

This project uses `uv` for package and project management.

- **Create a virtual environment:** `uv venv`
- **Add a dependency:** `uv add <package-name>`
- **Install dependencies:** `uv sync`

## 2. Linting and Formatting with `ruff`

We use `ruff` for linting and formatting to maintain a consistent code style.

- **Check for issues:** Run `ruff check .` to see linting and formatting errors.
- **Fix issues:** Run `ruff format .` and `ruff check . --fix` to automatically fix any issues.
- **Configuration:** `ruff` is configured in `pyproject.toml`.

## 3. Single Responsibility Principle (SRP)

Each module, class, or function should have one and only one reason to change.

- **Functions:** Should do one thing and do it well.
- **Classes:** Should have a single, well-defined purpose.
- **Modules:** Should group related functionality.

Avoid creating "god objects" or utility modules with unrelated functions.

## 4. Testing with `pytest`

We use `pytest` for testing.

- **Running tests:** Execute `pytest` in the root directory.
- **Writing tests:**
    - Test files should be named `test_*.py`.
    - Test functions should be named `test_*`.
    - Use descriptive test names.
    - Tests should be placed in the `/tests` directory.
    - Aim for high test coverage.

## 5. Readability and Code Style

Write clean, readable code. Follow PEP 8 guidelines.

- **Naming:** Use descriptive names for variables, functions, and classes (e.g., `user_profile` instead of `up`).
- **Comments:** Write comments for complex logic, but prefer self-documenting code.
- **Simplicity:** Prefer simple, straightforward code over complex, clever solutions.

## 6. Type Hinting

This project uses type hints (PEP 484).

- **Add type hints:** All new functions and methods must include type hints for arguments and return values.
- **Clarity:** Type hints improve code clarity and allow for static analysis.
- **Mypy:** You can use `mypy` to statically check your type hints.

## 7. Reduced Coupling

Strive for low coupling between different parts of the codebase.

- **Interfaces:** Depend on abstractions (like abstract base classes), not on concrete implementations.
- **Dependency Injection:** Inject dependencies instead of creating them inside a class or function. This makes components easier to test and reuse.
- **Avoid global state:** Minimize the use of global variables.

## 8. Security

Write secure code by default.

- **Use `bandit`:** Run `bandit -r .` to find common security issues.
- **Use `safety`:** Run `safety check` to check for known vulnerabilities in your dependencies.
- **Input validation:** Always validate and sanitize user-provided input.

## 9. Logging

Use the `logging` module for logging.

- **Configuration:** Configure logging in a centralized place.
- **Levels:** Use appropriate log levels (`DEBUG`, `INFO`, `WARNING`, `ERROR`, `CRITICAL`).
- **Context:** Provide context in your log messages.

## 10. Documentation

Document your code.

- **Docstrings:** Write docstrings for all modules, classes, functions, and methods (e.g., following Google Style or NumPy style).
- **README:** Keep the `README.md` file up-to-date.
- **Project Documentation:** For larger projects, consider using a tool like Sphinx or MkDocs to generate documentation.

## The Zen of Python

Finally, always remember the principles of "The Zen of Python" (PEP 20):

> Beautiful is better than ugly.
> Explicit is better than implicit.
> Simple is better than complex.
> Complex is better than complicated.
> Flat is better than nested.
> Sparse is better than dense.
> Readability counts.
> Special cases aren't special enough to break the rules.
> Although practicality beats purity.
> Errors should never pass silently.
> Unless explicitly silenced.
> In the face of ambiguity, refuse the temptation to guess.
> There should be one-- and preferably only one --obvious way to do it.
> Although that way may not be obvious at first unless you're Dutch.
> Now is better than never.
> Although never is often better than *right* now.
> If the implementation is hard to explain, it's a bad idea.
> If the implementation is easy to explain, it may be a good idea.
> Namespaces are one honking great idea -- let's do more of those!
