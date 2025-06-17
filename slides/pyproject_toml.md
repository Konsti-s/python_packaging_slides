<!-- Slide: pyproject.toml Specification -->
## pyproject.toml: Python's Project Configuration Standard

**PEP 518 and PEP 621**Specified `pyproject.toml` as the standard configuration file

#### Three Key Standardized Sections:
1. **[build-system]**: Specifies build requirements for packaging
   * Enables different build tools (setuptools, flit, hatchling, etc.)

2. **[project]**: Contains standardized metadata
   * Name, version, description, dependencies, etc.

3. **[tool.*]**: Tool-specific configurations. Non-standardized but widely adopted
   * Allows using different tools for different tasks (e.g., black for formatting, ruff for linting)

> *The standard enables interoperability between different packaging tools*

--

<!-- Slide: pyproject.toml Example -->
## pyproject.toml Example

```toml
# Build system configuration (PEP 518)
[build-system]
requires = ["hatchling>=1.0.0"]
build-backend = "hatchling.build"

# Project metadata (PEP 621)
[project]
name = "example-package"
version = "0.1.0"
description = "An example Python package"
readme = "README.md"
requires-python = ">=3.8"
license = {text = "MIT"}
authors = [
    {name = "Example Author", email = "author@example.com"}
]
dependencies = [
    "requests>=2.28.0",
    "numpy>=1.24.0",
    "my-lib",
]

# Tool-specific configurations
[tool.black]
line-length = 88

[tool.ruff]
target-version = "py38"

[tool.pytest.ini_options]
minversion = "6.0"
testpaths = ["tests"]

[tool.uv.sources]
my-lib = { path = "../my_lib", editable = true }
```