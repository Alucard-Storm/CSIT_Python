# Experiment 14 — Student Record Management System | Notes

---

## List of Dictionaries as an In-Memory Database

A **list of dictionaries** is Python's simplest way to hold structured records:

```python
students = [
    {"roll": "101", "name": "Akshay Sagar",  "marks": "85"},
    {"roll": "102", "name": "Diksha Pawar",  "marks": "72"},
    {"roll": "103", "name": "Pawan Tiwari",  "marks": "91"},
]
```

Think of it as a **spreadsheet in memory** — each dictionary is a row, and keys are column headers.

---

## CRUD Operations

### Create — `append()` a new dict
```python
students.append({"roll": "104", "name": "Divya Khade", "marks": "88"})
```

### Read — iterate and print
```python
for s in students:
    print(s["roll"], s["name"], s["marks"])
```

### Update — find by key, then modify
```python
for s in students:
    if s["roll"] == "101":
        s["marks"] = "90"
        break
```

### Delete — filter out the unwanted record
```python
students = [s for s in students if s["roll"] != "102"]
```

---

## Tabular Output with f-strings

```python
print(f"{'Roll No':<10} {'Name':<20} {'Marks':<10}")
# Roll No    Name                 Marks
# :<10 means: left-align in a field of minimum width 10 characters
```

| Specifier | Meaning |
|-----------|---------|
| `:<10` | Left-align, width 10 |
| `:>10` | Right-align, width 10 |
| `:^10` | Centre-align, width 10 |
| `:.2f` | Float with 2 decimal places |

---

## The Menu Loop Pattern

```python
while True:
    print("1. Option A\n2. Option B\n3. Exit")
    choice = input("Enter choice: ")

    if choice == '1':
        ...
    elif choice == '2':
        ...
    elif choice == '3':
        break           # ← exits the while True loop
    else:
        print("Invalid choice!")
```

This pattern is the foundation of all **CLI (command-line interface)** programs.

---

## Making Data Persistent

The program currently loses data on exit. To persist records, save to a file:

```python
import json

# Save
with open("students.json", "w") as f:
    json.dump(students, f)

# Load
with open("students.json", "r") as f:
    students = json.load(f)
```

---

## Key Points to Remember

- A list of dicts is flexible — you can add/remove fields without restructuring code.
- List comprehension `[x for x in lst if cond]` is the Pythonic way to filter a list.
- `global` is needed when you **reassign** a variable (e.g., `students = [...]`), but not when you only **mutate** it (e.g., `students.append(...)`).
- The `while True / break` pattern is the standard menu-driven loop in Python.
- Use `json` module to persist records between program runs.
