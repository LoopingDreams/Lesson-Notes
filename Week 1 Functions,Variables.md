## **Introduction: Your First Steps in Python**
<p align="center">
  <img src="pictures/Frieren.png"/>
</p>

- Welcome to Python! 
- Week 1 is all about learning the fundamental building blocks of the language. 
- We'll cover how to display information, 
- get input from a user, 
- store data in variables, and 
- organize our code into reusable blocks called functions.
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
- The very first thing you typically do in a new language is make it say something. In Python, we use the `print()` function for this.
- VS Code is a text editor. In addition to editing text, you can visually browse files and run text-based commands at a terminal.
- In the terminal, you can execute `code hello.py` to start coding.
- Save scripts with `.py` extension
- Write code in a **text editor** (e.g., VS Code, Notepad++, Notepad, Codeblocks, etc...)
- Run code in a terminal:
  ```bash
  python hello.py
  ```
- First program:
  ```python
  print("hello, world")
  ```
  ```
- Python is **interpreted** (executes line by line)

---

## Functions
- **Function** = reusable block of code
- A **function** is a pre-written piece of code that performs a specific action. You "call" a function by writing its name followed by parentheses `()`.
- Built-in example: `print()`  `max()` `min()` etc....
- [An Example List of functions](https://www.w3schools.com/python/python_ref_functions.asp)
- Functions can take **arguments (inputs)**
- The text you want to print, like `"hello, world"`, is called a **string** (or `str`). A string is a sequence of characters, and you must enclose it in either double quotes (`"`) or single quotes 
- (`'`).
- Example:
  
  ```python
 # The text "hello, world" is an argument passed to the print function. print("hello, world")
  print("Hello, World!")

  ```
```

---

# Bugs 

- A **bug** is an error in your program. A common early bug is a `SyntaxError`, which means you've broken one of Python's grammar rules.
-  Bugs are a natural part of coding. These are mistakes, problems for you to solve! Don’t get discouraged! 
- Error messages can often inform you of your mistakes and provide clues on how to fix them. However, there will be many times when the interpreter is not this helpful.

```python
# This will cause a SyntaxError because the closing quote is missing.
print("hello, world)
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
 - What if you want to print a quote?
 - You can use another type of quote to enclose the string.
 ```python
 print('He said, "Hello!"')
```

- Or you can use an **escape sequence**. A backslash `\` tells Python that the next character has a special meaning. For example, `\"` represents a literal double quote.

```python
print("He said, \"Hello!\"")
```
---
## Improvements
- This program is static, lets make it more interesting by making it interactive.
- We can do this by using `input()` function, which prompts the user for text and waits for a response.
- Example:
```python
input("What's your name? ")
print("hello, world")
```
- When you run this, the program will first ask for your name and then print "hello, world".

---

## Comments
- Comments = notes for humans to easily understand what the specific part of the code does and is ignored by Python
- Written with `#`
- Examples:
  ```python
  # This is a comment
  print("Hello")  # inline comment
  ```
- lets add a comment to our program it would turn into this.
```python

#Hellooo!!!!
input("What's your name? ")
print("hello, world") #earth 
```

---
## Input
- `input()` = get info from the user
- Example:
  ```python
  name = input("What's your name? ")
  print("Hello,", name)
  ```

---

## **Variables**
- To store the data we get from `input()`, we need a **variable**. A variable is a named container for a value. We use the equals sign (`=`), the assignment operator, to store a value in a variable.
- Variables = names that store values
- Example:

```python
# Ask the user for their name and store it in the 'name' variable.
# Variable names in Python are traditionally written in snake_case.
name = input("What's your name? ")
# Say hello to the user
print("hello,")
print(name)
  ```
  
- so we have the variable `name` from the `input` and using the variable we print it out below
- Variables make programs reusable and flexible

---

## **Strings and Parameters**

- A **string** (or `str`) is a sequence of characters, like text.
- Looking back a bit in our code, there's a visual side effect of having the result appearing in another line

- Functions take arguments that influence their behavior. If we look at the documentation for [`print`](https://docs.python.org/3/library/functions.html#print) you’ll notice we can learn a lot about the arguments that the print function takes.
- the `print` function automatically includes the argument `end='\n'`. This `\n` indicates that the `print` function will automatically create a line break when run.
  
- However, we can technically provide an argument for `end` ourselves such that a new line is not created
- Modifying the code like this
```python
# Ask the user for their name
name = input("What's your name? ")
print("hello,", end="")
print(name)
```

By providing `end=""` we are overwriting the default value of `end` such that it never creates a new line after this first print statement. Providing the name as “David”, the output in the terminal window will be `hello, David`.

- A more elegant way to print multiple items is to pass them as separate arguments to the `print()` function. `print()` will automatically put a space between them. The placeholder for an argument in a function's definition is called a **parameter**.


```python
name = input("What's your name? ")

# Here, "hello," and the variable 'name' are two separate arguments.
print("hello,", name)
```

---

## **A small problem with quotation marks**

If your string needs to contain a quote, you can either enclose the string with the _other_ type of quote or use a backslash (`\`) to **escape** the inner quote.



```python
# Using single quotes to enclose a string with double quotes
print('He said, "Hello!"')

# Using a backslash to escape the inner double quotes
print("She said, \"Hi!\"")
```

---

## **Formatting Strings (f-Strings)**

The best way to embed variables directly into strings is with **f-strings** (formatted strings). Simply prefix the string with an `f` and place your variables inside curly braces `{}`.


```python
name = input("What's your name? ")

# This f-string embeds the value of 'name' directly.
print(f"hello, {name}")
```

---

## **More on Strings**

Strings come with built-in functions called **methods**. You call them using dot notation (`variable.method()`). You can also **chain** methods together to perform multiple actions in one line.

- `str.strip()`: Removes leading and trailing whitespace.

```python
# Ask the user for their name
name = input("What's your name? ")

# Remove whitespace from the str
name = name.strip()

# Print the output
print(f"hello, {name}")
```

- `str.title()`: Capitalizes the first letter of each word.
```python
# Ask the user for their name
name = input("What's your name? ")

# Remove whitespace from the str
name = name.strip()

# Capitalize the first letter of each word
name = name.title()

# Print the output
print(f"hello, {name}")
```
- Notice that you can modify your code to be more efficient:

```python
# Chaining methods: input is received, whitespace is stripped,
# and then the result is title-cased.
name = input("What's your name? ").strip().title()

print(f"hello, {name}")
```
 
- You can learn more about strings in Python’s documentation on [`str`](https://docs.python.org/3/library/stdtypes.html#str)

---

## **Integers or `int`**

-   In Python, an integer is referred to as an `int`.

| Operator               | Description                               | Example                                                         |
| ---------------------- | ----------------------------------------- | --------------------------------------------------------------- |
| **+** (Addition)       | Adds two numbers together.                | 5 + 3 = 8                                                       |
| **-** (Subtraction)    | Finds the difference between two numbers. | 10 - 4 = 6                                                      |
| ***** (Multiplication) | Multiplies two numbers.                   | 7 * 6 = 42                                                      |
| **/** (Division)       | Divides one number by another.            | 20 / 5 = 4                                                      |
| **%** (Modulo)         | Returns the remainder of a division.      | 10 % 3 = 1 (because 10 divided by 3 is 3 with a remainder of 1) |
An **integer** (`int`) is a whole number. Since `input()` always gives back a string, you must convert it to an `int` if you want to do math. This conversion is called **type casting**.


```python
# Cast the string from input() into an integer
x = int(input("What's x? "))
y = int(input("What's y? "))

# Now we can perform mathematical operations
print(x + y)
```

 Using what we learned earlier we can make this more interactive using `input()`

```python
x = input("What's x? ")
y = input("What's y? ")

z = x + y

print(z)
```

Running it gives us a wrong output. Why might this be?

Prior, we have seen how the `+` sign concatenates two strings. Because your input from your keyboard on your computer comes into the interpreter as text, it is treated as a `str` string. We, therefore, need to convert this input from a string to an integer. We can do so as follows:

```python
x = input("What's x? ")
y = input("What's y? ")

z = int(x) + int(y)

print(z)
```

We can further improve our program as follows:

```python
x = int(input("What's x? "))
y = int(input("What's y? "))

print(x + y)
```

 This shows that you can run functions on functions although the inner function run first, then the other one runs after. First the `input` function is run, Then the `int` function.

 You can always learn more about it in Python's documentation of  [`int`](https://docs.python.org/3/library/functions.html?highlight=float#int).


---

## **Readability Wins**

Regardless of what approach you take to a programming task, remember that your code must be **readable.** You should use comments to give yourself and others clues about what your code is doing. Further, you should create code in a way that is readable.

While you can nest functions like `print(int(input("x: ")) + int(input("y: ")))`, it can be hard to read. Writing clear, step-by-step code is often better than writing the most compact code possible. **Readability wins**.

---

## **Float Basics & More on Floats**

A **float** is a number with a decimal point. Just like with integers, you can cast strings to floats using the `float()` function.

This is in contrast to an **int** (integer), which can only represent whole numbers. When you get input from a user using the `input()` function, it returns a **string** by default, even if the user types in a number. Therefore, to perform mathematical operations with decimals, you must explicitly convert the string to a float using `float()`.

Now, when you perform math with floats, you can sometimes end up with what's called **floating-point imprecision**. It's a quirk of how computers store and calculate numbers. You might divide 1 by 10 and get `0.09999999999999999`. That's not what we want

The built-in `round()` function can be used to round a float to a specified number of decimal places. You can also format numbers directly inside f-strings.

But what if you want to format that number for display, maybe to show it as currency? That's when you use an **f-string**, or "formatted string literal." It's a way of embedding expressions inside string literals, and it gives you a lot of control over formatting.

Consider this line `print(f"${z:,.2f}")`

- The `f` tells Python it's a formatted string.

- The `$` is just a literal character.

- The `{}` is where you put your variable, `z`.

- And after the colon, you have a **format specifier**.

    - The `,` adds a comma as a thousands separator.
        
    - The `.2f` tells Python to format the number as a float with exactly two digits after the decimal point.

```python
x = float(input("What's x? "))
y = float(input("What's y? "))

# Round the sum of x and y to two decimal places
z = round(x + y, 2)
print(z) # e.g., 6.91

# An f-string can format this for currency, adding comma separators
# and ensuring two decimal places.
print(f"${z:,.2f}") # e.g., $1,000.00
```

---

## **`def`**

To keep code organized and reusable, we can define our own functions using the `def` keyword. It's a convention to put the main logic of your program inside a function called `main`.

put your main program logic inside a function called `main()`. Why? Because it keeps your code organized and prevents everything from running all at once when you import other files.

```python
def main():
    name = input("What's your name? ")
    # This is a call to our custom 'hello' function
    hello(name)

def hello(to):
    print(f"hello, {to}")

# This line starts the program by calling the main function
main()
```

First, we **define** a function `main()`. Inside it, we ask the user for their name, and then we **call** our second custom function, `hello()`, and pass it the `name` variable.

Next, we **define** `hello()`. Notice it has a **parameter**, `to`, inside the parentheses. This is a placeholder for a value that the function will receive. When `main()` calls `hello(name)`, it passes the value of the `name` variable into `hello()`, where it gets assigned to the parameter `to`. The function then uses this value to print the greeting.

Finally, the very last line, `main()`, is what actually starts the program. It calls the `main` function, and that function then handles everything else. It's a great way to structure your code for clarity and reusability.

When the code calls `hello(name)` from inside the `main` function, the value stored in the `name` variable is passed to the `hello` function. The `hello` function then receives this value and assigns it to its own internal variable, `to`. This allows the function to use that value to complete its task, which is to print "hello, " followed by the person's name.

---

## **Returning Values**

Functions can send data back to the code that called them using the `return` keyword. This is incredibly powerful because it allows you to get a result from a function and store it in a variable.


```python
def main():
    x = int(input("What's x? "))
    # Call the square function and print the value it returns
    print("x squared is", square(x))

# This function takes a number 'n' as a parameter and returns its square
def square(n):
    return n * n

main()
```

 The `square` function takes a parameter `n`. Inside the function, it calculates `n * n`. The `return` keyword then takes that calculated value and sends it back out of the function.

A step by step breakdown of this would be

1. The program starts by calling `main()`.
    
2. Inside `main()`, the user is prompted to enter a number, which is stored in the variable `x`. Let's say the user enters `5`.
    
3. The next line is `print("x squared is", square(x))`. Before `print` can do its job, it needs to get a value from the `square(x)` part.
    
4. Python **calls** the `square` function, passing the value of `x` (which is `5`) as the argument for the parameter `n`.
    
5. Inside `square`, `n * n` is calculated (`5 * 5 = 25`).
    
6. The `return` keyword sends the value `25` back to where the function was called.
    
7. Now, the original line effectively becomes `print("x squared is", 25)`. The `square(x)` part has been replaced by the value it returned.
    
8. The program then prints the final output: "x squared is 25".
    

By using `return`, we can keep our code clean and modular. The `square` function does one thing—calculate a square—and then gives the result back to `main`, which handles the printing. This separation of concerns is a core principle of good programming.

---

## **Summing Up** 

In Week 1, 
- you've learned the absolute essentials of Python: using functions like `print()` and `input()`, storing data in variables, understanding data types (`str`, `int`, `float`), and organizing your code by defining your own functions with `def` and `return`. You now have the foundational tools to start building more complex programs. 
<p align="center">
  <img src="pictures/thumbs-up.gif" alt="animated" />
</p>
