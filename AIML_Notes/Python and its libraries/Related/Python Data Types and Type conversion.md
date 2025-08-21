## Basic Data Types

These are the fundamental building blocks for data in Python.

- **int**: For whole numbers, like `100`, `-5`.
    
- **float**: For numbers with a decimal point, like `3.14`, `-0.5`.
    
- **bool**: For truth values, which can only be `True` or `False`.
    
- **str (String)**: A sequence of characters used for text.
    
    - **Indexing**: Access characters by position, starting from 0. `"Python"[2]` gives `'t'`.
        
    - **Multi-line**: Create with triple quotes (`"""..."""`) or new-line characters (`\n`).
        
    - **Methods**: Strings have useful built-in functions, like `.upper()` and `.lower()`.
        

You can always check a variable's type using the `type()` function. For example, `type(3.14)` returns `<class 'float'>`.

## Container Data Types

These types are used to group and organize other data.

### 1. Lists `[]`

An **ordered** and **mutable** (changeable) collection of items.

- **Creation**: `my_list = []` or `my_list = [1, "hello", 3.0]`
    
- **Combining**: Use `+` to combine two lists into a new one. `[1, 2] + [3, 4]` results in `[1, 2, 3, 4]`.
    
- **Adding Elements**:
    
    - `.append(item)` adds a single item to the end.
        
    - `.extend(list)` adds all items from another list to the end.
        

### 2. Tuples `()`

An **ordered** and **immutable** (unchangeable) collection of items. Once created, you can't add, remove, or change elements.

- **Creation**: `my_tuple = (1, "hello", 3.0)`
    
- **Single-element tuple**: You must use a trailing comma: `single = (5,)`. Without the comma, `(5)` is just the integer `5`.
    

### 3. Dictionaries `{}`

A collection of **key-value pairs**. It's unordered in older Python versions but keeps insertion order in modern Python (3.7+).

- **Creation**: `my_dict = {}` or `my_dict = {"name": "Alice", "age": 25}`
    
- **Accessing Values**:
    
    - `my_dict["name"]` returns `"Alice"`. Accessing a key that doesn't exist will raise a `KeyError`.
        
    - `my_dict.get("city")` is the safe way to access a key. It returns `None` (or a specified default) if the key is not found, preventing a crash.
        
- **Getting Keys**: The `.keys()` method returns all the keys in the dictionary.
    

### 4. Sets `set()`

An **unordered** collection of **unique** elements. Duplicates are automatically removed.

- **Creation**:
    
    - `my_set = {1, 2, 3, 3}` results in `{1, 2, 3}`.
        
    - To create an **empty set**, you **must** use `empty_set = set()`. Using `{}` creates an empty dictionary.
        
- **Adding Elements**: Use the `.add()` method: `my_set.add(4)`.
    
- **Set Operations**: Sets are great for mathematical operations.
    
    - **Intersection (`&`)**: Finds elements common to both sets.
        
    - **Union (`|`)**: Combines all elements from both sets.

# Type conversion
Type conversion, or casting, is when you deliberately change a value from one data type to another. This is a common and essential task in programming.

You do this by using a function that shares the same name as the data type you want to convert to.

## Common Conversion Functions

- **`str(value)`**: Converts a value into a **string**. This is useful when you want to combine a number with text.

```
age = 30
# print("Age: " + age)  # This would cause a TypeError
print("Age: " + str(age)) # Correct way
# Output: Age: 30
```

- **`int(value)`**: Converts a value into an **integer**. It will cut off (truncate) any decimal part from a float or convert a numeric string to a whole number.

```
num_str = "101"
num_int = int(num_str) # Converts string to integer

pi = 3.14
int_pi = int(pi) # Converts float to integer

print(num_int)      # Output: 101
print(int_pi)       # Output: 3
```

- **`float(value)`**: Converts a value into a **floating-point number** (a number with a decimal).

```
num_int = 7
num_str = "12.5"

print(float(num_int)) # Output: 7.0
print(float(num_str)) # Output: 12.5
```