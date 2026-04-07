# Experiment 05 — Exponentiation (Power of a Number) | Notes

---

## What is Exponentiation?

Exponentiation means multiplying a number by itself a given number of times.

$$2^3 = 2 \times 2 \times 2 = 8$$

In Python, use the `**` operator:
```python
2 ** 3    # → 8
```

---

## Three Ways to Calculate Power in Python

### 1. `**` operator (most common)
```python
base = 2
exp  = 10
print(base ** exp)    # → 1024
```

### 2. Built-in `pow()`
```python
print(pow(2, 10))     # → 1024
print(pow(2, 10, 1000))  # → 24  (modular: 1024 % 1000)
```

### 3. `math.pow()`
```python
import math
print(math.pow(2, 10))  # → 1024.0  (always float)
```

---

## Special Cases

```python
5 ** 0      # → 1     (any number to the power 0 is 1)
0 ** 0      # → 1     (Python convention)
2 ** -1     # → 0.5   (negative exponent = reciprocal)
2 ** -3     # → 0.125
4 ** 0.5    # → 2.0   (fractional exponent = root)
8 ** (1/3)  # → 2.0   (cube root)
```

---

## `pow(base, exp, mod)` — Modular Exponentiation

```python
pow(2, 10, 1000)   # computes (2**10) % 1000 = 1024 % 1000 = 24
```
This three-argument form is efficient for **cryptography** (RSA algorithm) because it avoids computing huge intermediate numbers.

---

## Comparison Table

| Method | Returns | Modular Support | Notes |
|--------|---------|-----------------|-------|
| `x ** y` | int or float | No | Fastest, most Pythonic |
| `pow(x, y)` | int or float | Yes (`pow(x,y,mod)`) | Built-in, no import |
| `math.pow(x, y)` | float always | No | Requires `import math` |

---

## Key Points to Remember

- `**` is the Pythonic way to compute powers — prefer it over `math.pow()` for everyday use.
- `x ** 0 == 1` for all `x` (including `x = 0` in Python).
- Negative exponents give fractional results: `2 ** -n == 1 / 2**n`.
- `pow(b, e, m)` is the most efficient way to compute modular exponentiation.
