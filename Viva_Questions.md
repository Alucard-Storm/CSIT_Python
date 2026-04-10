# CSIT-605 Python Programming – Viva Questions

**RGPV VI Semester | Organized by Experiment**

---

## Experiment 1 – Python Installation, IDE Setup & Hello World

1. **Interpreted vs Compiled:** What is the difference between an interpreted and a compiled language? Which category does Python fall into?
2. **REPL:** What does REPL stand for? How do you start the Python interactive shell?
3. **`print()` function:** What happens if you call `print()` with no arguments?
4. **File Extension:** What extension do Python source files use, and why?
5. **Version Check:** What command do you run in a terminal to verify the installed Python version?

## Experiment 2 – Literals, Constants, Data Types & I/O

1. **Dynamic Typing:** What does it mean that Python is dynamically typed? Give an example.
2. **`input()` return type:** What data type does `input()` always return? How would you convert it to an integer?
3. **f-strings:** What is an f-string and how does it differ from `%` formatting or `str.format()`?
4. **`type()` function:** What does `type(3.0)` return? What about `type(True)`?
5. **Boolean as int:** What is the result of `True + True` in Python, and why?


## Experiment 03 — Even or Odd Number Checker

1. **Modulo operator:** What is the result of `10 % 3`? What about `-4 % 2`?
2. **`if–else` vs `if–elif–else`:** When would you use `elif` instead of a plain `else`?
3. **Zero:** Is 0 even or odd? What does `0 % 2` return in Python?
4. **Ternary expression:** Rewrite the even/odd check as a single line using Python's ternary (conditional) expression.
5. **Negative numbers:** Does the even/odd logic work correctly for negative integers in Python? Why?

## Experiment 04 — Square Root of a Number

1. **`math.sqrt` vs `** 0.5`:** Are `math.sqrt(x)` and `x ** 0.5` always equivalent? Is there any difference?
2. **Negative input:** What happens if you pass a negative number to `math.sqrt()`? How would you handle it?
3. **`import` statement:** What is the difference between `import math` and `from math import sqrt`?
4. **`float()` conversion:** Why is input converted to `float` instead of `int` for this program?
5. **`math` constants:** Name two mathematical constants available in the `math` module.

## Experiment 05 — Exponentiation (Power of a Number)

1. **`**` vs `pow()`:** What is the difference between `2 ** 10` and `pow(2, 10)`? Which is preferred?
2. **Modular exponentiation:** What does `pow(2, 10, 1000)` compute, and where is this used?
3. **Zero exponent:** What is any number raised to the power of 0? Verify with Python.
4. **Negative exponent:** What does `2 ** -3` evaluate to in Python?
5. **`math.pow` vs built-in `pow`:** What is the key return-type difference between `math.pow(2, 3)` and `pow(2, 3)`?

## Experiment 06 — List, Tuple, and Dictionary Operations

1. **List vs Tuple:** What is the fundamental difference between a list and a tuple? When would you prefer a tuple?
2. **Mutability:** Why are tuples used as dictionary keys but lists cannot be?
3. **Dictionary access:** What happens when you access a key that does not exist in a dictionary using `[]`? How does `.get()` behave differently?
4. **List methods:** Name at least four built-in methods of the `list` type.
5. **Ordered dictionaries:** Are Python dictionaries ordered? Since which Python version?

## Experiment 07 — Fibonacci Series Using Loops

1. **Fibonacci definition:** State the mathematical recurrence relation for the Fibonacci sequence.
2. **`_` variable:** Why is `_` used as the loop variable instead of `i`? What does it conventionally mean?
3. **Multiple assignment:** How does `a, b = b, a + b` work? Does Python evaluate both sides simultaneously?
4. **Recursion vs iteration:** What are the trade-offs between a recursive and an iterative Fibonacci implementation?
5. **Golden ratio:** What famous mathematical constant does the ratio of successive Fibonacci numbers approach?

## Experiment 08 — First n Prime Numbers

1. **Prime definition:** Is 1 a prime number? Why or why not?
2. **√n optimization:** Explain why you only need to check divisors up to the square root of a number.
3. **`break` statement:** What does `break` do inside a loop? How does it affect the `is_prime` flag logic here?
4. **`while` vs `for`:** Why is a `while` loop used for the outer loop rather than `for`?
5. **Sieve of Eratosthenes:** Briefly describe this algorithm. How does it differ from the approach in this experiment?

## Experiment 09 — Mean, Median, and Mode of a List

1. **Mean vs Median:** When is the median a better measure of central tendency than the mean? Give an example.
2. **Mode of uniform data:** What happens when `statistics.mode()` is called on `[1, 2, 3, 4]` in Python 3.8+?
3. **Manual mean:** Write a one-line expression to compute the mean without importing `statistics`.
4. **Even list median:** How is the median calculated when the list has an even number of elements? Verify with an example.
5. **`statistics` module:** Name two other statistical functions available in the `statistics` module besides `mean`, `median`, and `mode`.

## Experiment 10 — File Handling: Reverse Each Line of a File

1. **`with` statement:** What is the advantage of using `with open(...)` over manually calling `file.close()`?
2. **File modes:** What is the difference between `'w'` and `'a'` mode when opening a file?
3. **`.strip()` before reversing:** What would happen if you reversed the line without calling `.strip()` first?
4. **`[::-1]` slicing:** Explain Python's extended slice notation `[start:stop:step]`. What does step `-1` do?
5. **`FileNotFoundError`:** Name two other common file-related exceptions in Python.

## Experiment 11 — Functions and Modular Programming (Case Study: Banking Transaction System)

1. **`def` keyword:** What does `def` stand for and what does it do?
2. **`return` vs `print`:** What is the difference between a function that `return`s a value and one that only `print`s it?
3. **`global` keyword:** Why is `global balance` needed inside `deposit()` and `withdraw()`? What would happen without it?
4. **Default arguments:** Rewrite `deposit()` so that it has a default deposit amount of `100` if none is provided.
5. **Scope:** What is the difference between local scope and global scope in Python?

## Experiment 12 — Inheritance in Python (Case Study: Employee Management System)

1. **`__init__` method:** What is the purpose of `__init__`? When is it automatically called?
2. **`self` parameter:** What does `self` represent? Is it a Python keyword?
3. **`super()`:** Why is `super().__init__(...)` called in `Manager.__init__`? What happens if it is omitted?
4. **Method overriding:** How does Python know which `calculate_salary()` to call — the parent's or the child's?
5. **`isinstance()`:** What would `isinstance(mgr1, Employee)` return, and why?

## Experiment 13 — Functional Polymorphism (Case Study: Restaurant Order System)

1. **Polymorphism definition:** What is polymorphism? Name and briefly explain two types of polymorphism in Python.
2. **Default argument rules:** Can a parameter with a default value appear before a parameter without one? Why?
3. **Mutable defaults:** What is the "mutable default argument" pitfall in Python? Give an example.
4. **`None` vs `False`:** Why is `None` used as the default for `customization` instead of `""` (empty string)?
5. **Duck typing:** What is duck typing in Python, and how does it relate to polymorphism?

## Experiment 14 — Case Study: Student Record Management System

1. **List of dicts:** Why is a list of dictionaries used to store records rather than parallel lists?
2. **`while True`:** What is the purpose of `while True`? How is the loop terminated?
3. **List comprehension for delete:** Explain how `[s for s in students if s['roll'] != roll]` deletes a record.
4. **`global` in delete:** Why is `global students` needed in `delete_student()` but not in `add_student()`?
5. **Persistence:** This program loses all data when it exits. How would you make the records persist between runs?

## Experiment 15 — Case Study: Mathematical Utility Toolkit

1. **Recursion base case:** What are the base cases in `factorial(n)`? What happens without them?
2. **Recursion limit:** What is Python's default recursion limit? How can it be changed?
3. **`fibonacci(1)` edge case:** What does `fibonacci(1)` return? Trace through the code to verify.
4. **Modular design:** What is the advantage of separating each calculation into its own function?
5. **`math.factorial`:** Python has a built-in `math.factorial()`. When would you prefer it over a custom recursive implementation?
