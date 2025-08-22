## Modules in Python

A **module** is a file containing Python code—usually functions, classes, and variables—that you can reuse in other programs. Think of it as a **code library** or a toolbox filled with pre-written tools for you to use.

Using modules helps keep your code organized and allows you to use powerful functions without having to write them from scratch. Common built-in modules include `math`, `random`, `os`, and `time`.

#### 1. Importing a Module

There are a few common ways to import a module.

- **Standard Import:** This imports the entire module. You must use the module's name as a prefix to access its functions. This is the most common and recommended way because it avoids naming conflicts.

```
import math

# You must use the 'math.' prefix
print(math.sqrt(16)) # Output: 4.0
print(math.pi)       # Output: 3.14159...
```

- **Importing with an Alias (`as`):** You can give a module a shorter, more convenient name. This is very common with libraries like NumPy or Pandas.

```
import math as m

# Now use the alias 'm.' as the prefix
print(m.sqrt(25)) # Output: 5.0
```

- **Importing Specific Functions (`from`):** If you only need one or two functions from a module, you can import them directly. This allows you to use them without any prefix.

```
from math import sqrt, pi

# No prefix is needed now
print(sqrt(9))  # Output: 3.0
print(pi)       # Output: 3.14159...
```

#### 2. Accessing Module Contents

Once imported, you use the dot (`.`) operator to access the functions, variables, or classes inside the module.

```
import random

# Access the randint function from the random module
random_number = random.randint(1, 10)
print(f"A random number between 1 and 10 is {random_number}")
```