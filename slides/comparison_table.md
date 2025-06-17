<!-- Slide: Tool Comparison -->
## Python Packaging Tools Comparison

| Tool | Created | Python Install | Env Management | Dependency Mgmt | Build System | 3rd party tools |
|------|---------|:--------------:|:--------------:|:---------------:|:------------:|:------------:|
| setuptools | 2004 | ❌ | ❌ | ✅ | ✅ | ❌ |
| virtualenv | 2007 | ❌ | ✅ | ❌ | ❌ | ❌ |
| pip | 2008 | ❌ | ❌ | ✅ | ❌ | ❌ |
| pyenv | 2013 | ✅ | ✅ | ❌ | ❌ | ❌ |
| flit | 2016 | ❌ | ❌ | ✅ | ✅ | ❌ |
| pipenv | 2017 | ❌ | ✅ | ✅🔒 | ❌ | ❌ |
| pipx | 2018 | ❌ | ✅ | ❌ | ❌ | ✅ |
| poetry | 2018 | ❌ | ✅ | ✅🔒 | ✅ | ❌ |
| PDM | 2019 | ❌ | ⚠️ | ✅🔒 | ✅ | ❌ |
| hatchling | 2021 | ❌ | ❌ | ✅ | ✅ | ❌ |
| rye | 2023 | ✅ | ✅ | ✅🔒 | ⚠️ | ✅ |
| UV | 2024 | ✅ | ✅ | ✅🔒 | 👁️ | ✅ |

<small>
✅ = Supported feature &nbsp;&nbsp; ❌ = Not supported &nbsp;&nbsp; ⚠️ = Uses third-party tools &nbsp;&nbsp; 👁️ = Preview &nbsp;&nbsp; 🔒 = Includes lock files
</small>