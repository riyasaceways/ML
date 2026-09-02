[◀ Back](./)
---

# Loops in Python

## 1. What are Loops?

**Loops** are used to execute a block of code repeatedly.

Instead of writing the same code multiple times, a loop allows Python to repeat the code automatically.

For example, without a loop:

```python
print("Hello")
print("Hello")
print("Hello")
print("Hello")
print("Hello")
```

The same task can be written using a loop:

```python
for i in range(5):
    print("Hello")
```

Output:

```text
Hello
Hello
Hello
Hello
Hello
```

Loops are an important part of **control flow** in Python.

---

# 2. Types of Loops in Python

Python mainly provides two types of loops:

1. **`for` loop**
2. **`while` loop**

Python also supports:

* Nested loops
* Loop control statements such as `break`, `continue`, and `pass`

---

# 3. `for` Loop

A `for` loop is used to iterate over the items of an iterable.

An iterable can be:

* List
* Tuple
* String
* Set
* Dictionary
* Range
* And other iterable objects

### Syntax

```python
for variable in iterable:
    # code to execute
```

### Example

```python
fruits = ["apple", "banana", "orange"]

for fruit in fruits:
    print(fruit)
```

Output:

```text
apple
banana
orange
```

The loop takes each item from the list one by one and assigns it to `fruit`.

---

# 4. How a `for` Loop Works

Consider:

```python
numbers = [10, 20, 30]

for number in numbers:
    print(number)
```

The execution can be understood as:

```text
number = 10 → print(10)
number = 20 → print(20)
number = 30 → print(30)
```

After all items have been processed, the loop ends.

---

# 5. Iterating Over a String

A string is also iterable.

```python
name = "Python"

for character in name:
    print(character)
```

Output:

```text
P
y
t
h
o
n
```

Each character is processed one at a time.

---

# 6. Iterating Over a List

```python
numbers = [10, 20, 30, 40, 50]

for number in numbers:
    print(number)
```

Output:

```text
10
20
30
40
50
```

---

# 7. Iterating Over a Tuple

```python
colors = ("red", "green", "blue")

for color in colors:
    print(color)
```

Output:

```text
red
green
blue
```

---

# 8. Iterating Over a Set

```python
fruits = {"apple", "banana", "orange"}

for fruit in fruits:
    print(fruit)
```

The loop processes each element in the set.

> Sets are unordered collections, so you should not rely on a particular iteration order.

---

# 9. Iterating Over a Dictionary

When a dictionary is directly used in a `for` loop, Python iterates over its keys.

```python
student = {
    "name": "Riyas",
    "age": 20,
    "course": "Python"
}

for key in student:
    print(key)
```

Output:

```text
name
age
course
```

To access both keys and values, use `.items()`:

```python
for key, value in student.items():
    print(key, value)
```

---

# 10. The `range()` Function

`range()` is commonly used with `for` loops to generate a sequence of numbers.

### Example

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

Notice that `range(5)` starts from `0` and stops before `5`.

---

# 11. `range(start, stop)`

You can specify the starting and ending values.

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

The `stop` value is not included.

```text
range(1, 6)
       │  │
     start stop
```

Values:

```text
1, 2, 3, 4, 5
```

---

# 12. `range(start, stop, step)`

`range()` can also accept a step value.

### Syntax

```python
range(start, stop, step)
```

Example:

```python
for number in range(0, 11, 2):
    print(number)
```

Output:

```text
0
2
4
6
8
10
```

The `step` determines how much the value changes after each iteration.

---

# 13. Using a Negative Step

A negative step can be used to count backwards.

```python
for number in range(5, 0, -1):
    print(number)
```

Output:

```text
5
4
3
2
1
```

---

# 14. `while` Loop

A `while` loop repeatedly executes a block of code **as long as its condition is `True`**.

### Syntax

```python
while condition:
    # code to execute
```

### Example

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

Output:

```text
1
2
3
4
5
```

---

# 15. How a `while` Loop Works

Consider:

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

Execution:

```text
count = 1
   ↓
1 <= 3 → True → print(1)
   ↓
count = 2
   ↓
2 <= 3 → True → print(2)
   ↓
count = 3
   ↓
3 <= 3 → True → print(3)
   ↓
count = 4
   ↓
4 <= 3 → False
   ↓
Loop ends
```

The condition is checked before each iteration.

---

# 16. `for` Loop vs `while` Loop

| `for` loop                                        | `while` loop                                                     |
| ------------------------------------------------- | ---------------------------------------------------------------- |
| Commonly used for iterating over an iterable      | Commonly used when repetition depends on a condition             |
| Works naturally with lists, strings, tuples, etc. | Continues while a condition is `True`                            |
| Often used when the iteration sequence is known   | Useful when the number of iterations may not be known beforehand |
| Uses `for ... in ...` syntax                      | Uses `while condition` syntax                                    |

### Example of `for`

```python
for number in range(5):
    print(number)
```

### Example of `while`

```python
number = 0

while number < 5:
    print(number)
    number += 1
```

Both can produce similar results, but they are suited to different situations.

---

# 17. Nested Loops

A **nested loop** is a loop inside another loop.

### Example

```python
for i in range(3):
    for j in range(3):
        print(i, j)
```

Output:

```text
0 0
0 1
0 2
1 0
1 1
1 2
2 0
2 1
2 2
```

For every iteration of the outer loop, the inner loop completes all of its iterations.

---

# 18. Nested `for` Loop Example

```python
for row in range(3):
    for column in range(4):
        print("*", end=" ")
    print()
```

Output:

```text
* * * *
* * * *
* * * *
```

The outer loop controls the rows, while the inner loop controls the columns.

---

# 19. Nested `while` Loops

Nested loops are not limited to `for` loops.

A `while` loop can contain another `while` loop.

```python
row = 1

while row <= 3:
    column = 1

    while column <= 3:
        print(row, column)
        column += 1

    row += 1
```

---

# 20. Looping with Conditions

A loop can contain conditional statements.

```python
numbers = [1, 2, 3, 4, 5, 6]

for number in numbers:
    if number % 2 == 0:
        print(number)
```

Output:

```text
2
4
6
```

Here:

* The `for` loop processes each number.
* The `if` statement checks whether the number is even.

---

# 21. `break` Statement

The `break` statement immediately terminates the loop.

```python
for number in range(1, 10):
    if number == 5:
        break

    print(number)
```

Output:

```text
1
2
3
4
```

When `number` becomes `5`, `break` stops the loop.

---

# 22. `continue` Statement

The `continue` statement skips the current iteration and moves to the next iteration.

```python
for number in range(1, 6):
    if number == 3:
        continue

    print(number)
```

Output:

```text
1
2
4
5
```

The value `3` is skipped.

---

# 23. `pass` Statement

The `pass` statement does nothing.

It can be used as a placeholder when a statement is syntactically required but no action is needed yet.

```python
for number in range(5):
    pass
```

The loop runs, but nothing happens inside it.

---

# 24. `else` with Loops

Python allows an `else` block with both `for` and `while` loops.

### Example

```python
for number in range(5):
    print(number)
else:
    print("Loop completed.")
```

Output:

```text
0
1
2
3
4
Loop completed.
```

The loop's `else` block executes when the loop finishes normally.

---

# 25. `else` with `break`

If the loop is terminated using `break`, the loop's `else` block does not execute.

```python
for number in range(1, 6):
    if number == 3:
        break

    print(number)
else:
    print("Loop completed.")
```

Output:

```text
1
2
```

The `break` prevents the loop from completing normally, so the `else` block is skipped.

---

# 26. Infinite `while` Loop

A `while` loop can become infinite if its condition never becomes `False`.

Example:

```python
count = 1

while count <= 5:
    print(count)
```

Here, `count` never changes, so:

```python
count <= 5
```

remains `True`.

A common way to intentionally create an infinite loop is:

```python
while True:
    print("Running...")
```

Such loops generally need a `break` condition.

```python
while True:
    command = input("Enter 'q' to quit: ")

    if command == "q":
        break
```

---

# 27. Modifying a Loop Variable

A common mistake with `while` loops is forgetting to update the variable controlling the condition.

Incorrect:

```python
count = 1

while count <= 5:
    print(count)
```

Correct:

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

The update allows the condition to eventually become `False`.

---

# 28. Looping Through User Input

Loops are useful for repeatedly accepting input.

```python
while True:
    name = input("Enter your name: ")

    if name == "q":
        break

    print("Hello", name)
```

The loop continues until the user enters `q`.

---

# 29. Practical Example: Sum of Numbers

```python
numbers = [10, 20, 30, 40, 50]

total = 0

for number in numbers:
    total += number

print("Total:", total)
```

Output:

```text
Total: 150
```

The loop adds each number to `total`.

---

# 30. Practical Example: Finding an Item

```python
fruits = ["apple", "banana", "orange", "mango"]

for fruit in fruits:
    if fruit == "orange":
        print("Orange found.")
        break
```

Once `"orange"` is found, `break` stops the loop.

---

# 31. Practical Example: Multiplication Table

```python
number = 5

for i in range(1, 11):
    print(number, "x", i, "=", number * i)
```

Output:

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

---

# 32. Practical Example: Counting Even Numbers

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8]

count = 0

for number in numbers:
    if number % 2 == 0:
        count += 1

print("Even numbers:", count)
```

Output:

```text
Even numbers: 4
```

---

# 33. Practical Example: Password Attempts

```python
correct_password = "python123"
attempts = 3

while attempts > 0:
    password = input("Enter password: ")

    if password == correct_password:
        print("Login successful.")
        break

    attempts -= 1
    print("Incorrect password.")

if attempts == 0:
    print("Too many attempts.")
```

This example combines:

* `while`
* `if`
* `break`
* variables
* comparison
* user input

---

# 34. Common Mistakes

## Mistake 1: Forgetting to Update a `while` Loop

```python
count = 1

while count <= 5:
    print(count)
```

This can create an infinite loop.

Correct:

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

---

## Mistake 2: Incorrect `range()` Expectation

```python
for number in range(1, 5):
    print(number)
```

Output:

```text
1
2
3
4
```

The stop value `5` is not included.

---

## Mistake 3: Modifying a Collection While Iterating

Changing a collection directly while iterating over it can lead to unexpected behavior.

Instead, when necessary, iterate over a copy or construct a new collection.

---

## Mistake 4: Unnecessary Nested Loops

Nested loops can increase the amount of work significantly.

Before using a nested loop, consider whether the problem can be solved more simply.

---

# 35. Loop Execution Flow

### `for` loop

```text
Iterable
   ↓
Get next item
   ↓
Execute loop body
   ↓
More items?
 ┌───────┴───────┐
Yes              No
 │                │
 └──→ Repeat      ↓
               Loop ends
```

### `while` loop

```text
Check condition
      ↓
   True?
  ┌───┴───┐
 Yes      No
  │        │
  ↓        ↓
Execute   Loop ends
body
  │
  └──→ Check condition again
```

---

# 36. Quick Reference

| Feature     | Purpose                                  |
| ----------- | ---------------------------------------- |
| `for`       | Iterate over an iterable                 |
| `while`     | Repeat while a condition is true         |
| `range()`   | Generate a sequence of numbers           |
| Nested loop | Place one loop inside another            |
| `break`     | Stop the loop immediately                |
| `continue`  | Skip the current iteration               |
| `pass`      | Do nothing; act as a placeholder         |
| Loop `else` | Execute when the loop completes normally |

---

# 37. Key Points to Remember

* Loops allow code to be **repeated automatically**.
* Python mainly provides `for` and `while` loops.
* A `for` loop is commonly used to iterate over an iterable.
* A `while` loop continues while its condition is `True`.
* `range()` is commonly used with `for` loops.
* Loops can be nested.
* `break` terminates a loop.
* `continue` skips the current iteration.
* `pass` acts as a placeholder.
* Both `for` and `while` loops can have an `else` block.
* Be careful with `while` loops to avoid unintended infinite loops.
* Loops become especially powerful when combined with conditional statements.

---

# 38. Interview Questions

### 1. What is a loop?

A loop is a control-flow structure used to execute a block of code repeatedly.

### 2. What are the types of loops in Python?

Python mainly provides:

* `for` loop
* `while` loop

### 3. What is the difference between `for` and `while`?

A `for` loop is commonly used to iterate over an iterable, while a `while` loop repeats code as long as a condition remains `True`.

### 4. What is `range()` used for?

`range()` generates a sequence of numbers and is commonly used with `for` loops.

### 5. What does `break` do?

`break` immediately terminates the current loop.

### 6. What does `continue` do?

`continue` skips the current iteration and proceeds to the next iteration.

### 7. What does `pass` do?

`pass` performs no operation and is commonly used as a placeholder.

### 8. What is a nested loop?

A nested loop is a loop placed inside another loop.

### 9. What is an infinite loop?

An infinite loop is a loop that continues indefinitely because its termination condition never becomes `False`.

### 10. Can a loop have an `else` block?

Yes. Python supports `else` blocks with both `for` and `while` loops. The `else` block runs when the loop completes normally, but not when the loop is terminated by `break`.

### 11. Why is indentation important in loops?

Indentation determines which statements belong to the loop body.

Example:

```python
for number in range(3):
    print(number)
```

The indented `print()` statement belongs to the loop.

[◀ Back](./)
---