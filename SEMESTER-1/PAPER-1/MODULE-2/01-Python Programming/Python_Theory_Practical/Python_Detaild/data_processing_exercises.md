[◀Back](.././)
---

# Data Processing Exercises

Data processing means **taking raw data and performing operations on it to produce useful, organized, or meaningful information**.

A typical data-processing workflow is:

```text
Raw Data
   ↓
Read / Collect
   ↓
Clean
   ↓
Transform
   ↓
Filter / Sort / Group
   ↓
Analyze
   ↓
Output
```

Python is particularly useful for these tasks because it provides powerful tools for working with:

* Lists
* Tuples
* Sets
* Dictionaries
* Strings
* Files
* CSV
* JSON
* Functions
* Loops
* Conditions

---

# 1. What Is Data Processing?

Suppose we have:

```python id="p8pxj1"
marks = [70, 85, 60, 95, 45]
```

We can process this data to:

* Find the highest mark
* Find the lowest mark
* Calculate the average
* Find students above a certain mark
* Sort the marks
* Count passing students

The original values are the **input**, while the calculated information is the **output**.

---

# 2. Basic Data Processing Pattern

A common pattern is:

```python id="v4s5o8"
data = [...]

result = []

for item in data:
    if condition:
        result.append(item)

print(result)
```

Example:

```python id="d7rjap"
numbers = [10, 15, 20, 25, 30]

result = []

for number in numbers:
    if number >= 20:
        result.append(number)

print(result)
```

Output:

```text id="p0n8rj"
[20, 25, 30]
```

---

# 3. Filtering Data

Filtering means selecting only the data that meets a condition.

```python id="1j7m6w"
numbers = [10, 15, 20, 25, 30]

even_numbers = []

for number in numbers:
    if number % 2 == 0:
        even_numbers.append(number)

print(even_numbers)
```

Output:

```text id="f7yy0h"
[10, 20, 30]
```

### Using list comprehension

```python id="y3x9uo"
even_numbers = [number for number in numbers if number % 2 == 0]
```

---

# 4. Transforming Data

Transformation means changing data from one form into another.

Example: convert temperatures from Celsius to Fahrenheit.

```python id="zj6p1u"
celsius = [0, 10, 20, 30]

fahrenheit = []

for temperature in celsius:
    result = (temperature * 9 / 5) + 32
    fahrenheit.append(result)

print(fahrenheit)
```

Output:

```text id="qj50dp"
[32.0, 50.0, 68.0, 86.0]
```

---

# 5. Cleaning Data

Real-world data may contain unnecessary spaces or inconsistent formatting.

Example:

```python id="9y3dcr"
names = [
    " Ali ",
    "RIYAS",
    " john"
]
```

Clean the names:

```python id="h8l3mw"
cleaned_names = []

for name in names:
    cleaned_names.append(name.strip().title())

print(cleaned_names)
```

Output:

```text id="2c5v8d"
['Ali', 'Riyas', 'John']
```

---

# 6. Removing Empty Values

Suppose:

```python id="3p6c5m"
names = ["Ali", "", "Riyas", "", "John"]
```

We can remove empty strings:

```python id="n3v9s7"
result = []

for name in names:
    if name:
        result.append(name)

print(result)
```

Output:

```text id="v2q8l4"
['Ali', 'Riyas', 'John']
```

---

# 7. Removing Duplicate Data

```python id="t7n2qm"
names = ["Ali", "Riyas", "Ali", "John", "Riyas"]

unique_names = []

for name in names:
    if name not in unique_names:
        unique_names.append(name)

print(unique_names)
```

Output:

```text id="j8y6q0"
['Ali', 'Riyas', 'John']
```

A set can also be used when ordering is not important:

```python id="k1x7qa"
unique_names = list(set(names))
```

---

# 8. Sorting Data

```python id="x6m1tv"
marks = [75, 90, 65, 85, 70]

marks.sort()

print(marks)
```

Output:

```text id="c8z0wm"
[65, 70, 75, 85, 90]
```

Descending order:

```python id="e8z3qk"
marks.sort(reverse=True)
```

---

# 9. Searching Data

```python id="r9s4je"
names = ["Ali", "Riyas", "John"]

search_name = "Riyas"

if search_name in names:
    print("Found")
else:
    print("Not found")
```

Output:

```text id="q6h8z2"
Found
```

---

# 10. Counting Data

```python id="v0p8xw"
marks = [50, 70, 80, 50, 90, 50]

print(marks.count(50))
```

Output:

```text id="w4n2sc"
3
```

---

# 11. Frequency Analysis

A dictionary can store the frequency of each value.

```python id="p7x5as"
items = ["apple", "banana", "apple", "orange", "banana", "apple"]

frequency = {}

for item in items:
    frequency[item] = frequency.get(item, 0) + 1

print(frequency)
```

Output:

```text id="m4v9rt"
{'apple': 3, 'banana': 2, 'orange': 1}
```

---

# 12. Calculating Statistics

Given:

```python id="3q0d9b"
marks = [70, 85, 60, 95, 80]
```

### Total

```python id="x7v2kg"
total = sum(marks)
```

### Average

```python id="m9q4tz"
average = sum(marks) / len(marks)
```

### Highest

```python id="n8w5fp"
highest = max(marks)
```

### Lowest

```python id="e5s7hy"
lowest = min(marks)
```

---

# 13. Processing Student Records

A realistic dataset can be represented using a list of dictionaries.

```python id="w1c8df"
students = [
    {"name": "Ali", "mark": 75},
    {"name": "Riyas", "mark": 90},
    {"name": "John", "mark": 65},
    {"name": "Alex", "mark": 85}
]
```

Each dictionary represents one student.

---

# 14. Filter Students by Mark

```python id="x2b7md"
for student in students:
    if student["mark"] >= 80:
        print(student["name"])
```

Output:

```text id="r8s1qa"
Riyas
Alex
```

---

# 15. Calculate Average Student Mark

```python id="p6w4sn"
total = 0

for student in students:
    total += student["mark"]

average = total / len(students)

print(average)
```

---

# 16. Find the Highest-scoring Student

```python id="z9q3kf"
highest = max(students, key=lambda student: student["mark"])

print(highest)
```

Output:

```text id="a5k8nx"
{'name': 'Riyas', 'mark': 90}
```

---

# 17. Sort Student Records

Sort by mark:

```python id="v4c7mp"
sorted_students = sorted(
    students,
    key=lambda student: student["mark"]
)

print(sorted_students)
```

Highest first:

```python id="b8t2wr"
sorted_students = sorted(
    students,
    key=lambda student: student["mark"],
    reverse=True
)
```

---

# 18. Assign Categories

Data can be transformed into categories.

```python id="n7k4sy"
students = [
    {"name": "Ali", "mark": 75},
    {"name": "Riyas", "mark": 90},
    {"name": "John", "mark": 55}
]

for student in students:
    if student["mark"] >= 80:
        student["grade"] = "A"
    elif student["mark"] >= 60:
        student["grade"] = "B"
    else:
        student["grade"] = "C"

print(students)
```

Now each record contains an additional `grade` field.

---

# 19. Group Data

Suppose we have:

```python id="q8j3wv"
students = [
    {"name": "Ali", "course": "Python"},
    {"name": "Riyas", "course": "Python"},
    {"name": "John", "course": "Java"},
    {"name": "Alex", "course": "Java"}
]
```

Group students by course:

```python id="m6x2pa"
groups = {}

for student in students:
    course = student["course"]

    if course not in groups:
        groups[course] = []

    groups[course].append(student["name"])

print(groups)
```

Output:

```text id="c5n8yd"
{
    'Python': ['Ali', 'Riyas'],
    'Java': ['John', 'Alex']
}
```

---

# 20. Processing Nested Data

Nested collections are common in data processing.

```python id="h4z8kp"
sales = [
    [100, 200, 150],
    [300, 250, 100],
    [500, 100, 200]
]
```

Calculate the total:

```python id="q1r6vs"
total = 0

for row in sales:
    for value in row:
        total += value

print(total)
```

---

# 21. Process Data from Strings

Suppose data arrives as a string:

```python id="j7s4mn"
data = "Ali,75;Riyas,90;John,65"
```

Split the records:

```python id="r2f9kc"
records = data.split(";")

print(records)
```

Then process each record:

```python id="u5x3wb"
for record in records:
    name, mark = record.split(",")
    print(name, mark)
```

Output:

```text id="g8q1sd"
Ali 75
Riyas 90
John 65
```

---

# 22. Convert Data Types During Processing

Data read from text files is often represented as strings.

```python id="c4m7yx"
mark = "90"

mark = int(mark)

print(mark + 10)
```

Output:

```text id="f2s6kd"
100
```

This is important when processing CSV or other text-based data.

---

# 23. CSV Data Processing

Python provides the `csv` module for working with CSV files.

Example CSV:

```text id="2b8x7m"
name,mark
Ali,75
Riyas,90
John,65
```

Read it:

```python id="k9p3wv"
import csv

with open("students.csv", newline="", encoding="utf-8") as file:
    reader = csv.DictReader(file)

    for row in reader:
        print(row["name"], row["mark"])
```

CSV values are normally read as strings, so numeric values may need conversion:

```python id="d6w1fz"
mark = int(row["mark"])
```

---

# 24. Filter CSV Data

```python id="p8q2rm"
import csv

with open("students.csv", newline="", encoding="utf-8") as file:
    reader = csv.DictReader(file)

    for row in reader:
        if int(row["mark"]) >= 80:
            print(row["name"])
```

---

# 25. JSON Data Processing

JSON is commonly used for structured data.

Example:

```python id="s4m9vk"
students = [
    {"name": "Ali", "mark": 75},
    {"name": "Riyas", "mark": 90}
]
```

JSON can be loaded using the `json` module:

```python id="e6q1hy"
import json

with open("students.json", encoding="utf-8") as file:
    data = json.load(file)

for student in data:
    print(student["name"])
```

---

# 26. Transforming JSON Data

```python id="y7r2cp"
for student in data:
    student["passed"] = student["mark"] >= 50
```

This adds a new calculated field.

---

# 27. Combining Multiple Data Sources

Suppose we have:

```python id="w8k5ns"
students = {
    1: "Ali",
    2: "Riyas",
    3: "John"
}

marks = {
    1: 75,
    2: 90,
    3: 65
}
```

We can combine the information:

```python id="f3m6qa"
for student_id, name in students.items():
    mark = marks[student_id]
    print(name, mark)
```

Output:

```text id="n4x7jp"
Ali 75
Riyas 90
John 65
```

---

# 28. Handling Missing Data

Real datasets may contain missing values.

```python id="r5c8mz"
students = [
    {"name": "Ali", "mark": 75},
    {"name": "Riyas"},
    {"name": "John", "mark": 65}
]
```

Accessing `student["mark"]` directly can fail for the second record.

Use `.get()`:

```python id="b7q1vx"
for student in students:
    mark = student.get("mark")

    if mark is not None:
        print(student["name"], mark)
```

---

# 29. Data Validation

Before processing data, validate it.

```python id="t9k4cw"
mark = "85"

if mark.isdigit():
    mark = int(mark)

    if 0 <= mark <= 100:
        print("Valid mark")
    else:
        print("Invalid range")
else:
    print("Invalid value")
```

Validation prevents unexpected data from causing incorrect results.

---

# 30. Cleaning Numeric Data

Suppose numbers are stored as strings with spaces:

```python id="v2n7px"
values = [" 10 ", "20", " 30"]
```

Clean and convert:

```python id="q6m4zs"
numbers = []

for value in values:
    numbers.append(int(value.strip()))

print(numbers)
```

Output:

```text id="y8c2kr"
[10, 20, 30]
```

---

# 31. Processing Text Data

Given:

```python id="k3p7vf"
text = "Python is easy. Python is powerful."
```

We can count words:

```python id="m8q1dx"
words = text.split()

print(len(words))
```

Or count occurrences:

```python id="w5z9ta"
print(words.count("Python"))
```

---

# 32. Building a Simple Report

Processed information can be combined into a report.

```python id="h6r2yc"
marks = [75, 90, 65, 85]

total = sum(marks)
average = total / len(marks)
highest = max(marks)
lowest = min(marks)

print("Total:", total)
print("Average:", average)
print("Highest:", highest)
print("Lowest:", lowest)
```

Output:

```text id="u3k7mp"
Total: 315
Average: 78.75
Highest: 90
Lowest: 65
```

---

# 33. Data Processing with Functions

Separate processing tasks into functions.

```python id="n4w8qa"
def calculate_average(values):
    if not values:
        return 0

    return sum(values) / len(values)


marks = [75, 90, 65]

print(calculate_average(marks))
```

Functions make processing logic easier to reuse and test.

---

# 34. A Complete Small Example

Consider student data:

```python id="x7m3pv"
students = [
    {"name": "Ali", "mark": 75},
    {"name": "Riyas", "mark": 90},
    {"name": "John", "mark": 45},
    {"name": "Alex", "mark": 85}
]
```

### Step 1 — Filter passing students

```python id="c5q8yk"
passed = []

for student in students:
    if student["mark"] >= 50:
        passed.append(student)
```

### Step 2 — Sort by mark

```python id="r2v6mz"
passed = sorted(
    passed,
    key=lambda student: student["mark"],
    reverse=True
)
```

### Step 3 — Display the result

```python id="f9k1ws"
for student in passed:
    print(student["name"], student["mark"])
```

Output:

```text id="m4q7zp"
Riyas 90
Alex 85
Ali 75
```

This example demonstrates:

```text id="j8c3xa"
Data
 ↓
Filter
 ↓
Sort
 ↓
Output
```

---

# 35. Common Data Processing Operations

| Operation   | Purpose                          |
| ----------- | -------------------------------- |
| Filter      | Select matching data             |
| Transform   | Change data into another form    |
| Clean       | Remove or correct unwanted data  |
| Sort        | Arrange data                     |
| Search      | Find specific data               |
| Count       | Count records or occurrences     |
| Aggregate   | Calculate totals/statistics      |
| Group       | Organize related records         |
| Deduplicate | Remove repeated data             |
| Validate    | Check whether data is acceptable |
| Merge       | Combine data                     |
| Extract     | Retrieve required information    |
| Report      | Present processed information    |

---

# 36. Common Data Structures for Processing

### List

Useful for ordered collections:

```python id="a7x3pn"
students = ["Ali", "Riyas", "John"]
```

### Dictionary

Useful for key-value data:

```python id="q8m2vr"
student = {
    "name": "Riyas",
    "mark": 90
}
```

### List of Dictionaries

Very common for records:

```python id="k5z9wf"
students = [
    {"name": "Ali", "mark": 75},
    {"name": "Riyas", "mark": 90}
]
```

### Set

Useful for unique values:

```python id="n6p4yc"
courses = {"Python", "Java", "Python"}
```

Result:

```text id="s1w8km"
{'Python', 'Java'}
```

---

# 37. Common Mistakes

## Mistake 1 — Processing data before validating it

Bad input can cause:

```text id="q4m7xy"
ValueError
KeyError
TypeError
```

Validate data before using it.

---

## Mistake 2 — Assuming every record has the same fields

This can fail:

```python id="c8n2vz"
mark = student["mark"]
```

If `"mark"` is missing, a `KeyError` occurs.

Safer:

```python id="p6x4wk"
mark = student.get("mark")
```

---

## Mistake 3 — Forgetting type conversion

CSV and other text-based input often gives:

```python id="j3r8mq"
"90"
```

rather than:

```python id="s7v2kc"
90
```

Convert when numeric processing is required:

```python id="a9q5xf"
mark = int(mark)
```

---

## Mistake 4 — Modifying a collection while iterating

Avoid:

```python id="u4m8pz"
for item in data:
    if condition:
        data.remove(item)
```

Elements can be skipped.

Build a new collection instead:

```python id="x5k1vr"
filtered = [item for item in data if not condition]
```

---

## Mistake 5 — Dividing by zero

This is unsafe for an empty collection:

```python id="z7p3mc"
average = sum(values) / len(values)
```

Use:

```python id="n2w6qy"
if values:
    average = sum(values) / len(values)
```

---

# 38. Data Processing and Error Handling

File and external data processing can fail.

For example:

```python id="r9c4xm"
try:
    with open("students.csv", encoding="utf-8") as file:
        ...
except FileNotFoundError:
    print("File not found")
```

Specific exceptions make programs easier to understand and debug.

---

# 39. Data Processing and Functions

Large processing tasks should be divided into smaller functions.

For example:

```python id="k7v2ps"
def clean_data(data):
    ...


def filter_data(data):
    ...


def calculate_statistics(data):
    ...


def generate_report(data):
    ...
```

This creates a clearer pipeline:

```text id="m3x8qa"
Read
 ↓
Clean
 ↓
Validate
 ↓
Filter
 ↓
Transform
 ↓
Analyze
 ↓
Report
```

---

# 40. Practice Projects

Try building these small projects:

### 1. Student Mark Analyzer

Input:

```text id="b5q7zn"
Student names and marks
```

Calculate:

* Highest mark
* Lowest mark
* Average
* Pass count
* Fail count
* Grade distribution

---

### 2. Sales Data Analyzer

Process sales records and calculate:

* Total sales
* Highest sale
* Lowest sale
* Average sale
* Sales by product
* Sales by employee

---

### 3. Word Frequency Analyzer

Given a paragraph:

* Count words
* Count unique words
* Find most frequent word
* Find longest word
* Find shortest word

---

### 4. CSV Student Analyzer

Read a CSV file containing:

```text id="g6m2wp"
name,course,mark
```

Then:

* Filter passing students
* Calculate average marks
* Find highest scorer
* Group students by course

---

### 5. Expense Analyzer

Process:

```python id="y8n4kc"
expenses = [
    {"category": "Food", "amount": 500},
    {"category": "Travel", "amount": 300},
    {"category": "Food", "amount": 200}
]
```

Calculate:

* Total expenses
* Expenses by category
* Highest expense
* Average expense

---

# Problem-Solving Workflow

When solving a data-processing problem, follow this process:

```text
1. Understand the data
        ↓
2. Identify the required output
        ↓
3. Choose the appropriate data structure
        ↓
4. Clean and validate the data
        ↓
5. Process the data
        ↓
6. Filter / Sort / Group / Transform
        ↓
7. Calculate required results
        ↓
8. Test edge cases
        ↓
9. Display or save the result
```

---

# Key Points

* Data processing converts **raw data into useful information**.
* Lists and dictionaries are frequently used for processing records.
* Filtering selects data based on conditions.
* Transformation changes data into a required format.
* Cleaning removes unwanted or inconsistent data.
* Sorting organizes data.
* Grouping organizes related records.
* Dictionaries are useful for frequency counting and grouping.
* CSV and JSON are common sources of structured data.
* Data read from text-based sources often needs type conversion.
* Always validate data before processing it.
* Empty collections and missing fields must be handled safely.
* Functions help divide complex processing into reusable steps.
* A common pattern is **Read → Clean → Validate → Process → Analyze → Output**.

---

# Interview Questions

### 1. What is data processing?

Data processing is the process of collecting, cleaning, transforming, organizing, and analyzing data to produce useful information.

### 2. What is the difference between filtering and transforming?

**Filtering** selects specific elements from the data, while **transformation** changes the values or structure of the data.

### 3. Why are dictionaries useful in data processing?

Dictionaries provide key-value storage and are useful for representing records, frequency counting, grouping, and fast key-based lookups.

### 4. Why is data validation important?

It ensures that invalid, missing, or unexpected data does not produce incorrect results or cause program failures.

### 5. Why do CSV values often need type conversion?

CSV data is read as text, so values such as numbers generally need to be converted to `int` or `float` before numerical calculations.

### 6. What is data cleaning?

Data cleaning is the process of handling unwanted spaces, missing values, duplicates, inconsistent formats, and other data-quality problems.

### 7. What is aggregation?

Aggregation combines multiple values to produce a summary, such as a total, average, minimum, or maximum.

### 8. How can you group data in Python?

A dictionary can be used to create groups based on a common property.

### 9. Why should you avoid modifying a list while iterating over it?

Modifying the list during iteration can cause elements to be skipped or produce unexpected behavior. Creating a new filtered collection is often safer.

### 10. What is a common data-processing workflow?

```text
Read → Clean → Validate → Transform → Filter/Group → Analyze → Output
```


[◀Back](.././)
---