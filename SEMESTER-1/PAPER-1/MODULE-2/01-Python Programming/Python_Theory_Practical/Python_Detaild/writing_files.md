[◀Back](.././)
---

# Writing Files

## What is File Writing?

**Writing files** means storing data from a Python program into a file.

Python provides the `open()` function for creating and writing files.

For example:

```python
with open("example.txt", "w", encoding="utf-8") as file:
    file.write("Hello Python!")
```

This creates `example.txt` if it does not already exist and writes:

```text
Hello Python!
```

---

# Opening a File for Writing

The basic syntax is:

```python
open(file, mode)
```

For writing:

```python
file = open("example.txt", "w")
```

The `"w"` means **write mode**.

However, the recommended approach is:

```python
with open("example.txt", "w", encoding="utf-8") as file:
    file.write("Hello Python!")
```

The `with` statement automatically closes the file.

---

# File Writing Modes

Common modes include:

| Mode  | Purpose                                       |
| ----- | --------------------------------------------- |
| `"w"` | Write; creates or replaces the file           |
| `"a"` | Append; adds content to the end               |
| `"x"` | Create a new file; fails if it already exists |
| `"r"` | Read only                                     |

For writing files, the most important modes are:

```text
"w" → Write
"a" → Append
"x" → Create
```

---

# `"w"` Write Mode

The `"w"` mode is used to write content to a file.

```python
with open("example.txt", "w", encoding="utf-8") as file:
    file.write("Hello Python!")
```

If the file does not exist, Python creates it.

If the file already exists, its existing content is **replaced**.

---

## Important: `"w"` Overwrites Existing Content

Suppose `example.txt` contains:

```text
Hello
Welcome to Python
```

Now:

```python
with open("example.txt", "w", encoding="utf-8") as file:
    file.write("New content")
```

The file now contains:

```text
New content
```

The previous content has been replaced.

Therefore, be careful when using `"w"` with an existing file.

---

# `"a"` Append Mode

The `"a"` mode adds new content to the end of the file.

Suppose `example.txt` contains:

```text
Hello
```

Then:

```python
with open("example.txt", "a", encoding="utf-8") as file:
    file.write("Python")
```

The file becomes:

```text
HelloPython
```

If you want the new content on a separate line:

```python
with open("example.txt", "a", encoding="utf-8") as file:
    file.write("\nPython")
```

The file becomes:

```text
Hello
Python
```

---

# `"x"` Create Mode

The `"x"` mode is used to create a new file.

```python
with open("new_file.txt", "x", encoding="utf-8") as file:
    file.write("New file created.")
```

If `new_file.txt` does not exist, it is created.

If it already exists, Python raises:

```text
FileExistsError
```

This is useful when you specifically want to ensure that an existing file is not accidentally overwritten.

---

# The `write()` Method

The `write()` method writes a string to the file.

```python
with open("example.txt", "w", encoding="utf-8") as file:
    file.write("Hello Python")
```

`write()` expects a string in text mode.

For example:

```python
file.write("Hello")
```

works.

But:

```python
file.write(100)
```

does not work in text mode because `100` is an integer.

Convert it when necessary:

```python
file.write(str(100))
```

---

# Writing Multiple Lines

You can use the newline character `\n`.

```python
with open("example.txt", "w", encoding="utf-8") as file:
    file.write("Line 1\n")
    file.write("Line 2\n")
    file.write("Line 3\n")
```

The file contains:

```text
Line 1
Line 2
Line 3
```

---

# Writing a String With Multiple Lines

You can also write one string containing multiple newline characters:

```python
content = "Line 1\nLine 2\nLine 3\n"

with open("example.txt", "w", encoding="utf-8") as file:
    file.write(content)
```

---

# The `writelines()` Method

`writelines()` writes multiple strings to a file.

```python
lines = [
    "Line 1\n",
    "Line 2\n",
    "Line 3\n"
]

with open("example.txt", "w", encoding="utf-8") as file:
    file.writelines(lines)
```

The file contains:

```text
Line 1
Line 2
Line 3
```

### Important

`writelines()` does **not** automatically add newline characters.

This:

```python
lines = ["Line 1", "Line 2", "Line 3"]

with open("example.txt", "w", encoding="utf-8") as file:
    file.writelines(lines)
```

can produce:

```text
Line 1Line 2Line 3
```

If you want separate lines, include `\n`:

```python
lines = ["Line 1\n", "Line 2\n", "Line 3\n"]
```

---

# `write()` vs `writelines()`

| `write()`                           | `writelines()`                  |
| ----------------------------------- | ------------------------------- |
| Writes a string                     | Writes multiple strings         |
| Usually used for individual content | Useful for a sequence of lines  |
| Does not automatically add `\n`     | Does not automatically add `\n` |

Example:

```python
file.write("Hello\n")
```

vs:

```python
file.writelines(["Hello\n", "Python\n"])
```

---

# Using `with open()`

The recommended approach is:

```python
with open("example.txt", "w", encoding="utf-8") as file:
    file.write("Hello Python")
```

When the `with` block ends, Python automatically closes the file.

Without `with`:

```python
file = open("example.txt", "w", encoding="utf-8")

file.write("Hello Python")

file.close()
```

You have to remember to close the file manually.

---

# Why Should Files Be Closed?

When a file is opened, the operating system maintains resources associated with it.

Closing the file:

* Releases those resources.
* Ensures pending buffered data is flushed.
* Prevents unnecessary open file handles.

Using `with` handles this automatically.

---

# Writing User Input to a File

You can get input from the user and save it.

```python
name = input("Enter your name: ")

with open("name.txt", "w", encoding="utf-8") as file:
    file.write(name)
```

If the user enters:

```text
Riyas
```

the file contains:

```text
Riyas
```

---

# Writing Multiple User Inputs

```python
name = input("Enter your name: ")
age = input("Enter your age: ")

with open("student.txt", "w", encoding="utf-8") as file:
    file.write(f"Name: {name}\n")
    file.write(f"Age: {age}\n")
```

If the user enters:

```text
Riyas
20
```

the file contains:

```text
Name: Riyas
Age: 20
```

---

# Writing Numbers to a File

Text-mode file writing requires strings.

This will cause an error:

```python
age = 20

with open("age.txt", "w") as file:
    file.write(age)
```

Use `str()`:

```python
age = 20

with open("age.txt", "w") as file:
    file.write(str(age))
```

Or use an f-string:

```python
with open("age.txt", "w") as file:
    file.write(f"{age}")
```

---

# Writing Lists to a File

Suppose:

```python
names = ["Riyas", "Alex", "John"]
```

You can write each name on a separate line:

```python
with open("names.txt", "w", encoding="utf-8") as file:
    for name in names:
        file.write(name + "\n")
```

The file becomes:

```text
Riyas
Alex
John
```

---

# Writing a List With `writelines()`

You can also use:

```python
names = ["Riyas\n", "Alex\n", "John\n"]

with open("names.txt", "w", encoding="utf-8") as file:
    file.writelines(names)
```

---

# Adding Items to an Existing File

Use append mode when you want to preserve existing content.

```python
with open("names.txt", "a", encoding="utf-8") as file:
    file.write("Anu\n")
```

If the file previously contained:

```text
Riyas
Alex
John
```

it becomes:

```text
Riyas
Alex
John
Anu
```

---

# Writing Data From a Loop

Loops can be combined with file writing.

```python
with open("numbers.txt", "w", encoding="utf-8") as file:
    for number in range(1, 6):
        file.write(f"{number}\n")
```

The file contains:

```text
1
2
3
4
5
```

---

# Writing Conditional Results

You can write only the values that satisfy a condition.

```python
numbers = [10, 15, 20, 25, 30]

with open("even_numbers.txt", "w", encoding="utf-8") as file:
    for number in numbers:
        if number % 2 == 0:
            file.write(f"{number}\n")
```

The file contains:

```text
10
20
30
```

---

# Writing a Dictionary to a Text File

A dictionary can be formatted before writing.

```python
student = {
    "name": "Riyas",
    "age": 20,
    "course": "Python"
}

with open("student.txt", "w", encoding="utf-8") as file:
    for key, value in student.items():
        file.write(f"{key}: {value}\n")
```

The file contains:

```text
name: Riyas
age: 20
course: Python
```

---

# Writing With `pathlib`

`pathlib` can also be used to write text files.

```python
from pathlib import Path

file_path = Path("example.txt")

file_path.write_text("Hello Python!", encoding="utf-8")
```

This creates or replaces the file with the specified text.

For simple text-file operations, this can be convenient.

---

# File Encoding

When writing text, you can specify the encoding.

```python
with open("example.txt", "w", encoding="utf-8") as file:
    file.write("Hello Python")
```

UTF-8 supports a wide range of characters.

For example:

```python
with open("hello.txt", "w", encoding="utf-8") as file:
    file.write("Hello\nഹലോ\n你好")
```

The file can contain:

```text
Hello
ഹലോ
你好
```

---

# Overwriting vs Appending

This distinction is very important.

### `"w"`

```python
with open("example.txt", "w") as file:
    file.write("New data")
```

Existing content is replaced.

### `"a"`

```python
with open("example.txt", "a") as file:
    file.write("New data")
```

Existing content is preserved and new content is added at the end.

---

# Practical Example: Simple Notes App

```python
note = input("Enter your note: ")

with open("notes.txt", "a", encoding="utf-8") as file:
    file.write(note + "\n")

print("Note saved.")
```

Every time the program runs, the new note is added to the existing file.

---

# Practical Example: Student Record

```python
name = input("Enter name: ")
age = input("Enter age: ")
course = input("Enter course: ")

with open("students.txt", "a", encoding="utf-8") as file:
    file.write(f"Name: {name}\n")
    file.write(f"Age: {age}\n")
    file.write(f"Course: {course}\n")
    file.write("-" * 30 + "\n")
```

Example file:

```text
Name: Riyas
Age: 20
Course: Python
------------------------------
Name: Alex
Age: 21
Course: Java
------------------------------
```

---

# Practical Example: Log File

Append mode is commonly useful for logs.

```python
message = "User logged in"

with open("app.log", "a", encoding="utf-8") as file:
    file.write(message + "\n")
```

Each new message is added without deleting previous logs.

---

# Writing and Then Reading a File

You can write data and later read it.

```python
with open("example.txt", "w", encoding="utf-8") as file:
    file.write("Hello Python!")

with open("example.txt", "r", encoding="utf-8") as file:
    content = file.read()

print(content)
```

Output:

```text
Hello Python!
```

The file is opened separately for writing and reading.

---

# The `"w+"` Mode

`"w+"` opens a file for both writing and reading.

```python
with open("example.txt", "w+", encoding="utf-8") as file:
    file.write("Hello Python!")

    file.seek(0)

    content = file.read()

    print(content)
```

Output:

```text
Hello Python!
```

Remember that `"w+"` still **truncates the file when it is opened**.

---

# The `"a+"` Mode

`"a+"` opens a file for both appending and reading.

```python
with open("example.txt", "a+", encoding="utf-8") as file:
    file.write("New line\n")

    file.seek(0)

    content = file.read()

    print(content)
```

The existing content is preserved, and new content is appended.

Because the current file position after writing is at the end, `seek(0)` is used before reading the entire file.

---

# File Writing and Buffering

Python may buffer writes rather than sending every small write immediately to the underlying file.

Normally, you do not need to manage this yourself.

When the `with` block ends, the file is closed and pending data is flushed.

You can also explicitly use:

```python
file.flush()
```

when appropriate.

For normal programs, using:

```python
with open(...) as file:
```

is usually sufficient.

---

# Common Mistakes

## 1. Accidentally Overwriting a File

Using:

```python
open("data.txt", "w")
```

on an existing file replaces its contents.

If you want to add content instead, use:

```python
open("data.txt", "a")
```

---

## 2. Forgetting Newline Characters

This:

```python
with open("names.txt", "w") as file:
    file.write("Riyas")
    file.write("Alex")
```

produces:

```text
RiyasAlex
```

Use:

```python
file.write("Riyas\n")
file.write("Alex\n")
```

to produce:

```text
Riyas
Alex
```

---

## 3. Passing a Number Directly to `write()`

Incorrect:

```python
file.write(100)
```

Correct:

```python
file.write(str(100))
```

or:

```python
file.write(f"{100}")
```

---

## 4. Forgetting to Close the File

Avoid:

```python
file = open("example.txt", "w")
file.write("Hello")
```

Prefer:

```python
with open("example.txt", "w") as file:
    file.write("Hello")
```

---

## 5. Assuming `writelines()` Adds Newlines

It does not.

This:

```python
file.writelines(["A", "B", "C"])
```

does not automatically produce separate lines.

Use:

```python
file.writelines(["A\n", "B\n", "C\n"])
```

---

# Writing Files vs Reading Files

| Operation       | Common Mode              | Method               |
| --------------- | ------------------------ | -------------------- |
| Read            | `"r"`                    | `read()`             |
| Write/replace   | `"w"`                    | `write()`            |
| Append          | `"a"`                    | `write()`            |
| Create new file | `"x"`                    | `write()`            |
| Read + write    | `"r+"` / `"w+"` / `"a+"` | `read()` + `write()` |

---

# Quick Reference

### Write and replace

```python
with open("file.txt", "w", encoding="utf-8") as file:
    file.write("Hello")
```

### Append

```python
with open("file.txt", "a", encoding="utf-8") as file:
    file.write("\nNew content")
```

### Create only if it doesn't exist

```python
with open("file.txt", "x", encoding="utf-8") as file:
    file.write("New file")
```

### Write multiple lines

```python
lines = ["Line 1\n", "Line 2\n", "Line 3\n"]

with open("file.txt", "w", encoding="utf-8") as file:
    file.writelines(lines)
```

### Write a number

```python
number = 100

with open("file.txt", "w", encoding="utf-8") as file:
    file.write(str(number))
```

---

# Key Points

* `open()` is used to open files for writing.
* `"w"` writes to a file and replaces existing content.
* `"a"` adds content to the end of a file.
* `"x"` creates a new file and fails if the file already exists.
* `write()` writes a string.
* `writelines()` writes multiple strings.
* `writelines()` does not automatically add newline characters.
* Use `\n` to create separate lines.
* Use `with open()` so the file is automatically closed.
* Text-mode `write()` expects strings.
* Use `str()` or f-strings when writing numbers.
* `encoding="utf-8"` is commonly used for text files.
* Be especially careful with `"w"` because it can replace existing content.
* Large amounts of output can be written incrementally rather than building one huge string first.

---

# Interview Questions

### 1. How do you write to a file in Python?

```python
with open("example.txt", "w") as file:
    file.write("Hello Python")
```

### 2. What is the difference between `"w"` and `"a"`?

`"w"` writes from the beginning and replaces existing content, while `"a"` preserves existing content and adds new content at the end.

### 3. What does `"x"` mode do?

It creates a new file and raises `FileExistsError` if the file already exists.

### 4. What does the `write()` method do?

It writes a string to the file.

### 5. Does `write()` automatically add a newline?

No. You must explicitly add `\n` when needed.

### 6. What is `writelines()` used for?

It writes multiple strings from an iterable to a file.

### 7. Does `writelines()` automatically add newlines?

No.

### 8. Why is `with open()` preferred?

It automatically closes the file when the block finishes, helping ensure resources are released and buffered data is properly handled.

### 9. Can you write an integer directly using `write()`?

No. In text mode, convert it to a string first:

```python
file.write(str(100))
```

### 10. What happens when `"w"` is used on an existing file?

The existing file content is truncated and replaced by the new content.

### 11. How do you append content to a file?

Use `"a"` mode:

```python
with open("example.txt", "a") as file:
    file.write("New content")
```

### 12. What is the difference between `"w+"` and `"a+"`?

Both allow reading and writing.

* `"w+"` truncates the file when opened.
* `"a+"` preserves existing content and writes at the end.

### 13. How do you write multiple lines to a file?

```python
with open("example.txt", "w") as file:
    file.write("Line 1\n")
    file.write("Line 2\n")
```

### 14. Why is `"a"` useful for log files?

Because new entries can be added without deleting previous entries.

[◀Back](.././)
---