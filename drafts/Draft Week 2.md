
---

## **Introduction to Conditionals**

In programming, we don't want our code to be a straight road that always does the same thing. We want it to be able to react and make decisions. **Conditionals** are the tools that let our programs choose a path. Think of them as a fork in the road for your code. Based on a question (a condition), the program will either go left or right. 

This decision-making process is fundamental to creating any useful software, from a simple game that asks "Did the player find the key?" to a web browser that asks "Did the user click this link?".

---

## **Booleans: The Language of Logic**

Before we can make decisions, we need to understand the language of logic. In Python, this comes down to a special data type called a **boolean** (or `bool`). A boolean can only have one of two possible values:

- `True`
    
- `False`
    

Every conditional statement in Python ultimately boils down to evaluating whether a condition is `True` or `False`.

---

## **Comparison Operators**

To create `True` or `False` conditions, we ask questions using **comparison operators**. These operators compare two values and the entire expression _evaluates to_ a single boolean value.

|Operator|Meaning|Example (`x=10`, `y=5`)|Result|
|---|---|---|---|
|`==`|Equal to|`x == 10`|`True`|
|`!=`|Not equal to|`x != y`|`True`|
|`<`|Less than|`y < x`|`True`|
|`>`|Greater than|`x > y`|`True`|
|`<=`|Less than or equal to|`x <= 10`|`True`|
|`>=`|Greater than or equal to|`y >= x`|`False`|

Let's see this in a program that feels a bit clunky.

Python

```Python
# Get input from the user and convert to integers
x = int(input("What's x? "))
y = int(input("What's y? "))

# This code works, but it's inefficient.
# The computer will check every single 'if' statement,
# even if the first one was already true.
if x < y:
    print("x is less than y")
if x > y:
    print("x is greater than y")
if x == y:
    print("x is equal to y")
```

This is inefficient because `x`, `y`, and `z` are mutually exclusive conditions. If `x` is less than `y`, it's impossible for it to also be greater than `y`. The computer shouldn't have to waste time checking.

---

## **`if`, `elif`, and `else`: Efficient Decision Making**

To fix the inefficiency, we can chain our conditions together in an `if-elif-else` block. This structure tells Python: "Check these conditions in order, and as soon as you find one that's true, run its code and **skip the rest**."

- `if`: The starting point. "If this is true, do this and we're done."
    
- `elif`: (else if) "If the previous condition was false, try this one."
    
- `else`: The safety net. "If none of the above were true, then do this."
    

Python

```Python
# A more efficient and logical way to compare x and y
x = int(input("What's x? "))
y = int(input("What's y? "))

if x < y:
    # This block runs only if x is less than y.
    print("x is less than y")
elif x > y:
    # This block runs only if the first 'if' was False AND x > y.
    print("x is greater than y")
else:
    # This block is the default; it runs only if both the 'if' and 'elif' were False.
    # In this logic, it means x must be equal to y.
    print("x is equal to y")
```

---

## **Logical Operators: `and`, `or`, and `not`**

What if one question isn't enough? Logical operators let us combine multiple boolean conditions.

### The `and` Operator

The `and` operator evaluates to `True` **only if all** conditions connected by it are `True`. Think of it as a strict checklist—you need every item.

Python

```
# A more Pythonic way to check if a score is within a range
score = int(input("Score: "))

if 90 <= score <= 100: # This is a clean way of writing 'score >= 90 and score <= 100'
    print("Grade: A")
elif 80 <= score < 90:
    print("Grade: B")
# ...and so on
else:
    print("Grade: F")
```

### The `or` Operator

The `or` operator evaluates to `True` if **at least one** of its conditions is `True`. It's less strict—only one thing needs to be right.

Python

```
# Check if a student is in Gryffindor
name = input("What's your name? ")

if name == "Harry" or name == "Hermione" or name == "Ron":
    print("Gryffindor")
else:
    print("Not a main Gryffindor character.")
```

### The `not` Operator

The `not` operator is simple: it **inverts** a boolean value. `not True` becomes `False`, and `not False` becomes `True`.

Python

```
is_raining = False

if not is_raining:
    print("It's a sunny day!") # This will print
```

---

## **The Modulo Operator (`%`)**

The **modulo operator (`%`)** doesn't do regular division; instead, it gives you the **remainder** of a division. It's surprisingly useful for checking for divisibility.

A classic example is determining if a number is even or odd. If a number divided by 2 has a remainder of 0, it's even. Otherwise, it's odd.

n(mod2)==0if n is even

n(mod2)==1if n is odd

Python

```
# Get a number from the user
x = int(input("What's x? "))

# Check if the remainder when divided by 2 is 0
if x % 2 == 0:
    print("Even")
else:
    print("Odd")
```

---

## **Creating Functions with Conditionals**

Good programmers avoid repeating themselves. If you have a piece of conditional logic you'll use often, put it in a function.

Let's create an `is_even` function. Here's a perfectly valid, but slightly verbose, way to write it:

Python

```
def is_even_verbose(n):
    if n % 2 == 0:
        return True
    else:
        return False
```

However, we can be more concise. The expression `n % 2 == 0` already evaluates to `True` or `False`. So, why not just return that value directly? This is a common and elegant pattern in Python.

Python

```
def main():
    x = int(input("What's x? "))
    if is_even(x):
        print("Even")
    else:
        print("Odd")

# A more "Pythonic" version of the function
def is_even(n):
    # Just return the boolean result of the comparison directly
    return n % 2 == 0

main()
```

---

## **The `match` Statement**

Introduced in Python 3.10, the `match` statement (also called structural pattern matching) is a clean alternative to a long chain of `if-elif-elif...` statements, especially when you are comparing one value against many possible literal values.

Python

```
# Example: Getting a student's house at Hogwarts
name = input("What's your name? ").title()

match name:
    # The pipe '|' acts like an 'or' for multiple patterns
    case "Harry" | "Hermione" | "Ron":
        print("Gryffindor")
    case "Draco":
        print("Slytherin")
    # The underscore '_' is a wildcard that matches anything. It's the default case.
    case _:
        print("Who?")
```

---

## **The Ternary Operator (A Concise `if-else`)**

For simple `if-else` assignments, Python provides a one-line syntax called the **ternary operator**. It's great for readability when the logic is simple.

**Syntax:** `value_if_true if condition else value_if_false`

Python

```
def main():
    x = int(input("What's x? "))
    # The ternary operator reads like an English sentence.
    result = "Even" if is_even(x) else "Odd"
    print(result)

def is_even(n):
    return n % 2 == 0

main()
```