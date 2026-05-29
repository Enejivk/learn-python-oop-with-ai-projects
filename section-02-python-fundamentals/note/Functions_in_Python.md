# Lecture 6 — Functions in Python

## 1. What is a Function?

A **function** is a named block of code that performs a specific task. Instead of writing the same code over and over again, you define it once and call it whenever you need it.

Think of a function like a recipe — you write it once, and any time you want that dish, you just follow the recipe by name.

```python
def greet():
    print("Hello! Welcome to Python.")

# Calling the function
greet()   # Output: Hello! Welcome to Python.
```

> 💡 **Instructor Note:** Show students that without functions, they would need to copy-paste the same lines repeatedly. Functions solve that problem — they encourage the DRY principle: **Don't Repeat Yourself.**

---

## 2. Defining a Function

The syntax for creating a function in Python:

```python
def function_name():
    # code block (indented)
    statement
```

- `def` — keyword that tells Python you're defining a function
- `function_name` — the name you give your function (follow variable naming rules)
- `:` — colon at the end of the `def` line
- **Indented block** — the body of the function (everything inside must be indented)

---

## 3. Parameters and Arguments

Functions become much more powerful when they can accept **inputs**.

- A **parameter** is the variable name listed in the function definition.
- An **argument** is the actual value passed when you call the function.

```python
def greet(name):           # 'name' is the parameter
    print("Hello,", name)

greet("Chidi")             # 'Chidi' is the argument
greet("Fatima")            # 'Fatima' is the argument
```

**Output:**
```
Hello, Chidi
Hello, Fatima
```

### Multiple Parameters

```python
def add(a, b):
    print(a + b)

add(3, 5)     # 8
add(10, 20)   # 30
```

---

## 4. Return Values

A function can **send back a result** using the `return` keyword.

```python
def multiply(x, y):
    result = x * y
    return result

answer = multiply(4, 5)
print(answer)    # 20
```

> ⚠️ **Important:** Once Python hits a `return` statement, the function stops executing immediately. Any code after `return` is ignored.

---

## 5. `print()` vs `return` — What's the Difference?

This is one of the most common points of confusion for beginners.

| | `print()` | `return` |
|--|-----------|---------|
| What it does | Displays output to the screen | Sends a value back to the caller |
| Can be stored? | No | Yes |
| Use case | Showing information to the user | Getting a result to use later |

```python
def add_print(a, b):
    print(a + b)       # Just displays it

def add_return(a, b):
    return a + b       # Sends it back

x = add_print(3, 4)   # Prints 7, but x is None
y = add_return(3, 4)  # y is now 7 — we can use it!
print(y + 10)         # 17
```

> 💡 **Instructor Note:** Ask students: *"If you're baking bread and the recipe just shows you what bread looks like vs. actually gives you the bread — which is more useful?"* — that's `print` vs `return`.

---

## 6. Default Parameter Values

You can give a parameter a **default value** so the function still works even if no argument is passed.

```python
def greet(name="stranger"):
    print("Hello,", name)

greet("Amara")    # Hello, Amara
greet()           # Hello, stranger
```

---

## 7. Keyword Arguments

You can pass arguments by specifying the parameter name, making your code more readable.

```python
def profile(name, age, city):
    print(f"{name} is {age} years old and lives in {city}.")

profile(age=21, city="Lagos", name="Tunde")
# Tunde is 21 years old and lives in Lagos.
```

---

## 8. Practical Example

```python
def calculate_grade(score):
    if score >= 70:
        return "A"
    elif score >= 60:
        return "B"
    elif score >= 50:
        return "C"
    elif score >= 40:
        return "D"
    else:
        return "F"

student_score = 75
grade = calculate_grade(student_score)
print(f"Score: {student_score} — Grade: {grade}")
```

**Output:**
```
Score: 75 — Grade: A
```

---

## 9. Quick Summary

| Concept | Description |
|---------|-------------|
| `def` | Keyword to define a function |
| Parameters | Variables in the function definition |
| Arguments | Values passed when calling the function |
| `return` | Sends a value back from the function |
| Default values | Used when no argument is passed |

---

##Try It Yourself

1. Write a function called `square()` that takes a number and returns its square.
2. Write a function called `full_name()` that takes a first name and last name and prints the full name.
3. Write a function called `is_even()` that returns `True` if a number is even, and `False` if it is not.

---

*End of Lecture 6*
