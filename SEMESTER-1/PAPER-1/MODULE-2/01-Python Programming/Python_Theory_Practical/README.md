# Python

## Starting with Hello world
```python
print("Hello World")
```

### Variable All forms

# Python Variables — Complete Syntax Guide

> Every common way to declare, assign, and use variables in Python.

---

## 1. Basic Variable Assignment

```python
name = "Riyas"
age = 20
price = 99.99
```
[Variable in Many forms](Python_Detaild/Variables_in-many_forms.md)

---
# Python Data Types — Quick List

- `int` — Whole numbers
- `float` — Decimal numbers
- `complex` — Complex numbers
- `bool` — `True` or `False`
- `str` — Text/string values
- `list` — Ordered, mutable collection
- `tuple` — Ordered, immutable collection
- `range` — Sequence of numbers
- `set` — Unordered collection of unique values
- `frozenset` — Immutable set
- `dict` — Key-value pairs
- `bytes` — Immutable sequence of bytes
- `bytearray` — Mutable sequence of bytes
- `memoryview` — View of binary data without copying
- `NoneType` — Represents the absence of a value (`None`)

[View more detail of data types](Python_Detaild/Datatypes.md)

---

# Input and Output Operations

Python provides built-in functions to take input from the user and display output.

### Input

`input()` is used to receive data from the user. It always returns a `str`.

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))
```

### Output

`print()` is used to display data on the screen.

```python
print("Hello, Python!")
print(f"Hello, {name}")
```

### Common `print()` Parameters

* `sep` — Defines the separator between multiple values.
* `end` — Defines what is printed at the end.

```python
print("A", "B", "C", sep="-")
print("Hello", end=" ")
print("World")
```

### Quick Summary

| Function  | Purpose                |
| --------- | ---------------------- |
| `input()` | Get data from the user |
| `print()` | Display data           |
| `sep`     | Set value separator    |
| `end`     | Set line ending        |
| `\n`      | New line               |
| `\t`      | Tab                    |

**[View more details about Input and Output Operations](Python_Detaild/Input_and_output_operations.md)**


---


## Type Conversion

**Type conversion** is the process of converting a value from one data type to another.

Python provides built-in functions such as `int()`, `float()`, `str()`, `bool()`, `list()`, `tuple()`, `set()`, and `dict()` for type conversion.

```python
age = int("20")
price = float("99.99")
number = str(100)
```

Python supports both:

* **Implicit conversion** — Python automatically converts the type when appropriate.
* **Explicit conversion** — The programmer manually converts the type using conversion functions.

**[View detailed notes →](./Python_Detaild/type-conversion.md)**

---

## Expressions and Operators

An **expression** is a combination of values, variables, and operators that produces a result. **Operators** are symbols or keywords used to perform operations on values.

Common Python operators include:

* **Arithmetic:** `+`, `-`, `*`, `/`, `//`, `%`, `**`
* **Comparison:** `==`, `!=`, `>`, `<`, `>=`, `<=`
* **Logical:** `and`, `or`, `not`
* **Assignment:** `=`, `+=`, `-=`, `*=`, `/=`
* **Identity:** `is`, `is not`
* **Membership:** `in`, `not in`
* **Bitwise:** `&`, `|`, `^`, `~`, `<<`, `>>`

[View more details →](./Python_Detaild/expressions-and-operators.md)
