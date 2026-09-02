[◀ Back](.././)

---

# 6. Understand Exception Handling
* **What is Try?**<br>
  The **try** block is a designated code section where you place statements that might potentially trigger a runtime error (exception).

  <details>
  <summary>Click for more</summary>
  
  1. **Purpose:** It tests a block of code for errors without immediately halting the execution of the entire program.
  2. **Behavior:** Python monitors this block line-by-line; if an error occurs, it stops immediately and moves to the error-handling block.
  3. **Syntax:** Must always be followed by at least one `except` block or a `finally` block to remain syntactically valid.
  
  **Example Code:**
  ```python
  try:
      # This line will run fine
      print("Starting calculation...")
      # This line will trigger a ZeroDivisionError
      result = 10 / 0 
      # This line will be skipped completely
      print("Calculation successful!")
  except ZeroDivisionError:
      print("Caught an error: Cannot divide by zero!")
  ```
  
  </details>

* **What is Except?**<br>
  The **except** block defines the specific rescue logic that Python executes if an error or crash occurs within the corresponding `try` block.

  <details>
  <summary>Click for more</summary>
  
  1. **Targeting Errors:** You can catch specific errors (e.g., `except ValueError:`, `except ZeroDivisionError:`) to handle different failures uniquely.
  2. **Error Objects:** Use the `as` keyword (e.g., `except TypeError as err:`) to inspect the official error message sent by Python.
  3. **Catch-All:** A bare `except:` block catches all remaining errors, but should be used sparingly as it can hide unexpected bugs.
  
  **Example Code:**
  ```python
  try:
      user_input = "abc"
      # Attempting to convert characters to an integer triggers a ValueError
      number = int(user_input)
  except ValueError as err:
      print(f"Invalid input handled safely. Details: {err}")
  except Exception as generic_err:
      print(f"An unexpected error occurred: {generic_err}")
  ```
  
  </details>

* **What is Finally?**<br>
  The **finally** block contains cleanup instructions that Python is guaranteed to run, regardless of whether an exception was raised or successfully caught.

  <details>
  <summary>Click for more</summary>
  
  1. **Guaranteed Run:** Executes even if the `try` block hits a `return` statement or the `except` block encounters a complete system failure.
  2. **Resource Management:** Ideal for critical cleanup operations like closing active database connections or closing open system files.
  3. **Else Companion:** Can be used alongside an optional `else` block, which runs only if *no* exceptions were thrown in the `try` block.
  
  **Example Code:**
  ```python
  try:
      print("Opening system resources...")
      file = open("sample.txt", "r")
  except FileNotFoundError:
      print("Error: The requested file does not exist.")
  else:
      print("File processed successfully because no errors occurred.")
  finally:
      print("Cleanup step: This message always prints no matter what.")
  ```
  
  </details>

* **What are Custom Exceptions?**<br>
  **Custom exceptions** are user-defined error categories created by a programmer to handle unique, domain-specific rule violations in an application.

  <details>
  <summary>Click for more</summary>
  
  1. **Inheritance:** Created by defining a new class that explicitly inherits from Python's built-in `Exception` base class.
  2. **Triggering Errors:** Raised manually inside your code using the `raise` keyword when a custom business rule is broken.
  3. **Use Case Example:** Raising a custom `InsufficientFundsError` if a user attempts to withdraw more cash than their profile balance holds.
  
  **Example Code:**
  ```python
  # 1. Define the custom exception
  class InsufficientFundsError(Exception):
      pass

  balance = 50
  withdrawal_amount = 100

  # 2. Raise and handle the custom exception
  try:
      if withdrawal_amount > balance:
          raise InsufficientFundsError("You do not have enough money!")
  except InsufficientFundsError as error:
      print(f"Transaction Denied: {error}")
  ```
  
  </details>

* **What is Writing Robust Programs?**<br>
  **Writing robust programs** is the software development practice of anticipating failures, validating data inputs, and gracefully handling exceptions so an application never unexpectedly crashes.

  <details>
  <summary>Click for more</summary>
  
  1. **Proactive Defense:** Using condition checks (like `if` statements) to prevent errors before they happen, rather than relying solely on `try-except`.
  2. **Graceful Degradation:** Providing user-friendly error messages and fallback options instead of showing raw computer tracebacks to users.
  3. **Validation Loops:** Combining loops with `try-except` structures to repeatedly prompt users for information until they supply valid input data formats.
  
  **Example Code:**
  ```python
  # A robust function that forces a valid integer input without crashing
  def get_valid_age():
      while True:
          try:
              age = int(input("Enter your age: "))
              if age < 0:
                  print("Age cannot be negative. Try again.")
                  continue
              return age  # Breaks loop and exits function on success
          except ValueError:
              print("That is not a valid number. Please input digits only.")

  valid_user_age = get_valid_age()
  print(f"Registered age successfully: {valid_user_age}")
  ```
  
  </details>


---

[◀ Back](.././)