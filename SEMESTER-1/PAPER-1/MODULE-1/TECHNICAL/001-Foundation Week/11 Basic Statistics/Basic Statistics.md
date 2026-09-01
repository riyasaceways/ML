[◀ Back to Index](../../../../../../README.md) &emsp; | &emsp;[◀ Back](./)

---

# Basic Statistics

These are basic statistical concepts used to **summarize, understand, and measure data**. They are important in ML because we often need to understand a dataset before training a model.

## 1. Mean

The **mean** is the average of a set of numbers.

Add all the values together and divide by the number of values.

```text
Data: 2, 4, 6, 8

Mean = (2 + 4 + 6 + 8) / 4
     = 20 / 4
     = 5
```

**Remember:** Mean = **average**.

---

## 2. Median

The **median** is the middle value when the data is arranged in ascending or descending order.

For an odd number of values:

```text
Data: 2, 4, 6, 8, 10

Median = 6
```

For an even number of values, take the average of the two middle values:

```text
Data: 2, 4, 6, 8

Median = (4 + 6) / 2
       = 5
```

**Remember:** Median = **middle value**.

---

## 3. Mode

The **mode** is the value that appears most frequently in a dataset.

```text
Data: 2, 3, 3, 4, 5, 3, 6

Mode = 3
```

Because `3` appears three times.

A dataset can have:

* One mode
* More than one mode
* No mode

**Remember:** Mode = **most frequently occurring value**.

---

## 4. Variance

**Variance** measures how spread out the values are from the mean.

If values are close to the mean, the variance is smaller.

If values are far from the mean, the variance is larger.

For population data:

```text
Variance = Σ(x - μ)² / N
```

Where:

* `x` = each value
* `μ` = mean
* `N` = number of values

The differences from the mean are **squared**, so negative and positive differences don't cancel each other.

genui{"learning_viz":{"type_id":"VARIANCE"}}

**Remember:** Variance = **measure of spread using squared differences from the mean**.

---

## 5. Standard Deviation

**Standard deviation** also measures how spread out the data is around the mean.

It is the **square root of variance**.

```text
Standard Deviation = √Variance
```

A small standard deviation means the values are generally close to the mean.

A large standard deviation means the values are more spread out.

genui{"learning_viz":{"type_id":"STANDARD_DEVIATION"}}

Example:

```text
Data A: 9, 10, 11
```

The values are close together, so the standard deviation is small.

```text
Data B: 1, 10, 19
```

The values are more spread out, so the standard deviation is larger.

**Remember:** Standard deviation = **how far values typically spread from the mean**.

---

## 6. Range & Quartiles

### Range

The **range** shows the difference between the largest and smallest values.

```text
Data: 2, 4, 6, 8, 10

Range = 10 - 2
      = 8
```

**Remember:** Range = **maximum − minimum**.

### Quartiles

**Quartiles** divide ordered data into four parts.

* **Q1** → first quartile, around 25% of the data is below it
* **Q2** → second quartile, the median
* **Q3** → third quartile, around 75% of the data is below it

The **Interquartile Range (IQR)** is:

```text
IQR = Q3 - Q1
```

The IQR describes the spread of the **middle 50%** of the data.

**Remember:**

```text
Q1 → 25%
Q2 → 50% → Median
Q3 → 75%

IQR = Q3 - Q1
```

### Quick memory

```text
Mean       → Average
Median     → Middle
Mode       → Most frequent
Variance   → Squared spread
Std Dev    → Spread around mean
Range      → Max - Min
Quartiles  → Divide data into four parts
```



---

[◀ Back to Index](../../../../../../README.md) &emsp; | &emsp;[◀ Back](./)