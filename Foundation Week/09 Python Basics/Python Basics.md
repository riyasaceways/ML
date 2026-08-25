# Python Basics

This task covers the four fundamental areas needed before moving into more advanced Python and ML programming:

1. **Variables & Data Types**
2. **Operators**
3. **Control Statements**
4. **Input & Output**

For your GitHub documentation, I recommend creating one Markdown file for this task and explaining each section with small Python examples.

---

## a. Variables & Data Types

A **variable** is a name used to store a value in a Python program. Python does not require you to explicitly declare the variable's type; the type is determined automatically from the value assigned to it.

Common Python data types include:

* `int` — whole numbers
* `float` — decimal numbers
* `str` — text
* `bool` — `True` or `False`
* `list` — ordered collection of values
* `tuple` — ordered, immutable collection
* `dict` — key-value pairs
* `set` — collection of unique values

### Example

```python
name = "Riyas"
age = 20
height = 5.8
is_student = True

print(name)
print(age)
print(height)
print(is_student)
```

You can check the type of a value using `type()`:

```python
print(type(name))
print(type(age))
print(type(height))
print(type(is_student))
```

### Basic collection types

```python
languages = ["Python", "Java", "C++"]

coordinates = (10, 20)

student = {
    "name": "Riyas",
    "age": 20
}

unique_numbers = {1, 2, 3, 3}

print(languages)
print(coordinates)
print(student)
print(unique_numbers)
```

**Key idea:** Variables allow programs to store and work with information, while data types determine what kind of information is being stored.

---

## b. Operators

**Operators** are symbols or keywords used to perform operations on values and variables.

### Arithmetic operators

```python
a = 10
b = 3

print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a // b)
print(a % b)
print(a ** b)
```

Common arithmetic operators:

| Operator | Meaning        |
| -------- | -------------- |
| `+`      | Addition       |
| `-`      | Subtraction    |
| `*`      | Multiplication |
| `/`      | Division       |
| `//`     | Floor division |
| `%`      | Modulus        |
| `**`     | Exponentiation |

### Comparison operators

Comparison operators produce `True` or `False`.

```python
a = 10
b = 5

print(a == b)
print(a != b)
print(a > b)
print(a < b)
print(a >= b)
print(a <= b)
```

### Logical operators

```python
age = 20
has_id = True

print(age >= 18 and has_id)
print(age >= 18 or has_id)
print(not has_id)
```

The main logical operators are:

* `and`
* `or`
* `not`

### Assignment operators

```python
x = 10

x += 5
print(x)

x -= 2
print(x)

x *= 2
print(x)
```

**Key idea:** Operators allow a program to calculate values, compare information, make logical decisions, and modify variables.

---

## c. Control Statements

**Control statements** determine the order in which Python executes instructions. They allow a program to make decisions and repeat operations.

The main types covered here are:

* `if`
* `elif`
* `else`
* `for`
* `while`

### `if` statement

```python
age = 20

if age >= 18:
    print("Adult")
```

### `if`, `elif`, and `else`

```python
marks = 75

if marks >= 90:
    print("A")
elif marks >= 60:
    print("B")
else:
    print("C")
```

### `for` loop

A `for` loop can repeat an operation over a sequence.

```python
for number in range(5):
    print(number)
```

Output:

```text
0
1
2
3
4
```

### `while` loop

A `while` loop continues while its condition remains `True`.

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

### `break`

`break` stops a loop.

```python
for number in range(10):
    if number == 5:
        break

    print(number)
```

### `continue`

`continue` skips the current iteration and continues with the next one.

```python
for number in range(5):
    if number == 2:
        continue

    print(number)
```

**Key idea:** Control statements give programs the ability to make decisions and repeat operations instead of simply executing every line once from top to bottom.

---

## d. Input & Output

**Input** allows a program to receive information from the user. **Output** allows the program to display information.

### Output with `print()`

```python
print("Hello, Python!")
print(10)
print("Age:", 20)
```

### Getting user input

Python uses `input()` to receive text from the user.

```python
name = input("Enter your name: ")

print("Hello", name)
```

By default, `input()` returns a string.

If you want a number, convert the input:

```python
age = int(input("Enter your age: "))

print("Your age is:", age)
```

For decimal numbers:

```python
height = float(input("Enter your height: "))

print("Height:", height)
```

### Simple input/output program

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))

print("Name:", name)
print("Age:", age)
```

### Using an f-string

An f-string makes it easier to combine variables with text:

```python
name = "Riyas"
age = 20

print(f"My name is {name} and I am {age} years old.")
```

**Key idea:** Input allows programs to interact with users, while output communicates information or results back to them.

---

# Simple Practice Program

After studying all four topics, combine them into one small program:

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

This single program uses:

* **Variables** → `name`, `age`, `status`
* **Data types** → `str`, `int`
* **Input** → `input()`
* **Output** → `print()`
* **Operators** → `>=`
* **Control statements** → `if` / `else`

That gives you a practical base before moving to the next Python task: **basic logical problems**.
