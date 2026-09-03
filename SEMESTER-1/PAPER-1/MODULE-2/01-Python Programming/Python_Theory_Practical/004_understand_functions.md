## Function Creation

**Functions** are reusable blocks of code designed to perform a specific task. Creating functions helps make programs more organized, reusable, and easier to maintain.

### Basic Syntax

```python
def function_name():
    # code to execute
```

### Example

```python
def greet():
    print("Hello, Python!")

greet()
```

Output:

```text
Hello, Python!
```

### Common Function Concepts

* **Defining a function** — Use the `def` keyword to create a function.
* **Calling a function** — Use the function name followed by `()` to execute it.
* **Parameters** — Variables defined in a function that receive input values.
* **Arguments** — Actual values passed to a function when calling it.
* **Return value** — A value sent back from the function using `return`.
* **Default parameters** — Parameters that have a predefined value.
* **Keyword arguments** — Arguments passed using parameter names.

[View more details →](./Python_Detaild/function_creation.md)


---

## Parameters

**Parameters** are variables defined inside a function that receive values when the function is called. They allow functions to accept input and work with different data.

### Types of Parameters

* **Positional parameters** — Receive arguments based on their position.
* **Default parameters** — Have a predefined value if no argument is provided.
* **Keyword parameters** — Can receive values using the parameter name.
* **Variable-length parameters** — Allow a function to accept a variable number of arguments using `*args` and `**kwargs`.
* **Positional-only parameters** — Can only receive values positionally.
* **Keyword-only parameters** — Must be provided using their parameter names.

### Example

```python
def greet(name, age):
    print(f"Hello {name}, you are {age} years old.")

greet("Riyas", 20)
```

Output:

```text
Hello Riyas, you are 20 years old.
```

Here, `name` and `age` are **parameters**, while `"Riyas"` and `20` are **arguments**.

[View more details →](./Python_Detaild/parameters.md)

---


## Return Values

A **return value** is the value a function sends back to the place where it was called. Python uses the `return` statement to send a result from a function.

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

### Key Concepts

* **`return` statement** — Sends a value back from a function.
* **Storing a return value** — The returned result can be assigned to a variable.
* **Returning multiple values** — A function can return multiple values as a tuple.
* **Returning different data types** — Functions can return numbers, strings, lists, dictionaries, objects, etc.
* **`return` without a value** — Returns `None`.
* **`print()` vs `return`** — `print()` displays a value, while `return` sends a value back to the caller.
* **Early return** — `return` immediately stops the function and sends the result back.

[View more details →](./Python_Detaild/return_values.md)

## Scope

**Scope** determines where a variable can be accessed in a Python program. It controls the visibility and lifetime of variables within different parts of the code.

### Types of Scope

* **Local scope** — A variable created inside a function can normally be accessed only inside that function.
* **Enclosing scope** — Applies to variables in an outer function when working with nested functions.
* **Global scope** — A variable created outside functions can be accessed throughout the module.
* **Built-in scope** — Contains Python's built-in names such as `print()`, `len()`, and `range()`.

Python follows the **LEGB rule** when searching for a variable:

**L → Local → E → Enclosing → G → Global → B → Built-in**

```python
name = "Global"

def greet():
    name = "Local"
    print(name)

greet()
```

Output:

```text
Local
```

[View more details →](./Python_Detaild/scope.md)


---

## Reusable Logic

**Reusable logic** means writing a piece of code once and using it multiple times instead of repeating the same code. In Python, functions are the main way to create reusable logic.

```python
def calculate_square(number):
    return number * number

print(calculate_square(5))
print(calculate_square(10))
```

Output:

```text
25
100
```

### Key Concepts

* **Functions** — Encapsulate logic that can be called whenever needed.
* **Parameters** — Allow the same logic to work with different inputs.
* **Return values** — Allow functions to send results back to the caller.
* **Function calls** — Reuse the same logic multiple times.
* **Modularity** — Break a large program into smaller, manageable functions.
* **Avoiding repetition** — Prevent duplicate code and make programs easier to maintain.

[View more details →](./Python_Detaild/reusable_logic.md)
