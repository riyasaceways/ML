[◀Back](.././)
---


# Virtual Environments

## What Is a Virtual Environment?

A **virtual environment** is an isolated Python environment created for a specific project.

It allows a project to have its own:

* Python environment
* Installed packages
* Package versions
* Dependencies

Without virtual environments, different projects may interfere with each other by requiring different versions of the same package.

---

# 1. Why Use Virtual Environments?

Consider two projects:

```text
Project A → requests 2.x
Project B → requests 3.x
```

If both projects use the same global Python environment, installing or changing packages for one project can affect the other.

A virtual environment separates them:

```text
Project A
└── .venv
    └── its packages


Project B
└── .venv
    └── its packages
```

Each project can manage its dependencies independently.

---

# 2. What Is `venv`?

Python provides the built-in `venv` module for creating virtual environments.

The basic command is:

```bash
python -m venv .venv
```

Here:

* `python` → runs Python.
* `-m` → tells Python to run a module as a script.
* `venv` → Python's built-in virtual-environment module.
* `.venv` → name of the directory where the environment is created.

---

# 3. Creating a Virtual Environment

Suppose the project is:

```text
pythonStudy/
```

Open a terminal inside the project directory:

```bash
cd pythonStudy
```

Then create the environment:

```bash
python -m venv .venv
```

The project may now look like:

```text
pythonStudy/
│
├── .venv/
└── main.py
```

The `.venv` directory contains the virtual environment.

---

# 4. Why Is `.venv` Commonly Used?

`.venv` is a common convention for naming a project's virtual environment.

Example:

```text
project/
├── .venv/
├── main.py
└── requirements.txt
```

The name can technically be different:

```bash
python -m venv my_environment
```

but `.venv` is widely used because it clearly indicates that the directory contains a virtual environment.

---

# 5. Activating a Virtual Environment

Creating a virtual environment does not automatically activate it.

You normally activate it before installing packages or running project commands.

---

# 6. Windows PowerShell

Activate the environment using:

```powershell
.venv\Scripts\Activate.ps1
```

After activation, the terminal usually shows the environment name:

```text
(.venv) PS C:\Users\Riyas\pythonStudy>
```

The `(.venv)` indicates that the virtual environment is active.

---

# 7. Windows Command Prompt

For Command Prompt (`cmd`), use:

```cmd
.venv\Scripts\activate.bat
```

After activation:

```text
(.venv) C:\Users\Riyas\pythonStudy>
```

---

# 8. macOS and Linux

Use:

```bash
source .venv/bin/activate
```

After activation:

```text
(.venv) user@computer:~/project$
```

---

# 9. Deactivating the Environment

When finished working with the environment:

```bash
deactivate
```

The `(.venv)` indicator disappears from the terminal.

---

# 10. Installing Packages

Once the virtual environment is active, packages can be installed using `pip`.

Example:

```bash
python -m pip install requests
```

The package is installed into the active environment rather than the global environment.

---

# 11. What Is `pip`?

`pip` is Python's package installer.

It is commonly used to:

* Install packages.
* Upgrade packages.
* Uninstall packages.
* View installed packages.
* Manage project dependencies.

Example:

```bash
python -m pip install requests
```

---

# 12. Why Use `python -m pip`?

You may also see:

```bash
pip install requests
```

Using:

```bash
python -m pip install requests
```

explicitly runs `pip` through the selected Python interpreter.

This can help ensure that the package is installed into the environment associated with that Python interpreter.

For learning and troubleshooting, this form is often clearer.

---

# 13. Checking the Python Version

You can check Python with:

```bash
python --version
```

Example:

```text
Python 3.x.x
```

On systems where `python` is not the Python command, you may use:

```bash
py --version
```

---

# 14. Checking Whether the Environment Is Active

One simple indication is the terminal prompt:

```text
(.venv)
```

You can also check which Python executable is being used.

On Windows:

```powershell
where python
```

On macOS/Linux:

```bash
which python
```

When the environment is active, the path should point to the virtual environment's Python executable.

---

# 15. Installing a Package

Example:

```bash
python -m pip install requests
```

After installation, Python code can use it:

```python
import requests
```

The package is available inside that virtual environment.

---

# 16. Listing Installed Packages

Use:

```bash
python -m pip list
```

This displays packages installed in the current environment.

Example:

```text
Package    Version
---------- -------
pip        ...
requests   ...
```

The exact versions depend on the environment.

---

# 17. Checking Package Information

Use:

```bash
python -m pip show requests
```

This can display information such as:

* Package name
* Version
* Installation location
* Dependencies

---

# 18. Uninstalling a Package

To remove a package:

```bash
python -m pip uninstall requests
```

`pip` will normally ask for confirmation.

---

# 19. Upgrading a Package

To upgrade a package:

```bash
python -m pip install --upgrade requests
```

---

# 20. Requirements Files

A project can store its dependencies in:

```text
requirements.txt
```

For example:

```text
requests
```

Or with versions:

```text
requests==2.32.0
```

The exact versions should match the project's requirements.

---

# 21. Creating `requirements.txt`

You can export the installed packages from the current environment:

```bash
python -m pip freeze > requirements.txt
```

This creates:

```text
requirements.txt
```

containing installed package versions.

---

# 22. Installing from `requirements.txt`

Another developer can install the project's dependencies with:

```bash
python -m pip install -r requirements.txt
```

This is useful when sharing a project through Git or another source-control system.

---

# 23. Example Project Structure

A typical Python project may look like:

```text
my_project/
│
├── .venv/
├── main.py
├── requirements.txt
└── README.md
```

The roles are:

```text
.venv/
    → project-specific virtual environment

main.py
    → program code

requirements.txt
    → project dependencies

README.md
    → project documentation
```

---

# 24. Should `.venv` Be Committed to Git?

Usually, **no**.

The virtual environment contains installed files that can be recreated.

Instead, commit:

```text
requirements.txt
```

and add:

```text
.venv/
```

to `.gitignore`.

Example `.gitignore`:

```gitignore
.venv/
```

Then other developers can recreate the environment.

---

# 25. Recreating an Environment

Suppose someone clones your project.

They can create a new environment:

```bash
python -m venv .venv
```

Activate it.

Then install the project's dependencies:

```bash
python -m pip install -r requirements.txt
```

The environment is recreated without committing the original `.venv` directory.

---

# 26. Virtual Environment Workflow

A common workflow is:

### Step 1 — Create project

```bash
mkdir my_project
cd my_project
```

### Step 2 — Create environment

```bash
python -m venv .venv
```

### Step 3 — Activate it

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

### Step 4 — Upgrade/install packages

```bash
python -m pip install --upgrade pip
```

### Step 5 — Install required packages

```bash
python -m pip install requests
```

### Step 6 — Work on the project

```bash
python main.py
```

### Step 7 — Save dependencies

```bash
python -m pip freeze > requirements.txt
```

### Step 8 — Deactivate when finished

```bash
deactivate
```

---

# 27. Running Python Inside the Environment

After activation:

```bash
python main.py
```

uses the Python interpreter associated with the active environment.

This is important because the environment may have packages that are not installed globally.

---

# 28. What Happens Without Activation?

You can have a virtual environment without activating it.

Activation mainly changes the shell environment so commands such as:

```bash
python
pip
```

refer to the virtual environment.

Without activation, you may accidentally use the system/global Python environment.

---

# 29. Using the Environment Without Activation

You can directly run the environment's Python executable.

On Windows:

```powershell
.venv\Scripts\python.exe main.py
```

On macOS/Linux:

```bash
.venv/bin/python main.py
```

This can be useful in scripts or automation.

---

# 30. Virtual Environment and Global Python

Think of them as separate environments.

```text
Global Python
│
├── Package A
├── Package B
└── Package C


Project A
└── .venv
    ├── Package A
    └── Package X


Project B
└── .venv
    ├── Package B
    └── Package Y
```

Installing a package inside Project A's environment does not normally install it into Project B's environment.

---

# 31. Virtual Environment Does Not Mean a Separate Python Installation

A `venv` environment is isolated for a project, but it is not a completely independent operating system or machine.

It uses a Python installation to create an environment with its own project-specific interpreter setup and installed packages.

The exact implementation details vary by operating system.

---

# 32. Common Windows PowerShell Problem

You may encounter an error such as:

```text
running scripts is disabled on this system
```

when running:

```powershell
.venv\Scripts\Activate.ps1
```

This is related to PowerShell's **execution policy**.

It does not necessarily mean that the virtual environment itself is broken.

An alternative is to use Command Prompt:

```cmd
.venv\Scripts\activate.bat
```

or use an appropriate PowerShell execution-policy configuration for your system.

---

# 33. Virtual Environment and VS Code

Editors such as VS Code can detect virtual environments.

A project may contain:

```text
my_project/
└── .venv/
```

The Python interpreter should be selected from that environment.

This ensures that:

* Code runs with the intended Python interpreter.
* Installed packages are recognized.
* Imports are resolved correctly.
* The project's environment is used for execution.

---

# 34. Common Mistakes

### Mistake 1: Installing packages globally

You may accidentally run:

```bash
pip install package
```

outside the project environment.

Check that the environment is active:

```text
(.venv)
```

before installing project dependencies.

---

### Mistake 2: Forgetting to activate the environment

You create:

```bash
python -m venv .venv
```

but immediately run commands using the global Python environment.

Remember to activate it when working interactively.

---

### Mistake 3: Committing `.venv`

Avoid committing the entire virtual environment to Git.

Use:

```gitignore
.venv/
```

instead.

---

### Mistake 4: Forgetting `requirements.txt`

If a project depends on external packages, document those dependencies.

```bash
python -m pip freeze > requirements.txt
```

---

### Mistake 5: Using the wrong Python interpreter

Your terminal, editor, and project may accidentally use different Python installations.

Check:

```bash
python --version
```

and the Python path.

---

# 35. Virtual Environment vs Global Environment

| Feature                        | Global Environment | Virtual Environment |
| ------------------------------ | ------------------ | ------------------- |
| Scope                          | System/user        | Project             |
| Package isolation              | No                 | Yes                 |
| Different versions per project | Difficult          | Easy                |
| Project-specific dependencies  | Not ideal          | Yes                 |
| Recommended for projects       | Usually no         | Yes                 |

---

# 36. Complete Example

Create a project:

```text
student_app/
```

Enter it:

```bash
cd student_app
```

Create the environment:

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

Create:

```text
student_app/
├── .venv/
├── main.py
└── requirements.txt
```

Create the requirements file:

```bash
python -m pip freeze > requirements.txt
```

Then run:

```bash
python main.py
```

When finished:

```bash
deactivate
```

---

# 37. Recreating the Same Project on Another Computer

Given:

```text
student_app/
├── main.py
└── requirements.txt
```

A new developer can run:

```bash
python -m venv .venv
```

Activate the environment.

Then:

```bash
python -m pip install -r requirements.txt
```

Now the project dependencies are installed into the new environment.

---

# 38. Important Commands

### Create

```bash
python -m venv .venv
```

### Activate — Windows PowerShell

```powershell
.venv\Scripts\Activate.ps1
```

### Activate — Windows CMD

```cmd
.venv\Scripts\activate.bat
```

### Activate — macOS/Linux

```bash
source .venv/bin/activate
```

### Deactivate

```bash
deactivate
```

### Install package

```bash
python -m pip install package_name
```

### Uninstall package

```bash
python -m pip uninstall package_name
```

### List packages

```bash
python -m pip list
```

### Save dependencies

```bash
python -m pip freeze > requirements.txt
```

### Install dependencies

```bash
python -m pip install -r requirements.txt
```

---

# Quick Reference

| Command                                     | Purpose                              |
| ------------------------------------------- | ------------------------------------ |
| `python -m venv .venv`                      | Create a virtual environment         |
| `.venv\Scripts\Activate.ps1`                | Activate on PowerShell               |
| `.venv\Scripts\activate.bat`                | Activate on Windows CMD              |
| `source .venv/bin/activate`                 | Activate on macOS/Linux              |
| `deactivate`                                | Leave the environment                |
| `python -m pip install package`             | Install a package                    |
| `python -m pip uninstall package`           | Remove a package                     |
| `python -m pip list`                        | List installed packages              |
| `python -m pip show package`                | Show package information             |
| `python -m pip freeze`                      | Show installed packages and versions |
| `python -m pip freeze > requirements.txt`   | Save dependencies                    |
| `python -m pip install -r requirements.txt` | Install saved dependencies           |

---

# Key Points

1. A virtual environment isolates project dependencies.
2. Python provides the `venv` module for creating virtual environments.
3. `python -m venv .venv` creates a common `.venv` environment.
4. Creating an environment does not automatically activate it.
5. Activate the environment before working interactively with project packages.
6. `pip` is used to install and manage packages.
7. `python -m pip` explicitly runs `pip` through the selected Python interpreter.
8. `requirements.txt` can record project dependencies.
9. `.venv/` should normally be excluded from Git.
10. A new environment can be recreated from `requirements.txt`.
11. Virtual environments prevent projects from unnecessarily interfering with each other's dependencies.
12. Always verify which Python interpreter and environment your project is using.

---

# Interview Questions

### 1. What is a virtual environment?

A virtual environment is an isolated Python environment used to manage dependencies separately for a project.

### 2. Why are virtual environments important?

They prevent dependency conflicts between different Python projects.

### 3. How do you create a virtual environment?

```bash
python -m venv .venv
```

### 4. What is `venv`?

`venv` is Python's built-in module for creating virtual environments.

### 5. What does `-m` mean in `python -m venv .venv`?

`-m` tells Python to run a module as a script.

### 6. How do you activate a virtual environment in Windows PowerShell?

```powershell
.venv\Scripts\Activate.ps1
```

### 7. How do you deactivate a virtual environment?

```bash
deactivate
```

### 8. What is `pip`?

`pip` is Python's package installer and package-management tool.

### 9. Why shouldn't `.venv` normally be committed to Git?

A virtual environment contains generated environment files and installed packages that can be recreated. The project's dependencies should normally be shared instead.

### 10. What is `requirements.txt`?

It is a text file commonly used to record Python package dependencies and their versions.

### 11. How do you install dependencies from `requirements.txt`?

```bash
python -m pip install -r requirements.txt
```

### 12. What is the difference between a global environment and a virtual environment?

A global environment is shared more broadly by the system/user, while a virtual environment provides an isolated environment for a specific project.


---

[◀Back](.././)
---