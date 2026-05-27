# Lecture 8 — Loops and Conditional Statements

## 1. Conditional Statements

Conditional statements allow your program to **make decisions** — run certain code only when a condition is true.

### 1.1 The `if` Statement

```python
age = 20

if age >= 18:
    print("You are an adult.")
```

If the condition `age >= 18` is `True`, the indented block runs. If it's `False`, nothing happens.

---

### 1.2 `if...else`

```python
age = 15

if age >= 18:
    print("You are an adult.")
else:
    print("You are a minor.")
```

The `else` block runs only when the `if` condition is `False`.

---

### 1.3 `if...elif...else`

Use `elif` (short for "else if") when you have **multiple conditions** to check.

```python
score = 72

if score >= 70:
    print("Grade: A")
elif score >= 60:
    print("Grade: B")
elif score >= 50:
    print("Grade: C")
elif score >= 40:
    print("Grade: D")
else:
    print("Grade: F")
```

> 💡 **Instructor Note:** Python checks conditions from top to bottom and stops as soon as it finds the first `True` condition.

---

### 1.4 Comparison Operators

| Operator | Meaning | Example |
|----------|---------|---------|
| `==` | Equal to | `x == 5` |
| `!=` | Not equal to | `x != 5` |
| `>` | Greater than | `x > 5` |
| `<` | Less than | `x < 5` |
| `>=` | Greater than or equal | `x >= 5` |
| `<=` | Less than or equal | `x <= 5` |

---

### 1.5 Logical Operators

Combine multiple conditions using `and`, `or`, `not`.

```python
age = 22
has_id = True

if age >= 18 and has_id:
    print("Access granted.")
else:
    print("Access denied.")
```

| Operator | Returns True when... |
|----------|----------------------|
| `and` | Both conditions are True |
| `or` | At least one condition is True |
| `not` | The condition is False |

---

## 2. Loops

Loops let you **repeat a block of code** multiple times without writing it over and over.

---

### 2.1 The `for` Loop

A `for` loop iterates over a sequence (list, string, tuple, range, etc.) and executes the block once for each item.

```python
fruits = ["apple", "banana", "mango"]

for fruit in fruits:
    print(fruit)
```

**Output:**
```
apple
banana
mango
```

### Looping Through a String

```python
for letter in "Python":
    print(letter)
```

### Looping with `range()`

`range()` generates a sequence of numbers.

```python
for i in range(5):         # 0, 1, 2, 3, 4
    print(i)

for i in range(1, 6):      # 1, 2, 3, 4, 5
    print(i)

for i in range(0, 10, 2):  # 0, 2, 4, 6, 8 (step of 2)
    print(i)
```

---

### 2.2 The `while` Loop

A `while` loop keeps running **as long as a condition is True**.

```python
count = 1

while count <= 5:
    print("Count:", count)
    count += 1
```

**Output:**
```
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
```

> ⚠️ **Warning:** If the condition never becomes `False`, you get an **infinite loop** and your program never stops. Always make sure the loop has a way to end!

---

### 2.3 `break` — Exit the Loop Early

```python
for i in range(10):
    if i == 5:
        break      # Stop the loop immediately
    print(i)

# Output: 0 1 2 3 4
```

### 2.4 `continue` — Skip One Iteration

```python
for i in range(7):
    if i == 3:
        continue   # Skip 3 and move to the next iteration
    print(i)

# Output: 0 1 2 4 5 6
```

---

## 3. Combining Loops and Conditionals

This is where things get really powerful.

```python
numbers = [5, 12, 7, 20, 3, 18, 9]

for num in numbers:
    if num > 10:
        print(num, "is greater than 10")
    else:
        print(num, "is 10 or less")
```

---

## 4. Nested Loops

A loop inside another loop.

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(i, "x", j, "=", i * j)
    print("---")
```

> 💡 **Instructor Note:** Think of nested loops as a clock — the outer loop is the hour hand, the inner loop is the minute hand. The minute hand completes a full round for every single tick of the hour hand.

---

## 5. Practical Example

```python
# Check all students and assign grades
students = [
    {"name": "Amara", "score": 85},
    {"name": "Bolu", "score": 52},
    {"name": "Chidi", "score": 43},
    {"name": "Dapo", "score": 67},
]

for student in students:
    name = student["name"]
    score = student["score"]

    if score >= 70:
        grade = "A"
    elif score >= 60:
        grade = "B"
    elif score >= 50:
        grade = "C"
    elif score >= 40:
        grade = "D"
    else:
        grade = "F"

    print(f"{name}: {score} → Grade {grade}")
```

**Output:**
```
Amara: 85 → Grade A
Bolu: 52 → Grade C
Chidi: 43 → Grade D
Dapo: 67 → Grade B
```

---

## 6. Quick Summary

| Concept | Purpose |
|---------|---------|
| `if / elif / else` | Make decisions based on conditions |
| `for` loop | Repeat for each item in a sequence |
| `while` loop | Repeat as long as a condition is True |
| `break` | Exit the loop immediately |
| `continue` | Skip to the next iteration |
| `range()` | Generate a sequence of numbers |

---

## 🧪 Try It Yourself

1. Write a program that takes a number and prints whether it is **positive**, **negative**, or **zero**.
2. Use a `for` loop to print all even numbers from 1 to 20.
3. Use a `while` loop to count down from 10 to 1, then print `"Blast off!"`.
4. Write a loop that goes through the list `[4, 7, 2, 9, 1, 5, 8]` and prints only the numbers greater than 5.

---

*End of Lecture 8*
