## Reading Files

**Reading files** in Python means opening a file and retrieving its contents using functions such as `open()`. Python provides different methods for reading the complete file, individual lines, or multiple lines.

```python
file = open("example.txt", "r")

content = file.read()

print(content)

file.close()
```

The recommended approach is to use `with open()`, which automatically closes the file.

### Key Concepts

* **`open()`** — Opens a file for reading or other operations.
* **`"r"` mode** — Opens a file for reading.
* **`read()`** — Reads the entire file content.
* **`readline()`** — Reads one line at a time.
* **`readlines()`** — Reads all lines and returns them as a list.
* **`with open()`** — Safely opens and automatically closes a file.
* **File paths** — Specify where the file is located.
* **Encoding** — Controls how text is decoded when reading a file.

[View more details →](./Python_Detaild/reading_files.md)

---


## Writing Files

**Writing files** in Python means creating a new file or adding/modifying content in an existing file. Python uses the `open()` function with different modes such as `"w"`, `"a"`, and `"x"`.

```python
with open("example.txt", "w", encoding="utf-8") as file:
    file.write("Hello Python!")
```

### Key Concepts

* **`"w"` mode** — Writes to a file and replaces existing content.
* **`"a"` mode** — Adds content to the end of an existing file.
* **`"x"` mode** — Creates a new file and fails if it already exists.
* **`write()`** — Writes a string to a file.
* **`writelines()`** — Writes multiple strings to a file.
* **`with open()`** — Safely opens and automatically closes the file.
* **Newline `\n`** — Used to write content on separate lines.
* **Encoding** — Controls how text is encoded when writing.

[View more details →](./Python_Detaild/writing_files.md)

---


## CSV Files

**CSV (Comma-Separated Values)** is a simple text-based format used to store tabular data, such as names, marks, products, or employee records. Python provides the built-in `csv` module for reading and writing CSV files.

```python id="4v7j2p"
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.reader(file)

    for row in reader:
        print(row)
```

### Key Concepts

* **CSV format** — Stores data in rows and columns.
* **`csv` module** — Python's built-in module for working with CSV files.
* **`csv.reader()`** — Reads CSV data row by row.
* **`csv.writer()`** — Writes rows to a CSV file.
* **`csv.DictReader()`** — Reads CSV rows as dictionaries using column names.
* **`csv.DictWriter()`** — Writes dictionaries as CSV rows.
* **Header row** — Contains column names such as `name`, `age`, and `mark`.
* **Delimiter** — Separates values, usually a comma `,`.

[View more details →](./Python_Detaild/csv_files.md)

---


## JSON Files

**JSON (JavaScript Object Notation)** is a lightweight text-based format used to store and exchange structured data. It is commonly used for configuration files, APIs, web applications, and data storage.

Python provides the built-in `json` module for working with JSON files.

```python
import json

with open("student.json", "r", encoding="utf-8") as file:
    data = json.load(file)

print(data)
```

### Key Concepts

* **JSON format** — Stores structured data using objects and arrays.
* **`json` module** — Python's built-in module for working with JSON data.
* **`json.load()`** — Reads JSON data from a file and converts it into Python data.
* **`json.dump()`** — Writes Python data into a JSON file.
* **`json.loads()`** — Converts a JSON string into Python data.
* **`json.dumps()`** — Converts Python data into a JSON string.
* **JSON object** — Represents key-value data using `{}`.
* **JSON array** — Represents a collection of values using `[]`.
* **JSON values** — Can contain strings, numbers, booleans, `null`, objects, and arrays.

[View more details →](./Python_Detaild/json_files.md)

---


## Processing Structured Data

**Structured data** is information organized in a predictable format, such as rows and columns, key-value pairs, lists, or nested objects. Python provides data structures and tools that make it easy to read, access, modify, filter, and process this kind of data.

```python
students = [
    {"name": "Riyas", "mark": 90},
    {"name": "Arun", "mark": 85},
    {"name": "Rahul", "mark": 92}
]

for student in students:
    if student["mark"] >= 90:
        print(student["name"])
```

### Key Concepts

* **Structured data** — Data organized in a consistent and predictable format.
* **Dictionaries** — Store data as key-value pairs.
* **Lists** — Store multiple values or records.
* **Nested data** — Data structures can contain other lists and dictionaries.
* **Accessing data** — Retrieve specific values using keys and indexes.
* **Iterating data** — Process multiple records using loops.
* **Filtering** — Select records that satisfy a condition.
* **Updating data** — Modify existing values.
* **Sorting data** — Arrange records based on a specific value.
* **JSON and CSV** — Common file formats for structured data.
* **Data transformation** — Convert data from one structure or format into another.

[View more details →](./Python_Detaild/processing_structured_data.md)

