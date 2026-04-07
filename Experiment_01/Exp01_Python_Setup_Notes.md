# Experiment 01 — Python Installation, IDE Setup & Hello World | Notes

---

## What is Python?

Think of Python as a **universal translator** between a human and a computer:
- You write instructions in near-English syntax.
- The **interpreter** reads and executes each instruction immediately, line by line.
- This makes Python perfect for beginners and rapid development alike.

---

## The Interpreter vs the Compiler

```
Source Code (.py)
       |
  [ Interpreter ]  ← Python reads + runs directly
       |
   Output on screen
```

A compiled language (like C) first converts the entire source to machine code, then runs it. Python skips that step — it runs as it reads, which is why it is called **interpreted**.

---

## Setting Up Python

### Step 1 — Install Python
Download from [python.org](https://www.python.org/downloads/) and run the installer.  
**Important:** Check "Add Python to PATH" during installation on Windows.

### Step 2 — Verify Installation
```bash
python --version
# Example output: Python 3.12.0
```

### Step 3 — Choose an IDE
| IDE | Best For |
|-----|----------|
| IDLE | Beginners (bundled with Python) |
| VS Code | Lightweight, highly extensible |
| PyCharm | Full-featured professional use |

---

## Your First Python Program

```python
print("Hello, World!")
```

- `print` is a **built-in function** — no import needed.
- The string `"Hello, World!"` is enclosed in double quotes (single quotes also work).
- Python does **not** require a semicolon at the end of a line.

---

## Key Points to Remember

- Python is case-sensitive: `Print` is not the same as `print`.
- Indentation (spaces/tabs) defines code blocks — it is not optional.
- Comments start with `#` and are ignored by the interpreter.
- `python filename.py` runs a Python script from the terminal.

---

## Quick Reference

| Task | Command |
|------|---------|
| Check Python version | `python --version` |
| Run a script | `python hello.py` |
| Start interactive shell | `python` |
| Exit interactive shell | `exit()` or `Ctrl+D` |
