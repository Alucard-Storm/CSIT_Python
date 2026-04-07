# Experiment 13 — Functional Polymorphism | Notes

---

## What is Polymorphism?

**Polymorphism** means "many forms". In programming, it means one interface can work with many different input combinations.

Think of a **light switch** — one action (flick), but it can be applied to a bedside lamp, a ceiling fan, or a doorbell. Same interface, different effects.

---

## Function-Level Polymorphism — Default Arguments

```python
def take_order(item_name, quantity=1, customization=None):
    ...

# One function, four valid calling patterns:
take_order("Latte")                           # 1 arg
take_order("Latte", 2)                        # 2 args
take_order("Latte", customization="Oat Milk") # keyword arg
take_order("Latte", 2, "Oat Milk")           # 3 args
```

---

## Default Argument Rules

```python
# VALID — defaults come after required args
def f(a, b=10, c=20): ...

# INVALID — required arg after default
def f(a=10, b): ...  # SyntaxError!
```

---

## The Mutable Default Argument Trap

```python
# WRONG — the list is shared across all calls!
def add_item(item, cart=[]):
    cart.append(item)
    return cart

print(add_item("apple"))   # ['apple']
print(add_item("banana"))  # ['apple', 'banana']  ← not what you'd expect

# CORRECT — use None as sentinel
def add_item(item, cart=None):
    if cart is None:
        cart = []
    cart.append(item)
    return cart
```

---

## Object-Level Polymorphism (Method Overriding)

```python
class Shape:
    def area(self):
        return 0

class Circle(Shape):
    def __init__(self, r): self.r = r
    def area(self): return 3.14 * self.r ** 2

class Square(Shape):
    def __init__(self, s): self.s = s
    def area(self): return self.s ** 2

shapes = [Circle(5), Square(4)]
for shape in shapes:
    print(shape.area())   # Each calls its own area()
# 78.5
# 16
```

---

## Duck Typing — Python's Natural Polymorphism

> *"If it walks like a duck and quacks like a duck, it's a duck."*

Python doesn't check the type of an object — it only checks if the object **has the method or attribute** being used.

```python
def make_noise(animal):
    print(animal.speak())   # any object with .speak() works

class Dog: speak = lambda self: "Woof"
class Cat: speak = lambda self: "Meow"
class Robot: speak = lambda self: "Beep"

for obj in [Dog(), Cat(), Robot()]:
    make_noise(obj)
```

---

## Key Points to Remember

- Default arguments allow a single function to handle varying levels of detail.
- Default values are evaluated **once** at definition time — never use mutable objects (lists, dicts) as defaults.
- Use `None` as the default for optional parameters that are containers.
- Python achieves runtime polymorphism naturally through **duck typing** — no interfaces or explicit contracts needed.
