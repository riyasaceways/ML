[◀Back](.././)
---


# Reusable Logic

## What is Reusable Logic?

**Reusable logic** means writing a piece of code once and using it multiple times whenever the same operation is needed.

Instead of repeatedly writing:

```python
print(10 * 10)
print(20 * 20)
print(30 * 30)
```

we can create reusable logic:

```python
def square(number):
    return number * number

print(square(10))
print(square(20))
print(square(30))
```

Output:

```text
100
400
900
```

The calculation is written only once.

---

## Why Use Reusable Logic?

Reusable logic helps to:

* Reduce duplicate code.
* Make programs easier to read.
* Make programs easier to maintain.
* Make debugging easier.
* Avoid repeating the same logic.
* Make code more modular.
* Allow the same operation to work with different inputs.
* Make large programs easier to organize.

---

# Functions and Reusable Logic

Functions are the primary way to create reusable logic in Python.

Basic structure:

```python
def function_name():
    # reusable logic
```

Example:

```python
def greet():
    print("Hello!")

greet()
greet()
greet()
```

Output:

```text
Hello!
Hello!
Hello!
```

The logic inside `greet()` is written once but used three times.

---

# Reusable Logic With Parameters

Parameters make reusable logic more flexible.

Without parameters:

```python
def greet():
    print("Hello, Riyas")
```

This function is specific to one name.

With a parameter:

```python
def greet(name):
    print(f"Hello, {name}")
```

Now the same function can work with different names:

```python
greet("Riyas")
greet("Alex")
greet("John")
```

Output:

```text
Hello, Riyas
Hello, Alex
Hello, John
```

The logic remains the same while the input changes.

---

# Reusable Logic With Return Values

Return values allow reusable logic to produce a result.

```python
def add(a, b):
    return a + b
```

The function can now be reused:

```python
result1 = add(10, 20)
result2 = add(50, 30)

print(result1)
print(result2)
```

Output:

```text
30
80
```

The same addition logic works for different values.

---

# Reusing a Function Multiple Times

A function can be called as many times as needed.

```python
def calculate_area(length, width):
    return length * width

area1 = calculate_area(10, 5)
area2 = calculate_area(20, 8)
area3 = calculate_area(15, 4)

print(area1)
print(area2)
print(area3)
```

Output:

```text
50
160
60
```

Instead of writing the area calculation three times, we write it once.

---

# Avoiding Code Duplication

Consider this code:

```python
length1 = 10
width1 = 5
area1 = length1 * width1

length2 = 20
width2 = 8
area2 = length2 * width2

length3 = 15
width3 = 4
area3 = length3 * width3
```

The calculation is repeated.

A reusable function is cleaner:

```python
def calculate_area(length, width):
    return length * width

area1 = calculate_area(10, 5)
area2 = calculate_area(20, 8)
area3 = calculate_area(15, 4)
```

The calculation exists in only one place.

---

# Why Avoid Repeated Logic?

Suppose the calculation needs to change.

Repeated version:

```python
area1 = length1 * width1
area2 = length2 * width2
area3 = length3 * width3
```

You may need to modify multiple places.

With reusable logic:

```python
def calculate_area(length, width):
    return length * width
```

The logic has one central location.

This makes maintenance easier.

---

# Reusable Logic With Conditions

Functions can contain conditional logic.

```python
def check_age(age):
    if age >= 18:
        return "Adult"
    else:
        return "Minor"
```

The function can be reused:

```python
print(check_age(20))
print(check_age(15))
print(check_age(30))
```

Output:

```text
Adult
Minor
Adult
```

---

# Reusable Logic With Loops

Functions can also contain loops.

```python
def print_numbers(limit):
    for number in range(1, limit + 1):
        print(number)

print_numbers(5)
```

Output:

```text
1
2
3
4
5
```

The same logic can be reused with another limit:

```python
print_numbers(10)
```

---

# Reusable Logic With Collections

Functions can process collections.

```python
def calculate_total(numbers):
    total = 0

    for number in numbers:
        total += number

    return total
```

Now it can work with different lists:

```python
numbers1 = [10, 20, 30]
numbers2 = [5, 15, 25, 35]

print(calculate_total(numbers1))
print(calculate_total(numbers2))
```

Output:

```text
60
80
```

The calculation logic does not need to be rewritten.

---

# Reusable Validation Logic

A function can contain validation rules.

```python
def is_valid_age(age):
    return age >= 18
```

The function can be reused wherever age validation is needed:

```python
age = 20

if is_valid_age(age):
    print("Allowed")
else:
    print("Not allowed")
```

Another part of the program can use the same function:

```python
user_age = 16

if is_valid_age(user_age):
    print("Registration allowed")
else:
    print("Registration denied")
```

This prevents the same validation condition from being duplicated throughout the program.

---

# Combining Multiple Reusable Functions

Large problems can be divided into smaller functions.

For example, a student result system could use:

```python
def calculate_total(marks):
    return sum(marks)


def calculate_average(marks):
    return sum(marks) / len(marks)


def check_pass(average):
    return average >= 50
```

Then:

```python
marks = [80, 70, 90]

total = calculate_total(marks)
average = calculate_average(marks)
passed = check_pass(average)

print(total)
print(average)
print(passed)
```

Output:

```text
240
80.0
True
```

Each function performs one specific task.

---

# Single Responsibility

A reusable function should ideally have a clear purpose.

Instead of creating one large function:

```python
def student_system():
    # input
    # validation
    # calculations
    # formatting
    # output
    # saving
```

you can divide the logic:

```python
def get_student_name():
    ...

def validate_marks(marks):
    ...

def calculate_average(marks):
    ...

def calculate_grade(average):
    ...
```

Each function becomes easier to understand and reuse.

---

# Functions Calling Other Functions

Reusable functions can call other reusable functions.

```python
def calculate_total(a, b, c):
    return a + b + c


def calculate_average(a, b, c):
    total = calculate_total(a, b, c)
    return total / 3
```

Now:

```python
average = calculate_average(80, 70, 90)

print(average)
```

Output:

```text
80.0
```

The second function reuses the logic from the first function.

---

# Reusable Logic and Parameters

Parameters are important because they prevent functions from being tied to one specific value.

Less reusable:

```python
def calculate():
    return 10 + 20
```

More reusable:

```python
def calculate(a, b):
    return a + b
```

Now:

```python
calculate(10, 20)
calculate(100, 200)
calculate(5, 7)
```

The logic remains the same while the data changes.

---

# Reusable Logic and Return Values

A reusable function should often return a result instead of only printing it.

Less reusable:

```python
def calculate(a, b):
    print(a + b)
```

More reusable:

```python
def calculate(a, b):
    return a + b
```

Now the result can be:

```python
result = calculate(10, 20)
```

or:

```python
print(calculate(10, 20))
```

or:

```python
total = calculate(10, 20)
double = total * 2
```

The returned value can be used in different ways.

---

# Reusable Logic vs Copy-Paste

### Repeated code

```python
price1 = 100
discount1 = price1 * 0.10
final1 = price1 - discount1

price2 = 200
discount2 = price2 * 0.10
final2 = price2 - discount2
```

### Reusable logic

```python
def calculate_discounted_price(price):
    discount = price * 0.10
    return price - discount

final1 = calculate_discounted_price(100)
final2 = calculate_discounted_price(200)
```

The second approach is easier to maintain.

---

# Reusable Logic in a Real-World Example

Imagine an online shopping program.

Without reusable functions, you might repeatedly write:

```python
subtotal = price * quantity
discount = subtotal * 0.10
final_price = subtotal - discount
```

A reusable function can handle this:

```python
def calculate_price(price, quantity, discount_rate):
    subtotal = price * quantity
    discount = subtotal * discount_rate
    return subtotal - discount
```

Now:

```python
item1 = calculate_price(100, 2, 0.10)
item2 = calculate_price(500, 1, 0.20)

print(item1)
print(item2)
```

Output:

```text
180.0
400.0
```

The same pricing logic can be used for many products.

---

# Reusable Logic With Default Parameters

Default parameters can make reusable functions more convenient.

```python
def calculate_discount(price, rate=0.10):
    return price - (price * rate)
```

Now:

```python
print(calculate_discount(100))
print(calculate_discount(100, 0.20))
```

Output:

```text
90.0
80.0
```

The function can work with the default discount or a custom discount.

---

# Reusable Logic With `*args`

`*args` allows a function to accept a variable number of positional arguments.

```python
def calculate_total(*numbers):
    return sum(numbers)
```

Now:

```python
print(calculate_total(10, 20))
print(calculate_total(10, 20, 30))
print(calculate_total(10, 20, 30, 40))
```

Output:

```text
30
60
100
```

The same logic works with different numbers of inputs.

---

# Reusable Logic With `**kwargs`

`**kwargs` allows a function to accept a variable number of keyword arguments.

```python
def show_student(**details):
    for key, value in details.items():
        print(f"{key}: {value}")
```

Example:

```python
show_student(
    name="Riyas",
    age=20,
    course="Python"
)
```

Output:

```text
name: Riyas
age: 20
course: Python
```

---

# Reusable Logic and Modules

Reusable logic does not have to remain in one file.

For example:

```text
project/
│
├── main.py
└── calculations.py
```

`calculations.py`:

```python
def add(a, b):
    return a + b
```

`main.py`:

```python
from calculations import add

result = add(10, 20)

print(result)
```

Output:

```text
30
```

This allows reusable logic to be shared between different Python files.

---

# Reusable Logic and Libraries

Python itself provides many reusable functions through its standard library.

For example:

```python
import math

print(math.sqrt(25))
```

Output:

```text
5.0
```

Instead of implementing square-root logic yourself, you can reuse functionality provided by the library.

---

# Reusable Logic and DRY

A common programming principle is **DRY**:

> **Don't Repeat Yourself**

The idea is to avoid unnecessarily duplicating the same logic.

For example, instead of:

```python
total1 = price1 + tax1
total2 = price2 + tax2
total3 = price3 + tax3
```

you can create:

```python
def calculate_total(price, tax):
    return price + tax
```

and reuse it:

```python
total1 = calculate_total(price1, tax1)
total2 = calculate_total(price2, tax2)
total3 = calculate_total(price3, tax3)
```

DRY does not mean that every repeated line must become a function. The goal is to avoid unnecessary duplication of meaningful logic.

---

# Reusable Logic and Maintainability

Consider:

```python
def calculate_grade(mark):
    if mark >= 90:
        return "A"
    elif mark >= 75:
        return "B"
    elif mark >= 50:
        return "C"
    else:
        return "F"
```

If the grading rules change, there is one function to update.

Every part of the program that calls:

```python
calculate_grade(mark)
```

automatically uses the updated logic.

---

# Reusable Logic and Testing

Functions are easier to test because they can be tested independently.

```python
def is_even(number):
    return number % 2 == 0
```

You can test different inputs:

```python
print(is_even(10))
print(is_even(7))
print(is_even(0))
```

Output:

```text
True
False
True
```

A small, focused function is usually easier to verify than a large block of mixed logic.

---

# Reusable Logic: Good vs Poor Design

### Poor design

```python
def process():
    # read user input
    # calculate total
    # validate data
    # calculate discount
    # print result
    # save data
```

One function is responsible for many unrelated tasks.

### Better design

```python
def calculate_total(price, quantity):
    return price * quantity


def calculate_discount(total, rate):
    return total * rate


def calculate_final_price(total, discount):
    return total - discount
```

Now each function has a clear responsibility.

---

# Practical Example: Calculator

```python
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


def multiply(a, b):
    return a * b


def divide(a, b):
    if b == 0:
        return None

    return a / b
```

The functions can be reused anywhere:

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

---

# Practical Example: Password Validation

```python
def is_valid_password(password):
    if len(password) < 8:
        return False

    return True
```

Usage:

```python
password = input("Enter password: ")

if is_valid_password(password):
    print("Valid password")
else:
    print("Password must contain at least 8 characters")
```

The validation logic can later be reused during registration, login, password changes, or other parts of the application.

---

# Common Mistakes

## 1. Repeating the Same Logic

Avoid copying the same calculation into multiple places when it represents one reusable operation.

Instead, consider creating a function.

---

## 2. Creating Functions That Are Too Large

A function containing many unrelated responsibilities becomes difficult to reuse.

Break large logic into smaller functions when appropriate.

---

## 3. Hard-Coding Values

Less reusable:

```python
def calculate():
    return 100 * 5
```

More reusable:

```python
def calculate(price, quantity):
    return price * quantity
```

---

## 4. Using `print()` When a Result Is Needed

Less reusable:

```python
def add(a, b):
    print(a + b)
```

Better:

```python
def add(a, b):
    return a + b
```

---

## 5. Over-Abstraction

Not every two repeated lines need a separate function.

For example, creating a function for a simple one-time operation may make the code more complicated rather than simpler.

Reusable logic should improve clarity, not reduce it.

---

# A Simple Pattern for Reusable Logic

A common pattern is:

```text
Input
  ↓
Function
  ↓
Processing
  ↓
Return
  ↓
Use the result
```

Example:

```python
def calculate_area(length, width):
    return length * width

area = calculate_area(10, 5)

print(area)
```

Flow:

```text
10, 5
 ↓
calculate_area()
 ↓
10 × 5
 ↓
50
 ↓
area
```

---

# Reusable Logic Checklist

When creating a piece of logic, ask:

1. Am I repeating this logic?
2. Does this operation have a clear purpose?
3. Can I give it parameters instead of hard-coding values?
4. Should it return a result?
5. Could another part of the program use it?
6. Would putting it in a function make the code clearer?
7. Is the function doing one main job?
8. Would extracting it make the program easier to test or maintain?

---

# Quick Reference

| Concept    | Purpose                                |
| ---------- | -------------------------------------- |
| Function   | Encapsulates reusable logic            |
| Parameter  | Allows different input values          |
| Argument   | Provides values to parameters          |
| `return`   | Sends a result back                    |
| Module     | Stores reusable logic in a Python file |
| Library    | Provides reusable functionality        |
| DRY        | Avoid unnecessary code duplication     |
| Modularity | Breaks a program into manageable parts |

---

# Key Points

* **Reusable logic** means writing logic once and using it multiple times.
* Functions are the main mechanism for creating reusable logic in Python.
* Parameters allow the same function to work with different inputs.
* Return values allow the result to be reused by other code.
* Reusable functions help reduce code duplication.
* Breaking a large program into smaller functions improves modularity.
* Functions with a clear responsibility are easier to understand and test.
* Modules allow reusable functions to be shared across Python files.
* DRY means **Don't Repeat Yourself**.
* Reusability should improve clarity rather than create unnecessary complexity.

---

# Interview Questions

### 1. What is reusable logic?

Reusable logic is code written once that can be used multiple times instead of being duplicated.

### 2. How do you create reusable logic in Python?

The most common way is to create functions.

```python
def add(a, b):
    return a + b
```

### 3. Why are functions useful for reusable logic?

They allow code to be organized into independent, callable units that can accept different inputs and produce results.

### 4. How do parameters make logic reusable?

Parameters allow the same function to process different values.

```python
def square(number):
    return number * number
```

### 5. Why is `return` useful for reusable functions?

It allows the function to send a result back so the calling code can use that result in different ways.

### 6. What does DRY mean?

**DRY** means **Don't Repeat Yourself**. It is a principle of reducing unnecessary duplication of logic.

### 7. What is modularity?

Modularity means dividing a program into smaller, independent components such as functions and modules.

### 8. Should every repeated line of code become a function?

No. Abstraction should be used when it improves clarity, maintainability, or reuse. Excessive abstraction can make simple code harder to understand.

### 9. How can reusable logic be shared between Python files?

Reusable functions can be placed in a module and imported into another Python file.

```python
from calculations import add
```

### 10. What makes a good reusable function?

A good reusable function generally has:

* A clear purpose.
* Appropriate parameters.
* A useful return value when needed.
* Minimal unnecessary dependencies.
* A manageable amount of logic.
* A descriptive name.


[◀Back](.././)
---
