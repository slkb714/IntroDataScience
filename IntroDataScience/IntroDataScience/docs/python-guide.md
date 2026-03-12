# Python Guide

### A Complete Introduction for Absolute Beginners

---

## What Is Python?

Python is a **programming language** — a way to give precise instructions to a computer. But unlike most languages, Python was designed to read almost like plain English, making it one of the best first languages to learn.

You write instructions in a `.py` file (or in a notebook), run it, and the computer follows them top to bottom.

Python is used for: data science and analysis, automation and scripting, web development, machine learning and AI, and scientific research. It's the most widely used language in data and science fields, and one of the most popular languages overall.

---

## Why Python?

- Readable, clean syntax — less time fighting the language, more time solving problems
- Huge standard library — many tasks have built-in tools
- Enormous ecosystem of third-party packages (pandas, numpy, matplotlib, scikit-learn...)
- Massive community — answers to almost every question already exist online
- In-demand skill across data, tech, research, and more

---

## Part 1 — Installing Python

1. Go to [python.org/downloads](https://python.org/downloads)
2. Download the latest version (3.x)
3. Run the installer — on Windows, check "Add Python to PATH"

### Verify your installation

Open your terminal and run:

```bash
python --version
# or on some systems:
python3 --version
```

You should see something like `Python 3.11.4`.

---

## Part 2 — Running Python

### The Interactive Shell (REPL)

Type `python` (or `python3`) in your terminal and press Enter. You'll get a `>>>` prompt where you can type Python directly and see results immediately. Great for quick experiments.

```
>>> 2 + 2
4
>>> print("Hello!")
Hello!
>>> exit()
```

### Running a Script File

Write your code in a `.py` file, then run it from the terminal:

```bash
python my_script.py
```

---

## Part 3 — Variables and Data Types

A **variable** is a named container for storing a value. You create one with `=`:

```python
name = "Alice"
age = 30
height = 5.6
is_student = True
```

No need to declare types — Python figures it out. The four basic types:

| Type            | Example          | What it stores       |
| --------------- | ---------------- | -------------------- |
| `str` (string)  | `"hello"`        | Text                 |
| `int` (integer) | `42`             | Whole numbers        |
| `float`         | `3.14`           | Decimal numbers      |
| `bool`          | `True` / `False` | True or False values |

### Checking the type of a variable

```python
print(type(name))    # <class 'str'>
print(type(age))     # <class 'int'>
```

### Strings in detail

Strings are text, always wrapped in quotes (single or double — both work):

```python
greeting = "Hello, World!"
greeting = 'Hello, World!'   # same thing
```

Useful string operations:

```python
name = "alice"

print(name.upper())          # "ALICE"
print(name.capitalize())     # "Alice"
print(len(name))             # 5
print(name.replace("a", "e")) # "elice"
```

**f-strings** — the cleanest way to embed variables in text:

```python
name = "Alice"
age = 30
print(f"My name is {name} and I am {age} years old.")
# My name is Alice and I am 30 years old.
```

---

## Part 4 — Math and Operators

### Arithmetic

```python
5 + 3     # 8   (addition)
5 - 3     # 2   (subtraction)
5 * 3     # 15  (multiplication)
5 / 3     # 1.666... (division — always returns a float)
5 // 3    # 1   (floor division — rounds down)
5 % 3     # 2   (modulo — the remainder)
5 ** 3    # 125 (exponentiation — 5 to the power of 3)
```

### Comparison operators (return True or False)

```python
5 > 3     # True
5 < 3     # False
5 == 5    # True  (note: == for comparison, = for assignment)
5 != 3    # True  (not equal)
5 >= 5    # True
5 <= 4    # False
```

### Logical operators

```python
True and False   # False (both must be True)
True or False    # True  (at least one must be True)
not True         # False (flips it)
```

---

## Part 5 — Collections

### Lists

An ordered, changeable collection of items. Items can be any type, and can mix types.

```python
fruits = ["apple", "banana", "cherry"]

# Access by index (starts at 0)
print(fruits[0])    # "apple"
print(fruits[-1])   # "cherry" (negative = count from end)

# Slicing — get a portion
print(fruits[0:2])  # ["apple", "banana"]

# Common operations
fruits.append("mango")      # add to end
fruits.remove("banana")     # remove by value
fruits.insert(1, "grape")   # insert at position
print(len(fruits))          # number of items
```

### Dictionaries

Key-value pairs — like a real dictionary where you look up a word (key) to get its definition (value).

```python
person = {
    "name": "Alice",
    "age": 30,
    "city": "Lagos"
}

# Access a value
print(person["name"])       # "Alice"

# Add or update
person["email"] = "alice@example.com"
person["age"] = 31

# Check if a key exists
print("name" in person)     # True

# All keys, all values
print(person.keys())
print(person.values())
```

### Tuples

Like lists, but **immutable** (can't be changed after creation). Used for data that shouldn't change.

```python
coordinates = (10.5, 20.3)
print(coordinates[0])   # 10.5
```

### Sets

An unordered collection of **unique** values. Great for removing duplicates.

```python
colors = {"red", "blue", "green", "red"}  # duplicate "red" removed
print(colors)   # {"red", "blue", "green"}
```

---

## Part 6 — Control Flow

### If / Elif / Else

```python
temperature = 25

if temperature > 30:
    print("It's hot!")
elif temperature > 20:
    print("It's warm.")
else:
    print("It's cold.")
```

**Indentation is not optional in Python.** The 4-space indent is how Python knows what's inside an `if` block. Inconsistent indentation causes errors.

### For Loops

Repeat an action for each item in a collection:

```python
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)

# apple
# banana
# cherry
```

Loop over a range of numbers:

```python
for i in range(5):
    print(i)     # prints 0, 1, 2, 3, 4

for i in range(1, 6):
    print(i)     # prints 1, 2, 3, 4, 5
```

### While Loops

Repeat as long as a condition is True:

```python
count = 0

while count < 3:
    print(count)
    count += 1   # same as count = count + 1

# 0
# 1
# 2
```

### Break and Continue

```python
for i in range(10):
    if i == 5:
        break       # stop the loop entirely
    print(i)        # prints 0, 1, 2, 3, 4

for i in range(5):
    if i == 2:
        continue    # skip this iteration, keep going
    print(i)        # prints 0, 1, 3, 4
```

---

## Part 7 — Functions

A function is a reusable block of code. Define it once, call it anywhere.

```python
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")   # Hello, Alice!
greet("Bob")     # Hello, Bob!
```

### Returning values

```python
def add(a, b):
    return a + b

result = add(3, 4)
print(result)    # 7
```

### Default parameter values

```python
def greet(name, greeting="Hello"):
    print(f"{greeting}, {name}!")

greet("Alice")              # Hello, Alice!
greet("Alice", "Hi there")  # Hi there, Alice!
```

### Docstrings — documenting your functions

```python
def calculate_area(width, height):
    """
    Calculate the area of a rectangle.

    Args:
        width: the width of the rectangle
        height: the height of the rectangle

    Returns:
        The area as a number
    """
    return width * height
```

---

## Part 8 — Importing Modules

Python comes with a huge **standard library** — code you can import and use without installing anything.

```python
import math

print(math.sqrt(16))     # 4.0
print(math.pi)           # 3.14159...
print(math.floor(3.9))   # 3
```

```python
import random

print(random.randint(1, 10))    # random number between 1 and 10
print(random.choice(["a", "b", "c"]))  # random item from list
```

### Importing specific functions

```python
from math import sqrt, pi

print(sqrt(25))   # no need to write math.sqrt
```

### Installing third-party packages

For packages not in the standard library, use `pip`:

```bash
pip install pandas
pip install numpy
pip install matplotlib
```

Then import them just like built-in modules:

```python
import pandas as pd
import numpy as np
```

---

## Part 9 — Reading Error Messages

Errors are normal — even experienced developers see them constantly. Python's error messages are actually very helpful once you know how to read them.

```
Traceback (most recent call last):
  File "script.py", line 5, in <module>
    print(name)
NameError: name 'name' is not defined
```

Read it from the **bottom up**: the last line tells you what went wrong (`NameError`), and the lines above tell you where it happened (line 5).

### Common errors and what they mean

| Error               | What it means                                               |
| ------------------- | ----------------------------------------------------------- |
| `NameError`         | You used a variable that doesn't exist yet                  |
| `TypeError`         | You used the wrong type (e.g., adding a number to a string) |
| `IndexError`        | You tried to access a list index that doesn't exist         |
| `KeyError`          | You tried to access a dictionary key that doesn't exist     |
| `SyntaxError`       | Python can't parse your code — usually a typo               |
| `IndentationError`  | Inconsistent indentation                                    |
| `ZeroDivisionError` | You divided a number by zero                                |

---

## Part 10 — List Comprehensions

A compact, Pythonic way to build lists:

```python
# Regular way
squares = []
for i in range(1, 6):
    squares.append(i ** 2)

# List comprehension — same result, one line
squares = [i ** 2 for i in range(1, 6)]
print(squares)   # [1, 4, 9, 16, 25]
```

You can also add a filter:

```python
evens = [i for i in range(10) if i % 2 == 0]
print(evens)   # [0, 2, 4, 6, 8]
```

---

## Quick Reference Cheat Sheet

```python
# Variables
x = 10
name = "Alice"
is_valid = True

# String formatting
f"Hello, {name}!"

# List
items = [1, 2, 3]
items.append(4)
items[0]           # first item
items[-1]          # last item

# Dictionary
d = {"key": "value"}
d["key"]           # access value
d["new"] = "data"  # add entry

# If / elif / else
if x > 0:
    print("positive")
elif x == 0:
    print("zero")
else:
    print("negative")

# For loop
for item in items:
    print(item)

# While loop
while x > 0:
    x -= 1

# Function
def my_func(a, b=10):
    return a + b

# Import
import math
from math import sqrt

# List comprehension
[x**2 for x in range(5)]
[x for x in range(10) if x % 2 == 0]
```

---

## Common Mistakes to Avoid

| Mistake                                   | Fix                                                  |
| ----------------------------------------- | ---------------------------------------------------- |
| Using `=` instead of `==` in comparisons  | `if x == 5:` not `if x = 5:`                         |
| Inconsistent indentation                  | Use 4 spaces consistently; never mix tabs and spaces |
| Accessing a list index that doesn't exist | Check `len(list)` first, or use a try/except block   |
| Modifying a list while looping over it    | Loop over a copy: `for item in items[:]`             |
| Forgetting `return` in a function         | A function without `return` returns `None`           |
| Comparing to `True`/`False` explicitly    | Write `if is_valid:` not `if is_valid == True:`      |

---

## Where to Practice

- **[python.org/shell](https://www.python.org/shell)** — Run Python directly in your browser, no setup needed
- **[replit.com](https://replit.com)** — Free online Python environment
- **[exercism.org/tracks/python](https://exercism.org/tracks/python)** — Free exercises with feedback from mentors
- **[kaggle.com/learn](https://kaggle.com/learn)** — Free Python and data science courses with in-browser notebooks

---

## You're Ready

Python is a language that rewards practice over memorization. The best next step is to pick a small project you're actually curious about — cleaning a dataset, automating a repetitive task, analyzing something you find interesting — and start writing code. You'll learn far more from building something real than from any tutorial alone.
