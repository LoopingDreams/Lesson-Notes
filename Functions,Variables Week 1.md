# Functions, Variables

## Introduction to Programming
- Programming = giving instructions to a computer
- Computers only understand **binary (0s and 1s)**
- Programming languages bridge **human logic → machine code**
- **Python** = high-level, beginner-friendly, widely used

---

## Algorithms & Pseudocode
- **Algorithm** = step-by-step procedure to solve a problem
- **Pseudocode** = human-readable outline of an algorithm
- Helps bridge **ideas → actual code**
- Example pseudocode for making tea:
  ```
  1. Boil water
  2. Add tea leaves
  3. Steep for 5 minutes
  4. Serve
  ```

---

## Creating Code in Python
- VS Code is a text editor. In addition to editing text, you can visually browse files and run text-based commands at a terminal.
- In the terminal, you can execute `code hello.py` to start coding.
- Save scripts with `.py` extension
- Write code in a **text editor** (e.g., VS Code)
- Run code in a terminal:
  ```bash
  python hello.py
  ```
- First program:
  ```python
  print("hello, world")
  ```
- Python is **interpreted** (executes line by line)

---

## Functions
- **Function** = reusable block of code
- Built-in example: `print()`
- Functions can take **arguments (inputs)**
- Example:
  ```python
  print("CS50")
  print("Python")
  ```

---

## Strings
- **String** = text between quotes
- Examples: `"hello"`, `"123"`, `"CS50"`
- `print()` can output strings
- Multiple arguments:
  ```python
  print("hello,", "world")
  ```

---

## Comments
- Comments = notes for humans, ignored by Python
- Written with `#`
- Examples:
  ```python
  # This is a comment
  print("Hello")  # inline comment
  ```

---

## Variables
- Variables = names that store values
- Example:
  ```python
  name = "Alice"
  age = 20
  ```
- Variables make programs reusable and flexible

---

## Input
- `input()` = get info from the user
- Example:
  ```python
  name = input("What's your name? ")
  print("Hello,", name)
  ```

---

## Type Conversion
- Input returns **strings** by default
- Convert to numbers with:
  - `int()` → integer
  - `float()` → decimal
- Example:
  ```python
  age = int(input("Age: "))
  print(age + 1)
  ```

---

## Operators
- Arithmetic operators: `+`, `-`, `*`, `/`, `%`, `**`
- Examples:
  ```python
  print(6 + 2)  # 8
  print(6 ** 2) # 36
  ```

---

## Formatting Output
- Use **f-strings** to format variables:
  ```python
  name = "Alice"
  print(f"Hello, {name}")
  ```
- Cleaner and easier than concatenation

---

## Further Improving Your First Python Program
- Clean user input with `.strip()` and `.title()`:
  ```python
  name = input("What's your name? ").strip().title()
  print(f"Hello, {name}")
  ```

---

## Strings and Parameters
- Functions can take multiple arguments (parameters)
- Example:
  ```python
  print("hello", "world")
  # Output: hello world
  ```

---

## A Small Problem with Quotation Marks
- Strings can use `' '` or `" "`
- Examples:
  ```python
  print("Alice's book")
  print('She said "hi"')
  ```

---

## Formatting Strings
- Old way: concatenation
  ```python
  print("Hello, " + name)
  ```
- Better way: f-strings
  ```python
  print(f"Hello, {name}")
  ```

---

## More on Strings
- String methods:
  - `.upper()` → ALL CAPS
  - `.lower()` → all lowercase
  - `.strip()` → remove spaces
  - `.title()` → Capitalize Each Word
- Example:
  ```python
  name = " alice "
  print(name.strip().title())  # Alice
  ```

---

## Integers (int)
- `int` = whole numbers
- Example:
  ```python
  x = 5
  y = 3
  print(x + y)  # 8
  ```
- Convert with `int()`

---

## Readability Wins
- Clear, readable code > short, clever code
- Use descriptive variable names
- Example:
  ```python
  n = int(input("Number: "))   # less clear
  age = int(input("Age: "))    # clearer
  ```

---

## Float Basics
- `float` = decimal numbers
- Example:
  ```python
  pi = 3.14159
  print(pi * 2)
  ```
- Convert with `float()`

---

## More on Floats
- Floats may have **rounding issues**
- Example:
  ```python
  print(0.1 + 0.2)
  # Output: 0.30000000000000004
  ```
- Computers approximate decimals in binary

---

## Defining Your Own Functions
- Use `def` keyword
- Example:
  ```python
  def hello():
      print("Hello!")

  hello()
  ```

---

## Returning Values
- Functions can return results with `return`
- Example:
  ```python
  def square(n):
      return n * n

  print(square(4))  # 16
  ```

---

## Summing Up (Week 0)
- Python basics covered:
  - Programs & algorithms
  - Strings & functions
  - Comments
  - Variables
  - Input & type conversion
  - Integers & floats
  - Readability
  - Custom functions & return values
- Foundation for more advanced concepts
