# Experiment 15 — Case Study: Mathematical Utility Toolkit

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To develop a unified mathematical utility toolkit that combines prime checking, factorial computation, Fibonacci generation, and power calculation into a single menu-driven program.

## 2. Theory

| Function | Algorithm | Complexity |
|----------|-----------|------------|
| **`is_prime(n)`** | Trial division up to √n | O(√n) |
| **`factorial(n)`** | Recursive: `n * factorial(n-1)` | O(n) |
| **`fibonacci(n)`** | Iterative list building | O(n) |
| **`power(base, exp)`** | Python `**` operator | O(1) |

- **Recursion** is used for `factorial` to demonstrate the recursive pattern. Python's default recursion limit is ~1000.
- **Iteration** is preferred for `fibonacci` to avoid excessive function-call overhead.
- Combining multiple related functions into one module is the foundation of a **utility library**.

## 3. Implementation Code

```python
def is_prime(n):
    if n < 2: return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0: return False
    return True

def factorial(n):
    if n == 0 or n == 1: return 1
    return n * factorial(n - 1)

def fibonacci(n):
    series = [0, 1]
    while len(series) < n:
        series.append(series[-1] + series[-2])
    return series[:n]

def power(base, exp):
    return base ** exp

while True:
    print("\n--- Math Toolkit ---")
    print("1. Check Prime")
    print("2. Calculate Factorial")
    print("3. Generate Fibonacci Series")
    print("4. Calculate Power")
    print("5. Exit")
    choice = input("Select Operation: ")

    if choice == '1':
        num = int(input("Enter number: "))
        print(f"{num} is {'Prime' if is_prime(num) else 'Not Prime'}")
    elif choice == '2':
        num = int(input("Enter number: "))
        print(f"Factorial of {num} is {factorial(num)}")
    elif choice == '3':
        num = int(input("Enter number of terms: "))
        print(f"Fibonacci Series: {fibonacci(num)}")
    elif choice == '4':
        b = float(input("Enter base: "))
        e = float(input("Enter exponent: "))
        print(f"Result: {power(b, e)}")
    elif choice == '5':
        print("Goodbye!")
        break
    else:
        print("Invalid selection.")
```

## 4. Expected Output

```text
--- Math Toolkit ---
1. Check Prime
2. Calculate Factorial
3. Generate Fibonacci Series
4. Calculate Power
5. Exit
Select Operation: 1
Enter number: 17
17 is Prime

Select Operation: 3
Enter number of terms: 6
Fibonacci Series: [0, 1, 1, 2, 3, 5]

Select Operation: 5
Goodbye!
```


---

[Back to Main Index](../README.md)
