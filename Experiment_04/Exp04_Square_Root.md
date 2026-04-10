# Experiment 04 — Square Root of a Number

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To compute the square root of a number using the built-in `math` module and user input.

## 2. Theory

| Concept | Description |
|---------|-------------|
| **`math` module** | Standard library module providing mathematical functions and constants |
| **`math.sqrt(x)`** | Returns the square root of `x` as a float |
| **`import`** | Keyword used to include an external module in the current program |
| **`float()`** | Converts a value to a floating-point number |

- `math.sqrt()` raises `ValueError` for negative inputs.
- The `**` operator can also compute square roots: `x ** 0.5`.
- `import math` must appear before any use of `math` functions.

## 3. Implementation Code

```python
import math

num = float(input("Enter a number: "))
sqrt_val = math.sqrt(num)
print(f"Square root of {num} is {sqrt_val}")
```

## 4. Expected Output

```text
Enter a number: 16
Square root of 16.0 is 4.0
```

```text
Enter a number: 2
Square root of 2.0 is 1.4142135623730951
```


---

[Back to Main Index](../README.md)
