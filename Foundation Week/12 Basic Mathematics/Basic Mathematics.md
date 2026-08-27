[◀ Back to Index](../../README.md) &emsp; | &emsp;[◀ Back](./)

---

# Basic Mathematics

These are basic mathematical concepts I need for understanding machine learning. The main topics are **vectors, matrices, and probability**.

---

## 1. Vectors

A **vector** is an ordered collection of numbers.

Example:

```text
A = [2, 4, 6]
```

A vector can represent multiple values together. In ML, vectors are commonly used to represent **features** of a data point.

For example:

```text
Student = [age, height, marks]

Student = [20, 175, 85]
```

Here, the vector contains three features.

### Vector Addition

Two vectors can be added when they have the same number of elements.

```text
A = [1, 2, 3]
B = [4, 5, 6]

A + B = [1+4, 2+5, 3+6]

      = [5, 7, 9]
```

The elements are added **position by position**.

### Vector Multiplication

There are different types of vector multiplication. A basic one is the **dot product**.

```text
A = [1, 2, 3]
B = [4, 5, 6]

A · B = (1×4) + (2×5) + (3×6)

      = 4 + 10 + 18

      = 32
```

**Remember:**

```text
Vector
→ Ordered collection of numbers

Vector addition
→ Add corresponding elements

Dot product
→ Multiply corresponding elements and add the results
```

---

# 2. Matrices

A **matrix** is a rectangular arrangement of numbers organized into **rows and columns**.

Example:

```text
A = | 1  2 |
    | 3  4 |
```

This matrix has:

```text
2 rows × 2 columns
```

So its size is **2 × 2**.

Matrices are important in ML because datasets, transformations, and many mathematical operations can be represented using matrices.

### Matrix Addition

Matrices can be added when they have the **same dimensions**.

```text
A = | 1  2 |       B = | 5  6 |
    | 3  4 |           | 7  8 |
```

Add corresponding positions:

```text
A + B = | 1+5  2+6 |
        | 3+7  4+8 |

      = | 6   8 |
        | 10 12 |
```

### Matrix Multiplication

Matrix multiplication is different from simple element-by-element multiplication.

For example:

```text
A = | 1  2 |
    | 3  4 |

B = | 5  6 |
    | 7  8 |
```

To calculate `A × B`, multiply rows of `A` with columns of `B`:

```text
A × B = | (1×5)+(2×7)  (1×6)+(2×8) |
        | (3×5)+(4×7)  (3×6)+(4×8) |

      = | 19  22 |
        | 43  50 |
```

**Important:** For matrix multiplication, the number of **columns in the first matrix** must equal the number of **rows in the second matrix**.

---

# 3. Basic Probability

**Probability** measures how likely an event is to happen.

Its value is between:

```text
0 → Impossible
1 → Certain
```

It can also be represented as a percentage:

```text
0.5 = 50%
```

The basic formula is:

```text
Probability = Favorable outcomes / Total possible outcomes
```

### Example

For a fair six-sided die, the probability of rolling a `4` is:

```text
Favorable outcomes = 1
Total outcomes = 6

P(4) = 1/6
```

So there is a `1/6` probability of rolling a `4`.

---

## 4. Independent Events

Two events are **independent** when the outcome of one event does not affect the outcome of the other.

Example:

**Tossing a coin twice.**

The result of the first toss does not change the probability of the second toss.

For independent events:

```text
P(A and B) = P(A) × P(B)
```

Example:

```text
P(Heads) = 1/2

P(Heads twice)
= 1/2 × 1/2
= 1/4
```

---

## 5. Dependent Events

Two events are **dependent** when the outcome of one event affects the probability of the other.

Example:

A bag contains:

```text
3 red balls
2 blue balls
```

You take one ball **without replacing it**.

If the first ball is red, there are now fewer red balls available. Therefore, the probability of getting red on the second draw has changed.

For dependent events:

```text
P(A and B) = P(A) × P(B | A)
```

`P(B | A)` means the probability of event B **given that A has already happened**.

### Independent vs Dependent

```text
Independent
→ One event does NOT affect another.

Dependent
→ One event DOES affect another.
```

### Quick memory

```text
Vector       → Ordered collection of numbers
Matrix       → Numbers arranged in rows and columns

Vector add   → Add corresponding elements
Matrix add   → Add corresponding elements
Matrix ×     → Row × column

Probability  → How likely something is

Independent  → Events don't affect each other
Dependent    → One event affects another
```


---

[◀ Back to Index](../../README.md) &emsp; | &emsp;[◀ Back](./)