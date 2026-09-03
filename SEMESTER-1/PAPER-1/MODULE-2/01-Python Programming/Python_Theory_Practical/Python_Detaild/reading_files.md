[◀Back](.././)
---

# Reading Files

## What is File Reading?

**File reading** means opening an existing file and retrieving the data stored inside it.

Python provides the built-in `open()` function for working with files.

For example, suppose `example.txt` contains:

```text
Hello Python
This is a text file.
```

We can read it using:

```python
file = open("example.txt", "r")

content = file.read()

print(content)

file.close()
```

Output:

```text
Hello Python
This is a text file.
```

---

# The `open()` Function

The basic syntax is:

```python
open(file, mode)
```

Example:

```python
file = open("example.txt", "r")
```

Here:

* `"example.txt"` is the file name.
* `"r"` means **read mode**.
* `file` stores the file object.

---

# Reading Mode: `"r"`

The `"r"` mode is used to read an existing file.

```python
file = open("example.txt", "r")
```

If the file does not exist, Python raises a `FileNotFoundError`.

```python
file = open("missing.txt", "r")
```

Possible error:

```text
FileNotFoundError
```

---

# Using `with open()`

The recommended way to read files is:

```python
with open("example.txt", "r") as file:
    content = file.read()

print(content)
```

The `with` statement automatically closes the file after the block finishes.

This is safer and cleaner than manually calling:

```python
file.close()
```

---

# Why Use `with`?

Consider:

```python
file = open("example.txt", "r")

content = file.read()

file.close()
```

You have to remember to close the file.

With `with`:

```python
with open("example.txt", "r") as file:
    content = file.read()
```

Python automatically handles closing the file.

Therefore, prefer:

```python
with open(...) as file:
```

for normal file operations.

---

# `read()`

The `read()` method reads the file's content.

```python
with open("example.txt", "r") as file:
    content = file.read()

print(content)
```

If the file contains:

```text
Hello
Python
```

the result is one string:

```python
"Hello\nPython"
```

---

## Reading a Specific Number of Characters

`read()` can accept a number specifying how many characters to read.

```python
with open("example.txt", "r") as file:
    content = file.read(5)

print(content)
```

If the file contains:

```text
Hello Python
```

Output:

```text
Hello
```

The next `read()` continues from the current file position.

```python
with open("example.txt", "r") as file:
    print(file.read(5))
    print(file.read(6))
```

Output:

```text
Hello
 Pytho
```

The exact result depends on the characters and positions in the file.

---

# `readline()`

The `readline()` method reads one line at a time.

Suppose `example.txt` contains:

```text
Line 1
Line 2
Line 3
```

You can write:

```python
with open("example.txt", "r") as file:
    line = file.readline()

print(line)
```

Output:

```text
Line 1
```

Calling it again reads the next line:

```python
with open("example.txt", "r") as file:
    print(file.readline())
    print(file.readline())
```

Output:

```text
Line 1

Line 2
```

---

# `readlines()`

`readlines()` reads all lines and returns them as a list.

```python
with open("example.txt", "r") as file:
    lines = file.readlines()

print(lines)
```

For:

```text
Line 1
Line 2
Line 3
```

the result is approximately:

```python
["Line 1\n", "Line 2\n", "Line 3\n"]
```

The `\n` represents the newline character.

---

# Reading a File Line by Line

You can directly iterate over the file object.

```python
with open("example.txt", "r") as file:
    for line in file:
        print(line)
```

This is often preferable for large files because Python can process the file incrementally instead of loading the entire file into memory at once.

---

# Removing the Newline

When reading lines, the newline character may be included.

```python
with open("example.txt", "r") as file:
    for line in file:
        print(line.strip())
```

If the file contains:

```text
Python
Java
C++
```

Output:

```text
Python
Java
C++
```

`strip()` removes whitespace from the beginning and end of the string, including the newline.

If you only want to remove the line ending while preserving other surrounding spaces, `rstrip("\r\n")` can be more precise.

---

# Reading With `for`

A file object is iterable.

```python
with open("example.txt", "r") as file:
    for line in file:
        print(line.strip())
```

This reads the file one line at a time.

It is useful when processing large text files.

---

# Reading an Empty File

If the file is empty:

```python
with open("empty.txt", "r") as file:
    content = file.read()

print(content)
```

`content` will be:

```python
""
```

An empty string means that no characters were read.

---

# Checking Whether a File Exists

You can use `pathlib` to check whether a file exists.

```python
from pathlib import Path

file_path = Path("example.txt")

if file_path.exists():
    print("File exists")
else:
    print("File does not exist")
```

Output depends on whether the file exists.

This can be useful before attempting to read a file.

---

# Handling `FileNotFoundError`

A file may not exist at the specified path.

```python
try:
    with open("example.txt", "r") as file:
        content = file.read()

    print(content)

except FileNotFoundError:
    print("File not found")
```

This prevents the program from terminating unexpectedly when the file is missing.

---

# File Paths

You can provide a relative or absolute path.

### Relative path

```python
with open("example.txt", "r") as file:
    content = file.read()
```

Python looks for the file relative to the program's current working directory.

### File inside a folder

```python
with open("data/example.txt", "r") as file:
    content = file.read()
```

### Absolute path

```python
with open("C:/Users/Riyas/Documents/example.txt", "r") as file:
    content = file.read()
```

On Windows, using `/` in paths is often convenient in Python.

You can also use a raw string:

```python
with open(r"C:\Users\Riyas\Documents\example.txt", "r") as file:
    content = file.read()
```

---

# Encoding

Text files are stored as bytes, so Python needs to know how those bytes should be decoded into text.

You can specify an encoding:

```python
with open("example.txt", "r", encoding="utf-8") as file:
    content = file.read()
```

`UTF-8` is a common choice for text files.

This is particularly important when files contain characters beyond basic English letters.

Example:

```text
Hello
ഹലോ
你好
```

Using the appropriate encoding helps Python read such text correctly.

---

# Reading Text and Numbers

When reading a text file, Python returns strings.

Suppose `numbers.txt` contains:

```text
10
20
30
```

Reading it:

```python
with open("numbers.txt", "r") as file:
    content = file.read()

print(content)
print(type(content))
```

Output:

```text
10
20
30
<class 'str'>
```

The file contents are text.

If you need numbers, you must convert them.

For example:

```python
with open("numbers.txt", "r") as file:
    numbers = [int(line.strip()) for line in file]

print(numbers)
```

Output:

```text
[10, 20, 30]
```

---

# Reading a File Into a List

You can create a list of lines:

```python
with open("names.txt", "r") as file:
    names = [line.strip() for line in file]

print(names)
```

If the file contains:

```text
Riyas
Alex
John
```

Output:

```text
['Riyas', 'Alex', 'John']
```

---

# Reading and Searching

You can search for specific text while reading a file.

```python
with open("example.txt", "r") as file:
    for line in file:
        if "Python" in line:
            print(line.strip())
```

This prints only lines containing `"Python"`.

---

# Counting Lines

You can count the lines in a file:

```python
count = 0

with open("example.txt", "r") as file:
    for line in file:
        count += 1

print("Number of lines:", count)
```

A more compact approach is:

```python
with open("example.txt", "r") as file:
    count = sum(1 for _ in file)

print(count)
```

---

# Reading Large Files

For a small file, this is convenient:

```python
with open("example.txt", "r") as file:
    content = file.read()
```

However, if a file is very large, reading the entire file at once can consume significant memory.

Instead:

```python
with open("large_file.txt", "r") as file:
    for line in file:
        process = line.strip()
        print(process)
```

This processes the file line by line.

---

# File Object

When you write:

```python
file = open("example.txt", "r")
```

`file` is not the actual text content.

It is a **file object** that provides methods and information for working with the file.

For example:

```python
with open("example.txt", "r") as file:
    print(type(file))
```

The type will be a text file object.

Methods such as:

```python
file.read()
file.readline()
file.readlines()
file.close()
```

operate on that file object.

---

# File Position

A file object keeps track of its current position.

Example:

```python
with open("example.txt", "r") as file:
    print(file.read(5))
    print(file.read(5))
```

The second `read(5)` starts from where the first read stopped.

You can inspect the current position using `tell()`:

```python
with open("example.txt", "r") as file:
    print(file.tell())
    print(file.read(5))
    print(file.tell())
```

The position changes as data is read.

---

# `seek()`

The `seek()` method moves the file position.

```python
with open("example.txt", "r") as file:
    print(file.read(5))

    file.seek(0)

    print(file.read(5))
```

Output:

```text
Hello
Hello
```

`seek(0)` moves the position back to the beginning.

---

# `read()` vs `readline()` vs `readlines()`

| Method        | Result                                 |
| ------------- | -------------------------------------- |
| `read()`      | Reads the entire file as a string      |
| `read(size)`  | Reads a specified number of characters |
| `readline()`  | Reads one line                         |
| `readlines()` | Reads all lines into a list            |

Example:

```python
with open("example.txt", "r") as file:
    content = file.read()
```

```python
with open("example.txt", "r") as file:
    line = file.readline()
```

```python
with open("example.txt", "r") as file:
    lines = file.readlines()
```

---

# Reading With `pathlib`

Python's `pathlib` provides an object-oriented way to work with file paths.

```python
from pathlib import Path

file_path = Path("example.txt")

content = file_path.read_text(encoding="utf-8")

print(content)
```

This can be convenient for simple text-file reading.

---

# Practical Example: Reading Student Names

Suppose `students.txt` contains:

```text
Riyas
Alex
John
Anu
```

Python:

```python
with open("students.txt", "r", encoding="utf-8") as file:
    for name in file:
        print(f"Student: {name.strip()}")
```

Output:

```text
Student: Riyas
Student: Alex
Student: John
Student: Anu
```

---

# Practical Example: Reading Marks

Suppose `marks.txt` contains:

```text
80
75
90
65
```

Python:

```python
with open("marks.txt", "r", encoding="utf-8") as file:
    marks = [int(line.strip()) for line in file]

average = sum(marks) / len(marks)

print("Marks:", marks)
print("Average:", average)
```

Output:

```text
Marks: [80, 75, 90, 65]
Average: 77.5
```

---

# Practical Example: Reading a Configuration File

Suppose:

```text
username=riyas
language=python
level=beginner
```

You could read the lines:

```python
with open("config.txt", "r", encoding="utf-8") as file:
    for line in file:
        key, value = line.strip().split("=")
        print(key, "=", value)
```

Output:

```text
username = riyas
language = python
level = beginner
```

This demonstrates how file reading can be combined with string processing.

---

# File Reading Workflow

A typical file-reading workflow is:

```text
File
 ↓
open()
 ↓
Read
 ↓
Process
 ↓
Close
```

With `with`:

```text
File
 ↓
with open()
 ↓
Read
 ↓
Process
 ↓
Automatically closed
```

Example:

```python
with open("example.txt", "r", encoding="utf-8") as file:
    content = file.read()

print(content)
```

---

# Common Mistakes

## 1. Forgetting to Close the File

Less preferred:

```python
file = open("example.txt", "r")
content = file.read()
```

The file is left open until it is closed.

Better:

```python
with open("example.txt", "r") as file:
    content = file.read()
```

---

## 2. Using the Wrong File Path

```python
with open("example.txt", "r") as file:
    ...
```

If the file is actually inside `data/`, use:

```python
with open("data/example.txt", "r") as file:
    ...
```

---

## 3. Assuming File Contents Are Numbers

```python
with open("numbers.txt", "r") as file:
    value = file.read()

print(value + 10)
```

This fails because `value` is a string.

Convert it when appropriate:

```python
value = int(value)
```

For multiple lines:

```python
with open("numbers.txt", "r") as file:
    numbers = [int(line.strip()) for line in file]
```

---

## 4. Forgetting Newline Characters

Using:

```python
for line in file:
    print(line)
```

can produce extra blank lines because `line` may already contain `\n`.

Use:

```python
for line in file:
    print(line.strip())
```

when removing surrounding whitespace is appropriate.

---

## 5. Reading a Huge File With `read()`

This:

```python
content = file.read()
```

loads the entire file into memory.

For large files, consider:

```python
for line in file:
    ...
```

---

# Quick Reference

```python
# Read entire file
with open("file.txt", "r", encoding="utf-8") as file:
    content = file.read()
```

```python
# Read one line
with open("file.txt", "r", encoding="utf-8") as file:
    line = file.readline()
```

```python
# Read all lines as a list
with open("file.txt", "r", encoding="utf-8") as file:
    lines = file.readlines()
```

```python
# Read line by line
with open("file.txt", "r", encoding="utf-8") as file:
    for line in file:
        print(line.strip())
```

```python
# Read a specific number of characters
with open("file.txt", "r", encoding="utf-8") as file:
    content = file.read(10)
```

```python
# Move to the beginning
with open("file.txt", "r", encoding="utf-8") as file:
    file.seek(0)
```

---

# Key Points

* `open()` is used to open a file.
* `"r"` means **read mode**.
* `read()` reads file content as a string.
* `readline()` reads one line.
* `readlines()` returns all lines as a list.
* A file can be iterated over line by line.
* `with open()` is the recommended way to work with files because it automatically closes the file.
* File contents are read as text when using text mode.
* Numeric text must be converted to numbers before numerical operations.
* `encoding="utf-8"` is commonly used when reading text files.
* `seek()` changes the current file position.
* `tell()` reports the current file position.
* Large files are often better processed incrementally rather than loaded completely with `read()`.

---

# Interview Questions

### 1. How do you open a file for reading in Python?

```python
file = open("example.txt", "r")
```

### 2. What does `"r"` mean in `open()`?

`"r"` means **read mode**.

### 3. What is the recommended way to open a file?

Use a `with` statement:

```python
with open("example.txt", "r") as file:
    content = file.read()
```

### 4. What is the difference between `read()`, `readline()`, and `readlines()`?

* `read()` → reads the file content as a string.
* `readline()` → reads one line.
* `readlines()` → reads all lines into a list.

### 5. Why is `with open()` preferred?

It automatically closes the file after the block finishes, even when an exception occurs during the operation.

### 6. What happens if the file does not exist?

Reading it normally raises a `FileNotFoundError`.

### 7. How can you read a file line by line?

```python
with open("example.txt", "r") as file:
    for line in file:
        print(line)
```

### 8. What type of data does `read()` return for a text file?

It returns a `str`.

### 9. How do you specify UTF-8 encoding?

```python
with open("example.txt", "r", encoding="utf-8") as file:
    content = file.read()
```

### 10. How do you read only the first 10 characters?

```python
with open("example.txt", "r") as file:
    content = file.read(10)
```

### 11. What does `seek()` do?

`seek()` changes the current position in the file.

### 12. What does `tell()` do?

`tell()` returns the current position in the file.

### 13. How should large text files be read efficiently?

They can often be processed incrementally, for example:

```python
with open("large_file.txt", "r") as file:
    for line in file:
        process(line)
```

This avoids loading the entire file into memory at once.


[◀Back](.././)
---