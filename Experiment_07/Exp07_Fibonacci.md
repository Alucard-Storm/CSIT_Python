# Experiment 07 — Fibonacci Series Using Loops

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To generate the Fibonacci series using iterative logic and control flow.

## 2. Theory

| Concept | Description |
|---------|-------------|
| **Fibonacci sequence** | Each number is the sum of the two preceding ones: 0, 1, 1, 2, 3, 5, 8, … |
| **`for` loop** | Repeats a block a fixed number of times using `range()` |
| **Multiple assignment** | `a, b = b, a + b` swaps and updates two variables in one statement |
| **`end=" "`** | `print()` parameter that replaces the default newline with a space |

- The sequence starts with `a = 0` and `b = 1`.
- Each iteration: print `a`, then advance with `a, b = b, a + b`.
- `range(n)` generates numbers from `0` to `n-1`, producing exactly `n` iterations.

## 3. Implementation Code

```python
n = int(input("Enter number of terms: "))
a, b = 0, 1
print("Fibonacci Series:")
for _ in range(n):
    print(a, end=" ")
    a, b = b, a + b
print()
```

## 4. Expected Output

```text
Enter number of terms: 5
Fibonacci Series:
0 1 1 2 3
```

```text
Enter number of terms: 8
Fibonacci Series:
0 1 1 2 3 5 8 13
```


---

[Back to Main Index](../README.md)
