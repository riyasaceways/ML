## Lists

**Lists** are ordered, mutable collections used to store multiple values in a single variable. A list can contain different data types and allows duplicate values.

### Key Features

* **Ordered** — Items have a defined position and can be accessed using an index.
* **Mutable** — Items can be changed, added, or removed after the list is created.
* **Allows duplicates** — The same value can appear multiple times.
* **Supports different data types** — A single list can contain different types of values.

### Example

```python
numbers = [10, 20, 30, 40]

print(numbers[0])

numbers.append(50)
numbers[1] = 25

print(numbers)
```

Output:

```text
10
[10, 25, 30, 40, 50]
```

[View more details →](./Python_Detaild/lists.md)

---

## Tuples

**Tuples** are ordered, immutable collections used to store multiple values in a single variable. They are similar to lists, but their elements cannot be changed after creation.

### Key Features

* **Ordered** — Items maintain their position and can be accessed using indexes.
* **Immutable** — Items cannot be added, changed, or removed after creation.
* **Allows duplicates** — The same value can appear multiple times.
* **Supports different data types** — A tuple can contain different types of values.
* **Usually written with parentheses `()`**.

### Example

```python
student = ("Riyas", 20, "Python")

print(student[0])
print(student)
```

Output:

```text
Riyas
('Riyas', 20, 'Python')
```

[View more details →](./Python_Detaild/tuples.md)

---

## Sets

**Sets** are unordered, mutable collections used to store multiple values. A set automatically removes duplicate values.

### Key Features

* **Unordered** — Items do not have a fixed index or guaranteed order.
* **Mutable** — Items can be added or removed after the set is created.
* **No duplicates** — Each value can appear only once.
* **Supports different data types** — A set can contain different types of values, as long as the values are hashable.
* **Uses curly braces `{}`** — Sets are commonly created using curly braces.

### Example

```python
numbers = {10, 20, 30, 20, 40}

print(numbers)

numbers.add(50)
numbers.remove(20)

print(numbers)
```

Output:

```text
{10, 20, 30, 40}
{10, 30, 40, 50}
```

Here, the duplicate `20` is automatically removed.

[View more details →](./Python_Detaild/sets.md)

---

## Dictionaries

**Dictionaries** are mutable collections used to store data as **key-value pairs**. Each key is used to access its corresponding value.

### Key Features

* **Key-value pairs** — Data is stored as `key: value`.
* **Ordered** — Dictionaries preserve insertion order.
* **Mutable** — Values can be changed, added, or removed.
* **Keys are unique** — A dictionary cannot have duplicate keys.
* **Keys must be hashable** — For example, strings, numbers, and tuples can be keys.
* **Values can be any data type** — Different values can have different data types.

### Example

```python
student = {
    "name": "Riyas",
    "age": 20,
    "course": "Python"
}

print(student["name"])

student["age"] = 21
student["city"] = "Kochi"

print(student)
```

Output:

```text
Riyas
{'name': 'Riyas', 'age': 21, 'course': 'Python', 'city': 'Kochi'}
```

Here, `"name"`, `"age"`, `"course"`, and `"city"` are **keys**, while `"Riyas"`, `21`, `"Python"`, and `"Kochi"` are their corresponding **values**.

[View more details →](./Python_Detaild/dictionaries.md)

---

## Collection Manipulation

**Collection manipulation** means working with collections by accessing, adding, updating, removing, searching, sorting, and transforming their elements.

Python provides different techniques for manipulating **lists, tuples, sets, and dictionaries**.

### Common Operations

* **Accessing** — Retrieve elements using indexes or keys.
* **Adding** — Add new elements using methods such as `append()`, `add()`, or dictionary assignment.
* **Updating** — Change existing elements or values.
* **Removing** — Delete elements using methods such as `remove()`, `pop()`, or `del`.
* **Searching** — Check whether an element exists using `in` and `not in`.
* **Sorting** — Arrange values using `sort()` or `sorted()`.
* **Slicing** — Extract part of a sequence using `[start:stop:step]`.
* **Iterating** — Process each element using loops.
* **Transforming** — Create new collections using techniques such as comprehensions.

### Example

```python
numbers = [10, 20, 30, 40]

numbers.append(50)
numbers[1] = 25

print(numbers)
print(30 in numbers)
```

Output:

```text
[10, 25, 30, 40, 50]
True
```

[View more details →](./Python_Detaild/collection_manipulation.md)





