# Experiment 10 — File Handling: Reverse Each Line | Notes

---

## What is File Handling?

File handling lets a Python program **persist data** beyond the program's lifetime — read from disk, write results, and process large datasets that don't fit in memory.

---

## Opening and Closing Files

### The Old Way (manual close — error-prone)
```python
file = open("data.txt", 'r')
content = file.read()
file.close()    # If an error occurred above, this may never run!
```

### The Right Way — `with` statement
```python
with open("data.txt", 'r') as file:
    content = file.read()
# File is automatically closed here, even if an error occurred
```

---

## File Modes

| Mode | Meaning | File exists | File missing |
|------|---------|-------------|--------------|
| `'r'` | Read | Opens it | `FileNotFoundError` |
| `'w'` | Write | Overwrites it | Creates new |
| `'a'` | Append | Appends to end | Creates new |
| `'r+'` | Read+Write | Opens it | `FileNotFoundError` |

---

## Reading a File — Three Methods

```python
with open("sample.txt", 'r') as f:

    # 1. Read entire file as one string
    content = f.read()

    # 2. Read all lines as a list
    lines = f.readlines()          # [" line1\n", "line2\n", ...]

    # 3. Iterate line by line (memory-efficient for large files)
    for line in f:
        print(line.strip())
```

---

## String Reversal — `[::-1]` Slicing

Python's slice notation: `sequence[start:stop:step]`

```python
s = "Hello"
s[::-1]     # "olleH"  — step=-1 reads backwards

# Why strip() first?
line = "Hello\n"
line[::-1]           # "\nolleH"  ← newline moves to the front
line.strip()[::-1]   # "olleH"    ← correct
```

---

## Writing to a File

```python
with open("output.txt", 'w') as f:
    f.write("First line\n")
    f.write("Second line\n")

# Append without overwriting
with open("output.txt", 'a') as f:
    f.write("Third line\n")
```

---

## Error Handling for Files

```python
try:
    with open("missing.txt", 'r') as f:
        print(f.read())
except FileNotFoundError:
    print("File does not exist.")
except PermissionError:
    print("No permission to read this file.")
except IOError as e:
    print(f"I/O error: {e}")
```

---

## Key Points to Remember

- Always use `with open(...)` — it handles closing automatically and is the Pythonic way.
- `.strip()` removes `\n` from the end of each line read from a file.
- `'w'` mode **destroys** existing file content — use `'a'` to preserve it.
- Iterating over a file object (`for line in file`) is memory-efficient for large files.
- `FileNotFoundError` is a subclass of `OSError`.
