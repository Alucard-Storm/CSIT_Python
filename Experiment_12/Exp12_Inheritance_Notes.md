# Experiment 12 — Inheritance in Python | Notes

---

## What is Object-Oriented Programming?

OOP organizes code around **objects** — bundles of data (attributes) and behaviour (methods).

Think of a **class** as a **cookie cutter** and an **object** as the **cookie** made with it. Many cookies can be made from one cutter, each with its own filling (data).

---

## Classes and Objects

```python
class Dog:
    # Constructor — called when you create an object
    def __init__(self, name, breed):
        self.name = name     # attribute
        self.breed = breed

    def bark(self):          # method
        return f"{self.name} says: Woof!"

# Create objects (instances)
dog1 = Dog("Rex", "Labrador")
dog2 = Dog("Buddy", "Poodle")

print(dog1.bark())    # Rex says: Woof!
print(dog2.name)      # Buddy
```

---

## Inheritance — "Is-a" Relationship

Inheritance lets a **child class** reuse code from a **parent class**.

```
Employee (parent)
    └── Manager (child)   ← Manager IS an Employee
```

```python
class Animal:
    def speak(self):
        return "..."

class Dog(Animal):          # Dog inherits from Animal
    def speak(self):        # Override parent method
        return "Woof!"

class Cat(Animal):
    def speak(self):
        return "Meow!"
```

---

## `super()` — Calling the Parent

```python
class Manager(Employee):
    def __init__(self, name, emp_id, base_salary, bonus):
        super().__init__(name, emp_id, base_salary)  # Run Employee's __init__
        self.bonus = bonus                            # Add Manager-specific attr
```

Without `super().__init__(...)`:
- `self.name`, `self.emp_id`, `self.base_salary` would **not** be set.
- `display_info()` would raise `AttributeError`.

---

## Method Resolution Order (MRO)

Python searches methods in this order when you call `obj.method()`:

1. The object's own class
2. Its parent class
3. Its grandparent class
4. … up to `object` (root of all classes)

```python
print(Manager.__mro__)
# (<class 'Manager'>, <class 'Employee'>, <class 'object'>)
```

---

## Types of Inheritance

| Type | Description | Example |
|------|-------------|---------|
| **Single** | One parent → one child | `Manager(Employee)` |
| **Multilevel** | Chain: A → B → C | `Director(Manager)` |
| **Multiple** | Two parents → one child | `class C(A, B)` |
| **Hierarchical** | One parent → many children | `Manager(Employee)`, `Intern(Employee)` |

---

## Key Points to Remember

- `__init__` is the constructor — called automatically when an object is created.
- `self` refers to the current instance — it is a convention, not a keyword.
- Use `super()` to call the parent class's constructor or methods.
- Method overriding: child's method replaces parent's for objects of the child class.
- `isinstance(obj, Parent)` returns `True` for both direct and inherited relationships.
