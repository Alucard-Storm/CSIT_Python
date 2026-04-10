# Experiment 12 — Inheritance in Python (Case Study: Employee Management System)

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To demonstrate single inheritance using classes and objects by modeling an Employee Management System where a `Manager` class extends an `Employee` class.

## 2. Theory

| Concept | Description |
|---------|-------------|
| **Class** | Blueprint for creating objects; defined with `class` keyword |
| **Object** | An instance of a class with its own data (attributes) and behaviour (methods) |
| **Inheritance** | A child class acquires attributes and methods of a parent class |
| **`super()`** | Calls the parent class's `__init__` or any overridden method |
| **Method overriding** | A child class redefines a method from the parent to change its behaviour |

- **Single inheritance:** One child class inherits from one parent.
- **`super().__init__(...)`** must be called in the child's `__init__` to properly initialize the parent's attributes.
- Method overriding allows the child class to specialize behaviour without rewriting common logic.

## 3. Implementation Code

```python
class Employee:
    def __init__(self, name, emp_id, base_salary):
        self.name = name
        self.emp_id = emp_id
        self.base_salary = base_salary

    def display_info(self):
        print(f"Employee ID: {self.emp_id}")
        print(f"Name: {self.name}")

    def calculate_salary(self):
        return self.base_salary

class Manager(Employee):
    def __init__(self, name, emp_id, base_salary, bonus):
        super().__init__(name, emp_id, base_salary)
        self.bonus = bonus

    def calculate_salary(self):
        return self.base_salary + self.bonus

# Case Study: Payroll Processing
print("--- Payroll System ---")

emp1 = Employee("Akshay Sagar", "E001", 50000)
emp1.display_info()
print(f"Total Salary: ${emp1.calculate_salary()}")
print("-" * 20)

mgr1 = Manager("Pawan Tiwari", "M001", 80000, 15000)
mgr1.display_info()
print(f"Total Salary: ${mgr1.calculate_salary()}")
```

## 4. Expected Output

```text
--- Payroll System ---
Employee ID: E001
Name: Akshay Sagar
Total Salary: $50000
--------------------
Employee ID: M001
Name: Pawan Tiwari
Total Salary: $95000
```


---

[Back to Main Index](../README.md)
