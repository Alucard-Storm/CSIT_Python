# Experiment 03 — Even or Odd Number Checker

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To use conditional statements (`if–else`) to check whether a number is even or odd.

## 2. Theory

| Concept | Description |
|---------|-------------|
| **Modulo operator `%`** | Returns the remainder of integer division (`7 % 2` → `1`) |
| **`if–else`** | Executes one block if condition is `True`, another if `False` |
| **Even number** | A number completely divisible by 2 (remainder = 0) |
| **Odd number** | A number that leaves remainder 1 when divided by 2 |

- The condition `num % 2 == 0` evaluates to `True` when `num` is even.
- `int(input(...))` converts the string returned by `input()` to an integer before arithmetic.

## 3. Implementation Code

```python
num = int(input("Enter a number: "))
if num % 2 == 0:
    print(f"{num} is Even")
else:
    print(f"{num} is Odd")
```

## 4. Expected Output

```text
Enter a number: 4
4 is Even
```

```text
Enter a number: 7
7 is Odd
```


---

[Back to Main Index](../README.md)
