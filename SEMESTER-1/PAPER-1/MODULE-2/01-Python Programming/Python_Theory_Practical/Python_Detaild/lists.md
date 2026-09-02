[◀Back](.././)
---

# Lists in Python

## 1. What is a List?

A **list** is a collection used to store multiple values in a single variable.

Lists are one of the most commonly used collection data types in Python.

### Example

```python
fruits = ["apple", "banana", "orange"]
```

Instead of creating separate variables:

```python
fruit1 = "apple"
fruit2 = "banana"
fruit3 = "orange"
```

we can store the values together:

```python
fruits = ["apple", "banana", "orange"]
```

A list is created using **square brackets `[]`**.

---

# 2. Characteristics of Lists

Python lists have several important characteristics.

### Ordered

List items maintain their position.

```python
fruits = ["apple", "banana", "orange"]
```

The positions are:

```text
apple  → index 0
banana → index 1
orange → index 2
```

### Mutable

List items can be changed after the list is created.

```python
fruits[1] = "mango"
```

### Allows Duplicates

A list can contain the same value multiple times.

```python
numbers = [10, 20, 10, 30, 10]
```

### Allows Different Data Types

A list can contain values of different types.

```python
data = ["Riyas", 20, 5.5, True]
```

---

# 3. Creating a List

A list is created using square brackets.

```python
numbers = [10, 20, 30, 40]
```

An empty list can be created using:

```python
numbers = []
```

You can also use the `list()` constructor:

```python
numbers = list()
```

Both create an empty list.

---

# 4. List with Different Data Types

Python lists can contain different types of values.

```python
data = [
    "Riyas",
    25,
    75.5,
    True
]
```

A list can even contain another list.

```python
data = [
    "Python",
    [10, 20, 30]
]
```

This is called a **nested list**.

---

# 5. Accessing List Items

List items are accessed using their index.

Python uses **zero-based indexing**.

```python
fruits = ["apple", "banana", "orange"]

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

The first item has index `0`.

---

# 6. Negative Indexing

Python also supports negative indexing.

```python
fruits = ["apple", "banana", "orange"]

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

Negative indexes start from the end.

```text
-3       -2        -1
 ↓        ↓         ↓
apple   banana    orange
 0         1         2
```

---

# 7. Changing List Items

Lists are mutable, so individual items can be changed.

```python
fruits = ["apple", "banana", "orange"]

fruits[1] = "mango"

print(fruits)
```

Output:

```text
['apple', 'mango', 'orange']
```

Only the item at index `1` was changed.

---

# 8. Adding Items with `append()`

The `append()` method adds one item to the end of a list.

```python
fruits = ["apple", "banana"]

fruits.append("orange")

print(fruits)
```

Output:

```text
['apple', 'banana', 'orange']
```

---

# 9. Adding Items with `insert()`

The `insert()` method adds an item at a specific position.

### Syntax

```python
list.insert(index, item)
```

Example:

```python
fruits = ["apple", "orange"]

fruits.insert(1, "banana")

print(fruits)
```

Output:

```text
['apple', 'banana', 'orange']
```

---

# 10. Adding Multiple Items with `extend()`

The `extend()` method adds multiple items from another iterable.

```python
numbers = [1, 2, 3]

numbers.extend([4, 5, 6])

print(numbers)
```

Output:

```text
[1, 2, 3, 4, 5, 6]
```

---

# 11. `append()` vs `extend()`

These methods behave differently.

### `append()`

Adds the object as a single item.

```python
numbers = [1, 2, 3]

numbers.append([4, 5])

print(numbers)
```

Output:

```text
[1, 2, 3, [4, 5]]
```

### `extend()`

Adds the elements individually.

```python
numbers = [1, 2, 3]

numbers.extend([4, 5])

print(numbers)
```

Output:

```text
[1, 2, 3, 4, 5]
```

---

# 12. Removing Items with `remove()`

The `remove()` method removes the first occurrence of a specified value.

```python
fruits = ["apple", "banana", "orange"]

fruits.remove("banana")

print(fruits)
```

Output:

```text
['apple', 'orange']
```

If the specified value does not exist, Python raises a `ValueError`.

---

# 13. Removing Items with `pop()`

The `pop()` method removes an item using its index and returns the removed item.

```python
fruits = ["apple", "banana", "orange"]

removed = fruits.pop(1)

print(removed)
print(fruits)
```

Output:

```text
banana
['apple', 'orange']
```

Without an index, `pop()` removes the last item.

```python
fruits = ["apple", "banana", "orange"]

fruits.pop()

print(fruits)
```

Output:

```text
['apple', 'banana']
```

---

# 14. Removing Items with `del`

The `del` statement can remove an item using its index.

```python
fruits = ["apple", "banana", "orange"]

del fruits[1]

print(fruits)
```

Output:

```text
['apple', 'orange']
```

It can also remove a range of items.

```python
numbers = [1, 2, 3, 4, 5]

del numbers[1:4]

print(numbers)
```

Output:

```text
[1, 5]
```

---

# 15. Clearing a List

The `clear()` method removes all items from a list.

```python
numbers = [1, 2, 3, 4]

numbers.clear()

print(numbers)
```

Output:

```text
[]
```

The list still exists, but it contains no items.

---

# 16. Finding the Length of a List

The `len()` function returns the number of items in a list.

```python
fruits = ["apple", "banana", "orange"]

print(len(fruits))
```

Output:

```text
3
```

---

# 17. Checking Whether an Item Exists

The `in` operator checks whether an item exists in a list.

```python
fruits = ["apple", "banana", "orange"]

if "banana" in fruits:
    print("Banana is available.")
```

Using `not in`:

```python
if "mango" not in fruits:
    print("Mango is not available.")
```

---

# 18. List Slicing

**Slicing** is used to obtain a portion of a list.

### Syntax

```python
list[start:stop]
```

Example:

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[1:4])
```

Output:

```text
[20, 30, 40]
```

The `stop` index is not included.

---

# 19. Slicing with a Step

A third value can be used to specify the step.

```python
numbers = [0, 1, 2, 3, 4, 5, 6]

print(numbers[0:7:2])
```

Output:

```text
[0, 2, 4, 6]
```

Syntax:

```python
list[start:stop:step]
```

---

# 20. Omitting Slice Values

You can omit the start or stop value.

### From the beginning

```python
numbers = [1, 2, 3, 4, 5]

print(numbers[:3])
```

Output:

```text
[1, 2, 3]
```

### To the end

```python
print(numbers[2:])
```

Output:

```text
[3, 4, 5]
```

### Entire list

```python
print(numbers[:])
```

Output:

```text
[1, 2, 3, 4, 5]
```

---

# 21. Reversing a List with Slicing

A list can be reversed using a negative step.

```python
numbers = [1, 2, 3, 4, 5]

print(numbers[::-1])
```

Output:

```text
[5, 4, 3, 2, 1]
```

This creates a reversed version of the list.

---

# 22. Iterating Through a List

A `for` loop can be used to process each item.

```python
fruits = ["apple", "banana", "orange"]

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

# 23. Iterating with Indexes

The `range()` and `len()` functions can be used to access indexes.

```python
fruits = ["apple", "banana", "orange"]

for i in range(len(fruits)):
    print(i, fruits[i])
```

Output:

```text
0 apple
1 banana
2 orange
```

When you need both an index and its value, `enumerate()` is usually clearer:

```python
for index, fruit in enumerate(fruits):
    print(index, fruit)
```

---

# 24. Sorting a List

The `sort()` method sorts a list in place.

```python
numbers = [40, 10, 30, 20]

numbers.sort()

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

For descending order:

```python
numbers.sort(reverse=True)

print(numbers)
```

Output:

```text
[40, 30, 20, 10]
```

---

# 25. `sorted()` Function

The `sorted()` function returns a new sorted list without modifying the original list.

```python
numbers = [40, 10, 30, 20]

sorted_numbers = sorted(numbers)

print(sorted_numbers)
print(numbers)
```

Output:

```text
[10, 20, 30, 40]
[40, 10, 30, 20]
```

### Difference

| `sort()`                   | `sorted()`                        |
| -------------------------- | --------------------------------- |
| List method                | Built-in function                 |
| Modifies the original list | Returns a new sorted list         |
| Used with lists            | Can work with different iterables |

---

# 26. Reversing a List with `reverse()`

The `reverse()` method reverses the list in place.

```python
numbers = [1, 2, 3, 4]

numbers.reverse()

print(numbers)
```

Output:

```text
[4, 3, 2, 1]
```

---

# 27. Finding an Item's Index

The `index()` method returns the index of the first matching item.

```python
fruits = ["apple", "banana", "orange"]

position = fruits.index("banana")

print(position)
```

Output:

```text
1
```

If the item does not exist, Python raises a `ValueError`.

---

# 28. Counting Items

The `count()` method returns how many times a value occurs.

```python
numbers = [10, 20, 10, 30, 10]

print(numbers.count(10))
```

Output:

```text
3
```

---

# 29. Copying a List

Assigning one list to another does not create an independent list.

```python
numbers = [1, 2, 3]

new_numbers = numbers
```

Both variables refer to the same list.

Changing one affects the other:

```python
new_numbers.append(4)

print(numbers)
```

Output:

```text
[1, 2, 3, 4]
```

To create a shallow copy, use:

```python
new_numbers = numbers.copy()
```

or:

```python
new_numbers = numbers[:]
```

Now modifying the copied list does not modify the original list's top-level items.

---

# 30. Nested Lists

A list can contain other lists.

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
```

This can represent a table or matrix.

To access an item:

```python
print(matrix[0][1])
```

Output:

```text
2
```

The first index selects the inner list, and the second index selects the item inside it.

---

# 31. Iterating Through a Nested List

Nested loops can be used to process nested lists.

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

for row in matrix:
    for value in row:
        print(value)
```

Output:

```text
1
2
3
4
5
6
7
8
9
```

---

# 32. List Concatenation

Two lists can be combined using `+`.

```python
first = [1, 2, 3]
second = [4, 5, 6]

result = first + second

print(result)
```

Output:

```text
[1, 2, 3, 4, 5, 6]
```

The original lists are not modified.

---

# 33. Repeating a List

The `*` operator can repeat the contents of a list.

```python
numbers = [1, 2]

result = numbers * 3

print(result)
```

Output:

```text
[1, 2, 1, 2, 1, 2]
```

---

# 34. List Comprehension

A **list comprehension** provides a concise way to create a list.

### Traditional approach

```python
numbers = []

for number in range(1, 6):
    numbers.append(number * 2)

print(numbers)
```

### List comprehension

```python
numbers = [number * 2 for number in range(1, 6)]

print(numbers)
```

Output:

```text
[2, 4, 6, 8, 10]
```

Basic syntax:

```python
[expression for item in iterable]
```

---

# 35. List Comprehension with a Condition

A condition can be included in a list comprehension.

```python
numbers = [1, 2, 3, 4, 5, 6]

even_numbers = [
    number
    for number in numbers
    if number % 2 == 0
]

print(even_numbers)
```

Output:

```text
[2, 4, 6]
```

Basic structure:

```python
[expression for item in iterable if condition]
```

---

# 36. Practical Example: Student Marks

```python
marks = [85, 72, 90, 65, 78]

total = sum(marks)
average = total / len(marks)

print("Total:", total)
print("Average:", average)
```

Output:

```text
Total: 390
Average: 78.0
```

This demonstrates how lists can store and process multiple related values.

---

# 37. Practical Example: Find the Largest Number

```python
numbers = [12, 45, 7, 89, 34]

largest = numbers[0]

for number in numbers[1:]:
    if number > largest:
        largest = number

print("Largest:", largest)
```

Output:

```text
Largest: 89
```

Python also provides:

```python
print(max(numbers))
```

which produces:

```text
89
```

---

# 38. Practical Example: Remove Duplicates

A list may contain duplicate values:

```python
numbers = [1, 2, 2, 3, 3, 4]
```

One way to remove duplicates is to use a set:

```python
unique_numbers = list(set(numbers))

print(unique_numbers)
```

However, a set does not preserve the original ordering in the general case.

If preserving order is important, another approach is:

```python
numbers = [1, 2, 2, 3, 3, 4]

unique_numbers = []

for number in numbers:
    if number not in unique_numbers:
        unique_numbers.append(number)

print(unique_numbers)
```

Output:

```text
[1, 2, 3, 4]
```

---

# 39. Common Mistakes

## Mistake 1: Accessing an Invalid Index

```python
numbers = [10, 20, 30]

print(numbers[3])
```

This raises:

```text
IndexError
```

Valid indexes are:

```text
0, 1, 2
```

---

## Mistake 2: Confusing `append()` and `extend()`

```python
numbers = [1, 2]

numbers.append([3, 4])

print(numbers)
```

Result:

```text
[1, 2, [3, 4]]
```

Whereas:

```python
numbers = [1, 2]

numbers.extend([3, 4])

print(numbers)
```

Result:

```text
[1, 2, 3, 4]
```

---

## Mistake 3: Modifying a List While Iterating

Changing the structure of a list while iterating over it can produce unexpected results.

Instead, consider creating a new list or iterating over a copy when appropriate.

---

## Mistake 4: Accidentally Sharing a List

```python
a = [1, 2, 3]
b = a

b.append(4)

print(a)
```

Output:

```text
[1, 2, 3, 4]
```

`b = a` does not create a separate list.

Use:

```python
b = a.copy()
```

when an independent shallow copy is required.

---

# 40. Important List Methods

| Method      | Purpose                            |
| ----------- | ---------------------------------- |
| `append()`  | Add one item to the end            |
| `insert()`  | Add an item at a specific position |
| `extend()`  | Add multiple items                 |
| `remove()`  | Remove the first matching value    |
| `pop()`     | Remove and return an item          |
| `clear()`   | Remove all items                   |
| `index()`   | Find the index of a value          |
| `count()`   | Count occurrences                  |
| `sort()`    | Sort the list in place             |
| `reverse()` | Reverse the list in place          |
| `copy()`    | Create a shallow copy              |

---

# 41. Useful Built-in Functions

| Function   | Purpose                            |
| ---------- | ---------------------------------- |
| `len()`    | Number of items                    |
| `max()`    | Largest item                       |
| `min()`    | Smallest item                      |
| `sum()`    | Sum of numeric items               |
| `sorted()` | Return a sorted iterable as a list |
| `list()`   | Create a list                      |

Example:

```python
numbers = [10, 20, 30, 40]

print(len(numbers))
print(max(numbers))
print(min(numbers))
print(sum(numbers))
```

Output:

```text
4
40
10
100
```

---

# 42. Key Points to Remember

* A list stores multiple values in a single variable.
* Lists are created using square brackets `[]`.
* Lists are **ordered and mutable**.
* List indexes start from `0`.
* Negative indexes can access items from the end.
* Lists can contain duplicate values.
* Lists can contain different data types.
* Items can be added, changed, and removed.
* Lists support slicing.
* Lists can be iterated using loops.
* Lists can contain other lists.
* List comprehensions provide a concise way to create lists.
* `append()` adds one item, while `extend()` adds multiple items.
* `sort()` modifies the list, while `sorted()` returns a new sorted list.
* `copy()` can be used to create a shallow copy of a list.

---

# 43. Interview Questions

### 1. What is a list in Python?

A list is an ordered, mutable collection used to store multiple values in a single variable.

### 2. How do you create a list?

Using square brackets:

```python
numbers = [1, 2, 3]
```

### 3. Are lists mutable?

Yes. List elements can be changed after the list is created.

### 4. Can a list contain duplicate values?

Yes.

```python
numbers = [1, 2, 2, 3]
```

### 5. Can a list contain different data types?

Yes.

```python
data = [10, "Python", 5.5, True]
```

### 6. What is the index of the first item in a list?

The first item has index `0`.

### 7. What is the difference between `append()` and `extend()`?

`append()` adds an object as one item, while `extend()` adds the elements from an iterable individually.

### 8. What is the difference between `remove()` and `pop()`?

`remove()` removes the first matching value, while `pop()` removes and returns an item using its index.

### 9. What is list slicing?

List slicing is a way to extract a portion of a list using:

```python
list[start:stop:step]
```

### 10. What is a nested list?

A nested list is a list that contains one or more lists.

```python
matrix = [[1, 2], [3, 4]]
```

### 11. What is a list comprehension?

A list comprehension is a concise syntax for creating a new list from an iterable, optionally using a condition.

```python
squares = [x ** 2 for x in range(5)]
```

### 12. What is the difference between `sort()` and `sorted()`?

`sort()` modifies the original list, while `sorted()` returns a new sorted list.

### 13. What happens when you assign one list to another?

The assignment creates another reference to the same list rather than an independent copy.

```python
a = [1, 2]
b = a
```

### 14. How can you create a copy of a list?

For example:

```python
b = a.copy()
```

or:

```python
b = a[:]
```

[◀Back](.././)
---