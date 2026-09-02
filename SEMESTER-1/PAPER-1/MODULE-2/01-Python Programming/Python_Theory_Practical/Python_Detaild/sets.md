[◀Back](.././)
---

# Sets in Python

## What is a Set?

A **set** is a built-in Python collection used to store multiple **unique** values.

Unlike lists and tuples, sets:

* do not allow duplicate elements
* do not support indexing
* are unordered
* are mutable
* support mathematical set operations such as union, intersection, and difference

Example:

```python
numbers = {10, 20, 30, 20, 40}

print(numbers)
```

Output:

```text
{10, 20, 30, 40}
```

The duplicate `20` is automatically removed.

---

## Creating a Set

A set can be created using curly braces `{}`.

```python
fruits = {"apple", "banana", "orange"}

print(fruits)
```

Example output:

```text
{'apple', 'banana', 'orange'}
```

The order of elements should not be relied upon.

---

## Creating a Set from a List

The `set()` function can convert another iterable into a set.

```python
numbers = [10, 20, 20, 30, 30, 40]

unique_numbers = set(numbers)

print(unique_numbers)
```

Output:

```text
{10, 20, 30, 40}
```

This is a common way to remove duplicate values from a list.

---

## Empty Set

An important point is that `{}` does **not** create an empty set.

```python
empty = {}

print(type(empty))
```

Output:

```text
<class 'dict'>
```

To create an empty set, use `set()`:

```python
empty_set = set()

print(type(empty_set))
```

Output:

```text
<class 'set'>
```

---

## Single-Element Set

A set containing one element can be written as:

```python
numbers = {10}

print(numbers)
```

Do not confuse it with:

```python
numbers = {10,}
```

Both represent a set containing `10`.

---

## Duplicate Values

Sets automatically eliminate duplicate values.

```python
numbers = {1, 2, 2, 3, 3, 3}

print(numbers)
```

Output:

```text
{1, 2, 3}
```

This makes sets useful when uniqueness is important.

---

## Unordered Collection

Sets are **unordered** collections.

```python
numbers = {10, 20, 30, 40}

print(numbers)
```

The displayed order is not something your program should depend on.

A set does not provide normal positional indexing.

---

## Sets Do Not Support Indexing

This does not work:

```python
numbers = {10, 20, 30}

print(numbers[0])
```

It raises a `TypeError` because sets do not support indexing.

If you need to access elements by position, use a list or tuple.

---

## Adding Elements

### `add()`

The `add()` method adds one element to a set.

```python
numbers = {10, 20, 30}

numbers.add(40)

print(numbers)
```

Output:

```text
{10, 20, 30, 40}
```

If the value already exists, nothing new is added.

```python
numbers.add(20)

print(numbers)
```

The set still contains only one `20`.

---

## Adding Multiple Elements

### `update()`

The `update()` method adds multiple elements from an iterable.

```python
numbers = {10, 20}

numbers.update([30, 40, 50])

print(numbers)
```

Output:

```text
{10, 20, 30, 40, 50}
```

It can also accept other collections:

```python
numbers.update((60, 70))
numbers.update({80, 90})
```

---

## Removing Elements

### `remove()`

The `remove()` method removes a specified element.

```python
numbers = {10, 20, 30}

numbers.remove(20)

print(numbers)
```

Output:

```text
{10, 30}
```

If the element does not exist, `remove()` raises a `KeyError`.

---

## `discard()`

`discard()` also removes an element.

```python
numbers = {10, 20, 30}

numbers.discard(20)

print(numbers)
```

The important difference is what happens when the element does not exist.

```python
numbers.discard(100)
```

No error is raised.

### `remove()` vs `discard()`

| Method      | Element exists | Element does not exist |
| ----------- | -------------- | ---------------------- |
| `remove()`  | Removes it     | Raises `KeyError`      |
| `discard()` | Removes it     | Does nothing           |

---

## `pop()`

The `pop()` method removes and returns an arbitrary element from the set.

```python
numbers = {10, 20, 30}

value = numbers.pop()

print(value)
print(numbers)
```

Because sets are unordered, you should not assume which element will be removed.

---

## `clear()`

The `clear()` method removes all elements from a set.

```python
numbers = {10, 20, 30}

numbers.clear()

print(numbers)
```

Output:

```text
set()
```

---

# Checking Membership

The `in` operator checks whether a value exists in a set.

```python
fruits = {"apple", "banana", "orange"}

print("apple" in fruits)
```

Output:

```text
True
```

You can also use `not in`.

```python
print("mango" not in fruits)
```

Output:

```text
True
```

Sets are particularly useful for membership testing.

---

# Iterating Through a Set

You can use a `for` loop to iterate through a set.

```python
numbers = {10, 20, 30, 40}

for number in numbers:
    print(number)
```

The order of output should not be relied upon.

---

# Set Operations

One of the most important features of sets is their support for mathematical set operations.

Consider:

```python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}
```

---

## Union

**Union** combines all unique elements from both sets.

Using `|`:

```python
result = a | b

print(result)
```

Output:

```text
{1, 2, 3, 4, 5, 6}
```

Using the method:

```python
result = a.union(b)
```

---

## Intersection

**Intersection** returns elements that exist in both sets.

Using `&`:

```python
result = a & b

print(result)
```

Output:

```text
{3, 4}
```

Using the method:

```python
result = a.intersection(b)
```

---

## Difference

**Difference** returns elements that exist in the first set but not in the second.

```python
result = a - b

print(result)
```

Output:

```text
{1, 2}
```

Using the method:

```python
result = a.difference(b)
```

The direction matters.

```python
print(b - a)
```

Output:

```text
{5, 6}
```

---

## Symmetric Difference

Symmetric difference returns elements that exist in either set, but **not in both**.

Using `^`:

```python
result = a ^ b

print(result)
```

Output:

```text
{1, 2, 5, 6}
```

Using the method:

```python
result = a.symmetric_difference(b)
```

---

# Set Operation Summary

For:

```python
a = {1, 2, 3}
b = {3, 4, 5}
```

| Operation            | Syntax   | Result            |
| -------------------- | -------- | ----------------- |
| Union                | `a \| b` | `{1, 2, 3, 4, 5}` |
| Intersection         | `a & b`  | `{3}`             |
| Difference           | `a - b`  | `{1, 2}`          |
| Symmetric Difference | `a ^ b`  | `{1, 2, 4, 5}`    |

---

# Subset

A set is a **subset** of another set when all of its elements are contained in the other set.

```python
a = {1, 2}
b = {1, 2, 3, 4}

print(a.issubset(b))
```

Output:

```text
True
```

You can also use `<=`:

```python
print(a <= b)
```

---

# Superset

A set is a **superset** when it contains all elements of another set.

```python
a = {1, 2, 3, 4}
b = {1, 2}

print(a.issuperset(b))
```

Output:

```text
True
```

You can also use `>=`:

```python
print(a >= b)
```

---

# Disjoint Sets

Two sets are **disjoint** when they have no elements in common.

```python
a = {1, 2, 3}
b = {4, 5, 6}

print(a.isdisjoint(b))
```

Output:

```text
True
```

If they share an element:

```python
a = {1, 2, 3}
b = {3, 4, 5}

print(a.isdisjoint(b))
```

Output:

```text
False
```

---

# Set Comparison

Sets can be compared using operators.

```python
a = {1, 2}
b = {1, 2}
c = {1, 2, 3}

print(a == b)
print(a != c)
```

Output:

```text
True
True
```

---

# `len()` with Sets

The `len()` function returns the number of elements.

```python
numbers = {10, 20, 30, 40}

print(len(numbers))
```

Output:

```text
4
```

Duplicates are not counted because they are not stored as separate elements.

---

# Sets and Different Data Types

A set can contain multiple data types, provided the elements are hashable.

```python
data = {10, "Python", 3.14, True}

print(data)
```

However, mutable objects such as lists cannot be directly stored inside a set.

This is invalid:

```python
data = {[1, 2], [3, 4]}
```

It raises:

```text
TypeError: unhashable type: 'list'
```

---

# Mutable vs Immutable

A normal `set` is mutable.

```python
numbers = {1, 2, 3}

numbers.add(4)
numbers.remove(2)
```

The set itself can be modified.

However, Python also provides an immutable version called `frozenset`.

---

# Frozenset

A **frozenset** is an immutable set.

```python
numbers = frozenset({1, 2, 3})

print(numbers)
```

You cannot modify it:

```python
numbers.add(4)
```

This raises an error because `frozenset` does not provide methods such as `add()`.

Frozensets are useful when a set needs to remain unchanged or when it needs to be used where a hashable object is required.

---

# Copying Sets

The `copy()` method creates a shallow copy of a set.

```python
numbers = {1, 2, 3}

new_numbers = numbers.copy()

print(new_numbers)
```

The two sets are separate set objects.

---

# Nested Collections in Sets

A set cannot directly contain a list because lists are mutable and unhashable.

```python
data = {[1, 2], [3, 4]}
```

This is invalid.

However, tuples containing hashable values can be elements of a set:

```python
data = {(1, 2), (3, 4)}

print(data)
```

---

# Practical Example: Removing Duplicates

Suppose a list contains duplicate values:

```python
numbers = [10, 20, 20, 30, 30, 40, 40]

unique_numbers = set(numbers)

print(unique_numbers)
```

Output:

```text
{10, 20, 30, 40}
```

If you specifically need a list afterward:

```python
unique_numbers = list(set(numbers))

print(unique_numbers)
```

Remember that converting through a set does not preserve the original list order.

---

# Practical Example: Finding Common Students

Suppose two classes have students:

```python
class_a = {"Ali", "John", "Sara", "David"}
class_b = {"Sara", "David", "Mike", "Tom"}

common_students = class_a & class_b

print(common_students)
```

Output:

```text
{'Sara', 'David'}
```

The intersection operation makes it easy to find students present in both classes.

---

# Practical Example: Unique Words

A set can be used to find unique words.

```python
sentence = "python is easy and python is powerful"

words = sentence.split()

unique_words = set(words)

print(unique_words)
```

The resulting set contains each unique word only once.

---

# List vs Tuple vs Set

| Feature    | List               | Tuple            | Set                            |
| ---------- | ------------------ | ---------------- | ------------------------------ |
| Ordered    | Yes                | Yes              | No guaranteed order            |
| Mutable    | Yes                | No               | Yes                            |
| Duplicates | Yes                | Yes              | No                             |
| Indexing   | Yes                | Yes              | No                             |
| Slicing    | Yes                | Yes              | No                             |
| Syntax     | `[]`               | `()`             | `{}`                           |
| Main use   | General collection | Fixed collection | Unique values / set operations |

---

# Common Set Methods

| Method                   | Purpose                                                |
| ------------------------ | ------------------------------------------------------ |
| `add()`                  | Adds one element                                       |
| `update()`               | Adds multiple elements                                 |
| `remove()`               | Removes an element; raises an error if missing         |
| `discard()`              | Removes an element without raising an error if missing |
| `pop()`                  | Removes and returns an arbitrary element               |
| `clear()`                | Removes all elements                                   |
| `copy()`                 | Creates a shallow copy                                 |
| `union()`                | Combines sets                                          |
| `intersection()`         | Finds common elements                                  |
| `difference()`           | Finds elements only in the first set                   |
| `symmetric_difference()` | Finds elements in either set but not both              |
| `issubset()`             | Checks whether a set is a subset                       |
| `issuperset()`           | Checks whether a set is a superset                     |
| `isdisjoint()`           | Checks whether two sets have no common elements        |

---

# Common Mistakes

### 1. Thinking `{}` creates an empty set

```python
data = {}
```

This creates a dictionary.

Correct:

```python
data = set()
```

---

### 2. Trying to use an index

```python
numbers = {10, 20, 30}

print(numbers[0])
```

Sets do not support indexing.

---

### 3. Expecting duplicates

```python
numbers = {1, 1, 2, 2, 3}

print(numbers)
```

Output contains only:

```text
{1, 2, 3}
```

---

### 4. Assuming set order

Do not write code that depends on the order in which a set displays or iterates.

---

### 5. Using a list as a set element

```python
data = {[1, 2], [3, 4]}
```

Lists are unhashable and cannot be set elements.

---

# Quick Reference

```python
# Create
numbers = {1, 2, 3}

# Empty set
empty = set()

# Add
numbers.add(4)

# Add multiple
numbers.update([5, 6])

# Remove
numbers.remove(6)

# Remove safely
numbers.discard(10)

# Check membership
print(3 in numbers)

# Number of elements
print(len(numbers))

# Union
a | b

# Intersection
a & b

# Difference
a - b

# Symmetric difference
a ^ b

# Subset
a.issubset(b)

# Superset
a.issuperset(b)

# Disjoint
a.isdisjoint(b)

# Clear
numbers.clear()
```

---

# Key Points to Remember

1. A **set stores unique values**.
2. Sets are **mutable**.
3. Sets are **unordered collections**.
4. Sets do **not support indexing or slicing**.
5. Duplicate values are automatically removed.
6. Use `set()` to create an empty set.
7. `add()` adds one element.
8. `update()` adds multiple elements.
9. `remove()` raises an error if the element does not exist.
10. `discard()` does not raise an error if the element is missing.
11. Sets support **union, intersection, difference, and symmetric difference**.
12. Set elements must be **hashable**.
13. `frozenset` provides an immutable set.

---

# Interview Questions

### 1. What is a set in Python?

A set is an unordered, mutable collection that stores unique elements.

### 2. Does a set allow duplicate values?

No. Duplicate values are automatically removed.

### 3. Can we access set elements using indexes?

No. Sets do not support indexing.

### 4. How do you create an empty set?

```python
empty_set = set()
```

### 5. What is the difference between `remove()` and `discard()`?

`remove()` raises a `KeyError` if the element does not exist, while `discard()` does nothing.

### 6. What is the difference between a list and a set?

A list is ordered and allows duplicates, while a set is used for unique elements and does not provide positional indexing.

### 7. What is set union?

Union combines the unique elements of two sets.

```python
a | b
```

### 8. What is set intersection?

Intersection returns elements common to both sets.

```python
a & b
```

### 9. What is a `frozenset`?

A `frozenset` is an immutable version of a set.

### 10. Why are sets useful?

Sets are useful when you need unique values, fast membership testing, or mathematical set operations.


[◀Back](.././)
---
