[◀Back](.././)
---


# Importing Modules

## What Is a Module?

A **module** is a Python file containing code that can be reused in another Python program.

A module can contain:

* Variables
* Functions
* Classes
* Constants
* Other Python code

For example, Python provides a standard library module called `math`.

```python
import math

print(math.sqrt(25))
```

Here:

* `math` is the module.
* `sqrt()` is a function inside the module.
* `math.sqrt(25)` calls that function.

---

## Why Use Modules?

Modules help us:

* Reuse code.
* Organize large programs.
* Avoid repeating code.
* Keep related functionality together.
* Make programs easier to maintain.
* Use functionality already provided by Python.

Instead of writing the same functionality repeatedly, we can place it in a module and import it whenever needed.

---

# 1. Using `import`

The basic syntax is:

```python
import module_name
```

Example:

```python
import math
```

After importing the module, access its members using the module name:

```python
import math

print(math.sqrt(16))
print(math.pi)
```

The dot `.` is used to access something inside the module.

---

# 2. Importing Multiple Modules

Multiple modules can be imported.

```python
import math
import random
import datetime
```

Each module can then be used through its own name.

```python
import math
import random

print(math.sqrt(100))
print(random.randint(1, 10))
```

---

# 3. Importing a Specific Item

Instead of importing the whole module, a specific function or variable can be imported.

Syntax:

```python
from module_name import item_name
```

Example:

```python
from math import sqrt

print(sqrt(25))
```

Here, `sqrt` can be used directly without writing `math.sqrt()`.

---

# 4. Importing Multiple Items

Multiple items can be imported from the same module.

```python
from math import sqrt, pi

print(sqrt(25))
print(pi)
```

This can be useful when only a few items from a module are required.

---

# 5. Importing Everything

Python also allows:

```python
from math import *
```

This imports names from the module into the current namespace.

However, this style is generally discouraged because it can:

* Make it difficult to know where a name came from.
* Cause naming conflicts.
* Make code less readable.

Prefer:

```python
import math

print(math.sqrt(25))
```

or:

```python
from math import sqrt

print(sqrt(25))
```

---

# 6. Using an Alias

An **alias** gives an imported module another name.

Syntax:

```python
import module_name as alias
```

Example:

```python
import math as m

print(m.sqrt(25))
```

Here:

```text
math → m
```

The alias can make frequently used modules shorter to reference.

---

# 7. Alias with `from ... import`

Aliases can also be used for individual items.

```python
from math import sqrt as square_root

print(square_root(25))
```

Here, `sqrt` is available under the name `square_root`.

---

# 8. Standard Library Modules

Python includes a large **standard library** containing many modules.

Examples:

| Module       | Common Purpose                          |
| ------------ | --------------------------------------- |
| `math`       | Mathematical operations                 |
| `random`     | Random values and selections            |
| `datetime`   | Dates and times                         |
| `os`         | Operating-system functionality          |
| `sys`        | Python interpreter/system functionality |
| `json`       | JSON data                               |
| `csv`        | CSV files                               |
| `pathlib`    | File-system paths                       |
| `statistics` | Statistical calculations                |

Example:

```python
import random

number = random.randint(1, 100)

print(number)
```

---

# 9. The `math` Module

The `math` module provides mathematical functions and constants.

```python
import math

print(math.sqrt(49))
print(math.pi)
print(math.ceil(4.2))
print(math.floor(4.8))
```

---

# 10. The `random` Module

The `random` module provides tools for generating pseudo-random values.

```python
import random

number = random.randint(1, 10)

print(number)
```

Another example:

```python
import random

colors = ["red", "green", "blue"]

print(random.choice(colors))
```

---

# 11. The `datetime` Module

The `datetime` module provides functionality for working with dates and times.

```python
import datetime

today = datetime.date.today()

print(today)
```

---

# 12. Importing User-Defined Modules

A programmer can create their own modules.

Suppose we have:

```text
project/
│
├── main.py
└── calculator.py
```

### `calculator.py`

```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b
```

### `main.py`

```python
import calculator

print(calculator.add(10, 5))
print(calculator.subtract(10, 5))
```

The file `calculator.py` becomes a module that can be imported into `main.py`.

---

# 13. Importing Specific Functions from a User Module

Instead of:

```python
import calculator

print(calculator.add(10, 5))
```

we can write:

```python
from calculator import add

print(add(10, 5))
```

Multiple functions can also be imported:

```python
from calculator import add, subtract

print(add(10, 5))
print(subtract(10, 5))
```

---

# 14. Module Namespace

When using:

```python
import math
```

the functions and variables from `math` remain associated with the `math` namespace.

For example:

```python
import math

print(math.pi)
print(math.sqrt(36))
```

This makes it clear that `pi` and `sqrt` come from the `math` module.

---

# 15. Why Namespaces Matter

Consider two modules that both contain a function called `calculate()`.

Using module names:

```python
import module_a
import module_b

module_a.calculate()
module_b.calculate()
```

The module name tells Python exactly which function is being used.

This helps avoid naming conflicts.

---

# 16. Module Import Styles

### Import the module

```python
import math

math.sqrt(25)
```

### Import a specific item

```python
from math import sqrt

sqrt(25)
```

### Import with an alias

```python
import math as m

m.sqrt(25)
```

### Import a specific item with an alias

```python
from math import sqrt as root

root(25)
```

---

# 17. Modules and Code Reuse

Suppose a program needs the same calculation in several places.

Instead of repeatedly writing:

```python
def add(a, b):
    return a + b
```

the function can be placed in a module.

### `calculator.py`

```python
def add(a, b):
    return a + b
```

Then other programs can reuse it:

```python
from calculator import add

print(add(10, 20))
```

This supports reusable program design.

---

# 18. Modules and Large Programs

Large programs can be divided into multiple files.

For example:

```text
project/
│
├── main.py
├── calculator.py
├── validation.py
├── file_handler.py
└── database.py
```

Each module can have a specific responsibility.

For example:

```text
calculator.py
    → calculations

validation.py
    → input validation

file_handler.py
    → file operations
```

This makes the project easier to understand and maintain.

---

# 19. Importing Your Own Module

Suppose:

### `greetings.py`

```python
def greet(name):
    return f"Hello, {name}!"
```

### `main.py`

```python
import greetings

message = greetings.greet("Riyas")

print(message)
```

Output:

```text
Hello, Riyas!
```

---

# 20. Module Search

When Python executes:

```python
import calculator
```

Python searches for the module in locations available through its module search path.

The `sys.path` list represents locations Python searches when importing modules.

```python
import sys

print(sys.path)
```

You normally do not need to modify this manually for modules located correctly within your project.

---

# 21. Import Errors

If Python cannot find a requested module, it can raise:

```text
ModuleNotFoundError
```

Example:

```python
import unknown_module
```

Python may produce:

```text
ModuleNotFoundError: No module named 'unknown_module'
```

This usually means Python could not locate the requested module.

---

# 22. Importing a Module That Does Not Exist

Incorrect:

```python
import mymodule
```

if `mymodule.py` does not exist in an importable location.

Python will raise an import-related error.

Always check:

* Module name.
* File name.
* Project structure.
* Python environment.
* Module installation, when using external packages.

---

# 23. Standard Library vs External Packages

Not every module is included with Python.

### Standard library

Usually available with Python:

```python
import math
import json
import csv
```

### External package

May need to be installed separately:

```python
import requests
```

If the package is not installed, importing it can fail.

External packages are commonly installed using `pip`.

---

# 24. Modules vs Libraries

The terms **module** and **library** are related but are not exactly the same.

A **module** is generally a single Python file containing reusable code.

A **library** is a broader collection of reusable code and may contain multiple modules and packages.

For example:

```text
library
│
├── module_a.py
├── module_b.py
└── module_c.py
```

---

# 25. Module vs Package

A **module** is typically a `.py` file.

A **package** is a way of organizing related Python modules into a directory structure.

Example:

```text
project/
│
├── main.py
│
└── utilities/
    ├── calculator.py
    └── validation.py
```

The package can contain multiple modules.

---

# 26. Importing from a Package

For example:

```python
from utilities import calculator

print(calculator.add(10, 20))
```

Or:

```python
from utilities.calculator import add

print(add(10, 20))
```

---

# 27. Module-Level Variables

A module can contain variables as well as functions.

### `student.py`

```python
student_name = "Riyas"
student_age = 25
```

Another file can import them:

```python
import student

print(student.student_name)
print(student.student_age)
```

---

# 28. Module-Level Constants

A module can also contain constants.

### `settings.py`

```python
MAX_ATTEMPTS = 3
APP_NAME = "Student App"
```

Another module can use them:

```python
import settings

print(settings.APP_NAME)
print(settings.MAX_ATTEMPTS)
```

---

# 29. Importing a Module Executes Its Top-Level Code

Consider:

### `example.py`

```python
print("Module loaded")

number = 10
```

Then:

```python
import example
```

The top-level `print()` runs during the import.

Output:

```text
Module loaded
```

Therefore, modules should generally avoid putting unwanted execution at the top level.

---

# 30. `if __name__ == "__main__"`

A common pattern is:

```python
def greet():
    print("Hello")

if __name__ == "__main__":
    greet()
```

When the file is run directly:

```text
python example.py
```

the code inside the condition runs.

When the file is imported:

```python
import example
```

that block does not run.

This allows the same file to work both as a reusable module and as a directly executed program.

---

# 31. Practical Example

### `calculator.py`

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


if __name__ == "__main__":
    print(add(10, 5))
    print(subtract(10, 5))
```

### `main.py`

```python
import calculator

print(calculator.add(100, 50))
```

The functions can be reused without automatically running the example code inside `calculator.py`.

---

# 32. Avoid Unnecessary Imports

Only import what the program needs.

Instead of importing many modules unnecessarily:

```python
import math
import random
import datetime
import csv
import json
```

use only what is required.

For example:

```python
import math

print(math.sqrt(100))
```

This keeps the code easier to understand.

---

# 33. Common Mistakes

### Mistake 1: Forgetting the import

```python
print(math.sqrt(25))
```

without:

```python
import math
```

This results in a `NameError`.

---

### Mistake 2: Using the wrong module name

```python
import maths
```

when the module is actually:

```python
import math
```

---

### Mistake 3: Confusing module and function names

```python
import math

math()
```

`math` is a module, not a function.

Correct:

```python
math.sqrt(25)
```

---

### Mistake 4: Importing everything

```python
from math import *
```

This can make code harder to understand and may create naming conflicts.

---

### Mistake 5: Naming your file after a standard module

For example, creating:

```text
random.py
```

in your project can cause confusion when trying to import Python's `random` module.

Use descriptive names that do not conflict with standard library modules.

---

# 34. Best Practices

Prefer:

```python
import math

result = math.sqrt(100)
```

when you want clear module ownership.

Use:

```python
from math import sqrt

result = sqrt(100)
```

when importing a small number of well-known items makes the code clearer.

Use aliases when they improve readability or are conventional:

```python
import datetime as dt
```

Avoid:

```python
from math import *
```

Avoid unnecessary imports.

Keep related functionality organized into modules.

---

# Quick Reference

| Syntax                          | Meaning                                       |
| ------------------------------- | --------------------------------------------- |
| `import math`                   | Import the module                             |
| `math.sqrt()`                   | Access an item through the module             |
| `from math import sqrt`         | Import a specific item                        |
| `from math import sqrt, pi`     | Import multiple items                         |
| `import math as m`              | Give the module an alias                      |
| `from math import sqrt as root` | Give an imported item an alias                |
| `from math import *`            | Import many names into the current namespace  |
| `ModuleNotFoundError`           | Module cannot be found                        |
| `__name__`                      | Special variable containing the module's name |
| `__main__`                      | Indicates the file is being run directly      |

---

# Key Points

1. A module is a Python file containing reusable code.
2. Use `import` to make a module available.
3. Use `module.item` to access something inside an imported module.
4. `from ... import ...` imports specific items.
5. `as` creates an alias.
6. Python provides many standard library modules.
7. Programmers can create their own modules.
8. Modules help organize and reuse code.
9. Packages can contain multiple related modules.
10. Avoid unnecessary wildcard imports.
11. `ModuleNotFoundError` occurs when Python cannot find an imported module.
12. `if __name__ == "__main__":` prevents certain code from running automatically when a module is imported.

---

# Interview Questions

### 1. What is a module in Python?

A module is a Python file containing reusable code such as functions, classes, and variables.

### 2. How do you import a module?

Using the `import` statement:

```python
import math
```

### 3. What is the difference between `import math` and `from math import sqrt`?

`import math` imports the module and requires `math.sqrt()`.

`from math import sqrt` imports `sqrt` directly, so it can be called as `sqrt()`.

### 4. What is an alias in Python imports?

An alias is another name given to an imported module or item.

```python
import math as m
```

### 5. What is a user-defined module?

A Python file created by a programmer that contains reusable code.

### 6. What happens if Python cannot find an imported module?

Python raises `ModuleNotFoundError`.

### 7. Why should `from module import *` generally be avoided?

It can make the source of names unclear and can cause naming conflicts.

### 8. What is the purpose of `if __name__ == "__main__":`?

It allows code to run when the file is executed directly while preventing that code from running when the file is imported as a module.

### 9. What is the difference between a module and a package?

A module is generally a single Python file, while a package organizes multiple related modules in a directory structure.

### 10. Why are modules useful?

They provide code organization, reuse, maintainability, and separation of functionality.


[◀Back](.././)
---