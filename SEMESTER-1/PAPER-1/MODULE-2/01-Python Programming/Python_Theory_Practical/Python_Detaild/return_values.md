[◀Back](.././)
---




# Return Values

## What is a Return Value?

A **return value** is the result that a function sends back to the code that called it.

Python uses the `return` statement to send a value back from a function.

```python
def add(a, b):
    return a + b
```

When the function is called:

```python
result = add(10, 20)

print(result)
```

Output:

```text
30
```

Here:

* `add()` is the function.
* `a` and `b` are parameters.
* `10` and `20` are arguments.
* `a + b` calculates the result.
* `return` sends `30` back to the caller.
* `result` stores the returned value.

---

## The `return` Statement

The basic syntax is:

```python
return value
```

Example:

```python
def square(number):
    return number * number

result = square(5)

print(result)
```

Output:

```text
25
```

The function calculates:

```text
5 × 5 = 25
```

and returns `25`.

---

## `return` vs `print()`

One of the most important concepts is the difference between `return` and `print()`.

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

`print()` displays the result, but it does not send the result back to the caller.

Because the function does not explicitly return a value, `result` becomes `None`.

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

Now the result can be stored and used elsewhere.

```python
result = add(10, 20)

new_result = result * 2

print(new_result)
```

Output:

```text
60
```

### Simple Difference

| `print()`                                            | `return`                          |
| ---------------------------------------------------- | --------------------------------- |
| Displays a value                                     | Sends a value back                |
| Mainly used for output                               | Used to produce a function result |
| Cannot normally be assigned as the calculated result | Can be assigned to a variable     |
| Does not stop a function by itself                   | Immediately stops the function    |

---

## Returning a Number

A function can return an integer or floating-point number.

```python
def multiply(a, b):
    return a * b

result = multiply(5, 4)

print(result)
```

Output:

```text
20
```

Another example:

```python
def calculate_percentage(mark, total):
    return (mark / total) * 100

percentage = calculate_percentage(450, 500)

print(percentage)
```

Output:

```text
90.0
```

---

## Returning a String

A function can return a string.

```python
def greet(name):
    return f"Hello, {name}!"

message = greet("Riyas")

print(message)
```

Output:

```text
Hello, Riyas!
```

The returned string can also be used in another expression:

```python
print(greet("Riyas"))
```

Output:

```text
Hello, Riyas!
```

---

## Returning a Boolean

A function can return `True` or `False`.

```python
def is_even(number):
    return number % 2 == 0

result = is_even(10)

print(result)
```

Output:

```text
True
```

This is useful when creating functions that check conditions.

```python
def is_adult(age):
    return age >= 18

if is_adult(20):
    print("Adult")
else:
    print("Minor")
```

Output:

```text
Adult
```

---

## Returning a List

A function can return a list.

```python
def get_numbers():
    return [10, 20, 30, 40]

numbers = get_numbers()

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

The returned list can then be manipulated:

```python
numbers = get_numbers()

numbers.append(50)

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

---

## Returning a Dictionary

A function can return a dictionary.

```python
def get_student():
    return {
        "name": "Riyas",
        "age": 20,
        "course": "Python"
    }

student = get_student()

print(student)
```

Output:

```text
{'name': 'Riyas', 'age': 20, 'course': 'Python'}
```

You can access its values normally:

```python
print(student["name"])
```

Output:

```text
Riyas
```

---

## Returning Multiple Values

Python allows a function to return multiple values.

```python
def calculate(a, b):
    return a + b, a - b

result = calculate(20, 5)

print(result)
```

Output:

```text
(25, 15)
```

Python actually returns these values as a tuple.

```python
def calculate(a, b):
    return a + b, a - b

result = calculate(20, 5)

print(type(result))
```

Output:

```text
<class 'tuple'>
```

---

## Unpacking Multiple Return Values

Multiple returned values can be assigned to separate variables.

```python
def calculate(a, b):
    return a + b, a - b

addition, subtraction = calculate(20, 5)

print(addition)
print(subtraction)
```

Output:

```text
25
15
```

This is called **tuple unpacking**.

---

## Returning `None`

If a function does not return a value explicitly, Python returns `None`.

```python
def greet():
    print("Hello")

result = greet()

print(result)
```

Output:

```text
Hello
None
```

The function performs an action, but it does not return a result.

You can also explicitly write:

```python
def greet():
    print("Hello")
    return None
```

---

## `return` Without a Value

You can use `return` without specifying a value.

```python
def check_age(age):
    if age < 0:
        return

    print("Valid age")

check_age(-5)
```

Here, `return` immediately exits the function.

It returns `None`.

---

## `return` Stops Function Execution

When Python reaches a `return` statement, the function immediately ends.

```python
def test():
    print("First")
    return
    print("Second")

test()
```

Output:

```text
First
```

`"Second"` is never printed because the function has already returned.

---

## Early Return

An **early return** means returning from a function before reaching the end of the function.

Example:

```python
def check_number(number):
    if number < 0:
        return "Negative number"

    return "Positive number"

print(check_number(-5))
```

Output:

```text
Negative number
```

This can make conditional logic easier to read.

---

## Returning From Conditional Statements

A function can have different return values depending on a condition.

```python
def check_result(mark):
    if mark >= 50:
        return "Pass"
    else:
        return "Fail"

print(check_result(75))
```

Output:

```text
Pass
```

Another example:

```python
def get_grade(mark):
    if mark >= 90:
        return "A"
    elif mark >= 75:
        return "B"
    elif mark >= 50:
        return "C"
    else:
        return "Fail"

print(get_grade(82))
```

Output:

```text
B
```

---

## Returning From Loops

A `return` inside a loop immediately stops the entire function, not just the loop.

```python
def find_number(numbers, target):
    for number in numbers:
        if number == target:
            return number

    return None

numbers = [10, 20, 30, 40]

print(find_number(numbers, 30))
```

Output:

```text
30
```

Once `30` is found, the function returns immediately.

---

## `break` vs `return`

These are different.

### `break`

`break` stops the loop.

```python
for number in range(10):
    if number == 5:
        break

    print(number)
```

The loop stops, but execution can continue after the loop.

### `return`

`return` stops the entire function.

```python
def test():
    for number in range(10):
        if number == 5:
            return

        print(number)

    print("Finished")

test()
```

Output:

```text
0
1
2
3
4
```

`"Finished"` is not printed because `return` ended the function.

---

## Using a Return Value in Another Function

The result of one function can be passed to another function.

```python
def add(a, b):
    return a + b

def double(number):
    return number * 2

result = double(add(10, 20))

print(result)
```

Output:

```text
60
```

The process is:

```text
add(10, 20)
     ↓
    30
     ↓
double(30)
     ↓
    60
```

---

## Returning a Function Result Directly

You do not always need to store a return value in a variable.

```python
def add(a, b):
    return a + b

print(add(10, 20))
```

Output:

```text
30
```

The returned value is passed directly to `print()`.

---

## Return Values and Expressions

A return statement can contain an expression.

```python
def calculate(a, b):
    return (a + b) * 2

result = calculate(10, 5)

print(result)
```

Output:

```text
30
```

Python evaluates the expression first:

```text
(10 + 5) * 2
15 * 2
30
```

Then `30` is returned.

---

## Returning a Variable

You can return a variable.

```python
def add(a, b):
    result = a + b
    return result

answer = add(10, 20)

print(answer)
```

Output:

```text
30
```

This is equivalent to:

```python
def add(a, b):
    return a + b
```

---

## Return Value and Scope

A variable created inside a function normally belongs to that function's local scope.

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

The value is returned from the function and stored in `answer`.

You cannot directly access the local variable after the function ends:

```python
def calculate():
    result = 100

calculate()

print(result)
```

This produces a `NameError` because `result` is local to the function.

---

## Returning User Input

A function can process user input and return the result.

```python
def get_name():
    name = input("Enter your name: ")
    return name

user_name = get_name()

print(f"Hello, {user_name}")
```

Example output:

```text
Enter your name: Riyas
Hello, Riyas
```

---

## Practical Example: Calculator

```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    return a / b

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

Each function calculates a result and returns it.

---

## Practical Example: Student Result

```python
def calculate_average(mark1, mark2, mark3):
    total = mark1 + mark2 + mark3
    average = total / 3
    return average

average = calculate_average(80, 75, 90)

print(f"Average: {average}")
```

Output:

```text
Average: 81.66666666666667
```

The function focuses on calculation, while the calling code decides what to do with the result.

---

## Practical Example: Finding the Largest Number

```python
def find_largest(a, b, c):
    if a >= b and a >= c:
        return a
    elif b >= a and b >= c:
        return b
    else:
        return c

largest = find_largest(10, 25, 15)

print(largest)
```

Output:

```text
25
```

---

## Practical Example: Returning a Boolean

Boolean return values are useful for validation.

```python
def is_valid_password(password):
    return len(password) >= 8

password = "python123"

if is_valid_password(password):
    print("Valid password")
else:
    print("Password is too short")
```

Output:

```text
Valid password
```

---

## Important: `return` Does Not Print Automatically

Consider:

```python
def add(a, b):
    return a + b

add(10, 20)
```

Nothing is displayed.

The function returned `30`, but the returned value was not used.

You need to do something with it:

```python
result = add(10, 20)

print(result)
```

or:

```python
print(add(10, 20))
```

---

## Common Mistakes

### 1. Using `print()` Instead of `return`

Incorrect when the result needs to be reused:

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

### 2. Forgetting to Store or Use the Returned Value

```python
def add(a, b):
    return a + b

add(10, 20)
```

The function returns `30`, but the value is ignored.

Better:

```python
result = add(10, 20)

print(result)
```

---

### 3. Code After `return`

```python
def test():
    return 10
    print("Hello")
```

The `print()` statement is unreachable because the function already returned.

---

### 4. Returning Too Early

Be careful with the position of `return`.

```python
def check(numbers):
    for number in numbers:
        return number
```

This returns the first number immediately.

If the intention is to search for a specific value, the `return` should be placed inside the appropriate condition:

```python
def find_number(numbers, target):
    for number in numbers:
        if number == target:
            return number

    return None
```

---

## Return Values vs Arguments

These concepts are related but different.

### Argument

An **argument** is a value passed into a function.

```python
add(10, 20)
```

Here:

```text
10 and 20 → arguments
```

### Return value

The **return value** is the value sent back by the function.

```python
def add(a, b):
    return a + b
```

Here:

```text
30 → return value
```

Flow:

```text
Arguments
   ↓
Function
   ↓
Processing
   ↓
Return value
```

---

## Quick Reference

| Concept         | Meaning                               |
| --------------- | ------------------------------------- |
| `return`        | Sends a value back from a function    |
| `return value`  | Returns a specific value              |
| `return`        | Ends the function and returns `None`  |
| No `return`     | Function returns `None`               |
| Multiple values | Returned as a tuple                   |
| `print()`       | Displays a value                      |
| Early return    | Ends a function before its final line |
| Return in loop  | Ends the entire function              |

---

## Key Points

* `return` sends a result from a function back to the caller.
* A function can return almost any Python value.
* The returned value can be stored in a variable.
* `print()` displays a value; `return` sends a value back.
* A function without an explicit return value returns `None`.
* `return` immediately stops the function.
* A function can return multiple values.
* Multiple return values are packed into a tuple.
* Return values can be passed directly into other functions.
* `return` is essential when a function needs to produce a reusable result.

---

## Interview Questions

### 1. What is a return value?

A return value is the value that a function sends back to the code that called it.

### 2. What is the purpose of `return`?

It sends a value back from a function and immediately terminates the function.

### 3. What happens if a function has no `return` statement?

Python returns `None`.

### 4. What is the difference between `return` and `print()`?

`print()` displays a value, while `return` sends a value back to the caller.

### 5. Can a Python function return multiple values?

Yes. Python can return multiple values, which are packed into a tuple.

```python
def calculate(a, b):
    return a + b, a - b
```

### 6. Can a function return a list or dictionary?

Yes.

```python
def get_data():
    return [1, 2, 3]
```

### 7. Does `return` stop function execution?

Yes. Once `return` executes, the function immediately ends.

### 8. Can a function return `None`?

Yes.

```python
def test():
    return None
```

### 9. Can a returned value be used as an argument to another function?

Yes.

```python
print(len(get_name()))
```

### 10. What happens to code written after `return`?

It will not execute because the function has already ended.

[◀Back](.././)
---
