[◀Back](.././)
---

# Dependency Management

## What Is Dependency Management?

**Dependency management** is the process of identifying, installing, updating, tracking, and maintaining the packages that a Python project depends on.

For example, a program may contain:

```python id="2j6d2w"
import requests
```

The `requests` package is a dependency of that program if it is not part of Python's standard library.

A project may depend on several packages:

```text id="6u2t9d"
Project
│
├── requests
├── flask
├── pandas
└── ...
```

Managing these dependencies properly is important for keeping a project reliable and reproducible.

---

# 1. What Is a Dependency?

A **dependency** is something a program needs in order to work.

For example:

```python id="0h7n9s"
import requests
```

The program depends on the `requests` package.

A project can have:

* Direct dependencies
* Dependencies of those dependencies
* Different required versions

---

# 2. Why Is Dependency Management Important?

Without dependency management, a project can become difficult to set up and maintain.

Problems can include:

* Missing packages.
* Incorrect package versions.
* Conflicting dependencies.
* Different environments producing different results.
* Difficulty reproducing a project on another computer.
* Unexpected breakage after package updates.

Good dependency management makes the project easier to install, share, and maintain.

---

# 3. `pip`

`pip` is Python's commonly used package installer.

It can be used to:

* Install packages.
* Uninstall packages.
* Upgrade packages.
* List installed packages.
* Show package information.

Example:

```bash id="wglbci"
python -m pip install requests
```

---

# 4. Why Use `python -m pip`?

You may see:

```bash id="6z3e2c"
pip install requests
```

You can also use:

```bash id="mm4j94"
python -m pip install requests
```

The second form explicitly runs `pip` through the selected Python interpreter.

This is useful when multiple Python installations or environments exist.

---

# 5. Virtual Environments and Dependencies

Dependencies should normally be installed inside a project's virtual environment.

Example:

```text id="1tq8p4"
my_project/
│
├── .venv/
├── main.py
└── requirements.txt
```

Activate the environment and install the required packages.

```bash id="8fcb2w"
python -m pip install requests
```

The dependency is then available to that project's environment.

---

# 6. Installing a Dependency

Basic syntax:

```bash id="1k2t9s"
python -m pip install package_name
```

Example:

```bash id="9m3r2c"
python -m pip install requests
```

Multiple packages can also be installed:

```bash id="1l7lqn"
python -m pip install requests flask
```

---

# 7. Installing a Specific Version

A project may require a particular version.

```bash id="5x4y9e"
python -m pip install requests==2.32.0
```

The `==` operator specifies an exact version.

For example:

```text id="9fh5cz"
requests==2.32.0
```

means that version `2.32.0` is required.

---

# 8. Version Specifiers

Python package requirements can use different version constraints.

Examples:

```text id="7k0j6a"
requests==2.32.0
```

Exact version.

```text id="4z6x6r"
requests>=2.32.0
```

Version `2.32.0` or newer.

```text id="x4b3bq"
requests<3.0
```

Any version below `3.0`.

```text id="5u0c7g"
requests>=2.30,<3.0
```

A version within a specified range.

Version constraints help control which package versions can be used.

---

# 9. Checking Installed Packages

Use:

```bash id="4x2b7k"
python -m pip list
```

This shows packages installed in the current environment.

Example:

```text id="rx3h2a"
Package    Version
---------- -------
pip        ...
requests   ...
```

The actual versions depend on the environment.

---

# 10. Getting Package Information

Use:

```bash id="3d0v1s"
python -m pip show requests
```

This can provide information such as:

* Package name.
* Version.
* Installation location.
* Dependencies.
* Package metadata.

---

# 11. Upgrading a Dependency

To upgrade a package:

```bash id="q8m9c0"
python -m pip install --upgrade requests
```

This asks `pip` to install a newer compatible release according to the command's constraints and package availability.

---

# 12. Uninstalling a Dependency

To remove a package:

```bash id="6j2n7a"
python -m pip uninstall requests
```

`pip` normally asks for confirmation before removing it.

---

# 13. What Is `requirements.txt`?

`requirements.txt` is a commonly used text file for recording a project's Python dependencies.

Example:

```text id="3s5x7w"
requests
flask
```

Versions can also be specified:

```text id="t5n8q2"
requests==2.32.0
flask==3.0.0
```

This gives other developers a way to install the project's dependencies.

---

# 14. Creating `requirements.txt`

One common method is:

```bash id="f3v6z2"
python -m pip freeze > requirements.txt
```

This writes installed packages and their versions into the file.

Example:

```text id="0s7d4q"
requests==2.32.0
urllib3==2.2.1
...
```

The exact contents depend on what is installed in the environment.

---

# 15. What Does `pip freeze` Do?

```bash id="j4w2h6"
python -m pip freeze
```

lists installed packages in a format suitable for requirements files.

For example:

```text id="n5c7w1"
requests==2.32.0
```

Redirecting the output:

```bash id="9k5j1p"
python -m pip freeze > requirements.txt
```

stores that information in a file.

---

# 16. Installing from `requirements.txt`

Another developer can create a virtual environment and install the dependencies with:

```bash id="2m7p5s"
python -m pip install -r requirements.txt
```

The `-r` option tells `pip` to read requirements from a file.

---

# 17. Reproducing a Project Environment

Suppose a project contains:

```text id="3x0k9z"
my_project/
├── main.py
└── requirements.txt
```

On another computer:

### Create environment

```bash id="6g4n2v"
python -m venv .venv
```

### Activate it

Then activate `.venv`.

### Install dependencies

```bash id="n7r4k1"
python -m pip install -r requirements.txt
```

Now the required packages can be installed into the new environment.

---

# 18. Dependency Isolation

Imagine two projects:

```text id="q5x8m3"
Project A
└── .venv
    └── Package X version 1


Project B
└── .venv
    └── Package X version 2
```

The projects can use different dependency versions without requiring one shared global package installation.

This is one of the main reasons virtual environments are important.

---

# 19. Dependency Conflicts

A dependency conflict can occur when packages require incompatible versions.

For example:

```text id="2c8n5v"
Package A → requires Library X < 2.0

Package B → requires Library X >= 3.0
```

Both requirements cannot be satisfied by the same version of Library X.

Dependency management tools attempt to detect and resolve such conflicts, but some combinations may still be impossible.

---

# 20. Direct and Transitive Dependencies

### Direct dependency

A package that your project explicitly uses.

Example:

```python id="7y3m2n"
import requests
```

If your project installs `requests`, it is a direct dependency.

### Transitive dependency

A package required by another package.

For example:

```text id="v2n5x6"
Your project
    ↓
requests
    ↓
urllib3
```

Your project may not directly import `urllib3`, but `requests` may depend on it.

---

# 21. Why Dependency Versions Matter

Suppose your code was developed with:

```text id="p5d8q1"
package X 1.5
```

A newer release might:

* Change behavior.
* Remove functionality.
* Change APIs.
* Introduce bugs.
* Require a different Python version.

Recording versions can make the environment more predictable.

---

# 22. Updating Dependencies Carefully

Updating all dependencies blindly can introduce compatibility problems.

A safer workflow is:

1. Check the current versions.
2. Review available updates.
3. Update intentionally.
4. Run the project's tests.
5. Check the application.
6. Update the dependency record if necessary.

Dependency updates should be treated as changes to the project, not merely routine commands.

---

# 23. `requirements.txt` and Git

A typical project might contain:

```text id="r7q9v2"
my_project/
├── .venv/
├── main.py
├── requirements.txt
├── .gitignore
└── README.md
```

Git should normally track:

```text id="k3x1p6"
main.py
requirements.txt
.gitignore
README.md
```

and ignore:

```text id="q2m6s8"
.venv/
```

Example `.gitignore`:

```gitignore id="5n7c3x"
.venv/
```

---

# 24. Dependency Management Workflow

A practical workflow is:

### Step 1 — Create a project

```bash id="j3f8x1"
mkdir my_project
cd my_project
```

### Step 2 — Create a virtual environment

```bash id="0v6n4s"
python -m venv .venv
```

### Step 3 — Activate it

Activate `.venv`.

### Step 4 — Install dependencies

```bash id="p8r1m5"
python -m pip install requests
```

### Step 5 — Develop and test

```bash id="u4m7x2"
python main.py
```

### Step 6 — Record dependencies

```bash id="7n2c9w"
python -m pip freeze > requirements.txt
```

### Step 7 — Commit the dependency file

Add `requirements.txt` to version control.

---

# 25. Dependency Management for Team Projects

Suppose several developers work on the same project.

Without a dependency file:

```text id="j1m5x8"
Developer A → Package X installed
Developer B → Package X missing
Developer C → Different Package X version
```

With a dependency file:

```text id="x8v2m6"
requirements.txt
       ↓
all developers install
       ↓
project dependencies
```

This helps keep development environments consistent.

---

# 26. Development vs Production Dependencies

Some projects have packages needed only during development.

For example:

```text id="n4s7c2"
Application
    → requests

Development
    → pytest
```

`requests` may be required to run the application, while `pytest` may only be needed to run tests.

Larger Python projects often use more specialized dependency-management tools or separate dependency groups for handling this distinction.

---

# 27. Dependency Management Tools

`pip` and `requirements.txt` are common and useful for many Python projects.

Larger projects may also use tools such as:

* `pip-tools`
* Poetry
* Pipenv
* uv

These tools can provide additional dependency resolution, locking, project metadata, or environment-management features.

For basic Python projects, understanding:

```text id="e4j8m0"
venv
pip
requirements.txt
```

provides a strong foundation.

---

# 28. Dependency Locking

A dependency record can specify exact versions:

```text id="u8y1r6"
requests==2.32.0
```

This makes the requested environment more predictable than simply writing:

```text id="g5p3z9"
requests
```

Modern dependency-management tools can also generate **lock files** containing resolved versions for direct and transitive dependencies.

---

# 29. Reproducibility

**Reproducibility** means being able to recreate an environment with the required dependencies.

For example:

```text id="a2n7c4"
Source Code
     +
Dependency Information
     ↓
New Virtual Environment
     ↓
Reproducible Setup
```

This is particularly important when:

* Sharing projects.
* Working in teams.
* Deploying applications.
* Running automated tests.
* Moving to another computer.

---

# 30. Dependency Management and Security

Dependencies can contain security vulnerabilities.

Therefore, dependency management also involves:

* Keeping dependencies reasonably up to date.
* Reviewing important updates.
* Removing unused dependencies.
* Checking dependencies for known vulnerabilities.
* Avoiding unnecessary packages.

Do not install a package simply because it appears convenient if the functionality can easily be implemented safely with Python's standard library.

---

# 31. Avoid Unnecessary Dependencies

Suppose you need a simple calculation.

You do not necessarily need an external package for:

```python id="8j3x4k"
total = price * quantity
```

Adding unnecessary dependencies can:

* Increase project complexity.
* Increase installation time.
* Increase potential compatibility problems.
* Increase maintenance requirements.

Use dependencies when they provide meaningful functionality.

---

# 32. Common Mistakes

### Mistake 1: Installing packages globally

Installing everything into the global Python environment can cause projects to interfere with each other.

Use a virtual environment for project dependencies.

---

### Mistake 2: Forgetting `requirements.txt`

A project that depends on external packages should document those dependencies appropriately.

---

### Mistake 3: Committing `.venv`

Do not normally commit the entire virtual environment.

Use:

```gitignore id="0d3m7q"
.venv/
```

---

### Mistake 4: Updating packages without testing

A new package version can change behavior.

Test the project after important dependency updates.

---

### Mistake 5: Using unbounded dependencies unnecessarily

This:

```text id="2w8k4p"
requests
```

does not record a specific version.

For projects where reproducibility matters, an appropriate version constraint or lock mechanism can be useful.

---

### Mistake 6: Installing unnecessary packages

Every dependency adds maintenance and compatibility considerations.

Keep the dependency list as focused as practical.

---

# 33. Recommended Basic Project Structure

```text id="x6k3q8"
my_project/
│
├── .venv/
├── main.py
├── requirements.txt
├── .gitignore
└── README.md
```

`.gitignore`:

```gitignore id="b8w5c2"
.venv/
```

`requirements.txt`:

```text id="p1n7x4"
requests==2.32.0
```

The exact dependency and version should match the project's actual requirements.

---

# 34. Dependency Management Checklist

Before sharing a Python project:

* [ ] Is a virtual environment used?
* [ ] Are required external packages identified?
* [ ] Are dependency versions appropriately constrained?
* [ ] Is `requirements.txt` updated when applicable?
* [ ] Is `.venv/` excluded from Git?
* [ ] Can another developer recreate the environment?
* [ ] Have dependency updates been tested?
* [ ] Are unnecessary dependencies removed?
* [ ] Are important security updates considered?

---

# Quick Reference

| Command / Concept                           | Purpose                                      |
| ------------------------------------------- | -------------------------------------------- |
| `python -m pip install package`             | Install a package                            |
| `python -m pip uninstall package`           | Remove a package                             |
| `python -m pip list`                        | List installed packages                      |
| `python -m pip show package`                | Show package information                     |
| `python -m pip install --upgrade package`   | Upgrade a package                            |
| `python -m pip freeze`                      | List installed packages with versions        |
| `python -m pip freeze > requirements.txt`   | Save dependencies                            |
| `python -m pip install -r requirements.txt` | Install dependencies from a file             |
| `requirements.txt`                          | Common dependency record                     |
| `.venv/`                                    | Project virtual environment                  |
| Direct dependency                           | Package directly required by your project    |
| Transitive dependency                       | Dependency required by another dependency    |
| Version constraint                          | Controls acceptable package versions         |
| Dependency conflict                         | Incompatible dependency requirements         |
| Reproducibility                             | Ability to recreate the required environment |

---

# Key Points

1. Dependency management is the process of managing packages required by a project.
2. Dependencies can be installed and managed using `pip`.
3. Virtual environments isolate dependencies between projects.
4. `python -m pip` explicitly uses the selected Python interpreter to run `pip`.
5. `requirements.txt` is a common way to record project dependencies.
6. `pip freeze` can generate a list of installed packages and versions.
7. Dependencies can be specified with version constraints.
8. Direct dependencies are used directly by your project.
9. Transitive dependencies are required by other dependencies.
10. Dependency conflicts can occur when packages require incompatible versions.
11. Dependency updates should be tested before being adopted.
12. `.venv/` should normally not be committed to Git.
13. Good dependency management improves reproducibility and maintainability.
14. Avoid unnecessary dependencies.
15. Larger projects may use specialized tools such as Poetry, Pipenv, `pip-tools`, or `uv`.

---

# Interview Questions

### 1. What is dependency management?

Dependency management is the process of installing, tracking, updating, and maintaining the packages required by a software project.

### 2. What is a dependency?

A dependency is a package or library that a project requires to perform its functionality.

### 3. What is `pip`?

`pip` is Python's commonly used package installer and package-management tool.

### 4. Why use a virtual environment for dependencies?

It isolates project dependencies so that different projects can use different package versions without unnecessarily interfering with each other.

### 5. What is `requirements.txt`?

It is a commonly used text file that records Python packages required by a project, often including their versions.

### 6. What does `pip freeze` do?

It displays installed packages and their versions in a format that can be used to create a requirements file.

### 7. What does this command do?

```bash id="8m4q2v"
python -m pip install -r requirements.txt
```

It installs the dependencies listed in `requirements.txt`.

### 8. What is a dependency conflict?

A dependency conflict occurs when two or more packages require incompatible versions of the same dependency.

### 9. What is a transitive dependency?

A transitive dependency is a package required by another package that the project depends on.

### 10. Why shouldn't `.venv` normally be committed to Git?

The virtual environment can be recreated from dependency information, while committing the environment itself adds unnecessary generated files and platform-specific content.

### 11. Why are package versions important?

Different versions can have different APIs, behavior, or compatibility requirements, so controlling versions can make a project more predictable.

### 12. What is reproducibility in dependency management?

Reproducibility is the ability to recreate a project environment with the required dependencies and compatible versions.


---

[◀Back](.././)
---