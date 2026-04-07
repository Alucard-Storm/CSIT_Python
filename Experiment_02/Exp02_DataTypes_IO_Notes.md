# Experiment 02 — Literals, Constants, Data Types & I/O | Notes

---

## What are Data Types?

Every piece of data in Python has a **type** that tells Python what kind of value it is and what operations are valid on it.

Think of types like **containers**:
- An `int` container holds whole numbers (`10`, `-3`).
- A `float` container holds decimal numbers (`3.14`).
- A `str` container holds text (`"Hello"`).
- A `bool` container holds only `True` or `False`.

---

## Python's Core Data Types

### Integer — `int`
```python
x = 42
y = -7
big = 1_000_000   # underscore for readability
print(type(x))    # <class 'int'>
```

### Float — `float`
```python
pi = 3.14159
temp = -0.5
print(type(pi))   # <class 'float'>
```

### String — `str`
```python
greeting = "Hello, World!"
name = 'Python'
multi = """This is a
multiline string."""
print(len(greeting))  # 13
```

### Boolean — `bool`
```python
flag = True
print(type(flag))   # <class 'bool'>
print(int(True))    # 1
print(int(False))   # 0
```
> Boolean is a subtype of `int` in Python — `True` equals `1` and `False` equals `0`.

---

## User Input & Output

### `input()` — always returns a string
```python
age = input("Enter your age: ")   # returns "21" not 21
age = int(age)                     # convert to int
```

### `print()` — flexible output
```python
print("Name:", name, "Age:", age)         # comma-separated
print(f"Name: {name}, Age: {age}")        # f-string (preferred)
print("Pi = {:.2f}".format(3.14159))      # format to 2 decimal places
```

---

## Type Conversion

| From | To | Function | Example |
|------|----|----------|---------|
| `str` | `int` | `int()` | `int("42")` → `42` |
| `str` | `float` | `float()` | `float("3.14")` → `3.14` |
| `int` | `str` | `str()` | `str(42)` → `"42"` |
| `int` | `float` | `float()` | `float(5)` → `5.0` |

---

## Key Points to Remember

- Python variables do **not** need a type declaration — just assign and Python figures out the type.
- Use `type()` to inspect the type of any value at runtime.
- Always convert `input()` result before doing arithmetic: `int(input(...))`.
- f-strings are the most readable and modern way to format output.
