# Experiment 10 — File Handling: Reverse Each Line of a File

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To read a text file and print each line in reverse order using Python's file handling capabilities.

## 2. Theory

| Concept | Description |
|---------|-------------|
| **`open(file, mode)`** | Opens a file; modes: `'r'` (read), `'w'` (write), `'a'` (append) |
| **`with` statement** | Context manager — automatically closes the file when the block exits |
| **`.strip()`** | Removes leading/trailing whitespace and newline characters |
| **`[::-1]` slicing** | Reverses a string or sequence using step of `-1` |
| **`try–except`** | Catches and handles runtime errors gracefully |

- Always use `with open(...)` to ensure files are closed even if an error occurs.
- `.strip()` must be applied before reversing to remove the trailing `\n` from each line.
- `FileNotFoundError` is raised when the specified file path does not exist.

## 3. Implementation Code

```python
# Using sample.txt
filename = "sample.txt"
try:
    with open(filename, 'r') as file:
        for line in file:
            print(line.strip()[::-1])
except FileNotFoundError:
    print(f"{filename} not found.")
```

## 4. Expected Output

*(Given `sample.txt` contains five lines: "First line of the file", etc.)*

```text
elif eht fo enil tsriF
elif eht fo enil dnoceS
elif eht fo enil drihT
elif eht fo enil htruoF
elif eht fo enil htfiF
```


---

[Back to Main Index](../README.md)
