
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

#### Functions used with for loops
While you can loop over any sequence directly, these functions give you more power and flexibility.
1. range():
The `range()` function generates a sequence of numbers, which is perfect for when you need to run a loop a specific number of times. It's very memory-efficient because it doesn't create a full list of numbers.
- `range(stop)`: Generates numbers from `0` up to (but not including) `stop`.
- `range(start, stop)`: Generates numbers from `start` to `stop - 1`.
- `range(start, stop, step)`: Generates numbers from `start` to `stop - 1`, incrementing by `step`.

2. `enumerate()`
The `enumerate()` function is used when you need both the **index** and the **item** as you loop through a sequence. It adds a counter to an iterable.
```
fruits = ["apple", "banana", "cherry"]

# The enumerate function provides both the index and the fruit
for index, fruit in enumerate(fruits):
  print(f"Item {index} is {fruit}")
```
**Output:**
```
Item 0 is apple
Item 1 is banana
Item 2 is cherry
```

3. zip()
The `zip()` function is used to loop over two or more sequences at the same time. It pairs up the corresponding elements from each sequence into tuples. The loop stops when the shortest sequence runs out of items.

Think of it like a zipper on a jacket, joining the two sides together.

```
students = ["Alice", "Bob", "Charlie"]
scores = [85, 92, 78]

for student, score in zip(students, scores):
  print(f"{student}'s score is {score}")
```

**Output:**

```
Alice's score is 85
Bob's score is 92
Charlie's score is 78
```
### Website to visualize python code in iteration step by step
[link](https://pythontutor.com/render.html#mode=display)



### Break and continue and pass statements
The `break` and `continue` statements are loop control statements that change a loop's execution from its normal sequence. They can be used in both `for` and `while` loops.


| Statement  | `break`                    | `continue`                       | `pass`                                |
| :--------- | :------------------------- | :------------------------------- | :------------------------------------ |
| **Action** | **Exits** the entire loop. | **Skips** the current iteration. | **Does nothing**; it's a placeholder. |
| **Effect** | The loop stops completely. | The loop moves to the next item. | Execution continues to the next line. |