# Experiment 08 — First n Prime Numbers | Notes

---

## What is a Prime Number?

A **prime number** is any integer greater than 1 that cannot be divided evenly by any number other than 1 and itself.

```
Primes:    2, 3, 5, 7, 11, 13, 17, 19, 23, 29 ...
Not prime: 1 (by definition), 4 (÷2), 6 (÷2,3), 9 (÷3)
```

> **1 is not prime** — primes are defined as having exactly 2 factors (1 and itself). 1 has only 1 factor.

---

## The √n Optimization

To check if `num` is prime, you only need to try dividing by numbers up to **√num**.

**Why?** If `num = a × b` and both `a` and `b` are greater than √num, then `a × b > num` — a contradiction. So at least one factor must be ≤ √num.

```python
# Checking all divisors up to num-1 (slow — O(n))
for i in range(2, num):
    ...

# Checking only up to √num (fast — O(√n))
for i in range(2, int(num ** 0.5) + 1):
    ...
```

---

## Program Logic Trace (n = 5)

| num | Divisors checked | is_prime | count |
|-----|-----------------|----------|-------|
| 2 | range(2,2) → nothing | True | 1 |
| 3 | range(2,2) → nothing | True | 2 |
| 4 | 2 divides 4 | False | 2 |
| 5 | range(2,3) → 2 doesn't divide 5 | True | 3 |
| 6 | 2 divides 6 | False | 3 |
| 7 | range(2,3) → 2 doesn't divide 7 | True | 4 |
| 8 | 2 divides 8 | False | 4 |
| 9 | 3 divides 9 | False | 4 |
| 10 | 2 divides 10 | False | 4 |
| 11 | range(2,4) → none divide 11 | True | 5 ✓ |

---

## A Cleaner Primality Function

```python
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return False
    return True

# Generate first n primes
n = 10
primes = []
num = 2
while len(primes) < n:
    if is_prime(num):
        primes.append(num)
    num += 1

print(primes)  # [2, 3, 5, 7, 11, 13, 17, 19, 23, 29]
```

---

## The Sieve of Eratosthenes (Faster for a Range)

```python
def sieve(limit):
    is_prime = [True] * (limit + 1)
    is_prime[0] = is_prime[1] = False
    for i in range(2, int(limit ** 0.5) + 1):
        if is_prime[i]:
            for j in range(i*i, limit + 1, i):
                is_prime[j] = False
    return [i for i, p in enumerate(is_prime) if p]

print(sieve(30))  # [2, 3, 5, 7, 11, 13, 17, 19, 23, 29]
```

This is more efficient when you need all primes **up to a limit**, rather than the first `n` primes.

---

## Key Points to Remember

- 2 is the only even prime number.
- Check divisors only up to √num — this is the key optimization.
- `break` exits the inner loop early as soon as one factor is found.
- The `while` loop is the correct choice when you don't know how many numbers to check in advance.
