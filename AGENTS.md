# Python Coding Guidelines

These are rules for a modern Python project using uv.

## Python Version

Write for Python 3.11-3.13. Do NOT write code to support earlier versions of Python.
Always use modern Python practices appropriate for Python 3.11-3.13.

Always use full type annotations, generics, and other modern practices.

## Project Setup and Developer Workflows

- Important: BE SURE you read and understand the project setup by reading the
  pyproject.toml file and the Makefile.

- ALWAYS use uv for running all code and managing dependencies.
  Never use direct `pip` or `python` commands.

- Use modern uv commands: `uv sync`, `uv run ...`, etc.
  Prefer `uv add` over `uv pip install`.

- You may use the following shortcuts

  ```shell

  # Install all dependencies:
  make install

  # Run linting (with ruff) and type checking (with basedpyright).
  # Note when you run this, ruff will auto-format and sort imports, resolving any
  # linter warnings about import ordering:
  make lint

  # Run tests:
  make test

  # Run uv sync, lint, and test in one command:
  make
  ```

- The usual `make test` like standard pytest does not show test output.
  Run individual tests and see output with `uv run pytest -s some/file.py`.

- Always run `make lint` and `make test` to check your code after changes.

- You must verify there are zero linter warnings/errors or test failures before
  considering any task complete.

## General Development Practices

- Be sure to resolve the pyright linter errors as you develop and make
  changes.

## Testing

- For longer tests put them in a file like `tests/test_somename.py` in the `tests/`
  directory (or `tests/module_name/test_somename.py` file for a submodule).

- For simple tests, prefer inline functions in the original code file below a `## Tests`
  comment. This keeps the tests easy to maintain and close to the code.
  Inline tests should NOT import pytest or pytest fixtures as we do not want runtime
  dependency on pytest.

- You can run such individual tests with `uv run pytest -s src/.../path/to/test`

## Types and Type Annotations

- Use modern union syntax: `str | None` instead of `Optional[str]`, `dict[str]` instead
  of `Dict[str]`, `list[str]` instead of `List[str]`, etc.

- Never use/import `Optional` for new code.

- Use modern enums like `StrEnum` if appropriate.

## Guidelines for Comments

- Comments should be EXPLANATORY: Explain _WHY_ something is done a certain way and not
  just _what_ is done.

- Comments should be CONCISE: Remove all extraneous words.

## Guidelines for Docstrings

- Use concise pydoc strings with triple quotes on their own lines.

- Use `backticks` around variable names and inline code excerpts.

- Use plain fences (```) around code blocks inside of pydocs.

- For classes with many methods, use a concise docstring on the class that explains all
  the common information, and avoid repeating the same information on every method.

- Docstrings should provide context or as concisely as possible explain “why”, not
  obvious details evident from the class names, function names, parameter names, and
  type annotations.

- Docstrings _should_ mention any key rationale or pitfalls when using the class or
  function.

- Exported/public variables, functions, or methods SHOULD have concise docstrings.
  Internal/local variables, functions, and methods DO NOT need docstrings unless their
  purpose is not obvious.

## Guidelines for Backward Compatibility

- When changing code in a library or general function, if a change to an API or library
  will break backward compatibility, MENTION THIS to the user.

- DO NOT implement additional code for backward compatiblity (such as extra methods or
  variable aliases or comments about backward compatibility) UNLESS the user has
  confirmed that it is necessary.
