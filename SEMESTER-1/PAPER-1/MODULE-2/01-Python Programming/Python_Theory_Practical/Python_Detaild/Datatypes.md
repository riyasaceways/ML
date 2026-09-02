[◀Back](./)
---

# Python Data Types

Python has several built-in data types used to store different kinds of data.

## 1. Numeric Types

| Data Type | Description | Example |
|---|---|---|
| `int` | Whole numbers, positive or negative, without decimals. | `10`, `-5`, `0` |
| `float` | Numbers containing decimal values. | `10.5`, `-3.14` |
| `complex` | Numbers containing a real and imaginary part. | `3 + 4j` |

```python
age = 20
price = 99.99
number = 3 + 4j
```

---

## 2. Boolean Type

| Data Type | Description | Example |
|---|---|---|
| `bool` | Represents one of two logical values: `True` or `False`. | `True`, `False` |

```python
is_student = True
is_logged_in = False
```

---

## 3. Text Type

| Data Type | Description | Example |
|---|---|---|
| `str` | A sequence of characters used to store text. | `"Python"` |

```python
name = "Riyas"
message = "Hello, Python!"
```

---

## 4. Sequence Types

| Data Type | Description | Example |
|---|---|---|
| `list` | Ordered and mutable collection of items. | `[1, 2, 3]` |
| `tuple` | Ordered and immutable collection of items. | `(1, 2, 3)` |
| `range` | Represents a sequence of numbers, commonly used with loops. | `range(5)` |

```python
numbers = [10, 20, 30]

coordinates = (10, 20)

numbers_range = range(5)
```

---

## 5. Set Types

| Data Type | Description | Example |
|---|---|---|
| `set` | Unordered collection of unique items. | `{1, 2, 3}` |
| `frozenset` | Immutable version of a set. | `frozenset({1, 2, 3})` |

```python
numbers = {1, 2, 3, 3}

unique_numbers = frozenset({1, 2, 3})
```

> A `set` automatically removes duplicate values.

---

## 6. Mapping Type

| Data Type | Description | Example |
|---|---|---|
| `dict` | Stores data as **key-value pairs**. | `{"name": "Riyas"}` |

```python
student = {
    "name": "Riyas",
    "age": 20
}
```

---

## 7. Binary Types

| Data Type | Description | Example |
|---|---|---|
| `bytes` | Immutable sequence of bytes. | `b"Hello"` |
| `bytearray` | Mutable sequence of bytes. | `bytearray(5)` |
| `memoryview` | Provides access to the memory of binary data without copying it. | `memoryview(b"Hello")` |

```python
data = b"Hello"

mutable_data = bytearray(5)

view = memoryview(b"Hello")
```

---

## 8. None Type

| Data Type | Description | Example |
|---|---|---|
| `NoneType` | Represents the absence of a value. Its only value is `None`. | `None` |

```python
result = None
```

---

# Complete Built-in Data Types

| Category | Data Types |
|---|---|
| **Numeric** | `int`, `float`, `complex` |
| **Boolean** | `bool` |
| **Text** | `str` |
| **Sequence** | `list`, `tuple`, `range` |
| **Set** | `set`, `frozenset` |
| **Mapping** | `dict` |
| **Binary** | `bytes`, `bytearray`, `memoryview` |
| **None** | `NoneType` |

---

# Quick Examples

```python
# Numeric
integer_value = 10
float_value = 10.5
complex_value = 3 + 4j

# Boolean
is_active = True

# Text
name = "Riyas"

# Sequence
numbers = [1, 2, 3]
coordinates = (10, 20)
number_range = range(5)

# Set
unique_numbers = {1, 2, 3}
fixed_numbers = frozenset({1, 2, 3})

# Mapping
student = {"name": "Riyas", "age": 20}

# Binary
data = b"Hello"
mutable_data = bytearray(5)
view = memoryview(data)

# None
result = None
```

---

# Checking the Data Type

Use the `type()` function to determine the type of a value.

```python
age = 20
print(type(age))
```

Output:

```text
<class 'int'>
```

You can also check different values:

```python
print(type(10))          # int
print(type(10.5))        # float
print(type(3 + 4j))      # complex
print(type("Python"))    # str
print(type(True))        # bool
print(type([1, 2, 3]))   # list
print(type((1, 2, 3)))   # tuple
print(type({1, 2, 3}))   # set
print(type({"a": 1}))    # dict
print(type(None))        # NoneType
```

---

## Interview Tip

**Q: How many built-in data types does Python have?**

Python's built-in types are commonly grouped into these categories:

- Numeric
- Boolean
- Text
- Sequence
- Set
- Mapping
- Binary
- None

The commonly listed built-in types are:

```text
int
float
complex
bool
str
list
tuple
range
set
frozenset
dict
bytes
bytearray
memoryview
NoneType
```

[◀Back](./)
---