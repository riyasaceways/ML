# Dictionaries in Python

## What is a Dictionary?

A **dictionary** is a built-in Python collection used to store data as **key-value pairs**.

Each key identifies a value.

The general structure is:

```python
dictionary = {
    key: value,
    key: value
}
```

Example:

```python
student = {
    "name": "Riyas",
    "age": 20,
    "course": "Python"
}
```

Here:

* `"name"` → key
* `"Riyas"` → value
* `"age"` → key
* `20` → value
* `"course"` → key
* `"Python"` → value

---

# Creating a Dictionary

Dictionaries are usually created using curly braces `{}`.

```python
student = {
    "name": "Riyas",
    "age": 20,
    "course": "Python"
}

print(student)
```

Output:

```text
{'name': 'Riyas', 'age': 20, 'course': 'Python'}
```

---

# Empty Dictionary

An empty dictionary can be created using `{}`.

```python
student = {}

print(student)
```

Output:

```text
{}
```

You can also use:

```python
student = dict()
```

Both create an empty dictionary.

---

# Dictionary with Different Data Types

Keys and values can contain different data types, subject to the rules for valid dictionary keys.

```python
data = {
    "name": "Riyas",
    "age": 20,
    "marks": 85.5,
    "passed": True
}

print(data)
```

Here the values have different types:

* `"Riyas"` → string
* `20` → integer
* `85.5` → float
* `True` → boolean

---

# Dictionary Keys and Values

A dictionary consists of:

```text
Key → Value
```

Example:

```python
student = {
    "name": "Riyas",
    "age": 20
}
```

The structure can be visualized as:

```text
"name" → "Riyas"
"age"  → 20
```

Keys are used to retrieve the corresponding values.

---

# Accessing Dictionary Values

You can access a value using its key.

```python
student = {
    "name": "Riyas",
    "age": 20
}

print(student["name"])
print(student["age"])
```

Output:

```text
Riyas
20
```

---

# Accessing a Missing Key

If you try to access a key that does not exist using square brackets:

```python
student = {
    "name": "Riyas"
}

print(student["age"])
```

Python raises:

```text
KeyError
```

To avoid this, you can use `get()`.

---

# `get()`

The `get()` method retrieves a value using a key.

```python
student = {
    "name": "Riyas",
    "age": 20
}

print(student.get("name"))
```

Output:

```text
Riyas
```

If the key does not exist:

```python
print(student.get("city"))
```

The result is:

```text
None
```

You can also provide a default value:

```python
print(student.get("city", "Not available"))
```

Output:

```text
Not available
```

### `[]` vs `get()`

| Method                           | Missing key                   |
| -------------------------------- | ----------------------------- |
| `dictionary["key"]`              | Raises `KeyError`             |
| `dictionary.get("key")`          | Returns `None`                |
| `dictionary.get("key", default)` | Returns the specified default |

---

# Adding a New Item

You can add a new key-value pair by assigning a value to a new key.

```python
student = {
    "name": "Riyas",
    "age": 20
}

student["city"] = "Kochi"

print(student)
```

Output:

```text
{'name': 'Riyas', 'age': 20, 'city': 'Kochi'}
```

---

# Updating an Existing Value

If the key already exists, assigning a new value changes the existing value.

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

The key `"age"` was not duplicated. Its value was changed.

---

# Dictionary Keys Must Be Unique

Dictionary keys are unique.

Consider:

```python
student = {
    "name": "Riyas",
    "name": "John"
}

print(student)
```

The later value replaces the earlier value.

Output:

```text
{'name': 'John'}
```

Therefore, duplicate keys should not be used when you need to preserve multiple values.

---

# Dictionary Values Can Be Duplicated

Unlike keys, values can be duplicated.

```python
students = {
    "student1": "Python",
    "student2": "Python",
    "student3": "Python"
}

print(students)
```

This is valid because the keys are unique.

---

# Removing Items

## `pop()`

The `pop()` method removes a specified key and returns its value.

```python
student = {
    "name": "Riyas",
    "age": 20,
    "city": "Kochi"
}

age = student.pop("age")

print(age)
print(student)
```

Output:

```text
20
{'name': 'Riyas', 'city': 'Kochi'}
```

---

## `popitem()`

`popitem()` removes and returns the last inserted key-value pair.

```python
student = {
    "name": "Riyas",
    "age": 20,
    "city": "Kochi"
}

item = student.popitem()

print(item)
print(student)
```

Example output:

```text
('city', 'Kochi')
{'name': 'Riyas', 'age': 20}
```

---

## `del`

The `del` statement can remove a specific dictionary item.

```python
student = {
    "name": "Riyas",
    "age": 20
}

del student["age"]

print(student)
```

Output:

```text
{'name': 'Riyas'}
```

You can also delete the entire dictionary:

```python
del student
```

---

## `clear()`

`clear()` removes all items from the dictionary.

```python
student = {
    "name": "Riyas",
    "age": 20
}

student.clear()

print(student)
```

Output:

```text
{}
```

---

# Checking if a Key Exists

The `in` operator checks whether a key exists.

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

You can also use:

```python
print("city" not in student)
```

Output:

```text
True
```

By default, `in` checks **keys**, not values.

---

# Getting All Keys

The `keys()` method returns the dictionary's keys.

```python
student = {
    "name": "Riyas",
    "age": 20,
    "course": "Python"
}

print(student.keys())
```

Example output:

```text
dict_keys(['name', 'age', 'course'])
```

You can convert them to a list:

```python
keys = list(student.keys())

print(keys)
```

---

# Getting All Values

The `values()` method returns all values.

```python
student = {
    "name": "Riyas",
    "age": 20,
    "course": "Python"
}

print(student.values())
```

Example output:

```text
dict_values(['Riyas', 20, 'Python'])
```

---

# Getting Key-Value Pairs

The `items()` method returns the dictionary's key-value pairs.

```python
student = {
    "name": "Riyas",
    "age": 20
}

print(student.items())
```

Example output:

```text
dict_items([('name', 'Riyas'), ('age', 20)])
```

Each item behaves like a `(key, value)` pair.

---

# Iterating Through a Dictionary

## Iterating Through Keys

```python
student = {
    "name": "Riyas",
    "age": 20,
    "course": "Python"
}

for key in student:
    print(key)
```

Output:

```text
name
age
course
```

---

## Iterating Through Values

```python
for value in student.values():
    print(value)
```

Output:

```text
Riyas
20
Python
```

---

## Iterating Through Keys and Values

Using `items()`:

```python
for key, value in student.items():
    print(key, value)
```

Output:

```text
name Riyas
age 20
course Python
```

This is one of the most common ways to iterate through a dictionary.

---

# Dictionary Length

The `len()` function returns the number of key-value pairs.

```python
student = {
    "name": "Riyas",
    "age": 20,
    "course": "Python"
}

print(len(student))
```

Output:

```text
3
```

---

# Updating a Dictionary

The `update()` method adds new key-value pairs or changes existing ones.

```python
student = {
    "name": "Riyas",
    "age": 20
}

student.update({
    "age": 21,
    "city": "Kochi"
})

print(student)
```

Output:

```text
{'name': 'Riyas', 'age': 21, 'city': 'Kochi'}
```

Here:

* `"age"` was updated.
* `"city"` was added.

---

# Copying a Dictionary

You can create a copy using `copy()`.

```python
student = {
    "name": "Riyas",
    "age": 20
}

student_copy = student.copy()

print(student_copy)
```

Another option is:

```python
student_copy = dict(student)
```

---

# Dictionary References

Be careful when assigning one dictionary to another variable.

```python
student = {
    "name": "Riyas"
}

student_copy = student

student_copy["age"] = 20

print(student)
```

Output:

```text
{'name': 'Riyas', 'age': 20}
```

Both variables refer to the same dictionary object.

Use `copy()` when you need a separate shallow copy.

---

# Nested Dictionaries

A dictionary can contain another dictionary as a value.

```python
students = {
    "student1": {
        "name": "Riyas",
        "age": 20
    },
    "student2": {
        "name": "John",
        "age": 21
    }
}
```

You can access nested values:

```python
print(students["student1"]["name"])
```

Output:

```text
Riyas
```

Nested dictionaries are useful for representing structured data.

---

# Dictionary with Lists

A dictionary value can also be a list.

```python
student = {
    "name": "Riyas",
    "subjects": ["Python", "SQL", "HTML"]
}

print(student["subjects"])
```

Output:

```text
['Python', 'SQL', 'HTML']
```

You can access the list elements:

```python
print(student["subjects"][0])
```

Output:

```text
Python
```

---

# Lists as Dictionary Values

Lists are valid as dictionary values.

```python
data = {
    "numbers": [10, 20, 30],
    "names": ["Ali", "John", "Sara"]
}
```

The restriction applies to **keys**, not values.

---

# Valid Dictionary Keys

Dictionary keys must be **hashable**.

Common valid keys include:

```python
data = {
    "name": "Riyas",
    1: "one",
    3.14: "pi",
    True: "yes",
    (1, 2): "tuple"
}
```

Strings, numbers, booleans, and tuples containing hashable elements can be dictionary keys.

---

# Invalid Dictionary Keys

Mutable objects such as lists cannot be dictionary keys.

This is invalid:

```python
data = {
    [1, 2]: "numbers"
}
```

Python raises:

```text
TypeError: unhashable type: 'list'
```

Similarly, a normal `set` cannot be used as a key.

---

# Dictionary Comprehension

A **dictionary comprehension** provides a concise way to create dictionaries.

Example:

```python
numbers = [1, 2, 3, 4]

squares = {number: number ** 2 for number in numbers}

print(squares)
```

Output:

```text
{1: 1, 2: 4, 3: 9, 4: 16}
```

The general structure is:

```python
{key: value for item in iterable}
```

---

# Dictionary Comprehension with a Condition

You can include a condition.

```python
numbers = range(1, 6)

even_numbers = {
    number: number ** 2
    for number in numbers
    if number % 2 == 0
}

print(even_numbers)
```

Output:

```text
{2: 4, 4: 16}
```

---

# Using `fromkeys()`

The `fromkeys()` method creates a dictionary from a sequence of keys.

```python
keys = ["name", "age", "city"]

student = dict.fromkeys(keys)

print(student)
```

Output:

```text
{'name': None, 'age': None, 'city': None}
```

You can provide a default value:

```python
student = dict.fromkeys(keys, "Unknown")

print(student)
```

Output:

```text
{'name': 'Unknown', 'age': 'Unknown', 'city': 'Unknown'}
```

---

# Sorting Dictionary Data

The `sorted()` function can be used with dictionary keys.

```python
student = {
    "zebra": 1,
    "apple": 2,
    "mango": 3
}

print(sorted(student))
```

Output:

```text
['apple', 'mango', 'zebra']
```

To sort items by values, you can provide a key function:

```python
scores = {
    "Ali": 80,
    "John": 95,
    "Sara": 88
}

sorted_scores = sorted(
    scores.items(),
    key=lambda item: item[1]
)

print(sorted_scores)
```

---

# Practical Example: Student Information

A dictionary is useful for representing information about an object.

```python
student = {
    "name": "Riyas",
    "age": 20,
    "course": "Python",
    "marks": 85
}

print("Name:", student["name"])
print("Age:", student["age"])
print("Course:", student["course"])
print("Marks:", student["marks"])
```

---

# Practical Example: Counting Items

Dictionaries can be used to count occurrences.

```python
fruits = ["apple", "banana", "apple", "orange", "banana", "apple"]

count = {}

for fruit in fruits:
    if fruit in count:
        count[fruit] += 1
    else:
        count[fruit] = 1

print(count)
```

Output:

```text
{'apple': 3, 'banana': 2, 'orange': 1}
```

This is a common dictionary-based problem-solving pattern.

---

# Dictionary vs List vs Tuple vs Set

| Feature      | List                 | Tuple            | Set                 | Dictionary     |
| ------------ | -------------------- | ---------------- | ------------------- | -------------- |
| Main purpose | Collection of values | Fixed collection | Unique values       | Key-value data |
| Ordered      | Yes                  | Yes              | No guaranteed order | Yes            |
| Mutable      | Yes                  | No               | Yes                 | Yes            |
| Duplicates   | Yes                  | Yes              | No                  | Keys: No       |
| Indexing     | Yes                  | Yes              | No                  | By key         |
| Syntax       | `[]`                 | `()`             | `{}`                | `{key: value}` |
| Access       | Index                | Index            | Membership          | Key            |

---

# Common Dictionary Methods

| Method       | Purpose                        |
| ------------ | ------------------------------ |
| `get()`      | Gets a value safely            |
| `keys()`     | Returns all keys               |
| `values()`   | Returns all values             |
| `items()`    | Returns key-value pairs        |
| `update()`   | Adds or updates items          |
| `pop()`      | Removes a specified key        |
| `popitem()`  | Removes the last inserted pair |
| `clear()`    | Removes all items              |
| `copy()`     | Creates a shallow copy         |
| `fromkeys()` | Creates a dictionary from keys |

---

# Common Mistakes

## 1. Using a missing key

```python
student = {"name": "Riyas"}

print(student["age"])
```

This raises `KeyError`.

Use:

```python
print(student.get("age"))
```

when a missing key should be handled safely.

---

## 2. Using duplicate keys

```python
student = {
    "name": "Riyas",
    "name": "John"
}
```

The second `"name"` replaces the first one.

---

## 3. Confusing keys and values

In:

```python
student = {
    "name": "Riyas"
}
```

`"name"` is the **key**, while `"Riyas"` is the **value**.

---

## 4. Using a list as a key

```python
data = {
    [1, 2]: "numbers"
}
```

This is invalid because lists are unhashable.

---

## 5. Checking for a value using `in`

```python
student = {
    "name": "Riyas",
    "age": 20
}

print("Riyas" in student)
```

This checks whether `"Riyas"` is a **key**, not a value.

To check values:

```python
print("Riyas" in student.values())
```

---

# Quick Reference

```python
# Create
student = {
    "name": "Riyas",
    "age": 20
}

# Access
print(student["name"])

# Safe access
print(student.get("name"))

# Add
student["city"] = "Kochi"

# Update
student["age"] = 21

# Update multiple
student.update({"course": "Python"})

# Check key
print("name" in student)

# Get keys
print(student.keys())

# Get values
print(student.values())

# Get key-value pairs
print(student.items())

# Remove
student.pop("city")

# Remove last inserted item
student.popitem()

# Clear
student.clear()

# Copy
new_student = student.copy()

# Length
print(len(student))
```

---

# Key Points to Remember

1. A **dictionary stores data as key-value pairs**.
2. Dictionaries are **mutable**.
3. Dictionary keys must be **unique**.
4. Dictionary values can be duplicated.
5. Dictionaries preserve **insertion order**.
6. Values are accessed using their keys.
7. `get()` can safely retrieve a value without raising `KeyError` for a missing key.
8. `keys()` returns keys.
9. `values()` returns values.
10. `items()` returns key-value pairs.
11. `update()` adds or changes key-value pairs.
12. `pop()` removes a specified key.
13. `popitem()` removes the last inserted key-value pair.
14. Dictionary keys must be **hashable**.
15. Dictionaries can contain lists and other dictionaries as values.
16. Dictionary comprehensions provide a concise way to create dictionaries.

---

# Interview Questions

### 1. What is a dictionary in Python?

A dictionary is a mutable collection that stores data as key-value pairs.

### 2. Can a dictionary have duplicate keys?

No. Keys must be unique. If the same key is specified more than once, the later value replaces the earlier one.

### 3. Can dictionary values be duplicated?

Yes. Multiple keys can have the same value.

### 4. How do you access a dictionary value?

Using its key:

```python
student["name"]
```

### 5. What happens if you access a missing key using `[]`?

Python raises a `KeyError`.

### 6. How can you safely access a missing key?

Use `get()`:

```python
student.get("age")
```

### 7. What is the difference between `keys()`, `values()`, and `items()`?

* `keys()` → returns keys
* `values()` → returns values
* `items()` → returns key-value pairs

### 8. Can a list be used as a dictionary key?

No. Lists are mutable and unhashable.

### 9. Can a tuple be used as a dictionary key?

Yes, provided all elements inside the tuple are hashable.

### 10. Are dictionaries mutable?

Yes. You can add, modify, and remove key-value pairs.

### 11. What is dictionary comprehension?

It is a concise way to create a dictionary using an expression and an iterable.

```python
squares = {x: x ** 2 for x in range(1, 5)}
```

### 12. What is the difference between a set and a dictionary?

A set stores unique values, while a dictionary stores key-value pairs.

```python
# Set
numbers = {1, 2, 3}

# Dictionary
student = {
    "name": "Riyas",
    "age": 20
}
```
