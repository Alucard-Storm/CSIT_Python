# Experiment 14 — Case Study: Student Record Management System

**Subject:** CSIT-605 Python Lab  
**Location:** RGPV, Bhopal

---

## 1. Aim

To develop a menu-driven program using a list of dictionaries and functions to manage student records (Add, View, Search, Delete).

## 2. Theory

| Concept | Description |
|---------|-------------|
| **List of dictionaries** | Each element is a `dict` representing one record — a simple in-memory data store |
| **Menu-driven program** | Uses a loop with `input()` and `if–elif–else` to repeatedly offer choices |
| **CRUD operations** | Create, Read, Update, Delete — the four fundamental data operations |
| **List comprehension** | Compact syntax to build a filtered list: `[x for x in lst if condition]` |
| **f-string formatting** | `:<10` left-aligns in a field of width 10 for tabular output |

- A `while True` loop combined with `break` creates an indefinite menu that exits only on the user's request.
- Using `global students` in `delete_student()` allows reassignment of the module-level list.

## 3. Implementation Code

```python
students = []

def add_student(roll, name, marks):
    students.append({"roll": roll, "name": name, "marks": marks})
    print(f"Student {name} added successfully.")

def view_students():
    print("\n--- Student Records ---")
    print(f"{'Roll No':<10} {'Name':<20} {'Marks':<10}")
    print("-" * 40)
    for s in students:
        print(f"{s['roll']:<10} {s['name']:<20} {s['marks']:<10}")
    print("-" * 40)

def search_student(roll):
    for s in students:
        if s['roll'] == roll:
            return s
    return None

def delete_student(roll):
    global students
    original_len = len(students)
    students = [s for s in students if s['roll'] != roll]
    if len(students) < original_len:
        print(f"Student with Roll No {roll} deleted.")
    else:
        print("Student not found.")

while True:
    print("\n1. Add Student\n2. View Students\n3. Search Student\n4. Delete Student\n5. Exit")
    choice = input("Enter choice: ")
    if choice == '1':
        r = input("Enter Roll No: ")
        n = input("Enter Name: ")
        m = input("Enter Marks: ")
        add_student(r, n, m)
    elif choice == '2':
        view_students()
    elif choice == '3':
        r = input("Enter Roll No to search: ")
        s = search_student(r)
        print(f"Found: {s}" if s else "Not Found.")
    elif choice == '4':
        r = input("Enter Roll No to delete: ")
        delete_student(r)
    elif choice == '5':
        print("Exiting...")
        break
    else:
        print("Invalid choice!")
```

## 4. Expected Output

```text
1. Add Student
2. View Students
3. Search Student
4. Delete Student
5. Exit
Enter choice: 1
Enter Roll No: 101
Enter Name: Akshay Sagar
Enter Marks: 85
Student Akshay Sagar added successfully.

Enter choice: 2
--- Student Records ---
Roll No    Name                 Marks
----------------------------------------
101        Akshay Sagar         85
----------------------------------------

Enter choice: 5
Exiting...
```

## 5. Viva / Discussion Questions

1. **List of dicts:** Why is a list of dictionaries used to store records rather than parallel lists?
2. **`while True`:** What is the purpose of `while True`? How is the loop terminated?
3. **List comprehension for delete:** Explain how `[s for s in students if s['roll'] != roll]` deletes a record.
4. **`global` in delete:** Why is `global students` needed in `delete_student()` but not in `add_student()`?
5. **Persistence:** This program loses all data when it exits. How would you make the records persist between runs?

---

[Back to Main Index](../README.md)
