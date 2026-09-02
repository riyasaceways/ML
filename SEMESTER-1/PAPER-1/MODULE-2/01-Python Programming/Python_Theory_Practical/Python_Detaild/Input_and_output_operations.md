[◀Back](.././)
---

# Input and Output Operations in Python

Input and output operations allow a Python program to **receive data from the user** and **display information to the user**.

---

## 1. Output Operation

Python uses the `print()` function to display output.

### Syntax

```python
print(value)
```

### Example

```python
print("Hello, Python!")
```

Output:

```text
Hello, Python!
```

---

## 2. Printing Variables

```python
name = "Riyas"
age = 20

print(name)
print(age)
```

Output:

```text
Riyas
20
```

---

## 3. Printing Multiple Values

```python
name = "Riyas"
age = 20

print(name, age)
```

Output:

```text
Riyas 20
```

---

## 4. Printing Text and Variables

```python
name = "Riyas"
age = 20

print("Name:", name)
print("Age:", age)
```

Output:

```text
Name: Riyas
Age: 20
```

---

## 5. Using f-Strings

f-strings are a convenient way to insert variables into strings.

```python
name = "Riyas"
age = 20

print(f"My name is {name} and I am {age} years old.")
```

Output:

```text
My name is Riyas and I am 20 years old.
```

---

# `print()` Parameters

## 6. `sep` Parameter

`sep` specifies the separator between multiple values.

### Default

```python
print("Python", "Java", "C++")
```

Output:

```text
Python Java C++
```

### Custom Separator

```python
print("Python", "Java", "C++", sep=", ")
```

Output:

```text
Python, Java, C++
```

---

## 7. `end` Parameter

`end` specifies what is printed at the end of the output.

### Default

```python
print("Hello")
print("World")
```

Output:

```text
Hello
World
```

By default, `print()` ends with a newline (`\n`).

### Custom `end`

```python
print("Hello", end=" ")
print("World")
```

Output:

```text
Hello World
```

---

# 8. New Line (`\n`)

`\n` is used to create a new line.

```python
print("Hello\nWorld")
```

Output:

```text
Hello
World
```

---

# 9. Tab (`\t`)

`\t` inserts a tab space.

```python
print("Name:\tRiyas")
print("Age:\t20")
```

Output:

```text
Name:   Riyas
Age:    20
```

---

# Input Operations

## 10. `input()` Function

The `input()` function is used to receive data from the user.

### Syntax

```python
variable = input(prompt)
```

### Example

```python
name = input("Enter your name: ")

print(name)
```

If the user enters:

```text
Riyas
```

Output:

```text
Riyas
```

---

## 11. Input Without a Prompt

```python
name = input()
```

The program waits for the user to enter a value.

---

## 12. Important: `input()` Returns a String

The `input()` function always returns a value of type `str`.

```python
age = input("Enter your age: ")

print(type(age))
```

If the user enters:

```text
20
```

Output:

```text
<class 'str'>
```

---

# Input with Type Conversion

Since `input()` returns a string, numeric input usually needs type conversion.

## 13. Integer Input

```python
age = int(input("Enter your age: "))

print(age)
```

---

## 14. Float Input

```python
height = float(input("Enter your height: "))

print(height)
```

---

## 15. String Input

No conversion is required for normal text input.

```python
name = input("Enter your name: ")
```

---

## 16. Boolean Input

`input()` itself returns a string, so this does **not** work as many beginners expect:

```python
is_student = bool(input("Are you a student? "))
```

For example, even `"False"` is a non-empty string and therefore evaluates to `True`.

For simple yes/no input, use explicit logic:

```python
answer = input("Are you a student? ")

is_student = answer.lower() == "yes"

print(is_student)
```

---

# Multiple Inputs

## 17. Taking Multiple Inputs Separately

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))
```

---

## 18. Taking Multiple Values in One Line

The `split()` method can separate input into multiple values.

```python
name, age = input("Enter name and age: ").split()
```

Example input:

```text
Riyas 20
```

Now:

```python
name = "Riyas"
age = "20"
```

> Notice that `age` is still a string.

---

## 19. Multiple Integer Inputs

```python
a, b = map(int, input("Enter two numbers: ").split())
```

Example input:

```text
10 20
```

Now:

```python
a = 10
b = 20
```

---

## 20. Multiple Float Inputs

```python
a, b = map(float, input("Enter two numbers: ").split())
```

Example input:

```text
10.5 20.5
```

---

# Output with Calculations

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

total = a + b

print("Total:", total)
```

Example:

```text
Enter first number: 10
Enter second number: 20
Total: 30
```

---

# Complete Example

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))
height = float(input("Enter your height: "))

print("\nStudent Information")
print("------------------")
print(f"Name: {name}")
print(f"Age: {age}")
print(f"Height: {height} meters")
```

---

# Quick Reference

| Function / Syntax | Purpose |
|---|---|
| `print()` | Display output |
| `input()` | Receive user input |
| `print(value)` | Print a value |
| `print(a, b)` | Print multiple values |
| `print(a, b, sep=", ")` | Customize separator |
| `print(a, end=" ")` | Customize line ending |
| `input("Enter: ")` | Input with a prompt |
| `int(input())` | Get integer input |
| `float(input())` | Get float input |
| `input().split()` | Split input into values |
| `map(int, input().split())` | Convert multiple inputs to integers |

---

## Key Points

- `print()` is used for **output**.
- `input()` is used for **input**.
- `input()` **always returns a string**.
- Use `int()` or `float()` when numeric input is required.
- `sep` controls the separator between printed values.
- `end` controls what is printed after the output.
- `\n` creates a new line.
- `\t` creates a tab space.
- f-strings are commonly used for formatted output.

[◀Back](.././)
---