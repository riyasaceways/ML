[◀Back](.././)
---


# Collection-based Problems

Collection-based problems involve processing **multiple values stored together**.

Python provides several built-in collection types:

* `list`
* `tuple`
* `set`
* `dict`

These problems commonly require:

* Iteration
* Searching
* Counting
* Filtering
* Sorting
* Removing duplicates
* Comparing collections
* Combining collections
* Updating values
* Grouping data

---

# 1. Find the Largest Element

Given a collection of numbers, find the largest value.

```python
numbers = [10, 45, 23, 67, 12]

largest = numbers[0]

for number in numbers:
    if number > largest:
        largest = number

print(largest)
```

Output:

```text
67
```

Python also provides `max()`:

```python
print(max(numbers))
```

---

# 2. Find the Smallest Element

```python
numbers = [10, 45, 23, 67, 12]

smallest = numbers[0]

for number in numbers:
    if number < smallest:
        smallest = number

print(smallest)
```

Output:

```text
10
```

Using the built-in function:

```python
print(min(numbers))
```

---

# 3. Calculate the Sum

```python
numbers = [10, 20, 30, 40]

total = 0

for number in numbers:
    total += number

print(total)
```

Output:

```text
100
```

Python also provides:

```python
print(sum(numbers))
```

---

# 4. Calculate the Average

Average is calculated as:

```text
average = total / number_of_elements
```

Example:

```python
numbers = [10, 20, 30, 40]

total = sum(numbers)
average = total / len(numbers)

print(average)
```

Output:

```text
25.0
```

### Important

Always consider an empty collection:

```python
numbers = []

if numbers:
    average = sum(numbers) / len(numbers)
    print(average)
else:
    print("Collection is empty")
```

---

# 5. Count Elements

The `len()` function returns the number of elements.

```python
numbers = [10, 20, 30, 40]

print(len(numbers))
```

Output:

```text
4
```

---

# 6. Search for an Element

Use the `in` operator to check whether an element exists.

```python
numbers = [10, 20, 30, 40]

if 20 in numbers:
    print("Found")
else:
    print("Not found")
```

Output:

```text
Found
```

---

# 7. Count Occurrences

The `count()` method can count how many times an element appears in a list or tuple.

```python
numbers = [10, 20, 10, 30, 10]

print(numbers.count(10))
```

Output:

```text
3
```

---

# 8. Find Repeated Elements

To identify duplicate values:

```python
numbers = [10, 20, 10, 30, 20, 40]

duplicates = []

for number in numbers:
    if numbers.count(number) > 1 and number not in duplicates:
        duplicates.append(number)

print(duplicates)
```

Output:

```text
[10, 20]
```

For larger collections, a frequency dictionary or `collections.Counter` is usually more efficient.

---

# 9. Remove Duplicates

A `set` can be used to remove duplicate values.

```python
numbers = [10, 20, 10, 30, 20, 40]

unique_numbers = list(set(numbers))

print(unique_numbers)
```

The resulting order should not be relied upon.

If the original order must be preserved:

```python
numbers = [10, 20, 10, 30, 20, 40]

unique_numbers = []

for number in numbers:
    if number not in unique_numbers:
        unique_numbers.append(number)

print(unique_numbers)
```

Output:

```text
[10, 20, 30, 40]
```

---

# 10. Find Unique Elements

A unique element is a value that appears only once.

```python
numbers = [10, 20, 10, 30, 20, 40]

for number in numbers:
    if numbers.count(number) == 1:
        print(number)
```

Output:

```text
30
40
```

---

# 11. Sort a Collection

### Ascending order

```python
numbers = [40, 10, 30, 20]

numbers.sort()

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

### Descending order

```python
numbers.sort(reverse=True)

print(numbers)
```

Output:

```text
[40, 30, 20, 10]
```

---

# 12. `sort()` vs `sorted()`

`sort()` modifies the existing list:

```python
numbers = [30, 10, 20]

numbers.sort()

print(numbers)
```

`sorted()` creates a new sorted list:

```python
numbers = [30, 10, 20]

new_numbers = sorted(numbers)

print(new_numbers)
```

The original list remains unchanged when using `sorted()`.

---

# 13. Reverse a Collection

```python
numbers = [10, 20, 30, 40]

numbers.reverse()

print(numbers)
```

Output:

```text
[40, 30, 20, 10]
```

Another approach:

```python
numbers = [10, 20, 30, 40]

reversed_numbers = numbers[::-1]

print(reversed_numbers)
```

---

# 14. Filter Elements

Filtering means selecting elements that satisfy a condition.

Example: find numbers greater than `20`.

```python
numbers = [10, 25, 15, 40, 30]

result = []

for number in numbers:
    if number > 20:
        result.append(number)

print(result)
```

Output:

```text
[25, 40, 30]
```

---

# 15. Separate Even and Odd Numbers

```python
numbers = [1, 2, 3, 4, 5, 6]

even = []
odd = []

for number in numbers:
    if number % 2 == 0:
        even.append(number)
    else:
        odd.append(number)

print("Even:", even)
print("Odd:", odd)
```

Output:

```text
Even: [2, 4, 6]
Odd: [1, 3, 5]
```

---

# 16. Find Common Elements

Given two lists:

```python
list1 = [1, 2, 3, 4]
list2 = [3, 4, 5, 6]

common = []

for item in list1:
    if item in list2:
        common.append(item)

print(common)
```

Output:

```text
[3, 4]
```

Using sets:

```python
common = set(list1) & set(list2)

print(common)
```

---

# 17. Find Elements Present Only in One Collection

```python
list1 = [1, 2, 3, 4]
list2 = [3, 4, 5, 6]

result = []

for item in list1:
    if item not in list2:
        result.append(item)

print(result)
```

Output:

```text
[1, 2]
```

---

# 18. Merge Two Collections

```python
list1 = [1, 2, 3]
list2 = [4, 5, 6]

merged = list1 + list2

print(merged)
```

Output:

```text
[1, 2, 3, 4, 5, 6]
```

---

# 19. Merge and Remove Duplicates

```python
list1 = [1, 2, 3]
list2 = [3, 4, 5]

merged = list1 + list2
unique = list(set(merged))

print(unique)
```

If order matters, use an order-preserving approach instead.

---

# 20. Find the Second Largest Element

One approach is to remove duplicates and sort:

```python
numbers = [10, 40, 20, 40, 30]

unique_numbers = list(set(numbers))
unique_numbers.sort()

print(unique_numbers[-2])
```

Output:

```text
30
```

This assumes at least two distinct values exist.

---

# 21. Find the Second Smallest Element

```python
numbers = [10, 40, 20, 40, 30]

unique_numbers = list(set(numbers))
unique_numbers.sort()

print(unique_numbers[1])
```

Output:

```text
20
```

---

# 22. Frequency of Elements

Frequency means the number of times each value occurs.

```python
numbers = [1, 2, 2, 3, 1, 2]

frequency = {}

for number in numbers:
    if number in frequency:
        frequency[number] += 1
    else:
        frequency[number] = 1

print(frequency)
```

Output:

```text
{1: 2, 2: 3, 3: 1}
```

This is a very common collection-based problem.

---

# 23. Using `dict.get()` for Frequency Counting

The previous example can be simplified:

```python
numbers = [1, 2, 2, 3, 1, 2]

frequency = {}

for number in numbers:
    frequency[number] = frequency.get(number, 0) + 1

print(frequency)
```

---

# 24. Using `Counter`

Python's `collections` module provides `Counter` for frequency counting.

```python
from collections import Counter

numbers = [1, 2, 2, 3, 1, 2]

frequency = Counter(numbers)

print(frequency)
```

Output:

```text
Counter({2: 3, 1: 2, 3: 1})
```

---

# 25. Find the Most Frequent Element

```python
from collections import Counter

numbers = [1, 2, 2, 3, 1, 2]

frequency = Counter(numbers)

most_common = frequency.most_common(1)

print(most_common)
```

Output:

```text
[(2, 3)]
```

---

# 26. List Comprehension

Collection-based problems can often be solved using list comprehensions.

Example:

```python
numbers = [1, 2, 3, 4, 5, 6]

even = [number for number in numbers if number % 2 == 0]

print(even)
```

Output:

```text
[2, 4, 6]
```

The equivalent normal loop is:

```python
even = []

for number in numbers:
    if number % 2 == 0:
        even.append(number)
```

---

# 27. Transform Collection Elements

Suppose we want to square every number.

```python
numbers = [1, 2, 3, 4]

squares = []

for number in numbers:
    squares.append(number ** 2)

print(squares)
```

Using list comprehension:

```python
squares = [number ** 2 for number in numbers]

print(squares)
```

Output:

```text
[1, 4, 9, 16]
```

---

# 28. Find Strings by Length

Collection-based problems are not limited to numbers.

```python
names = ["Ali", "Riyas", "John", "Alex"]

for name in names:
    if len(name) > 4:
        print(name)
```

Output:

```text
Riyas
```

---

# 29. Find the Longest String

```python
names = ["Ali", "Riyas", "Alexander", "John"]

longest = max(names, key=len)

print(longest)
```

Output:

```text
Alexander
```

---

# 30. Find the Shortest String

```python
names = ["Ali", "Riyas", "Alexander", "John"]

shortest = min(names, key=len)

print(shortest)
```

Output:

```text
Ali
```

---

# 31. Dictionary-based Problems

Dictionaries store data using **key-value pairs**.

Example:

```python
student = {
    "name": "Riyas",
    "age": 20,
    "mark": 85
}
```

Access a value:

```python
print(student["name"])
```

Output:

```text
Riyas
```

---

# 32. Find Students Above a Mark

```python
students = {
    "Ali": 75,
    "Riyas": 90,
    "John": 65
}

for name, mark in students.items():
    if mark >= 80:
        print(name)
```

Output:

```text
Riyas
```

---

# 33. Find the Student with the Highest Mark

```python
students = {
    "Ali": 75,
    "Riyas": 90,
    "John": 65
}

highest = max(students, key=students.get)

print(highest)
```

Output:

```text
Riyas
```

To get both name and mark:

```python
highest = max(students.items(), key=lambda item: item[1])

print(highest)
```

Output:

```text
('Riyas', 90)
```

---

# 34. Group Data Using a Dictionary

Suppose we have students and their departments:

```python
students = [
    ("Ali", "Python"),
    ("Riyas", "Python"),
    ("John", "Java"),
    ("Alex", "Java")
]
```

We can group them:

```python
groups = {}

for name, course in students:
    if course not in groups:
        groups[course] = []

    groups[course].append(name)

print(groups)
```

Output:

```text
{
    "Python": ["Ali", "Riyas"],
    "Java": ["John", "Alex"]
}
```

This is a common real-world collection problem.

---

# 35. Nested Collections

Collections can contain other collections.

Example:

```python
students = [
    ["Ali", 80],
    ["Riyas", 90],
    ["John", 75]
]
```

Accessing data:

```python
for student in students:
    print(student[0], student[1])
```

Output:

```text
Ali 80
Riyas 90
John 75
```

---

# 36. Processing a Matrix

A matrix can be represented using nested lists.

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
```

Print every value:

```python
for row in matrix:
    for value in row:
        print(value)
```

Output:

```text
1
2
3
4
5
6
7
8
9
```

---

# 37. Sum of Matrix Elements

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6]
]

total = 0

for row in matrix:
    for value in row:
        total += value

print(total)
```

Output:

```text
21
```

---

# 38. Collection Processing with Functions

Collection logic can be placed inside reusable functions.

```python
def find_largest(numbers):
    return max(numbers)


numbers = [10, 30, 20, 50]

print(find_largest(numbers))
```

Output:

```text
50
```

This separates the problem-solving logic from the rest of the program.

---

# 39. Common Collection Problem Pattern

A large number of collection problems follow this structure:

```python
collection = [...]

result = []

for item in collection:
    if condition:
        result.append(item)

print(result)
```

For example:

```python
numbers = [10, 15, 20, 25, 30]

result = []

for number in numbers:
    if number > 20:
        result.append(number)

print(result)
```

Output:

```text
[25, 30]
```

---

# 40. Important Collection Methods and Functions

| Function / Method | Purpose                                 |
| ----------------- | --------------------------------------- |
| `len()`           | Number of elements                      |
| `sum()`           | Sum of numeric elements                 |
| `min()`           | Smallest value                          |
| `max()`           | Largest value                           |
| `sorted()`        | Returns a sorted collection             |
| `list.sort()`     | Sorts a list in place                   |
| `list.append()`   | Adds an element                         |
| `list.extend()`   | Adds multiple elements                  |
| `list.insert()`   | Inserts an element                      |
| `list.remove()`   | Removes a value                         |
| `list.pop()`      | Removes and returns an element          |
| `list.count()`    | Counts occurrences                      |
| `list.index()`    | Finds an element's index                |
| `set()`           | Creates a set / helps remove duplicates |
| `dict.get()`      | Safely retrieves a dictionary value     |
| `dict.items()`    | Returns key-value pairs                 |
| `dict.keys()`     | Returns keys                            |
| `dict.values()`   | Returns values                          |

---

# Common Problem-Solving Techniques

## 1. Traversal

Visit every element.

```python
for item in collection:
    print(item)
```

---

## 2. Accumulation

Build a result while traversing.

```python
total = 0

for number in numbers:
    total += number
```

---

## 3. Filtering

Keep only elements satisfying a condition.

```python
result = []

for number in numbers:
    if number > 10:
        result.append(number)
```

---

## 4. Searching

Look for a particular element.

```python
if target in numbers:
    print("Found")
```

---

## 5. Frequency Counting

Count occurrences using a dictionary.

```python
frequency[item] = frequency.get(item, 0) + 1
```

---

## 6. Sorting

Arrange elements in a particular order.

```python
numbers.sort()
```

---

## 7. Deduplication

Remove repeated values.

```python
unique = list(set(numbers))
```

Remember that converting to a set does not preserve the original order as a general guarantee.

---

# Common Mistakes

## Mistake 1: Modifying a list while iterating over it

Avoid:

```python
for item in numbers:
    if item < 0:
        numbers.remove(item)
```

This can cause elements to be skipped.

Instead, create a new collection:

```python
numbers = [number for number in numbers if number >= 0]
```

---

## Mistake 2: Confusing `append()` and `extend()`

`append()` adds one object:

```python
numbers.append([4, 5])
```

Result:

```text
[1, 2, 3, [4, 5]]
```

`extend()` adds the individual elements:

```python
numbers.extend([4, 5])
```

Result:

```text
[1, 2, 3, 4, 5]
```

---

## Mistake 3: Forgetting empty collections

This can cause problems:

```python
numbers = []

average = sum(numbers) / len(numbers)
```

`len(numbers)` is `0`, causing division by zero.

Always consider:

```python
if numbers:
    ...
```

---

## Mistake 4: Assuming `set` preserves list order

Do not rely on:

```python
list(set(numbers))
```

to maintain the original ordering.

---

## Mistake 5: Using the wrong dictionary key

Given:

```python
student = {
    "name": "Riyas",
    "mark": 90
}
```

This is correct:

```python
student["mark"]
```

Not:

```python
student[90]
```

---

# Practical Problem-Solving Workflow

When given a collection-based problem:

### Step 1 — Identify the collection

Determine whether the data is represented as:

```text
list
tuple
set
dictionary
nested collection
```

### Step 2 — Identify the required result

Ask:

```text
Do I need one value?
A new collection?
A count?
A modified collection?
A dictionary?
True/False?
```

### Step 3 — Decide how to traverse

Usually:

```python
for item in collection:
```

For nested collections:

```python
for row in matrix:
    for item in row:
```

### Step 4 — Identify the operation

Common operations include:

```text
search
filter
sort
count
sum
compare
group
remove duplicates
transform
```

### Step 5 — Test edge cases

Consider:

```text
empty collection
one element
duplicate elements
all elements satisfying the condition
no elements satisfying the condition
negative numbers
mixed data
```

---

# Practice Problems

Try solving these without looking at the solution:

1. Find the largest element in a list.
2. Find the smallest element in a list.
3. Calculate the sum of all elements.
4. Calculate the average.
5. Count the number of elements.
6. Search for an element.
7. Count how many times an element occurs.
8. Remove duplicates from a list.
9. Find duplicate elements.
10. Find elements that occur only once.
11. Sort a list without modifying the original list.
12. Reverse a list.
13. Find all even numbers.
14. Find all odd numbers.
15. Find all numbers greater than a given value.
16. Find common elements between two lists.
17. Find elements that exist in one list but not another.
18. Merge two lists.
19. Find the second largest distinct value.
20. Find the second smallest distinct value.
21. Count the frequency of every element.
22. Find the most frequent element.
23. Find the longest string in a list.
24. Find the shortest string in a list.
25. Find all strings longer than a given length.
26. Find the student with the highest mark using a dictionary.
27. Find students whose marks are above a given value.
28. Group students by course.
29. Calculate the sum of all values in a nested list.
30. Find the largest value in a matrix.

---

# Key Points

* Collection-based problems work with **multiple values**.
* Lists are commonly used when order and duplicates matter.
* Tuples are useful for fixed collections of values.
* Sets are useful for uniqueness and set operations.
* Dictionaries are useful for key-value relationships and frequency counting.
* `for` loops are fundamental for traversing collections.
* `if` conditions are commonly used for filtering.
* `append()` builds a list one element at a time.
* `set()` can be used for uniqueness.
* Dictionaries are especially useful for counting and grouping.
* `sorted()` returns a new sorted collection, while `sort()` modifies a list.
* Always consider empty collections and duplicate values.
* Many collection problems can be solved using the pattern **traverse → check/process → store result**.

---

# Interview Questions

### 1. What is a collection in Python?

A collection is an object used to store multiple values, such as a list, tuple, set, or dictionary.

### 2. What is the difference between a list and a set?

A list is ordered and can contain duplicate values, while a set stores unique elements and does not provide list-style indexing.

### 3. How do you find the largest element in a list?

```python
max(numbers)
```

### 4. How do you find the number of elements?

```python
len(numbers)
```

### 5. How do you remove duplicates?

A common approach is:

```python
list(set(numbers))
```

If order must be preserved, use an order-preserving approach instead.

### 6. What is the difference between `append()` and `extend()`?

`append()` adds one object as a single element, while `extend()` adds each element from an iterable.

### 7. What is frequency counting?

Frequency counting means determining how many times each value occurs in a collection.

### 8. Which collection is commonly used for frequency counting?

A dictionary is commonly used:

```python
frequency = {}

for item in collection:
    frequency[item] = frequency.get(item, 0) + 1
```

`collections.Counter` is also designed for this purpose.

### 9. What is the difference between `sort()` and `sorted()`?

`sort()` modifies a list in place, while `sorted()` returns a new sorted list.

### 10. Why are collection-based problems important?

They teach how to process and manipulate groups of data, which is a fundamental requirement in real-world programming.


--

[◀Back](.././)
---