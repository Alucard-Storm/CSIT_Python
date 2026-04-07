# Experiment 04 — Square Root of a Number | Notes

---

## What is the `math` Module?

Python's **standard library** ships with many pre-built modules. The `math` module provides access to common mathematical functions — you don't reinvent the wheel.

```python
import math         # Load the entire math module
print(math.sqrt(9)) # Use with the module prefix
```

Or import just the function you need:
```python
from math import sqrt
print(sqrt(9))      # No prefix needed
```

---

## `math.sqrt()` in Detail

```python
import math

math.sqrt(16)     # → 4.0     (perfect square)
math.sqrt(2)      # → 1.4142135623730951
math.sqrt(0)      # → 0.0
math.sqrt(-1)     # → ValueError: math domain error
```

> `math.sqrt()` always returns a **float**, even for perfect squares.

---

## Alternative: The `**` Operator

```python
16 ** 0.5    # → 4.0   (same result)
2  ** 0.5    # → 1.4142135623730951
```

Both approaches are equivalent for non-negative numbers. `math.sqrt()` is slightly faster for large numbers and more readable when intent is clear.

---

## Handling Negative Input

```python
import math

num = float(input("Enter a number: "))
if num < 0:
    print("Square root of a negative number is not real.")
else:
    print(f"Square root of {num} is {math.sqrt(num)}")
```

For complex square roots, use Python's built-in `cmath` module:
```python
import cmath
print(cmath.sqrt(-1))  # → 1j
```

---

## Useful `math` Constants and Functions

| Name | Description | Example |
|------|-------------|---------|
| `math.pi` | π ≈ 3.14159… | `math.pi` |
| `math.e` | Euler's number ≈ 2.71828… | `math.e` |
| `math.sqrt(x)` | Square root | `math.sqrt(25)` → `5.0` |
| `math.pow(x, y)` | x raised to y (returns float) | `math.pow(2, 3)` → `8.0` |
| `math.floor(x)` | Round down | `math.floor(3.7)` → `3` |
| `math.ceil(x)` | Round up | `math.ceil(3.2)` → `4` |

---

## Key Points to Remember

- Always `import math` before using `math.sqrt()`.
- `math.sqrt()` returns a `float` — even `math.sqrt(4)` gives `2.0`, not `2`.
- Passing a negative number raises `ValueError` — add input validation for robust code.
- `x ** 0.5` is a quick alternative that does not require an import.
