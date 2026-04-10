# Experiment 05 — Exponentiation (Power of a Number)

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To calculate the power of a number using the `**` operator and the built-in `pow()` function.

## 2. Theory

| Concept | Description |
|---------|-------------|
| **`**` operator** | Exponentiation operator — `base ** exp` computes base raised to exp |
| **`pow(x, y)`** | Built-in function equivalent to `x ** y` |
| **`math.pow(x, y)`** | Returns a float; `pow()` can return int if inputs are int |
| **`float()`** | Converts input string to float to allow decimal bases and exponents |

- Python's `**` operator handles integer, float, and negative exponents natively.
- `pow(base, exp, mod)` accepts an optional third argument for modular exponentiation.
- `2 ** -1` gives `0.5`; `2 ** 0` gives `1` — both are valid in Python.

## 3. Implementation Code

```python
base = float(input("Enter base: "))
exp = float(input("Enter exponent: "))
result = base ** exp
print(f"{base} raised to {exp} is {result}")
```

## 4. Expected Output

```text
Enter base: 2
Enter exponent: 3
2.0 raised to 3.0 is 8.0
```

```text
Enter base: 5
Enter exponent: 0
5.0 raised to 0.0 is 1.0
```


---

[Back to Main Index](../README.md)
