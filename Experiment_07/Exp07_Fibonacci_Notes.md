# Experiment 07 — Fibonacci Series Using Loops | Notes

---

## What is the Fibonacci Sequence?

The **Fibonacci sequence** is a series where each number is the sum of the two numbers before it.

```
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ...
```

Mathematically:
- F(0) = 0
- F(1) = 1
- F(n) = F(n-1) + F(n-2) for n ≥ 2

---

## Iterative Approach (Efficient)

```python
a, b = 0, 1       # start with first two terms

for _ in range(n):
    print(a, end=" ")
    a, b = b, a + b   # advance: a becomes b, b becomes a+b
```

**Trace for n = 5:**
| Iteration | a | b | printed |
|-----------|---|---|---------|
| 1 | 0 | 1 | 0 |
| 2 | 1 | 1 | 1 |
| 3 | 1 | 2 | 1 |
| 4 | 2 | 3 | 2 |
| 5 | 3 | 5 | 3 |

**Output:** `0 1 1 2 3`

---

## How `a, b = b, a + b` Works

Python evaluates the **right side** completely before assigning:

```python
a, b = 0, 1
a, b = b, a + b
# Right side: b=1, a+b=0+1=1
# Assignment: a=1, b=1
```

This simultaneous assignment avoids needing a temporary variable.

---

## Recursive Approach (Simple but Slower)

```python
def fibonacci(n):
    if n <= 0: return 0
    if n == 1: return 1
    return fibonacci(n - 1) + fibonacci(n - 2)

for i in range(8):
    print(fibonacci(i), end=" ")
# Output: 0 1 1 2 3 5 8 13
```

> **Warning:** Recursion has exponential time complexity O(2ⁿ) without memoization. The iterative approach is O(n).

---

## Fibonacci in a List

```python
def fibonacci_list(n):
    series = [0, 1]
    while len(series) < n:
        series.append(series[-1] + series[-2])
    return series[:n]

print(fibonacci_list(8))  # [0, 1, 1, 2, 3, 5, 8, 13]
```

---

## Key Points to Remember

- The Fibonacci series starts with `0, 1` (not `1, 1`).
- Iterative approach is preferred for large `n` — it runs in O(n) time and O(1) space.
- `a, b = b, a + b` is idiomatic Python — right side is fully evaluated before assignment.
- `_` as a loop variable signals that the loop counter is intentionally unused.
- The ratio F(n+1)/F(n) converges to the **Golden Ratio** φ ≈ 1.618.
