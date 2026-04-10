# Experiment 11 — Functions and Modular Programming (Case Study: Banking Transaction System)

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To define and call functions with arguments and return values, demonstrated through a modular banking transaction system.

## 2. Theory

| Concept | Description |
|---------|-------------|
| **Function** | A named, reusable block of code defined with `def` |
| **Parameters** | Variables listed in the function definition (`def f(x):`) |
| **Arguments** | Values passed to a function when calling it (`f(10)`) |
| **`return`** | Sends a value back to the caller; exits the function |
| **`global`** | Allows a function to modify a variable defined at module scope |

- Functions promote **DRY** (Don't Repeat Yourself) — write once, reuse many times.
- A function without a `return` statement implicitly returns `None`.
- `global balance` inside a function tells Python to use the module-level `balance` variable instead of creating a local one.

## 3. Implementation Code

```python
balance = 0

def check_balance():
    return balance

def deposit(amount):
    global balance
    if amount > 0:
        balance += amount
        print(f"Deposited: ${amount}")
    else:
        print("Invalid deposit amount")
    return balance

def withdraw(amount):
    global balance
    if 0 < amount <= balance:
        balance -= amount
        print(f"Withdrew: ${amount}")
    elif amount > balance:
        print(f"Failed Withdrawal: ${amount} (Insufficient Funds)")
    else:
        print("Invalid withdrawal amount")
    return balance

# Case Study: ATM Session
print("--- Banking System Simulation ---")
print(f"Current Balance: ${check_balance()}")
deposit(5000)
print(f"Balance after deposit: ${check_balance()}")
withdraw(1200)
withdraw(10000)
print(f"Final Balance: ${check_balance()}")
```

## 4. Expected Output

```text
--- Banking System Simulation ---
Current Balance: $0
Deposited: $5000
Balance after deposit: $5000
Withdrew: $1200
Failed Withdrawal: $10000 (Insufficient Funds)
Final Balance: $3800
```


---

[Back to Main Index](../README.md)
