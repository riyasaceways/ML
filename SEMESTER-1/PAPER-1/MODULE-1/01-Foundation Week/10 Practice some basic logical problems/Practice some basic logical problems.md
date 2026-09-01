[◀ Back to Index](../../../../../README.md) &emsp; | &emsp;[◀ Back](./)

---

# Practice Some Basic Logical Problems

The goal of these problems is to improve my **problem-solving and programming logic** before moving into more advanced ML programming.

## 1. Prime Numbers

A **prime number** is a whole number greater than `1` that has exactly **two factors**: `1` and itself.

Examples:

```text
2, 3, 5, 7, 11, 13, 17, 19
```

For example, `7` is prime because it can only be divided evenly by:

```text
1 × 7
```

But `8` is not prime because it has more than two factors:

```text
1 × 8
2 × 4
```

### Basic logic

To check whether a number is prime:

```text
1. Take a number.
2. Check whether it is greater than 1.
3. Try dividing it by possible numbers.
4. If it is divisible by another number, it is not prime.
5. If no divisor is found, it is prime.
```

### Python practice

```python
number = int(input("Enter a number: "))

if number > 1:
    is_prime = True

    for i in range(2, number):
        if number % i == 0:
            is_prime = False
            break

    if is_prime:
        print("Prime number")
    else:
        print("Not a prime number")
else:
    print("Not a prime number")
```

**Important:** `1` is **not** a prime number.

---

## 2. Unique Numbers

A **unique number** in a collection means a number that occurs only once.

For example:

```text
Input:  [1, 2, 3, 2, 4, 1, 5]

Unique numbers:
3, 4, 5
```

Here:

```text
1 → appears twice
2 → appears twice
3 → appears once
4 → appears once
5 → appears once
```

So `3`, `4`, and `5` are unique.

### Basic logic

```text
1. Take a collection of numbers.
2. Look at each number.
3. Count how many times it appears.
4. If it appears exactly once, it is unique.
5. Store or print that number.
```

### Python practice

```python
numbers = [1, 2, 3, 2, 4, 1, 5]

for number in numbers:
    if numbers.count(number) == 1:
        print(number)
```

Output:

```text
3
4
5
```

### Another approach using a dictionary

```python
numbers = [1, 2, 3, 2, 4, 1, 5]

counts = {}

for number in numbers:
    counts[number] = counts.get(number, 0) + 1

for number, count in counts.items():
    if count == 1:
        print(number)
```

This approach is useful because **counting occurrences** is a common programming problem.

---

## Practice Goal

I should not just memorize the code. I should be able to explain the logic in my own words:

```text
Prime number
→ Check whether a number has only two factors.

Unique number
→ Check whether a number occurs only once.
```

The main purpose of these exercises is to practice **conditions, loops, operators, lists, counting, and logical thinking**.


---

[◀ Back to Index](../../../../../README.md) &emsp; | &emsp;[◀ Back](./)