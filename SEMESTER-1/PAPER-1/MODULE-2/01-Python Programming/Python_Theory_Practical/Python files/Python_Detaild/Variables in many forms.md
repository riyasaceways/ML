# Python

## Starting with Hello world
```python
print("Hello World")
```

### Variable All forms

# Python Variables — Complete Syntax Guide

> Every common way to declare, assign, and use variables in Python.

---

### 1. Basic Variable Assignment

```python
name = "Riyas"
age = 20
price = 99.99
```

---

### 2. Multiple Variables (Different Values)

```python
name, age, city = "Riyas", 20, "Bengaluru"
```

---

### 3. Multiple Variables (Same Value)

```python
x = y = z = 100
```

---

### 4. Integer Variable

```python
age = 20
```

---

### 5. Float Variable

```python
price = 99.99
```

---

### 6. String Variable

```python
name = "Riyas"
```

---

### 7. Boolean Variable

```python
is_student = True
is_logged_in = False
```

---

### 8. None Variable

```python
result = None
```

---

### 9. Variable from an Expression

```python
a = 10
b = 20

total = a + b
```

---

### 10. Variable from Another Variable

```python
age = 20
next_year_age = age + 1
```

---

### 11. Variable from User Input

```python
name = input("Enter your name: ")
```

---

### 12. Variable with Type Conversion

```python
age = int(input("Enter your age: "))
height = float(input("Enter your height: "))
text = str(100)
```

---

### 13. Variable with Type Annotation

```python
name: str = "Riyas"
age: int = 20
price: float = 99.99
is_student: bool = True
```

---

### 14. Type Annotation Only

```python
name: str
age: int
```

---

### 15. Constant (Naming Convention)

```python
PI = 3.14159
MAX_USERS = 100
```

> **Note:** Python has no true constants. Uppercase is a convention.

---

### 16. List Unpacking

```python
numbers = [10, 20, 30]

a, b, c = numbers
```

---

### 17. Extended Unpacking

```python
numbers = [10, 20, 30, 40, 50]

first, *middle, last = numbers
```

Result:

```python
first = 10
middle = [20, 30, 40]
last = 50
```

---

### 18. Swap Variables

```python
a = 10
b = 20

a, b = b, a
```

---

### 19. Augmented Assignment

```python
x = 10

x += 5
x -= 2
x *= 3
x /= 2
x //= 2
x %= 3
x **= 2
```

---

### 20. Dynamic Typing

A variable can change its type during execution.

```python
value = 10
value = 10.5
value = "Python_Theory_Practical"
value = True
```

---

## Variable Naming Rules

### Valid Names

```python
student_name = "Riyas"
age2 = 20
_private = "Yes"
```

### Invalid Names

```python
2age = 20        # Starts with a number
student-name = "" # Hyphen is not allowed
class = "Python_Theory_Practical" # Reserved keyword
```

---

## Naming Conventions (PEP 8)

| Type | Convention | Example |
|------|------------|---------|
| Variable | `snake_case` | `student_name` |
| Function | `snake_case` | `calculate_total()` |
| Class | `PascalCase` | `StudentProfile` |
| Constant | `UPPER_CASE` | `MAX_SIZE` |

---

## Quick Reference Table

| Syntax | Example |
|---------|---------|
| Basic assignment | `x = 10` |
| String | `name = "Riyas"` |
| Float | `price = 99.99` |
| Boolean | `is_active = True` |
| None | `result = None` |
| Multiple assignment | `a, b = 1, 2` |
| Same value | `a = b = 100` |
| Expression | `total = a + b` |
| Input | `name = input()` |
| Type conversion | `age = int(input())` |
| Type annotation | `age: int = 20` |
| Constant | `MAX_USERS = 100` |
| Swap | `a, b = b, a` |
| Unpacking | `a, b, c = values` |
| Extended unpacking | `a, *b, c = values` |

---

## The Fundamental Syntax

```python
variable_name = value
```

Examples:

```python
name = "Riyas"
age = 20
height = 5.9
is_student = True
```

> **Interview Tip:** Python is **dynamically typed**, so the variable's type is determined automatically at runtime.
