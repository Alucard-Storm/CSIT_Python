# Experiment 13 — Functional Polymorphism (Case Study: Restaurant Order System)

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To achieve polymorphism using default arguments, demonstrated through a flexible restaurant order-taking system.

## 2. Theory

| Concept | Description |
|---------|-------------|
| **Polymorphism** | The ability to use a single interface to work with different forms of input |
| **Default arguments** | Parameters with preset values used when the caller does not provide them |
| **Keyword arguments** | Arguments passed by name, allowing any order at the call site |
| **`None` as default** | Common Python pattern to represent an optional, absent value |

- Default arguments must appear **after** all required (positional) arguments in the signature.
- `if customization:` evaluates to `False` when `customization` is `None` or an empty string.
- This experiment demonstrates **function-level polymorphism** — one function handles multiple calling patterns.

## 3. Implementation Code

```python
def take_order(item_name, quantity=1, customization=None):
    order_summary = f"Order: {quantity} x {item_name}"
    if customization:
        order_summary += f" [Note: {customization}]"
    return order_summary

print("--- Kitchen Ticket System ---")
print(take_order("Cappuccino"))
print(take_order("Cheeseburger", 2))
print(take_order("Margherita Pizza", 1, "Extra Cheese & Basil"))
print(take_order("Pasta Alfredo", 3, "No Parsley"))
```

## 4. Expected Output

```text
--- Kitchen Ticket System ---
Order: 1 x Cappuccino
Order: 2 x Cheeseburger
Order: 1 x Margherita Pizza [Note: Extra Cheese & Basil]
Order: 3 x Pasta Alfredo [Note: No Parsley]
```

## 5. Viva / Discussion Questions

1. **Polymorphism definition:** What is polymorphism? Name and briefly explain two types of polymorphism in Python.
2. **Default argument rules:** Can a parameter with a default value appear before a parameter without one? Why?
3. **Mutable defaults:** What is the "mutable default argument" pitfall in Python? Give an example.
4. **`None` vs `False`:** Why is `None` used as the default for `customization` instead of `""` (empty string)?
5. **Duck typing:** What is duck typing in Python, and how does it relate to polymorphism?

---

[Back to Main Index](../README.md)
