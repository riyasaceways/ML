[◀Back](.././)
---



# Parameters in Python

## What is a Parameter?

A **parameter** is a variable defined in a function definition that receives a value when the function is called.

Parameters allow a function to accept input and work with different values.

Example:

```python
def greet(name):
    print("Hello", name)
```

Here:

```python
name
```

is a **parameter**.

When the function is called:

```python
greet("Riyas")
```

`"Riyas"` is the **argument** passed to the parameter `name`.

---

# Parameters vs Arguments

These two terms are often confused.

### Parameter

A parameter is the variable written in the function definition.

```python
def greet(name):
    print(name)
```

`name` is a parameter.

### Argument

An argument is the actual value supplied when calling the function.

```python
greet("Riyas")
```

`"Riyas"` is an argument.

### Simple Difference

```text
Parameter → Variable in the function definition
Argument  → Actual value passed to the function
```

Example:

```python
def add(a, b):
    return a + b

add(10, 20)
```

Here:

* `a` and `b` → parameters
* `10` and `20` → arguments

---

# Creating Parameters

Parameters are written inside the parentheses of a function definition.

```python
def function_name(parameter):
    # function body
```

Example:

```python
def square(number):
    return number ** 2
```

Here:

```python
number
```

is the parameter.

Calling the function:

```python
print(square(5))
```

Output:

```text
25
```

---

# Multiple Parameters

A function can have multiple parameters.

```python
def add(a, b):
    return a + b
```

Calling it:

```python
result = add(10, 20)

print(result)
```

Output:

```text
30
```

The arguments are assigned according to their positions:

```text
a → 10
b → 20
```

---

# Positional Parameters

With positional arguments, values are assigned to parameters based on their position.

```python
def student(name, age, course):
    print(name)
    print(age)
    print(course)

student("Riyas", 20, "Python")
```

The mapping is:

```text
name   → "Riyas"
age    → 20
course → "Python"
```

The order matters.

```python
student("Riyas", 20, "Python")
```

is different from:

```python
student(20, "Riyas", "Python")
```

because the values are assigned based on position.

---

# Default Parameters

A parameter can have a default value.

```python
def greet(name="Guest"):
    print("Hello", name)
```

If no argument is provided:

```python
greet()
```

Output:

```text
Hello Guest
```

If an argument is provided:

```python
greet("Riyas")
```

Output:

```text
Hello Riyas
```

The supplied argument replaces the default value.

---

# Multiple Default Parameters

A function can have multiple default parameters.

```python
def student(name="Unknown", age=0):
    print(name, age)
```

Examples:

```python
student()
student("Riyas")
student("Riyas", 20)
```

Output:

```text
Unknown 0
Riyas 0
Riyas 20
```

---

# Required Parameters

A parameter without a default value is normally required.

```python
def add(a, b):
    return a + b
```

Both arguments are required:

```python
add(10, 20)
```

Calling:

```python
add(10)
```

raises a `TypeError` because the required parameter `b` was not provided.

---

# Positional Arguments

Arguments can be passed according to the parameter positions.

```python
def introduce(name, age):
    print(name, age)

introduce("Riyas", 20)
```

Output:

```text
Riyas 20
```

The first argument goes to `name`, and the second goes to `age`.

---

# Keyword Arguments

Arguments can also be passed using parameter names.

```python
def introduce(name, age):
    print(name, age)

introduce(age=20, name="Riyas")
```

Output:

```text
Riyas 20
```

Here, the order does not matter because the parameter names explicitly identify the values.

---

# Positional and Keyword Arguments Together

You can combine positional and keyword arguments.

```python
def student(name, age, course):
    print(name, age, course)

student("Riyas", age=20, course="Python")
```

This is valid.

However, positional arguments must come **before** keyword arguments.

Correct:

```python
student("Riyas", age=20)
```

Incorrect:

```python
student(name="Riyas", 20)
```

---

# Default Parameters and Keyword Arguments

Default parameters work especially well with keyword arguments.

```python
def student(name, age=20, course="Python"):
    print(name, age, course)
```

You can override only the value you need:

```python
student("Riyas", course="SQL")
```

Output:

```text
Riyas 20 SQL
```

The default value `20` is used for `age`.

---

# Parameter Ordering Rules

Python has rules about how parameters can be arranged.

A common valid arrangement is:

```python
def example(required, default=10):
    pass
```

A required parameter cannot normally appear after a default parameter.

This is invalid:

```python
def example(default=10, required):
    pass
```

Python raises a `SyntaxError`.

---

# Parameters with Different Kinds of Arguments

Consider:

```python
def student(name, age=20):
    print(name, age)
```

You can call it in several ways:

```python
student("Riyas")
student("Riyas", 21)
student(name="Riyas")
student(name="Riyas", age=21)
```

All of these are valid.

---

# `*args`

`*args` allows a function to accept a variable number of positional arguments.

Example:

```python
def add_numbers(*numbers):
    return sum(numbers)
```

Now you can pass different numbers of arguments:

```python
print(add_numbers(10, 20))
print(add_numbers(10, 20, 30))
print(add_numbers(10, 20, 30, 40))
```

Output:

```text
30
60
100
```

Inside the function, `numbers` is a tuple.

```python
def show(*numbers):
    print(type(numbers))
```

Output:

```text
<class 'tuple'>
```

---

# `**kwargs`

`**kwargs` allows a function to accept a variable number of keyword arguments.

```python
def student_info(**details):
    print(details)
```

Calling:

```python
student_info(
    name="Riyas",
    age=20,
    course="Python"
)
```

Output:

```text
{'name': 'Riyas', 'age': 20, 'course': 'Python'}
```

Inside the function, `details` is a dictionary.

---

# `*args` vs `**kwargs`

| Feature         | `*args`              | `**kwargs`         |
| --------------- | -------------------- | ------------------ |
| Accepts         | Positional arguments | Keyword arguments  |
| Inside function | Tuple                | Dictionary         |
| Example         | `func(10, 20)`       | `func(a=10, b=20)` |

---

# Combining Normal Parameters with `*args`

A function can have regular parameters followed by `*args`.

```python
def show(name, *subjects):
    print("Name:", name)
    print("Subjects:", subjects)

show("Riyas", "Python", "SQL", "HTML")
```

Output:

```text
Name: Riyas
Subjects: ('Python', 'SQL', 'HTML')
```

Here:

```text
name     → "Riyas"
subjects → ("Python", "SQL", "HTML")
```

---

# Combining Parameters with `**kwargs`

```python
def student(name, **details):
    print("Name:", name)
    print(details)

student(
    "Riyas",
    age=20,
    course="Python"
)
```

Output:

```text
Name: Riyas
{'age': 20, 'course': 'Python'}
```

---

# Combining `*args` and `**kwargs`

A function can accept both.

```python
def example(*args, **kwargs):
    print(args)
    print(kwargs)

example(10, 20, name="Riyas", age=20)
```

Output:

```text
(10, 20)
{'name': 'Riyas', 'age': 20}
```

---

# Positional-Only Parameters

Python allows parameters that must be passed positionally.

The `/` symbol marks the end of positional-only parameters.

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

because `a` and `b` are positional-only.

---

# Keyword-Only Parameters

The `*` symbol can be used to make parameters keyword-only.

```python
def student(name, *, age):
    print(name, age)
```

This is valid:

```python
student("Riyas", age=20)
```

This is invalid:

```python
student("Riyas", 20)
```

because `age` must be passed using its parameter name.

---

# Positional-Only and Keyword-Only Together

Python allows both types in the same function.

```python
def example(a, b, /, c, *, d, e):
    pass
```

The structure is:

```text
a, b → positional-only
c    → positional or keyword
d, e → keyword-only
```

For example:

```python
example(1, 2, 3, d=4, e=5)
```

---

# Type-Hinted Parameters

Parameters can include type hints.

```python
def add(a: int, b: int):
    return a + b
```

Here:

```python
a: int
b: int
```

indicate that the parameters are expected to contain integers.

Type hints are mainly used for readability and development tools. They do not automatically enforce the types at runtime.

---

# Parameters with Collection Data

Parameters can receive collections.

## List

```python
def calculate_total(numbers):
    return sum(numbers)

print(calculate_total([10, 20, 30]))
```

Output:

```text
60
```

---

## Tuple

```python
def display(values):
    for value in values:
        print(value)

display((10, 20, 30))
```

---

## Set

```python
def display(values):
    for value in values:
        print(value)

display({10, 20, 30})
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

# Passing Mutable Objects

Lists and dictionaries are mutable, so a function can modify the object when it mutates the object received.

Example:

```python
def add_number(numbers):
    numbers.append(40)

values = [10, 20, 30]

add_number(values)

print(values)
```

Output:

```text
[10, 20, 30, 40]
```

The function modified the list object.

This is important when working with mutable collections.

---

# Parameter Scope

Parameters are local variables within the function.

```python
def greet(name):
    print(name)

greet("Riyas")
```

The parameter `name` belongs to the function's local scope.

It cannot normally be accessed outside the function:

```python
print(name)
```

This raises a `NameError` if no separate `name` variable exists outside the function.

---

# Practical Example: Calculator

```python
def calculate(a, b):
    addition = a + b
    subtraction = a - b
    multiplication = a * b

    return addition, subtraction, multiplication

result = calculate(10, 5)

print(result)
```

Output:

```text
(15, 5, 50)
```

Here `a` and `b` are parameters.

---

# Practical Example: Student Information

```python
def student_info(name, age, course="Python"):
    print("Name:", name)
    print("Age:", age)
    print("Course:", course)

student_info("Riyas", 20)
```

Output:

```text
Name: Riyas
Age: 20
Course: Python
```

The `course` parameter uses a default value.

---

# Practical Example: Flexible Shopping Cart

```python
def calculate_total(*prices):
    return sum(prices)

print(calculate_total(100, 200))
print(calculate_total(100, 200, 50, 75))
```

Output:

```text
300
425
```

`*prices` allows the function to accept any number of positional arguments.

---

# Practical Example: User Information

```python
def display_user(**user):
    for key, value in user.items():
        print(key, ":", value)

display_user(
    name="Riyas",
    age=20,
    course="Python"
)
```

Output:

```text
name : Riyas
age : 20
course : Python
```

---

# Common Mistakes

## 1. Forgetting a required argument

```python
def add(a, b):
    return a + b

add(10)
```

This raises a `TypeError` because `b` is missing.

---

## 2. Providing too many arguments

```python
def add(a, b):
    return a + b

add(10, 20, 30)
```

This also raises a `TypeError`.

---

## 3. Putting a required parameter after a default parameter

Incorrect:

```python
def example(a=10, b):
    pass
```

Correct:

```python
def example(a, b=10):
    pass
```

---

## 4. Passing a positional argument after a keyword argument

Incorrect:

```python
def student(name, age):
    pass

student(name="Riyas", 20)
```

Correct:

```python
student("Riyas", age=20)
```

---

## 5. Confusing `*args` and `**kwargs`

```python
*args
```

handles positional arguments.

```python
**kwargs
```

handles keyword arguments.

---

## 6. Assuming type hints automatically validate parameters

```python
def add(a: int, b: int):
    return a + b
```

The annotations do not automatically force callers to provide integers.

---

# Parameter Types Summary

| Parameter Type      | Example            | Purpose                               |
| ------------------- | ------------------ | ------------------------------------- |
| Required            | `def f(x):`        | Must normally receive a value         |
| Default             | `def f(x=10):`     | Uses a default when omitted           |
| Positional          | `def f(x):`        | Can receive a positional argument     |
| Keyword             | `def f(x):`        | Can receive a value by parameter name |
| Variable positional | `def f(*args):`    | Accepts many positional arguments     |
| Variable keyword    | `def f(**kwargs):` | Accepts many keyword arguments        |
| Positional-only     | `def f(x, /):`     | Must be passed positionally           |
| Keyword-only        | `def f(*, x):`     | Must be passed by name                |

---

# Parameter Ordering Quick Reference

A function can be structured using these categories:

```python
def function(
    positional_only,
    /,
    normal_parameter,
    default_parameter=10,
    *args,
    keyword_only,
    another_keyword_only=20,
    **kwargs
):
    pass
```

The exact combination is governed by Python's function parameter rules.

The important idea is:

```text
Positional-only
       ↓
Normal / positional-or-keyword
       ↓
*args
       ↓
Keyword-only
       ↓
**kwargs
```

---

# Quick Reference

```python
# Required parameter
def greet(name):
    print(name)


# Multiple parameters
def add(a, b):
    return a + b


# Default parameter
def greet(name="Guest"):
    print(name)


# Positional arguments
add(10, 20)


# Keyword arguments
add(a=10, b=20)


# Variable positional parameters
def total(*numbers):
    return sum(numbers)


# Variable keyword parameters
def information(**details):
    return details


# Positional-only parameters
def add(a, b, /):
    return a + b


# Keyword-only parameters
def student(name, *, age):
    return name, age


# Type-hinted parameters
def square(number: int) -> int:
    return number ** 2
```

---

# Key Points to Remember

1. A **parameter** is a variable defined in a function definition.
2. An **argument** is the actual value passed to a function.
3. Parameters allow functions to accept input.
4. A function can have one or multiple parameters.
5. Required parameters normally need an argument.
6. Default parameters provide fallback values.
7. Positional arguments are assigned according to their position.
8. Keyword arguments are assigned using parameter names.
9. `*args` accepts a variable number of positional arguments.
10. `**kwargs` accepts a variable number of keyword arguments.
11. `*args` is received as a tuple.
12. `**kwargs` is received as a dictionary.
13. `/` can define positional-only parameters.
14. `*` can define keyword-only parameters.
15. Parameters can receive collections such as lists, tuples, sets, and dictionaries.
16. Parameters are local to the function.
17. Type hints can describe expected parameter types.
18. Mutable objects such as lists can be modified inside a function.
19. Python has specific rules governing parameter order.
20. Choosing appropriate parameters makes functions more flexible and reusable.

---

# Interview Questions

### 1. What is a parameter?

A parameter is a variable defined in a function that receives a value when the function is called.

### 2. What is the difference between a parameter and an argument?

A parameter is defined in the function definition, while an argument is the actual value passed during the function call.

### 3. What is a default parameter?

A parameter with a predefined value that is used when the caller does not provide an argument.

```python
def greet(name="Guest"):
    print(name)
```

### 4. What are positional arguments?

Arguments assigned to parameters according to their position.

```python
add(10, 20)
```

### 5. What are keyword arguments?

Arguments passed using parameter names.

```python
add(a=10, b=20)
```

### 6. What is `*args`?

`*args` allows a function to receive a variable number of positional arguments. Inside the function, the values are stored in a tuple.

### 7. What is `**kwargs`?

`**kwargs` allows a function to receive a variable number of keyword arguments. Inside the function, the values are stored in a dictionary.

### 8. What is a positional-only parameter?

A parameter that can only receive a value through positional arguments.

```python
def add(a, b, /):
    return a + b
```

### 9. What is a keyword-only parameter?

A parameter that must be supplied using its parameter name.

```python
def student(name, *, age):
    pass
```

### 10. Can a function have both `*args` and `**kwargs`?

Yes.

```python
def example(*args, **kwargs):
    print(args)
    print(kwargs)
```

### 11. Can parameters have different data types?

Yes. Python functions can receive values of different types unless the function's logic requires specific types.

### 12. Can a parameter have a mutable object as its default value?

Yes, Python allows it syntactically, but using mutable defaults such as `[]` or `{}` can cause unexpected behavior because the same default object is reused across calls. A common safer pattern is:

```python
def add_item(item, items=None):
    if items is None:
        items = []

    items.append(item)
    return items
```

### 13. Can a function accept a list as a parameter?

Yes.

```python
def total(numbers):
    return sum(numbers)

print(total([10, 20, 30]))
```

### 14. Can parameters have type hints?

Yes.

```python
def add(a: int, b: int) -> int:
    return a + b
```

### 15. Why are parameters important?

Parameters allow the same function to work with different input values, making the function more reusable and flexible.

[◀Back](.././)
---
