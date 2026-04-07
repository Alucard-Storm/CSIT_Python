# Experiment 08 — First n Prime Numbers

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To write a program that finds and prints the first `n` prime numbers using nested loops.

## 2. Theory

| Concept | Description |
|---------|-------------|
| **Prime number** | A number greater than 1 that has no divisors other than 1 and itself |
| **`while` loop** | Repeats as long as a condition is `True`; used when iteration count is not fixed upfront |
| **Nested loops** | A loop inside another loop; outer tracks count, inner checks primality |
| **`int(num ** 0.5)`** | Check divisors only up to √num — sufficient to detect all factors |

- Checking divisors only up to √num reduces the primality test from O(n) to O(√n).
- Setting a `is_prime` flag and breaking early on finding a divisor improves efficiency.

## 3. Implementation Code

```python
n = int(input("Enter value of n: "))
count = 0
num = 2
print(f"First {n} prime numbers:")
while count < n:
    is_prime = True
    for i in range(2, int(num ** 0.5) + 1):
        if num % i == 0:
            is_prime = False
            break
    if is_prime:
        print(num, end=" ")
        count += 1
    num += 1
print()
```

## 4. Expected Output

```text
Enter value of n: 5
First 5 prime numbers:
2 3 5 7 11
```

```text
Enter value of n: 10
First 10 prime numbers:
2 3 5 7 11 13 17 19 23 29
```

## 5. Viva / Discussion Questions

1. **Prime definition:** Is 1 a prime number? Why or why not?
2. **√n optimization:** Explain why you only need to check divisors up to the square root of a number.
3. **`break` statement:** What does `break` do inside a loop? How does it affect the `is_prime` flag logic here?
4. **`while` vs `for`:** Why is a `while` loop used for the outer loop rather than `for`?
5. **Sieve of Eratosthenes:** Briefly describe this algorithm. How does it differ from the approach in this experiment?

---

[Back to Main Index](../README.md)
