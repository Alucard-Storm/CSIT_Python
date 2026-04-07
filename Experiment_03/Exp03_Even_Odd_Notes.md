# Experiment 03 — Even or Odd Number Checker | Notes

---

## What is the Modulo Operator?

The `%` operator gives the **remainder** after integer division.

```
12 ÷ 5 = 2  remainder  2   →   12 % 5 = 2
10 ÷ 2 = 5  remainder  0   →   10 % 2 = 0  ← Even!
 7 ÷ 2 = 3  remainder  1   →    7 % 2 = 1  ← Odd!
```

So the rule is simple:
- `num % 2 == 0` → Even
- `num % 2 != 0` → Odd

---

## `if–else` Control Flow

```python
if condition:        # if condition is True → run this block
    ...
else:                # otherwise → run this block
    ...
```

Python uses **indentation** (4 spaces) to define blocks — there are no `{}` braces like in C or Java.

---

## The Even / Odd Program Step-by-Step

```python
num = int(input("Enter a number: "))
# input() returns a string, int() converts it to integer

if num % 2 == 0:           # Check remainder
    print(f"{num} is Even")
else:
    print(f"{num} is Odd")
```

---

## Ternary (One-Line) Version

```python
result = "Even" if num % 2 == 0 else "Odd"
print(f"{num} is {result}")
```

---

## Extended Version — Handle Negative Numbers & Zero

```python
num = int(input("Enter a number: "))
if num == 0:
    print("Zero is Even")
elif num % 2 == 0:
    print(f"{num} is Even")
else:
    print(f"{num} is Odd")
```

---

## Key Points to Remember

- `%` is the modulo operator — it returns the **remainder**, not the quotient.
- `==` is the equality comparison; `=` is assignment — do not confuse them.
- Python `if` blocks require consistent indentation — mixing spaces and tabs causes errors.
- Zero (`0`) is defined as an even number mathematically.
