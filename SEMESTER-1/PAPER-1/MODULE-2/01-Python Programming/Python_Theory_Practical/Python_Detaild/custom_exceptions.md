[◀Back](.././)
---


# Custom Exceptions in Python

## What are Custom Exceptions?

A **custom exception** is an exception created by the programmer to represent a specific error or unusual situation in an application.

Python already provides many built-in exceptions:

```python
ValueError
TypeError
IndexError
KeyError
FileNotFoundError
ZeroDivisionError
```

However, sometimes a program has an error specific to its own rules.

For example:

```text
Invalid age
Insufficient balance
Invalid student mark
User already exists
Product out of stock
Permission denied for this operation
```

A custom exception can make these situations easier to identify and handle.

---

# Why Create Custom Exceptions?

Suppose a banking application has:

```python
balance = 500

if amount > balance:
    raise ValueError("Insufficient balance.")
```

`ValueError` works, but it does not specifically identify the application's business rule.

A custom exception can make the error more meaningful:

```python
class InsufficientBalanceError(Exception):
    pass
```

Then:

```python
if amount > balance:
    raise InsufficientBalanceError("Insufficient balance.")
```

Now the program can specifically catch `InsufficientBalanceError`.

---

# Creating a Custom Exception

A custom exception is usually created by inheriting from `Exception`.

```python
class InvalidAgeError(Exception):
    pass
```

Here:

```text
InvalidAgeError
       ↓
   Exception
```

`InvalidAgeError` is now an exception class.

---

# Raising a Custom Exception

The `raise` statement is used to trigger the custom exception.

```python
class InvalidAgeError(Exception):
    pass


age = -5

if age < 0:
    raise InvalidAgeError("Age cannot be negative.")
```

The program raises:

```text
InvalidAgeError: Age cannot be negative.
```

---

# Catching a Custom Exception

A custom exception can be caught using `except`.

```python
class InvalidAgeError(Exception):
    pass


try:
    age = -5

    if age < 0:
        raise InvalidAgeError("Age cannot be negative.")

except InvalidAgeError as error:
    print(error)
```

Output:

```text
Age cannot be negative.
```

---

# Basic Custom Exception Pattern

The common pattern is:

```python
class MyError(Exception):
    pass


try:
    raise MyError("Something went wrong.")

except MyError as error:
    print(error)
```

The flow is:

```text
Define exception
      ↓
    raise
      ↓
    try
      ↓
   except
      ↓
Handle error
```

---

# Custom Exception with a Message

A custom exception does not need additional code to accept a message.

```python
class InvalidMarkError(Exception):
    pass


raise InvalidMarkError("Mark must be between 0 and 100.")
```

The message can be retrieved through the exception object:

```python
try:
    raise InvalidMarkError("Mark must be between 0 and 100.")

except InvalidMarkError as error:
    print(error)
```

---

# Custom Exception for Validation

Custom exceptions are useful for application-specific validation.

```python
class InvalidMarkError(Exception):
    pass


mark = 150

if mark < 0 or mark > 100:
    raise InvalidMarkError("Mark must be between 0 and 100.")
```

This clearly communicates what went wrong.

---

# Handling Custom Validation Errors

```python
class InvalidMarkError(Exception):
    pass


try:
    mark = 150

    if mark < 0 or mark > 100:
        raise InvalidMarkError("Mark must be between 0 and 100.")

except InvalidMarkError as error:
    print("Invalid mark:", error)
```

Output:

```text
Invalid mark: Mark must be between 0 and 100.
```

---

# Custom Exceptions with Functions

Custom exceptions can be used inside functions.

```python
class InvalidAgeError(Exception):
    pass


def check_age(age):
    if age < 0:
        raise InvalidAgeError("Age cannot be negative.")

    return True
```

Calling the function:

```python
try:
    check_age(-10)

except InvalidAgeError as error:
    print(error)
```

Output:

```text
Age cannot be negative.
```

---

# Custom Exceptions and `return`

A function can either return a result or raise an exception when the input is invalid.

```python
class InvalidAgeError(Exception):
    pass


def check_age(age):
    if age < 0:
        raise InvalidAgeError("Invalid age.")

    return True
```

This separates successful results from error situations.

---

# Custom Exception with `try`, `except`, and `finally`

Custom exceptions work with the normal exception-handling structure.

```python
class InvalidAgeError(Exception):
    pass


try:
    age = -5

    if age < 0:
        raise InvalidAgeError("Age cannot be negative.")

except InvalidAgeError as error:
    print(error)

finally:
    print("Validation completed.")
```

Output:

```text
Age cannot be negative.
Validation completed.
```

---

# Multiple Custom Exceptions

A program can define multiple custom exceptions.

```python
class InvalidAgeError(Exception):
    pass


class InvalidMarkError(Exception):
    pass
```

They can be handled separately:

```python
try:
    raise InvalidAgeError("Invalid age.")

except InvalidAgeError:
    print("Age error.")

except InvalidMarkError:
    print("Mark error.")
```

---

# Custom Exception Hierarchy

Custom exceptions can inherit from another custom exception.

```python
class StudentError(Exception):
    pass


class InvalidAgeError(StudentError):
    pass


class InvalidMarkError(StudentError):
    pass
```

The hierarchy is:

```text
Exception
    │
    └── StudentError
          │
          ├── InvalidAgeError
          │
          └── InvalidMarkError
```

This allows related errors to be handled together.

---

# Handling the Parent Exception

Because `InvalidAgeError` inherits from `StudentError`, it can be caught using `StudentError`.

```python
class StudentError(Exception):
    pass


class InvalidAgeError(StudentError):
    pass


try:
    raise InvalidAgeError("Invalid age.")

except StudentError:
    print("A student-related error occurred.")
```

Output:

```text
A student-related error occurred.
```

---

# Handling Specific and General Custom Exceptions

Specific handlers should generally come before general handlers.

```python
class StudentError(Exception):
    pass


class InvalidAgeError(StudentError):
    pass


try:
    raise InvalidAgeError("Invalid age.")

except InvalidAgeError:
    print("Invalid age.")

except StudentError:
    print("Student error.")
```

The first matching handler is used.

---

# Custom Exception with Attributes

A custom exception can store additional information.

```python
class InsufficientBalanceError(Exception):
    def __init__(self, balance, amount):
        self.balance = balance
        self.amount = amount

        super().__init__(
            f"Balance: {balance}, requested: {amount}"
        )
```

Usage:

```python
try:
    raise InsufficientBalanceError(500, 1000)

except InsufficientBalanceError as error:
    print(error)
    print("Available:", error.balance)
    print("Requested:", error.amount)
```

Output:

```text
Balance: 500, requested: 1000
Available: 500
Requested: 1000
```

This can be useful when the program needs structured information about the error.

---

# Why Use `super().__init__()`?

When a custom exception defines its own `__init__()`, calling:

```python
super().__init__(message)
```

initializes the base `Exception` class with the message.

Example:

```python
class InvalidMarkError(Exception):
    def __init__(self, mark):
        self.mark = mark
        super().__init__(f"Invalid mark: {mark}")
```

Now:

```python
try:
    raise InvalidMarkError(150)

except InvalidMarkError as error:
    print(error)
    print(error.mark)
```

Output:

```text
Invalid mark: 150
150
```

---

# Custom Exception for a Bank Account

```python
class InsufficientBalanceError(Exception):
    pass


def withdraw(balance, amount):
    if amount > balance:
        raise InsufficientBalanceError(
            "Insufficient balance."
        )

    return balance - amount
```

Usage:

```python
try:
    balance = withdraw(500, 1000)

except InsufficientBalanceError as error:
    print(error)
```

Output:

```text
Insufficient balance.
```

---

# Custom Exception for User Registration

```python
class UsernameTakenError(Exception):
    pass


existing_users = ["riyas", "arun", "rahul"]

username = "riyas"

if username in existing_users:
    raise UsernameTakenError(
        "Username is already taken."
    )
```

The custom exception clearly describes the application-specific problem.

---

# Custom Exception for Product Stock

```python
class OutOfStockError(Exception):
    pass


stock = 0
quantity = 2

if quantity > stock:
    raise OutOfStockError("Product is out of stock.")
```

Handling it:

```python
try:
    if quantity > stock:
        raise OutOfStockError("Product is out of stock.")

except OutOfStockError as error:
    print(error)
```

---

# Custom Exceptions in Larger Programs

In larger projects, custom exceptions can be placed in a separate file.

For example:

```text
project/
│
├── main.py
├── exceptions.py
└── account.py
```

`exceptions.py`:

```python
class InsufficientBalanceError(Exception):
    pass


class InvalidAmountError(Exception):
    pass
```

Another file can import them:

```python
from exceptions import InsufficientBalanceError
```

Then:

```python
raise InsufficientBalanceError("Insufficient balance.")
```

This keeps exception definitions organized.

---

# Custom Exception vs Built-in Exception

Use a built-in exception when it accurately describes the problem.

Example:

```python
raise ValueError("Age must be positive.")
```

A custom exception may be better when the error represents a specific application rule:

```python
raise InvalidAgeError("Age must be positive.")
```

The custom exception provides a more meaningful type that other parts of the program can specifically catch.

---

# When Should You Create a Custom Exception?

Custom exceptions are useful when:

* The error has a specific meaning in your application.
* Other parts of the program need to catch that particular error.
* A built-in exception does not clearly communicate the problem.
* Several related application-specific errors need their own hierarchy.

Do not create a custom exception for every small error.

For example, there is usually no need to create:

```python
class InvalidIntegerError(Exception):
    pass
```

if a normal `ValueError` already clearly describes the problem.

---

# Custom Exceptions vs Normal Validation

Consider:

```python
age = 25

if age < 0:
    print("Invalid age.")
```

This is normal validation.

A custom exception is useful when the invalid condition needs to be propagated to another part of the program:

```python
class InvalidAgeError(Exception):
    pass


def validate_age(age):
    if age < 0:
        raise InvalidAgeError("Age cannot be negative.")
```

The caller can then decide how to handle it:

```python
try:
    validate_age(-5)

except InvalidAgeError:
    print("Please enter a valid age.")
```

---

# Common Mistakes

## 1. Forgetting to Inherit from `Exception`

Incorrect:

```python
class InvalidAgeError:
    pass
```

Correct:

```python
class InvalidAgeError(Exception):
    pass
```

---

## 2. Creating Custom Exceptions Unnecessarily

Do not create a custom exception when a built-in exception already communicates the problem clearly.

For example:

```python
raise ValueError("Invalid number.")
```

may be sufficient.

---

## 3. Using a Custom Exception Without Handling It

```python
class InvalidAgeError(Exception):
    pass


raise InvalidAgeError("Invalid age.")
```

If nothing handles the exception, it propagates normally and may terminate the program.

---

## 4. Catching the Parent Before the Child

Avoid:

```python
try:
    raise InvalidAgeError()

except StudentError:
    print("Student error.")

except InvalidAgeError:
    print("Age error.")
```

The parent handler catches the child exception first.

Prefer:

```python
except InvalidAgeError:
    print("Age error.")

except StudentError:
    print("Student error.")
```

---

## 5. Silently Ignoring Custom Exceptions

Avoid:

```python
try:
    operation()

except InvalidAgeError:
    pass
```

If the exception is intentionally ignored, there should be a clear reason. Otherwise, handle it meaningfully.

---

# Quick Reference

### Define

```python
class MyError(Exception):
    pass
```

### Raise

```python
raise MyError("Something went wrong.")
```

### Catch

```python
try:
    raise MyError("Something went wrong.")

except MyError as error:
    print(error)
```

### Custom exception with attributes

```python
class MyError(Exception):
    def __init__(self, value):
        self.value = value
        super().__init__(f"Invalid value: {value}")
```

### Custom hierarchy

```python
class AppError(Exception):
    pass


class InputError(AppError):
    pass


class DatabaseError(AppError):
    pass
```

---

# Key Points

* A custom exception is a programmer-defined exception.
* Custom exceptions normally inherit from `Exception`.
* `raise` is used to trigger a custom exception.
* `except` is used to catch a custom exception.
* Custom exceptions can have meaningful names.
* Custom exceptions are useful for application-specific errors.
* Custom exceptions can contain additional attributes.
* `super().__init__()` can initialize the base `Exception` with an error message.
* Custom exceptions can form inheritance hierarchies.
* Parent exception handlers can catch child custom exceptions.
* Specific exception handlers should generally come before general handlers.
* Built-in exceptions should be preferred when they already describe the problem accurately.
* Custom exceptions are especially useful when different parts of an application need to identify and handle a particular error type.

---

# Interview Questions

### 1. What is a custom exception?

A custom exception is a programmer-defined exception created to represent a specific application-related error.

### 2. How do you create a custom exception?

Usually by inheriting from `Exception`.

```python
class MyError(Exception):
    pass
```

### 3. How do you raise a custom exception?

Use `raise`.

```python
raise MyError("Something went wrong.")
```

### 4. How do you catch a custom exception?

Use `except`.

```python
try:
    raise MyError("Error")

except MyError as error:
    print(error)
```

### 5. Why use custom exceptions instead of built-in exceptions?

Custom exceptions can provide a specific error type for application-specific situations and allow other parts of the program to handle that error separately.

### 6. Can custom exceptions inherit from another custom exception?

Yes.

```python
class AppError(Exception):
    pass


class DatabaseError(AppError):
    pass
```

### 7. Can a custom exception store additional information?

Yes.

```python
class InvalidMarkError(Exception):
    def __init__(self, mark):
        self.mark = mark
        super().__init__(f"Invalid mark: {mark}")
```

### 8. What is the purpose of `super().__init__()` in a custom exception?

It initializes the base `Exception` class, commonly with the exception's message.

### 9. Should every error have a custom exception?

No. Use built-in exceptions when they already accurately describe the error.

### 10. Can a parent custom exception catch a child custom exception?

Yes. Because of inheritance, a handler for the parent can catch exceptions raised from its child classes.


---

[◀Back](.././)
---
