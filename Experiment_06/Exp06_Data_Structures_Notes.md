# Experiment 06 — List, Tuple, and Dictionary Operations | Notes

---

## Python's Core Data Structures

Think of them as **different types of storage boxes**:
- **List** → a numbered shelf where you can add, remove, and swap items freely.
- **Tuple** → a sealed box — once packed, the contents never change.
- **Dictionary** → a labelled filing cabinet — each item has a unique label (key) to find it instantly.

---

## List — Dynamic, Ordered, Mutable

```python
fruits = ["apple", "banana", "cherry"]

# Access by index (0-based)
print(fruits[0])       # apple
print(fruits[-1])      # cherry  (last element)

# Modify
fruits[1] = "mango"

# Add
fruits.append("grape")    # add to end
fruits.insert(1, "kiwi")  # insert at position 1

# Remove
fruits.remove("apple")    # remove by value
fruits.pop()              # remove last element
fruits.pop(0)             # remove at index 0

# Traverse
for fruit in fruits:
    print(fruit)

print(len(fruits))        # number of elements
```

### Common List Methods
| Method | Description |
|--------|-------------|
| `append(x)` | Add x to end |
| `insert(i, x)` | Insert x at index i |
| `remove(x)` | Remove first occurrence of x |
| `pop(i)` | Remove and return element at index i |
| `sort()` | Sort in place |
| `reverse()` | Reverse in place |
| `index(x)` | Return index of first x |
| `count(x)` | Count occurrences of x |

---

## Tuple — Ordered, Immutable

```python
coordinates = (10.5, 20.3)
rgb = (255, 128, 0)

# Access (same as list)
print(coordinates[0])   # 10.5

# Tuples CANNOT be modified
# coordinates[0] = 5    ← TypeError!

# Tuple unpacking
x, y = coordinates
print(x, y)             # 10.5  20.3

# Single-element tuple needs trailing comma
single = (42,)
print(type(single))     # <class 'tuple'>
```

---

## Dictionary — Key-Value Store

```python
student = {"name": "Akshay Sagar", "age": 21, "grade": "A"}

# Access
print(student["name"])          # Akshay Sagar
print(student.get("phone", "N/A"))  # N/A  (safe access with default)

# Add / Update
student["city"] = "Bhopal"
student["age"] = 22             # overwrite existing key

# Delete
del student["grade"]
student.pop("city")

# Traverse
for key, value in student.items():
    print(f"{key}: {value}")

# Useful methods
print(student.keys())     # all keys
print(student.values())   # all values
```

---

## Key Points to Remember

- Lists use `[]`, Tuples use `()`, Dictionaries use `{}` with `key: value` pairs.
- Tuples are **immutable** — attempting to modify them raises `TypeError`.
- Dictionary keys must be **hashable** (immutable types like `str`, `int`, `tuple`).
- Use `.get(key, default)` instead of `[]` when the key might not exist.
- Python 3.7+ guarantees dictionaries maintain **insertion order**.
