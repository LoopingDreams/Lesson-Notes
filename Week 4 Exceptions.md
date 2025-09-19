![[/pictures/Komi_san_Python.png]]
---

## **Introduction to Exceptions: Handling the Unexpected**

So far, our programs have been a bit fragile. If a user types in a word where we expect a number, our program doesn't just fail—it crashes violently with a big red error message. This isn't a good user experience.

An **exception** is an error that occurs _while your program is running_. It is about how to anticipate and handle these exceptions gracefully, a practice known as **exception handling**. Instead of our program crashing, we can "catch" the error and decide what to do about it, making our code far more user-friendly. 

---

## **Syntax Errors vs. Exceptions**

It's crucial to understand the difference between a syntax error and an exception.

- A **`SyntaxError`** is a grammatical mistake in your code that Python detects _before_ it even tries to run your program. You've broken the language's rules, like forgetting a colon or a closing parenthesis. The program won't start at all.
    
- An **exception** (also called a runtime error) happens when your code is syntactically perfect, but something goes wrong during execution. A classic example is `ValueError`, which occurs when a function receives an argument of the correct type but an inappropriate value.
    

Python

```Python
# This is a SyntaxError. The program will not run.
print("hello, world"

# This code is syntactically correct, but will raise a ValueError
# if the user types "cat" instead of a number. This is an exception.
x = int(input("What's x? "))
```

---

## **The `try...except` A Safety Net**

To handle exceptions, we use a `try...except` block. It works like this:

- **`try`**: You put the "risky" code that might cause an exception inside the `try` block.
    
- **`except`**: If an exception _does_ occur in the `try` block, Python immediately jumps to the `except` block and runs that code instead of crashing.
    

Think of it as saying, "Python, **try** to do this, but if you run into a problem, don't panic. **Except**, do this instead."

Python

```Python
try:
    x = int(input("What's x? "))
    print(f"x is {x}")
except ValueError:
    print("x is not an integer")
```

**How it works:**

1. Python enters the `try` block and executes `int(input(...))`.
    
2. **Scenario A (No Error):** The user enters `5`. The conversion to an integer succeeds. `print(f"x is {x}")` runs, and Python completely **skips** the `except` block.
    
3. **Scenario B (Error):** The user enters `cat`. `int()` cannot convert "cat" and raises a `ValueError`. Python immediately stops executing the `try` block, jumps down to the `except ValueError:` block, and runs `print("x is not an integer")`. The program continues on without crashing.
    

---

## **Common Types of Exceptions**

- **`ValueError`**: A function receives an argument of the right type, but an invalid value (e.g., `int("cat")`).
    
- **`NameError`**: You try to use a variable that hasn't been defined yet.
    
- **`ZeroDivisionError`**: You attempt to divide a number by zero.
    
- **`TypeError`**: You try to perform an operation on a value of the wrong type, like trying to add a string to an integer (`"hello" + 5`).
    

You can handle different types of exceptions separately.

Python

```Python
try:
    x = int(input("What's x? "))
    y = int(input("What's y? "))
    result = x / y
except ValueError:
    print("Error: Please enter a valid number.")
except ZeroDivisionError:
    print("Error: Cannot divide by zero.")
```

---

## **The `else` and `pass` Statements**

### **The `else` Block**

Sometimes you have code that should _only_ run if the `try` block was successful (i.e., no exceptions were raised). For this, you can add an `else` block.

Python

```Python
try:
    x = int(input("What's x? "))
except ValueError:
    print("x is not an integer")
else:
    # This line will only run if the 'try' block succeeds.
    print(f"x is {x}")
```

This is considered better design because it narrows the scope of the `try` block to only the single line of code that could actually cause the error.

### **The `pass` Statement**

What if you want to catch an error but do nothing about it? The **`pass`** statement is a placeholder that tells Python, "I acknowledge this could happen, but just ignore it and move on."

Python

```Python
# A loop that silently ignores bad input
while True:
    try:
        x = int(input("What's x? "))
        break # Exit the loop if input is good
    except ValueError:
        pass # Ignore the error and let the loop ask again
```

---

## **Refactoring with Functions**

Good programming practice involves organizing your code into functions. Let's create a function that handles getting an integer from the user, making it reusable.

Python

```Python
def main():
    x = get_int("What's x? ")
    print(f"x is {x}")

def get_int(prompt):
    """
    Prompts the user for an integer and handles ValueErrors.
    Returns the integer.
    """
    while True: # Loop forever until we get a valid integer
        try:
            # We return the value directly from the try block
            return int(input(prompt))
        except ValueError:
            # The 'pass' here makes the loop re-prompt the user
            pass

main()
```

This design is clean and modular. The `main` function doesn't need to worry about error handling; it can trust that `get_int` will always give it back a valid integer.

---

## **Raising Your Own Exceptions (`raise`)**

Sometimes, you want to create your own error conditions. You can use the **`raise`** keyword to trigger an exception yourself. This is useful when a value is the correct _type_ but doesn't make sense in the context of your program (a logical error).

Python

```Python
def main():
    x = get_positive_int()
    print(f"x is {x}")

def get_positive_int():
    while True:
        try:
            n = int(input("Positive Integer: "))
            if n > 0:
                return n
            else:
                # We are creating our own error condition here!
                raise ValueError("Number must be positive.")
        except ValueError as e:
            # We can optionally catch the error to print its message.
            print(e)

main()
```

By using `raise`, you can enforce more complex rules than the built-in exceptions cover, leading to more robust and logical programs.