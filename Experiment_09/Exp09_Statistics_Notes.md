# Experiment 09 — Mean, Median, and Mode | Notes

---

## What are Measures of Central Tendency?

These three statistics describe the **"centre"** of a dataset in different ways:

| Measure | Best for | Sensitive to outliers? |
|---------|----------|----------------------|
| **Mean** | Normally distributed data | Yes — a single extreme value shifts it |
| **Median** | Skewed distributions | No — not affected by extremes |
| **Mode** | Categorical or discrete data | No |

---

## Calculating Mean

$$\bar{x} = \frac{\sum x_i}{n}$$

```python
data = [1, 2, 2, 3, 4, 7, 9]

# Using statistics module
import statistics
print(statistics.mean(data))   # 4

# Manual calculation
print(sum(data) / len(data))   # 4.0
```

---

## Calculating Median

Sort the data, then find the middle value.

```python
# Odd number of elements → single middle value
data_odd = [1, 2, 3, 4, 5]
# Sorted: 1 2 [3] 4 5  → Median = 3

# Even number of elements → average of two middle values
data_even = [1, 2, 3, 4]
# Sorted: 1 [2, 3] 4  → Median = (2+3)/2 = 2.5

import statistics
print(statistics.median([1, 2, 2, 3, 4, 7, 9]))  # 3
```

---

## Calculating Mode

The value that appears **most frequently**.

```python
import statistics

data = [1, 2, 2, 3, 4, 7, 9]
print(statistics.mode(data))        # 2  (appears twice)

# Python 3.8+ — all modes
data2 = [1, 1, 2, 2, 3]
print(statistics.multimode(data2))  # [1, 2]
```

---

## Manual Implementations

```python
data = [1, 2, 2, 3, 4, 7, 9]

# Mean
mean = sum(data) / len(data)

# Median
sorted_data = sorted(data)
n = len(sorted_data)
if n % 2 == 1:
    median = sorted_data[n // 2]
else:
    median = (sorted_data[n // 2 - 1] + sorted_data[n // 2]) / 2

# Mode (using a dictionary to count frequencies)
freq = {}
for x in data:
    freq[x] = freq.get(x, 0) + 1
mode = max(freq, key=freq.get)

print(f"Mean: {mean}, Median: {median}, Mode: {mode}")
```

---

## Key Points to Remember

- `statistics.mean()` returns an exact `Fraction` or `int` for integer data; use `statistics.fmean()` for a float result.
- `statistics.median()` automatically handles both odd and even list sizes.
- `statistics.mode()` in Python < 3.8 raises `StatisticsError` when there is no unique mode.
- The `statistics` module is part of the standard library — no installation needed.
- For large-scale data analysis, prefer `numpy` and `scipy` over the `statistics` module.
