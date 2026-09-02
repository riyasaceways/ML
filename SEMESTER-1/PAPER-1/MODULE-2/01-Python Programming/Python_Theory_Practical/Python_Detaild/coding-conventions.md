[◀Back](.././)
---

# Python Coding Conventions

Python coding conventions are recommended practices for writing code that is **readable, consistent, maintainable, and easy to understand**.

Python's most widely followed style guide is **PEP 8**.

---

# 1. Indentation

Python uses indentation to define blocks of code.

Use **4 spaces** for each indentation level.

### Recommended

```python
if age >= 18:
    print("Adult")
```

### Avoid

```python
if age >= 18:
        print("Adult")
```

> Do not use unnecessary indentation.

---

# 2. Spaces Around Operators

Use spaces around operators.

### Recommended

```python
total = price + tax
result = a * b
```

### Avoid

```python
total=price+tax
result=a*b
```

---

# 3. Variable Naming

Use **snake_case** for variable names.

### Recommended

```python
student_name = "Riyas"
student_age = 20
total_price = 99.99
```

### Avoid

```python
studentName = "Riyas"
StudentName = "Riyas"
student-name = "Riyas"
```

---

# 4. Function Naming

Functions should also use **snake_case**.

```python
def calculate_total():
    pass


def get_user_name():
    pass
```

---

# 5. Class Naming

Classes conventionally use **PascalCase**.

```python
class Student:
    pass


class StudentProfile:
    pass
```

### Naming Pattern

```text
student_name      → variable
calculate_total() → function
StudentProfile    → class
```

---

# 6. Constants

Constants are conventionally written using **UPPER_CASE** with underscores.

```python
MAX_USERS = 100
PI = 3.14159
DEFAULT_TIMEOUT = 30
```

> Python does not enforce constants. Uppercase naming is a convention that tells other developers the value should not normally be changed.

---

# 7. Meaningful Names

Use names that clearly describe what the value represents.

### Good

```python
student_name = "Riyas"
student_age = 20
total_marks = 450
```

### Poor

```python
x = "Riyas"
a = 20
t = 450
```

Short names can be appropriate in small contexts, such as loop counters:

```python
for i in range(10):
    print(i)
```

---

# 8. Avoid Single-Letter Names When Possible

Avoid unclear names:

```python
x = 100
y = 200
z = x + y
```

Prefer descriptive names:

```python
price = 100
tax = 200
total = price + tax
```

However, common short names are acceptable when their meaning is obvious:

```python
for i in range(10):
    print(i)
```

---

# 9. Avoid Reserved Keywords

Do not use Python keywords as variable, function, or class names.

Examples of Python keywords include:

```text
if
else
for
while
class
def
return
import
True
False
None
and
or
not
```

Invalid:

```python
class = "Python"
```

---

# 10. Avoid Built-in Names

Avoid using names of Python built-in functions and types for your variables.

### Avoid

```python
list = [1, 2, 3]
str = "Python"
sum = 100
```

This can hide the original built-in functionality.

### Better

```python
numbers = [1, 2, 3]
text = "Python"
total = 100
```

---

# 11. Use Blank Lines

Blank lines help separate logical sections of code.

```python
name = "Riyas"
age = 20


def greet_user():
    print(f"Hello, {name}")


greet_user()
```

Avoid filling the code with unnecessary blank lines.

---

# 12. Imports

Imports should generally be placed at the beginning of the file.

```python
import math
import os

name = "Riyas"
```

Do not place imports randomly throughout the file unless there is a specific reason.

---

# 13. One Import Per Line

### Recommended

```python
import os
import sys
import math
```

### Avoid

```python
import os, sys, math
```

---

# 14. Import Order

A common structure is:

1. Standard library imports
2. Third-party imports
3. Local application imports

Example:

```python
import os
import sys

import requests

from my_project import utils
```

---

# 15. Comments

Comments should explain code when necessary.

### Good

```python
# Calculate the final price after applying the discount
final_price = price - discount
```

### Unnecessary

```python
# Add 1 to age
age = age + 1
```

The second comment simply repeats what the code already says.

---

# 16. Comments Should Be Clear

Use comments to explain **why**, especially when the reason is not obvious.

```python
# Use a temporary variable because the original value is needed later
temporary_value = value
```

---

# 17. Inline Comments

Inline comments can be used when helpful, but excessive inline comments reduce readability.

```python
age = 20  # Student's current age
```

Avoid:

```python
age = 20  # Set age to 20
```

---

# 18. Docstrings

Use docstrings to document functions, classes, and modules.

```python
def calculate_total(price, tax):
    """Return the price including tax."""
    return price + tax
```

Docstrings are different from ordinary comments because they are part of the object's documentation.

---

# 19. Line Length

Keep lines reasonably short and readable.

PEP 8 traditionally recommends a maximum of **79 characters for code lines** and **72 characters for comments/docstrings**.

Modern projects may use different limits depending on their formatter or project configuration.

### Instead of:

```python
result = first_value + second_value + third_value + fourth_value + fifth_value
```

You can format a long expression across multiple lines:

```python
result = (
    first_value
    + second_value
    + third_value
    + fourth_value
    + fifth_value
)
```

---

# 20. String Quotes

Python supports both single and double quotes.

```python
name = "Riyas"
message = 'Hello'
```

The important point is to **be consistent within a project**.

For example:

```python
name = "Riyas"
city = "Bengaluru"
language = "Python"
```

---

# 21. Trailing Commas

Trailing commas are useful when writing multi-line collections.

```python
students = [
    "Riyas",
    "Ali",
    "John",
]
```

They can make future additions and version-control changes cleaner.

---

# 22. Boolean Comparisons

Avoid unnecessary comparisons with `True` or `False`.

### Avoid

```python
if is_student == True:
    print("Student")
```

### Prefer

```python
if is_student:
    print("Student")
```

For `False`:

```python
if not is_student:
    print("Not a student")
```

---

# 23. Checking for `None`

Use `is` when checking against `None`.

### Recommended

```python
if result is None:
    print("No result")
```

### Avoid

```python
if result == None:
    print("No result")
```

---

# 24. Use `is` and `is not` for Identity

`is` checks whether two references refer to the same object.

```python
result = None

if result is None:
    print("No result")
```

Use `==` when comparing values:

```python
age = 20

if age == 20:
    print("Age is 20")
```

---

# 25. Avoid Unnecessary Code

Prefer simple code when it is clear.

### Avoid

```python
if is_student == True:
    student = True
else:
    student = False
```

Prefer:

```python
student = is_student
```

---

# 26. Use Functions to Organize Code

Instead of putting everything into one large block, separate logical tasks into functions.

```python
def get_name():
    return input("Enter your name: ")


def greet_user(name):
    print(f"Hello, {name}")


name = get_name()
greet_user(name)
```

---

# 27. Use `if __name__ == "__main__"`

When a Python file can be used both as a module and as a standalone program:

```python
def main():
    print("Program started")


if __name__ == "__main__":
    main()
```

This allows the main program code to run when the file is executed directly, but not when it is imported as a module.

---

# 28. Avoid Unnecessary Semicolons

Python does not normally require semicolons.

### Recommended

```python
name = "Riyas"
age = 20
```

### Avoid

```python
name = "Riyas";
age = 20;
```

---

# 29. Avoid Multiple Statements on One Line

### Avoid

```python
name = "Riyas"; age = 20
```

### Prefer

```python
name = "Riyas"
age = 20
```

---

# 30. Use Readable Expressions

### Less readable

```python
x = a+b*c-d/e
```

### More readable

```python
result = first_value + second_value * third_value - fourth_value / fifth_value
```

Good naming often makes code easier to understand than comments.

---

# 31. Naming Conventions Summary

| Element | Convention | Example |
|---|---|---|
| Variable | `snake_case` | `student_name` |
| Function | `snake_case` | `calculate_total()` |
| Class | `PascalCase` | `StudentProfile` |
| Constant | `UPPER_CASE` | `MAX_USERS` |
| Module | `snake_case` | `student_data.py` |
| Package | Short lowercase name | `utils` |

---

# 32. Complete Example

```python
import math


MAX_STUDENTS = 50


class Student:
    """Represent a student."""

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display_info(self):
        """Display the student's information."""
        print(f"Name: {self.name}")
        print(f"Age: {self.age}")


def calculate_circle_area(radius):
    """Return the area of a circle."""
    return math.pi * radius ** 2


def main():
    student_name = input("Enter your name: ")
    student_age = int(input("Enter your age: "))

    student = Student(student_name, student_age)
    student.display_info()

    radius = 5
    area = calculate_circle_area(radius)

    print(f"Circle area: {area:.2f}")


if __name__ == "__main__":
    main()
```

This example demonstrates several conventions:

- Imports at the top
- `UPPER_CASE` constant
- `PascalCase` class name
- `snake_case` functions and variables
- 4-space indentation
- Meaningful names
- Docstrings
- Blank lines between logical sections
- f-strings
- `if __name__ == "__main__":`

---

# Quick Reference

```text
Indentation       → 4 spaces
Variables         → snake_case
Functions         → snake_case
Classes           → PascalCase
Constants         → UPPER_CASE
Operators         → Spaces around operators
Imports           → At the beginning
Comments          → Explain when useful
Docstrings        → Document functions/classes/modules
Semicolons        → Generally avoid
Line length       → Keep reasonably short
Names             → Clear and descriptive
None comparison   → is / is not
Boolean checks    → if value / if not value
```

---

# Key Points

- **PEP 8** is Python's main style guide.
- Use **4 spaces** for indentation.
- Use **snake_case** for variables and functions.
- Use **PascalCase** for classes.
- Use **UPPER_CASE** for constants.
- Choose meaningful names.
- Avoid shadowing built-in names.
- Use spaces around operators.
- Keep code readable and reasonably short.
- Use comments to explain non-obvious decisions.
- Use docstrings to document functions, classes, and modules.
- Keep imports organized at the top of the file.
- Prefer readable code over unnecessarily clever code.

---

# Interview Questions

### 1. What is PEP 8?

PEP 8 is the official Python style guide that provides recommendations for writing readable and consistent Python code.

### 2. What naming convention is used for Python variables?

Python commonly uses `snake_case`.

```python
student_name = "Riyas"
```

### 3. What naming convention is used for classes?

Python commonly uses `PascalCase`.

```python
class StudentProfile:
    pass
```

### 4. How many spaces should normally be used for indentation?

PEP 8 recommends **4 spaces** per indentation level.

### 5. How should constants be named?

Constants are conventionally written in `UPPER_CASE`.

```python
MAX_USERS = 100
```

### 6. What is the difference between a comment and a docstring?

A comment explains code for readers, while a docstring provides documentation for a module, class, or function and can be accessed programmatically.

### 7. Should `==` or `is` be used to check for `None`?

Use:

```python
value is None
```

### 8. Why should built-in names not be used as variable names?

Using names such as `list`, `str`, or `sum` can hide Python's built-in functions or types and cause unexpected behavior.

```python
list = [1, 2, 3]
```

This can prevent you from using the built-in `list()` function normally.

---
[◀Back](.././)
---