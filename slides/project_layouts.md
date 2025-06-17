<!-- Slide: Project Layout Comparison -->
## Project Layout Comparison

<div style="display: flex; justify-content: space-around; align-items: flex-start; gap: 2rem;">

<div style="flex: 1;">

### Src Layout
```
my_project/
├── pyproject.toml
├── src/
│   └── my_package/
│       ├── __init__.py
│       └── module.py
└── tests/
    ├── test_module.py
    └── ...
```

**Pros:**
- Prevents accidental imports
- Clear separation of source code
- Better for complex projects

</div>

<div style="flex: 1;">

### Flat Layout
```
my_project/
├── pyproject.toml
├── my_package/
│   ├── __init__.py
│   └── module.py
└── tests/
    ├── test_module.py
    └── ...
```

**Pros:**
- Simpler structure
- Fewer directories
- Traditional Python layout

</div>

</div>

<div style="margin-top: 2rem; text-align: center;">
<small>Both layouts are valid - choose based on project complexity and team preferences</small>
</div>