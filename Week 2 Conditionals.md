
## **Introduction to Conditionals**

In programming, **conditionals** are statements that allow your code to make decisions and execute different blocks of code based on whether certain conditions are `True` or `False`. Think of it as asking a question and then performing an action based on the answer. 🤔

---

## **Comparison Operators**

To ask questions, Python uses **comparison operators**. These operators compare two values and evaluate to either `True` or `False`.

|Operator|Meaning|Example|Result|
|---|---|---|---|
|`==`|Equal to|`x == y`|`True`|
|`!=`|Not equal to|`x != y`|`False`|
|`<`|Less than|`x < y`|`False`|
|`>`|Greater than|`x > y`|`True`|
|`<=`|Less than or equal to|`x <= y`|`True`|
|`>=`|Greater than or equal to|`x >= y`|`True`|

_(Assuming `x = 10` and `y = 10` for the examples in the table, except where noted)_

Let's see them in action with a simple program that compares two numbers.

Python

```
# Get input from the user and convert to integers
x = int(input("What's x? "))
y = int(input("What's y? "))

# Compare x and y
if x < y:
    print("x is less than y")
if x > y:
    print("x is greater than y")
if x == y:
    print("x is equal to y")
```

This code works, but it's inefficient because the computer checks all three `if` statements, even after it finds one that is true.

---

## **`if`, `elif`, and `else`**

A more efficient way to structure conditional logic is by using an `if-elif-else` block. This structure ensures that only **one** block of code is executed.

- `if`: The first condition to be checked.
    
- `elif`: (short for "else if") Checked only if the preceding `if` (or `elif`) was `False`. You can have multiple `elif` statements.
    
- `else`: The "catch-all" block. It runs only if **all** preceding `if` and `elif` conditions were `False`.
    

Python

```
# A more efficient way to compare x and y
x = int(input("What's x? "))
y = int(input("What's y? "))

if x < y:
    print("x is less than y")
elif x > y:
    print("x is greater than y")
else:
    print("x is equal to y")
```

In this version, if `x < y` is `True`, Python prints the corresponding message and skips the `elif` and `else` checks entirely. Much better! ✅

---

## **Logical Operators: `or` and `and`**

Sometimes you need to check multiple conditions at once. This is where logical operators come in handy.

### The `or` Operator

The `or` operator evaluates to `True` if **at least one** of its conditions is true.

Python

```
# Example of 'or'
x = int(input("What's x? "))
y = int(input("What's y? "))

if x < y or x > y:
    print("x is not equal to y")
else:
    print("x is equal to y")
```

This is equivalent to using the not equal operator: `if x != y:`.

### The `and` Operator

The `and` operator evaluates to `True` only if **all** of its conditions are true.

Python

```
# Example of 'and' for grading
score = int(input("Score: "))

if score >= 90 and score <= 100:
    print("Grade: A")
elif score >= 80 and score < 90:
    print("Grade: B")
# ... and so on
```

This can be simplified in Python using chaining:

Python

```
# A more Pythonic way to write the same logic
score = int(input("Score: "))

if 90 <= score <= 100:
    print("Grade: A")
elif 80 <= score < 90:
    print("Grade: B")
elif 70 <= score < 80:
    print("Grade: C")
elif 60 <= score < 70:
    print("Grade: D")
else:
    print("Grade: F")
```

---

## **The Modulo Operator (`%`)**

The **modulo operator (`%`)** is incredibly useful in conditional logic. It gives you the **remainder** of a division operation.

A common use case is determining if a number is even or odd. A number is even if it's perfectly divisible by 2, meaning the remainder is 0.

npmod2==0quadif n is even

npmod2==1quadif n is odd

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

It's good practice to encapsulate logic inside functions. This makes your code reusable and easier to read.

Let's create a function `is_even` that returns `True` if a number is even and `False` otherwise.

Python

```
def main():
    x = int(input("What's x? "))
    if is_even(x):
        print("Even")
    else:
        print("Odd")

def is_even(n):
    # This expression 'n % 2 == 0' will evaluate to either True or False
    return n % 2 == 0

main()
```

Notice how `is_even(n)` is more readable. Instead of an `if/else` block, we can directly return the result of the boolean expression `n % 2 == 0`. This is a common and concise pattern in Python.

---

## **The `match` Statement**

Introduced in Python 3.10, the `match` statement is a powerful tool for pattern matching, similar to a `switch` statement in other languages. It compares a value against several patterns (`case`) and executes the code corresponding to the first successful match.

Python

```
# Example: Getting a student's house at Hogwarts
name = input("What's your name? ")

match name:
    case "Harry" | "Hermione" | "Ron":
        print("Gryffindor")
    case "Draco":
        print("Slytherin")
    # The underscore '_' is a wildcard that matches anything
    case _:
        print("Who?")
```

In this example:

- The `|` acts like an `or`, matching any of the names in the list.
    
- `case _:` is the default case, catching any input that didn't match the patterns above. It's similar to an `else` block.