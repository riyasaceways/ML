# Type Conversion in Python

Type conversion is the process of **changing a value from one data type to another**.

Python supports two types of type conversion:

1. **Implicit Type Conversion**
2. **Explicit Type Conversion**

---

## 1. Implicit Type Conversion

Implicit type conversion happens **automatically** when Python converts a value from one type to another without the programmer explicitly requesting it.

### Example

```python
x = 10        # int
y = 2.5       # float

result = x + y

print(result)
print(type(result))
```

Output:

```text
12.5
<class 'float'>
```

Here, Python automatically converts `10` from `int` to `float` during the calculation.

### Another Example

```python
x = 5
y = 2.0

result = x * y

print(result)
print(type(result))
```

Output:

```text
10.0
<class 'float'>
```

> Python performs implicit conversion when the conversion is safe and appropriate for the operation.

---

# 2. Explicit Type Conversion

Explicit type conversion happens when the **programmer manually converts** a value from one type to another.

This is also commonly called **type casting**.

### Example

```python
age = "20"

age = int(age)

print(age)
print(type(age))
```

Output:

```text
20
<class 'int'>
```

The `int()` function explicitly converts the string `"20"` into an integer.

---

# Common Type Conversion Functions

| Function | Converts To | Example |
|---|---|---|
| `int()` | Integer | `int("10")` |
| `float()` | Float | `float("10.5")` |
| `str()` | String | `str(100)` |
| `bool()` | Boolean | `bool(1)` |
| `list()` | List | `list("ABC")` |
| `tuple()` | Tuple | `tuple([1, 2])` |
| `set()` | Set | `set([1, 2, 2])` |
| `dict()` | Dictionary | `dict([("a", 1)])` |

---

# 3. String to Integer

Use `int()` to convert a numeric string into an integer.

```python
number = int("100")

print(number)
print(type(number))
```

Output:

```text
100
<class 'int'>
```

### User Input Example

```python
age = int(input("Enter your age: "))

print(age)
```

Since `input()` returns a string, `int()` converts the input into an integer.

---

# 4. String to Float

Use `float()` to convert a numeric string into a floating-point number.

```python
price = float("99.99")

print(price)
print(type(price))
```

Output:

```text
99.99
<class 'float'>
```

### User Input Example

```python
height = float(input("Enter your height: "))

print(height)
```

---

# 5. Integer to Float

```python
number = 10

result = float(number)

print(result)
```

Output:

```text
10.0
```

---

# 6. Float to Integer

Use `int()` to convert a float to an integer.

```python
number = 10.99

result = int(number)

print(result)
```

Output:

```text
10
```

> `int()` **does not round** the number. It removes the fractional part.

For example:

```python
print(int(10.99))
print(int(10.01))
print(int(-10.99))
```

Output:

```text
10
10
-10
```

---

# 7. Integer to String

Use `str()` to convert a number into a string.

```python
age = 20

text = str(age)

print(text)
print(type(text))
```

Output:

```text
20
<class 'str'>
```

This is useful when combining numbers with strings.

```python
age = 20

print("I am " + str(age) + " years old.")
```

---

# 8. String to Boolean

Use `bool()` to convert a value into a Boolean.

```python
print(bool("Hello"))
print(bool(""))
```

Output:

```text
True
False
```

### Important

For strings:

- Any **non-empty string** → `True`
- An **empty string** → `False`

```python
bool("False")
```

Result:

```text
True
```

This is because `"False"` is a non-empty string. Python does not interpret the text `"False"` as the Boolean value `False`.

---

# 9. Integer to Boolean

```python
print(bool(1))
print(bool(0))
```

Output:

```text
True
False
```

Generally:

- `0` → `False`
- Any non-zero number → `True`

```python
print(bool(10))
print(bool(-5))
```

Output:

```text
True
True
```

---

# 10. Boolean to Integer

```python
print(int(True))
print(int(False))
```

Output:

```text
1
0
```

In Python:

```text
True  → 1
False → 0
```

---

# 11. String to List

Use `list()` to convert an iterable into a list.

```python
text = "Python"

result = list(text)

print(result)
```

Output:

```text
['P', 'y', 't', 'h', 'o', 'n']
```

Each character becomes an individual list element.

---

# 12. List to Tuple

```python
numbers = [1, 2, 3]

result = tuple(numbers)

print(result)
```

Output:

```text
(1, 2, 3)
```

---

# 13. Tuple to List

```python
numbers = (1, 2, 3)

result = list(numbers)

print(result)
```

Output:

```text
[1, 2, 3]
```

---

# 14. List to Set

```python
numbers = [1, 2, 2, 3, 3]

result = set(numbers)

print(result)
```

Output:

```text
{1, 2, 3}
```

> A `set` stores only unique values, so duplicates are removed.

---

# 15. Set to List

```python
numbers = {1, 2, 3}

result = list(numbers)

print(result)
```

Output:

```text
[1, 2, 3]
```

---

# 16. Dictionary Conversion

A dictionary can be created from an iterable containing key-value pairs.

```python
items = [("name", "Riyas"), ("age", 20)]

student = dict(items)

print(student)
```

Output:

```text
{'name': 'Riyas', 'age': 20}
```

---

# 17. Converting User Input

Because `input()` always returns a string:

```python
age = input("Enter your age: ")
```

`age` is a `str`.

To get an integer:

```python
age = int(input("Enter your age: "))
```

To get a float:

```python
salary = float(input("Enter your salary: "))
```

---

# 18. Multiple Input Conversion

```python
a, b = map(int, input("Enter two numbers: ").split())

print(a)
print(b)
```

Input:

```text
10 20
```

Here:

```python
input()
```

gets the input as a string.

```python
split()
```

separates the values.

```python
map(int, ...)
```

converts each value to an integer.

---

# 19. Invalid Type Conversion

Not every value can be converted into every type.

For example:

```python
number = int("Hello")
```

This produces:

```text
ValueError
```

Similarly:

```python
number = int("10.5")
```

also produces:

```text
ValueError
```

Because `"10.5"` is not a valid integer representation.

Instead:

```python
number = int(float("10.5"))
```

Result:

```text
10
```

---

# 20. Checking the Type

Use `type()` to check the type of a value.

```python
value = "100"

print(type(value))

value = int(value)

print(type(value))
```

Output:

```text
<class 'str'>
<class 'int'>
```

---

# Implicit vs Explicit Conversion

| Feature | Implicit | Explicit |
|---|---|---|
| Performed by | Python | Programmer |
| Automatic | Yes | No |
| Function required | Usually no | Usually yes |
| Example | `10 + 2.5` | `int("10")` |

### Implicit Example

```python
x = 10
y = 2.5

result = x + y
```

Python automatically handles the conversion needed for the arithmetic operation.

### Explicit Example

```python
x = "10"

result = int(x)
```

The programmer explicitly requests the conversion.

---

# Important Conversion Examples

```python
# String → Integer
x = int("10")

# String → Float
x = float("10.5")

# Integer → Float
x = float(10)

# Float → Integer
x = int(10.5)

# Integer → String
x = str(10)

# Float → String
x = str(10.5)

# String → Boolean
x = bool("Python")

# Integer → Boolean
x = bool(1)

# Boolean → Integer
x = int(True)

# String → List
x = list("Python")

# List → Tuple
x = tuple([1, 2, 3])

# Tuple → List
x = list((1, 2, 3))

# List → Set
x = set([1, 2, 2, 3])
```

---

# Quick Reference

```text
int()        → Integer
float()      → Float
str()        → String
bool()       → Boolean
list()       → List
tuple()      → Tuple
set()        → Set
dict()       → Dictionary
```

---

# Key Points

- **Type conversion** means changing one data type into another.
- **Implicit conversion** is performed automatically by Python.
- **Explicit conversion** is performed manually by the programmer.
- `input()` always returns a `str`.
- Use `int()` for integer conversion.
- Use `float()` for decimal-number conversion.
- Use `str()` for string conversion.
- Use `bool()` for Boolean conversion.
- `int()` truncates a float; it does not round it.
- Invalid conversions can raise exceptions such as `ValueError`.
- Use `type()` to check the data type of a value.

---

## Interview Questions

### 1. What is type conversion?

Type conversion is the process of converting a value from one data type to another.

### 2. What are the two types of type conversion in Python?

- Implicit type conversion
- Explicit type conversion

### 3. What does `input()` return?

`input()` always returns a value of type `str`.

### 4. Does `int(10.9)` round the number?

No. It removes the fractional part and returns `10`.

### 5. What happens with `bool("False")`?

It returns `True` because `"False"` is a non-empty string.

### 6. What happens when an invalid conversion is attempted?

Python may raise an exception such as `ValueError`.

```python
int("Hello")
# ValueError
```