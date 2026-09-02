[◀Back](.././)
---


# Tuples in Python

## 1. What is a Tuple?

A **tuple** is an ordered collection used to store multiple values in a single variable.

Tuples are similar to lists, but the main difference is that **tuples are immutable**.

A tuple is commonly written using parentheses `()`.

```python
student = ("Riyas", 20, "Python")
```

The tuple contains three values:

```text
Riyas
20
Python
```

---

# 2. Characteristics of Tuples

Tuples have several important characteristics.

### Ordered

Tuple items maintain their position.

```python
fruits = ("apple", "banana", "orange")
```

Indexes:

```text
apple  → 0
banana → 1
orange → 2
```

### Immutable

Once a tuple is created, its elements cannot be changed.

```python
fruits = ("apple", "banana", "orange")

# fruits[1] = "mango"  # TypeError
```

### Allows Duplicates

A tuple can contain duplicate values.

```python
numbers = (10, 20, 10, 30, 10)
```

### Allows Different Data Types

A tuple can contain different types of values.

```python
data = ("Riyas", 20, 5.5, True)
```

---

# 3. Creating a Tuple

A tuple can be created using parentheses.

```python
numbers = (10, 20, 30)
```

An empty tuple:

```python
empty = ()
```

A tuple can also be created using the `tuple()` constructor.

```python
numbers = tuple()
```

---

# 4. Single-Item Tuple

A single-item tuple requires a **trailing comma**.

Correct:

```python
number = (10,)
```

Without the comma:

```python
number = (10)
```

This is simply an integer, not a tuple.

```python
print(type((10,)))
print(type((10)))
```

Output:

```text
<class 'tuple'>
<class 'int'>
```

The comma is what makes `(10,)` a tuple.

---

# 5. Accessing Tuple Items

Tuple items are accessed using indexes.

```python
fruits = ("apple", "banana", "orange")

print(fruits[0])
print(fruits[1])
print(fruits[2])
```

Output:

```text
apple
banana
orange
```

Python uses **zero-based indexing**.

---

# 6. Negative Indexing

Negative indexes access items from the end of the tuple.

```python
fruits = ("apple", "banana", "orange")

print(fruits[-1])
print(fruits[-2])
print(fruits[-3])
```

Output:

```text
orange
banana
apple
```

The index structure is:

```text
-3       -2        -1
 ↓        ↓         ↓
apple   banana    orange
 0         1         2
```

---

# 7. Tuple Immutability

The most important characteristic of a tuple is that it is **immutable**.

This means that tuple elements cannot be changed after the tuple is created.

```python
numbers = (10, 20, 30)

numbers[1] = 25
```

This produces:

```text
TypeError
```

Unlike a list:

```python
numbers = [10, 20, 30]

numbers[1] = 25

print(numbers)
```

Output:

```text
[10, 25, 30]
```

### List vs Tuple

```text
List   → Mutable
Tuple  → Immutable
```

---

# 8. Adding Items to a Tuple

Tuples do not have methods such as `append()` or `insert()` because they cannot be modified.

This is invalid:

```python
numbers = (1, 2, 3)

numbers.append(4)
```

It produces an error because tuples cannot be changed.

If a new tuple is required, you can create another tuple:

```python
numbers = (1, 2, 3)

numbers = numbers + (4,)

print(numbers)
```

Output:

```text
(1, 2, 3, 4)
```

This does not modify the original tuple. A new tuple is created and assigned to the variable.

---

# 9. Removing Items from a Tuple

Individual items cannot be removed from a tuple.

```python
numbers = (1, 2, 3)

# numbers.remove(2)
```

Tuple objects do not provide `remove()` because they are immutable.

You can create a new tuple containing only the required values.

```python
numbers = (1, 2, 3)

numbers = (1, 3)

print(numbers)
```

Output:

```text
(1, 3)
```

---

# 10. Tuple Slicing

Tuples support slicing just like lists.

### Syntax

```python
tuple[start:stop]
```

Example:

```python
numbers = (10, 20, 30, 40, 50)

print(numbers[1:4])
```

Output:

```text
(20, 30, 40)
```

The `stop` index is not included.

---

# 11. Tuple Slicing with a Step

```python
numbers = (0, 1, 2, 3, 4, 5, 6)

print(numbers[0:7:2])
```

Output:

```text
(0, 2, 4, 6)
```

Syntax:

```python
tuple[start:stop:step]
```

---

# 12. Reversing a Tuple with Slicing

A tuple can be reversed using a negative step.

```python
numbers = (1, 2, 3, 4, 5)

print(numbers[::-1])
```

Output:

```text
(5, 4, 3, 2, 1)
```

This creates a new tuple.

---

# 13. Finding the Length of a Tuple

The `len()` function returns the number of items.

```python
fruits = ("apple", "banana", "orange")

print(len(fruits))
```

Output:

```text
3
```

---

# 14. Checking Whether an Item Exists

The `in` operator can check whether an item exists.

```python
fruits = ("apple", "banana", "orange")

if "banana" in fruits:
    print("Banana is available.")
```

Using `not in`:

```python
if "mango" not in fruits:
    print("Mango is not available.")
```

---

# 15. Iterating Through a Tuple

A `for` loop can be used to process each tuple item.

```python
fruits = ("apple", "banana", "orange")

for fruit in fruits:
    print(fruit)
```

Output:

```text
apple
banana
orange
```

---

# 16. Tuple Methods

Because tuples are immutable, they have fewer methods than lists.

The two main tuple methods are:

* `count()`
* `index()`

### `count()`

Returns the number of times a value occurs.

```python
numbers = (10, 20, 10, 30, 10)

print(numbers.count(10))
```

Output:

```text
3
```

### `index()`

Returns the index of the first matching value.

```python
fruits = ("apple", "banana", "orange")

print(fruits.index("banana"))
```

Output:

```text
1
```

---

# 17. Tuple Concatenation

Two tuples can be combined using `+`.

```python
first = (1, 2, 3)
second = (4, 5, 6)

result = first + second

print(result)
```

Output:

```text
(1, 2, 3, 4, 5, 6)
```

A new tuple is created.

---

# 18. Repeating a Tuple

The `*` operator can repeat tuple contents.

```python
numbers = (1, 2)

result = numbers * 3

print(result)
```

Output:

```text
(1, 2, 1, 2, 1, 2)
```

---

# 19. Tuple Unpacking

**Tuple unpacking** allows the values of a tuple to be assigned to multiple variables.

```python
student = ("Riyas", 20, "Python")

name, age, course = student

print(name)
print(age)
print(course)
```

Output:

```text
Riyas
20
Python
```

The number of variables should normally match the number of values.

---

# 20. Extended Unpacking

Python also supports extended unpacking using `*`.

```python
numbers = (1, 2, 3, 4, 5)

first, *middle, last = numbers

print(first)
print(middle)
print(last)
```

Output:

```text
1
[2, 3, 4]
5
```

The variable preceded by `*` receives the remaining values as a list.

---

# 21. Swapping Variables Using Tuples

Tuple unpacking can be used to swap two variables.

```python
a = 10
b = 20

a, b = b, a

print(a)
print(b)
```

Output:

```text
20
10
```

Python performs the assignment using tuple-style unpacking.

---

# 22. Converting a List to a Tuple

The `tuple()` function can convert an iterable into a tuple.

```python
numbers = [1, 2, 3, 4]

numbers = tuple(numbers)

print(numbers)
```

Output:

```text
(1, 2, 3, 4)
```

---

# 23. Converting a Tuple to a List

A tuple can be converted into a list using `list()`.

```python
numbers = (1, 2, 3, 4)

numbers = list(numbers)

print(numbers)
```

Output:

```text
[1, 2, 3, 4]
```

This can be useful when modifications are required.

---

# 24. Nested Tuples

A tuple can contain other tuples.

```python
data = (
    ("Riyas", 20),
    ("John", 25),
    ("Alex", 22)
)
```

Values can be accessed using multiple indexes.

```python
print(data[0][0])
```

Output:

```text
Riyas
```

---

# 25. Tuple Containing a Mutable Object

A tuple itself is immutable, but it can contain a mutable object such as a list.

```python
data = ("Python", [1, 2, 3])

data[1].append(4)

print(data)
```

Output:

```text
('Python', [1, 2, 3, 4])
```

The tuple's reference to the list has not changed. Instead, the list object inside the tuple was modified.

This is an important distinction:

```text
Tuple → Immutable
Objects stored inside it → May themselves be mutable
```

---

# 26. Practical Example: Student Information

A tuple can be used to represent a fixed group of related values.

```python
student = ("Riyas", 20, "Python")

name, age, course = student

print("Name:", name)
print("Age:", age)
print("Course:", course)
```

Output:

```text
Name: Riyas
Age: 20
Course: Python
```

---

# 27. Practical Example: Coordinates

Tuples are commonly useful for representing fixed groups of values such as coordinates.

```python
point = (10, 20)

x, y = point

print("X:", x)
print("Y:", y)
```

Output:

```text
X: 10
Y: 20
```

---

# 28. Practical Example: Returning Multiple Values

A function can return multiple values using a tuple.

```python
def calculate(a, b):
    total = a + b
    difference = a - b

    return total, difference


result = calculate(10, 5)

print(result)
```

Output:

```text
(15, 5)
```

The function returns a tuple containing both results.

The returned values can also be unpacked:

```python
total, difference = calculate(10, 5)

print(total)
print(difference)
```

Output:

```text
15
5
```

---

# 29. List vs Tuple

| Feature              | List | Tuple |
| -------------------- | ---- | ----- |
| Syntax               | `[]` | `()`  |
| Ordered              | Yes  | Yes   |
| Mutable              | Yes  | No    |
| Allows duplicates    | Yes  | Yes   |
| Different data types | Yes  | Yes   |
| Indexing             | Yes  | Yes   |
| Slicing              | Yes  | Yes   |
| `append()`           | Yes  | No    |
| `remove()`           | Yes  | No    |
| `count()`            | Yes  | Yes   |
| `index()`            | Yes  | Yes   |

### Simple distinction

```text
List  → Ordered + Mutable
Tuple → Ordered + Immutable
```

---

# 30. When to Use a Tuple

Use a tuple when the collection represents data that should generally remain unchanged.

Examples include:

```python
coordinates = (10, 20)
```

```python
rgb = (255, 128, 0)
```

```python
student = ("Riyas", 20, "Python")
```

The choice depends on whether the data is intended to be modified.

---

# 31. Common Mistakes

## Mistake 1: Forgetting the Comma in a Single-Item Tuple

Incorrect:

```python
value = (10)
```

This is an integer.

Correct:

```python
value = (10,)
```

---

## Mistake 2: Trying to Modify a Tuple

Incorrect:

```python
numbers = (1, 2, 3)

numbers[0] = 100
```

Tuples are immutable, so this raises a `TypeError`.

---

## Mistake 3: Expecting `append()` to Work

Incorrect:

```python
numbers = (1, 2, 3)

numbers.append(4)
```

Tuples do not have `append()`.

---

## Mistake 4: Wrong Number of Variables During Unpacking

```python
numbers = (1, 2, 3)

a, b = numbers
```

This raises a `ValueError` because there are three values but only two variables.

Correct:

```python
a, b, c = numbers
```

---

# 32. Quick Reference

| Operation        | Example               |
| ---------------- | --------------------- |
| Create           | `numbers = (1, 2, 3)` |
| Access           | `numbers[0]`          |
| Negative index   | `numbers[-1]`         |
| Slice            | `numbers[1:3]`        |
| Length           | `len(numbers)`        |
| Membership       | `2 in numbers`        |
| Count            | `numbers.count(2)`    |
| Find index       | `numbers.index(2)`    |
| Concatenate      | `a + b`               |
| Repeat           | `a * 3`               |
| Convert to tuple | `tuple(iterable)`     |
| Convert to list  | `list(tuple)`         |
| Unpack           | `a, b, c = numbers`   |

---

# 33. Key Points to Remember

* A tuple is an **ordered collection**.
* Tuples are **immutable**.
* Tuples are commonly created using `()`.
* A single-item tuple requires a trailing comma.
* Tuple indexes start from `0`.
* Negative indexing is supported.
* Tuples support slicing.
* Tuples can contain duplicate values.
* Tuples can contain different data types.
* Tuples can contain mutable objects.
* Tuples provide `count()` and `index()` methods.
* Tuple unpacking allows multiple variables to receive tuple values.
* Tuples can be concatenated and repeated.
* A tuple can be converted to a list, and a list can be converted to a tuple.
* Choose a tuple when the collection should generally remain unchanged.

[◀Back](.././)
---