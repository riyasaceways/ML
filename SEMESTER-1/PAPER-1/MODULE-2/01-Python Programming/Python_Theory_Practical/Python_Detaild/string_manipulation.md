[◀Back](.././)
---


# String Manipulation

String manipulation means **processing, analyzing, modifying, and working with text data**.

In Python, strings are sequences of characters enclosed in quotes.

```python
name = "Riyas"
message = 'Hello Python'
```

Strings can contain:

```text
letters
numbers
spaces
symbols
special characters
```

Example:

```python
text = "Python 3.14!"
```

---

# 1. String Indexing

Each character in a string has an index.

```python
text = "Python"
```

The indexes are:

```text
 P  y  t  h  o  n
 0  1  2  3  4  5
```

Access a character:

```python
print(text[0])
```

Output:

```text
P
```

---

# 2. Negative Indexing

Python also supports negative indexes.

```text
 P   y   t   h   o   n
-6  -5  -4  -3  -2  -1
```

Example:

```python
text = "Python"

print(text[-1])
```

Output:

```text
n
```

---

# 3. String Slicing

Slicing extracts a portion of a string.

```python
text = "Python Programming"

print(text[0:6])
```

Output:

```text
Python
```

The general syntax is:

```python
string[start:stop:step]
```

The `stop` index is not included.

---

# 4. Slicing with Step

```python
text = "Python"

print(text[::2])
```

Output:

```text
Pto
```

Every second character is selected.

---

# 5. Reverse a String

A common string problem is reversing a string.

```python
text = "Python"

reverse = text[::-1]

print(reverse)
```

Output:

```text
nohtyP
```

---

# 6. Check for a Palindrome

A palindrome reads the same from both directions.

Examples:

```text
madam
level
radar
```

```python
text = "madam"

if text == text[::-1]:
    print("Palindrome")
else:
    print("Not a palindrome")
```

Output:

```text
Palindrome
```

For case-insensitive checking:

```python
text = "Madam"

text = text.lower()

if text == text[::-1]:
    print("Palindrome")
```

---

# 7. Find String Length

Use `len()`:

```python
text = "Python"

print(len(text))
```

Output:

```text
6
```

Spaces are also counted.

```python
text = "Hello World"

print(len(text))
```

Output:

```text
11
```

---

# 8. Convert to Uppercase

```python
text = "python"

print(text.upper())
```

Output:

```text
PYTHON
```

---

# 9. Convert to Lowercase

```python
text = "PYTHON"

print(text.lower())
```

Output:

```text
python
```

---

# 10. Title Case

`title()` converts the first letter of each word to uppercase.

```python
text = "python programming language"

print(text.title())
```

Output:

```text
Python Programming Language
```

---

# 11. Capitalize

`capitalize()` makes the first character uppercase and the remaining characters lowercase.

```python
text = "python PROGRAMMING"

print(text.capitalize())
```

Output:

```text
Python programming
```

---

# 12. Swap Case

`swapcase()` changes uppercase characters to lowercase and lowercase characters to uppercase.

```python
text = "Python"

print(text.swapcase())
```

Output:

```text
pYTHON
```

---

# 13. Remove Leading and Trailing Spaces

Use `strip()`:

```python
text = "   Python   "

print(text.strip())
```

Output:

```text
Python
```

---

# 14. Remove Leading Spaces

Use `lstrip()`:

```python
text = "   Python"

print(text.lstrip())
```

---

# 15. Remove Trailing Spaces

Use `rstrip()`:

```python
text = "Python   "

print(text.rstrip())
```

---

# 16. Search for a Substring

Use the `in` operator.

```python
text = "Python Programming"

if "Python" in text:
    print("Found")
```

Output:

```text
Found
```

---

# 17. Check Whether Text Does Not Exist

```python
text = "Python Programming"

if "Java" not in text:
    print("Java not found")
```

---

# 18. Find the Position of Text

`find()` returns the index of the first occurrence.

```python
text = "Python Programming"

position = text.find("Programming")

print(position)
```

Output:

```text
7
```

If the substring is not found:

```python
print(text.find("Java"))
```

Output:

```text
-1
```

---

# 19. Using `index()`

`index()` also searches for a substring.

```python
text = "Python Programming"

print(text.index("Python"))
```

Unlike `find()`, `index()` raises a `ValueError` if the substring is not found.

---

# 20. Count Characters

```python
text = "banana"

print(text.count("a"))
```

Output:

```text
3
```

---

# 21. Count a Substring

```python
text = "Python Python"

print(text.count("Python"))
```

Output:

```text
2
```

---

# 22. Replace Text

Use `replace()`.

```python
text = "I like Java"

new_text = text.replace("Java", "Python")

print(new_text)
```

Output:

```text
I like Python
```

Strings are immutable, so `replace()` returns a new string.

---

# 23. Split a String

`split()` divides a string into a list.

```python
text = "Python is easy"

words = text.split()

print(words)
```

Output:

```text
['Python', 'is', 'easy']
```

---

# 24. Split Using a Separator

```python
data = "apple,banana,orange"

fruits = data.split(",")

print(fruits)
```

Output:

```text
['apple', 'banana', 'orange']
```

---

# 25. Count Words

A simple way to count words is:

```python
sentence = "Python is easy to learn"

words = sentence.split()

print(len(words))
```

Output:

```text
5
```

---

# 26. Join Strings

`join()` combines strings from an iterable.

```python
words = ["Python", "is", "easy"]

sentence = " ".join(words)

print(sentence)
```

Output:

```text
Python is easy
```

Using a comma:

```python
fruits = ["apple", "banana", "orange"]

result = ", ".join(fruits)

print(result)
```

Output:

```text
apple, banana, orange
```

---

# 27. Count Vowels

```python
text = "Python Programming"

vowels = "aeiou"
count = 0

for char in text.lower():
    if char in vowels:
        count += 1

print(count)
```

---

# 28. Count Consonants

```python
text = "Python"

vowels = "aeiou"
count = 0

for char in text.lower():
    if char.isalpha() and char not in vowels:
        count += 1

print(count)
```

Using `isalpha()` ensures that spaces and numbers are not treated as consonants.

---

# 29. Count Digits in a String

A string can contain both letters and numbers.

```python
text = "Python123"

count = 0

for char in text:
    if char.isdigit():
        count += 1

print(count)
```

Output:

```text
3
```

---

# 30. Count Letters

```python
text = "Python123"

count = 0

for char in text:
    if char.isalpha():
        count += 1

print(count)
```

Output:

```text
6
```

---

# 31. Count Spaces

```python
text = "Python is easy"

count = 0

for char in text:
    if char == " ":
        count += 1

print(count)
```

---

# 32. Character Frequency

A dictionary can be used to count every character.

```python
text = "banana"

frequency = {}

for char in text:
    frequency[char] = frequency.get(char, 0) + 1

print(frequency)
```

Output:

```text
{'b': 1, 'a': 3, 'n': 2}
```

---

# 33. Find Duplicate Characters

```python
text = "programming"

duplicates = []

for char in text:
    if text.count(char) > 1 and char not in duplicates:
        duplicates.append(char)

print(duplicates)
```

For larger strings, a frequency dictionary or `Counter` is generally more efficient.

---

# 34. Remove Duplicate Characters

```python
text = "programming"

result = ""

for char in text:
    if char not in result:
        result += char

print(result)
```

Output:

```text
progamin
```

This approach preserves the first occurrence of each character.

---

# 35. Find Unique Characters

A unique character appears only once.

```python
text = "programming"

for char in text:
    if text.count(char) == 1:
        print(char)
```

---

# 36. Check Whether Two Strings Are Equal

```python
a = "Python"
b = "Python"

if a == b:
    print("Same")
else:
    print("Different")
```

String comparison is case-sensitive.

```python
"Python" == "python"
```

Result:

```text
False
```

---

# 37. Case-insensitive Comparison

Use `lower()` or, preferably for general Unicode-aware caseless comparison, `casefold()`.

```python
a = "Python"
b = "python"

if a.casefold() == b.casefold():
    print("Same")
```

---

# 38. Check Whether Two Strings Are Anagrams

Two strings are anagrams when they contain the same characters with the same frequencies, regardless of order.

Example:

```text
listen
silent
```

```python
a = "listen"
b = "silent"

if sorted(a) == sorted(b):
    print("Anagrams")
else:
    print("Not anagrams")
```

Output:

```text
Anagrams
```

For case-insensitive checking:

```python
a = a.casefold()
b = b.casefold()
```

---

# 39. Remove Spaces Before Comparing

For some problems, spaces should not matter.

```python
a = "hello world"
b = "helloworld"

a = a.replace(" ", "")
b = b.replace(" ", "")

print(a == b)
```

Output:

```text
True
```

---

# 40. Check Whether a String Contains Only Letters

```python
text = "Python"

print(text.isalpha())
```

Output:

```text
True
```

---

# 41. Check Whether a String Contains Only Digits

```python
text = "12345"

print(text.isdigit())
```

Output:

```text
True
```

---

# 42. Check for Alphanumeric Characters

`isalnum()` returns `True` when all characters are letters or digits and the string is not empty.

```python
text = "Python123"

print(text.isalnum())
```

Output:

```text
True
```

---

# 43. Check for Lowercase

```python
text = "python"

print(text.islower())
```

---

# 44. Check for Uppercase

```python
text = "PYTHON"

print(text.isupper())
```

---

# 45. Reverse Each Word

```python
sentence = "Python is easy"

words = sentence.split()

result = []

for word in words:
    result.append(word[::-1])

print(" ".join(result))
```

Output:

```text
nohtyP si ysae
```

---

# 46. Reverse the Order of Words

```python
sentence = "Python is easy"

words = sentence.split()

result = " ".join(words[::-1])

print(result)
```

Output:

```text
easy is Python
```

This is different from reversing every word.

---

# 47. Find the Longest Word

```python
sentence = "Python programming is interesting"

words = sentence.split()

longest = max(words, key=len)

print(longest)
```

Output:

```text
programming
```

---

# 48. Find the Shortest Word

```python
sentence = "Python is easy"

words = sentence.split()

shortest = min(words, key=len)

print(shortest)
```

Output:

```text
is
```

---

# 49. Remove Punctuation

A simple approach:

```python
text = "Hello, World!"

result = ""

for char in text:
    if char.isalnum() or char.isspace():
        result += char

print(result)
```

Output:

```text
Hello World
```

For more complex text processing, Python's `string` module or regular expressions can be useful.

---

# 50. String Formatting

String formatting allows values to be inserted into text.

### f-strings

```python
name = "Riyas"
age = 20

message = f"My name is {name} and I am {age} years old."

print(message)
```

Output:

```text
My name is Riyas and I am 20 years old.
```

---

# 51. Formatting Expressions

Expressions can also be placed inside an f-string.

```python
a = 10
b = 20

print(f"Sum = {a + b}")
```

Output:

```text
Sum = 30
```

---

# 52. Format Numbers

```python
price = 1234.5678

print(f"{price:.2f}")
```

Output:

```text
1234.57
```

---

# 53. Escape Characters

Special characters can be represented using escape sequences.

### New line

```python
print("Hello\nWorld")
```

Output:

```text
Hello
World
```

### Tab

```python
print("Name\tAge")
```

Output:

```text
Name    Age
```

### Quote inside a string

```python
print("He said \"Hello\"")
```

---

# 54. Raw Strings

Raw strings are useful when backslashes should generally be treated literally.

```python
path = r"C:\Users\Riyas\Documents"

print(path)
```

---

# 55. String Immutability

Strings are **immutable**.

This means individual characters cannot be changed directly.

Incorrect:

```python
text = "Python"

text[0] = "J"
```

This causes:

```text
TypeError
```

Instead, create a new string:

```python
text = "Python"

text = "J" + text[1:]

print(text)
```

Output:

```text
Jython
```

---

# 56. Traversing a String

A string can be processed character by character.

```python
text = "Python"

for char in text:
    print(char)
```

Output:

```text
P
y
t
h
o
n
```

---

# 57. String Problems Using Functions

String logic can be placed inside reusable functions.

```python
def reverse_string(text):
    return text[::-1]


result = reverse_string("Python")

print(result)
```

Output:

```text
nohtyP
```

---

# 58. String Problems Using List Comprehension

List comprehensions can process characters.

Example: extract vowels.

```python
text = "Python Programming"

vowels = [char for char in text.lower() if char in "aeiou"]

print(vowels)
```

Output:

```text
['o', 'o', 'a', 'i']
```

---

# 59. Common String Methods

| Method         | Purpose                                          |
| -------------- | ------------------------------------------------ |
| `upper()`      | Converts to uppercase                            |
| `lower()`      | Converts to lowercase                            |
| `title()`      | Converts to title case                           |
| `capitalize()` | Capitalizes the first character                  |
| `swapcase()`   | Swaps uppercase/lowercase                        |
| `strip()`      | Removes leading/trailing whitespace              |
| `lstrip()`     | Removes leading whitespace                       |
| `rstrip()`     | Removes trailing whitespace                      |
| `find()`       | Finds substring position                         |
| `index()`      | Finds substring position or raises an error      |
| `count()`      | Counts occurrences                               |
| `replace()`    | Replaces text                                    |
| `split()`      | Splits a string into a list                      |
| `join()`       | Combines strings                                 |
| `startswith()` | Checks the beginning                             |
| `endswith()`   | Checks the ending                                |
| `isalpha()`    | Checks whether all characters are alphabetic     |
| `isdigit()`    | Checks whether all characters are digits         |
| `isalnum()`    | Checks whether all characters are letters/digits |
| `isspace()`    | Checks whether all characters are whitespace     |
| `islower()`    | Checks lowercase                                 |
| `isupper()`    | Checks uppercase                                 |

---

# Common String Problem Patterns

## Pattern 1 — Traverse Characters

```python
for char in text:
    # process char
```

Useful for:

* Counting vowels
* Counting digits
* Counting spaces
* Finding special characters

---

## Pattern 2 — Build a New String

```python
result = ""

for char in text:
    if condition:
        result += char
```

Useful for:

* Removing characters
* Filtering characters
* Cleaning text

---

## Pattern 3 — Build a List

```python
result = []

for char in text:
    if condition:
        result.append(char)
```

Useful when the result needs to be processed as a collection.

---

## Pattern 4 — Split → Process → Join

```python
words = text.split()

# process words

result = " ".join(words)
```

Useful for:

* Word manipulation
* Reversing words
* Removing extra spaces
* Formatting sentences

---

# Common Mistakes

## Mistake 1: Trying to modify a string directly

Incorrect:

```python
text[0] = "A"
```

Strings are immutable.

Create a new string instead.

---

## Mistake 2: Confusing `find()` and `index()`

`find()` returns `-1` when the substring is not found.

```python
text.find("Java")
```

`index()` raises `ValueError` when it is not found.

```python
text.index("Java")
```

---

## Mistake 3: Forgetting that indexes start at zero

For:

```text
Python
```

`P` is index `0`, not index `1`.

---

## Mistake 4: Confusing `split()` and `join()`

`split()`:

```text
string → list
```

`join()`:

```text
list/iterable of strings → string
```

---

## Mistake 5: Counting uppercase and lowercase separately

This:

```python
text.count("a")
```

does not count `"A"`.

For case-insensitive processing, normalize the text first:

```python
text = text.casefold()
```

---

# Practical Problem-Solving Workflow

When solving a string problem:

### Step 1 — Identify the input

Ask:

```text
Is it a single word?
A sentence?
Multiple strings?
A string containing numbers?
```

### Step 2 — Identify the required output

Do you need:

```text
A new string?
A number?
A Boolean?
A list?
A dictionary?
```

### Step 3 — Decide whether to normalize

Depending on the problem:

```python
text = text.lower()
```

or:

```python
text = text.casefold()
```

or:

```python
text = text.strip()
```

### Step 4 — Choose the technique

Common techniques:

```text
indexing
slicing
looping
string methods
split()
join()
dictionary counting
list comprehension
```

### Step 5 — Test edge cases

Consider:

```text
empty string
single character
spaces
uppercase/lowercase
numbers
special characters
repeated characters
```

---

# Practice Problems

Try solving these without looking at the solution:

1. Find the length of a string.
2. Reverse a string.
3. Check whether a string is a palindrome.
4. Count vowels.
5. Count consonants.
6. Count digits.
7. Count spaces.
8. Count special characters.
9. Count words in a sentence.
10. Convert a string to uppercase.
11. Convert a string to lowercase.
12. Remove leading and trailing spaces.
13. Replace a word in a sentence.
14. Find the first occurrence of a character.
15. Count the occurrences of a character.
16. Find duplicate characters.
17. Find unique characters.
18. Remove duplicate characters.
19. Find the most frequent character.
20. Find the longest word.
21. Find the shortest word.
22. Reverse each word in a sentence.
23. Reverse the order of words.
24. Check whether two strings are equal.
25. Check whether two strings are anagrams.
26. Remove all spaces from a string.
27. Remove punctuation from a sentence.
28. Count the frequency of every character.
29. Find the first non-repeating character.
30. Check whether a string contains only digits.
31. Check whether a string contains only letters.
32. Extract all digits from a string.
33. Extract all alphabetic characters from a string.
34. Capitalize the first letter of every word.
35. Find the largest word by length.

---

# Key Points

* A string is a **sequence of characters**.
* String indexes start at `0`.
* Negative indexes access characters from the end.
* Slicing extracts portions of strings.
* Strings are **immutable**.
* `len()` finds string length.
* `split()` converts a string into parts.
* `join()` combines strings.
* `find()` searches for a substring and returns `-1` when absent.
* `count()` counts occurrences.
* `replace()` creates a new string with replacements.
* `strip()` removes leading and trailing whitespace.
* `in` is useful for checking whether text exists.
* Loops are useful for character-by-character processing.
* Dictionaries are useful for character-frequency problems.
* f-strings are the modern and convenient way to format strings.
* Always consider case sensitivity, whitespace, empty strings, and special characters when solving string problems.

---

# Interview Questions

### 1. What is a string in Python?

A string is an immutable sequence of characters.

### 2. Are strings mutable?

No. Python strings are immutable.

### 3. How do you reverse a string?

```python
text[::-1]
```

### 4. How do you find the length of a string?

```python
len(text)
```

### 5. What is the difference between `find()` and `index()`?

`find()` returns `-1` when the substring is not found, while `index()` raises `ValueError`.

### 6. What does `split()` do?

It divides a string into a list of substrings.

### 7. What does `join()` do?

It combines an iterable of strings into a single string using a separator.

### 8. How do you check whether a substring exists?

```python
if "Python" in text:
    ...
```

### 9. How do you check whether two strings are anagrams?

One simple approach is:

```python
sorted(a) == sorted(b)
```

after applying any required normalization.

### 10. Why is string immutability important?

Because string operations that appear to modify text actually create new string objects rather than changing the existing string in place.

### 11. How do you count character frequency?

A dictionary can be used:

```python
frequency[char] = frequency.get(char, 0) + 1
```

### 12. What is the difference between `lower()` and `casefold()`?

Both are used for case normalization, but `casefold()` is designed for more aggressive Unicode-aware case-insensitive comparisons.


[◀Back](.././)
---