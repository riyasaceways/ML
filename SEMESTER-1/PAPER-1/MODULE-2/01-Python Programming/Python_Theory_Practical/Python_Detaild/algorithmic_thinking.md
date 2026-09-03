[◀Back](.././)
---


# Algorithmic Thinking

Algorithmic thinking is the process of **thinking logically and systematically about how to solve a problem**.

It involves understanding a problem, breaking it into smaller parts, identifying patterns, designing a sequence of steps, testing the solution, and finally implementing it as code.

A programmer should not immediately start writing Python code.

A better approach is:

```text
Problem
   ↓
Understand
   ↓
Break Down
   ↓
Design Algorithm
   ↓
Write Pseudocode / Flowchart
   ↓
Implement
   ↓
Test
   ↓
Improve
```

---

# 1. What Is an Algorithm?

An algorithm is a **finite sequence of clear steps used to solve a problem or perform a task**.

For example, an algorithm for making tea might be:

```text
1. Boil water
2. Add tea
3. Add milk
4. Add sugar
5. Mix
6. Serve
```

Similarly, a programming algorithm describes the steps required to produce a result.

---

# 2. Why Algorithmic Thinking Is Important

Algorithmic thinking helps you:

* Solve problems systematically
* Avoid random trial and error
* Write clearer programs
* Break complex problems into smaller parts
* Identify errors more easily
* Reuse known problem-solving techniques
* Improve program efficiency
* Prepare for programming interviews

Knowing Python syntax is not enough.

A programmer must also know **how to approach a problem**.

---

# 3. Understand the Problem First

Before writing code, determine exactly what the problem requires.

Consider:

> Find the average of three numbers.

Identify:

### Input

Three numbers.

```text
10, 20, 30
```

### Processing

Add the numbers and divide by `3`.

```text
(10 + 20 + 30) / 3
```

### Output

```text
20
```

The basic structure is:

```text
Input → Processing → Output
```

---

# 4. Identify Inputs

Ask:

```text
What information is given?
```

For example:

```text
Find the largest number among three numbers.
```

Input:

```text
a
b
c
```

---

# 5. Identify Outputs

Ask:

```text
What should the program produce?
```

For the previous problem:

```text
largest number
```

Clearly identifying the output prevents solving the wrong problem.

---

# 6. Identify Constraints

Constraints describe limitations or special requirements.

For example:

```text
Find the largest number among 100 numbers.
```

Possible considerations:

* How many values are there?
* Are negative numbers allowed?
* Can duplicate values exist?
* Can the collection be empty?

Understanding constraints helps choose an appropriate algorithm.

---

# 7. Decomposition

Decomposition means **breaking a large problem into smaller problems**.

Suppose you need to create a student management program.

Instead of thinking:

```text
Build student management system
```

Break it down:

```text
Student Management System
        ↓
Add Student
        ↓
Update Student
        ↓
Delete Student
        ↓
Search Student
        ↓
Calculate Marks
        ↓
Generate Report
```

Each smaller problem can then be solved separately.

---

# 8. Example of Decomposition

Problem:

> Create a program that reads student marks, calculates the average, determines the grade, and displays the result.

Break it into:

```text
1. Read student information
2. Read marks
3. Validate marks
4. Calculate total
5. Calculate average
6. Determine grade
7. Display result
```

Now the problem becomes easier to solve.

---

# 9. Pattern Recognition

Pattern recognition means identifying similarities between a new problem and problems you have already solved.

For example, if you know how to:

```text
Find the largest number
```

you can apply a similar pattern to:

```text
Find the highest student mark
Find the most expensive product
Find the longest word
Find the oldest person
```

The data changes, but the underlying logic can be similar.

---

# 10. Abstraction

Abstraction means focusing on the **important details** while ignoring unnecessary information.

Suppose you need to calculate a student's average mark.

You may only need:

```text
Student name
Marks
```

You do not need unrelated information such as:

```text
Student's favorite color
Home address
Phone model
```

Abstraction helps keep algorithms focused.

---

# 11. Step-by-Step Thinking

An algorithm should describe actions in a logical order.

Problem:

> Find whether a number is even or odd.

Algorithm:

```text
1. Start
2. Get a number
3. Divide the number by 2 and check the remainder
4. If the remainder is 0, it is even
5. Otherwise, it is odd
6. Display the result
7. End
```

Python:

```python id="3h6q7m"
number = int(input("Enter a number: "))

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

---

# 12. Conditions in Algorithms

Conditions allow an algorithm to make decisions.

General structure:

```text
IF condition is true
    perform action A
ELSE
    perform action B
```

Example:

```text
IF mark >= 50
    Student passed
ELSE
    Student failed
```

Python:

```python id="x3m8qa"
if mark >= 50:
    print("Pass")
else:
    print("Fail")
```

---

# 13. Iteration in Algorithms

Iteration means repeating a set of instructions.

For example:

> Print numbers from 1 to 5.

Algorithm:

```text
1. Start at 1
2. Print the number
3. Increase the number
4. Repeat until the number reaches 5
```

Python:

```python id="c7v2pk"
for number in range(1, 6):
    print(number)
```

---

# 14. Selection

Selection means choosing between different paths.

Example:

```text
IF age >= 18
    Adult
ELSE
    Minor
```

In Python:

```python id="b4n8sy"
if age >= 18:
    print("Adult")
else:
    print("Minor")
```

---

# 15. Sequence

Sequence means executing instructions in a specific order.

Example:

```python id="p5m2wx"
a = 10
b = 20

total = a + b

print(total)
```

The operations happen in order:

```text
Assign values
    ↓
Calculate
    ↓
Display
```

---

# 16. Input → Process → Output

Many algorithms can be understood using:

```text
Input
  ↓
Process
  ↓
Output
```

Example:

```text
Input:
10, 20

Process:
10 + 20

Output:
30
```

Python:

```python id="n6q9rc"
a = 10
b = 20

result = a + b

print(result)
```

---

# 17. Pseudocode

Pseudocode is a way of describing an algorithm using **simple human-readable instructions** rather than the syntax of a specific programming language.

Example:

```text
START

READ number

IF number is divisible by 2
    DISPLAY "Even"
ELSE
    DISPLAY "Odd"

END
```

Pseudocode allows you to focus on the logic before worrying about Python syntax.

---

# 18. Why Use Pseudocode?

Pseudocode helps:

* Plan a solution
* Explain logic
* Find mistakes before coding
* Communicate algorithms
* Convert logic into any programming language

The same pseudocode can later be implemented in Python, Java, C++, or another language.

---

# 19. Flowcharts

A flowchart represents an algorithm visually.

Common flowchart concepts include:

```text
Start / End
    ↓
Process
    ↓
Decision
    ↓
Input / Output
```

For an even/odd problem:

```text
Start
  ↓
Input number
  ↓
number % 2 == 0?
  ├── Yes → Even
  └── No  → Odd
              ↓
             End
```

Flowcharts are useful when a problem contains many decisions or branches.

---

# 20. Example: Largest of Three Numbers

Problem:

> Find the largest of three numbers.

Input:

```text
10, 25, 15
```

### Algorithm

```text
1. Read three numbers
2. Assume the first number is the largest
3. Compare the second number with the largest
4. If the second is larger, update largest
5. Compare the third number with the largest
6. If the third is larger, update largest
7. Display largest
```

Python:

```python id="x8m3qc"
numbers = [10, 25, 15]

largest = numbers[0]

for number in numbers:
    if number > largest:
        largest = number

print(largest)
```

Output:

```text id="w6q1kp"
25
```

---

# 21. Example: Reverse a Number

Problem:

```text
1234 → 4321
```

### Algorithm

```text
1. Get the number
2. Set reverse = 0
3. Extract the last digit
4. Add the digit to reverse
5. Remove the last digit from the original number
6. Repeat until no digits remain
7. Display reverse
```

Python:

```python id="k4w7px"
number = 1234
reverse = 0

while number > 0:
    digit = number % 10
    reverse = reverse * 10 + digit
    number //= 10

print(reverse)
```

---

# 22. Generalization

A good algorithm should solve a **class of problems**, not just one specific example.

Instead of designing an algorithm specifically for:

```text
10, 20, 30
```

design it for:

```text
any list of numbers
```

For example:

```python id="p7x2mv"
def find_largest(numbers):
    largest = numbers[0]

    for number in numbers:
        if number > largest:
            largest = number

    return largest
```

Now the same algorithm works for:

```python id="y4n8sc"
find_largest([10, 20, 30])
find_largest([100, 5, 75])
find_largest([-10, -5, -20])
```

---

# 23. Edge Cases

An algorithm should not only work for the normal example.

Consider:

```text
normal input
empty input
single value
duplicate values
negative values
zero
very large values
invalid input
```

Example:

```python id="w2c6qy"
numbers = []
```

An algorithm that assumes at least one value exists may fail.

Therefore, ask:

```text
What happens if the input is empty?
What happens if there is only one value?
What happens if values are negative?
```

---

# 24. Testing an Algorithm

Testing means checking whether the algorithm produces the expected result.

Suppose:

```text
Algorithm: Find largest number
```

Test:

```text
Input              Expected Output
-----------------------------------
[10, 20, 30]       30
[-5, -2, -10]      -2
[5]                5
[10, 10, 5]        10
```

Testing different inputs helps reveal logical errors.

---

# 25. Debugging Through Algorithmic Thinking

When a program produces the wrong result, do not immediately rewrite everything.

Instead:

```text
1. Identify the expected result
2. Identify the actual result
3. Trace the algorithm step by step
4. Find where the logic differs
5. Fix the specific step
6. Test again
```

This is much more effective than randomly changing code.

---

# 26. Efficiency

Algorithmic thinking also involves asking:

> How efficiently does this solution solve the problem?

Suppose you need to find an element in a list.

A simple approach is to check each element:

```python id="z8k4qn"
for item in numbers:
    if item == target:
        print("Found")
        break
```

In the worst case, many elements may need to be checked.

Choosing appropriate data structures and algorithms can make a significant difference for large datasets.

---

# 27. Brute Force Approach

A brute-force algorithm tries possible solutions directly, often without using a more specialized optimization.

Example:

```text
Check every element
Check every possible pair
Try every possible combination
```

Brute force can be useful because it is often simple and easy to understand.

However, it may become inefficient for large inputs.

---

# 28. Improving an Algorithm

Suppose you need to find whether a number is prime.

A basic approach might check every number from `2` to `n - 1`.

A better approach only needs to check possible divisors up to:

```text
√n
```

Example:

```python id="f1m7wc"
number = 29
is_prime = True

if number < 2:
    is_prime = False
else:
    for i in range(2, int(number ** 0.5) + 1):
        if number % i == 0:
            is_prime = False
            break

print(is_prime)
```

The important idea is:

```text
Correct solution
      ↓
Efficient solution
```

---

# 29. Choosing the Right Data Structure

Algorithmic thinking is also about choosing an appropriate way to represent data.

For example:

### List

Useful for ordered collections:

```python id="m8x3qa"
numbers = [10, 20, 30]
```

### Set

Useful when uniqueness or membership testing is important:

```python id="q6v9ps"
numbers = {10, 20, 30}
```

### Dictionary

Useful for key-value relationships:

```python id="r2w7kc"
student = {
    "name": "Riyas",
    "mark": 90
}
```

Choosing the correct data structure can simplify the algorithm.

---

# 30. Divide and Conquer Thinking

Some complex problems can be divided into smaller parts.

For example:

```text
Large Problem
   ↓
Problem A + Problem B
   ↓
Solve A
Solve B
   ↓
Combine Results
```

This is a general problem-solving strategy and appears in many algorithms.

---

# 31. Reusability

A good algorithm can often be turned into a reusable function.

Instead of repeatedly writing:

```python id="x5m2pq"
largest = numbers[0]

for number in numbers:
    if number > largest:
        largest = number
```

create:

```python id="g8q4vn"
def find_largest(numbers):
    largest = numbers[0]

    for number in numbers:
        if number > largest:
            largest = number

    return largest
```

Now the logic can be reused.

---

# 32. Algorithmic Thinking vs Coding

These are related but different.

### Algorithmic thinking

Focuses on:

```text
What should I do?
What steps are required?
What cases should I handle?
Can the solution be improved?
```

### Coding

Focuses on:

```text
How do I express those steps in Python?
```

Therefore:

```text
Problem-solving
      ↓
Algorithm
      ↓
Code
```

---

# 33. Common Algorithmic Patterns

Many programming problems can be solved using common patterns.

### Traversal

Visit every element:

```python id="y8p3qa"
for item in data:
    ...
```

### Accumulation

Build a result:

```python id="c4n7ws"
total += value
```

### Filtering

Keep values satisfying a condition:

```python id="v9m2kp"
if condition:
    result.append(item)
```

### Searching

Look for a target:

```python id="s6x1rq"
if item == target:
    ...
```

### Counting

Track occurrences:

```python id="p3w8nc"
count += 1
```

### Frequency Mapping

Use a dictionary:

```python id="f7q2mx"
frequency[item] = frequency.get(item, 0) + 1
```

### Two-pointer thinking

Use two positions to process a sequence from different directions or maintain a range.

### Sorting

Arrange data first to simplify certain problems.

Recognizing these patterns makes new problems easier to approach.

---

# 34. A Complete Problem-Solving Example

Problem:

> Given a list of numbers, find the second-largest distinct number.

### Step 1 — Understand

Input:

```text
[10, 30, 20, 30, 40]
```

Expected:

```text
30
```

### Step 2 — Identify the challenge

The largest value is:

```text
40
```

The second-largest **distinct** value is:

```text
30
```

### Step 3 — Design a simple algorithm

```text
1. Remove duplicate values
2. Sort the values
3. Select the second-largest value
```

### Step 4 — Implement

```python id="d6x9qa"
numbers = [10, 30, 20, 30, 40]

unique_numbers = set(numbers)
sorted_numbers = sorted(unique_numbers)

print(sorted_numbers[-2])
```

Output:

```text id="k5m1ws"
30
```

### Step 5 — Consider edge cases

What if:

```text
[]
[10]
[10, 10]
```

There may not be a second distinct value.

The algorithm therefore needs appropriate validation.

---

# 35. Algorithm Checklist

Before implementing a solution, ask:

```text
□ Do I understand the problem?
□ What are the inputs?
□ What is the expected output?
□ What constraints exist?
□ Can I break the problem into smaller parts?
□ Have I identified a useful pattern?
□ What data structure should I use?
□ What conditions are required?
□ What loops are required?
□ What are the edge cases?
□ Can I describe the solution in pseudocode?
□ Can I test the algorithm manually?
□ Is the algorithm efficient enough?
```

---

# 36. Practical Exercises

Try solving these using algorithmic thinking **before writing Python code**.

### Beginner

1. Check whether a number is even or odd.
2. Find the largest of two numbers.
3. Find the largest of three numbers.
4. Calculate the sum of numbers from `1` to `n`.
5. Calculate factorial.
6. Reverse a string.
7. Count vowels in a string.
8. Find the largest element in a list.
9. Calculate the average of a list.
10. Search for an element in a list.

### Intermediate

11. Check whether a number is prime.
12. Find duplicate elements in a list.
13. Remove duplicate values.
14. Count character frequencies.
15. Check whether two strings are anagrams.
16. Find the second-largest distinct value.
17. Find the most frequent element.
18. Group records by a common property.
19. Find the longest word in a sentence.
20. Process student records and generate a summary.

### Advanced Thinking

21. Find the first non-repeating character.
22. Find the intersection of two collections.
23. Find the maximum sum of a continuous subarray.
24. Search efficiently in sorted data.
25. Compare two different solutions and determine which is more efficient.

For each problem, try:

```text
Problem
  ↓
Input / Output
  ↓
Break down
  ↓
Pattern
  ↓
Algorithm
  ↓
Pseudocode
  ↓
Python
  ↓
Test
  ↓
Improve
```

---

# Key Points

* Algorithmic thinking is **problem-solving before coding**.
* An algorithm is a finite sequence of steps for solving a problem.
* Start by understanding the input, output, and constraints.
* Decomposition breaks large problems into smaller problems.
* Pattern recognition helps reuse known problem-solving techniques.
* Abstraction removes unnecessary details.
* Conditions handle decisions.
* Loops handle repetition.
* Pseudocode helps design logic before writing Python syntax.
* Flowcharts provide a visual representation of an algorithm.
* Edge cases are essential for reliable solutions.
* Testing should include normal and unusual inputs.
* Choosing the right data structure can simplify a solution.
* A correct algorithm may still be improved for efficiency.
* Reusable algorithms can be implemented as functions.
* Good algorithmic thinking makes learning and writing code easier.

---

# Interview Questions

### 1. What is algorithmic thinking?

Algorithmic thinking is the ability to solve problems by breaking them into logical, ordered, and manageable steps.

### 2. What is an algorithm?

An algorithm is a finite sequence of well-defined steps used to solve a problem or perform a task.

### 3. Why should you design an algorithm before writing code?

It helps you understand the problem and establish the logic before dealing with programming-language syntax.

### 4. What is decomposition?

Decomposition is the process of breaking a complex problem into smaller, easier-to-solve parts.

### 5. What is pattern recognition?

Pattern recognition is identifying similarities between a new problem and previously solved problems or known algorithms.

### 6. What is abstraction?

Abstraction means focusing on the information and operations relevant to the problem while ignoring unnecessary details.

### 7. What is pseudocode?

Pseudocode is an informal, human-readable description of an algorithm that is independent of a particular programming language.

### 8. What is the difference between an algorithm and a program?

An algorithm describes **how to solve the problem**, while a program is the implementation of that solution in a programming language.

### 9. What are edge cases?

Edge cases are unusual or boundary inputs that may expose problems in an algorithm, such as an empty collection, zero, negative values, or a single element.

### 10. Why is testing important?

Testing verifies that an algorithm produces the expected results for different inputs and helps identify logical errors.

### 11. What is optimization?

Optimization is improving an algorithm so that it uses fewer resources or performs the required task more efficiently.

### 12. What is brute force?

A brute-force approach systematically tries possible options directly, often favoring simplicity over efficiency.

### 13. Why are data structures important in algorithm design?

The choice of data structure affects how easily and efficiently data can be stored, accessed, searched, and modified.

### 14. What is the general problem-solving process?

```text
Understand
→ Decompose
→ Identify patterns
→ Design algorithm
→ Implement
→ Test
→ Optimize
```


---


[◀Back](.././)
---