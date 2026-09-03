[◀Back](.././)
---


# Creating Reusable Modules

## What Is a Reusable Module?

A **reusable module** is a Python file containing code that is designed to be imported and used by other programs.

A module can contain:

* Functions
* Classes
* Variables
* Constants
* Reusable logic

For example:

```python
# calculator.py

def add(a, b):
    return a + b
```

Another program can use it:

```python
import calculator

result = calculator.add(10, 20)

print(result)
```

The calculation does not need to be rewritten in every program.

---

# 1. Why Create Reusable Modules?

Reusable modules help you:

* Avoid repeating code.
* Organize large programs.
* Separate different responsibilities.
* Make code easier to test.
* Make code easier to maintain.
* Share functionality between programs.
* Build larger applications from smaller components.

Instead of writing one huge Python file, related functionality can be separated into modules.

---

# 2. Basic Module Structure

A module is simply a Python file.

Example project:

```text
project/
│
├── main.py
└── calculator.py
```

The file:

```text
calculator.py
```

is a module.

---

# 3. Put Reusable Functions in a Module

### `calculator.py`

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


def multiply(a, b):
    return a * b
```

These functions can now be reused by another Python file.

### `main.py`

```python
import calculator

print(calculator.add(10, 5))
print(calculator.subtract(10, 5))
print(calculator.multiply(10, 5))
```

---

# 4. Use Parameters to Make Modules Flexible

A reusable function should generally avoid hard-coded values.

Less reusable:

```python
def calculate():
    return 10 + 20
```

More reusable:

```python
def calculate(a, b):
    return a + b
```

Now the same function can work with different values:

```python
print(calculate(10, 20))
print(calculate(50, 30))
print(calculate(100, 200))
```

Parameters make reusable logic flexible.

---

# 5. Return Values Instead of Only Printing

A reusable function should often **return** a result.

Less reusable:

```python
def add(a, b):
    print(a + b)
```

Better:

```python
def add(a, b):
    return a + b
```

Now the caller can decide what to do with the result:

```python
result = add(10, 20)

print(result)
```

The returned value can also be stored, calculated with, or passed to another function.

---

# 6. Avoid User Input Inside General-Purpose Functions

Consider:

```python
def add():
    a = int(input("Enter first number: "))
    b = int(input("Enter second number: "))

    return a + b
```

This function is less reusable because it always depends on user input.

A more reusable design is:

```python
def add(a, b):
    return a + b
```

The caller handles input:

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

result = add(a, b)

print(result)
```

This separates **input handling** from **calculation logic**.

---

# 7. Keep a Module Focused

A module should generally contain related functionality.

For example:

```text
calculator.py
```

could contain:

```python
def add(a, b):
    ...


def subtract(a, b):
    ...


def multiply(a, b):
    ...


def divide(a, b):
    ...
```

A separate module could handle validation:

```text
validation.py
```

```python
def is_positive(number):
    return number > 0
```

This creates a clearer project structure.

---

# 8. Single Responsibility

A good module should have a clear purpose.

For example:

```text
calculator.py
    → mathematical calculations

validation.py
    → input validation

file_handler.py
    → file operations

student.py
    → student-related operations
```

This makes it easier to find and reuse functionality.

---

# 9. Import a Reusable Module

Suppose:

### `calculator.py`

```python
def add(a, b):
    return a + b
```

Then:

### `main.py`

```python
import calculator

result = calculator.add(10, 20)

print(result)
```

The syntax:

```python
module_name.function_name()
```

accesses the function inside the module.

---

# 10. Import Specific Functions

You can import only the functions you need.

```python
from calculator import add

print(add(10, 20))
```

Multiple functions:

```python
from calculator import add, subtract

print(add(10, 20))
print(subtract(20, 5))
```

---

# 11. Use Module Aliases

A module can be given an alias.

```python
import calculator as calc

print(calc.add(10, 20))
```

The alias can make frequently used module names shorter.

---

# 12. Module-Level Constants

Reusable modules can contain constants.

### `settings.py`

```python
MAX_MARK = 100
PASS_MARK = 40
```

Another file can use them:

```python
import settings

mark = 75

if mark >= settings.PASS_MARK:
    print("Pass")
```

This avoids repeating important values throughout the project.

---

# 13. Module-Level Variables

Modules can also contain variables.

### `student.py`

```python
school_name = "ABC School"
```

Then:

```python
import student

print(student.school_name)
```

However, reusable modules should generally avoid relying heavily on mutable global state.

Functions that receive their data through parameters are usually easier to reuse.

---

# 14. Avoid Global State When Possible

Less reusable:

```python
total = 100


def add_amount(amount):
    global total
    total += amount
```

The function depends on a global variable.

More reusable:

```python
def add_amount(total, amount):
    return total + amount
```

Now the function can be used with any value.

```python
balance = add_amount(100, 50)

print(balance)
```

---

# 15. Use Docstrings

A **docstring** describes what a module, function, or class does.

Example:

```python
def calculate_area(length, width):
    """Return the area of a rectangle."""
    return length * width
```

A module can also have a module-level docstring:

```python
"""Utility functions for mathematical calculations."""
```

Docstrings make reusable code easier for other programmers to understand.

---

# 16. Create a Utility Module

Suppose several programs need the same validation functions.

### `validation.py`

```python
def is_valid_mark(mark):
    return 0 <= mark <= 100


def is_valid_age(age):
    return 0 <= age <= 120
```

Another program can reuse them:

```python
import validation

mark = 85

if validation.is_valid_mark(mark):
    print("Valid mark.")
```

Another program can use the same module:

```python
import validation

age = 25

if validation.is_valid_age(age):
    print("Valid age.")
```

The validation logic is written once.

---

# 17. Modules Can Use Other Modules

A reusable module can import another module.

### `validation.py`

```python
def is_positive(number):
    return number > 0
```

### `calculator.py`

```python
import validation


def divide(a, b):
    if not validation.is_positive(b):
        raise ValueError("Divisor must be positive.")

    return a / b
```

Modules can therefore be combined to build larger systems.

However, dependencies should be kept simple and well organized.

---

# 18. Avoid Circular Imports

A **circular import** occurs when modules depend on each other.

For example:

```text
module_a → imports module_b
module_b → imports module_a
```

This can cause import problems and make the project difficult to understand.

A better design is often to move shared functionality into a third module.

```text
module_a
     ↓
 shared
     ↑
module_b
```

---

# 19. Use `if __name__ == "__main__"`

A reusable module may contain test or demonstration code.

Example:

```python
def add(a, b):
    return a + b


if __name__ == "__main__":
    print(add(10, 20))
```

When the file is run directly:

```text
python calculator.py
```

the code inside the `if` block runs.

When the file is imported:

```python
import calculator
```

the test code does not run.

This is useful when a file is intended to be both:

* A reusable module.
* A directly executable program.

---

# 20. Keep Demonstration Code Separate

Avoid this in a reusable module:

```python
def add(a, b):
    return a + b


print(add(10, 20))
```

The `print()` executes when the module is imported.

Instead:

```python
def add(a, b):
    return a + b


if __name__ == "__main__":
    print(add(10, 20))
```

Now importing the module only makes the reusable function available.

---

# 21. Example: Student Module

### `student.py`

```python
def calculate_average(marks):
    if not marks:
        return 0

    return sum(marks) / len(marks)


def is_passed(average):
    return average >= 40
```

### `main.py`

```python
import student

marks = [70, 80, 65]

average = student.calculate_average(marks)

print(f"Average: {average}")

if student.is_passed(average):
    print("Passed")
else:
    print("Failed")
```

The student-related logic is reusable.

---

# 22. Example: File Utility Module

### `file_utils.py`

```python
def read_file(filename):
    with open(filename, "r", encoding="utf-8") as file:
        return file.read()


def write_file(filename, content):
    with open(filename, "w", encoding="utf-8") as file:
        file.write(content)
```

Another program can use these functions:

```python
import file_utils

file_utils.write_file("notes.txt", "Python is useful.")

content = file_utils.read_file("notes.txt")

print(content)
```

The file-handling logic does not need to be rewritten.

---

# 23. Reusable Modules and DRY

**DRY** means:

> Don't Repeat Yourself

If the same logic appears in several places, consider moving it into a reusable function or module.

Instead of:

```python
# program1.py
def calculate_tax(price):
    return price * 0.18
```

and:

```python
# program2.py
def calculate_tax(price):
    return price * 0.18
```

create:

```python
# tax.py
def calculate_tax(price):
    return price * 0.18
```

Then both programs can import it.

```python
from tax import calculate_tax
```

---

# 24. Reusable Modules and Testing

Small reusable functions are easier to test.

Example:

```python
def add(a, b):
    return a + b
```

A test can simply check:

```python
assert add(2, 3) == 5
assert add(10, 20) == 30
```

Because the function does not depend on `input()` or `print()`, it is easy to test.

---

# 25. Reusable Modules and Separation of Concerns

A program can separate different responsibilities.

For example:

```text
project/
│
├── main.py
├── validation.py
├── calculator.py
└── file_utils.py
```

Responsibilities:

```text
main.py
    → controls the program

validation.py
    → validates data

calculator.py
    → performs calculations

file_utils.py
    → handles files
```

Each module has a clear purpose.

---

# 26. A Good Reusable Module

A reusable module generally has:

* A clear purpose.
* Focused functions.
* Parameters instead of hard-coded values.
* Return values instead of unnecessary printing.
* Minimal global state.
* Useful docstrings.
* Clear names.
* Limited dependencies.
* No unwanted execution during import.

Example:

```python
"""Utility functions for calculating student results."""


def calculate_average(marks):
    """Return the average of a list of marks."""
    if not marks:
        return 0

    return sum(marks) / len(marks)


def is_passed(average):
    """Return True when the average is at least 40."""
    return average >= 40


if __name__ == "__main__":
    sample_marks = [70, 80, 90]

    average = calculate_average(sample_marks)

    print(f"Average: {average}")
    print(f"Passed: {is_passed(average)}")
```

---

# 27. Common Mistakes

### Mistake 1: Hard-coding values

Less reusable:

```python
def calculate():
    return 100 * 20
```

Better:

```python
def calculate(price, quantity):
    return price * quantity
```

---

### Mistake 2: Depending on user input

Less reusable:

```python
def calculate():
    number = int(input("Enter number: "))
    return number * 2
```

Better:

```python
def calculate(number):
    return number * 2
```

---

### Mistake 3: Printing instead of returning

Less reusable:

```python
def add(a, b):
    print(a + b)
```

Better:

```python
def add(a, b):
    return a + b
```

---

### Mistake 4: Too many responsibilities

Avoid creating one module that handles:

```text
calculations
files
database
user interface
validation
networking
```

Separate related responsibilities into appropriate modules.

---

### Mistake 5: Unwanted code execution during import

Avoid:

```python
def greet():
    print("Hello")


greet()
```

Prefer:

```python
def greet():
    print("Hello")


if __name__ == "__main__":
    greet()
```

---

### Mistake 6: Circular dependencies

Avoid designs where:

```text
A imports B
B imports A
```

Reorganize shared functionality when necessary.

---

# 28. Module Design Workflow

When creating a reusable module:

### Step 1 — Identify repeated logic

Find functionality that is used in multiple places.

### Step 2 — Group related logic

Put related functionality together.

### Step 3 — Create a module

Create a `.py` file.

```text
validation.py
```

### Step 4 — Create reusable functions

```python
def is_valid_age(age):
    return 0 <= age <= 120
```

### Step 5 — Use parameters

Avoid hard-coded values where possible.

### Step 6 — Return results

Allow the caller to decide what to do with the result.

### Step 7 — Import the module

```python
import validation
```

### Step 8 — Test the module

Test normal values, invalid values, and edge cases.

---

# 29. Complete Example

### Project structure

```text
student_app/
│
├── main.py
├── validation.py
└── results.py
```

### `validation.py`

```python
def is_valid_mark(mark):
    return 0 <= mark <= 100
```

### `results.py`

```python
def calculate_average(marks):
    if not marks:
        return 0

    return sum(marks) / len(marks)


def get_result(average):
    if average >= 40:
        return "Pass"

    return "Fail"
```

### `main.py`

```python
import validation
import results

marks = [70, 80, 65]

if all(validation.is_valid_mark(mark) for mark in marks):
    average = results.calculate_average(marks)
    result = results.get_result(average)

    print(f"Average: {average}")
    print(f"Result: {result}")
else:
    print("Invalid marks.")
```

The project is divided into reusable components.

---

# Quick Reference

| Concept               | Purpose                                    |
| --------------------- | ------------------------------------------ |
| Module                | Python file containing reusable code       |
| Function              | Reusable piece of logic                    |
| Parameter             | Allows different input values              |
| `return`              | Sends a result back to the caller          |
| `import`              | Makes a module available                   |
| `from ... import`     | Imports specific items                     |
| Alias                 | Alternative name for an imported item      |
| Docstring             | Documents a module or function             |
| `__name__`            | Special module-related variable            |
| `__main__`            | Indicates direct execution                 |
| DRY                   | Avoid repeating the same logic             |
| Single responsibility | Keep functionality focused                 |
| Circular import       | Modules depending on each other in a cycle |

---

# Key Points

1. A reusable module is a Python file designed to provide functionality to other programs.
2. Put related functionality into the same module.
3. Use functions to package reusable logic.
4. Use parameters instead of hard-coded values.
5. Prefer returning values instead of unnecessarily printing them.
6. Avoid unnecessary global state.
7. Keep modules focused on a clear responsibility.
8. Use docstrings to document reusable code.
9. Use `if __name__ == "__main__":` for code that should run only when the module is executed directly.
10. Avoid circular imports.
11. Reusable modules support the DRY principle.
12. Well-designed modules make programs easier to test, maintain, and extend.

---

# Interview Questions

### 1. What is a reusable module?

A reusable module is a Python file containing code that can be imported and used by other programs.

### 2. Why should we create reusable modules?

They reduce code duplication, improve organization, and make functionality easier to maintain and reuse.

### 3. How can you make a function reusable?

Use parameters for input and return values for output instead of hard-coding values or depending directly on user input.

### 4. Why is `return` often preferred over `print()` in reusable functions?

`return` gives the calling program the result, allowing it to decide how the result should be used.

### 5. What is the purpose of `if __name__ == "__main__":`?

It allows code to execute when the file is run directly but prevents that code from executing when the file is imported.

### 6. What is the DRY principle?

DRY means **Don't Repeat Yourself**. It encourages placing repeated logic into reusable functions or modules.

### 7. What is a module's responsibility?

A module should generally have a clear purpose and contain related functionality.

### 8. What is a circular import?

A circular import occurs when two or more modules depend on each other through imports.

### 9. Why should global state be minimized in reusable modules?

Heavy dependence on global state makes functions harder to understand, test, and reuse.

### 10. What makes a module reusable?

Clear responsibility, flexible functions, parameters, return values, minimal dependencies, documentation, and no unwanted execution during import.


---


[◀Back](.././)
---