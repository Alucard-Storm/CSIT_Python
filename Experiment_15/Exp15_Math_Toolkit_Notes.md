# Experiment 15 — Mathematical Utility Toolkit | Notes

---

## What is a Utility Toolkit?

A **utility toolkit** (or utility library) groups related, reusable functions in one place. Instead of rewriting prime-check logic every time, you define `is_prime()` once and call it wherever needed.

This is the foundation of **modular programming** and the basis of Python's own standard library.

---

## `is_prime(n)` — Trial Division

```python
def is_prime(n):
    if n < 2: return False                       # 0 and 1 are not prime
    for i in range(2, int(n**0.5) + 1):          # check up to √n
        if n % i == 0: return False              # divisible → not prime
    return True                                  # no divisors found → prime
```

**Why √n?** If n has a factor > √n, then the complementary factor must be < √n — so we'd have already found it.

---

## `factorial(n)` — Recursion

$$n! = n \times (n-1) \times (n-2) \times \ldots \times 1$$

```python
def factorial(n):
    if n == 0 or n == 1: return 1       # base case
    return n * factorial(n - 1)          # recursive case

# Call stack for factorial(4):
# factorial(4) = 4 * factorial(3)
#                    = 3 * factorial(2)
#                         = 2 * factorial(1)
#                              = 1
# Result: 4 * 3 * 2 * 1 = 24
```

> Python's recursion limit is ~1000 by default. For large n, use `math.factorial()` or an iterative approach.

---

## `fibonacci(n)` — Iterative List Building

```python
def fibonacci(n):
    series = [0, 1]
    while len(series) < n:
        series.append(series[-1] + series[-2])
    return series[:n]
```

**Edge cases:**
```python
fibonacci(0)  # []      (slice [:0] of [0,1] is [])
fibonacci(1)  # [0]     (slice [:1] of [0,1] is [0])
fibonacci(2)  # [0, 1]  (no loop needed)
fibonacci(7)  # [0, 1, 1, 2, 3, 5, 8]
```

---

## `power(base, exp)` — The `**` Operator

```python
def power(base, exp):
    return base ** exp

power(2, 10)    # 1024
power(2, -1)    # 0.5
power(4, 0.5)   # 2.0  (square root)
```

---

## Comparing Approaches

| Operation | Custom | Built-in |
|-----------|--------|---------|
| Prime check | `is_prime(n)` | No direct built-in |
| Factorial | `factorial(n)` | `math.factorial(n)` |
| Fibonacci | `fibonacci(n)` | No direct built-in |
| Power | `base ** exp` | `pow(base, exp)` |

Use **built-in / standard library** whenever available — they are faster, tested, and handle edge cases.

---

## Key Points to Remember

- **Recursion** needs a base case — without it, the function calls itself forever until `RecursionError`.
- `math.factorial()` is faster than recursive implementation for large n (uses C under the hood).
- Iterative Fibonacci is O(n) time, O(n) space; recursive Fibonacci without memoization is O(2ⁿ).
- Organizing related functions together is the first step toward writing a Python **module** (`.py` file that others can `import`).
