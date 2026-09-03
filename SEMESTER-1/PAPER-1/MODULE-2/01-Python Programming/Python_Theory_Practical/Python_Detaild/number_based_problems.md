[◀Back](.././)
---


# Number-based Problems

Number-based problems are problems that require working with **integers, digits, arithmetic operations, mathematical properties, conditions, and loops**.

They are especially useful for beginners because they combine Python syntax with logical problem-solving.

---

## 1. Even or Odd

A number is **even** if it is completely divisible by `2`.

The modulo operator `%` gives the remainder after division.

```python
number = 10

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

Output:

```text
Even
```

### Logic

```text
number % 2 == 0 → Even
number % 2 != 0 → Odd
```

---

## 2. Positive, Negative, or Zero

A number can be:

* Positive → greater than `0`
* Negative → less than `0`
* Zero → equal to `0`

```python
number = -5

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

---

## 3. Largest of Two Numbers

Use a comparison to determine which number is larger.

```python
a = 25
b = 40

if a > b:
    print(a)
else:
    print(b)
```

Python also provides `max()`:

```python
print(max(a, b))
```

---

## 4. Largest of Three Numbers

```python
a = 10
b = 35
c = 20

if a >= b and a >= c:
    largest = a
elif b >= a and b >= c:
    largest = b
else:
    largest = c

print(largest)
```

Using the built-in function:

```python
print(max(a, b, c))
```

---

## 5. Smallest of Numbers

The same concept can be used to find the smallest value.

```python
a = 10
b = 5
c = 20

smallest = min(a, b, c)

print(smallest)
```

Output:

```text
5
```

---

## 6. Sum of Digits

The **sum of digits** means adding every individual digit.

Example:

```text
1234
1 + 2 + 3 + 4 = 10
```

### Using arithmetic operations

```python
number = 1234
total = 0

while number > 0:
    digit = number % 10
    total += digit
    number //= 10

print(total)
```

Output:

```text
10
```

### How it works

For `1234`:

```text
1234 % 10 → 4
123 // 10 → 123

123 % 10 → 3
12 // 10 → 12

12 % 10 → 2
1 // 10 → 1

1 % 10 → 1
0 // 10 → 0
```

Therefore:

```text
4 + 3 + 2 + 1 = 10
```

---

## 7. Reverse a Number

Example:

```text
12345 → 54321
```

```python
number = 12345
reverse = 0

while number > 0:
    digit = number % 10
    reverse = reverse * 10 + digit
    number //= 10

print(reverse)
```

Output:

```text
54321
```

### Important logic

```python
reverse = reverse * 10 + digit
```

This shifts the existing digits to the left and adds the new digit.

---

## 8. Palindrome Number

A **palindrome number** reads the same forward and backward.

Examples:

```text
121 → Palindrome
1331 → Palindrome
123 → Not a palindrome
```

```python
number = 121
original = number
reverse = 0

while number > 0:
    digit = number % 10
    reverse = reverse * 10 + digit
    number //= 10

if original == reverse:
    print("Palindrome")
else:
    print("Not a palindrome")
```

The original value is stored because the number is changed inside the loop.

---

## 9. Count Digits

Example:

```text
123456 → 6 digits
```

```python
number = 123456
count = 0

while number > 0:
    count += 1
    number //= 10

print(count)
```

Output:

```text
6
```

### Alternative

For a non-negative integer:

```python
number = 123456

print(len(str(number)))
```

---

## 10. Factorial

The factorial of `n` is written as `n!`.

```text
5! = 5 × 4 × 3 × 2 × 1
   = 120
```

```python
number = 5
factorial = 1

for i in range(1, number + 1):
    factorial *= i

print(factorial)
```

Output:

```text
120
```

### Important

```text
0! = 1
```

---

## 11. Prime Number

A **prime number** has exactly two positive factors:

```text
1 and itself
```

Examples:

```text
2, 3, 5, 7, 11, 13
```

```python
number = 17
is_prime = True

if number < 2:
    is_prime = False
else:
    for i in range(2, number):
        if number % i == 0:
            is_prime = False
            break

if is_prime:
    print("Prime")
else:
    print("Not prime")
```

### More efficient approach

It is sufficient to check divisors up to the square root of the number.

```python
number = 17
is_prime = True

if number < 2:
    is_prime = False
else:
    for i in range(2, int(number ** 0.5) + 1):
        if number % i == 0:
            is_prime = False
            break

print("Prime" if is_prime else "Not prime")
```

---

## 12. Factors of a Number

A factor is a number that divides another number without leaving a remainder.

For example:

```text
12 → 1, 2, 3, 4, 6, 12
```

```python
number = 12

for i in range(1, number + 1):
    if number % i == 0:
        print(i)
```

Output:

```text
1
2
3
4
6
12
```

---

## 13. Fibonacci Series

The Fibonacci sequence starts with:

```text
0, 1
```

Every following number is the sum of the previous two.

```text
0, 1, 1, 2, 3, 5, 8, 13...
```

```python
n = 10

a = 0
b = 1

for i in range(n):
    print(a)
    a, b = b, a + b
```

Output:

```text
0
1
1
2
3
5
8
13
21
34
```

---

## 14. Armstrong Number

An **Armstrong number** is a number equal to the sum of its digits raised to the power of the number of digits.

Example:

```text
153

1³ + 5³ + 3³
= 1 + 125 + 27
= 153
```

Therefore, `153` is an Armstrong number.

```python
number = 153
original = number

digits = len(str(number))
total = 0

while number > 0:
    digit = number % 10
    total += digit ** digits
    number //= 10

if total == original:
    print("Armstrong number")
else:
    print("Not an Armstrong number")
```

---

## 15. Perfect Number

A **perfect number** is equal to the sum of its proper divisors.

Example:

```text
6

Proper divisors:
1, 2, 3

1 + 2 + 3 = 6
```

Therefore, `6` is a perfect number.

```python
number = 6
total = 0

for i in range(1, number):
    if number % i == 0:
        total += i

if total == number:
    print("Perfect number")
else:
    print("Not a perfect number")
```

---

## 16. Sum of Natural Numbers

Natural numbers can be represented as:

```text
1, 2, 3, 4, 5, ...
```

To calculate the sum from `1` to `n`:

```python
n = 10
total = 0

for i in range(1, n + 1):
    total += i

print(total)
```

Output:

```text
55
```

### Mathematical formula

```text
sum = n × (n + 1) / 2
```

In Python:

```python
n = 10

total = n * (n + 1) // 2

print(total)
```

---

## 17. Multiplication Table

```python
number = 5

for i in range(1, 11):
    print(number, "x", i, "=", number * i)
```

Output:

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
...
5 x 10 = 50
```

---

## 18. Check Divisibility

A number is divisible by another number when the remainder is `0`.

```python
number = 20

if number % 5 == 0:
    print("Divisible by 5")
else:
    print("Not divisible by 5")
```

The `%` operator is extremely important in number-based problems.

---

## 19. Find the Sum of Numbers in a Range

```python
start = 1
end = 10
total = 0

for i in range(start, end + 1):
    total += i

print(total)
```

Output:

```text
55
```

---

## 20. Find Even Numbers in a Range

```python
for number in range(1, 21):
    if number % 2 == 0:
        print(number)
```

Output:

```text
2
4
6
8
10
12
14
16
18
20
```

---

## 21. Find Odd Numbers in a Range

```python
for number in range(1, 21):
    if number % 2 != 0:
        print(number)
```

---

## 22. Sum of Even Numbers

```python
total = 0

for number in range(1, 11):
    if number % 2 == 0:
        total += number

print(total)
```

Output:

```text
30
```

Because:

```text
2 + 4 + 6 + 8 + 10 = 30
```

---

## 23. Sum of Odd Numbers

```python
total = 0

for number in range(1, 11):
    if number % 2 != 0:
        total += number

print(total)
```

Output:

```text
25
```

Because:

```text
1 + 3 + 5 + 7 + 9 = 25
```

---

## 24. Product of Digits

Instead of adding digits, we can multiply them.

Example:

```text
1234

1 × 2 × 3 × 4 = 24
```

```python
number = 1234
product = 1

while number > 0:
    digit = number % 10
    product *= digit
    number //= 10

print(product)
```

---

## 25. First and Last Digit

For a positive integer:

```python
number = 12345

last_digit = number % 10
first_digit = number

while first_digit >= 10:
    first_digit //= 10

print("First:", first_digit)
print("Last:", last_digit)
```

Output:

```text
First: 1
Last: 5
```

---

## 26. Swap Two Numbers

Python allows swapping without a temporary variable.

```python
a = 10
b = 20

a, b = b, a

print(a)
print(b)
```

Output:

```text
20
10
```

---

## 27. Find the Greatest Common Divisor

The **GCD** is the largest number that divides two numbers without a remainder.

Python provides `math.gcd()`:

```python
import math

a = 24
b = 36

print(math.gcd(a, b))
```

Output:

```text
12
```

---

## 28. Find the Least Common Multiple

The **LCM** is the smallest positive number that is divisible by two numbers.

```python
import math

a = 12
b = 18

print(math.lcm(a, b))
```

Output:

```text
36
```

---

## 29. Number-based Problems Using Functions

Instead of writing all logic directly in the main program, the logic can be placed inside functions.

```python
def is_even(number):
    return number % 2 == 0


number = 10

if is_even(number):
    print("Even")
else:
    print("Odd")
```

This makes the logic **reusable**.

---

## 30. Taking User Input

Number-based problems commonly receive numbers from the user.

```python
number = int(input("Enter a number: "))
```

For multiple numbers:

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))
```

Then the values can be processed using conditions, loops, and operators.

---

# Important Operators for Number Problems

| Operator | Meaning        | Example  | Result |
| -------- | -------------- | -------- | -----: |
| `+`      | Addition       | `5 + 2`  |    `7` |
| `-`      | Subtraction    | `5 - 2`  |    `3` |
| `*`      | Multiplication | `5 * 2`  |   `10` |
| `/`      | Division       | `5 / 2`  |  `2.5` |
| `//`     | Floor division | `5 // 2` |    `2` |
| `%`      | Remainder      | `5 % 2`  |    `1` |
| `**`     | Power          | `5 ** 2` |   `25` |

---

# Important Patterns to Remember

### Extract the last digit

```python
digit = number % 10
```

### Remove the last digit

```python
number //= 10
```

### Check divisibility

```python
number % divisor == 0
```

### Build a reversed number

```python
reverse = reverse * 10 + digit
```

### Accumulate a sum

```python
total += value
```

### Accumulate a product

```python
product *= value
```

---

# General Problem-Solving Approach

When solving a number-based problem, follow these steps:

### 1. Understand the problem

Identify:

* What is the input?
* What is the expected output?
* What mathematical operation is required?
* Are there special cases?

### 2. Identify the required logic

Determine whether you need:

* `if`
* `elif`
* `else`
* `for`
* `while`
* `%`
* `//`
* arithmetic operators
* functions

### 3. Work through a small example

For example, to reverse `123`:

```text
123 → 3
12  → 2
1   → 1

Result → 321
```

### 4. Convert the logic into Python

```python
number = 123
reverse = 0

while number > 0:
    digit = number % 10
    reverse = reverse * 10 + digit
    number //= 10

print(reverse)
```

### 5. Test edge cases

Consider values such as:

```text
0
1
negative numbers
large numbers
repeated digits
single-digit numbers
```

---

# Common Mistakes

### Mistake 1: Using `/` instead of `//`

```python
number /= 10
```

This produces a floating-point value.

For digit extraction problems, you normally want:

```python
number //= 10
```

---

### Mistake 2: Forgetting the original number

In problems such as palindrome and Armstrong numbers, the number is modified during processing.

Store the original:

```python
original = number
```

---

### Mistake 3: Incorrect reverse logic

Incorrect:

```python
reverse += digit
```

Correct:

```python
reverse = reverse * 10 + digit
```

---

### Mistake 4: Incorrect loop boundaries

Remember that:

```python
range(1, number)
```

does not include `number`.

To include it:

```python
range(1, number + 1)
```

---

### Mistake 5: Not considering zero

For example, this logic:

```python
while number > 0:
```

does not execute for `number = 0`.

Always consider whether `0` needs special handling.

---

# Practice Problems

Try solving these without looking at the solution first:

1. Check whether a number is even or odd.
2. Check whether a number is positive, negative, or zero.
3. Find the largest of three numbers.
4. Find the smallest of three numbers.
5. Find the sum of digits.
6. Find the product of digits.
7. Reverse a number.
8. Check whether a number is a palindrome.
9. Count the digits.
10. Find all factors of a number.
11. Check whether a number is prime.
12. Print all prime numbers in a range.
13. Find the factorial of a number.
14. Generate the Fibonacci series.
15. Check whether a number is an Armstrong number.
16. Check whether a number is a perfect number.
17. Find the sum of natural numbers.
18. Find the sum of even numbers in a range.
19. Find the sum of odd numbers in a range.
20. Generate a multiplication table.
21. Find the GCD of two numbers.
22. Find the LCM of two numbers.
23. Find the first and last digit of a number.
24. Count how many times a particular digit occurs.
25. Find the largest digit in a number.

---

# Quick Reference

```text
Even/Odd
    ↓
number % 2

Last digit
    ↓
number % 10

Remove last digit
    ↓
number // 10

Divisibility
    ↓
number % divisor == 0

Reverse
    ↓
reverse = reverse * 10 + digit

Factorial
    ↓
multiply numbers from 1 to n

Prime
    ↓
check whether a number has divisors other than 1 and itself

Palindrome
    ↓
original == reversed

Armstrong
    ↓
sum of powered digits == original

Perfect number
    ↓
sum of proper divisors == original
```

---

# Key Points

* Number-based problems are excellent for developing **programming logic**.
* `%` is particularly important for working with digits and divisibility.
* `//` is commonly used to remove the last digit of an integer.
* `while` loops are useful when processing individual digits.
* `for` loops are useful for ranges and repeated calculations.
* Store the original number when the algorithm modifies the input.
* Functions can make number-based logic reusable.
* Always test edge cases such as `0`, `1`, negative values, and single-digit numbers.

---

# Interview Questions

### 1. How do you check whether a number is even?

```python
number % 2 == 0
```

### 2. What is the difference between `/` and `//`?

`/` performs regular division and returns a floating-point result, while `//` performs floor division.

### 3. How do you extract the last digit of a number?

```python
number % 10
```

### 4. How do you remove the last digit?

```python
number // 10
```

### 5. How do you check whether a number is prime?

Check whether it has any divisor other than `1` and itself.

### 6. Why should you store the original number when reversing it?

Because the original value is modified during the digit-processing loop and may be needed for comparison afterward.

### 7. How can you check whether a number is a palindrome?

Reverse the number and compare it with the original number.

### 8. What is an Armstrong number?

A number whose value equals the sum of its digits raised to the power of the number of digits.

### 9. What is a perfect number?

A number equal to the sum of its proper divisors.

### 10. Why are number-based problems important for beginners?

They provide practice with **variables, operators, conditions, loops, functions, and logical problem-solving**.

[◀Back](.././)
---