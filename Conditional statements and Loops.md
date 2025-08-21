
# Conditional Statements (if/elif/else)

Conditional statements allow your program to make decisions and execute different blocks of code based on whether a condition is `True` or `False`.
The structure relies on three keywords: **if**, **elif**, and **else**.
### The `if` Statement
This is the starting point. The code block indented under `if` will only run if the condition is **True**.
```
age = 20
if age >= 18:
  print("You are eligible to vote.")
```
### The `else` Statement

This is the "catch-all" block. It's optional and runs only if the preceding `if` (and all `elif`) conditions are **False**.
```
temperature = 15
if temperature > 25:
  print("It's a hot day.")
else:
  print("It's a cool or cold day.")
```

### The `elif` Statement

Short for "else if," this allows you to check multiple conditions in sequence. Python checks them one by one and runs the code for the **first** condition that is **True**.

# Loops in Python - While and For
Python has two primary types of loops: the **`for` loop** and the **`while` loop**.

Each is designed for a different situation, and the key difference is whether you know the number of iterations in advance.
### The `while` Loop: The Condition Watcher
A `while` loop is used for **indefinite iteration**. This means you use it when you want a block of code to repeat as long as a certain condition is **True**.
```
# Loop as long as the count is less than 3
count = 0
while count < 3:
  print(f"Looping... count is {count}")
  count += 1 # It is crucial to change the condition inside the loop to avoid an infinite loop

print("Loop finished.")
```
### The `for` Loop: The List Checker
A `for` loop is used for **definite iteration**. This means you use it when you have a sequence of items (like a list, a string, or a range of numbers) and you want to do something for each item in that sequence.
```
# Loop through each item in the list
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
  print(fruit)
```
