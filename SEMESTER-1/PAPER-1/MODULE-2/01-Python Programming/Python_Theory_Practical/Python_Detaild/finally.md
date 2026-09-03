[◀Back](.././)
---


# Finally in Python

## What is `finally`?

The **`finally` block** is used with `try` and `except` to execute code regardless of whether an exception occurs.

Basic structure:

```python
try:
    # Code that may cause an exception

except SomeError:
    # Handle the exception

finally:
    # Code that should run afterward
```

The main purpose of `finally` is to perform **cleanup operations**.

---

# Basic Example

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Invalid number.")

finally:
    print("Execution completed.")
```

If the user enters a valid number:

```text
try
 ↓
finally
```

If the user enters an invalid value:

```text
try
 ↓
except
 ↓
finally
```

In both cases, `finally` runs.

---

# Why Use `finally`?

Some operations require cleanup regardless of whether they succeed.

Examples:

* Closing a file
* Closing a database connection
* Releasing a resource
* Closing a network connection
* Cleaning temporary resources
* Restoring a state

The important idea is:

> **The cleanup code should run whether the operation succeeds or fails.**

---

# `finally` with `try` and `except`

The most common structure is:

```python
try:
    risky_operation()

except ValueError:
    print("An error occurred.")

finally:
    print("Cleanup completed.")
```

The `finally` block runs after the `try` or `except` block.

---

# `finally` Without `except`

A `try` block does not always need an `except` block.

You can use:

```python
try:
    risky_operation()

finally:
    cleanup()
```

Example:

```python
file = open("data.txt", "r", encoding="utf-8")

try:
    data = file.read()

finally:
    file.close()
```

Even if an exception occurs while reading the file, the `finally` block attempts to close the file.

For normal file handling, however, `with open()` is generally preferred because it automatically manages the file resource.

---

# `finally` with `else`

`finally` can be combined with `else`.

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Invalid input.")

else:
    print("Valid input:", number)

finally:
    print("Finished.")
```

If the input is valid:

```text
try
 ↓
else
 ↓
finally
```

If the input is invalid:

```text
try
 ↓
except
 ↓
finally
```

---

# Complete `try` Structure

The complete structure is:

```python
try:
    # Code that may raise an exception

except SomeError:
    # Handle the exception

else:
    # Runs if no exception occurs

finally:
    # Runs regardless
```

Remember the order:

```text
try
 ↓
except / else
 ↓
finally
```

---

# `finally` and Exceptions

Consider:

```python
try:
    number = int("abc")

except ValueError:
    print("Invalid value.")

finally:
    print("Finally executed.")
```

Output:

```text
Invalid value.
Finally executed.
```

The exception was handled by `except`, and then `finally` executed.

---

# `finally` When No Exception Occurs

```python
try:
    number = int("100")

except ValueError:
    print("Invalid value.")

finally:
    print("Finally executed.")
```

Output:

```text
Finally executed.
```

The `except` block does not run because no exception occurred.

The `finally` block still runs.

---

# `finally` When an Exception Is Not Handled

Consider:

```python
try:
    result = 10 / 0

finally:
    print("Cleanup executed.")
```

Output includes:

```text
Cleanup executed.
```

Then the unhandled `ZeroDivisionError` propagates.

This demonstrates an important point:

**`finally` does not handle the exception.**

It performs its required final actions, while the exception can still propagate afterward.

---

# `finally` Does Not Handle Errors

This:

```python
try:
    number = int("abc")

finally:
    print("Finished.")
```

does not catch the `ValueError`.

To handle the exception, use `except`:

```python
try:
    number = int("abc")

except ValueError:
    print("Invalid value.")

finally:
    print("Finished.")
```

The responsibilities are different:

```text
try     → attempt the operation
except  → handle the exception
else    → run after successful try
finally → perform final/cleanup actions
```

---

# `finally` with Files

A traditional approach to file cleanup is:

```python
file = None

try:
    file = open("data.txt", "r", encoding="utf-8")
    data = file.read()

finally:
    if file is not None:
        file.close()
```

The file is closed in `finally`.

However, Python provides a cleaner approach:

```python
with open("data.txt", "r", encoding="utf-8") as file:
    data = file.read()
```

The `with` statement is generally preferred for managing files.

---

# `finally` with Multiple Exceptions

```python
try:
    number = int(input("Enter a number: "))
    result = 10 / number

except ValueError:
    print("Invalid number.")

except ZeroDivisionError:
    print("Cannot divide by zero.")

finally:
    print("Operation finished.")
```

Regardless of which exception occurs, the `finally` block runs.

---

# Practical Example: Calculator

```python
try:
    first = float(input("Enter first number: "))
    second = float(input("Enter second number: "))

    result = first / second

except ValueError:
    print("Please enter valid numbers.")

except ZeroDivisionError:
    print("Cannot divide by zero.")

else:
    print("Result:", result)

finally:
    print("Calculator closed.")
```

---

# Practical Example: JSON File

```python
import json

file = None

try:
    file = open("student.json", "r", encoding="utf-8")
    data = json.load(file)

except FileNotFoundError:
    print("File not found.")

except json.JSONDecodeError:
    print("Invalid JSON.")

finally:
    if file is not None:
        file.close()
```

Again, `with open()` is generally cleaner:

```python
import json

try:
    with open("student.json", "r", encoding="utf-8") as file:
        data = json.load(file)

except FileNotFoundError:
    print("File not found.")

except json.JSONDecodeError:
    print("Invalid JSON.")
```

The context manager handles file cleanup automatically.

---

# `finally` and `return`

An important behavior is that `finally` runs even when the `try` or `except` block contains `return`.

```python
def example():
    try:
        return "Try"

    finally:
        print("Finally executed.")


result = example()
print(result)
```

Output:

```text
Finally executed.
Try
```

The `finally` block runs before the function actually returns.

---

# `return` in `finally`

Although possible, returning from `finally` is generally discouraged.

Example:

```python
def example():
    try:
        return "Try"

    finally:
        return "Finally"
```

The `finally` return overrides the earlier return.

```python
print(example())
```

Output:

```text
Finally
```

This can make program behavior confusing, so it is generally better to avoid `return` statements in `finally`.

---

# `finally` with Loops

`finally` can also be used when a `try` block is inside a loop.

```python
for number in range(3):
    try:
        print(10 / number)

    except ZeroDivisionError:
        print("Cannot divide by zero.")

    finally:
        print("Iteration completed.")
```

The `finally` block runs for each iteration.

---

# `finally` and `break`

If a `break` occurs inside a `try` block, the `finally` block still executes before leaving the structure.

```python
for number in range(5):
    try:
        if number == 2:
            break

        print(number)

    finally:
        print("Finally executed.")
```

The `finally` block executes even when the loop is exited with `break`.

---

# `finally` and `continue`

Similarly, `finally` executes before a `continue` takes effect.

```python
for number in range(3):
    try:
        if number == 1:
            continue

        print(number)

    finally:
        print("Finally executed.")
```

The cleanup code still runs.

---

# Resource Cleanup

One of the most important uses of `finally` is ensuring that resources are released.

Conceptually:

```text
Acquire resource
       ↓
     try
       ↓
Use resource
       ↓
   finally
       ↓
Release resource
```

Examples of resources include:

* Files
* Database connections
* Network connections
* Locks
* Temporary resources

---

# `finally` vs `with`

Both can be used for resource management, but they serve different purposes.

### Using `finally`

```python
file = open("data.txt", "r", encoding="utf-8")

try:
    data = file.read()

finally:
    file.close()
```

### Using `with`

```python
with open("data.txt", "r", encoding="utf-8") as file:
    data = file.read()
```

For files, `with` is usually simpler and safer.

`finally` is still useful when you need custom cleanup logic that is not naturally handled by a context manager.

---

# Common Mistakes

## 1. Thinking `finally` Catches Exceptions

Incorrect understanding:

```text
finally → catches errors
```

Correct:

```text
except → handles errors
finally → performs final/cleanup actions
```

---

## 2. Assuming `finally` Runs Only When There Is an Error

It does not.

```python
try:
    print("Success")

finally:
    print("Always runs")
```

Output:

```text
Success
Always runs
```

---

## 3. Putting `return` in `finally`

Avoid:

```python
def example():
    try:
        return 10

    finally:
        return 20
```

The `finally` return overrides the previous return and can make code difficult to understand.

---

## 4. Using `finally` When `with` Is Better

For simple file operations:

```python
with open("data.txt", "r", encoding="utf-8") as file:
    data = file.read()
```

is generally preferable to manually opening and closing the file with `finally`.

---

# Execution Summary

### No exception

```text
try
 ↓
else
 ↓
finally
```

### Exception handled

```text
try
 ↓
except
 ↓
finally
```

### Exception not handled

```text
try
 ↓
finally
 ↓
exception propagates
```

---

# Quick Reference

### Basic

```python
try:
    risky_code()

finally:
    cleanup()
```

### With `except`

```python
try:
    risky_code()

except ValueError:
    handle_error()

finally:
    cleanup()
```

### Complete structure

```python
try:
    risky_code()

except ValueError:
    handle_error()

else:
    success_code()

finally:
    cleanup()
```

### File cleanup

```python
file = open("data.txt", "r", encoding="utf-8")

try:
    data = file.read()

finally:
    file.close()
```

---

# Key Points

* `finally` is used for code that should run after a `try` statement.
* It normally runs whether an exception occurs or not.
* `finally` does not handle exceptions; `except` does.
* `finally` is commonly used for cleanup.
* It can be used with `try` without an `except`.
* It can be combined with `try`, `except`, and `else`.
* `finally` executes before a function returns.
* `finally` also executes when leaving a `try` block through `break` or `continue`.
* Returning from `finally` can override an earlier return and should generally be avoided.
* For file handling, `with open()` is usually preferable to manual cleanup with `finally`.
* `finally` is particularly useful when resources must be released regardless of success or failure.

---

# Interview Questions

### 1. What is `finally` in Python?

`finally` is a block used to execute code after a `try` statement, regardless of whether an exception occurs.

### 2. Does `finally` execute when there is no exception?

Yes.

### 3. Does `finally` handle exceptions?

No. `except` handles exceptions. `finally` is primarily used for final or cleanup operations.

### 4. Can `finally` be used without `except`?

Yes.

```python
try:
    operation()

finally:
    cleanup()
```

### 5. What is the difference between `except` and `finally`?

`except` handles matching exceptions, while `finally` executes final or cleanup code regardless of whether an exception occurs.

### 6. Does `finally` execute before a `return`?

Normally, yes. The `finally` block executes before the function actually returns.

### 7. What happens if `finally` contains a `return`?

Its return can override a return from the `try` or `except` block.

### 8. Why is `finally` useful for resource management?

It provides a place to release resources even when an operation fails.

### 9. Is `finally` required when using `try`?

No. A `try` statement can use `except`, `else`, `finally`, or appropriate combinations of them.

### 10. Is `finally` necessary for closing files in Python?

Not usually. For files, `with open()` is generally preferred because the context manager handles closing the file automatically.


---


[◀Back](.././)
---