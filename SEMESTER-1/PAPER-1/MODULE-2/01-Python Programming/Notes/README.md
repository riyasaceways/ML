> [!CAUTION]
    <details>
    <summary>⚠View Disclaimer</summary>
    $$\textcolor{#FF4400}{\texttt{Hi, I'm Riyas. I created these notes to help students understand and revise the topics more easily.}}$$
    $$\textcolor{#FF4400}{\texttt{Please keep in mind that these notes may contain mistakes, inaccuracies, or incomplete information. Use them as a reference and study aid, and always verify important information with your textbooks, instructors, official documentation, or other reliable sources.}}$$
    $$\textcolor{#FF4400}{\texttt{If you find an error or something that needs improvement, feel free to point it out or contribute a correction.}}$$
    </details>

# Study pytho it is a main matter in this week


## list

## Tuple 
- immutable
- Example: student = ("John", 25, "Python")

## set
- unorderd
- Example: numbers = {10, 20, 30, 20, 40}
---
# dictionary
- keys and values
- Example:
    ```python
    student = {
      "name": "John",
      "age": 25,
      "course": "Python"
  }
  ```
---
# Operators _______

## 1. Arithmetic operators*
- Calculations
    ```python
    a = 10
    b = 3
    
    print(a + b)
    print(a - b)
    print(a * b)
    print(a / b)
    print(a // b)
    print(a % b)
    print(a ** b)
    ``` 

## 2. Conditional Operators*
- compare with 
    ```python
    a = 10
    b = 20
    
    print(a == b)   # False
    print(a != b)   # True
    print(a > b)    # False
    print(a < b)    # True
    print(a >= b)   # False
    print(a <= b)   # True
    ```

## 3. Logical operators*
- true
    ```python
    age = 17
    has_permission = True
    
    if age >= 18 or has_permission:
        print("Allowed")
    ```
- false
    ```python
    is_logged_in = False
    
    if not is_logged_in:
        print("Please login")
    ```
## 4. Relational Operator*
## 5. Membership operator*
## 6. identity*
## 7. Bitwise Operators
- Example:
    ```python
    &	AND	5 & 3
    `	`	OR
    ^	XOR	5 ^ 3
    ~	NOT	~5
    <<	Left shift	5 << 1
    >>	Right shift	5 >> 1
    ```

---
## control statement
- if
    ```python
    age = 20
    
    if age >= 18:
        print("Eligible to vote")
    ```
  
- if else
    ```python
    marks = 65
    
    if marks >= 50:
        print("Pass")
    else:
        print("Fail")
    ```
- if elif else
    ```python
    marks = 75
    
    if marks >= 90:
        print("A+")
    elif marks >= 80:
        print("A")
    elif marks >= 70:
        print("B")
    elif marks >= 50:
        print("C")
    else:
        print("Fail")
    ```
---
# Loop
- Conditional loop
    ```python
    age = 25
    has_license = True
    
    if age >= 18:
        if has_license:
            print("Can drive")
        else:
            print("License required")
    else:
        print("Not eligible")
    names = ["John", "Alex", "David"]
    ```
- for loop
    ```python
    names = ["John", "Alex", "David"]
    
    for name in names:
        print(name)
    ```
- while loop
    ```python
    i = 1
    
    while i <= 5:
        print(i)
        i += 1
    ```
- nested loop
    ```python
    numbers = [10, 15, 20, 25, 30]
    
    for number in numbers:
    
        if number > 20:
            if number % 2 == 0:
                print(number)
    ```
- brake
    ```python
    for i in range(10):
    
        if i == 5:
            break
    
        print(i)
    ```
- continue
    ```python
    for i in range(5):
    
        if i == 2:
            continue
    
        print(i)
    ```
- pass
    ```python
    age = 25
    
    if age >= 18:
        pass
    else:
        print("Not eligible")
    ```
---
## function
> syntax of a function.
```python
def add(a, b):
    print(a + b)

add(10, 20)
```
> Call the fungtion
```python
add (10)
```


```python
def add (a,b):
c = a+b
return c
file = open("data.
```
---
## File handling
- file = open("data.txt", "r")
- "r"	Read
- "w"	Write
- "a"	Append
- "x"	Create new file
- "r+"	Read + Write
- "w+"	Write + Read
- "a+"	Append + Read
- file = open("data.txt", "w")
- file.write("Hello Python")
- file.close()
- import os
- os.remove("data.txt")
---
## trye and except
```python
try:
    a = 10
    b = 0
    result = a / b
    print(result)

except:
    print("Something went wrong")
```
## Modules and packages

---
# Practice

* Palindrome number 
* Factorial of number 
* Count vowels and consonants from a string
* Return the second most elements from the list
* Return the most repeated elements from a list
* Longest common substring
* Calculator implementation
* Bubble sort
* Star pattern code
* Return the largest and smallest element from list
* Pls practice the above  coding questions
* Pls explore these kind of questions for coding exam
* Regarding the env based question just show the reviewer how do u created the environment ,how to activate the environment . Use of env
* Pls ask him to mail me
* Check whether two strings are anagrams 
* reverse a string  

Add this 2 also

> [!CAUTION]
$$\textcolor{#FF0000}{\texttt{Hi, I'm Riyas. I created these notes to help students understand and revise the topics more easily.}}$$
$$\textcolor{#FF0000}{\texttt{Please keep in mind that these notes may contain mistakes, inaccuracies, or incomplete information. Use them as a reference and study aid, and always verify important information with your textbooks, instructors, official documentation, or other reliable sources.}}$$
$$\textcolor{#FF0000}{\texttt{If you find an error or something that needs improvement, feel free to point it out or contribute a correction.}}$$
