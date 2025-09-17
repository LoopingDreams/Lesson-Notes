
---

## **Introduction to Loops: Don't Repeat Yourself!**

In programming, a core principle is **DRY**—**D**on't **R**epeat **Y**ourself. If you find yourself writing the same line of code over and over, there's almost certainly a better, more efficient way. That better way is using **loops**.

Loops allow us to execute a block of code multiple times, saving us from tedious repetition and making our programs more powerful and dynamic. 🔄

---

## **`while` Loops: Repeating Indefinitely**

A **`while` loop** is the simplest form of a loop. It will repeat a block of code **as long as a certain condition remains `True`**.

Think of it as telling the computer: "While this is true, keep doing this."

Python

```Python
# A simple counter using a while loop
i = 0
while i < 3:
    print("meow")
    i = i + 1 # Increment the counter
```

**Anatomy of the `while` Loop:**

1. **Initialization:** We start with a "counter" variable, `i`, set to `0`.
    
2. **Condition:** The loop checks `while i < 3:`. The first time, `0 < 3` is `True`, so the loop runs.
    
3. **Body:** The indented code inside the loop (`print("meow")` and `i = i + 1`) is executed.
    
4. **Update:** We increment `i`. It becomes `1`. The loop goes back to step 2 and checks the condition again (`1 < 3` is `True`... then `2 < 3` is `True`).
    
5. **Termination:** Once `i` becomes `3`, the condition `3 < 3` is `False`, and the loop stops.
    

**⚠️ Beware of Infinite Loops!** If you forget to update the variable in your condition (like forgetting `i = i + 1`), the condition will _never_ become false, and your program will be stuck forever!
Use `Ctrl+C` to break out of the loop in VS Code

---

## **`for` Loops: Iterating Over a Sequence**

A **`for` loop** is designed for **definite iteration**—that is, looping a specific number of times. It is perfect for iterating over a **sequence** of items, like a list.

Think of it as telling the computer: "For each item in this collection, do this."

### **Lists (`list`)**

Before we master `for` loops, we need a data structure to loop over. A **list** is an ordered collection of items, stored in a single variable. You create a list using square brackets `[]`.

Python

```Python
Gacha_Games = ["Zenless Zone Zero", "Wuthering Waves", "Genshin Impact"]

# Accessing an item by its index (position)
print(Gacha_Games[0]) # Output: "Zenless Zone Zero"
```

### **Using `for` with a List**

The `for` loop elegantly handles the initialization, condition check, and updating for you.

Python

```Python
Characters = ["Iuno", "Augusta", "Galbrena"]

# The variable 'student' will take on the value of each item in the list, one by one.
for Characters in Characters:
    print(Characters)
```

This is far cleaner and less error-prone than a `while` loop for this task.

### **The `range()` Function**

What if you just want to do something a specific number of times, without a list? The `range()` function generates a sequence of numbers for you.

- `range(3)` produces the sequence `0, 1, 2`.
    
- `range(5)` produces `0, 1, 2, 3, 4`.
    

Python

```Python
# A more "Pythonic" way to meow three times
for _ in range(3):
    print("meow")
```

> **Pro Tip:** When you need a loop to run a certain number of times but you don't care about the counter variable itself, it's a common convention to use an underscore (`_`) as the variable name.

---

## **Dictionaries (`dict`): Key-Value Pairs**

What if a simple list isn't enough? A **dictionary** or `dict` stores data not in an ordered sequence, but as **key-value pairs**. It's like a real-world dictionary where you look up a word (the **key**) to find its definition (the **value**). You create dictionaries with curly braces `{}`.

Python

```Python
# Using a dictionary to store characters and their games
characters = {
    "Iuno": "WutheringWaves",
    "Zani": "WutheringWaves",
    "Cartethiya": "WutheringWaves",
    "Seed": "Zenless",
    "Evelynn": "Zenless"
}

# Access the value using its key
print(characters["Iuno"]) #Output WutheringWaves
```

### **Looping Over a Dictionary**

When you loop over a dictionary, you are iterating over its **keys**.

Python

```python
# This loop prints each character's name (the key)
for character in characters:
    # We use the key to look up the corresponding value
    print(character, characters[character], sep=", ")
```

---

## **Nested Loops: Loops Inside Loops**

You can put a loop inside another loop. This is called a **nested loop**, and it's perfect for problems that involve grids, matrices, or combinations of items.

Imagine you want to print a square of bricks (`#`).

Python

```Python
def main():
    print_square(3)

def print_square(size):
    # The outer loop handles the rows (height)
    for i in range(size):
        # The inner loop handles the columns (width)
        for j in range(size):
            # The 'end=""' prevents print() from starting a new line
            print("#", end="")
        # After the inner loop finishes, print a newline to start the next row
        print()

main()
```

**How it works:**

1. The outer loop starts (`i = 0`).
    
2. The inner loop runs to completion, printing `###`.
    
3. `print()` creates a new line.
    
4. The outer loop runs again (`i = 1`), and the inner loop runs to completion again, printing another row of `###`.
    
5. This repeats until the square is complete.
    

---

## **Keywords for Loop Control**

Sometimes you need to alter a loop's behavior mid-run.

- `break`: Immediately **terminates** the loop it's in.
    
- `continue`: Skips the rest of the current iteration and jumps to the **next** one.
    

Python

```Python
# An example of getting positive input from a user
while True: # This creates an intentional infinite loop
    n = int(input("What's n? "))
    if n > 0:
        break # If n is positive, exit the loop

# This code will only be reached after the loop is broken
for i in range(n):
    print("meow")
```

This "loop forever and break" pattern is a very common and useful way to handle user input validation.