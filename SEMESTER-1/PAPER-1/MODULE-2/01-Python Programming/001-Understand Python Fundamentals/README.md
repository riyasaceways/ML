[◀ Back](.././)

# Understand Python Fundamentals
1. Variables and data types
2. Input and output operations
3. Type conversion
4. Expressions and operators
5. Python coding conventions
---

## 1. Variables and data types
* **What is variable?**<br>
  A **variable** is a named label used to store and look up data in a computer program.

  <details>
  <summary>Click for more</summary>
  
  1. Must start with a letter or an underscore (_).
  2. Cannot start with a digit. 
  3. Can only contain alphanumeric characters and underscores (A-z, 0-9, and _).
  
  </details>

* **What is Data types?**<br>
  A **data type** is a classification that tells the computer what kind of value a variable holds and how it can be used.

  <details>
  <summary>Click for more</summary>
  
  1. Determines valid operations (e.g., you can add numbers, but you cannot add a number to a word).
  2. Python automatically detects the data type when you assign a value (Dynamic Typing). 
  3. Core types include text (str), numeric (int, float), logical (bool), and collections (list, dict).
  
  </details>

## 2. Input and output operations
* **What is an output operation?**<br>
  An **output operation** is a way for a program to display information or results to the user, typically on the screen.

  <details>
  <summary>Click for more</summary>
  
  1. Handled by the built-in `print()` function in Python.
  2. Automatically adds a newline character at the end of the message by default. 
  3. Can display multiple items separated by commas, which inserts a space between them automatically.
  
  </details>

* **What is an input operation?**<br>
  An **input operation** allows a program to pause and collect information or text typed by the user from the keyboard.

  <details>
  <summary>Click for more</summary>
  
  1. Handled by the built-in `input()` function in Python.
  2. Accepts an optional string argument to display as a helpful prompt message for the user. 
  3. **Crucial Rule:** It always reads and returns the entered data as text (`str`), even if the user types a number.
  
  </details>

## 3. Type conversion
* **What is Type Conversion?**<br>
  **Type conversion** (also called typecasting) is the process of changing a value from one data type into another data type.

  <details>
  <summary>Click for more</summary>
  
  1. Necessary when you need to perform operations on mixed data types (like joining text with numbers).
  2. Divided into two main categories: automatic (implicit) and manual (explicit).
  3. Helps prevent `TypeError` bugs when processing user text input that represents numerical values.
  
  </details>

* **What is Implicit vs. Explicit Conversion?**<br>
  **Implicit conversion** is done automatically by Python, while **explicit conversion** requires the programmer to manually use a built-in function to force a type change.

  <details>
  <summary>Click for more</summary>
  
  1. **Implicit example:** Adding an integer to a float automatically converts the integer to a float (e.g., `5 + 2.0` becomes `7.0`).
  2. **Explicit functions:** Built-in tools like `int()`, `float()`, and `str()` forcefully convert a value.
  3. **Explicit example:** Converting raw user text into an integer using `age = int(input("Enter age: "))`.
  
  </details>

## 4. Expressions and operators
* **What is an Operator?**<br>
  An **operator** is a special symbol or keyword used to perform specific mathematical, comparison, or logical calculations on data values (called operands).

  <details>
  <summary>Click for more</summary>
  
  1. Arithmetic operators handle math (e.g., `+` for addition, `-` for subtraction, `*` for multiplication).
  2. Comparison operators evaluate relationships (e.g., `==` for equal to, `>` for greater than) and return a Boolean.
  3. Logical operators combine conditions (e.g., `and`, `or`, `not`).
  
  </details>

* **What is an Expression?**<br>
  An **expression** is a combination of variables, constants, operators, and function calls that Python evaluates to produce a single final value.

  <details>
  <summary>Click for more</summary>
  
  1. Example of an expression: `total_price = (price * quantity) + tax`.
  2. Follows standard mathematical rules of operator precedence (PEMDAS/BODMAS).
  3. Parentheses `()` can be used to manually control and change the evaluation order.
  
  </details>

## 5. Python coding conventions
* **What are Python Coding Conventions?**<br>
  **Coding conventions** are a set of guidelines and best practices for writing clean, readable, and consistent code that other developers can easily understand.

  <details>
  <summary>Click for more</summary>
  
  1. PEP 8 (Python Enhancement Proposal 8) is the official style guide for writing Python code.
  2. Following conventions makes code sharing, debugging, and team collaboration much more efficient.
  3. Consistency is the primary goal; clear code minimizes errors during software maintenance.
  
  </details>

* **What are the key rules of PEP 8?**<br>
  The most critical rules of **PEP 8** focus on structural indentation, careful spacing, and standard naming formats for code elements.

  <details>
  <summary>Click for more</summary>
  
  1. **Indentation:** Always use exactly 4 spaces per indentation level; never mix tabs and spaces.
  2. **Naming Styles:** Use `snake_case` for variables/functions, and `PascalCase` for class names.
  3. **Comments:** Keep comments updated, short, and place a single space after the `#` symbol.
  
  </details>
