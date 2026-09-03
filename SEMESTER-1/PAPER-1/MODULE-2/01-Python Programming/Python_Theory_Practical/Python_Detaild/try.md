[◀Back](.././)
---




# Try and Exception Handling in Python

## What is `try`?

The **`try` statement** is used to test a block of code for exceptions.

An exception is an error that occurs while a program is running and interrupts the normal flow of execution.

For example:

```python
number = int(input("Enter a number: "))
```

If the user enters:

```text
abc
```

Python cannot convert `"abc"` into an integer and raises a `ValueError`.

We can handle this using `try` and `except`.

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("Please enter a valid number.")
```

---

# Basic `try` and `except`

The basic structure is:

```python
try:
    # Code that may cause an exception
except:
    # Code that handles the exception
```

Example:

```python
try:
    number = int(input("Enter a number: "))
    print(number)
except:
    print("Something went wrong.")
```

However, using a bare `except` is usually not recommended because it can hide unexpected errors.

It is generally better to catch a specific exception.

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("Invalid number.")
```

---

# Why Use `try`?

Without exception handling:

```python
number = int(input("Enter a number: "))
print("Program continues...")
```

If the user enters invalid data, the program may terminate with an error.

With exception handling:

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("Invalid number.")

print("Program continues...")
```

The program can handle the expected error and continue.

---

# The `except` Block

The `except` block contains the code that runs when a matching exception occurs.

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

---

# Common Exceptions

Some common Python exceptions include:

| Exception           | Example situation        |
| ------------------- | ------------------------ |
| `ValueError`        | Invalid value conversion |
| `TypeError`         | Incompatible data types  |
| `ZeroDivisionError` | Dividing by zero         |
| `IndexError`        | Invalid list index       |
| `KeyError`          | Missing dictionary key   |
| `FileNotFoundError` | File does not exist      |
| `NameError`         | Variable does not exist  |
| `AttributeError`    | Invalid object attribute |
| `ImportError`       | Import problem           |

---

# Handling Different Exceptions

Multiple `except` blocks can be used.

```python
try:
    number = int(input("Enter a number: "))
    result = 10 / number
    print(result)

except ValueError:
    print("Please enter a valid number.")

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

If the user enters:

```text
abc
```

the `ValueError` handler runs.

If the user enters:

```text
0
```

the `ZeroDivisionError` handler runs.

---

# Exception Object

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

---

# The `else` Block

The `else` block runs **only when the `try` block does not raise an exception**.

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Invalid number.")

else:
    print("Valid number:", number)
```

If the user enters:

```text
25
```

Output:

```text
Valid number: 25
```

If the user enters invalid data, the `except` block runs and `else` does not.

---

# The `finally` Block

The `finally` block runs **whether an exception occurs or not**.

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Invalid number.")

finally:
    print("Program finished.")
```

The `finally` block is commonly used for cleanup operations.

---

# `try`, `except`, `else`, and `finally`

All four can be used together.

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Invalid input.")

else:
    print("Valid input:", number)

finally:
    print("Execution completed.")
```

The general structure is:

```python
try:
    # Code that may raise an exception

except SomeError:
    # Handle exception

else:
    # Runs if no exception occurred

finally:
    # Always runs
```

---

# Execution Flow

Consider:

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Invalid input.")

else:
    print("Valid input.")

finally:
    print("Done.")
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

# `try` with File Handling

`try` is useful when working with files because a file may not exist.

```python
try:
    with open("students.txt", "r", encoding="utf-8") as file:
        data = file.read()

except FileNotFoundError:
    print("File not found.")
```

This prevents a missing file from immediately terminating the program.

---

# `try` with JSON Files

JSON data may be invalid.

```python
import json

try:
    with open("student.json", "r", encoding="utf-8") as file:
        data = json.load(file)

except FileNotFoundError:
    print("File not found.")

except json.JSONDecodeError:
    print("Invalid JSON format.")
```

Different problems can therefore have different responses.

---

# `try` with User Input

A common use of exception handling is validating numerical input.

```python
try:
    age = int(input("Enter your age: "))
    print("Age:", age)

except ValueError:
    print("Age must be a number.")
```

If the user enters:

```text
25
```

the conversion succeeds.

If the user enters:

```text
twenty five
```

a `ValueError` occurs.

---

# Handling Multiple Exceptions Together

If multiple exceptions should have the same response, they can be grouped.

```python
try:
    number = int(input("Enter a number: "))
    result = 10 / number

except (ValueError, ZeroDivisionError):
    print("Invalid operation.")
```

This handles both:

* `ValueError`
* `ZeroDivisionError`

with the same `except` block.

---

# Catching `Exception`

Python provides the general `Exception` class.

```python
try:
    result = 10 / 0

except Exception as error:
    print("An error occurred:", error)
```

This can catch many normal runtime exceptions.

However, it should not automatically replace specific exception handling.

Prefer:

```python
except ValueError:
```

when you know the expected problem.

Use:

```python
except Exception as error:
```

when a broader fallback is genuinely appropriate.

---

# Bare `except`

Python allows:

```python
try:
    something()
except:
    print("Error")
```

But this is usually discouraged.

A bare `except` can catch almost anything, including exceptions that you may not intend to handle.

Better:

```python
try:
    something()
except ValueError:
    print("Invalid value.")
```

---

# Raising an Exception with `raise`

The `raise` statement can manually generate an exception.

```python
age = -5

if age < 0:
    raise ValueError("Age cannot be negative.")
```

Output:

```text
ValueError: Age cannot be negative.
```

This is useful when a program detects invalid data itself.

---

# `raise` with `try`

An exception can be raised inside a `try` block and then handled.

```python
try:
    age = -5

    if age < 0:
        raise ValueError("Age cannot be negative.")

except ValueError as error:
    print(error)
```

Output:

```text
Age cannot be negative.
```

---

# Re-Raising an Exception

An exception can be caught and then raised again.

```python
try:
    number = int("abc")

except ValueError:
    print("Logging the error...")
    raise
```

The `raise` statement without an exception name re-raises the currently handled exception.

This is useful when you want to perform some action and still allow the error to propagate.

---

# Nested `try`

A `try` block can exist inside another `try` block.

```python
try:
    try:
        number = int(input("Enter a number: "))
        print(10 / number)

    except ValueError:
        print("Invalid number.")

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

Although possible, deeply nested exception handling can make code difficult to understand.

---

# `try` Inside a Loop

Exception handling can be used inside loops to repeatedly request valid input.

```python
while True:
    try:
        number = int(input("Enter a number: "))
        break

    except ValueError:
        print("Please enter a valid number.")
```

The loop continues until valid input is entered.

---

# `try` and Functions

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

# Exception Handling Outside a Function

The function can also allow the exception to propagate and handle it where the function is called.

```python
def divide(a, b):
    return a / b


try:
    result = divide(10, 0)

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

This separates the operation from the decision about how to handle the error.

---

# `finally` and Resource Cleanup

One important use of `finally` is cleanup.

```python
file = None

try:
    file = open("data.txt", "r", encoding="utf-8")
    data = file.read()

except FileNotFoundError:
    print("File not found.")

finally:
    if file is not None:
        file.close()
```

However, when working with files, `with open()` is generally preferred because it handles closing the file automatically.

```python
with open("data.txt", "r", encoding="utf-8") as file:
    data = file.read()
```

---

# Exception Handling Does Not Mean Ignoring Errors

Bad approach:

```python
try:
    risky_operation()

except:
    pass
```

This silently ignores the error.

Problems can become difficult to discover and debug.

Better:

```python
try:
    risky_operation()

except ValueError as error:
    print("Invalid value:", error)
```

Handle the error meaningfully.

---

# Validation vs Exception Handling

Validation can prevent some errors before they occur.

For example:

```python
age = int(input("Enter age: "))

if age >= 18:
    print("Adult")
```

But the conversion itself can fail if the user enters invalid text.

Therefore:

```python
try:
    age = int(input("Enter age: "))

except ValueError:
    print("Please enter a valid age.")

else:
    if age >= 18:
        print("Adult")
```

Exception handling and normal validation can work together.

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
    print("Calculator finished.")
```

---

# Practical Example: Student Marks

```python
try:
    mark = int(input("Enter mark: "))

    if mark < 0 or mark > 100:
        raise ValueError("Mark must be between 0 and 100.")

except ValueError as error:
    print("Invalid mark:", error)

else:
    print("Mark accepted:", mark)
```

Here, `ValueError` can occur either from:

```python
int(input(...))
```

or from the manually raised exception.

---

# Practical Example: Reading a JSON File

```python
import json

try:
    with open("students.json", "r", encoding="utf-8") as file:
        students = json.load(file)

except FileNotFoundError:
    print("The file does not exist.")

except json.JSONDecodeError:
    print("The JSON file contains invalid data.")

else:
    print("Students loaded successfully.")

finally:
    print("JSON processing completed.")
```

---

# Exception Hierarchy

Python exceptions follow an inheritance hierarchy.

A simplified structure is:

```text
BaseException
    │
    ├── SystemExit
    ├── KeyboardInterrupt
    │
    └── Exception
          │
          ├── ValueError
          ├── TypeError
          ├── OSError
          │     └── FileNotFoundError
          └── ...
```

This is why a general exception can sometimes catch more specific exceptions.

For example:

```python
except Exception:
```

can catch `ValueError` because `ValueError` inherits from `Exception`.

---

# Order of `except` Blocks

When using multiple exception handlers, more specific exceptions should generally come before broader ones.

Correct:

```python
try:
    number = int(input())

except ValueError:
    print("Invalid value.")

except Exception:
    print("Other error.")
```

If the broad handler comes first:

```python
try:
    number = int(input())

except Exception:
    print("Error.")

except ValueError:
    print("Invalid value.")
```

the `ValueError` handler becomes unreachable for that exception because `Exception` already catches it.

---

# Common Mistakes

### 1. Catching Everything

Avoid unnecessarily broad handlers:

```python
except:
    pass
```

Prefer a specific exception:

```python
except ValueError:
    print("Invalid value.")
```

---

### 2. Putting Too Much Code Inside `try`

Avoid:

```python
try:
    # A large amount of unrelated code
```

If an exception occurs, it may be difficult to determine which operation caused it.

Keep the `try` block focused:

```python
try:
    number = int(user_input)

except ValueError:
    print("Invalid number.")
```

---

### 3. Using the Wrong Exception Type

If the operation raises `ValueError`, catching an unrelated exception will not handle it.

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

### 4. Silently Ignoring Errors

Avoid:

```python
except:
    pass
```

It hides problems.

---

### 5. Thinking `try` Prevents Errors

`try` does not prevent an exception from occurring.

It allows the program to **handle an exception** if one occurs.

---

# Quick Reference

### Basic

```python
try:
    risky_code()

except SomeError:
    handle_error()
```

### With `else`

```python
try:
    risky_code()

except SomeError:
    handle_error()

else:
    success_code()
```

### With `finally`

```python
try:
    risky_code()

except SomeError:
    handle_error()

finally:
    cleanup()
```

### All together

```python
try:
    risky_code()

except SomeError:
    handle_error()

else:
    success_code()

finally:
    cleanup()
```

### Exception variable

```python
except ValueError as error:
    print(error)
```

### Multiple exceptions

```python
except (ValueError, TypeError):
    print("Invalid data.")
```

### Raise an exception

```python
raise ValueError("Invalid value")
```

---

# Key Points

* `try` is used to test code that may raise an exception.
* `except` handles matching exceptions.
* `else` runs when no exception occurs.
* `finally` runs whether an exception occurs or not.
* Specific exceptions should generally be preferred over a bare `except`.
* `as` can store the exception object.
* Multiple `except` blocks can handle different exceptions.
* Multiple exception types can be grouped in one handler.
* `raise` can manually create an exception.
* `try` does not prevent errors; it provides a way to handle them.
* `finally` is useful for cleanup.
* `with open()` is generally preferred for file handling because it manages file cleanup automatically.
* Exception handling should make programs safer and easier to use, not silently hide problems.

---

# Interview Questions

### 1. What is the purpose of `try` in Python?

`try` is used to test a block of code that may raise an exception.

### 2. What is the purpose of `except`?

`except` handles an exception raised by the code inside the `try` block.

### 3. What is the purpose of `else`?

The `else` block runs only when the `try` block completes without raising an exception.

### 4. What is the purpose of `finally`?

The `finally` block runs regardless of whether an exception occurs.

### 5. What is the difference between `raise` and `try`?

`raise` manually generates an exception, while `try` is used to execute code that may raise an exception and handle it.

### 6. Why should specific exceptions be preferred?

Specific exceptions make the program's error handling more precise and avoid accidentally hiding unexpected problems.

### 7. Can there be multiple `except` blocks?

Yes.

```python
try:
    operation()

except ValueError:
    print("Value error.")

except TypeError:
    print("Type error.")
```

### 8. Can `try` be used without `except`?

Yes, a `try` statement can be used with `finally` without an `except`.

```python
try:
    operation()

finally:
    cleanup()
```

### 9. What happens if an exception is not handled?

The exception propagates to an appropriate outer handler. If no handler handles it, Python terminates the program and displays a traceback.

### 10. What is the difference between `except Exception` and a specific exception?

`except Exception` catches most normal runtime exceptions derived from `Exception`, while a specific handler such as `except ValueError` catches only that particular exception type.


[◀Back](.././)
---