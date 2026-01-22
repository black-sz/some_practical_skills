---
name: git_changelog_analyzer
description: Analyze Git changes and generate Conventional Commits-compliant commit messages for Python projects
version: 1.0.0
---

# Skill: Git Changelog Analyzer & Commit Message Generator for Python

## Objective
When the user is preparing a Git commit for a Python project, automatically analyze all modified files, **with special attention to Python-specific patterns and structures**. Summarize the changes and generate well-formatted, Conventional Commits-compliant commit messages in both Chinese and English.

## Workflow
1.  **Analyze Git Status**: Run `git status --short` to get the changed file list.
2.  **Examine Changes with Python Context**:
    *   For each `.py` file, analyze the diff to identify:
        *   **Function/Method Signatures**: New additions, parameter changes, return type annotations.
        *   **Class Definitions**: New classes, inherited base classes, modified class attributes.
        *   **Imports**: Added, removed, or changed import statements (e.g., from standard library, third-party packages, or internal modules). This can indicate dependency or architectural shifts.
        *   **Decorator Usage**: Introduction or removal of decorators like `@property`, `@staticmethod`, `@dataclass`, or framework-specific ones (e.g., `@app.route`).
    *   **Key Non-Python Files**:
        *   `requirements.txt`, `pyproject.toml`, `Pipfile`, `setup.py`: Changes imply **dependency updates or additions**. Try to extract the package name and version.
        *   `__init__.py`: Changes can indicate module public interface changes.
        *   `test_*.py` or files in `tests/`: Flag changes as related to **testing**.
        *   Configuration files (`.yml`, `.ini`, `.env`): Note as configuration updates.
3.  **Categorize & Summarize (Python-aware)**:
    *   Group changes into categories like: `Core Logic`, `API Layer`, `Data Models`, `CLI`, `Dependencies`, `Configuration`, `Tests`, `Documentation`.
    *   Assess the change's impact: Is it a `BREAKING CHANGE` (e.g., removed public function, changed API response structure)?
4.  **Generate Commit Messages**:
    *   Use appropriate Conventional Commit `types`. For Python, common types include:
        *   `feat`, `fix`, `refactor`, `docs`, `test`, `chore`.
        *   For dependency updates, consider `chore(deps):` or `build(deps):`.
    *   The `scope` can be a module name (e.g., `auth`, `models`, `utils`), or a component like `api`, `cli`, `deps`.

## Output Format
The output must be formatted Markdown.

### Summary of Changes Analysis (Python Project)
*   **Files Modified**: [Number] files
*   **Primary Change Types**: [e.g., New Feature, Bug Fix, Dependency Update, Refactor]
*   **Python-Specific Notes**:
    *   Dependencies Changed: [e.g., Added `pandas`, Upgraded `fastapi` to `^0.104.0`]
    *   Modules/Components Affected: [e.g., `core.calculations`, `api.routers`]
    *   Test Files Updated: [Yes/No, e.g., `Updated 2 test files for the new validation logic`]

### Recommended Commit Message (English)