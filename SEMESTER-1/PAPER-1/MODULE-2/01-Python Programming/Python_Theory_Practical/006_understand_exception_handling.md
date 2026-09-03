
## Try

The **`try` statement** is used in Python to test code that may cause an exception. It is commonly used together with `except` to handle errors without immediately stopping the program.

```python
try:
    number = int(input("Enter a number: "))
    print(10 / number)
except ValueError:
    print("Please enter a valid number.")
except ZeroDivisionError:
    print("Cannot divide by zero.")
```

### Key Concepts

* **`try`** — Contains code that may raise an exception.
* **`except`** — Handles an exception when one occurs.
* **`else`** — Runs when the `try` block completes without an exception.
* **`finally`** — Runs whether an exception occurs or not.
* **Exception handling** — Allows programs to respond to errors safely.
* **Multiple `except` blocks** — Handle different exception types separately.
* **`Exception`** — A general base class that can be used to catch many exceptions.
* **`raise`** — Manually creates an exception.
* **Specific exceptions** — Catch the expected error instead of unnecessarily catching everything.
* **`try` does not fix errors** — It provides a way to detect and handle exceptions.

[View more details →](./Python_Detaild/try.md)

---

## Except

The **`except` statement** is used with `try` to handle exceptions that occur while a program is running. It allows the program to respond to expected errors instead of terminating immediately.

```python
try:
    number = int(input("Enter a number: "))
    print(10 / number)

except ValueError:
    print("Please enter a valid number.")

except ZeroDivisionError:
    print("Cannot divide by zero.")
```

### Key Concepts

* **`except`** — Handles an exception raised inside the `try` block.
* **Specific exception** — Handles a particular type of error, such as `ValueError`.
* **Multiple `except` blocks** — Handle different exceptions separately.
* **Exception object** — Store error information using `as`.
* **Multiple exceptions** — Handle several exception types with one `except`.
* **`Exception`** — A general exception class for broader error handling.
* **Bare `except`** — Catches almost any exception and should generally be avoided.
* **Exception matching** — Python runs the first matching `except` block.
* **`raise`** — Can be used to create or re-raise exceptions.
* **Specific handling** — Catch only the errors you know how to handle.

[View more details →](./Python_Detaild/except.md)


---

## Finally

The **`finally` block** is used with `try` and `except` to execute code **regardless of whether an exception occurs or not**. It is commonly used for cleanup operations such as closing files or releasing resources.

```python
try:
    number = int(input("Enter a number: "))

except ValueError:
    print("Invalid input.")

finally:
    print("Execution completed.")
```

### Key Concepts

* **`finally`** — Runs whether an exception occurs or not.
* **Cleanup** — Commonly used for closing files, connections, or releasing resources.
* **`try` + `finally`** — `finally` can be used even without `except`.
* **`try` + `except` + `finally`** — Handles errors and performs cleanup.
* **`else` + `finally`** — `else` runs only when there is no exception; `finally` always runs.
* **Guaranteed execution** — `finally` normally executes before leaving the `try` statement.
* **Resource management** — Useful when resources must be cleaned up regardless of success or failure.

[View more details →](./Python_Detaild/finally.md)

---

## Custom Exceptions

**Custom exceptions** are user-defined exception classes created to represent specific errors in an application. They make error handling clearer and allow programs to describe application-specific problems.

Custom exceptions are usually created by inheriting from Python's built-in `Exception` class.

```python
class InvalidAgeError(Exception):
    pass


age = -5

if age < 0:
    raise InvalidAgeError("Age cannot be negative.")
```

### Key Concepts

* **Custom exception** — An exception created by the programmer for a specific situation.
* **`Exception`** — The common base class normally inherited by custom exceptions.
* **`class`** — Used to define a custom exception.
* **`raise`** — Used to manually trigger an exception.
* **`except`** — Used to catch and handle a custom exception.
* **Custom error message** — Provides meaningful information about what went wrong.
* **Custom exception hierarchy** — Custom exceptions can inherit from other custom exceptions.
* **Application-specific errors** — Useful when built-in exceptions do not clearly describe a particular problem.

[View more details →](./Python_Detaild/custom_exceptions.md)


---

## Writing Robust Programs

A **robust program** is a program that continues to work correctly even when unexpected input, errors, or unusual situations occur.

### Key Concepts

* **Input validation** — Check user input before processing it.
* **Error handling** — Use `try`, `except`, `else`, and `finally` to handle runtime errors safely.
* **Specific exceptions** — Catch the exceptions you actually expect instead of hiding every error.
* **Defensive programming** — Write code that anticipates possible problems.
* **Boundary checking** — Make sure values such as indexes, numbers, and ranges are valid.
* **Handling missing data** — Safely deal with missing files, dictionary keys, or empty collections.
* **Clear error messages** — Tell the user what went wrong and, when possible, how to fix it.
* **Avoiding crashes** — Handle expected problems instead of allowing the entire program to terminate unexpectedly.
* **Reusable validation** — Put repeated validation logic into functions.
* **Testing edge cases** — Test empty input, invalid input, very large values, and other unusual cases.
* **Clean resource management** — Use tools such as `with open()` to ensure resources are properly handled.
* **Maintainable code** — Use meaningful names, functions, and simple program structure.

### Example

```python
try:
    age = int(input("Enter your age: "))

    if age < 0:
        print("Age cannot be negative.")
    else:
        print(f"Your age is {age}")

except ValueError:
    print("Please enter a valid number.")
```

The program validates the input and handles an invalid value without crashing.

[View more details →](./Python_Detaild/writing_robust_programs.md)

