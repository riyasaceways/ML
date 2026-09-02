[◀Back](.././)
---

# Nested Conditions in Python

## 1. What are Nested Conditions?

**Nested conditions** are conditional statements placed inside another conditional statement.

In other words, an `if`, `elif`, or `else` block can contain another conditional statement.

Nested conditions are useful when a decision has **multiple levels**.

### Basic structure

```python
if condition1:
    if condition2:
        # code
    else:
        # code
else:
    # code
```

The inner condition is evaluated only when the outer condition allows execution to reach it.

---

## 2. Simple Example

```python
age = 20

if age >= 18:
    if age >= 60:
        print("Senior citizen")
    else:
        print("Adult")
else:
    print("Minor")
```

Output:

```text
Adult
```

### Execution flow

```text
age >= 18?
│
├── False → Minor
│
└── True
     │
     └── age >= 60?
          ├── True  → Senior citizen
          └── False → Adult
```

---

## 3. Outer and Inner Conditions

Nested conditions contain at least two levels of decision-making.

```python
if outer_condition:
    if inner_condition:
        print("Both conditions are satisfied.")
```

* **Outer condition** — The first condition that is checked.
* **Inner condition** — The condition inside the outer block.

Example:

```python
age = 25
has_id = True

if age >= 18:
    if has_id:
        print("Access granted.")
```

The inner condition is checked only if:

```python
age >= 18
```

is `True`.

---

## 4. Nested `if-else`

An inner condition can also have an `else` block.

```python
age = 20
has_id = False

if age >= 18:
    if has_id:
        print("Access granted.")
    else:
        print("ID is required.")
else:
    print("You are underage.")
```

Output:

```text
ID is required.
```

The program first checks the age. Since the person is an adult, it then checks whether they have an ID.

---

## 5. Nested `if-elif-else`

Nested conditions can also contain multiple branches.

```python
mark = 85

if mark >= 50:
    if mark >= 90:
        print("Grade A")
    elif mark >= 75:
        print("Grade B")
    else:
        print("Grade C")
else:
    print("Fail")
```

Output:

```text
Grade B
```

---

## 6. Multiple Levels of Nesting

A condition can contain another condition, which can contain another condition.

```python
age = 25
has_id = True
is_member = True

if age >= 18:
    if has_id:
        if is_member:
            print("Member access granted.")
        else:
            print("Membership required.")
    else:
        print("ID is required.")
else:
    print("You are underage.")
```

The execution follows a hierarchy:

```text
Age check
   │
   ├── Underage
   │
   └── Adult
        │
        ├── No ID
        │
        └── Has ID
             │
             ├── Not a member
             │
             └── Member → Access granted
```

Although Python allows multiple levels of nesting, excessive nesting can make code difficult to read.

---

## 7. Nested Conditions with Logical Operators

Sometimes nested conditions can be replaced by logical operators.

### Nested version

```python
age = 25
has_id = True

if age >= 18:
    if has_id:
        print("Access granted.")
```

### Combined version

```python
if age >= 18 and has_id:
    print("Access granted.")
```

Both can produce the same result.

The combined version is often simpler when the conditions are directly related.

---

## 8. When to Use Nested Conditions

Nested conditions are useful when:

* The second condition depends on the first condition.
* Different levels of validation are required.
* A decision needs to be broken into logical stages.
* The inner condition should not be checked unless the outer condition is satisfied.

### Example

```python
username = "admin"
password = "1234"

if username == "admin":
    if password == "1234":
        print("Login successful.")
    else:
        print("Incorrect password.")
else:
    print("Unknown username.")
```

Here, the password is checked only after the username is recognized.

---

## 9. Nested Conditions with User Input

Nested conditions are commonly used with user input.

```python
age = int(input("Enter your age: "))

if age >= 18:
    has_license = input("Do you have a driving license? ")

    if has_license == "yes":
        print("You can drive.")
    else:
        print("You need a driving license.")
else:
    print("You are too young to drive.")
```

The second input is requested only when the user is at least 18.

---

## 10. Nested Conditions and Indentation

Python uses indentation to determine which statements belong to each condition.

Correct:

```python
if age >= 18:
    if has_id:
        print("Access granted.")
```

The second `if` belongs to the first `if`.

Incorrect indentation can change the meaning of the program or cause an error.

```python
if age >= 18:
    if has_id:
    print("Access granted.")
```

The `print()` statement must be indented inside the inner condition.

---

## 11. Nested Conditions vs `elif`

Nested conditions and `elif` solve different types of problems.

### Nested condition

```python
if age >= 18:
    if has_id:
        print("Access granted.")
```

The second decision depends on the first decision.

### `elif`

```python
if age >= 60:
    print("Senior")
elif age >= 18:
    print("Adult")
else:
    print("Minor")
```

Here, Python is choosing between alternative conditions at the same level.

### Simple distinction

| Nested condition                           | `elif`                                  |
| ------------------------------------------ | --------------------------------------- |
| Decision inside another decision           | Alternative condition at the same level |
| Inner condition depends on outer condition | Conditions are checked sequentially     |
| Creates multiple levels                    | Keeps decisions at the same level       |

---

## 12. Nested Conditions vs Logical Operators

Consider:

```python
if age >= 18:
    if has_id:
        print("Access granted.")
```

This can often be simplified to:

```python
if age >= 18 and has_id:
    print("Access granted.")
```

Use a logical operator when the conditions form one simple combined condition.

Use nesting when the second decision has its own logic or should happen only after the first decision.

---

## 13. Practical Example: ATM Withdrawal

```python
balance = 5000
withdraw = 2000
pin_correct = True

if pin_correct:
    if withdraw <= balance:
        print("Withdrawal successful.")
        balance -= withdraw
    else:
        print("Insufficient balance.")
else:
    print("Incorrect PIN.")
```

The program first checks the PIN.

Only if the PIN is correct does it check the account balance.

---

## 14. Practical Example: Exam Eligibility

```python
attendance = 80
assignment_completed = True

if attendance >= 75:
    if assignment_completed:
        print("Eligible for the exam.")
    else:
        print("Complete the assignment first.")
else:
    print("Attendance requirement not met.")
```

This demonstrates a decision hierarchy:

```text
Attendance check
      │
      ├── Less than 75% → Not eligible
      │
      └── 75% or more
            │
            ├── Assignment incomplete → Complete assignment
            │
            └── Assignment complete → Eligible
```

---

## 15. Practical Example: Shopping Discount

```python
amount = 5000
is_member = True

if amount >= 3000:
    if is_member:
        print("20% discount")
    else:
        print("10% discount")
else:
    print("No discount")
```

The membership status is relevant only after the purchase amount qualifies for a discount.

---

## 16. Common Mistakes

### Mistake 1: Excessive Nesting

Avoid unnecessarily deep nesting.

```python
if condition1:
    if condition2:
        if condition3:
            if condition4:
                print("Something")
```

Too many levels can make code difficult to understand.

When appropriate, conditions can be combined:

```python
if condition1 and condition2 and condition3 and condition4:
    print("Something")
```

---

### Mistake 2: Incorrect Indentation

Incorrect:

```python
if age >= 18:
    if has_id:
    print("Access granted.")
```

Correct:

```python
if age >= 18:
    if has_id:
        print("Access granted.")
```

---

### Mistake 3: Unnecessary Nesting

This:

```python
if age >= 18:
    if has_id:
        print("Access granted.")
```

can be simplified to:

```python
if age >= 18 and has_id:
    print("Access granted.")
```

When the nested structure does not add useful logic, combining conditions can make the code clearer.

---

## 17. Key Points to Remember

* **Nested conditions** are conditions placed inside other conditions.
* The inner condition is checked only when execution reaches it.
* Indentation determines the nesting structure in Python.
* Nested conditions are useful for dependent decisions.
* Nested conditions can contain `if`, `elif`, and `else`.
* Logical operators such as `and` can sometimes replace nesting.
* Avoid unnecessary or excessive nesting.
* Use nesting when it makes the decision-making logic easier to understand.

---

## 18. Interview Questions

### 1. What are nested conditions?

Nested conditions are conditional statements placed inside another conditional statement.

### 2. Why are nested conditions used?

They are used when one decision depends on the result of another decision.

### 3. Can an `if` statement be placed inside another `if` statement?

Yes.

```python
if condition1:
    if condition2:
        print("Both conditions are true.")
```

### 4. Can nested conditions contain `else`?

Yes.

```python
if condition1:
    if condition2:
        print("True")
    else:
        print("False")
```

### 5. Can nested conditions be replaced with logical operators?

Sometimes. For simple dependent conditions, `and` or other logical operators can often provide a simpler alternative.

### 6. What is the main problem with excessive nesting?

Excessive nesting can make code harder to read, understand, maintain, and debug.


[◀Back](.././)
---