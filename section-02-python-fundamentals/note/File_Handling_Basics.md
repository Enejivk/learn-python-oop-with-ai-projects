# File Handling Basics

## 1. Why File Handling?

Everything we've done so far exists only while the program is running — when it stops, the data is gone. **File handling** lets us:
- Save data permanently to a file
- Read data that was saved earlier
- Log information for later review

> 💡 **Instructor Note:** Relate this to everyday apps — WhatsApp saves your messages, Word saves your documents. All of that is file handling under the hood.

---

## 2. Opening a File — `open()`

Python's built-in `open()` function is used to open a file.

```python
file = open("filename.txt", "mode")
```

### File Modes

| Mode | Description |
|------|-------------|
| `"r"` | **Read** — opens an existing file for reading (default) |
| `"w"` | **Write** — creates a new file, or **overwrites** an existing one |
| `"a"` | **Append** — adds to the end of an existing file without deleting content |
| `"x"` | **Create** — creates a new file; fails if it already exists |

> ⚠️ **Warning:** Using `"w"` mode on an existing file will **erase all its contents** immediately!

---

## 3. The `with` Statement (Best Practice)

Instead of manually opening and closing a file, use `with`. It automatically closes the file when you're done — even if an error occurs.

```python
# ✅ Recommended approach
with open("notes.txt", "r") as file:
    content = file.read()
    print(content)
# File is automatically closed here
```

```python
# ❌ Not recommended (forgetting to close can cause problems)
file = open("notes.txt", "r")
content = file.read()
file.close()
```

---

## 4. Reading Files

### 4.1 Read the Entire File — `.read()`
```python
with open("students.txt", "r") as file:
    content = file.read()
    print(content)
```

### 4.2 Read Line by Line — `.readline()`
```python
with open("students.txt", "r") as file:
    line1 = file.readline()    # Reads one line
    line2 = file.readline()    # Reads the next line
    print(line1)
    print(line2)
```

### 4.3 Read All Lines as a List — `.readlines()`
```python
with open("students.txt", "r") as file:
    lines = file.readlines()    # Returns a list of lines
    for line in lines:
        print(line.strip())     # .strip() removes the \n at the end of each line
```

### 4.4 Loop Through a File Directly (Most Efficient)
```python
with open("students.txt", "r") as file:
    for line in file:
        print(line.strip())
```

---

## 5. Writing to Files

### 5.1 Write Mode — `"w"` (Overwrites everything)
```python
with open("output.txt", "w") as file:
    file.write("Hello, World!\n")
    file.write("This is a new file.\n")
```

> After running this, `output.txt` will contain only those two lines.

### 5.2 Append Mode — `"a"` (Adds without erasing)
```python
with open("output.txt", "a") as file:
    file.write("This line is added at the end.\n")
```

### Writing Multiple Lines at Once — `.writelines()`
```python
lines = ["Line 1\n", "Line 2\n", "Line 3\n"]

with open("output.txt", "w") as file:
    file.writelines(lines)
```

---

## 6. Checking If a File Exists

Before reading a file, it's good practice to check if it exists to avoid errors.

```python
import os

if os.path.exists("students.txt"):
    with open("students.txt", "r") as file:
        print(file.read())
else:
    print("File not found!")
```

---

## 7. Handling Errors with `try...except`

What if you try to open a file that doesn't exist? Python will throw a `FileNotFoundError`. Use `try...except` to handle it gracefully.

```python
try:
    with open("data.txt", "r") as file:
        content = file.read()
        print(content)
except FileNotFoundError:
    print("Error: The file 'data.txt' was not found.")
except Exception as e:
    print("An unexpected error occurred:", e)
```

> 💡 **Instructor Note:** Error handling is a sign of professional code. Programs should not crash — they should inform the user what went wrong.

---

## 8. Practical Example

Let's simulate saving and loading student records.

### Step 1: Save student names to a file
```python
students = ["Amara", "Bolu", "Chidi", "Dapo", "Emeka"]

with open("students.txt", "w") as file:
    for student in students:
        file.write(student + "\n")

print("Student list saved!")
```

### Step 2: Read the student list back
```python
print("Reading student list from file:")

with open("students.txt", "r") as file:
    for line in file:
        print("-", line.strip())
```

### Step 3: Add a new student (append)
```python
with open("students.txt", "a") as file:
    file.write("Fatima\n")

print("New student added!")
```

---

## 9. Quick Summary

| Operation | Method / Mode | Notes |
|-----------|--------------|-------|
| Open a file | `open("file.txt", mode)` | Always use `with` |
| Read all | `.read()` | Returns a single string |
| Read line | `.readline()` | Reads one line at a time |
| Read all lines | `.readlines()` | Returns a list |
| Write (overwrite) | `"w"` mode + `.write()` | Erases existing content |
| Append | `"a"` mode + `.write()` | Adds to the end |
| Check exists | `os.path.exists()` | Requires `import os` |
| Handle errors | `try...except` | Prevents crashes |

---

## 🧪 Try It Yourself

1. Create a file called `diary.txt` and write three lines to it — each line should be a sentence.
2. Read the file back and print each line with its line number (e.g., `1: Today was a good day.`)
3. Append one more line to `diary.txt` without overwriting the existing content.
4. Wrap your file-reading code in a `try...except` block to handle the case where the file doesn't exist.

---

*End of Lecture 9*
