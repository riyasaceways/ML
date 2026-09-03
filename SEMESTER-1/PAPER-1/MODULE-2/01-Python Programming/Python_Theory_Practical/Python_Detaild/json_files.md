[◀Back](.././)
---


# JSON Files in Python

## What is JSON?

**JSON (JavaScript Object Notation)** is a lightweight, text-based format used to represent and exchange structured data.

JSON is commonly used for:

* Configuration files
* Web applications
* APIs
* Data storage
* Application settings
* Communication between different programs

Example JSON:

```json
{
    "name": "Riyas",
    "age": 25,
    "student": true
}
```

JSON looks similar to Python dictionaries, but JSON is a **data format**, while a Python dictionary is a **Python data structure**.

---

## Python's `json` Module

Python provides a built-in module called `json`.

```python
import json
```

No external installation is required.

The module provides functions for converting between JSON and Python data.

### Important Functions

| Function       | Purpose                            |
| -------------- | ---------------------------------- |
| `json.load()`  | Read JSON from a file              |
| `json.dump()`  | Write JSON to a file               |
| `json.loads()` | Convert JSON string to Python data |
| `json.dumps()` | Convert Python data to JSON string |

---

# JSON Data Types

JSON supports several basic data types.

### JSON Object

A JSON object uses `{}` and contains key-value pairs.

```json
{
    "name": "Riyas",
    "age": 25
}
```

This is similar to a Python dictionary:

```python
{
    "name": "Riyas",
    "age": 25
}
```

---

### JSON Array

A JSON array uses `[]`.

```json
{
    "subjects": ["Python", "SQL", "Machine Learning"]
}
```

It corresponds to a Python list.

```python
["Python", "SQL", "Machine Learning"]
```

---

### JSON String

```json
{
    "name": "Riyas"
}
```

Python equivalent:

```python
{"name": "Riyas"}
```

---

### JSON Number

```json
{
    "age": 25,
    "mark": 87.5
}
```

JSON numbers correspond to Python `int` and `float`.

---

### JSON Boolean

JSON uses:

```json
true
false
```

Python uses:

```python
True
False
```

---

### JSON `null`

JSON uses:

```json
{
    "middle_name": null
}
```

Python equivalent:

```python
{
    "middle_name": None
}
```

---

# Reading a JSON File

Suppose `student.json` contains:

```json
{
    "name": "Riyas",
    "age": 25,
    "course": "Python"
}
```

We can read it using `json.load()`.

```python
import json

with open("student.json", "r", encoding="utf-8") as file:
    data = json.load(file)

print(data)
```

Output:

```text
{'name': 'Riyas', 'age': 25, 'course': 'Python'}
```

The JSON data has been converted into a Python dictionary.

---

## Accessing JSON Data

Once the JSON has been loaded, we can access its values like a normal Python dictionary.

```python
print(data["name"])
print(data["age"])
print(data["course"])
```

Output:

```text
Riyas
25
Python
```

---

# Writing Data to a JSON File

Python data can be written to a JSON file using `json.dump()`.

```python
import json

student = {
    "name": "Riyas",
    "age": 25,
    "course": "Python"
}

with open("student.json", "w", encoding="utf-8") as file:
    json.dump(student, file)
```

This creates:

```json
{
    "name": "Riyas",
    "age": 25,
    "course": "Python"
}
```

---

# Formatting JSON with `indent`

Without indentation, JSON may be written as:

```json
{"name": "Riyas", "age": 25, "course": "Python"}
```

We can make it easier to read using `indent`.

```python
import json

student = {
    "name": "Riyas",
    "age": 25,
    "course": "Python"
}

with open("student.json", "w", encoding="utf-8") as file:
    json.dump(student, file, indent=4)
```

Output:

```json
{
    "name": "Riyas",
    "age": 25,
    "course": "Python"
}
```

---

# Reading JSON from a String

`json.loads()` is used when the JSON data is already available as a **string**.

```python
import json

json_data = '{"name": "Riyas", "age": 25}'

data = json.loads(json_data)

print(data)
```

Output:

```text
{'name': 'Riyas', 'age': 25}
```

### `load()` vs `loads()`

* `load()` → reads JSON from a **file**
* `loads()` → reads JSON from a **string**

---

# Converting Python Data to a JSON String

`json.dumps()` converts Python data into a JSON-formatted string.

```python
import json

student = {
    "name": "Riyas",
    "age": 25
}

json_data = json.dumps(student)

print(json_data)
```

Output:

```text
{"name": "Riyas", "age": 25}
```

### `dump()` vs `dumps()`

* `dump()` → writes JSON to a **file**
* `dumps()` → returns JSON as a **string**

---

# JSON with Lists

JSON can contain arrays.

```json
{
    "name": "Riyas",
    "subjects": [
        "Python",
        "SQL",
        "Machine Learning"
    ]
}
```

Python:

```python
import json

with open("student.json", "r", encoding="utf-8") as file:
    data = json.load(file)

print(data["subjects"])
```

Output:

```text
['Python', 'SQL', 'Machine Learning']
```

Accessing an individual item:

```python
print(data["subjects"][0])
```

Output:

```text
Python
```

---

# JSON with Nested Objects

JSON objects can contain other objects.

```json
{
    "name": "Riyas",
    "address": {
        "city": "Kozhikode",
        "state": "Kerala"
    }
}
```

Python:

```python
print(data["address"]["city"])
```

Output:

```text
Kozhikode
```

---

# JSON with Lists of Objects

A common JSON structure is a list containing multiple objects.

```json
{
    "students": [
        {
            "name": "Riyas",
            "mark": 85
        },
        {
            "name": "Arun",
            "mark": 90
        }
    ]
}
```

Python:

```python
import json

with open("students.json", "r", encoding="utf-8") as file:
    data = json.load(file)

for student in data["students"]:
    print(student["name"], student["mark"])
```

Output:

```text
Riyas 85
Arun 90
```

---

# Updating JSON Data

JSON data becomes a Python object after loading, so we can modify it like normal Python data.

```python
import json

with open("student.json", "r", encoding="utf-8") as file:
    data = json.load(file)

data["age"] = 26
```

To save the updated data:

```python
with open("student.json", "w", encoding="utf-8") as file:
    json.dump(data, file, indent=4)
```

---

# Adding Data

```python
data["city"] = "Kozhikode"
```

Then save:

```python
with open("student.json", "w", encoding="utf-8") as file:
    json.dump(data, file, indent=4)
```

---

# Removing Data

```python
del data["age"]
```

Then save the updated dictionary back to the file.

---

# JSON and Python Data Conversion

When Python converts data to JSON, the types correspond approximately as follows:

| Python  | JSON    |
| ------- | ------- |
| `dict`  | object  |
| `list`  | array   |
| `str`   | string  |
| `int`   | number  |
| `float` | number  |
| `True`  | `true`  |
| `False` | `false` |
| `None`  | `null`  |

Example:

```python
data = {
    "name": "Riyas",
    "age": 25,
    "student": True,
    "skills": ["Python", "SQL"],
    "middle_name": None
}
```

Converted to JSON:

```json
{
    "name": "Riyas",
    "age": 25,
    "student": true,
    "skills": ["Python", "SQL"],
    "middle_name": null
}
```

---

# JSON File Modes

When working with JSON files, the same file modes used with normal text files apply.

### Read

```python
open("data.json", "r")
```

### Write

```python
open("data.json", "w")
```

The `"w"` mode creates the file if it does not exist and replaces its existing contents.

---

# Using `ensure_ascii`

By default, `json.dump()` may escape non-ASCII characters.

You can use:

```python
json.dump(data, file, indent=4, ensure_ascii=False)
```

This is useful when the JSON contains characters from languages other than English.

---

# Handling JSON Errors

Invalid JSON can cause a `json.JSONDecodeError`.

```python
import json

try:
    with open("student.json", "r", encoding="utf-8") as file:
        data = json.load(file)

except json.JSONDecodeError:
    print("Invalid JSON format")
```

This allows the program to handle malformed JSON more safely.

---

# `FileNotFoundError`

If the JSON file does not exist:

```python
import json

try:
    with open("student.json", "r", encoding="utf-8") as file:
        data = json.load(file)

except FileNotFoundError:
    print("JSON file not found")
```

---

# JSON vs Python Dictionary

They may look similar, but they are not the same thing.

### Python Dictionary

```python
student = {
    "name": "Riyas",
    "age": 25
}
```

This exists inside a running Python program.

### JSON

```json
{
    "name": "Riyas",
    "age": 25
}
```

This is stored or exchanged as text data.

We can convert between them using the `json` module.

```text
Python Dictionary
       ↓
   json.dumps()
       ↓
   JSON String
```

And:

```text
JSON String
       ↓
   json.loads()
       ↓
Python Dictionary
```

---

# JSON vs CSV

| JSON                             | CSV                            |
| -------------------------------- | ------------------------------ |
| Supports nested data             | Mainly tabular data            |
| Supports objects and arrays      | Rows and columns               |
| Good for APIs and configurations | Good for spreadsheet-like data |
| More flexible structure          | Simpler structure              |
| Uses `{}` and `[]`               | Uses delimiters such as `,`    |

Example JSON:

```json
{
    "name": "Riyas",
    "skills": ["Python", "SQL"]
}
```

CSV is better suited for:

```text
name,skill
Riyas,Python
Riyas,SQL
```

---

# Practical Example: Student Data

Create a JSON file:

```json
{
    "name": "Riyas",
    "course": "Python",
    "marks": {
        "python": 90,
        "sql": 85
    }
}
```

Python program:

```python
import json

with open("student.json", "r", encoding="utf-8") as file:
    student = json.load(file)

print("Name:", student["name"])
print("Course:", student["course"])
print("Python Mark:", student["marks"]["python"])
print("SQL Mark:", student["marks"]["sql"])
```

Output:

```text
Name: Riyas
Course: Python
Python Mark: 90
SQL Mark: 85
```

---

# Practical Example: Saving Application Settings

JSON is commonly used for configuration data.

```json
{
    "theme": "dark",
    "language": "en",
    "notifications": true
}
```

Python:

```python
import json

settings = {
    "theme": "dark",
    "language": "en",
    "notifications": True
}

with open("settings.json", "w", encoding="utf-8") as file:
    json.dump(settings, file, indent=4)
```

---

# Practical Example: Working with Multiple Students

```python
import json

students = [
    {
        "name": "Riyas",
        "mark": 90
    },
    {
        "name": "Arun",
        "mark": 85
    },
    {
        "name": "Rahul",
        "mark": 92
    }
]

with open("students.json", "w", encoding="utf-8") as file:
    json.dump(students, file, indent=4)
```

The resulting file:

```json
[
    {
        "name": "Riyas",
        "mark": 90
    },
    {
        "name": "Arun",
        "mark": 85
    },
    {
        "name": "Rahul",
        "mark": 92
    }
]
```

---

# Common Mistakes

### 1. Using Python booleans in JSON

Incorrect JSON:

```json
{
    "student": True
}
```

Correct JSON:

```json
{
    "student": true
}
```

---

### 2. Using `None` in JSON

Incorrect JSON:

```json
{
    "value": None
}
```

Correct JSON:

```json
{
    "value": null
}
```

---

### 3. Forgetting Quotes Around Keys

Incorrect:

```json
{
    name: "Riyas"
}
```

Correct:

```json
{
    "name": "Riyas"
}
```

---

### 4. Using Single Quotes

JSON normally requires double quotes for strings.

Incorrect:

```json
{'name': 'Riyas'}
```

Correct:

```json
{"name": "Riyas"}
```

---

### 5. Forgetting to Save Changes

Loading JSON into Python does not automatically update the file.

```python
data["age"] = 26
```

You must write it back:

```python
with open("student.json", "w", encoding="utf-8") as file:
    json.dump(data, file, indent=4)
```

---

# Quick Reference

```python
import json
```

### Read JSON file

```python
with open("data.json", "r", encoding="utf-8") as file:
    data = json.load(file)
```

### Write JSON file

```python
with open("data.json", "w", encoding="utf-8") as file:
    json.dump(data, file, indent=4)
```

### JSON string → Python

```python
data = json.loads(json_string)
```

### Python → JSON string

```python
json_string = json.dumps(data)
```

---

# Key Points

* JSON stands for **JavaScript Object Notation**.
* JSON is a text-based data format.
* Python provides the built-in `json` module.
* `json.load()` reads JSON from a file.
* `json.dump()` writes JSON to a file.
* `json.loads()` converts a JSON string to Python data.
* `json.dumps()` converts Python data to a JSON string.
* JSON objects are represented using `{}`.
* JSON arrays are represented using `[]`.
* JSON supports nested structures.
* JSON is widely used with APIs and configuration files.
* JSON and Python dictionaries look similar but are not the same thing.
* `indent=4` makes JSON easier to read.
* Invalid JSON can raise `json.JSONDecodeError`.

---

# Interview Questions

### 1. What is JSON?

JSON is a lightweight, text-based format used to store and exchange structured data.

### 2. Which Python module is used to work with JSON?

The built-in `json` module.

```python
import json
```

### 3. What is the difference between `json.load()` and `json.loads()`?

`json.load()` reads JSON from a file, while `json.loads()` reads JSON from a string.

### 4. What is the difference between `json.dump()` and `json.dumps()`?

`json.dump()` writes JSON to a file, while `json.dumps()` converts Python data into a JSON string.

### 5. Can JSON store nested data?

Yes. JSON supports nested objects and arrays.

### 6. What is the JSON equivalent of Python `None`?

```text
None → null
```

### 7. What is the JSON equivalent of Python `True`?

```text
True → true
```

### 8. Why is JSON commonly used with APIs?

Because it provides a simple, structured, and language-independent way to exchange data between applications.


[◀Back](.././)
---