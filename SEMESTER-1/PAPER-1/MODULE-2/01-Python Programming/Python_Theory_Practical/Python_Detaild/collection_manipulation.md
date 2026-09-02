[◀Back](.././)
---



# Collection Manipulation in Python

## What is Collection Manipulation?

**Collection manipulation** means performing operations on collections to access, add, modify, remove, search, sort, and transform their elements.

Python provides several built-in collection types:

* **List** — Ordered and mutable collection.
* **Tuple** — Ordered and immutable collection.
* **Set** — Collection of unique elements.
* **Dictionary** — Collection of key-value pairs.

Each collection provides different ways to manipulate its data.

---

# 1. Accessing Collection Elements

Accessing means retrieving data from a collection.

## List

Lists use indexes.

```python
numbers = [10, 20, 30, 40]

print(numbers[0])
print(numbers[2])
```

Output:

```text
10
30
```

---

## Tuple

Tuples also use indexes.

```python
numbers = (10, 20, 30, 40)

print(numbers[1])
```

Output:

```text
20
```

---

## Dictionary

Dictionaries use keys instead of indexes.

```python
student = {
    "name": "Riyas",
    "age": 20
}

print(student["name"])
```

Output:

```text
Riyas
```

---

## Set

Sets do not support indexing.

```python
numbers = {10, 20, 30}

print(20 in numbers)
```

Output:

```text
True
```

Sets are generally accessed through iteration or membership operations rather than positional indexing.

---

# 2. Adding Elements

Different collections use different methods for adding data.

## Adding to a List

### `append()`

Adds one element to the end.

```python
numbers = [10, 20, 30]

numbers.append(40)

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

---

### `insert()`

Adds an element at a specific position.

```python
numbers = [10, 20, 30]

numbers.insert(1, 15)

print(numbers)
```

Output:

```text
[10, 15, 20, 30]
```

---

### `extend()`

Adds multiple elements.

```python
numbers = [10, 20]

numbers.extend([30, 40, 50])

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

---

## Adding to a Set

### `add()`

Adds one unique element.

```python
numbers = {10, 20, 30}

numbers.add(40)

print(numbers)
```

---

### `update()`

Adds multiple elements.

```python
numbers = {10, 20}

numbers.update([30, 40, 50])

print(numbers)
```

---

## Adding to a Dictionary

A new key-value pair can be added using assignment.

```python
student = {
    "name": "Riyas"
}

student["age"] = 20

print(student)
```

Output:

```text
{'name': 'Riyas', 'age': 20}
```

---

## Adding to a Tuple

Tuples are immutable, so elements cannot be directly added.

```python
numbers = (10, 20, 30)
```

This is not possible:

```python
numbers.append(40)
```

If you need another tuple, create a new one:

```python
numbers = numbers + (40,)

print(numbers)
```

Output:

```text
(10, 20, 30, 40)
```

---

# 3. Updating Elements

## Updating a List

Lists are mutable.

```python
numbers = [10, 20, 30]

numbers[1] = 25

print(numbers)
```

Output:

```text
[10, 25, 30]
```

---

## Updating a Dictionary

Dictionary values can be changed using their keys.

```python
student = {
    "name": "Riyas",
    "age": 20
}

student["age"] = 21

print(student)
```

Output:

```text
{'name': 'Riyas', 'age': 21}
```

---

## Updating a Set

Sets do not support changing an element by index.

Instead, remove the old value and add the new value.

```python
numbers = {10, 20, 30}

numbers.remove(20)
numbers.add(25)

print(numbers)
```

Result:

```text
{10, 25, 30}
```

---

## Updating a Tuple

Tuples cannot be modified directly because they are immutable.

```python
numbers = (10, 20, 30)
```

This is invalid:

```python
numbers[1] = 25
```

If a changed tuple is required, create a new tuple.

---

# 4. Removing Elements

## List `remove()`

Removes the first matching value.

```python
numbers = [10, 20, 30, 20]

numbers.remove(20)

print(numbers)
```

Output:

```text
[10, 30, 20]
```

Only the first matching `20` is removed.

---

## List `pop()`

Removes and returns an element by index.

```python
numbers = [10, 20, 30]

value = numbers.pop()

print(value)
print(numbers)
```

Output:

```text
30
[10, 20]
```

You can also specify an index:

```python
value = numbers.pop(0)
```

---

## List `del`

`del` can remove an element by index.

```python
numbers = [10, 20, 30]

del numbers[1]

print(numbers)
```

Output:

```text
[10, 30]
```

---

## List `clear()`

Removes all elements.

```python
numbers = [10, 20, 30]

numbers.clear()

print(numbers)
```

Output:

```text
[]
```

---

## Set `remove()`

```python
numbers = {10, 20, 30}

numbers.remove(20)

print(numbers)
```

---

## Set `discard()`

`discard()` removes an element without raising an error if the element is missing.

```python
numbers = {10, 20, 30}

numbers.discard(100)

print(numbers)
```

No error occurs.

---

## Dictionary `pop()`

```python
student = {
    "name": "Riyas",
    "age": 20
}

student.pop("age")

print(student)
```

Output:

```text
{'name': 'Riyas'}
```

---

## Dictionary `del`

```python
student = {
    "name": "Riyas",
    "age": 20
}

del student["age"]
```

---

# 5. Membership Testing

The `in` operator checks whether an element exists.

## List

```python
numbers = [10, 20, 30]

print(20 in numbers)
```

Output:

```text
True
```

---

## Tuple

```python
numbers = (10, 20, 30)

print(40 in numbers)
```

Output:

```text
False
```

---

## Set

```python
numbers = {10, 20, 30}

print(20 in numbers)
```

Output:

```text
True
```

---

## Dictionary

For dictionaries, `in` checks keys.

```python
student = {
    "name": "Riyas",
    "age": 20
}

print("name" in student)
```

Output:

```text
True
```

To check values:

```python
print("Riyas" in student.values())
```

---

# 6. Slicing

**Slicing** extracts a portion of a sequence.

The general syntax is:

```python
collection[start:stop:step]
```

The `stop` position is excluded.

---

## List Slicing

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[1:4])
```

Output:

```text
[20, 30, 40]
```

---

## Tuple Slicing

```python
numbers = (10, 20, 30, 40, 50)

print(numbers[1:4])
```

Output:

```text
(20, 30, 40)
```

---

## Negative Indexing

Negative indexes count from the end.

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[-1])
print(numbers[-2])
```

Output:

```text
50
40
```

---

## Reverse Slicing

A negative step can be used to reverse a sequence.

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[::-1])
```

Output:

```text
[50, 40, 30, 20, 10]
```

Sets and dictionaries do not support sequence slicing.

---

# 7. Iterating Through Collections

A `for` loop can process each element.

## List

```python
numbers = [10, 20, 30]

for number in numbers:
    print(number)
```

---

## Tuple

```python
numbers = (10, 20, 30)

for number in numbers:
    print(number)
```

---

## Set

```python
numbers = {10, 20, 30}

for number in numbers:
    print(number)
```

The order should not be relied upon.

---

## Dictionary

```python
student = {
    "name": "Riyas",
    "age": 20
}

for key, value in student.items():
    print(key, value)
```

---

# 8. Finding the Length

The `len()` function returns the number of elements.

```python
numbers = [10, 20, 30, 40]

print(len(numbers))
```

Output:

```text
4
```

It can also be used with tuples, sets, and dictionaries.

```python
len((10, 20, 30))
len({10, 20, 30})
len({"a": 1, "b": 2})
```

For a dictionary, `len()` returns the number of key-value pairs.

---

# 9. Sorting Collections

Python provides `sorted()` to create a new sorted list.

```python
numbers = [40, 10, 30, 20]

result = sorted(numbers)

print(result)
```

Output:

```text
[10, 20, 30, 40]
```

The original list is not changed.

---

## List `sort()`

Lists also provide the `sort()` method.

```python
numbers = [40, 10, 30, 20]

numbers.sort()

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

`sort()` modifies the original list.

---

## Descending Order

```python
numbers = [10, 40, 20, 30]

numbers.sort(reverse=True)

print(numbers)
```

Output:

```text
[40, 30, 20, 10]
```

---

# `sort()` vs `sorted()`

| `sort()`                   | `sorted()`                   |
| -------------------------- | ---------------------------- |
| List method                | Built-in function            |
| Modifies the original list | Creates a new sorted list    |
| Works directly on lists    | Can work with many iterables |
| Returns `None`             | Returns a sorted list        |

Example:

```python
numbers = [30, 10, 20]

result = numbers.sort()

print(result)
```

Output:

```text
None
```

---

# 10. Combining Collections

## List Concatenation

Lists can be combined using `+`.

```python
a = [1, 2]
b = [3, 4]

result = a + b

print(result)
```

Output:

```text
[1, 2, 3, 4]
```

---

## Tuple Concatenation

```python
a = (1, 2)
b = (3, 4)

result = a + b

print(result)
```

Output:

```text
(1, 2, 3, 4)
```

---

## Set Union

Sets use union to combine unique elements.

```python
a = {1, 2, 3}
b = {3, 4, 5}

result = a | b

print(result)
```

Result:

```text
{1, 2, 3, 4, 5}
```

---

# 11. Repeating Collections

Lists and tuples can be repeated using `*`.

```python
numbers = [1, 2]

print(numbers * 3)
```

Output:

```text
[1, 2, 1, 2, 1, 2]
```

For tuples:

```python
numbers = (1, 2)

print(numbers * 2)
```

Output:

```text
(1, 2, 1, 2)
```

---

# 12. Converting Between Collections

Python provides built-in functions to convert collections.

## List to Tuple

```python
numbers = [10, 20, 30]

result = tuple(numbers)

print(result)
```

Output:

```text
(10, 20, 30)
```

---

## Tuple to List

```python
numbers = (10, 20, 30)

result = list(numbers)

print(result)
```

Output:

```text
[10, 20, 30]
```

---

## List to Set

```python
numbers = [10, 20, 20, 30]

result = set(numbers)

print(result)
```

Output:

```text
{10, 20, 30}
```

This is useful for removing duplicates.

---

## Set to List

```python
numbers = {10, 20, 30}

result = list(numbers)

print(result)
```

Remember that set order should not be relied upon.

---

# 13. Collection Functions

Python provides several built-in functions that are useful when manipulating collections.

## `len()`

Returns the number of elements.

```python
numbers = [10, 20, 30]

print(len(numbers))
```

---

## `min()`

Returns the smallest value.

```python
numbers = [10, 20, 5, 30]

print(min(numbers))
```

Output:

```text
5
```

---

## `max()`

Returns the largest value.

```python
numbers = [10, 20, 5, 30]

print(max(numbers))
```

Output:

```text
30
```

---

## `sum()`

Returns the total of numeric values.

```python
numbers = [10, 20, 30]

print(sum(numbers))
```

Output:

```text
60
```

---

## `sorted()`

Returns a sorted list.

```python
numbers = [30, 10, 20]

print(sorted(numbers))
```

Output:

```text
[10, 20, 30]
```

---

# 14. `enumerate()`

`enumerate()` provides both the index and the value while iterating.

```python
fruits = ["apple", "banana", "orange"]

for index, fruit in enumerate(fruits):
    print(index, fruit)
```

Output:

```text
0 apple
1 banana
2 orange
```

You can specify a starting index:

```python
for index, fruit in enumerate(fruits, start=1):
    print(index, fruit)
```

Output:

```text
1 apple
2 banana
3 orange
```

---

# 15. `zip()`

`zip()` combines elements from multiple iterables.

```python
names = ["Ali", "John", "Sara"]
marks = [80, 90, 85]

students = zip(names, marks)

print(list(students))
```

Output:

```text
[('Ali', 80), ('John', 90), ('Sara', 85)]
```

It is useful when related data is stored in separate collections.

---

# 16. Filtering Collections

You can use conditions to select specific values.

Example:

```python
numbers = [1, 2, 3, 4, 5, 6]

even_numbers = []

for number in numbers:
    if number % 2 == 0:
        even_numbers.append(number)

print(even_numbers)
```

Output:

```text
[2, 4, 6]
```

This can also be written using a list comprehension.

---

# 17. List Comprehension

A **list comprehension** provides a concise way to create a list.

```python
numbers = [1, 2, 3, 4, 5]

squares = [number ** 2 for number in numbers]

print(squares)
```

Output:

```text
[1, 4, 9, 16, 25]
```

---

## List Comprehension with a Condition

```python
numbers = range(1, 11)

even_numbers = [
    number
    for number in numbers
    if number % 2 == 0
]

print(even_numbers)
```

Output:

```text
[2, 4, 6, 8, 10]
```

---

# 18. Set Comprehension

Set comprehensions create sets.

```python
numbers = [1, 2, 2, 3, 3, 4]

squares = {number ** 2 for number in numbers}

print(squares)
```

Output:

```text
{1, 4, 9, 16}
```

Duplicate results are automatically removed.

---

# 19. Dictionary Comprehension

Dictionary comprehensions create dictionaries.

```python
numbers = [1, 2, 3, 4]

squares = {
    number: number ** 2
    for number in numbers
}

print(squares)
```

Output:

```text
{1: 1, 2: 4, 3: 9, 4: 16}
```

---

# 20. Searching Collections

## Using `in`

```python
numbers = [10, 20, 30, 40]

if 30 in numbers:
    print("Found")
```

Output:

```text
Found
```

---

## Finding an Index in a List

The `index()` method returns the position of the first matching element.

```python
fruits = ["apple", "banana", "orange"]

print(fruits.index("banana"))
```

Output:

```text
1
```

---

## Counting Elements

The `count()` method counts occurrences.

```python
numbers = [10, 20, 20, 30, 20]

print(numbers.count(20))
```

Output:

```text
3
```

Tuples also support `count()`.

---

# 21. Reversing a List

The `reverse()` method changes the list itself.

```python
numbers = [10, 20, 30, 40]

numbers.reverse()

print(numbers)
```

Output:

```text
[40, 30, 20, 10]
```

You can also use slicing:

```python
numbers = [10, 20, 30, 40]

reversed_numbers = numbers[::-1]

print(reversed_numbers)
```

The slicing approach creates a new list.

---

# 22. Nested Collections

Collections can contain other collections.

Example:

```python
students = [
    ["Riyas", 20],
    ["John", 21],
    ["Sara", 19]
]
```

Accessing nested values:

```python
print(students[0][0])
```

Output:

```text
Riyas
```

Dictionaries can also contain nested collections:

```python
student = {
    "name": "Riyas",
    "subjects": ["Python", "SQL", "HTML"]
}
```

---

# 23. Practical Example

Suppose we have a list of marks:

```python
marks = [78, 92, 65, 88, 92, 75]
```

### Find the highest mark

```python
print(max(marks))
```

### Find the lowest mark

```python
print(min(marks))
```

### Find the total

```python
print(sum(marks))
```

### Remove duplicates

```python
unique_marks = set(marks)

print(unique_marks)
```

### Sort the marks

```python
sorted_marks = sorted(marks)

print(sorted_marks)
```

### Find whether a particular mark exists

```python
print(92 in marks)
```

These are all examples of collection manipulation.

---

# Collection Manipulation Summary

| Operation  | List                               | Tuple           | Set                              | Dictionary             |
| ---------- | ---------------------------------- | --------------- | -------------------------------- | ---------------------- |
| Access     | Index                              | Index           | Membership/iteration             | Key                    |
| Add        | `append()`, `insert()`, `extend()` | Not directly    | `add()`, `update()`              | Assignment, `update()` |
| Update     | Yes                                | No              | Remove + add                     | Yes                    |
| Remove     | `remove()`, `pop()`, `del`         | No              | `remove()`, `discard()`, `pop()` | `pop()`, `del`         |
| Search     | `in`, `index()`                    | `in`, `index()` | `in`                             | `in`                   |
| Sort       | `sort()`, `sorted()`               | `sorted()`      | `sorted()`                       | `sorted()`             |
| Slice      | Yes                                | Yes             | No                               | No                     |
| Iterate    | Yes                                | Yes             | Yes                              | Yes                    |
| Duplicates | Allowed                            | Allowed         | Not allowed                      | Keys: Not allowed      |
| Mutable    | Yes                                | No              | Yes                              | Yes                    |

---

# Important Methods at a Glance

### Lists

```python
append()
insert()
extend()
remove()
pop()
clear()
sort()
reverse()
index()
count()
```

### Tuples

```python
count()
index()
```

### Sets

```python
add()
update()
remove()
discard()
pop()
clear()
union()
intersection()
difference()
symmetric_difference()
```

### Dictionaries

```python
get()
keys()
values()
items()
update()
pop()
popitem()
clear()
copy()
```

---

# Common Mistakes

## 1. Using the wrong method for a collection

For example:

```python
numbers = (1, 2, 3)

numbers.append(4)
```

This fails because tuples are immutable and do not have `append()`.

---

## 2. Confusing `append()` and `extend()`

```python
numbers = [1, 2]

numbers.append([3, 4])

print(numbers)
```

Result:

```text
[1, 2, [3, 4]]
```

But:

```python
numbers = [1, 2]

numbers.extend([3, 4])

print(numbers)
```

Result:

```text
[1, 2, 3, 4]
```

`append()` adds one object, while `extend()` adds elements from an iterable.

---

## 3. Forgetting that `sort()` changes the list

```python
numbers.sort()
```

The original list is modified.

If you want a new sorted list:

```python
sorted_numbers = sorted(numbers)
```

---

## 4. Assuming set order

Do not depend on the order of elements in a set.

---

## 5. Trying to modify a tuple

```python
numbers = (10, 20, 30)

numbers[0] = 100
```

This raises a `TypeError` because tuples are immutable.

---

## 6. Confusing dictionary keys and values

```python
student = {
    "name": "Riyas"
}
```

`"name"` is the key.

`"Riyas"` is the value.

```python
"name" in student
```

checks keys.

```python
"Riyas" in student.values()
```

checks values.

---

# Key Points to Remember

1. **Collection manipulation** means working with the data stored inside collections.
2. Different collections provide different manipulation methods.
3. Lists are useful when you need an ordered, mutable collection.
4. Tuples are useful when the collection should remain unchanged.
5. Sets are useful for unique values and set operations.
6. Dictionaries are useful for key-value data.
7. `append()` adds one item to a list.
8. `extend()` adds multiple elements from an iterable.
9. `remove()` removes a specified value.
10. `pop()` removes and returns an element.
11. `in` is commonly used for membership testing.
12. `sort()` modifies a list, while `sorted()` creates a new sorted list.
13. Slicing works with sequences such as lists and tuples.
14. `enumerate()` provides indexes and values while iterating.
15. `zip()` combines related elements from multiple iterables.
16. Comprehensions provide concise ways to create new collections.
17. Collection conversion can be performed using `list()`, `tuple()`, `set()`, and `dict()` where appropriate.
18. Choosing the correct collection type makes data manipulation easier and more efficient.

---

# Interview Questions

### 1. What is collection manipulation?

Collection manipulation is the process of accessing, adding, updating, removing, searching, sorting, and transforming data stored in collections.

### 2. What is the difference between `append()` and `extend()`?

`append()` adds one object to a list, while `extend()` adds each element from an iterable.

### 3. What is the difference between `sort()` and `sorted()`?

`sort()` modifies the original list, while `sorted()` returns a new sorted list.

### 4. Can tuples be modified?

No. Tuples are immutable.

### 5. Which collection automatically removes duplicates?

A set.

### 6. How do you check whether an item exists in a collection?

Use the `in` operator.

```python
item in collection
```

### 7. How do you remove duplicates from a list?

A common approach is:

```python
unique_values = set(numbers)
```

If a list is required afterward:

```python
unique_values = list(set(numbers))
```

The set conversion does not preserve the original list order.

### 8. What does `enumerate()` do?

It allows you to iterate over a collection while receiving both the index and the value.

### 9. What does `zip()` do?

It combines elements from multiple iterables into tuples.

### 10. What are comprehensions?

Comprehensions are concise syntax for creating collections from iterables, optionally applying conditions.

Examples include:

```python
[x ** 2 for x in numbers]
```

```python
{x ** 2 for x in numbers}
```

```python
{x: x ** 2 for x in numbers}
```


[◀Back](.././)
---
