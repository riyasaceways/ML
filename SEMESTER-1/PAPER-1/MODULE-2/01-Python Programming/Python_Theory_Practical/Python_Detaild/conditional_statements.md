[◀ Back](./)
---


# Conditional Statements in Python

## 1. What are Conditional Statements?

**Conditional statements** are used to make decisions in a Python program.

They allow the program to execute different blocks of code depending on whether a condition evaluates to `True` or `False`.

The basic idea is:

```text
Condition
   │
   ├── True  → Execute one block
   │
   └── False → Execute another block
```

For example:

```python
age = 20

if age >= 18:
    print("Adult")
```

Here, Python checks:

```python
age >= 18
```

Since the condition is `True`, the `print()` statement is executed.

---

# 2. The `if` Statement

The `if` statement executes a block of code only when its condition is `True`.

### Syntax

```python
if condition:
    # code to execute
```

### Example

```python
age = 20

if age >= 18:
    print("You are an adult.")
```

### How it works

1. Python evaluates `age >= 18`.
2. The result is `True`.
3. Python executes the indented code.
4. If the condition were `False`, the indented code would be skipped.

### Another example

```python
temperature = 35

if temperature > 30:
    print("It is hot.")
```

---

# 3. The `if-else` Statement

The `if-else` statement provides two possible execution paths.

* If the condition is `True`, the `if` block executes.
* If the condition is `False`, the `else` block executes.

### Syntax

```python
if condition:
    # code when condition is True
else:
    # code when condition is False
```

### Example

```python
age = 16

if age >= 18:
    print("You can vote.")
else:
    print("You cannot vote.")
```

Since `age >= 18` is `False`, Python executes the `else` block.

---

# 4. The `if-elif-else` Statement

The `if-elif-else` structure is used when there are **multiple conditions** to check.

### Syntax

```python
if condition1:
    # code
elif condition2:
    # code
elif condition3:
    # code
else:
    # code
```

Python checks the conditions from **top to bottom**.

Once it finds a condition that is `True`, its block executes and the remaining conditions are skipped.

### Example

```python
mark = 75

if mark >= 90:
    print("Grade A")
elif mark >= 75:
    print("Grade B")
elif mark >= 50:
    print("Grade C")
else:
    print("Fail")
```

Output:

```text
Grade B
```

---

# 5. Multiple `elif` Statements

You can use more than one `elif` when several possibilities need to be checked.

```python
day = 3

if day == 1:
    print("Monday")
elif day == 2:
    print("Tuesday")
elif day == 3:
    print("Wednesday")
elif day == 4:
    print("Thursday")
else:
    print("Another day")
```

Output:

```text
Wednesday
```

---

# 6. The `else` Statement

The `else` block executes when none of the preceding conditions are `True`.

```python
number = 7

if number > 10:
    print("Greater than 10")
else:
    print("10 or less")
```

Output:

```text
10 or less
```

The `else` statement is optional.

This is valid:

```python
if number > 10:
    print("Greater than 10")
```

---

# 7. Conditions

A condition is an expression that produces a Boolean result:

```python
True
```

or

```python
False
```

### Comparison operators

| Operator | Meaning                  |
| -------- | ------------------------ |
| `==`     | Equal to                 |
| `!=`     | Not equal to             |
| `>`      | Greater than             |
| `<`      | Less than                |
| `>=`     | Greater than or equal to |
| `<=`     | Less than or equal to    |

### Example

```python
age = 20

print(age == 20)
print(age > 18)
print(age < 18)
```

Output:

```text
True
True
False
```

These expressions can be used directly in conditional statements.

```python
age = 20

if age >= 18:
    print("Adult")
```

---

# 8. Using Logical Operators in Conditions

Multiple conditions can be combined using logical operators.

Python provides:

* `and`
* `or`
* `not`

### `and`

Both conditions must be `True`.

```python
age = 25
has_id = True

if age >= 18 and has_id:
    print("Access granted.")
```

### `or`

At least one condition must be `True`.

```python
day = "Saturday"

if day == "Saturday" or day == "Sunday":
    print("Weekend")
```

### `not`

Reverses the Boolean result.

```python
is_raining = False

if not is_raining:
    print("You can go outside.")
```

---

# 9. Combining Conditions

Conditions can be combined to create more specific decisions.

```python
age = 25
salary = 50000

if age >= 18 and salary >= 30000:
    print("Eligible")
else:
    print("Not eligible")
```

Here, both conditions must be `True`.

---

# 10. Nested Conditional Statements

A **nested conditional statement** is a conditional statement inside another conditional statement.

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Access granted.")
    else:
        print("ID required.")
else:
    print("You are underage.")
```

The inner `if` is evaluated only after the outer condition is `True`.

Nested conditions are useful when one decision depends on another decision.

> Nested conditions are closely related to conditional statements but are treated separately when studying control flow.

---

# 11. Conditional Expressions

A **conditional expression** provides a short way to choose between two values.

### Syntax

```python
value_if_true if condition else value_if_false
```

### Example

```python
age = 20

status = "Adult" if age >= 18 else "Minor"

print(status)
```

Output:

```text
Adult
```

The same logic using a normal `if-else` statement would be:

```python
age = 20

if age >= 18:
    status = "Adult"
else:
    status = "Minor"

print(status)
```

Conditional expressions are useful when the decision is simple and can be expressed clearly in one line.

---

# 12. Truthy and Falsy Values

Python conditions do not always have to be explicit comparisons.

Some values are treated as `True` or `False` when used in a condition.

### Example

```python
name = "Riyas"

if name:
    print("Name is available.")
```

An empty string is considered falsy:

```python
name = ""

if name:
    print("Name is available.")
else:
    print("Name is empty.")
```

Common falsy values include:

```python
False
None
0
0.0
""
[]
()
{}
set()
```

Most other values are considered truthy.

---

# 13. Checking Membership in Conditions

The `in` and `not in` operators can be used to check whether a value exists inside a collection.

```python
fruits = ["apple", "banana", "orange"]

if "apple" in fruits:
    print("Apple is available.")
```

Using `not in`:

```python
if "mango" not in fruits:
    print("Mango is not available.")
```

---

# 14. Checking Object Identity

The `is` and `is not` operators check whether two references refer to the same object.

They are commonly used with `None`.

```python
value = None

if value is None:
    print("No value provided.")
```

For normal value comparison, use `==` rather than `is`.

```python
a = 10
b = 10

if a == b:
    print("Values are equal.")
```

---

# 15. Indentation in Conditional Statements

Python uses **indentation** to define the block of code belonging to a conditional statement.

Correct:

```python
age = 20

if age >= 18:
    print("Adult")
```

Incorrect:

```python
age = 20

if age >= 18:
print("Adult")
```

The code inside the conditional block must be indented.

A common convention is **4 spaces**.

---

# 16. Conditions with User Input

Conditional statements are often used together with `input()`.

```python
age = int(input("Enter your age: "))

if age >= 18:
    print("You are an adult.")
else:
    print("You are a minor.")
```

The program:

1. Takes input from the user.
2. Converts it to an integer.
3. Checks the age.
4. Executes the appropriate block.

---

# 17. Practical Example: Positive, Negative, or Zero

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

Possible results:

```text
Enter a number: 10
Positive
```

```text
Enter a number: -5
Negative
```

```text
Enter a number: 0
Zero
```

---

# 18. Practical Example: Login Check

```python
username = input("Enter username: ")
password = input("Enter password: ")

if username == "admin" and password == "1234":
    print("Login successful.")
else:
    print("Invalid username or password.")
```

This example combines:

* `input()`
* variables
* comparison operators
* the `and` logical operator
* `if-else`

---

# 19. Practical Example: Grade Calculator

```python
mark = int(input("Enter your mark: "))

if mark >= 90:
    grade = "A"
elif mark >= 80:
    grade = "B"
elif mark >= 70:
    grade = "C"
elif mark >= 60:
    grade = "D"
else:
    grade = "F"

print("Grade:", grade)
```

The conditions are evaluated from top to bottom.

For example, if the mark is `85`:

```text
mark >= 90  → False
mark >= 80  → True
```

Therefore, Python assigns:

```python
grade = "B"
```

---

# 20. Common Mistakes

## Mistake 1: Using `=` instead of `==`

Incorrect:

```python
if age = 18:
    print("Age is 18")
```

Correct:

```python
if age == 18:
    print("Age is 18")
```

`=` is assignment, while `==` is comparison.

---

## Mistake 2: Forgetting the Colon

Incorrect:

```python
if age >= 18
    print("Adult")
```

Correct:

```python
if age >= 18:
    print("Adult")
```

A colon `:` is required after the condition.

---

## Mistake 3: Incorrect Indentation

Incorrect:

```python
if age >= 18:
print("Adult")
```

Correct:

```python
if age >= 18:
    print("Adult")
```

---

## Mistake 4: Using Separate `if` Statements When `elif` Is Needed

Consider:

```python
mark = 85

if mark >= 90:
    print("A")

if mark >= 80:
    print("B")
```

Output:

```text
B
```

For mutually exclusive conditions, an `if-elif-else` structure is usually clearer:

```python
if mark >= 90:
    print("A")
elif mark >= 80:
    print("B")
```

---

# 21. Quick Reference

| Structure              | Purpose                                       |
| ---------------------- | --------------------------------------------- |
| `if`                   | Execute code when a condition is true         |
| `if-else`              | Choose between two paths                      |
| `if-elif-else`         | Choose between multiple conditions            |
| Nested `if`            | Make decisions inside another decision        |
| Conditional expression | Write a simple conditional choice in one line |
| `and`                  | Require multiple conditions to be true        |
| `or`                   | Allow at least one condition to be true       |
| `not`                  | Reverse a Boolean condition                   |
| `in`                   | Check membership                              |
| `not in`               | Check absence                                 |
| `is`                   | Check object identity                         |

---

# 22. Key Points to Remember

* Conditional statements allow Python programs to **make decisions**.
* `if` checks a condition.
* `else` handles the alternative when the condition is false.
* `elif` allows multiple conditions to be checked.
* Conditions normally produce `True` or `False`.
* `and`, `or`, and `not` can combine or modify conditions.
* Python uses indentation to define conditional blocks.
* Nested conditions place one conditional inside another.
* Conditional expressions provide a concise way to choose between two values.
* Conditions can work with comparisons, membership checks, Boolean values, and other expressions.

---

# 23. Interview Questions

### 1. What is a conditional statement in Python?

A conditional statement allows a program to make decisions and execute different code depending on whether a condition is `True` or `False`.

### 2. What is the difference between `if` and `if-else`?

`if` executes code only when its condition is `True`, while `if-else` provides an alternative block when the condition is `False`.

### 3. What is the purpose of `elif`?

`elif` allows Python to check additional conditions when the previous condition was `False`.

### 4. Can an `if` statement exist without `else`?

Yes.

```python
if age >= 18:
    print("Adult")
```

### 5. Can there be multiple `elif` statements?

Yes.

```python
if condition1:
    ...
elif condition2:
    ...
elif condition3:
    ...
else:
    ...
```

### 6. What is a nested conditional statement?

A conditional statement placed inside another conditional statement is called a nested conditional statement.

### 7. What is the difference between `=` and `==`?

* `=` assigns a value.
* `==` compares two values.

Example:

```python
x = 10

if x == 10:
    print("Equal")
```

### 8. What happens when none of the `if`/`elif` conditions are true?

If an `else` block exists, Python executes the `else` block. Otherwise, the conditional structure is simply skipped.

### 9. What are truthy and falsy values?

Truthy values behave like `True` in a condition, while falsy values behave like `False`.

### 10. What is a conditional expression?

A conditional expression is a compact, single-line way to select one of two values based on a condition.

```python
result = "Pass" if mark >= 50 else "Fail"
```
---

[◀ Back](./)
---