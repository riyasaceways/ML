[◀Back](.././)
---



# Scope

## What is Scope?

**Scope** refers to the region of a Python program where a variable or name can be accessed.

In simple terms, scope answers the question:

> **"Where can I use this variable?"**

Example:

```python
name = "Riyas"

def greet():
    print(name)

greet()
```

Output:

```text
Riyas
```

Here, `name` is defined outside the function, so it belongs to the **global scope** and can be accessed inside the function.

---

## Why is Scope Important?

Scope helps Python:

* Determine where variables are available.
* Prevent variables from interfering with each other.
* Manage variables inside functions.
* Control how names are resolved.
* Avoid unnecessary global variables.

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

The two `x` variables are different because they belong to different scopes.

---

# Types of Scope

Python commonly describes four levels of scope:

1. **Local scope**
2. **Enclosing scope**
3. **Global scope**
4. **Built-in scope**

These are remembered using the **LEGB rule**.

```text
L → Local
E → Enclosing
G → Global
B → Built-in
```

---

# 1. Local Scope

A variable created inside a function normally has **local scope**.

```python
def greet():
    name = "Riyas"
    print(name)

greet()
```

Output:

```text
Riyas
```

Here, `name` is local to `greet()`.

Trying to access it outside the function:

```python
def greet():
    name = "Riyas"

greet()

print(name)
```

produces:

```text
NameError
```

because `name` does not exist in the global scope.

---

## Local Variables

Local variables are created when the function executes.

```python
def calculate():
    result = 100
    print(result)

calculate()
```

`result` is available inside `calculate()`.

It is not normally available outside the function.

---

## Different Functions Can Have Variables With the Same Name

```python
def first():
    name = "Riyas"
    print(name)

def second():
    name = "Alex"
    print(name)

first()
second()
```

Output:

```text
Riyas
Alex
```

Each function has its own local `name`.

---

# 2. Enclosing Scope

The **enclosing scope** occurs when one function is defined inside another function.

Example:

```python
def outer():
    name = "Riyas"

    def inner():
        print(name)

    inner()

outer()
```

Output:

```text
Riyas
```

Here:

```text
outer()
 └── inner()
```

`name` belongs to the `outer()` function.

It is not local to `inner()`, but `inner()` can access it.

This is called the **enclosing scope**.

---

## Nested Function Example

```python
def outer():
    message = "Hello"

    def inner():
        print(message)

    inner()

outer()
```

Output:

```text
Hello
```

The `inner()` function searches its local scope first.

It does not find `message` there, so Python checks the enclosing scope and finds it in `outer()`.

---

# 3. Global Scope

A variable created outside functions belongs to the **global scope** of that module.

```python
name = "Riyas"

def greet():
    print(name)

greet()
```

Output:

```text
Riyas
```

The function can read the global variable because Python does not find a local variable named `name`.

---

## Global Variables

Example:

```python
age = 20

def show_age():
    print(age)

show_age()
```

Output:

```text
20
```

`age` is defined outside the function, so it has global scope.

---

# Local vs Global

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

The global variable:

```python
x = 10
```

and the local variable:

```python
x = 20
```

are different variables.

The local `x` **shadows** the global `x` inside the function.

---

# Reading a Global Variable

A function can read a global variable without using the `global` keyword.

```python
count = 10

def show_count():
    print(count)

show_count()
```

Output:

```text
10
```

The `global` keyword is not required simply to read the variable.

---

# Modifying a Global Variable

If you want to assign a new value to a global variable from inside a function, use the `global` keyword.

```python
count = 10

def update_count():
    global count
    count = 20

update_count()

print(count)
```

Output:

```text
20
```

Without `global`:

```python
count = 10

def update_count():
    count = 20

update_count()

print(count)
```

Output:

```text
10
```

The assignment creates a local variable instead of changing the global variable.

---

# The `global` Keyword

The `global` keyword tells Python:

> "This name refers to the global variable, not a new local variable."

Example:

```python
score = 50

def update_score():
    global score
    score = 100

update_score()

print(score)
```

Output:

```text
100
```

---

## When Should You Avoid `global`?

Although `global` is valid Python, excessive use of global variables can make programs harder to understand and maintain.

Instead of:

```python
balance = 1000

def deposit(amount):
    global balance
    balance += amount
```

it is often cleaner to use parameters and return values:

```python
def deposit(balance, amount):
    return balance + amount

balance = 1000
balance = deposit(balance, 500)

print(balance)
```

Output:

```text
1500
```

This keeps the function's inputs and outputs clear.

---

# 4. Built-in Scope

The **built-in scope** contains names provided by Python itself.

Examples include:

```python
print()
len()
range()
sum()
max()
min()
type()
```

For example:

```python
numbers = [10, 20, 30]

print(len(numbers))
```

Output:

```text
3
```

Python finds `len` in the built-in scope.

---

# The LEGB Rule

Python uses the **LEGB rule** to search for names.

```text
L → Local
E → Enclosing
G → Global
B → Built-in
```

When Python encounters a variable name, it searches these scopes in order.

---

## LEGB Example

```python
x = "Global"

def outer():
    x = "Enclosing"

    def inner():
        x = "Local"
        print(x)

    inner()

outer()
```

Output:

```text
Local
```

Python finds `x` in the local scope first.

Therefore, it does not need to search the enclosing or global scopes.

---

## LEGB Search Example

```python
x = "Global"

def outer():
    x = "Enclosing"

    def inner():
        print(x)

    inner()

outer()
```

Output:

```text
Enclosing
```

There is no local `x` inside `inner()`.

Python searches:

```text
Local      → Not found
Enclosing  → Found
```

So it uses `"Enclosing"`.

---

## Another LEGB Example

```python
x = "Global"

def outer():
    def inner():
        print(x)

    inner()

outer()
```

Output:

```text
Global
```

Python searches:

```text
Local      → Not found
Enclosing  → Not found
Global     → Found
```

---

# Variable Shadowing

**Variable shadowing** occurs when a variable in an inner scope has the same name as a variable in an outer scope.

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

The local variable shadows the global variable inside `greet()`.

---

# Scope Inside Loops

A `for` loop or `while` loop does **not** create a separate local scope in Python.

```python
for i in range(3):
    x = i

print(x)
```

Output:

```text
2
```

The variable `x` remains available after the loop.

This is different from a function:

```python
def test():
    x = 10

test()

print(x)
```

Here, `x` is not available outside the function.

---

# Scope Inside `if` Statements

Similarly, an `if` block does not create a separate scope.

```python
if True:
    message = "Hello"

print(message)
```

Output:

```text
Hello
```

The `message` variable remains accessible because the `if` block does not create a new scope.

---

# Function Scope

Functions create a new local scope.

```python
x = 10

def test():
    y = 20
    print(x)
    print(y)

test()
```

Inside the function:

* `x` can be accessed from the global scope.
* `y` is local to the function.

Outside:

```python
print(x)
```

works.

But:

```python
print(y)
```

causes a `NameError`.

---

# Scope and Parameters

Function parameters are local variables.

```python
def greet(name):
    print(name)

greet("Riyas")
```

Here, `name` is a local variable of `greet()`.

It only exists within the function's scope.

---

# Scope and Return Values

A local variable can be returned from a function.

```python
def calculate():
    result = 100
    return result

answer = calculate()

print(answer)
```

Output:

```text
100
```

The local variable `result` itself is not available outside the function.

Instead, its value is returned and stored in `answer`.

---

# `nonlocal` Keyword

The `nonlocal` keyword is used with nested functions when you want to modify a variable belonging to an enclosing function.

Example:

```python
def outer():
    count = 0

    def inner():
        nonlocal count
        count += 1

    inner()

    print(count)

outer()
```

Output:

```text
1
```

Without `nonlocal`, assigning to `count` inside `inner()` would create a new local variable.

---

## `global` vs `nonlocal`

| Keyword    | Refers to                |
| ---------- | ------------------------ |
| `global`   | Global scope             |
| `nonlocal` | Enclosing function scope |

Example:

```python
x = 10

def outer():
    y = 20

    def inner():
        global x
        nonlocal y

        x = 100
        y = 200

    inner()

    print(y)

outer()

print(x)
```

Output:

```text
200
100
```

---

# Scope Example: Counter

Consider:

```python
count = 0

def increase():
    global count
    count += 1

increase()
increase()

print(count)
```

Output:

```text
2
```

The `global` keyword allows the function to modify the global variable.

A cleaner alternative is to use a return value:

```python
def increase(count):
    return count + 1

count = 0

count = increase(count)
count = increase(count)

print(count)
```

Output:

```text
2
```

---

# Scope Example: Student Data

```python
school = "ABC School"

def student_info(name, age):
    grade = "A"

    print(name)
    print(age)
    print(grade)
    print(school)

student_info("Riyas", 20)
```

Here:

* `school` → global variable
* `name` → local parameter
* `age` → local parameter
* `grade` → local variable

---

# Scope Example: Nested Functions

```python
def school():
    school_name = "ABC School"

    def student():
        student_name = "Riyas"

        print(school_name)
        print(student_name)

    student()

school()
```

The scopes are:

```text
Global
  │
  └── school()
       │
       ├── school_name
       │
       └── student()
            │
            └── student_name
```

`student()` can access `school_name` because it belongs to the enclosing scope.

---

# Local Scope vs Global Scope

| Feature                                       | Local                              | Global                                        |
| --------------------------------------------- | ---------------------------------- | --------------------------------------------- |
| Created                                       | Inside a function                  | Outside functions                             |
| Accessible                                    | Inside its function                | Throughout the module                         |
| Lifetime                                      | During relevant function execution | Generally while the module/program is running |
| Can be accessed by nested functions           | Yes                                | Yes                                           |
| Requires `global` to read                     | No                                 | No                                            |
| Requires `global` to reassign from a function | Not applicable                     | Yes                                           |

---

# Enclosing Scope vs Global Scope

Consider:

```python
x = "Global"

def outer():
    x = "Enclosing"

    def inner():
        print(x)

    inner()

outer()
```

Output:

```text
Enclosing
```

The enclosing variable takes priority over the global variable because of LEGB.

---

# Scope and Mutable Objects

Scope determines where the variable name can be accessed, but a function can still modify a mutable object passed to it.

Example:

```python
numbers = [10, 20]

def add_number(items):
    items.append(30)

add_number(numbers)

print(numbers)
```

Output:

```text
[10, 20, 30]
```

The list is modified because lists are mutable.

This is different from rebinding the variable itself.

---

# Avoiding Global Variables

Instead of relying heavily on global variables:

```python
total = 0

def add(amount):
    global total
    total += amount
```

Prefer:

```python
def add(total, amount):
    return total + amount

total = 0

total = add(total, 100)
total = add(total, 200)

print(total)
```

Output:

```text
300
```

Using parameters and return values makes the data flow easier to understand.

---

# Common Scope Mistakes

## 1. Trying to Access a Local Variable Outside Its Function

```python
def test():
    value = 10

test()

print(value)
```

This causes:

```text
NameError
```

because `value` is local to `test()`.

---

## 2. Accidentally Creating a Local Variable

```python
count = 10

def update():
    count = 20

update()

print(count)
```

Output:

```text
10
```

The assignment inside `update()` creates a local `count`.

It does not change the global `count`.

---

## 3. Forgetting `global`

If you intend to reassign a global variable:

```python
count = 10

def update():
    global count
    count = 20
```

Without `global`, Python treats the assignment as local.

---

## 4. Confusing `if` Scope With Function Scope

This works:

```python
if True:
    value = 10

print(value)
```

But this does not:

```python
def test():
    value = 10

test()

print(value)
```

An `if` block does not create a new scope, while a function does.

---

# Quick Reference

```text
Local
  ↓
Enclosing
  ↓
Global
  ↓
Built-in
```

This is the **LEGB rule**.

### Local

```python
def test():
    x = 10
```

### Enclosing

```python
def outer():
    x = 10

    def inner():
        print(x)
```

### Global

```python
x = 10

def test():
    print(x)
```

### Built-in

```python
print(len([1, 2, 3]))
```

`len()` comes from Python's built-in namespace.

---

# Key Points

* **Scope** determines where a variable can be accessed.
* A function creates a **local scope**.
* Variables defined outside functions normally belong to the **global scope**.
* Nested functions create an **enclosing scope**.
* Python's built-in functions and names belong to the **built-in scope**.
* Python searches names according to the **LEGB rule**.
* `global` allows a function to reassign a global variable.
* `nonlocal` allows a nested function to modify a variable from an enclosing function.
* `if`, `for`, and `while` blocks do not normally create their own scope in Python.
* Function parameters are local variables.
* Using parameters and return values is often preferable to relying heavily on global variables.

---

# Interview Questions

### 1. What is scope in Python?

Scope is the region of a program where a variable or name can be accessed.

### 2. What are the four types of scope in Python?

* Local
* Enclosing
* Global
* Built-in

### 3. What is the LEGB rule?

LEGB stands for:

**Local → Enclosing → Global → Built-in**

It describes the order Python follows when searching for a name.

### 4. What is a local variable?

A variable defined inside a function that is normally accessible only within that function.

### 5. What is a global variable?

A variable defined outside functions that belongs to the module's global scope.

### 6. Can a function read a global variable?

Yes.

```python
x = 10

def test():
    print(x)
```

### 7. How can a function modify a global variable?

Use the `global` keyword.

```python
x = 10

def test():
    global x
    x = 20
```

### 8. What is the `nonlocal` keyword?

`nonlocal` allows a nested function to modify a variable belonging to an enclosing function.

### 9. Do `if` and `for` blocks create a new scope in Python?

No. Unlike functions, these blocks do not normally create a separate scope.

### 10. What happens when a local and global variable have the same name?

The local variable takes precedence inside the function.

```python
x = 10

def test():
    x = 20
    print(x)

test()
```

Output:

```text
20
```

### 11. What is variable shadowing?

Variable shadowing occurs when a variable in an inner scope has the same name as a variable in an outer scope.

### 12. Why should excessive global variables be avoided?

They can make programs harder to understand, test, debug, and maintain. Parameters and return values often provide clearer data flow.



[◀Back](.././)
---
