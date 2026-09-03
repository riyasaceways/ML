[◀Back](.././)
---


# Except in Python

## What is `except`?

The **`except` statement** is used with `try` to handle exceptions.

When an exception occurs inside a `try` block, Python looks for an appropriate `except` block to handle it.

Basic structure:

```python
try:
    # Code that may cause an exception

except:
    # Code that handles the exception
```

A better approach is to specify the expected exception:

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Invalid number.")
```

---

# Why Use `except`?

Without exception handling:

```python
number = int(input("Enter a number: "))
```

If the user enters:

```text
abc
```

Python raises a `ValueError` and the program stops if nothing handles it.

With `except`:

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Please enter a valid number.")
```

The program can respond to the error.

---

# Basic `except`

```python
try:
    result = 10 / 0

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

Output:

```text
Cannot divide by zero.
```

The `except` block runs because the `try` block raised a `ZeroDivisionError`.

---

# Specific Exceptions

It is usually better to catch a specific exception.

```python
try:
    number = int("hello")

except ValueError:
    print("The value is not a valid integer.")
```

Here, only `ValueError` is being handled.

This makes the program's error handling more precise.

---

# Multiple `except` Blocks

A `try` statement can have multiple `except` blocks.

```python
try:
    number = int(input("Enter a number: "))
    result = 10 / number

except ValueError:
    print("Please enter a valid number.")

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

Different errors can therefore receive different responses.

---

# How Python Chooses an `except`

Python checks the `except` blocks from top to bottom.

It executes the **first matching handler**.

For example:

```python
try:
    number = int("abc")

except ValueError:
    print("Value error.")

except TypeError:
    print("Type error.")
```

The first handler matches `ValueError`, so it runs.

Python does not continue to the next `except` after a matching handler has been selected.

---

# Exception Object with `as`

An exception can be stored in a variable using `as`.

```python
try:
    number = int("abc")

except ValueError as error:
    print(error)
```

The variable `error` contains information about the exception.

Example output:

```text
invalid literal for int() with base 10: 'abc'
```

This can be useful for logging or displaying useful error information.

---

# Multiple Exceptions in One `except`

If several exceptions should be handled in the same way, they can be grouped.

```python
try:
    number = int(input("Enter a number: "))
    result = 10 / number

except (ValueError, ZeroDivisionError):
    print("Invalid operation.")
```

This single handler catches either:

* `ValueError`
* `ZeroDivisionError`

---

# `except Exception`

`Exception` is a general base class for many normal runtime exceptions.

```python
try:
    result = 10 / 0

except Exception as error:
    print("An error occurred:", error)
```

Output:

```text
An error occurred: division by zero
```

This is broader than:

```python
except ZeroDivisionError:
```

Specific exception handling is generally preferable when the expected error is known.

---

# Bare `except`

Python allows:

```python
try:
    risky_operation()

except:
    print("Something went wrong.")
```

A bare `except` catches almost any exception.

However, it is generally discouraged because it can hide unexpected problems.

Prefer:

```python
try:
    number = int(user_input)

except ValueError:
    print("Invalid number.")
```

---

# Exception Hierarchy and `except`

Python exceptions are organized into a hierarchy.

A simplified example:

```text
Exception
   │
   ├── ValueError
   ├── TypeError
   ├── ArithmeticError
   │      └── ZeroDivisionError
   └── OSError
          └── FileNotFoundError
```

Because specific exceptions inherit from broader exceptions, a broader handler can also catch them.

For example:

```python
try:
    number = int("abc")

except Exception:
    print("Error occurred.")
```

`Exception` catches the `ValueError`.

---

# Specific Before General

When using specific and general handlers together, put the specific handler first.

Correct:

```python
try:
    number = int("abc")

except ValueError:
    print("Invalid value.")

except Exception:
    print("Other error.")
```

The specific `ValueError` handler gets the opportunity to handle the error first.

Avoid putting the general handler first:

```python
try:
    number = int("abc")

except Exception:
    print("Error.")

except ValueError:
    print("Invalid value.")
```

The `ValueError` handler will never be reached for that exception because `Exception` already matches it.

---

# `except` with `else`

An `except` block can be combined with `else`.

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Invalid input.")

else:
    print("Valid number:", number)
```

If an exception occurs:

```text
try → except
```

If no exception occurs:

```text
try → else
```

---

# `except` with `finally`

`finally` runs regardless of whether an exception occurs.

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Invalid input.")

finally:
    print("Finished.")
```

Flow when an error occurs:

```text
try
 ↓
except
 ↓
finally
```

Flow when there is no error:

```text
try
 ↓
finally
```

---

# Handling `FileNotFoundError`

`except` is commonly used when working with files.

```python
try:
    with open("students.txt", "r", encoding="utf-8") as file:
        data = file.read()

except FileNotFoundError:
    print("The file does not exist.")
```

---

# Handling JSON Errors

```python
import json

try:
    with open("student.json", "r", encoding="utf-8") as file:
        data = json.load(file)

except FileNotFoundError:
    print("JSON file not found.")

except json.JSONDecodeError:
    print("Invalid JSON format.")
```

Different errors can therefore be handled separately.

---

# Handling `IndexError`

An invalid list index raises `IndexError`.

```python
numbers = [10, 20, 30]

try:
    print(numbers[5])

except IndexError:
    print("List index does not exist.")
```

---

# Handling `KeyError`

Accessing a missing dictionary key can raise `KeyError`.

```python
student = {
    "name": "Riyas"
}

try:
    print(student["mark"])

except KeyError:
    print("Mark is not available.")
```

Output:

```text
Mark is not available.
```

---

# Handling `TypeError`

A `TypeError` can occur when incompatible types are used together.

```python
try:
    result = "10" + 5

except TypeError:
    print("Cannot combine these data types.")
```

---

# Handling `ValueError`

A `ValueError` occurs when a value has the correct general type but an inappropriate value.

Example:

```python
try:
    number = int("abc")

except ValueError:
    print("Cannot convert the value to an integer.")
```

---

# Handling User Input

One of the most common uses of `except` is handling invalid user input.

```python
while True:
    try:
        age = int(input("Enter your age: "))
        break

    except ValueError:
        print("Please enter a valid number.")

print("Age:", age)
```

The program continues asking until a valid integer is entered.

---

# `except` Inside a Function

Exception handling can be placed inside a function.

```python
def divide(a, b):
    try:
        return a / b

    except ZeroDivisionError:
        return None
```

Usage:

```python
result = divide(10, 0)

print(result)
```

Output:

```text
None
```

---

# Handling the Exception Outside the Function

Alternatively, the function can allow the exception to propagate.

```python
def divide(a, b):
    return a / b


try:
    result = divide(10, 0)

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

This allows the caller to decide how the exception should be handled.

---

# Re-Raising an Exception

Sometimes an exception needs to be handled partially and then passed to another level.

```python
try:
    number = int("abc")

except ValueError:
    print("Logging error...")
    raise
```

The bare `raise` inside the `except` block re-raises the current exception.

---

# `except` and `raise`

An exception can also be caught and replaced with another exception.

```python
try:
    number = int("abc")

except ValueError:
    raise RuntimeError("Unable to process the number.")
```

This can be useful when creating clearer application-level errors.

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
```

---

# Practical Example: Student Marks

```python
try:
    mark = int(input("Enter mark: "))

except ValueError:
    print("Mark must be a number.")

else:
    if 0 <= mark <= 100:
        print("Valid mark.")
    else:
        print("Mark must be between 0 and 100.")
```

Notice that not every invalid condition is an exception.

For example, `150` successfully converts to an integer, so no `ValueError` occurs. The range must be checked separately.

---

# Exception Handling vs Validation

These are related but different.

### Exception handling

Handles an operation that raises an exception.

```python
try:
    number = int(user_input)

except ValueError:
    print("Invalid number.")
```

### Validation

Checks whether a value satisfies a rule.

```python
if number < 0:
    print("Number cannot be negative.")
```

A program can use both.

---

# Good Exception Handling

Good:

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Please enter a valid integer.")
```

Why?

* The expected exception is specified.
* The error message is meaningful.
* The handler handles a known problem.

---

# Poor Exception Handling

```python
try:
    number = int(input("Enter a number: "))

except:
    pass
```

Problems:

* It catches too broadly.
* It silently ignores the error.
* It makes debugging difficult.
* Unexpected errors can be hidden.

---

# Keep the `try` Block Focused

Avoid placing unrelated operations inside one large `try` block.

Instead of:

```python
try:
    number = int(input())
    name = input()
    data = read_file()
    process_data()
    save_data()

except Exception:
    print("Something went wrong.")
```

Prefer handling operations where appropriate:

```python
try:
    number = int(input())

except ValueError:
    print("Invalid number.")
```

This makes it clearer which operation caused the expected error.

---

# Common Mistakes

### 1. Catching the Wrong Exception

```python
try:
    number = int("abc")

except ZeroDivisionError:
    print("Error.")
```

This does not handle the `ValueError`.

Correct:

```python
except ValueError:
    print("Invalid number.")
```

---

### 2. Catching Everything

Avoid unnecessarily broad handling:

```python
except:
    pass
```

Prefer a specific exception.

---

### 3. Putting a General Handler First

Avoid:

```python
except Exception:
    print("Error.")

except ValueError:
    print("Invalid value.")
```

Put specific handlers first.

---

### 4. Hiding Errors

Avoid:

```python
except Exception:
    pass
```

If an error is caught, there should usually be a meaningful reason for handling it.

---

### 5. Assuming `except` Prevents the Exception

`except` does not prevent the exception.

The exception occurs inside the `try` block, and the matching `except` block handles it.

---

# Quick Reference

### Specific exception

```python
try:
    risky_code()

except ValueError:
    handle_error()
```

### Exception object

```python
try:
    risky_code()

except ValueError as error:
    print(error)
```

### Multiple exceptions

```python
try:
    risky_code()

except (ValueError, TypeError):
    print("Invalid data.")
```

### Multiple handlers

```python
try:
    risky_code()

except ValueError:
    print("Value error.")

except TypeError:
    print("Type error.")
```

### General exception

```python
try:
    risky_code()

except Exception as error:
    print(error)
```

### Re-raise

```python
try:
    risky_code()

except ValueError:
    raise
```

---

# Key Points

* `except` is used with `try` to handle exceptions.
* A specific exception can be handled using its exception class.
* Multiple `except` blocks can handle different errors.
* The first matching `except` block is executed.
* `as` can store the exception object.
* Multiple exception types can be handled in one `except`.
* `except Exception` provides broader exception handling.
* Bare `except` should generally be avoided.
* Specific handlers should come before general handlers.
* `except` can be combined with `else` and `finally`.
* `raise` can re-raise an exception from an `except` block.
* Exception handling and normal validation are different concepts.
* Good exception handling should handle known problems without silently hiding unexpected errors.

---

# Interview Questions

### 1. What is `except` in Python?

`except` is used with `try` to catch and handle exceptions raised during program execution.

### 2. Can a `try` block have multiple `except` blocks?

Yes. Different exception types can have separate handlers.

### 3. What is `except Exception`?

It catches most exceptions derived from Python's `Exception` base class.

### 4. What is a bare `except`?

A bare `except` does not specify an exception type and can catch almost any exception. It should generally be avoided when more precise handling is possible.

### 5. How do you get the error message from an exception?

Use `as`:

```python
except ValueError as error:
    print(error)
```

### 6. Can multiple exceptions be handled by one `except`?

Yes:

```python
except (ValueError, TypeError):
    print("Invalid data.")
```

### 7. Which `except` block executes if multiple handlers could match?

Python executes the first matching `except` block.

### 8. Why should specific exceptions come before general exceptions?

Because a general handler such as `except Exception` can also match more specific exceptions. If it comes first, the later specific handler may never be reached.

### 9. What happens if no `except` block matches?

The exception is not handled by that `try` statement and propagates to an outer handler. If nothing handles it, the program terminates with a traceback.

### 10. What is the difference between `except` and `finally`?

`except` runs when a matching exception occurs. `finally` runs whether an exception occurs or not.

---

[◀Back](.././)
---