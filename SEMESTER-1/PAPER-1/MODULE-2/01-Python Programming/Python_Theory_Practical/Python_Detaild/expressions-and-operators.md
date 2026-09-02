[◀Back](./)
---

# Expressions and Operators in Python

## 1. What is an Expression?

An **expression** is a combination of values, variables, operators, and function calls that Python evaluates to produce a result.

```python
10 + 20
```

Result:

```text
30
```

Another example:

```python
a = 10
b = 20

result = a + b
```

Here:

```python
a + b
```

is an expression.

---

# 2. What is an Operator?

An **operator** is a symbol or keyword used to perform an operation on one or more values.

```python
a + b
```

Here:

- `a` and `b` → operands
- `+` → operator

---

# 3. Arithmetic Operators

Arithmetic operators are used to perform mathematical operations.

| Operator | Name | Example | Result |
|---|---|---|---:|
| `+` | Addition | `10 + 3` | `13` |
| `-` | Subtraction | `10 - 3` | `7` |
| `*` | Multiplication | `10 * 3` | `30` |
| `/` | Division | `10 / 3` | `3.333...` |
| `//` | Floor Division | `10 // 3` | `3` |
| `%` | Modulus | `10 % 3` | `1` |
| `**` | Exponentiation | `10 ** 3` | `1000` |

### Addition

```python
a = 10
b = 5

print(a + b)
```

Output:

```text
15
```

### Subtraction

```python
print(10 - 5)
```

Output:

```text
5
```

### Multiplication

```python
print(10 * 5)
```

Output:

```text
50
```

### Division

```python
print(10 / 3)
```

Output:

```text
3.3333333333333335
```

> `/` always produces a floating-point result in Python.

### Floor Division

```python
print(10 // 3)
```

Output:

```text
3
```

Floor division returns the floor of the division result.

### Modulus

```python
print(10 % 3)
```

Output:

```text
1
```

`%` returns the remainder.

### Exponentiation

```python
print(2 ** 3)
```

Output:

```text
8
```

---

# 4. Comparison Operators

Comparison operators compare two values and return a Boolean value:

```text
True
```

or

```text
False
```

| Operator | Meaning | Example |
|---|---|---|
| `==` | Equal to | `10 == 10` |
| `!=` | Not equal to | `10 != 5` |
| `>` | Greater than | `10 > 5` |
| `<` | Less than | `10 < 5` |
| `>=` | Greater than or equal to | `10 >= 10` |
| `<=` | Less than or equal to | `10 <= 10` |

### Examples

```python
x = 10

print(x == 10)
print(x != 5)
print(x > 5)
print(x < 20)
print(x >= 10)
print(x <= 10)
```

Output:

```text
True
True
True
True
True
True
```

### `=` vs `==`

This is an important distinction.

`=` is the **assignment operator**:

```python
age = 20
```

`==` is the **comparison operator**:

```python
age == 20
```

The first assigns a value. The second checks whether two values are equal.

---

# 5. Logical Operators

Logical operators are used to combine or modify conditions.

| Operator | Description |
|---|---|
| `and` | Returns true when both conditions are true |
| `or` | Returns true when at least one condition is true |
| `not` | Reverses the Boolean result |

### `and`

```python
age = 20

print(age >= 18 and age <= 60)
```

Output:

```text
True
```

Both conditions are true.

### `or`

```python
age = 16

print(age < 18 or age > 60)
```

Output:

```text
True
```

At least one condition is true.

### `not`

```python
is_student = True

print(not is_student)
```

Output:

```text
False
```

---

# 6. Assignment Operators

Assignment operators are used to assign values to variables.

### Basic Assignment

```python
x = 10
```

### Augmented Assignment

| Operator | Equivalent |
|---|---|
| `+=` | `x = x + value` |
| `-=` | `x = x - value` |
| `*=` | `x = x * value` |
| `/=` | `x = x / value` |
| `//=` | `x = x // value` |
| `%=` | `x = x % value` |
| `**=` | `x = x ** value` |

### Example

```python
x = 10

x += 5

print(x)
```

Output:

```text
15
```

This:

```python
x += 5
```

is equivalent to:

```python
x = x + 5
```

---

# 7. Identity Operators

Identity operators check whether two variables refer to the **same object**.

| Operator | Meaning |
|---|---|
| `is` | Same object |
| `is not` | Not the same object |

Example:

```python
a = None

print(a is None)
```

Output:

```text
True
```

### `is` vs `==`

This is important.

`==` checks whether values are equal:

```python
a == b
```

`is` checks whether they are the same object:

```python
a is b
```

Do not generally use `is` when you simply want to compare values.

---

# 8. Membership Operators

Membership operators check whether a value exists inside a sequence or collection.

| Operator | Meaning |
|---|---|
| `in` | Value exists |
| `not in` | Value does not exist |

### Example

```python
languages = ["Python", "Java", "C++"]

print("Python" in languages)
```

Output:

```text
True
```

### `not in`

```python
print("JavaScript" not in languages)
```

Output:

```text
True
```

Membership operators can be used with strings:

```python
text = "Python"

print("Py" in text)
```

Output:

```text
True
```

---

# 9. Bitwise Operators

Bitwise operators work with numbers at the **binary/bit level**.

| Operator | Name |
|---|---|
| `&` | Bitwise AND |
| `|` | Bitwise OR |
| `^` | Bitwise XOR |
| `~` | Bitwise NOT |
| `<<` | Left Shift |
| `>>` | Right Shift |

### Bitwise AND

```python
a = 5
b = 3

print(a & b)
```

Output:

```text
1
```

### Bitwise OR

```python
print(5 | 3)
```

Output:

```text
7
```

### Bitwise XOR

```python
print(5 ^ 3)
```

Output:

```text
6
```

### Bitwise NOT

```python
print(~5)
```

Output:

```text
-6
```

### Left Shift

```python
print(5 << 1)
```

Output:

```text
10
```

### Right Shift

```python
print(5 >> 1)
```

Output:

```text
2
```

---

# 10. Unary Operators

Unary operators work with a single operand.

### Unary Plus

```python
x = 10

print(+x)
```

### Unary Minus

```python
x = 10

print(-x)
```

Output:

```text
-10
```

### Logical NOT

```python
is_active = True

print(not is_active)
```

Output:

```text
False
```

---

# 11. String Operators

The `+` and `*` operators can also work with strings.

### String Concatenation

```python
first_name = "Muhammed"
last_name = "Riyas"

full_name = first_name + " " + last_name

print(full_name)
```

Output:

```text
Muhammed Riyas
```

### String Repetition

```python
print("Python " * 3)
```

Output:

```text
Python Python Python
```

---

# 12. Operator Precedence

When an expression contains multiple operators, Python follows a specific order of evaluation.

For example:

```python
result = 10 + 5 * 2

print(result)
```

Output:

```text
20
```

Multiplication is performed before addition:

```text
10 + (5 * 2)
10 + 10
20
```

Parentheses can be used to control the order:

```python
result = (10 + 5) * 2

print(result)
```

Output:

```text
30
```

### Common Precedence Order

From higher to lower precedence:

1. `()`
2. `**`
3. Unary `+`, `-`, `~`
4. `*`, `/`, `//`, `%`
5. `+`, `-`
6. Comparisons: `==`, `!=`, `>`, `<`, `>=`, `<=`
7. `not`
8. `and`
9. `or`

> When in doubt, use parentheses to make the intended order clear.

---

# 13. Chained Comparisons

Python allows multiple comparisons in a single expression.

```python
age = 20

print(18 <= age <= 60)
```

Output:

```text
True
```

This is equivalent to:

```python
18 <= age and age <= 60
```

---

# 14. Combining Operators

Different operators can be used together.

```python
age = 20
has_id = True

can_enter = age >= 18 and has_id

print(can_enter)
```

Output:

```text
True
```

---

# 15. Expression Examples

### Arithmetic Expression

```python
result = 10 + 20 * 2
```

### Comparison Expression

```python
result = 10 > 5
```

### Logical Expression

```python
result = 10 > 5 and 20 > 10
```

### String Expression

```python
message = "Hello " + "Python"
```

### Assignment Expression

Python also supports the **assignment expression operator** `:=`.

```python
if (length := len("Python")) > 5:
    print(length)
```

Output:

```text
6
```

The `:=` operator is known as the **walrus operator**. It assigns a value while also allowing that value to be used as part of an expression.

---

# Complete Operator List

| Category | Operators |
|---|---|
| Arithmetic | `+`, `-`, `*`, `/`, `//`, `%`, `**` |
| Comparison | `==`, `!=`, `>`, `<`, `>=`, `<=` |
| Logical | `and`, `or`, `not` |
| Assignment | `=`, `+=`, `-=`, `*=`, `/=`, `//=`, `%=`, `**=` |
| Identity | `is`, `is not` |
| Membership | `in`, `not in` |
| Bitwise | `&`, `|`, `^`, `~`, `<<`, `>>` |
| Unary | `+`, `-`, `~` |
| Assignment Expression | `:=` |

---

# Quick Reference

```python
# Arithmetic
+   -   *   /   //   %   **

# Comparison
==   !=   >   <   >=   <=

# Logical
and   or   not

# Assignment
=   +=   -=   *=   /=   //=   %=   **=

# Identity
is   is not

# Membership
in   not in

# Bitwise
&   |   ^   ~   <<   >>

# Assignment expression
:=
```

---

# Key Points

- An **expression** produces a value when Python evaluates it.
- An **operator** performs an operation on one or more operands.
- Arithmetic operators perform mathematical operations.
- Comparison operators return `True` or `False`.
- Logical operators combine conditions.
- Assignment operators assign or update variable values.
- Identity operators compare object identity.
- Membership operators check whether a value exists in a collection.
- Bitwise operators work at the binary level.
- Operator precedence determines the order in which expressions are evaluated.
- Parentheses can be used to explicitly control evaluation order.

---

# Interview Questions

### 1. What is an expression?

An expression is a combination of values, variables, operators, and other elements that Python evaluates to produce a result.

### 2. What is an operator?

An operator is a symbol or keyword used to perform an operation on one or more operands.

### 3. What is the difference between `=` and `==`?

`=` assigns a value, while `==` compares two values.

### 4. What is the difference between `/` and `//`?

`/` performs normal division and returns a float, while `//` performs floor division.

### 5. What does `%` do?

It returns the remainder of a division.

### 6. What is the difference between `is` and `==`?

`==` compares values, while `is` checks whether two references point to the same object.

### 7. What are logical operators in Python?

```python
and
or
not
```

### 8. What is operator precedence?

Operator precedence determines the order in which operators are evaluated in an expression.

### 9. What is the walrus operator?

`:=` is the assignment expression operator. It assigns a value while allowing that value to be used within an expression.

```python
if (x := 10) > 5:
    print(x)
```

[◀Back](./)
---