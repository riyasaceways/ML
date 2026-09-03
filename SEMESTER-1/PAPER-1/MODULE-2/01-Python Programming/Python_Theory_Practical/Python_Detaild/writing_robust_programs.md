[◀Back](.././)
---


# Writing Robust Programs

## What Is a Robust Program?

A **robust program** is a program that behaves correctly and predictably even when it receives unexpected input, encounters errors, or faces unusual situations.

A robust program should:

* Handle invalid input.
* Handle expected errors.
* Prevent unnecessary crashes.
* Give useful error messages.
* Validate data before using it.
* Handle edge cases.
* Manage resources properly.
* Be easy to maintain and modify.

---

## Why Write Robust Programs?

A simple program may work correctly when everything goes as expected.

For example:

```python
age = int(input("Enter your age: "))
print(age)
```

This works when the user enters:

```text
20
```

But what happens if the user enters:

```text
twenty
```

The program raises a `ValueError`.

A robust program anticipates this possibility.

```python
try:
    age = int(input("Enter your age: "))
    print(age)
except ValueError:
    print("Please enter a valid age.")
```

---

## 1. Validate Input

**Input validation** means checking whether data is acceptable before using it.

```python
age = int(input("Enter your age: "))

if age < 0:
    print("Invalid age")
else:
    print(f"Age: {age}")
```

Validation can check:

* Data type
* Range
* Length
* Format
* Required values
* Allowed choices

---

## 2. Handle Invalid Input

User input should not automatically be trusted.

```python
try:
    number = int(input("Enter a number: "))
    print(number)
except ValueError:
    print("Invalid input. Enter a whole number.")
```

Here, the program handles the expected `ValueError`.

---

## 3. Use Specific Exceptions

Prefer specific exceptions when you know what can go wrong.

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("Invalid number.")
```

Instead of:

```python
try:
    number = int(input("Enter a number: "))
except:
    print("Something went wrong.")
```

Specific exceptions make programs easier to understand and debug.

---

## 4. Handle Multiple Errors

Different operations can produce different exceptions.

```python
try:
    number = int(input("Enter a number: "))
    result = 100 / number
    print(result)

except ValueError:
    print("Please enter a valid integer.")

except ZeroDivisionError:
    print("The number cannot be zero.")
```

Each exception receives an appropriate response.

---

## 5. Use `else`

The `else` block runs when no exception occurs.

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("Invalid input.")
else:
    print(f"You entered {number}.")
```

This keeps successful execution separate from error handling.

---

## 6. Use `finally` for Cleanup

`finally` is useful when something must be done whether an error occurs or not.

```python
try:
    print("Processing...")
except Exception:
    print("An error occurred.")
finally:
    print("Finished.")
```

It is commonly used for cleanup operations.

For files, `with` is generally preferred:

```python
with open("data.txt", "r") as file:
    data = file.read()
```

The file is properly managed automatically.

---

## 7. Check Before Accessing Data

A robust program checks whether data exists before using it.

### Dictionary

Instead of:

```python
student = {
    "name": "Riyas"
}

print(student["age"])
```

which raises `KeyError`, use:

```python
print(student.get("age", "Age not available"))
```

### List

Check the index before accessing it:

```python
numbers = [10, 20, 30]

index = 5

if 0 <= index < len(numbers):
    print(numbers[index])
else:
    print("Invalid index.")
```

---

## 8. Handle Missing Files

Files may not exist.

```python
try:
    with open("data.txt", "r") as file:
        data = file.read()

except FileNotFoundError:
    print("The file does not exist.")
```

This prevents an expected file-related problem from crashing the program.

---

## 9. Handle Missing Data

Data may be incomplete.

```python
student = {
    "name": "Riyas"
}

marks = student.get("marks")

if marks is None:
    print("Marks are not available.")
else:
    print(marks)
```

A robust program does not assume that every piece of data is present.

---

## 10. Check Ranges

Values should often be within an expected range.

```python
mark = int(input("Enter mark: "))

if 0 <= mark <= 100:
    print("Valid mark.")
else:
    print("Mark must be between 0 and 100.")
```

---

## 11. Check Choices

When the user must select from a fixed set of options, validate the choice.

```python
choice = input("Enter yes or no: ").lower()

if choice in ("yes", "no"):
    print("Valid choice.")
else:
    print("Please enter yes or no.")
```

---

## 12. Defensive Programming

**Defensive programming** means writing code with the assumption that unexpected situations may occur.

For example:

```python
numbers = [10, 20, 30]

if numbers:
    print(numbers[0])
else:
    print("The list is empty.")
```

The program checks the condition before accessing the list.

---

## 13. Handle Empty Collections

Collections can be empty.

```python
numbers = []

if numbers:
    print(max(numbers))
else:
    print("No numbers available.")
```

Without the check, calling `max()` on an empty list raises an error.

---

## 14. Handle Type Problems

Unexpected data types can cause errors.

```python
value = "100"

try:
    number = int(value)
    print(number + 10)

except ValueError:
    print("Value cannot be converted to an integer.")
```

When processing external data, always consider what type the data actually has.

---

## 15. Give Clear Error Messages

Compare:

```python
print("Error")
```

with:

```python
print("Invalid age. Please enter a number between 0 and 120.")
```

The second message is more useful because it explains:

1. What went wrong.
2. What value is expected.

---

## 16. Avoid Hiding Errors

Avoid using a broad exception handler unnecessarily.

```python
try:
    result = 10 / number
except Exception:
    pass
```

This can hide programming mistakes.

A better approach is:

```python
try:
    result = 10 / number
except ZeroDivisionError:
    print("Cannot divide by zero.")
```

Handle the problem you actually expect.

---

## 17. Use `raise` When Necessary

Sometimes a program should detect an invalid condition and raise an exception.

```python
def set_age(age):
    if age < 0:
        raise ValueError("Age cannot be negative.")

    return age
```

Then:

```python
try:
    age = set_age(-5)
except ValueError as error:
    print(error)
```

`raise` allows a program to explicitly signal an error.

---

## 18. Use Functions for Validation

If the same validation is needed repeatedly, put it inside a function.

```python
def is_valid_age(age):
    return 0 <= age <= 120
```

Then:

```python
age = 25

if is_valid_age(age):
    print("Valid age.")
else:
    print("Invalid age.")
```

This makes the program more reusable and maintainable.

---

## 19. Combine Validation and Exception Handling

Validation and exception handling solve different problems.

Validation checks whether a value is acceptable.

Exception handling deals with errors that occur while executing an operation.

```python
try:
    age = int(input("Enter your age: "))

    if age < 0:
        print("Age cannot be negative.")
    else:
        print(f"Age: {age}")

except ValueError:
    print("Please enter a valid number.")
```

Here:

* `try/except` handles conversion errors.
* `if` validates the resulting value.

---

## 20. Handle User Input in a Loop

For important input, a program can continue asking until valid data is provided.

```python
while True:
    try:
        age = int(input("Enter your age: "))

        if age < 0:
            print("Age cannot be negative.")
            continue

        break

    except ValueError:
        print("Please enter a valid number.")

print(f"Your age is {age}")
```

The program does not continue until valid input is received.

---

## 21. Handle File Operations Safely

```python
try:
    with open("students.txt", "r", encoding="utf-8") as file:
        data = file.read()

except FileNotFoundError:
    print("students.txt was not found.")

except PermissionError:
    print("Permission denied.")
```

This handles common file-related problems separately.

---

## 22. Handle JSON Data Safely

When reading JSON, the file may contain invalid JSON.

```python
import json

try:
    with open("data.json", "r", encoding="utf-8") as file:
        data = json.load(file)

except FileNotFoundError:
    print("JSON file not found.")

except json.JSONDecodeError:
    print("The JSON data is invalid.")
```

A robust program handles both missing files and invalid content.

---

## 23. Use Custom Exceptions When Appropriate

For application-specific problems, custom exceptions can make errors clearer.

```python
class InsufficientBalanceError(Exception):
    pass
```

Then:

```python
if amount > balance:
    raise InsufficientBalanceError("Insufficient balance.")
```

Custom exceptions are useful when the program has specific error conditions that built-in exceptions do not clearly represent.

---

## 24. Keep Functions Small and Focused

Large functions are harder to test and maintain.

Instead of putting everything into one function:

```python
def process_student():
    # input
    # validation
    # calculation
    # file writing
    # printing
    ...
```

Separate responsibilities:

```python
def get_student_name():
    ...

def validate_mark(mark):
    ...

def calculate_grade(mark):
    ...

def save_student(data):
    ...
```

This makes each part easier to understand and test.

---

## 25. Avoid Repeating Error-Handling Logic

If the same validation is required in many places, create reusable functions.

```python
def get_positive_number():
    while True:
        try:
            number = float(input("Enter a positive number: "))

            if number > 0:
                return number

            print("Number must be positive.")

        except ValueError:
            print("Enter a valid number.")
```

Now the same logic can be reused throughout the program.

---

## 26. Test Edge Cases

A robust program should be tested with more than normal input.

For example, if a program expects a number from `1` to `100`, test:

```text
1
50
100
0
101
-1
abc
""
```

Important edge cases include:

* Empty input
* Zero
* Negative numbers
* Very large numbers
* Boundary values
* Wrong data types
* Missing files
* Empty collections
* Duplicate data
* Unexpected formats

---

## 27. Avoid Hard-Coded Assumptions

Fragile code:

```python
numbers = [10, 20, 30]

print(numbers[2])
```

This assumes the list always contains at least three elements.

More robust:

```python
if len(numbers) > 2:
    print(numbers[2])
```

The program checks its assumption before performing the operation.

---

## 28. Use Meaningful Variable Names

Less clear:

```python
x = 20
y = 80
z = x + y
```

Clearer:

```python
math_mark = 20
science_mark = 80
total_mark = math_mark + science_mark
```

Readable code is easier to inspect, debug, and maintain.

---

## 29. Keep Error Handling Close to the Risky Operation

Instead of wrapping a large amount of unrelated code:

```python
try:
    # many different operations
    ...
except Exception:
    print("Error")
```

keep the `try` block focused:

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("Invalid number.")
```

This makes it easier to determine which operation caused the problem.

---

## 30. Robustness Does Not Mean Hiding Every Error

A robust program should handle **expected problems**, not silently hide every problem.

Bad:

```python
try:
    ...
except:
    pass
```

Better:

```python
try:
    ...
except ValueError:
    print("Invalid input.")
```

Unexpected programming errors should generally remain visible during development so they can be fixed.

---

# Practical Example

Consider a simple student-mark program.

### Less robust version

```python
name = input("Enter name: ")
mark = int(input("Enter mark: "))

print(f"{name} scored {mark}")
```

Possible problems:

* User enters text instead of a number.
* User enters a negative mark.
* User enters a mark greater than 100.
* The program crashes on invalid input.

### More robust version

```python
name = input("Enter name: ").strip()

if not name:
    print("Name cannot be empty.")
else:
    try:
        mark = int(input("Enter mark: "))

        if 0 <= mark <= 100:
            print(f"{name} scored {mark}")
        else:
            print("Mark must be between 0 and 100.")

    except ValueError:
        print("Please enter a valid whole number.")
```

The improved version handles:

* Empty names
* Invalid numbers
* Negative marks
* Marks above 100

---

# Robust Program Checklist

Before considering a program reliable, ask:

* [ ] Does it validate user input?
* [ ] Does it handle expected exceptions?
* [ ] Does it use specific exception types?
* [ ] Does it handle missing data?
* [ ] Does it handle empty collections?
* [ ] Does it check boundaries and ranges?
* [ ] Does it handle missing files?
* [ ] Does it provide useful error messages?
* [ ] Does it avoid unnecessary broad `except` blocks?
* [ ] Does it clean up resources properly?
* [ ] Does it handle edge cases?
* [ ] Is repeated validation reusable?
* [ ] Are functions focused and understandable?
* [ ] Has the program been tested with invalid input?

---

# Quick Reference

| Concept               | Purpose                                |
| --------------------- | -------------------------------------- |
| Input validation      | Check data before using it             |
| `try`                 | Put potentially failing code inside it |
| `except`              | Handle an exception                    |
| `else`                | Run code when no exception occurs      |
| `finally`             | Run cleanup code                       |
| `raise`               | Explicitly raise an exception          |
| Defensive programming | Anticipate possible problems           |
| Edge-case testing     | Test unusual or boundary situations    |
| Specific exceptions   | Handle known errors precisely          |
| Custom exceptions     | Represent application-specific errors  |
| `with`                | Safely manage resources such as files  |

---

# Key Points

1. A robust program handles unexpected situations safely.
2. Validate input before processing it.
3. Use `try`/`except` for expected runtime errors.
4. Prefer specific exceptions over broad exception handling.
5. Use `else` for successful execution and `finally` for cleanup.
6. Use `raise` when the program needs to explicitly signal an invalid condition.
7. Check for missing data and empty collections.
8. Test edge cases, not just normal input.
9. Use reusable validation functions.
10. Robustness should make errors understandable, not hide them.

---

# Interview Questions

### 1. What is a robust program?

A robust program is a program that handles unexpected input, errors, and unusual situations safely and continues to behave predictably.

### 2. What is defensive programming?

Defensive programming is the practice of anticipating possible problems and writing code to handle them safely.

### 3. Why is input validation important?

It prevents invalid or unexpected data from causing incorrect results or runtime errors.

### 4. How does exception handling improve program robustness?

It allows a program to handle expected runtime errors instead of terminating unexpectedly.

### 5. Why should specific exceptions be used?

Specific exceptions make error handling more precise, readable, and easier to debug.

### 6. What is the difference between validation and exception handling?

Validation checks whether data is acceptable. Exception handling deals with errors that occur during program execution.

### 7. Why should edge cases be tested?

Edge cases can reveal problems that do not appear during normal execution.

### 8. What is the purpose of `finally`?

`finally` is used for code that should execute whether an exception occurs or not, especially cleanup operations.

### 9. What is defensive programming in Python?

It involves checking assumptions, validating data, handling expected exceptions, and preparing the program for unusual situations.

### 10. Does robust programming mean catching every exception?

No. Robust programming means handling expected problems appropriately while allowing unexpected programming errors to remain visible for debugging.


---

[◀Back](.././)
---