<!-- Slide 1: Setup.py Era -->
## Python Packaging: The Early Days

* **setup.py** (2000s): The original Python packaging mechanism
  * Script-based approach using Distutils, later Setuptools (easy_install)
  * Configuration mixed with Python code
* **setup.cfg** (mid-2000s): First attempt at declarative configuration
  * Still required setup.py for many operations
  * Limited support for complex dependencies
* **dependencies**: Manual retrieval
  * Manual download of packages from arbitrary sources required, e.g. private servers.
  * Searchable via the Vaults of Parnassus (early-2000s)

> Problems: Build process tied to execution, security concerns with arbitrary code sources and execution, no virtual environments, no separation of buildtime and runtime, dependency hell

---

<!-- Slide 2: Pip and PyPI -->
## Package Installation: Pip and PyPI

* **PyPI** (Python Package Index, 2002): Central repository for packages
  * Originally called the "Cheeseshop", now hosts over 450,000 projects
  * Replaced the Vaults of Parnassus, a very popular searchable catalog of Python modules, scripts and resources

* **easy_install**: CLI installation
  * A CLI tool that came with setuptools and integrated tightly with PyPI
  * Deprecated

* **pip** (2008): Package installer for Python
  * Introduced requirements.txt for dependency listing
  * Added uninstallation, better dependency resolution
  * Had a greedy resolver until 2020 (OMG)

> Solved: Central repository, hashes, declarative syntax, improved dependency resolution
> 
> Still problematic: No virtual environments, No lock files, still "works on my machine" syndrome, Build times took long and were not always reliable

---

<!-- Slide 3: Virtual Environments -->
## Next up - Isolation: Virtual Environments

* **virtualenv** (2007): First tool for isolated Python environments
  * Created separate Python installations for projects
  * Allowed different projects to use different dependency versions

* **venv** (2014, PEP 405): Built-in virtual environment module
  * Standardized approach to environment isolation
  * Simpler but less feature-rich than virtualenv

> Solved: Virtual environments, environment management separate from package management

---

<!-- Slide 4: Distribution Formats -->
## Getting good - Package Distribution

* **Source Distribution (sdist)**: Still widely used
  * Tar archive containing source code and build instructions
  * Requires build step on installation
  * Platform-independent but may need compilers
  * still widely used

* **Egg**: Deprecated in favor of wheels
  * Pre-built distribution format
  * No standard, only used by setuptools, poor uninstall capabilities

* **Wheel (PEP 427, 2012)**: Current standard
  * Pre-built distribution format
  * Standard, faster installation, less error-prone than eggs

> Evolution: From build-time to pre-built distributions for faster, more reliable installs, much faster package installation times
>
> Still problematic: Yet again no lock files (OMG...)

--

<!-- Slide 5: Wheel Naming Convention -->
## Wheel Naming Convention

Wheel names encode compatibility information, enabling precise dependency resolution in lock files.
Wheel filenames follow a specific pattern:

> `{distribution}-{version}(-{build tag})?-{python tag}-{abi tag}-{platform tag}.whl`

**Pure Python (Universal) Wheels:** (E.g. Python 2 & 3, no ABI dependencies, any platform)

> `tzdata-2025.2-py2.py3-none-any.whl`

**Compiled Binary Wheels:** (E.g. CPython 3.10, specific ABI, Linux x86_64 only)

> `scikit_learn-1.6.1-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl`

---

<!-- Slide 7: PEP 518 and Beyond -->
## Standardization and pyproject.toml

* **PEP 518 and 621 (2016-2020)** (2016): Specified pyproject.toml for build dependencies
  * Decoupled build-time and runtime dependencies
  * Unified approach to package configuration
  * Tool-agnostic specification for project metadata

* Building on these PEP-specifications poetry was the first tool that built a reliable resolver that produced lock files (Pipenv used lock files earlier but it did not respect PEP518 and really was not reliable)
* Different tools could be used in the same project with a unified configuration file

---

<!-- Slide 8: Core Challenges -->
## Summary: Package Management Challenges Overview

* **Build vs. Runtime**: setup.py executing arbitrary code during installation
* **Package distribution**: Compilation of C extensions varied across platforms, build times took long
* **Security Concerns**: Need for integrity verification (hashes, signatures)
* **Dependency Resolution**: Conflicting requirements created "dependency hell", no mature resolves until poetry
* **Reproducibility**: No lock files in early ecosystem
* **Project Configuration**: No unified syntax for project configuration in early ecosystem
