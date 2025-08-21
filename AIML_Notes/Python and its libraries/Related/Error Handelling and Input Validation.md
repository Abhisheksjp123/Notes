## Input Validation
Validation is the process of checking if user input is of the correct format or data type before your program tries to use it. This is crucial for preventing errors and crashes.

### Using Built-in String Methods

For simple cases, strings have several built-in methods that return `True` or `False`. These are great for quick checks.

- **.isdigit()**: Returns `True` if all characters in the string are digits (0-9).

Python

```
num_str = "12345"
print(num_str.isdigit()) # Output: True

not_num_str = "123a"
print(not_num_str.isdigit()) # Output: False
```

- **.isalpha()**: Checks for only letters.

- **.isalnum()**: Checks for letters and numbers.

- **.isspace()**: Checks for only whitespace characters.