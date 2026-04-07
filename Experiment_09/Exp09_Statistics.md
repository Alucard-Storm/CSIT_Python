# Experiment 09 — Mean, Median, and Mode of a List

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To perform statistical computations — mean, median, and mode — on a list of numbers using the `statistics` module.

## 2. Theory

| Measure | Definition | Formula |
|---------|------------|---------|
| **Mean** | Arithmetic average of all values | Sum ÷ Count |
| **Median** | Middle value when data is sorted | Middle element (or average of two middle elements) |
| **Mode** | Most frequently occurring value | Value with highest frequency |

- `statistics.mean(data)` returns the arithmetic mean.
- `statistics.median(data)` returns the median (handles both odd and even list sizes).
- `statistics.mode(data)` returns the single most common value; raises `StatisticsError` if no unique mode exists (Python < 3.8).
- Python 3.8+ added `statistics.multimode(data)` which returns all modes as a list.

## 3. Implementation Code

```python
import statistics

data = [1, 2, 2, 3, 4, 7, 9]
print("Data:", data)
print("Mean:", statistics.mean(data))
print("Median:", statistics.median(data))
print("Mode:", statistics.mode(data))
```

## 4. Expected Output

```text
Data: [1, 2, 2, 3, 4, 7, 9]
Mean: 4
Median: 3
Mode: 2
```

## 5. Viva / Discussion Questions

1. **Mean vs Median:** When is the median a better measure of central tendency than the mean? Give an example.
2. **Mode of uniform data:** What happens when `statistics.mode()` is called on `[1, 2, 3, 4]` in Python 3.8+?
3. **Manual mean:** Write a one-line expression to compute the mean without importing `statistics`.
4. **Even list median:** How is the median calculated when the list has an even number of elements? Verify with an example.
5. **`statistics` module:** Name two other statistical functions available in the `statistics` module besides `mean`, `median`, and `mode`.

---

[Back to Main Index](../README.md)
