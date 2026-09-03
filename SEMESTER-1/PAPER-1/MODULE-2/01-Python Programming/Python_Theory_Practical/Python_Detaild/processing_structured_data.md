# Processing Structured Data in Python

## What is Structured Data?

**Structured data** is information organized in a consistent and predictable format.

Examples include:

* Student records
* Employee information
* Product catalogs
* Customer records
* Configuration data
* API responses
* CSV files
* JSON files

For example:

```python
student = {
    "name": "Riyas",
    "age": 25,
    "mark": 90
}
```

The information has a clear structure:

```text
name → Riyas
age  → 25
mark → 90
```

Structured data is easier for programs to access, process, search, filter, and modify.

---

# Common Python Structures for Structured Data

Python commonly uses:

* Dictionaries
* Lists
* Tuples
* Sets
* Nested combinations of these structures

For data processing, **lists and dictionaries** are especially important.

---

# Dictionaries

A dictionary stores data using **key-value pairs**.

```python
student = {
    "name": "Riyas",
    "age": 25,
    "mark": 90
}
```

Accessing values:

```python
print(student["name"])
print(student["mark"])
```

Output:

```text
Riyas
90
```

Dictionaries are useful when each piece of data has a meaningful name.

---

# Lists

A list stores multiple values.

```python
marks = [90, 85, 92, 78]
```

Accessing values:

```python
print(marks[0])
```

Output:

```text
90
```

Lists are useful when working with collections of data.

---

# List of Dictionaries

A very common structured-data format is a **list of dictionaries**.

```python
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
```

Each dictionary represents one student.

The list contains multiple student records.

```text
students
   │
   ├── Student 1
   │     ├── name
   │     └── mark
   │
   ├── Student 2
   │     ├── name
   │     └── mark
   │
   └── Student 3
         ├── name
         └── mark
```

---

# Accessing Nested Data

To access Rahul's mark:

```python
print(students[2]["mark"])
```

Output:

```text
92
```

The first index accesses the list item.

The key then accesses the dictionary value.

```text
students[2]["mark"]
    │       │
    │       └── dictionary key
    │
    └── list index
```

---

# Iterating Through Structured Data

Instead of accessing every record individually, use a loop.

```python
for student in students:
    print(student["name"])
```

Output:

```text
Riyas
Arun
Rahul
```

To display names and marks:

```python
for student in students:
    print(student["name"], student["mark"])
```

Output:

```text
Riyas 90
Arun 85
Rahul 92
```

---

# Processing Data with Conditions

Structured data can be filtered using conditions.

For example, find students who scored at least 90.

```python
for student in students:
    if student["mark"] >= 90:
        print(student["name"])
```

Output:

```text
Riyas
Rahul
```

The program checks each record and processes only the records that satisfy the condition.

---

# Filtering Structured Data

Filtering means selecting only the data that matches a condition.

```python
students = [
    {"name": "Riyas", "mark": 90},
    {"name": "Arun", "mark": 65},
    {"name": "Rahul", "mark": 92}
]

passed_students = []

for student in students:
    if student["mark"] >= 50:
        passed_students.append(student)

print(passed_students)
```

Output:

```text
[
    {'name': 'Riyas', 'mark': 90},
    {'name': 'Arun', 'mark': 65},
    {'name': 'Rahul', 'mark': 92}
]
```

---

# Updating Structured Data

We can modify values inside a record.

```python
student = {
    "name": "Riyas",
    "mark": 80
}

student["mark"] = 90

print(student)
```

Output:

```text
{'name': 'Riyas', 'mark': 90}
```

With multiple records:

```python
for student in students:
    if student["name"] == "Riyas":
        student["mark"] = 95
```

---

# Adding Data

A new key-value pair can be added to a dictionary.

```python
student = {
    "name": "Riyas",
    "mark": 90
}

student["course"] = "Python"
```

Now:

```python
print(student)
```

Output:

```text
{'name': 'Riyas', 'mark': 90, 'course': 'Python'}
```

A new record can be added to a list:

```python
students.append({
    "name": "Vishnu",
    "mark": 88
})
```

---

# Removing Data

A dictionary value can be removed using `del`.

```python
del student["course"]
```

A list record can be removed using methods such as `remove()`.

```python
students.remove(students[0])
```

When removing structured data, make sure the correct record is selected.

---

# Searching Structured Data

Structured data can be searched using loops and conditions.

```python
for student in students:
    if student["name"] == "Riyas":
        print(student)
```

Output:

```text
{'name': 'Riyas', 'mark': 90}
```

A search can also be written as a reusable function:

```python
def find_student(students, name):
    for student in students:
        if student["name"] == name:
            return student

    return None
```

Usage:

```python
result = find_student(students, "Riyas")

print(result)
```

---

# Counting Records

The `len()` function can be used to count records.

```python
print(len(students))
```

If there are three student records:

```text
3
```

---

# Calculating Values

Structured data can be used for calculations.

```python
total = 0

for student in students:
    total += student["mark"]

print(total)
```

To calculate the average:

```python
total = 0

for student in students:
    total += student["mark"]

average = total / len(students)

print(average)
```

---

# Finding the Highest Value

```python
highest = students[0]

for student in students:
    if student["mark"] > highest["mark"]:
        highest = student

print(highest)
```

This keeps track of the record with the highest mark.

---

# Sorting Structured Data

Python's `sorted()` function can sort structured data.

```python
students = [
    {"name": "Riyas", "mark": 90},
    {"name": "Arun", "mark": 85},
    {"name": "Rahul", "mark": 92}
]

sorted_students = sorted(
    students,
    key=lambda student: student["mark"]
)
```

The records are sorted by mark in ascending order.

To sort in descending order:

```python
sorted_students = sorted(
    students,
    key=lambda student: student["mark"],
    reverse=True
)
```

---

# Nested Structured Data

Structured data can contain multiple levels.

```python
student = {
    "name": "Riyas",
    "contact": {
        "email": "riyas@example.com",
        "phone": "1234567890"
    },
    "subjects": [
        "Python",
        "SQL",
        "Machine Learning"
    ]
}
```

Accessing the email:

```python
print(student["contact"]["email"])
```

Accessing a subject:

```python
print(student["subjects"][0])
```

Output:

```text
Python
```

---

# Processing Nested Data

Suppose we have:

```python
students = [
    {
        "name": "Riyas",
        "subjects": {
            "python": 90,
            "sql": 85
        }
    },
    {
        "name": "Arun",
        "subjects": {
            "python": 80,
            "sql": 88
        }
    }
]
```

We can process the nested data:

```python
for student in students:
    print(student["name"])
    print(student["subjects"]["python"])
```

Output:

```text
Riyas
90
Arun
80
```

---

# Processing JSON Data

JSON is one of the most common formats for structured data.

Example:

```json
{
    "name": "Riyas",
    "age": 25,
    "skills": [
        "Python",
        "SQL"
    ]
}
```

Python can load this JSON:

```python
import json

with open("student.json", "r", encoding="utf-8") as file:
    data = json.load(file)
```

The JSON data is converted into Python objects.

For example:

```text
JSON object → Python dictionary
JSON array  → Python list
JSON string → Python string
JSON number → Python number
JSON true   → Python True
JSON false  → Python False
JSON null   → Python None
```

Once loaded, it can be processed using normal Python operations.

---

# Processing CSV Data

CSV is another common structured-data format.

Example:

```text
name,mark
Riyas,90
Arun,85
Rahul,92
```

Python can read it using the `csv` module:

```python
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.DictReader(file)

    for student in reader:
        print(student["name"], student["mark"])
```

CSV values are generally read as strings, so numerical values may need conversion.

```python
mark = int(student["mark"])
```

---

# Data Transformation

**Data transformation** means changing data into a different structure or format.

For example:

```python
students = [
    {"name": "Riyas", "mark": 90},
    {"name": "Arun", "mark": 85}
]
```

We can create a list containing only the names:

```python
names = []

for student in students:
    names.append(student["name"])

print(names)
```

Output:

```text
['Riyas', 'Arun']
```

The original structured data has been transformed into a simpler list.

---

# Combining Data

Structured data from different sources can sometimes be combined.

```python
names = ["Riyas", "Arun"]
marks = [90, 85]

students = []

for name, mark in zip(names, marks):
    students.append({
        "name": name,
        "mark": mark
    })

print(students)
```

Output:

```text
[
    {'name': 'Riyas', 'mark': 90},
    {'name': 'Arun', 'mark': 85}
]
```

---

# Handling Missing Data

Not every record necessarily contains every field.

```python
students = [
    {"name": "Riyas", "mark": 90},
    {"name": "Arun"},
    {"name": "Rahul", "mark": 92}
]
```

Trying this directly can cause an error:

```python
print(student["mark"])
```

Instead, use `get()`:

```python
for student in students:
    print(student.get("mark"))
```

Output:

```text
90
None
92
```

A default value can also be provided:

```python
mark = student.get("mark", 0)
```

---

# Validating Structured Data

Before processing data, it can be useful to check whether the required information exists.

```python
student = {
    "name": "Riyas",
    "mark": 90
}

if "name" in student and "mark" in student:
    print("Valid student record")
```

This helps prevent errors caused by missing keys.

---

# Real-World Example

Consider product data:

```python
products = [
    {
        "name": "Laptop",
        "price": 55000,
        "stock": 10
    },
    {
        "name": "Mouse",
        "price": 800,
        "stock": 25
    },
    {
        "name": "Keyboard",
        "price": 1500,
        "stock": 0
    }
]
```

Find products that are available:

```python
for product in products:
    if product["stock"] > 0:
        print(product["name"])
```

Output:

```text
Laptop
Mouse
```

Find products above ₹1,000:

```python
for product in products:
    if product["price"] > 1000:
        print(product["name"])
```

Output:

```text
Laptop
Keyboard
```

---

# A Structured Data Processing Workflow

A typical workflow looks like this:

```text
Input
  ↓
Read data
  ↓
Understand structure
  ↓
Access required values
  ↓
Validate data
  ↓
Filter / Search
  ↓
Transform / Calculate
  ↓
Sort / Group
  ↓
Save or display result
```

For example:

```python
import json

# 1. Read
with open("students.json", "r", encoding="utf-8") as file:
    students = json.load(file)

# 2. Process
passed_students = []

for student in students:
    if student["mark"] >= 50:
        passed_students.append(student)

# 3. Sort
passed_students = sorted(
    passed_students,
    key=lambda student: student["mark"],
    reverse=True
)

# 4. Display
for student in passed_students:
    print(student["name"], student["mark"])
```

---

# Common Mistakes

### 1. Assuming Every Key Exists

This can cause a `KeyError`:

```python
print(student["email"])
```

If the key may not exist, consider:

```python
print(student.get("email"))
```

---

### 2. Confusing List Indexes with Dictionary Keys

```python
students[0]
```

Accesses the first list item.

```python
students[0]["name"]
```

Accesses the `"name"` value inside that item.

---

### 3. Forgetting Type Conversion

CSV data is commonly read as strings.

```python
mark = student["mark"]
```

If `mark` is `"90"`, convert it when numerical processing is required:

```python
mark = int(student["mark"])
```

---

### 4. Modifying Data While Iterating

Changing the structure of a list while directly iterating over it can produce unexpected results.

Instead, create a new list when filtering:

```python
filtered_students = []

for student in students:
    if student["mark"] >= 50:
        filtered_students.append(student)
```

---

### 5. Not Understanding the Data Structure

Before processing data, determine whether you are working with:

```text
Dictionary
List
List of dictionaries
Dictionary containing lists
Nested dictionaries
JSON
CSV
```

Understanding the structure makes accessing the data much easier.

---

# Quick Reference

### Access dictionary value

```python
student["name"]
```

### Safe dictionary access

```python
student.get("name")
```

### Access list item

```python
students[0]
```

### Loop through records

```python
for student in students:
    print(student)
```

### Filter records

```python
for student in students:
    if student["mark"] >= 50:
        print(student)
```

### Add a record

```python
students.append({
    "name": "Vishnu",
    "mark": 88
})
```

### Update a value

```python
student["mark"] = 95
```

### Count records

```python
len(students)
```

### Sort records

```python
sorted(students, key=lambda student: student["mark"])
```

---

# Key Points

* Structured data follows a predictable organization.
* Python dictionaries are useful for key-value data.
* Lists are useful for collections of records.
* Lists and dictionaries can be combined to represent complex data.
* Nested structures can contain multiple levels of data.
* Loops are commonly used to process records.
* Conditions can filter structured data.
* Data can be searched, updated, sorted, and transformed.
* `dict.get()` helps handle potentially missing keys.
* JSON is commonly processed using Python's `json` module.
* CSV is commonly processed using Python's `csv` module.
* Data should be validated before processing when its structure may be unreliable.
* Understanding the structure of the data is the first step in processing it.

---

# Interview Questions

### 1. What is structured data?

Structured data is information organized in a consistent and predictable format, making it easier for programs to access and process.

### 2. Which Python data structures are commonly used to process structured data?

Lists and dictionaries are especially common, although tuples, sets, and nested combinations can also be used.

### 3. What is a list of dictionaries?

It is a list where each element is a dictionary representing one structured record.

```python
students = [
    {"name": "Riyas", "mark": 90},
    {"name": "Arun", "mark": 85}
]
```

### 4. How do you access a value in a list of dictionaries?

Use the list index followed by the dictionary key.

```python
students[0]["name"]
```

### 5. How can structured data be filtered?

Use a loop and condition.

```python
for student in students:
    if student["mark"] >= 50:
        print(student)
```

### 6. How can you safely access a dictionary key that may not exist?

Use `get()`.

```python
student.get("email")
```

### 7. What is data transformation?

Data transformation is the process of changing data from one structure or representation into another.

### 8. Why is JSON useful for structured data?

JSON provides a standard, human-readable format for representing nested structured data and is widely used for APIs, configuration, and data exchange.

### 9. Why is CSV useful for structured data?

CSV is useful for tabular data organized into rows and columns and is commonly used for spreadsheet-like datasets.

### 10. What is the first step when processing structured data?

Understand the **structure and format of the data** before deciding how to access and process it.
