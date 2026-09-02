[◀ Back](.././)

---

# 3. Understand Collections
* **What are Lists?**<br>
  A **list** is an ordered, changeable (mutable) collection of items that allows duplicate values and uses brackets `[]`.

  <details>
  <summary>Click for more</summary>
  
  1. **Syntax:** Created using square brackets (e.g., `fruits = ["apple", "banana", "apple"]`).
  2. **Characteristics:** Items preserve their insertion order and can be modified or updated after creation.
  3. **Access:** Individual elements are accessed using zero-based indexing (e.g., `fruits[0]` gets the first item).
  
  </details>

* **What are Tuples?**<br>
  A **tuple** is an ordered, unchangeable (immutable) collection of items that allows duplicate values and uses parentheses `()`.

  <details>
  <summary>Click for more</summary>
  
  1. **Syntax:** Created using rounded parentheses (e.g., `coordinates = (10, 20)`).
  2. **Characteristics:** Once defined, its elements cannot be added, removed, or altered, making it highly memory-efficient and secure.
  3. **Use Case:** Perfect for storing fixed data that should never change throughout a program (like GPS coordinates).
  
  </details>

* **What are Sets?**<br>
  A **set** is an unordered, unindexed collection of unique elements that does not allow duplicate values and uses braces `{}`.

  <details>
  <summary>Click for more</summary>
  
  1. **Syntax:** Created using curly braces (e.g., `unique_nums = {1, 2, 3}`).
  2. **Characteristics:** Automatically strips out any duplicate values and does not track the order of entry.
  3. **Operations:** Optimized for ultra-fast item lookups and mathematical operations like unions or intersections.
  
  </details>

* **What are Dictionaries?**<br>
  A **dictionary** is an ordered (as of Python 3.7+) collection of key-value pairs where keys must be completely unique.

  <details>
  <summary>Click for more</summary>
  
  1. **Syntax:** Created using curly braces with colons separating keys and values (e.g., `user = {"id": 101, "role": "admin"}`).
  2. **Characteristics:** Values are instantly retrieved by looking up their mapped key rather than an index number.
  3. **Key Constraint:** Keys must be of an unchangeable data type (like strings or tuples), but values can be anything.
  
  </details>

* **What is Collection Manipulation?**<br>
  **Collection manipulation** refers to the built-in methods and techniques used to modify, slice, or extract data from these data structures.

  <details>
  <summary>Click for more</summary>
  
  1. **Adding Data:** Use `.append()` for lists, `.add()` for sets, and key assignment or `.update()` for dictionaries.
  2. **Removing Data:** Methods like `.pop()` or `.remove()` cleanly eliminate target elements from lists, sets, or dictionaries.
  3. **Slicing & Loops:** Slicing syntax `[start:stop]` extracts ranges from lists/tuples, while `for` loops traverse keys or values.
  
  </details>

---

[◀ Back](.././)