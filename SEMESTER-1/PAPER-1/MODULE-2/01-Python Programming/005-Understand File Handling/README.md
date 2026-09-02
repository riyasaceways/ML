[◀ Back](.././)

---

# 5. Understand File Handling

* **What is Reading Files?**<br>
  **Reading files** is the process of opening an externally stored text or binary file to retrieve its data and load it into your program's active memory.

  <details>
  <summary>Click for more</summary>
  
  1. **Syntax:** Handled by opening a file in read mode `open("filename.txt", "r")`.
  2. **Context Managers:** It is best practice to use the `with` keyword (e.g., `with open(...) as file:`), which safely and automatically closes the file when done.
  3. **Read Methods:** Built-in options include `.read()` to pull the whole file as one single string, `.readline()` for a single line, and `.readlines()` to get a list of lines.
  
  </details>

* **What is Writing Files?**<br>
  **Writing files** is the process of sending text or raw data out of your program to be permanently saved inside a file on your disk storage.

  <details>
  <summary>Click for more</summary>
  
  1. **Modes:** Opening with `"w"` (write) mode creates a new file or completely wipes out an existing file; `"a"` (append) mode adds text safely onto the end without erasing data.
  2. **Methods:** Use `.write("text")` to export a clean string of characters, or `.writelines(list)` to dump a full collection of strings sequentially.
  3. **Data Control:** Unlike the `print()` function, the `.write()` method does not append a fresh newline character automatically; you must add `\n` manually.
  
  </details>

* **What are CSV Files?**<br>
  A **CSV (Comma-Separated Values) file** is a plain-text file format used to store structured tabular data, where each line represents a row and columns are separated by commas.

  <details>
  <summary>Click for more</summary>
  
  1. **The Module:** Python uses its native built-in `import csv` library to safely parse and build tabular documents.
  2. **Reading Data:** Transformed into a readable format using `csv.reader(file)`, which allows you to loop through rows as clean Python lists.
  3. **Writing Data:** Managed using a `csv.writer(file)` object, using `.writerow()` for a individual line or `.writerows()` for multi-row datasets.
  
  </details>

* **What are JSON Files?**<br>
  A **JSON (JavaScript Object Notation) file** is a lightweight, human-readable data format structured around nested key-value pairs and ordered lists.

  <details>
  <summary>Click for more</summary>
  
  1. **The Module:** Handled natively using `import json`, which converts file data back and forth between raw text and Python objects.
  2. **Parsing (Reading):** The `json.load(file)` method reads a JSON text file and instantly maps it into a matching Python dictionary or list.
  3. **Serialization (Writing):** The `json.dump(data, file)` function takes a Python dictionary and encodes it cleanly into structured text format on disk.
  
  </details>

* **What is Processing Structured Data?**<br>
  **Processing structured data** refers to reading organized external records (like CSV or JSON), then cleaning, updating, or analyzing them within your software application.

  <details>
  <summary>Click for more</summary>
  
  1. **Data Conversion:** Turning text values pulled from rows into operational data types (such as wrapping a read string inside `int()` or `float()`).
  2. **Filtering & Aggregating:** Looping over retrieved records to find specific information matching conditions or summing numerical data fields.
  3. **Advanced Scaling:** For large-scale data manipulation, developers transition from basic file loops to high-powered libraries like [Pandas](https://pydata.org "Pandas Documentation") for processing DataFrames.
  
  </details>

---

[◀ Back](.././)