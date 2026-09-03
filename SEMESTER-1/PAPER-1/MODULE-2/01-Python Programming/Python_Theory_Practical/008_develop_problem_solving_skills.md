## Number-based Problems

Number-based problems are programming problems that involve **numbers, mathematical operations, conditions, loops, and logical thinking**. They are commonly used to practice Python fundamentals and problem-solving skills.

### Common Number-based Problems

* **Even or Odd** – Determine whether a number is divisible by `2`.
* **Positive, Negative, or Zero** – Check the sign of a number.
* **Largest of Numbers** – Find the largest among two or more numbers.
* **Smallest of Numbers** – Find the smallest among given numbers.
* **Sum of Digits** – Add all the individual digits of a number.
* **Reverse a Number** – Reverse the digits of a number.
* **Palindrome Number** – Check whether a number remains the same when reversed.
* **Prime Number** – Determine whether a number has only two factors: `1` and itself.
* **Factorial** – Calculate the product of all positive integers up to a given number.
* **Fibonacci Series** – Generate a sequence where each number is the sum of the previous two.
* **Armstrong Number** – Check whether a number is equal to the sum of its digits raised to the number of digits.
* **Perfect Number** – Check whether a number is equal to the sum of its proper divisors.
* **Factors of a Number** – Find all numbers that divide a given number without a remainder.
* **Count Digits** – Find the number of digits in an integer.
* **Sum of Natural Numbers** – Calculate the sum of numbers from `1` to `n`.
* **Multiplication Table** – Generate the multiplication table of a number.

### Example

```python
number = int(input("Enter a number: "))

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

Number-based problems help develop **arithmetic logic, conditional thinking, loops, and algorithmic problem-solving skills**.

[View more details →](./Python_Detaild/number_based_problems.md)

---

## Collection-based Problems

Collection-based problems are programming problems that involve working with **multiple values stored in collections** such as lists, tuples, sets, and dictionaries.

They help develop skills in **iteration, searching, filtering, sorting, counting, updating, and manipulating groups of data**.

### Common Collection-based Problems

* **Find the largest element** – Find the maximum value in a collection.
* **Find the smallest element** – Find the minimum value.
* **Calculate sum** – Add all numeric elements.
* **Calculate average** – Find the average of collection values.
* **Count elements** – Determine the number of items.
* **Search for an element** – Check whether a value exists.
* **Count occurrences** – Find how many times a value appears.
* **Remove duplicates** – Create a collection containing unique values.
* **Find common elements** – Find values shared by two collections.
* **Merge collections** – Combine multiple collections.
* **Sort elements** – Arrange values in ascending or descending order.
* **Filter elements** – Select elements based on a condition.
* **Separate even and odd numbers** – Divide numbers into two groups.
* **Find repeated elements** – Identify values that occur multiple times.
* **Find unique elements** – Identify values that occur only once.
* **Reverse a collection** – Change the order of elements.
* **Frequency counting** – Count how often each value occurs.
* **Dictionary-based grouping** – Organize related data using key-value pairs.

### Example

```python
numbers = [10, 20, 30, 40, 50]

total = 0

for number in numbers:
    total += number

print("Sum:", total)
```

Output:

```text
Sum: 150
```

Collection-based problems are important because real-world programs frequently process **groups of related data rather than a single value**.

[View more details →](./Python_Detaild/collection_based_problems.md)

---

## String Manipulation

String manipulation is the process of **working with and modifying text** in Python. It includes operations such as accessing characters, slicing, searching, replacing, splitting, joining, formatting, and changing the case of strings.

### Common String Manipulation Problems

* **Reverse a string** – Reverse the order of characters.
* **Check palindrome** – Determine whether a string reads the same forward and backward.
* **Count characters** – Find the number of characters in a string.
* **Count vowels and consonants** – Count different types of alphabetic characters.
* **Count words** – Determine the number of words in a sentence.
* **Change case** – Convert text to uppercase, lowercase, title case, etc.
* **Remove spaces** – Remove leading, trailing, or unnecessary spaces.
* **Search for text** – Check whether a character or substring exists.
* **Count occurrences** – Find how many times a character or substring appears.
* **Replace text** – Replace one part of a string with another.
* **Split strings** – Break a string into multiple parts.
* **Join strings** – Combine multiple strings into one.
* **Extract substrings** – Get a specific portion of a string.
* **Remove duplicate characters** – Create a string containing unique characters.
* **Find repeated characters** – Identify characters that occur multiple times.
* **Anagram checking** – Determine whether two strings contain the same characters.
* **Character frequency** – Count how often each character appears.
* **String formatting** – Construct strings using variables and formatted values.

### Example

```python
text = "Python Programming"

print(text.upper())
print(text.lower())
print(text[0:6])
```

Output:

```text
PYTHON PROGRAMMING
python programming
Python
```

String manipulation is important because **text processing is used in almost every type of software application**.

[View more details →](./Python_Detaild/string_manipulation.md)

---

## Data Processing Exercises

Data processing exercises involve **collecting, organizing, transforming, filtering, and analyzing data** using Python. They combine concepts such as lists, dictionaries, strings, loops, functions, and file handling.

### Common Data Processing Exercises

* **Filter data** – Select only records that satisfy a condition.
* **Transform data** – Modify values into a required format.
* **Clean data** – Handle missing, unwanted, or inconsistent values.
* **Sort data** – Arrange records based on one or more values.
* **Search data** – Find records matching a specific value.
* **Count data** – Count records or occurrences.
* **Calculate statistics** – Find sum, average, minimum, maximum, etc.
* **Group data** – Organize records based on a common property.
* **Remove duplicates** – Identify and remove repeated records.
* **Process nested data** – Work with lists and dictionaries containing other collections.
* **Process text data** – Extract and analyze information from strings.
* **Process CSV data** – Read, modify, and analyze tabular data.
* **Process JSON data** – Work with structured key-value data.
* **Combine data** – Merge information from multiple collections or sources.
* **Generate reports** – Convert processed data into a readable result.

### Example

```python id="qk1w8a"
students = [
    {"name": "Ali", "mark": 75},
    {"name": "Riyas", "mark": 90},
    {"name": "John", "mark": 65}
]

for student in students:
    if student["mark"] >= 80:
        print(student["name"])
```

Output:

```text id="8qz7qg"
Riyas
```

The general data-processing pattern is:

```text
Input → Process → Analyze → Output
```

[View more details →](./Python_Detaild/data_processing_exercises.md)

---

## Algorithmic Thinking

Algorithmic thinking is the ability to **break a problem into clear, logical, and step-by-step instructions** that can be followed to produce the desired result.

It is not about writing code immediately. The main goal is to understand the problem, design a solution, and then convert that solution into code.

### Key Concepts

* **Problem Understanding** – Clearly identify what the problem is asking.
* **Input and Output** – Determine what data is given and what result is required.
* **Decomposition** – Break a large problem into smaller, manageable problems.
* **Pattern Recognition** – Identify similarities with problems already solved.
* **Abstraction** – Focus on important information while ignoring unnecessary details.
* **Step-by-step Logic** – Arrange operations in the correct order.
* **Conditions** – Make decisions based on different situations.
* **Iteration** – Repeat operations when necessary.
* **Algorithms** – Define a finite sequence of steps to solve a problem.
* **Pseudocode** – Describe the solution using simple, code-like instructions.
* **Flowcharts** – Represent the logic visually.
* **Testing** – Check whether the algorithm works for different inputs.
* **Optimization** – Improve the solution to make it more efficient.

### Example

Problem: Find the largest number in a list.

```text
1. Start
2. Take the list of numbers
3. Assume the first number is the largest
4. Compare it with each remaining number
5. If a larger number is found, update the largest value
6. Continue until all numbers are checked
7. Display the largest number
8. End
```

Python implementation:

```python id="f6v2qa"
numbers = [10, 25, 15, 40, 30]

largest = numbers[0]

for number in numbers:
    if number > largest:
        largest = number

print(largest)
```

Algorithmic thinking is the foundation of **problem-solving, programming, debugging, and software development**.

[View more details →](./Python_Detaild/algorithmic_thinking.md)


