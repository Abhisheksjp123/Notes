## Variables

Variables are names used to store data values. Think of them as labeled containers. In Python, a variable is created the moment you first assign a value to it.

### Naming Rules
A variable name must follow specific rules:
- It must start with a **letter** (`a-z`, `A-Z`) or an **underscore** (`_`).
- It can only contain **letters**, **numbers** (`0-9`), and **underscores**.
- It **cannot** start with a number.
- It **cannot** contain spaces or special characters like hyphens (`-`).
- Variable names are **case-sensitive** (`age`, `Age`, and `AGE` are three different variables).

 **Valid:** `user_name`, `value_1`, `_private_var` ❌ **Invalid:** `2_users`, `user-name`, `user name`

### Assigning Values

You can assign values to variables in several ways.

- **Single Assignment**:
```
name = "Alice"
age = 30
```

- **Multiple Assignment (in one line)**: You can assign different values to different variables simultaneously.
```
a, b, c = 10, "Hello", True
print(a) # Output: 10
print(b) # Output: "Hello"
```

- **Assigning the Same Value to Multiple Variables**:
```
x = y = z = "Ready"
print(x, y, z) # Output: Ready Ready Ready
```


## Keywords

Keywords are the **reserved words** that form the core vocabulary of the Python language. They have special, predefined meanings and cannot be used as names for your variables, functions, or anything else.

### Key Characteristics
- They are the fundamental building blocks for logic, like `if`, `for`, `while`
- They are **case-sensitive** and are always lowercase, except for three: `True`, `False`, and `None`.
- You will get a `SyntaxError` if you try to use a keyword as a variable name.

```
# This will cause an error
class = "My Class" # SyntaxError: invalid syntax
```

### How to See All Keywords

Python provides a built-in `keyword` module to see the current list of all keywords for your version.

```
import keyword

# Get the total count
num_keywords = len(keyword.kwlist)
print(f"Number of keywords: {num_keywords}")

# Print the full list
print(keyword.kwlist)
```

**Output:**
```
Number of keywords: 35
['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 
'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 
'except', 'finally', 'for', 'from', 'global', 'if', 'import', 
'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 
'return', 'try', 'while', 'with', 'yield']
```


## Identifiers

An **identifier** is the name given to an entity like a variable, function, class, or module. It's how you refer to that object in your code.

### General Naming Rules
- An identifier must start with a letter (`a-z`, `A-Z`) or an underscore (`_`).
- The first character can be followed by any number of letters, digits (`0-9`), or underscores.
- Reserved **keywords** (like `if`, `for`, `class`) cannot be used as identifiers.
- Identifiers are **case-sensitive** (`age` and `Age` are different).
### Naming Conventions Using Underscores

While the rules above are enforced by Python, programmers follow certain conventions with underscores to signal the intended use of an identifier.
- **`_single_leading_underscore`**: This is a convention indicating that a variable or method is for "internal use" only. It's a hint to other programmers, but nothing is technically restricted.

- **`__double_leading_underscore`**: This triggers **name mangling**. When used inside a class, Python automatically changes the name to avoid conflicts in subclasses. This is how Python creates a "pseudo-private" variable.
```
class MyClass:
  def __init__(self):
    self.__private_var = 42 # This is a name-mangled variable

obj = MyClass()
# print(obj.__private_var)  # This will cause an AttributeError

# The name was automatically changed to _ClassName__private_var
print(obj._MyClass__private_var) # Output: 42
```
- **`__dunder__`**: Identifiers with a double underscore at both the beginning and end (e.g., `__init__`, `__str__`) are called "dunder" (double underscore) or "magic" methods. These are special names that Python reserves for specific behaviors.

## Literals
A **literal** is the raw data or fixed value written directly in your code. For example, in the assignment `name = "Alice"`, the raw data `"Alice"` is a string literal.

### String Literals
These are sequences of characters enclosed in quotes.
- **Single or Double Quotes**: `'hello'` or `"hello"`.
- **Multi-line Strings**: Use triple quotes (`"""..."""` or `'''...'''`).
- **Raw Strings (`r"..."`)**: Prefixed with an `r`, these strings treat backslashes as literal characters, not as escape characters. This is very useful for file paths.
```
# The \n would normally be a newline, but 'r' prevents that
path = r"C:\new\folder"
print(path) # Output: C:\new\folder
```

- **Bytes Literals (`b"..."`)**: 
Prefixed with a `b`, these create a `bytes` object, which is a sequence of bytes, not a text string.
```
data = b"hello"
print(type(data)) # Output: <class 'bytes'>
```

### Numeric Literals
These are literals representing numbers.

- **Integer**: Can be written in different bases.
- **Decimal**: `255`
- **Binary**: `0b11111111`
- **Octal**: `0o377`
- **Hexadecimal**: `0xFF` (All of these equal 255)
- **Float**: Can be written with a decimal or in scientific notation.
	- `3.14`
	- `1e6` (which means 1times106, or 1,000,000)
- **Complex**: Written with a `j` to denote the imaginary part.
	- `3 + 4j`
### Boolean Literals
There are only two Boolean literals, representing truth values.
- `True`
- `False`

### The Special Literal
Python has one special literal used to represent the absence of a value.
- `None`
### Container Literals
You can also define containers and their contents literally.
- **List**: `[10, "apple", True]`
- **Tuple**: `(10, "apple", True)`
- **Dictionary**: `{"name": "Bob", "age": 40}`
- **Set**: `{10, "apple", True}`

You can also use multiplication to create a list with repeated elements.
```
zeros = [0] * 5
print(zeros) # Output: [0, 0, 0, 0, 0]
```