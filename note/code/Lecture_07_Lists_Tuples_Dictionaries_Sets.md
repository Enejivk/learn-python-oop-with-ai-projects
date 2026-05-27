# Lecture 7 — Lists, Tuples, Dictionaries, and Sets

## 1. Why Do We Need Collections?

So far, we've stored one value per variable. But what if you need to store a list of 30 student names? Creating 30 separate variables isn't practical. Python gives us **collection data types** to store multiple values in a single variable.

---

## 2. Lists

A **list** is an ordered, changeable (mutable) collection that allows duplicates. Lists are the most commonly used collection in Python.

### Creating a List
```python
fruits = ["apple", "banana", "mango", "orange"]
numbers = [10, 20, 30, 40, 50]
mixed = ["Alice", 25, True, 3.14]   # Lists can hold different types
```

### Accessing Items (Indexing)
Lists are **zero-indexed** — the first item is at index `0`.

```python
fruits = ["apple", "banana", "mango"]
print(fruits[0])   # apple
print(fruits[1])   # banana
print(fruits[-1])  # mango  (negative index = count from the end)
```

### Modifying a List
```python
fruits = ["apple", "banana", "mango"]

fruits.append("orange")      # Add to the end
fruits.insert(1, "grape")    # Insert at index 1
fruits.remove("banana")      # Remove by value
fruits.pop()                 # Remove last item
print(len(fruits))           # Number of items
```

### Looping Through a List
```python
for fruit in fruits:
    print(fruit)
```

> 💡 **Instructor Note:** Lists are like a shopping list — ordered, you can add or remove items, and the same item can appear more than once.

---

## 3. Tuples

A **tuple** is like a list, but it is **immutable** — once created, it cannot be changed. Tuples use parentheses `()`.

### Creating a Tuple
```python
coordinates = (10.5, 6.3)
days = ("Monday", "Tuesday", "Wednesday")
single = (42,)    # A tuple with ONE item needs a trailing comma!
```

### Accessing Items
```python
print(days[0])    # Monday
print(days[-1])   # Wednesday
```

### When to Use Tuples?
- When data should **not change** (e.g., GPS coordinates, RGB colour values, days of the week)
- Tuples are slightly **faster** than lists

```python
# Example: fixed configuration
screen_size = (1920, 1080)
```

> ⚠️ **Key Difference:** `list` = mutable (changeable), `tuple` = immutable (fixed)

---

## 4. Dictionaries

A **dictionary** stores data as **key-value pairs**. Instead of using a numeric index, you access values by their key — like looking up a word in a real dictionary.

### Creating a Dictionary
```python
student = {
    "name": "Emeka",
    "age": 20,
    "course": "Computer Science",
    "gpa": 3.8
}
```

### Accessing Values
```python
print(student["name"])     # Emeka
print(student["gpa"])      # 3.8

# Safer method — won't crash if key doesn't exist
print(student.get("age"))           # 20
print(student.get("phone", "N/A"))  # N/A (default if missing)
```

### Modifying a Dictionary
```python
student["age"] = 21                 # Update a value
student["email"] = "emeka@uni.com"  # Add a new key
del student["gpa"]                  # Delete a key
```

### Looping Through a Dictionary
```python
for key, value in student.items():
    print(key, ":", value)
```

> 💡 **Instructor Note:** A dictionary is like a contact card. Every piece of information has a label (key) — "Name", "Phone", "Email" — and a value next to it.

---

## 5. Sets

A **set** is an unordered collection of **unique** items. Sets automatically remove duplicates.

### Creating a Set
```python
colours = {"red", "blue", "green", "red", "blue"}
print(colours)   # {'red', 'blue', 'green'} — duplicates removed!
```

### Adding and Removing
```python
colours.add("yellow")
colours.remove("blue")
print(colours)
```

### Set Operations
Sets are great for mathematical operations:

```python
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}

print(A | B)   # Union — all items: {1, 2, 3, 4, 5, 6}
print(A & B)   # Intersection — common items: {3, 4}
print(A - B)   # Difference — in A but not B: {1, 2}
```

> 💡 **Instructor Note:** Sets are perfect when you want to eliminate duplicates from a list: just convert the list to a set.

```python
names = ["Alice", "Bob", "Alice", "Charlie", "Bob"]
unique_names = set(names)
print(unique_names)   # {'Alice', 'Bob', 'Charlie'}
```

---

## 6. Side-by-Side Comparison

| Feature | List | Tuple | Dictionary | Set |
|---------|------|-------|------------|-----|
| Syntax | `[ ]` | `( )` | `{ key: val }` | `{ }` |
| Ordered | ✅ Yes | ✅ Yes | ✅ Yes (3.7+) | ❌ No |
| Mutable | ✅ Yes | ❌ No | ✅ Yes | ✅ Yes |
| Duplicates | ✅ Yes | ✅ Yes | Keys: ❌ No | ❌ No |
| Access by | Index | Index | Key | — |

---

## 7. Practical Example

```python
# Store student info using all four types
student_names = ["Amara", "Bolu", "Chidi", "Amara"]  # List (allows duplicates)
fixed_grades = ("A", "B", "C", "D", "F")              # Tuple (fixed grading scale)

student_profile = {                                    # Dictionary (structured info)
    "name": "Bolu",
    "age": 19,
    "major": "Engineering"
}

registered_courses = {"MTH101", "ENG201", "CSC102", "MTH101"}  # Set (no duplicates)

print("Students:", student_names)
print("Grades scale:", fixed_grades)
print("Profile:", student_profile)
print("Courses:", registered_courses)
```

---

## Try It Yourself

1. Create a list of 5 of your favourite movies. Print the first and last one.
2. Create a tuple of the 7 days of the week. Try to change a value — what happens?
3. Create a dictionary for a book with keys: `title`, `author`, `year`, `pages`. Print each key-value pair.
4. Create a set from this list and print it: `[1, 2, 2, 3, 4, 4, 4, 5]`

---

*End of Lecture 7*
