## Importing Modules

A **module** is a Python file containing reusable code such as functions, classes, and variables. Modules allow us to organize code and reuse functionality across different programs.

### Key Concepts

* **`import`** — Imports a module into a program.
* **`import module`** — Imports the complete module.
* **`from module import`** — Imports specific items from a module.
* **`import ... as`** — Gives a module or item an alias.
* **Standard library modules** — Modules provided with Python, such as `math`, `random`, and `datetime`.
* **User-defined modules** — Python files created by the programmer.
* **Module functions** — Functions can be accessed using the module name.
* **Module namespace** — Keeps imported names organized and prevents unnecessary naming conflicts.
* **Multiple modules** — A program can import and use several modules.
* **Reusable code** — Modules help avoid repeating code.

### Example

```python
import math

number = 25

print(math.sqrt(number))
```

Here, `math` is imported and its `sqrt()` function is used.

[View more details →](./Python_Detaild/importing_modules.md)

---

## Creating Reusable Modules

A **reusable module** is a Python file containing functions, classes, variables, or other logic that can be imported and used in different programs.

### Key Concepts

* **Module** — A `.py` file containing reusable Python code.
* **Functions** — Put commonly used operations into functions.
* **Parameters** — Make functions flexible by accepting different values.
* **Return values** — Return results instead of only printing them.
* **Importing** — Use `import` or `from ... import ...` to reuse the module.
* **Single responsibility** — Keep a module focused on a related set of tasks.
* **Avoid duplication** — Write logic once and reuse it.
* **Module namespace** — Access module members using the module name.
* **`__name__`** — Helps distinguish between direct execution and importing.
* **`if __name__ == "__main__":`** — Keeps test/demo code from running during import.
* **Documentation** — Use docstrings to explain reusable functions and modules.
* **Clean dependencies** — Import only what the module actually needs.

### Example

**`calculator.py`**

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b
```

**`main.py`**

```python
import calculator

print(calculator.add(10, 5))
print(calculator.subtract(10, 5))
```

The logic is written once in `calculator.py` and can be reused by other Python programs.

[View more details →](./Python_Detaild/creating_reusable_modules.md)

---

## Package Organization

A **package** is a directory used to organize related Python modules. Package organization helps divide a large project into smaller, logical parts that are easier to maintain and reuse.

### Key Concepts

* **Package** — A directory containing related Python modules.
* **Module** — A Python `.py` file containing reusable code.
* **Subpackage** — A package inside another package.
* **`__init__.py`** — A file traditionally used to define and initialize a package.
* **Package structure** — Organizes modules according to their responsibilities.
* **Importing from packages** — Use paths such as `from utilities.calculator import add`.
* **Absolute imports** — Import using the full package path.
* **Relative imports** — Import modules relative to the current package.
* **Separation of responsibilities** — Keep related functionality together.
* **Reusable organization** — Makes code easier to reuse across a project.

### Example

```text
my_project/
│
├── main.py
│
└── utilities/
    ├── __init__.py
    ├── calculator.py
    └── validation.py
```

`calculator.py` can contain calculation logic, while `validation.py` handles validation.

```python
from utilities.calculator import add

print(add(10, 20))
```

[View more details →](./Python_Detaild/package_organization.md)

---

## Virtual Environments

A **virtual environment** is an isolated Python environment that has its own Python interpreter and installed packages. It allows each project to manage its dependencies separately.

### Key Concepts

* **Virtual environment** — An isolated environment for a Python project.
* **`venv`** — Python's built-in module for creating virtual environments.
* **`.venv`** — A common name for the virtual-environment directory.
* **Create environment** — Use `python -m venv .venv`.
* **Activate** — Activate the environment before working on the project.
* **Deactivate** — Use `deactivate` to leave the environment.
* **`pip`** — Installs and manages Python packages.
* **Dependencies** — External packages required by a project.
* **`requirements.txt`** — Stores project dependencies and their versions.
* **Isolation** — Different projects can use different package versions.

### Example

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it on Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

Install a package:

```bash
python -m pip install requests
```

Deactivate it:

```bash
deactivate
```

[View more details →](./Python_Detaild/virtual_environments.md)

---

## Dependency Management

**Dependency management** is the process of managing the external packages and libraries that a Python project needs to run correctly.

### Key Concepts

* **Dependency** — A package or library required by a project.
* **`pip`** — Tool used to install and manage Python packages.
* **Virtual environment** — Isolates project dependencies.
* **`requirements.txt`** — Records project dependencies and versions.
* **Package version** — Identifies a specific release of a package.
* **Install** — Add a dependency to the environment.
* **Upgrade** — Update a dependency to a newer version.
* **Uninstall** — Remove an installed dependency.
* **Freeze** — Record installed packages and their versions.
* **Reproducibility** — Allows the same project environment to be recreated.
* **Dependency conflicts** — Occur when different packages require incompatible versions.

### Example

Install a package:

```bash id="8q5j0h"
python -m pip install requests
```

Save installed dependencies:

```bash id="x8y0wc"
python -m pip freeze > requirements.txt
```

Install them later:

```bash id="z9r4qf"
python -m pip install -r requirements.txt
```

This allows the project's required packages to be recreated in another environment.

[View more details →](./Python_Detaild/dependency_management.md)

---

