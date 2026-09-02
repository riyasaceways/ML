# Study pytho it is a main matter in this week


## list


## Tuple 
- immutable
- Example: student = ("John", 25, "Python")

## set
- unorderd
- Example: numbers = {10, 20, 30, 20, 40}
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
          
