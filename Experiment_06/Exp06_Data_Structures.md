# Experiment 06 — List, Tuple, and Dictionary Operations

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To create and manipulate Python's core data structures — List, Tuple, and Dictionary — with insertion, deletion, and traversal.

## 2. Theory

| Data Structure | Ordered | Mutable | Duplicates | Syntax |
|----------------|---------|---------|------------|--------|
| **List** | Yes | Yes | Yes | `[1, 2, 3]` |
| **Tuple** | Yes | No | Yes | `(1, 2, 3)` |
| **Dictionary** | Yes (3.7+) | Yes | Keys: No | `{"key": "val"}` |

- **List:** Dynamic array — elements can be added, removed, or changed after creation.
- **Tuple:** Immutable sequence — once created, its elements cannot be modified; used for fixed data.
- **Dictionary:** Key-value store — values are accessed and modified by their unique keys.

## 3. Implementation Code

```python
# List
my_list = [1, 2, 3]
my_list.append(4)
print("List:", my_list)

# Tuple
my_tuple = (10, 20)
print("Tuple:", my_tuple)

# Dictionary
my_dict = {'name': 'Akshay Sagar', 'age': 21}
my_dict['city'] = 'Bhopal'
print("Dictionary:", my_dict)
```

## 4. Expected Output

```text
List: [1, 2, 3, 4]
Tuple: (10, 20)
Dictionary: {'name': 'Akshay Sagar', 'age': 21, 'city': 'Bhopal'}
```

## 5. Viva / Discussion Questions

1. **List vs Tuple:** What is the fundamental difference between a list and a tuple? When would you prefer a tuple?
2. **Mutability:** Why are tuples used as dictionary keys but lists cannot be?
3. **Dictionary access:** What happens when you access a key that does not exist in a dictionary using `[]`? How does `.get()` behave differently?
4. **List methods:** Name at least four built-in methods of the `list` type.
5. **Ordered dictionaries:** Are Python dictionaries ordered? Since which Python version?

---

[Back to Main Index](../README.md)
