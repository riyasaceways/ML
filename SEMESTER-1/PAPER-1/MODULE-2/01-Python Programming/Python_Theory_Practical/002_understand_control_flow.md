## Conditional Statements

**Conditional statements** allow a Python program to make decisions based on whether a condition is `True` or `False`.

### Types of Conditional Statements

* **`if` statement** — Executes a block of code when a condition is `True`.
* **`if-else` statement** — Executes one block when the condition is `True` and another when it is `False`.
* **`if-elif-else` statement** — Checks multiple conditions and executes the block for the first condition that is `True`.
* **Nested `if` statement** — Places one conditional statement inside another.
* **Conditional expression** — A short, single-line way to choose between two values based on a condition.

### Example

```python
age = 18

if age >= 18:
    print("You are eligible to vote.")
else:
    print("You are not eligible to vote.")
```

[View more details →](./Python_Detaild/conditional-statements.md)

---

## Nested Conditions

**Nested conditions** are conditional statements placed inside another conditional statement. They are useful when one decision depends on another decision.

### Example

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Access granted.")
    else:
        print("ID is required.")
else:
    print("You are underage.")
```

Here, the inner `if` is checked only when the outer condition is `True`.

[View more details →](./Python_Detaild/nested_conditions.md)

---

## Loops

**Loops** are used to execute a block of code repeatedly. They help avoid writing the same code multiple times.

### Types of Loops

* **`for` loop** — Used to iterate over items in a sequence or other iterable.
* **`while` loop** — Repeats a block of code as long as a condition remains `True`.
* **Nested loops** — A loop placed inside another loop.
* **`range()`** — Commonly used with `for` loops to generate a sequence of numbers.

### Example

```python
for number in range(1, 6):
    print(number)
```

Output:

```text
1
2
3
4
5
```

[View more details →](./Python_Detaild/loops.md)

---

## Logical Problem Solving

**Logical problem solving** is the process of breaking a programming problem into smaller steps and using logic to reach the desired result.

### Key Steps

* **Understand the problem** — Identify what the problem is asking.
* **Identify inputs and outputs** — Determine what data is needed and what result is expected.
* **Break the problem into steps** — Divide the problem into smaller, manageable tasks.
* **Apply conditions** — Use conditional statements to make decisions.
* **Use loops** — Repeat operations when necessary.
* **Test the logic** — Check the solution with different inputs and edge cases.

### Example

```python
number = int(input("Enter a number: "))

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

Here, the problem is divided into three possible cases: positive, negative, and zero.

[View more details →](./Python_Detaild/logical_problem_solving.md)
