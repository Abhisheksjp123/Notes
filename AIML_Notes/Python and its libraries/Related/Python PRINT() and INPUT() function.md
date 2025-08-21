# Print function
The `print()` function is used to display output to the console.

**Definition:** It can take zero or more objects as input and will display them as text. By default, it separates multiple items with a space and ends with a newline.

**Examples:**

- **Printing multiple items with a custom separator (`sep`)** You can change the default space separator to any other character.
```
name = "Alice"
age = 25
print(name, age, sep=" | ")
# Output: Alice | 25
```

- **Controlling the end of the line (`end`)** You can prevent `print()` from automatically moving to the next line.
```
print("Hello", end="")
print("World")
# Output: HelloWorld
```

- **Unpacking lists (`*`)** The `*` operator unpacks a list, feeding its elements to `print` as separate arguments.
```
items = ["apple", "banana", "cherry"]
print(*items, sep=", ")
# Output: apple, banana, cherry
```

- **F-Strings for easy formatting** Prefix a string with `f` to embed variables directly. You can also format them, for example, `:.2f` rounds a number to two decimal places.
```
name = "Emma"
price = 19.99
print(f"{name} paid ${price:.1f}")
# Output: Emma paid $20.0
```

- **Escape characters for special formatting (`\`)** Use `\` to include special characters like newlines (`\n`), tabs (`\t`), or literal quotes (`\"`).
```
print("First line\n\tSecond line (indented)")
print("She said: \"That's great!\"")
# Output:
# First line
#   Second line (indented)
# She said: "That's great!"
```

# Input function
To get input from a user in Python, you use the built-in `input()` function.

**Definition:** The `input()` function pauses the program's execution and waits for the user to type something and press Enter. You can also provide an optional string prompt to display to the user.

**Key Point:** The `input()` function **always returns the user's input as a string (`str`)**, even if they type in numbers.

**Examples:**

- **Getting and converting input** To use the input for mathematical operations, you must convert it from a string to a number using `int()` or `float()`. This is called **type casting**.
```
# The prompt "What is your age? " is displayed to the user
age_str = input("What is your age? ")

# Convert the string to an integer
age_num = int(age_str)

print(f"Next year, you will be {age_num + 1} years old.")
```

## **Getting hidden input for passwords** 
For sensitive information like passwords, use the `getpass` module. It prompts the user for input without showing the characters on the screen.

```
import getpass

password = getpass.getpass("Enter your password: ")
# When you run this, your typing will be hidden

print("Password received.")
```

