[◀Back](.././)
---

# CSV Files

## What is a CSV File?

**CSV** stands for **Comma-Separated Values**.

It is a simple text format commonly used to store **tabular data** in rows and columns.

For example:

```text id="7v3j1n"
name,age,course
Riyas,20,Python
Alex,21,Java
Anu,19,C++
```

The first row is commonly used as a **header**:

```text id="0hj7j6"
name,age,course
```

The remaining rows contain the data:

```text id="p5q4w2"
Riyas,20,Python
Alex,21,Java
Anu,19,C++
```

---

# Why Use CSV Files?

CSV files are useful for storing structured data in a simple format.

Common examples include:

* Student records
* Employee information
* Product data
* Sales records
* Marks
* Customer information
* Contact lists
* Exported spreadsheet data

CSV files are supported by many applications, including spreadsheet software and databases.

---

# CSV Structure

A CSV file usually consists of:

```text id="z1q5q8"
Header
  ↓
Column 1 | Column 2 | Column 3
  ↓
Data rows
```

Example:

```text id="x7y1pj"
name,age,course
Riyas,20,Python
Alex,21,Java
John,22,C++
```

The columns are:

| name  | age | course |
| ----- | --: | ------ |
| Riyas |  20 | Python |
| Alex  |  21 | Java   |
| John  |  22 | C++    |

---

# The `csv` Module

Python provides a built-in `csv` module.

Import it using:

```python id="q1d3yk"
import csv
```

The module provides tools for:

* Reading CSV files.
* Writing CSV files.
* Working with headers.
* Reading rows as dictionaries.
* Writing dictionaries as rows.
* Handling delimiters and quoting.

---

# Reading a CSV File

Suppose `students.csv` contains:

```text id="q3c9t5"
name,age,course
Riyas,20,Python
Alex,21,Java
Anu,19,C++
```

You can read it using `csv.reader()`:

```python id="6f8q2p"
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.reader(file)

    for row in reader:
        print(row)
```

Output:

```text id="7d2n8s"
['name', 'age', 'course']
['Riyas', '20', 'Python']
['Alex', '21', 'Java']
['Anu', '19', 'C++']
```

Each row is returned as a list of strings.

---

# `csv.reader()`

`csv.reader()` reads CSV data row by row.

```python id="f4c8z0"
reader = csv.reader(file)
```

For example:

```python id="4y5r2a"
for row in reader:
    print(row)
```

A row such as:

```text id="7n4q2j"
Riyas,20,Python
```

becomes:

```python id="j5p9v4"
["Riyas", "20", "Python"]
```

---

# Accessing Individual Values

Because each row is a list, you can use indexes.

```python id="v7z3x9"
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.reader(file)

    for row in reader:
        print(row[0])
```

Output:

```text id="1j8r4v"
name
Riyas
Alex
Anu
```

For example:

```python id="p2m8qs"
print(row[1])
```

accesses the second column.

---

# Skipping the Header

If the CSV has a header, you may want to skip it.

```python id="b4k7w1"
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.reader(file)

    next(reader)

    for row in reader:
        print(row)
```

Output:

```text id="6p8s2k"
['Riyas', '20', 'Python']
['Alex', '21', 'Java']
['Anu', '19', 'C++']
```

`next(reader)` retrieves and discards the first row.

---

# Reading CSV With `DictReader`

`csv.DictReader()` reads each row as a dictionary.

```python id="z4k1py"
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.DictReader(file)

    for row in reader:
        print(row)
```

Output will be similar to:

```text id="g8m2z4"
{'name': 'Riyas', 'age': '20', 'course': 'Python'}
{'name': 'Alex', 'age': '21', 'course': 'Java'}
{'name': 'Anu', 'age': '19', 'course': 'C++'}
```

This can be easier to understand because you can use column names.

---

# Accessing `DictReader` Values

```python id="k6q9vx"
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.DictReader(file)

    for row in reader:
        print(row["name"])
        print(row["course"])
```

Output:

```text id="z8w3f5"
Riyas
Python
Alex
Java
Anu
C++
```

Instead of:

```python id="m5j1z7"
row[0]
row[2]
```

you can write:

```python id="7b3c4v"
row["name"]
row["course"]
```

---

# Writing a CSV File

Python provides `csv.writer()` for writing CSV data.

```python id="c9v2r6"
import csv

with open("students.csv", "w", newline="", encoding="utf-8") as file:
    writer = csv.writer(file)

    writer.writerow(["name", "age", "course"])
    writer.writerow(["Riyas", 20, "Python"])
    writer.writerow(["Alex", 21, "Java"])
```

The resulting file contains:

```text id="7g2k8q"
name,age,course
Riyas,20,Python
Alex,21,Java
```

---

# `writerow()`

`writerow()` writes one row.

```python id="4s1k6y"
writer.writerow(["Riyas", 20, "Python"])
```

The list represents one CSV row.

---

# `writerows()`

`writerows()` writes multiple rows.

```python id="0g7w2h"
import csv

rows = [
    ["name", "age", "course"],
    ["Riyas", 20, "Python"],
    ["Alex", 21, "Java"],
    ["Anu", 19, "C++"]
]

with open("students.csv", "w", newline="", encoding="utf-8") as file:
    writer = csv.writer(file)
    writer.writerows(rows)
```

The file contains:

```text id="w2j6c9"
name,age,course
Riyas,20,Python
Alex,21,Java
Anu,19,C++
```

---

# Writing CSV With `DictWriter`

`csv.DictWriter()` allows you to write dictionaries.

```python id="q3y8s6"
import csv

fieldnames = ["name", "age", "course"]

students = [
    {"name": "Riyas", "age": 20, "course": "Python"},
    {"name": "Alex", "age": 21, "course": "Java"},
    {"name": "Anu", "age": 19, "course": "C++"}
]

with open("students.csv", "w", newline="", encoding="utf-8") as file:
    writer = csv.DictWriter(file, fieldnames=fieldnames)

    writer.writeheader()
    writer.writerows(students)
```

The resulting file:

```text id="2q7m8d"
name,age,course
Riyas,20,Python
Alex,21,Java
Anu,19,C++
```

---

# `writeheader()`

When using `DictWriter`, `writeheader()` writes the column names.

```python id="v5c8x2"
writer.writeheader()
```

If:

```python id="a9d3p7"
fieldnames = ["name", "age", "course"]
```

the header becomes:

```text id="2z4q9x"
name,age,course
```

---

# Appending to a CSV File

Use `"a"` mode to add rows without replacing existing data.

```python id="q8v2m1"
import csv

with open("students.csv", "a", newline="", encoding="utf-8") as file:
    writer = csv.writer(file)

    writer.writerow(["John", 22, "JavaScript"])
```

If the file previously contained:

```text id="9m2k7q"
name,age,course
Riyas,20,Python
Alex,21,Java
```

it becomes:

```text id="c5v8x1"
name,age,course
Riyas,20,Python
Alex,21,Java
John,22,JavaScript
```

---

# Important: `"w"` vs `"a"`

| Mode  | Behavior                                        |
| ----- | ----------------------------------------------- |
| `"w"` | Creates or replaces the file                    |
| `"a"` | Creates if needed and adds to the end           |
| `"x"` | Creates only if the file does not already exist |
| `"r"` | Reads the file                                  |

Be careful with `"w"` because it can replace existing CSV data.

---

# Why Use `newline=""`?

When opening CSV files, it is recommended to use:

```python id="x8n4t2"
newline=""
```

Example:

```python id="5r7m3p"
with open("students.csv", "w", newline="", encoding="utf-8") as file:
```

This allows Python's `csv` module to handle newline behavior correctly across platforms.

---

# CSV Values Are Read as Strings

Consider:

```text id="x6v3b1"
name,age
Riyas,20
```

When using `csv.reader()`:

```python id="3k9p5m"
for row in reader:
    print(type(row[1]))
```

The result is:

```text id="g0m7w2"
<class 'str'>
```

Even though `20` looks like a number, CSV text is read as a string.

Convert it when numerical operations are required:

```python id="9q2v6d"
age = int(row[1])
```

---

# Practical Example: Calculate Average Marks

Suppose `marks.csv` contains:

```text id="k4x7m2"
name,mark
Riyas,80
Alex,75
Anu,90
```

You can calculate the average:

```python id="h2m8v5"
import csv

marks = []

with open("marks.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.DictReader(file)

    for row in reader:
        marks.append(int(row["mark"]))

average = sum(marks) / len(marks)

print("Average:", average)
```

Output:

```text id="j9p3s7"
Average: 81.66666666666667
```

The important part is:

```python id="z4x8k1"
int(row["mark"])
```

because CSV values are initially strings.

---

# Practical Example: Product Data

CSV:

```text id="b7m3q9"
product,price,quantity
Keyboard,1500,2
Mouse,800,3
Monitor,12000,1
```

Python:

```python id="c2k7v4"
import csv

with open("products.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.DictReader(file)

    for row in reader:
        product = row["product"]
        price = float(row["price"])
        quantity = int(row["quantity"])

        total = price * quantity

        print(product, total)
```

Output:

```text id="p8q2m6"
Keyboard 3000.0
Mouse 2400.0
Monitor 12000.0
```

---

# Practical Example: Creating a Student CSV

```python id="m4x8v2"
import csv

students = [
    {"name": "Riyas", "age": 20, "mark": 85},
    {"name": "Alex", "age": 21, "mark": 78},
    {"name": "Anu", "age": 19, "mark": 92}
]

fieldnames = ["name", "age", "mark"]

with open("students.csv", "w", newline="", encoding="utf-8") as file:
    writer = csv.DictWriter(file, fieldnames=fieldnames)

    writer.writeheader()
    writer.writerows(students)
```

---

# CSV Delimiters

CSV stands for comma-separated values, so the default delimiter is:

```text id="g4y8p1"
,
```

Example:

```text id="c7v2m9"
name,age,course
Riyas,20,Python
```

However, other separators can be used.

For example:

```text id="q8m4x2"
name;age;course
Riyas;20;Python
```

You can specify the delimiter:

```python id="j6p3v8"
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.reader(file, delimiter=";")

    for row in reader:
        print(row)
```

---

# Tab-Separated Data

A tab can also be used as a delimiter.

```python id="f3k8m1"
reader = csv.reader(file, delimiter="\t")
```

The CSV module can therefore work with delimited text beyond commas.

---

# Quoted Values

CSV data may contain commas inside a value.

For example:

```text id="r7p2m5"
name,address
Riyas,"Kozhikode, Kerala"
```

The address contains a comma, but the quotes tell the CSV parser that it is one field.

Using `csv.reader()`:

```python id="x4m8q2"
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.reader(file)

    for row in reader:
        print(row)
```

The address remains one value.

This is one reason it is better to use Python's `csv` module instead of manually splitting CSV lines with:

```python id="b9v3k7"
line.split(",")
```

---

# Why Not Use `split(",")`?

A simple approach might be:

```python id="y7m2q5"
line = "Riyas,20,Python"

data = line.split(",")

print(data)
```

This works for very simple data.

But CSV has rules for:

* Quoted fields.
* Commas inside fields.
* Different delimiters.
* Escaping.
* Newlines inside quoted fields.

Therefore, use:

```python id="k3x8p1"
csv.reader()
```

for actual CSV files.

---

# CSV and Dictionaries

`DictReader` is useful when the CSV contains headers.

CSV:

```text id="c8m4v2"
name,age,course
Riyas,20,Python
```

Python:

```python id="m6p2x9"
reader = csv.DictReader(file)

for row in reader:
    print(row["name"])
```

This is often clearer than relying on column indexes.

---

# CSV and Lists

`csv.reader()` returns rows as lists.

```python id="q5x7m3"
for row in reader:
    print(row)
```

Example:

```python id="w8k2v4"
["Riyas", "20", "Python"]
```

You can therefore use normal list operations:

```python id="p4m9x1"
for row in reader:
    print(len(row))
```

---

# Handling Missing Values

A CSV file may contain empty fields.

Example:

```text id="z7k3m8"
name,age,course
Riyas,20,
Alex,,Java
```

The reader can return empty strings for those fields.

With `DictReader`:

```python id="n5q2v8"
for row in reader:
    print(row["name"], row["age"], row["course"])
```

You can check for empty values:

```python id="m8x4p1"
if row["age"] == "":
    print("Age is missing")
```

---

# Handling Extra or Missing Columns

When working with structured CSV data, the number and names of columns should generally match the expected format.

For `DictWriter`, `fieldnames` defines the expected columns:

```python id="x2m7q5"
fieldnames = ["name", "age", "course"]
```

Then dictionaries can be written according to those field names.

---

# Reading CSV With `DictReader` and Filtering

Suppose:

```text id="f6k2m9"
name,mark
Riyas,85
Alex,45
Anu,92
```

You can find students who passed:

```python id="r4x8m1"
import csv

with open("marks.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.DictReader(file)

    for row in reader:
        mark = int(row["mark"])

        if mark >= 50:
            print(row["name"])
```

Output:

```text id="y3q7m2"
Riyas
Anu
```

---

# CSV File Workflow

A typical CSV workflow is:

```text id="q8m4x2"
CSV File
   ↓
open()
   ↓
csv.reader() / csv.DictReader()
   ↓
Read rows
   ↓
Process data
   ↓
Close file
```

For writing:

```text id="v2k7m5"
Python Data
   ↓
open()
   ↓
csv.writer() / csv.DictWriter()
   ↓
Write rows
   ↓
Close file
```

---

# `reader` vs `DictReader`

| `csv.reader()`             | `csv.DictReader()`                            |
| -------------------------- | --------------------------------------------- |
| Returns each row as a list | Returns each row as a dictionary-like mapping |
| Access by index            | Access by column name                         |
| Simple and direct          | Easier for named columns                      |
| `row[0]`                   | `row["name"]`                                 |

Example:

```python id="c4x9m7"
# reader
row[0]
```

vs:

```python id="h7q2p5"
# DictReader
row["name"]
```

---

# `writer` vs `DictWriter`

| `csv.writer()`            | `csv.DictWriter()`                       |
| ------------------------- | ---------------------------------------- |
| Writes lists/sequences    | Writes dictionaries                      |
| Uses column positions     | Uses field names                         |
| `writerow(["Riyas", 20])` | `writerow({"name": "Riyas", "age": 20})` |
| Simple tabular data       | Structured named-column data             |

---

# CSV vs Normal Text Files

| Text File                         | CSV File                       |
| --------------------------------- | ------------------------------ |
| General-purpose text              | Structured tabular data        |
| No fixed column structure         | Usually organized into columns |
| Often processed manually          | Has a dedicated CSV parser     |
| `.txt` commonly used              | `.csv` commonly used           |
| `read()` / `write()` often enough | `csv` module is useful         |

---

# CSV vs Excel

CSV:

* Plain text.
* Simple.
* Easy to exchange.
* Stores rows and columns.
* Does not store spreadsheet formatting, formulas, or multiple worksheets.

Excel files such as `.xlsx` are richer spreadsheet formats and can contain formatting, formulas, charts, and multiple worksheets.

For basic tabular data exchange, CSV is often sufficient.

---

# Common Mistakes

## 1. Forgetting to Import `csv`

Incorrect:

```python id="p8m3x6"
reader = csv.reader(file)
```

Correct:

```python id="j4q7v2"
import csv
```

---

## 2. Forgetting `newline=""`

For normal CSV handling, prefer:

```python id="r6m2x8"
with open("data.csv", "r", newline="", encoding="utf-8") as file:
```

and:

```python id="x3q9m5"
with open("data.csv", "w", newline="", encoding="utf-8") as file:
```

---

## 3. Treating CSV Numbers as Numbers

CSV values are generally read as strings.

```python id="v8k2p4"
age = int(row["age"])
```

Convert them when numerical operations are needed.

---

## 4. Using `split(",")` for Real CSV Parsing

This can fail when fields contain commas inside quotes.

Prefer:

```python id="m7q3x9"
csv.reader(file)
```

---

## 5. Accidentally Overwriting Data

Using:

```python id="n2k8v5"
open("students.csv", "w")
```

can replace the existing contents.

Use `"a"` when you need to append.

---

## 6. Forgetting the Header

When using `DictReader`, the first row is normally interpreted as the field names.

Make sure the CSV header contains the expected column names.

---

# Quick Reference

### Read CSV

```python id="b4m7x2"
import csv

with open("data.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.reader(file)

    for row in reader:
        print(row)
```

### Read CSV as dictionaries

```python id="q8x3m6"
import csv

with open("data.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.DictReader(file)

    for row in reader:
        print(row["name"])
```

### Write CSV

```python id="v5m9k2"
import csv

with open("data.csv", "w", newline="", encoding="utf-8") as file:
    writer = csv.writer(file)

    writer.writerow(["name", "age"])
    writer.writerow(["Riyas", 20])
```

### Write dictionaries

```python id="x7q2m4"
import csv

fieldnames = ["name", "age"]

with open("data.csv", "w", newline="", encoding="utf-8") as file:
    writer = csv.DictWriter(file, fieldnames=fieldnames)

    writer.writeheader()
    writer.writerow({"name": "Riyas", "age": 20})
```

### Append a row

```python id="m3k8v6"
with open("data.csv", "a", newline="", encoding="utf-8") as file:
    writer = csv.writer(file)
    writer.writerow(["Alex", 21])
```

---

# Key Points

* **CSV** means **Comma-Separated Values**.
* CSV files are commonly used to store tabular data.
* Python provides the built-in `csv` module.
* `csv.reader()` reads rows as lists.
* `csv.DictReader()` reads rows using column names.
* `csv.writer()` writes rows.
* `csv.DictWriter()` writes dictionary-based rows.
* `writerow()` writes one row.
* `writerows()` writes multiple rows.
* `writeheader()` writes column names when using `DictWriter`.
* CSV values are generally read as strings.
* Convert numeric values with `int()` or `float()` when necessary.
* Use `newline=""` when opening CSV files for normal CSV handling.
* Use `encoding="utf-8"` for text encoding.
* `"w"` can replace existing data, while `"a"` appends.
* Use the `csv` module instead of manually using `split(",")` for proper CSV parsing.
* CSV files store data, but unlike spreadsheet formats such as `.xlsx`, they do not store rich spreadsheet features such as formatting, formulas, charts, or multiple worksheets.

---

# Interview Questions

### 1. What is CSV?

CSV stands for **Comma-Separated Values**. It is a text-based format commonly used to store tabular data.

### 2. Which Python module is used to work with CSV files?

The built-in `csv` module.

```python id="q7m3x8"
import csv
```

### 3. What is `csv.reader()`?

`csv.reader()` reads CSV data row by row, returning each row as a list.

### 4. What is `csv.DictReader()`?

`DictReader` reads each CSV row using the header names as dictionary keys.

### 5. What is the difference between `reader` and `DictReader`?

`reader` accesses columns using indexes:

```python id="n4k8p2"
row[0]
```

`DictReader` accesses columns using names:

```python id="x6m2q9"
row["name"]
```

### 6. How do you write data to a CSV file?

Use `csv.writer()`:

```python id="r8v3m5"
writer.writerow(["Riyas", 20])
```

### 7. What is `DictWriter`?

`DictWriter` writes dictionaries to a CSV file using predefined field names.

### 8. What is the difference between `"w"` and `"a"` when writing CSV?

* `"w"` creates or replaces the file.
* `"a"` preserves existing data and adds new rows at the end.

### 9. Are CSV numbers automatically read as integers?

No. CSV values are generally read as strings.

```python id="k3x7m1"
age = int(row["age"])
```

### 10. Why should `newline=""` be used with the `csv` module?

It allows the CSV module to handle newline processing correctly across platforms.

### 11. Why shouldn't you simply use `split(",")` to parse a CSV file?

Because valid CSV can contain quoted fields containing commas, which simple string splitting does not correctly handle.

### 12. How do you write CSV headers using `DictWriter`?

```python id="p5m8x2"
writer.writeheader()
```

### 13. Can CSV files contain strings with commas?

Yes. Such fields can be quoted according to CSV rules.

Example:

```text id="v2q7m4"
Riyas,"Kozhikode, Kerala"
```

### 14. Can Python read CSV files without installing an external library?

Yes. Python's `csv` module is part of the standard library.

### 15. What is the advantage of using `DictReader`?

It makes code easier to understand because columns can be accessed by meaningful names instead of numeric indexes.


[◀Back](.././)
---