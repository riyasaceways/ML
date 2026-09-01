[◀ Back to Index](../../../../../../README.md) &emsp; | &emsp;[◀ Back](./)

---

# Python Basics

## 1. Variables & Data Types

A **variable** is a name that stores a value.

```python
name = "Riyas"
age = 20
height = 5.8
is_student = True
```

Common data types:

```text
int    → whole numbers      → 20
float  → decimal numbers    → 5.8
str    → text               → "Riyas"
bool   → True / False       → True
list   → collection         → [1, 2, 3]
tuple  → fixed collection   → (1, 2, 3)
dict   → key-value pairs    → {"name": "Riyas"}
set    → unique values      → {1, 2, 3}
```

Check the type:

```python
print(type(age))
print(type(name))
```

---

## 2. Operators

Operators are used to perform operations on values.

### Arithmetic

```python
a = 10
b = 3

a + b   # addition
a - b   # subtraction
a * b   # multiplication
a / b   # division
a // b  # floor division
a % b   # remainder
a ** b  # power
```

### Comparison

Comparison gives `True` or `False`.

```python
a == b
a != b
a > b
a < b
a >= b
a <= b
```

### Logical

```python
age >= 18 and has_id
age >= 18 or has_id
not has_id
```

Main logical operators:

```text
and
or
not
```

---

## 3. Control Statements

Control statements control how the program executes.

### if / elif / else

```python
marks = 75

if marks >= 90:
    print("A")
elif marks >= 60:
    print("B")
else:
    print("C")
```

### for loop

Used when I want to repeat something for a sequence/range.

```python
for number in range(5):
    print(number)
```

### while loop

Repeats while a condition is `True`.

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

### break

Stops the loop.

```python
for number in range(10):
    if number == 5:
        break

    print(number)
```

### continue

Skips the current iteration.

```python
for number in range(5):
    if number == 2:
        continue

    print(number)
```

---

## 4. Input & Output

### Output

`print()` displays information.

```python
print("Hello")
print(10)
```

### Input

`input()` gets information from the user.

```python
name = input("Enter your name: ")
print(name)
```

`input()` returns a **string** by default.

For an integer:

```python
age = int(input("Enter your age: "))
```

For a decimal:

```python
height = float(input("Enter your height: "))
```

### f-string

Useful for putting variables inside text.

```python
name = "Riyas"
age = 20

print(f"My name is {name} and I am {age} years old.")
```

---

## Small Practice

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))

if age >= 18:
    status = "adult"
else:
    status = "minor"

print(f"Hello {name}!")
print(f"You are an {status}.")
```

### What this program uses

```text
Variables       → name, age, status
Data types      → str, int
Input           → input()
Output          → print()
Operator        → >=
Control         → if / else
```
---

[◀ Back to Index](../../../../../../README.md) &emsp; | &emsp;[◀ Back](./)