# Experiment 02 — Literals, Constants, Data Types & I/O

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To demonstrate numeric, string, and boolean data types with user input and formatted output.

## 2. Theory

| Data Type | Keyword | Example |
|-----------|---------|---------|
| **Integer** | `int` | `10`, `-3`, `0` |
| **Float** | `float` | `3.14`, `-0.5` |
| **String** | `str` | `"Hello"`, `'World'` |
| **Boolean** | `bool` | `True`, `False` |

- `input()` reads a line from standard input and always returns a **string**.
- `type()` returns the data type of any variable.
- f-strings (`f"..."`) allow embedding expressions directly inside string literals using `{}`.
- Python is **dynamically typed** — the type of a variable is determined at runtime, not declared.

## 3. Implementation Code

```python
num = 10
pi = 3.14
name = "Python"
is_fun = True

user_input = input("Enter something: ")
print(f"Integer: {num}, Type: {type(num)}")
print(f"Float: {pi}, Type: {type(pi)}")
print(f"String: {name}, Type: {type(name)}")
print(f"Boolean: {is_fun}, Type: {type(is_fun)}")
print(f"You entered: {user_input}")
```

## 4. Expected Output

```text
Enter something: Sample Input
Integer: 10, Type: <class 'int'>
Float: 3.14, Type: <class 'float'>
String: Python, Type: <class 'str'>
Boolean: True, Type: <class 'bool'>
You entered: Sample Input
```

---

[Back to Main Index](../README.md)
