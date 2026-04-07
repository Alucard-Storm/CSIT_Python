# Experiment 11 — Functions and Modular Programming | Notes

---

## What is a Function?

A function is a **named block of code** that performs a specific task. You define it once and can call it as many times as needed.

Think of functions as **vending machine buttons** — press the button (call the function), provide coins (arguments), get a snack (return value).

---

## Defining and Calling Functions

```python
# Define
def greet(name):
    return f"Hello, {name}!"

# Call
message = greet("Akshay Sagar")
print(message)    # Hello, Akshay Sagar!
```

---

## Parameters vs Arguments

```python
def add(x, y):      # x, y are PARAMETERS (placeholders in definition)
    return x + y

result = add(3, 5)  # 3, 5 are ARGUMENTS (actual values passed)
```

---

## Types of Arguments

```python
# Positional
add(3, 5)

# Keyword
add(y=5, x=3)      # order doesn't matter with keywords

# Default
def power(base, exp=2):
    return base ** exp

power(3)     # → 9   (uses default exp=2)
power(3, 3)  # → 27

# Variable-length
def total(*numbers):
    return sum(numbers)

total(1, 2, 3, 4)  # → 10
```

---

## Variable Scope

```python
balance = 1000        # GLOBAL variable (module level)

def show():
    print(balance)    # OK — read access to global is allowed

def bad_deposit(amount):
    balance += amount  # ERROR! Python creates a new local 'balance'
                       # and tries to read it before assigning

def good_deposit(amount):
    global balance     # Declare intent to modify global
    balance += amount  # Now works correctly
```

**Rule:** Reading a global variable inside a function is fine. **Modifying** it requires the `global` keyword.

---

## The Banking System — How It Works

```
balance = 0  ← shared state (global)

check_balance() ──── reads balance
deposit(amount) ──── balance += amount
withdraw(amount) ─── balance -= amount (only if sufficient funds)
```

Each function handles **one responsibility** — this is **modular programming**.

---

## Key Points to Remember

- Use `def function_name(parameters):` to define a function.
- Functions `return` values; without `return`, they return `None`.
- Use `global var` inside a function only when you need to **modify** a module-level variable.
- Default arguments make functions flexible: `def f(x, y=10):`.
- Functions should do **one thing** — this makes them easier to test and reuse.
