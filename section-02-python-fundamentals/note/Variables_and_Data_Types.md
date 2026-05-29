# Lecture 5 — Variables and Data Types

## 1. What is a Variable?

A **variable** is like a labelled box where you store a piece of information. Python lets you create a variable simply by giving it a name and assigning a value to it.

```python
name = "Alice"
age = 25
height = 5.6
```

- `name`, `age`, and `height` are the **variable names** (labels on the box).
- `"Alice"`, `25`, and `5.6` are the **values** stored inside.

> 💡 **Instructor Note:** Use a real-world analogy — a variable is like a contact name in your phone. "Mum" stores a phone number; you just use the name, not the number.

---

## 2. Rules for Naming Variables

| Rule | Example |
|------|---------|
| Must start with a letter or underscore | `_name`, `age` ✅ |
| Cannot start with a number | `1name` ❌ |
| Cannot contain spaces | `my name` ❌ → use `my_name` ✅ |
| Case-sensitive | `Age` and `age` are different variables |
| Cannot be a Python keyword | `if`, `for`, `while` ❌ |

---

## 3. Core Data Types in Python

Python has several built-in data types. The most important ones for beginners are:

### 3.1 Integer (`int`)
Whole numbers — no decimal point.

```python
score = 100
year = 2024
temperature = -5
```

### 3.2 Float (`float`)
Numbers with a decimal point.

```python
price = 9.99
pi = 3.14159
gpa = 3.7
```

### 3.3 String (`str`)
Text — always wrapped in quotes (single or double).

```python
first_name = "John"
greeting = 'Hello, World!'
sentence = "Python is fun"
```

### 3.4 Boolean (`bool`)
Only two possible values: `True` or `False`.

```python
is_logged_in = True
has_paid = False
is_raining = True
```

> 💡 **Instructor Note:** Booleans are the foundation of decision-making in code. Emphasise that `True` and `False` must be capitalised — Python is case-sensitive.

---

## 4. Checking the Data Type — `type()`

Use the built-in `type()` function to find out what type a variable is.

```python
x = 42
print(type(x))       # <class 'int'>

y = 3.14
print(type(y))       # <class 'float'>

z = "hello"
print(type(z))       # <class 'str'>

a = True
print(type(a))       # <class 'bool'>
```

---

## 5. Type Casting (Converting Between Types)

Sometimes you need to convert a value from one type to another.

```python
# String to Integer
age_str = "25"
age_int = int(age_str)
print(age_int + 5)    # 30

# Integer to Float
num = 7
print(float(num))     # 7.0

# Number to String
score = 100
print("Your score is: " + str(score))   # Your score is: 100

# String to Float
price = float("19.99")
print(price)          # 19.99
```

> ⚠️ **Common Error:** You cannot convert a non-numeric string like `"hello"` to an integer — Python will throw a `ValueError`.

---

## 6. Multiple Assignment

Python allows you to assign multiple variables in one line.

```python
x, y, z = 1, 2, 3
print(x, y, z)    # 1 2 3

# Assign the same value to multiple variables
a = b = c = 0
print(a, b, c)    # 0 0 0
```

---

## 7. Practical Example

```python
# Student profile
student_name = "Emeka"
student_age = 20
student_gpa = 3.85
is_enrolled = True

print("Name:", student_name)
print("Age:", student_age)
print("GPA:", student_gpa)
print("Enrolled:", is_enrolled)
print("Data type of GPA:", type(student_gpa))
```

**Output:**
```
Name: Emeka
Age: 20
GPA: 3.85
Enrolled: True
Data type of GPA: <class 'float'>
```

---

## 8. Quick Summary

| Data Type | Keyword | Example |
|-----------|---------|---------|
| Integer | `int` | `42` |
| Float | `float` | `3.14` |
| String | `str` | `"hello"` |
| Boolean | `bool` | `True` / `False` |

---

## Try It Yourself

1. Create a variable for your name, age, and favourite number.
2. Print each variable and its type using `type()`.
3. Convert your age to a string and print the message: `"I am 20 years old."` (using your actual age).

---

*End of Lecture 5*
