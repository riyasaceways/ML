[◀Back](.././)
---



# Function Creation in Python

## What is a Function?

A **function** is a reusable block of code that performs a specific task.

Instead of writing the same code repeatedly, you can place it inside a function and call that function whenever you need it.

Example:

```python
def greet():
    print("Hello, Python!")
```

The function can then be called:

```python
greet()
```

Output:

```text
Hello, Python!
```

---

# Why Use Functions?

Functions help make programs:

* **Reusable** — Write code once and use it multiple times.
* **Organized** — Divide a large program into smaller parts.
* **Readable** — Give meaningful names to specific tasks.
* **Maintainable** — Changes can be made in one place.
* **Testable** — Individual functions can be tested separately.

---

# Creating a Function

A function is created using the `def` keyword.

### Basic Syntax

```python
def function_name():
    # function body
```

Example:

```python
def greet():
    print("Hello!")
```

Here:

* `def` → keyword used to define a function.
* `greet` → function name.
* `()` → parameter list.
* `:` → marks the beginning of the function body.
* Indented code → function body.

---

# Calling a Function

Defining a function does not execute it.

You need to **call** the function.

```python
def greet():
    print("Hello!")

greet()
```

Output:

```text
Hello!
```

The function runs when `greet()` is called.

---

# Function Execution Flow

Consider:

```python
def greet():
    print("Hello!")

print("Start")

greet()

print("End")
```

Output:

```text
Start
Hello!
End
```

The execution flow is:

```text
Program starts
     ↓
print("Start")
     ↓
greet()
     ↓
Function body executes
     ↓
print("End")
```

---

# Functions with Parameters

A function can receive data through **parameters**.

```python
def greet(name):
    print("Hello", name)
```

Calling the function:

```python
greet("Riyas")
```

Output:

```text
Hello Riyas
```

Here:

```python
name
```

is the **parameter**.

```python
"Riyas"
```

is the **argument**.

---

# Parameters vs Arguments

These terms are related but different.

### Parameter

A variable defined in the function definition.

```python
def greet(name):
    print(name)
```

`name` is a parameter.

### Argument

The actual value passed when calling the function.

```python
greet("Riyas")
```

`"Riyas"` is an argument.

### Simple Difference

```text
Parameter → variable in function definition
Argument  → actual value passed to the function
```

---

# Multiple Parameters

A function can have multiple parameters.

```python
def add(a, b):
    print(a + b)

add(10, 20)
```

Output:

```text
30
```

Here:

* `a` receives `10`
* `b` receives `20`

---

# Returning a Value

The `return` statement sends a value back to the code that called the function.

```python
def add(a, b):
    return a + b
```

You can store the returned value:

```python
result = add(10, 20)

print(result)
```

Output:

```text
30
```

---

# `print()` vs `return`

These are not the same.

### Using `print()`

```python
def add(a, b):
    print(a + b)

result = add(10, 20)

print(result)
```

Output:

```text
30
None
```

The function printed the result but did not return it.

### Using `return`

```python
def add(a, b):
    return a + b

result = add(10, 20)

print(result)
```

Output:

```text
30
```

### Main Difference

* `print()` displays a value.
* `return` sends a value back to the caller.

---

# Function Without `return`

A function does not have to explicitly return a value.

```python
def greet():
    print("Hello!")

result = greet()

print(result)
```

Output:

```text
Hello!
None
```

When a function does not explicitly return a value, Python returns `None`.

---

# Returning Multiple Values

A function can return multiple values.

```python
def calculate(a, b):
    return a + b, a - b
```

Calling it:

```python
addition, subtraction = calculate(10, 5)

print(addition)
print(subtraction)
```

Output:

```text
15
5
```

Python actually returns these values together as a tuple.

---

# Default Parameters

A parameter can have a default value.

```python
def greet(name="Guest"):
    print("Hello", name)
```

Calling without an argument:

```python
greet()
```

Output:

```text
Hello Guest
```

Calling with an argument:

```python
greet("Riyas")
```

Output:

```text
Hello Riyas
```

The supplied argument replaces the default value.

---

# Positional Arguments

Arguments can be passed according to their position.

```python
def student(name, age):
    print(name, age)

student("Riyas", 20)
```

Output:

```text
Riyas 20
```

Here:

```text
"Riyas" → name
20      → age
```

---

# Keyword Arguments

Arguments can also be passed using parameter names.

```python
def student(name, age):
    print(name, age)

student(age=20, name="Riyas")
```

Output:

```text
Riyas 20
```

The order does not matter when using keyword arguments.

---

# Positional and Keyword Arguments Together

You can combine them.

```python
def student(name, age, course):
    print(name, age, course)

student("Riyas", age=20, course="Python")
```

However, positional arguments must come before keyword arguments.

Correct:

```python
student("Riyas", age=20)
```

Incorrect:

```python
student(name="Riyas", 20)
```

---

# Function with No Parameters

A function does not have to receive input.

```python
def welcome():
    print("Welcome to Python!")

welcome()
```

---

# Function with Parameters and Return Value

Functions can both receive input and return output.

```python
def square(number):
    return number ** 2

result = square(5)

print(result)
```

Output:

```text
25
```

This is one of the most common function patterns:

```text
Input → Function → Output
```

---

# Local Variables

A variable created inside a function is generally **local to that function**.

```python
def calculate():
    result = 10 + 20
    print(result)

calculate()
```

`result` is a local variable.

Trying to access it outside the function:

```python
print(result)
```

will raise a `NameError` if no variable named `result` exists in that outer scope.

---

# Global Variables

A variable defined outside a function is in the global scope.

```python
message = "Hello"

def greet():
    print(message)

greet()
```

Output:

```text
Hello
```

The function can read the global variable.

---

# Local vs Global Variables

```python
message = "Global"

def show():
    message = "Local"
    print(message)

show()

print(message)
```

Output:

```text
Local
Global
```

The local variable inside the function does not replace the global variable.

---

# The `global` Keyword

The `global` keyword can be used when a function needs to assign to a global variable.

```python
count = 0

def increase():
    global count
    count += 1

increase()

print(count)
```

Output:

```text
1
```

Using global variables extensively can make programs harder to maintain, so functions generally work better when they receive inputs and return outputs.

---

# Function Documentation

A function can have a **docstring** describing what it does.

```python
def add(a, b):
    """Return the sum of two numbers."""
    return a + b
```

You can access the documentation using:

```python
print(add.__doc__)
```

Output:

```text
Return the sum of two numbers.
```

Docstrings are useful for documenting functions.

---

# Type Hints in Functions

Python allows you to specify expected parameter and return types using type hints.

```python
def add(a: int, b: int) -> int:
    return a + b
```

Here:

```text
a: int
```

suggests that `a` should be an integer.

```text
-> int
```

suggests that the function returns an integer.

Type hints improve readability and tooling, but Python does not generally enforce them at runtime.

---

# Functions with Conditions

A function can contain conditional statements.

```python
def check_number(number):
    if number > 0:
        return "Positive"
    elif number < 0:
        return "Negative"
    else:
        return "Zero"

print(check_number(10))
```

Output:

```text
Positive
```

---

# Functions with Loops

Functions can also contain loops.

```python
def print_numbers(numbers):
    for number in numbers:
        print(number)

print_numbers([10, 20, 30])
```

Output:

```text
10
20
30
```

This demonstrates how functions can combine with other Python concepts.

---

# Passing Collections to Functions

Lists, tuples, sets, and dictionaries can be passed as arguments.

## List

```python
def display_numbers(numbers):
    for number in numbers:
        print(number)

display_numbers([10, 20, 30])
```

---

## Dictionary

```python
def display_student(student):
    print(student["name"])

display_student({
    "name": "Riyas",
    "age": 20
})
```

---

# Returning Collections

A function can return a collection.

```python
def get_numbers():
    return [10, 20, 30]

numbers = get_numbers()

print(numbers)
```

Output:

```text
[10, 20, 30]
```

It can also return tuples, sets, or dictionaries.

---

# Variable-Length Arguments

Sometimes you do not know how many arguments a function will receive.

Python provides:

* `*args`
* `**kwargs`

---

# `*args`

`*args` allows a function to receive a variable number of positional arguments.

```python
def add_numbers(*numbers):
    return sum(numbers)

print(add_numbers(10, 20))
print(add_numbers(10, 20, 30, 40))
```

Output:

```text
30
100
```

Inside the function, `numbers` is a tuple.

---

# `**kwargs`

`**kwargs` allows a function to receive a variable number of keyword arguments.

```python
def display_info(**details):
    print(details)

display_info(name="Riyas", age=20, course="Python")
```

Output:

```text
{'name': 'Riyas', 'age': 20, 'course': 'Python'}
```

Inside the function, `details` is a dictionary.

---

# Combining Parameters, `*args`, and `**kwargs`

A function can use different types of parameters.

```python
def example(name, age=20, *args, **kwargs):
    print(name)
    print(age)
    print(args)
    print(kwargs)
```

The exact parameter ordering rules must be followed when defining such functions.

---

# Positional-Only Parameters

Python supports parameters that can only be supplied positionally using `/`.

```python
def add(a, b, /):
    return a + b
```

This is valid:

```python
add(10, 20)
```

But this is not:

```python
add(a=10, b=20)
```

---

# Keyword-Only Parameters

Parameters after `*` can be made keyword-only.

```python
def student(name, *, age):
    print(name, age)
```

Valid:

```python
student("Riyas", age=20)
```

This is invalid:

```python
student("Riyas", 20)
```

because `age` is keyword-only.

---

# Function Calling Another Function

One function can call another function.

```python
def square(number):
    return number ** 2

def display_square(number):
    result = square(number)
    print(result)

display_square(5)
```

Output:

```text
25
```

This allows larger programs to be divided into smaller reusable functions.

---

# Nested Functions

A function can be defined inside another function.

```python
def outer():
    def inner():
        print("Inside inner function")

    inner()

outer()
```

Output:

```text
Inside inner function
```

The inner function is available within the scope where it is defined.

---

# Recursive Functions

A function can call itself. This is called **recursion**.

Example:

```python
def countdown(number):
    if number == 0:
        return

    print(number)
    countdown(number - 1)

countdown(5)
```

Output:

```text
5
4
3
2
1
```

A recursive function needs a condition that eventually stops the recursion.

---

# Lambda Functions

A **lambda** is a small anonymous function.

Syntax:

```python
lambda arguments: expression
```

Example:

```python
square = lambda x: x ** 2

print(square(5))
```

Output:

```text
25
```

For larger or more complex logic, a normal `def` function is generally clearer.

---

# Practical Example: Calculator

Functions can divide a program into separate tasks.

```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    return a / b
```

Using the functions:

```python
print(add(10, 5))
print(subtract(10, 5))
print(multiply(10, 5))
print(divide(10, 5))
```

Output:

```text
15
5
50
2.0
```

Each function has a specific responsibility.

---

# Practical Example: Student Result

```python
def calculate_average(marks):
    return sum(marks) / len(marks)

def check_result(average):
    if average >= 50:
        return "Passed"
    return "Failed"

marks = [70, 80, 60]

average = calculate_average(marks)
result = check_result(average)

print("Average:", average)
print("Result:", result)
```

Output:

```text
Average: 70.0
Result: Passed
```

The problem is divided into separate functions.

---

# Function Naming

Function names should describe what the function does.

Good examples:

```python
calculate_total()
get_user_name()
check_age()
display_result()
calculate_average()
```

Avoid unclear names such as:

```python
x()
abc()
do_it()
```

unless their purpose is obvious from the context.

Python convention generally uses **snake_case** for function names.

---

# Function Scope

A function creates a new local scope.

Consider:

```python
x = 10

def test():
    x = 20
    print(x)

test()

print(x)
```

Output:

```text
20
10
```

The `x` inside the function is a different local variable from the global `x`.

---

# Function Annotations

Python allows annotations for parameters and return values.

```python
def greet(name: str) -> str:
    return f"Hello, {name}"
```

Annotations can provide useful information to developers and development tools.

They do not automatically convert or validate the supplied value.

---

# Common Mistakes

## 1. Forgetting to call the function

Defining:

```python
def greet():
    print("Hello")
```

does not execute it.

You need:

```python
greet()
```

---

## 2. Forgetting parentheses

Incorrect:

```python
greet
```

Correct:

```python
greet()
```

The first refers to the function object; the second calls the function.

---

## 3. Forgetting the colon

Incorrect:

```python
def greet()
```

Correct:

```python
def greet():
```

---

## 4. Incorrect indentation

Incorrect:

```python
def greet():
print("Hello")
```

Correct:

```python
def greet():
    print("Hello")
```

The function body must be properly indented.

---

## 5. Calling with the wrong number of arguments

```python
def add(a, b):
    return a + b

add(10)
```

This raises a `TypeError` because the required argument `b` is missing.

---

## 6. Confusing `print()` with `return`

```python
def add(a, b):
    print(a + b)
```

This displays the result but does not return it.

If another part of the program needs the result, use:

```python
def add(a, b):
    return a + b
```

---

## 7. Returning before expected code executes

```python
def example():
    return 10
    print("Hello")
```

The `print()` statement will never execute because `return` immediately leaves the function.

---

# Quick Reference

```python
# Basic function
def greet():
    print("Hello")

greet()


# Function with parameters
def greet(name):
    print("Hello", name)

greet("Riyas")


# Function with multiple parameters
def add(a, b):
    return a + b

result = add(10, 20)


# Default parameter
def greet(name="Guest"):
    print("Hello", name)


# Keyword arguments
def student(name, age):
    print(name, age)

student(age=20, name="Riyas")


# Variable positional arguments
def total(*numbers):
    return sum(numbers)


# Variable keyword arguments
def information(**details):
    print(details)


# Type hints
def square(number: int) -> int:
    return number ** 2


# Lambda
square = lambda x: x ** 2
```

---

# Key Points to Remember

1. A **function** is a reusable block of code.
2. Use `def` to define a function.
3. Defining a function does not execute it.
4. Call a function using its name followed by `()`.
5. **Parameters** receive data inside a function definition.
6. **Arguments** are the actual values passed during a function call.
7. `return` sends a value back to the caller.
8. `print()` displays a value but does not return it.
9. Functions can have default parameters.
10. Arguments can be positional or keyword arguments.
11. `*args` handles variable positional arguments.
12. `**kwargs` handles variable keyword arguments.
13. Variables created inside a function generally belong to its local scope.
14. Functions can receive and return collections.
15. Functions can call other functions.
16. A function can call itself using recursion.
17. Python supports anonymous functions using `lambda`.
18. Type hints can describe expected parameter and return types.
19. Good functions generally perform a clear, specific task.
20. Functions help make programs reusable, organized, readable, and maintainable.

---

# Interview Questions

### 1. What is a function?

A function is a reusable block of code designed to perform a specific task.

### 2. How do you create a function in Python?

Use the `def` keyword:

```python
def greet():
    print("Hello")
```

### 3. What is the difference between a parameter and an argument?

A parameter is a variable defined in a function definition, while an argument is the actual value passed to the function.

### 4. What does `return` do?

`return` sends a value from the function back to the caller and ends that function's current execution.

### 5. What happens when a function has no `return` statement?

It returns `None`.

### 6. What is the difference between `print()` and `return`?

`print()` displays data, while `return` sends data back to the caller.

### 7. What is a default parameter?

A parameter that has a predefined value.

```python
def greet(name="Guest"):
    print(name)
```

### 8. What are keyword arguments?

Arguments passed using parameter names.

```python
student(age=20, name="Riyas")
```

### 9. What are `*args` and `**kwargs`?

* `*args` allows a variable number of positional arguments.
* `**kwargs` allows a variable number of keyword arguments.

### 10. What is recursion?

Recursion occurs when a function calls itself.

### 11. What is a lambda function?

A lambda is a small anonymous function written using the `lambda` keyword.

### 12. What is variable scope?

Scope determines where a variable can be accessed. Variables created inside a function are generally local to that function.

### 13. Can a function return multiple values?

Yes.

```python
def calculate(a, b):
    return a + b, a - b
```

Python packages these returned values into a tuple.

### 14. Can a function accept a list as an argument?

Yes.

```python
def total(numbers):
    return sum(numbers)

print(total([10, 20, 30]))
```

### 15. Why are functions important in programming?

They allow code to be reused and help divide complex programs into smaller, organized, maintainable pieces.


[◀Back](.././)
---
