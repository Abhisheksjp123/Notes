In Python specifically string are Sequence of UNICODE characters 
Q. Why UNICODE and not ASCII?
Ans. [[UNICODE vs ASCII]]

# 1. Creating string
You can create strings in Python by enclosing text in quotes or by converting other data types.
- Using Single or Double Quotes
The most common way to create a string is by enclosing text in either single quotes (`'`) or double quotes (`"`). There's no functional difference between them, but having both allows you to easily include one type of quote within a string.

```
# Using single quotes
string_1 = 'Hello, World!'

# Using double quotes
string_2 = "Python programming"

# Using single quotes to easily include double quotes
quote = 'She said, "This is great!"'
```
- Multi-line Strings
For strings that span multiple lines, you can use triple single quotes (`'''`) or triple double quotes (`"""`). These are often used for writing docstrings or storing large blocks of text.

```
multi_line_string = """This is a string
that spans across
multiple lines."""

print(multi_line_string)
```

**Output:**

```
This is a string
that spans across
multiple lines.
```


# 2. Accessing strings
Since strings are ordered sequences of characters, you can access their contents by position. You can access individual characters or parts of a string using indexing and slicing.
## Concept of Indexing(Accessing a Single Character)
Indexing lets you retrieve a single character from a specific position. Python uses **zero-based indexing**, meaning the first character is at index `0`.

You can also use **negative indexing** to access characters from the end of the string, where `-1` is the last character.
```
 P  y  t  h  o  n
 0  1  2  3  4  5  (Positive Index)
-6 -5 -4 -3 -2 -1  (Negative Index)
```
```
my_string = "Python"

# Using positive indexing
print(f"First character: {my_string[0]}")  # Output: First character: P
print(f"Third character: {my_string[2]}")  # Output: Third character: t

# Using negative indexing
print(f"Last character: {my_string[-1]}") # Output: Last character: n
```

## Slicing a string - Accessing a Substring
Slicing is used to get a substring (a portion or "slice") of the string. The syntax is `string[start:stop:step]`.
- **`start`**: The index where the slice begins (inclusive). Defaults to `0`.
- **`stop`**: The index where the slice ends (**exclusive**). Defaults to the end of the string.
- **`step`**: The interval between characters. Defaults to `1`.
```
my_string = "Programming"

# Get a slice from index 2 up to (but not including) index 7
# P r o g r a m m i n g
# 0 1 2 3 4 5 6 7 8 9 10
print(my_string[2:7]) # Output: ogram

# Slice from the beginning to index 4
print(my_string[:5]) # Output: Progr

# Slice from index 3 to the end
print(my_string[3:]) # Output: gramming

# Get every second character
print(my_string[::2]) # Output: Pormig
```
==IMP==
```
# A common trick to reverse a string
print(my_string[::-1])
```

# 3. Adding char to strings aka edditing or deleting strings
You can't directly edit, add, or delete characters from an existing string in Python because **strings are immutable**.

Attempting to change a character in a string will result in a `TypeError`.
```
my_string = "hello"
# Let's try to change the 'h' to 'H'
my_string[0] = 'H' 
# This will raise a TypeError: 'str' object does not support item assignment
```
to change the characters of a string, the more powerful tool for this is the `.replace()` method, which returns a new string with all occurrences of a substring replaced.

# 4. Operations on strings
- ==Arithmetic operation==
You can use two arithmetic-style operators on strings: `+` for concatenation and `*` for repetition.
	- **Concatenation (`+`):** Joins two or more strings together to create a new one.
```
first_name = "John"
last_name = "Doe"
full_name = first_name + " " + last_name
print(full_name) # Output: John Doe
```
	- **Repetition (`*`):** Creates a new string by repeating the original string a given number of times.
```
line = "-" * 10
print(line) # Output: ----------
```

- ==Realtional operations==
You can compare strings using relational operators (`==`, `!=`, `<`, `>`, `<=`, `>=`). The comparison is done **lexicographically** (like in a dictionary), based on the characters' Unicode values.

A key point is that uppercase letters come before lowercase letters (e.g., `'Z'` is less than `'a'`).
```
print('apple' == 'apple')   # Output: True
print('apple' < 'banana')   # Output: True (because 'a' < 'b')
print('Apple' < 'apple')    # Output: True (because 'A' < 'a')
```


- ==Logical operations==
When used with logical operators (`and`, `or`, `not`), strings have a "truthiness" value.
	- An **empty string (`""`)** is considered **`False`**.
	- Any **non-empty string** is considered **`True`**.

```
# 'or' returns the first True value or the last value if all are False
result1 = "" or "Hello"
print(result1) # Output: Hello

# 'and' returns the first False value or the last value if all are True
result2 = "Hi" and "World"
print(result2) # Output: World

# 'not' inverts the truthiness
result3 = not ""
print(result3) # Output: True
```

- ==Loops in string==
Since strings are sequences, you can iterate over them directly using a `for` loop to process one character at a time.
- ==Membership operations==
You can check if a substring exists within a larger string using the `in` and `not in` operators. The result is always a boolean (`True` or `False`).

# 5. string functions and methods
A quick note on the difference:
- **Functions** like `len()` take the string as an argument: `len(my_string)`.
- **Methods** are called on the string object itself using dot notation: `my_string.upper()`.
## Common functions (work on many sequence types)
These functions are not exclusive to strings but are commonly used with them.
- **`len(string)`**: Returns the length (number of characters) of the string.
```
print(len("Hello")) # Output: 5
```
- **`max(string)` / `min(string)`**: Returns the character with the highest or lowest Unicode value.
```
print(max("python")) # Output: y
print(min("python")) # Output: h
```
- **`sorted(string)`**: Returns a **list** of the characters in the string, sorted alphabetically.
```
# Note that the output is a list, not a string
print(sorted("world")) # Output: ['d', 'l', 'o', 'r', 'w']
# To sort a string ins reverse
print(sorted("world",reverse = True)) # Output: ['w', 'r', 'o', 'l', 'd']

```
## Common String Methods (specific to strings)
#### 1. `Case Covnversion`

These methods return a new string with the case changed.
- `.capitalize()`: First character uppercase, rest lowercase.
- `.title()`: First character of each word uppercase.
- `.upper()`: All characters uppercase.
- `.lower()`: All characters lowercase.
- `.swapcase()`: Swaps the case of every character.
```
msg = "heLLo wORLd"
print(msg.capitalize()) # Output: Hello world
print(msg.title())      # Output: Hello World
print(msg.upper())      # Output: HELLO WORLD
print(msg.lower())      # Output: hello world
print(msg.swapcase())   # Output: HEllO WorlD
```
#### 2. `.count(substring)`
Returns the number of times a substring appears in the string.

```
print("hello world".count('l')) # Output: 3
```

#### 3. `.find(substring)` and `.index(substring)`
Both find the first occurrence of a substring.
- `.find()`: Returns **-1** if the substring is not found.
- `.index()`: Raises a **`ValueError`** if the substring is not found.
```
s = "hello"
print(s.find('l'))    # Output: 2
print(s.find('x'))    # Output: -1
# print(s.index('x')) # This would cause a ValueError
```
### 4. `.startswith(substring)` and `.endswith(substring)`
Check if the string starts or ends with a specific substring. Returns `True` or `False`.
```
filename = "document.pdf"
print(filename.startswith("doc")) # Output: True
print(filename.endswith(".txt"))  # Output: False
```
#### 5. `.format()`
A way to insert values into a string's placeholders (`{}`). **Note: f-strings are now more common and often preferred.**
```
print("Hello, {}. You are {}.".format("Alice", 30))
# Output: Hello, Alice. You are 30.
```
#### 6. Validation Methods (`is...`)
These methods check the characters in a string and return `True` or `False`.
- `.isalnum()`: True if all characters are letters or numbers.
- `.isalpha()`: True if all characters are letters.
- `.isdigit()`: True if all characters are digits (0-9).
```
print("Python3".isalnum()) # Output: True
print("Python".isalpha())  # Output: True
print("12345".isdigit())   # Output: True
```
#### 7. `.split(separator)`
Splits a string into a **list** of substrings. If no separator is given, it splits by whitespace.
```
csv_data = "apple,banana,cherry"
print(csv_data.split(',')) # Output: ['apple', 'banana', 'cherry']
```
#### 8. `separator.join(iterable)`
The opposite of `split`. Joins the elements of an iterable (like a list) into a single string, with the separator string in between each element.

```
words = ['Python', 'is', 'fun']
sentence = " ".join(words)
print(sentence) # Output: Python is fun
```
#### 9. `.replace(old, new)`
Returns a new string where all occurrences of `old` are replaced by `new`.
```
s = "I like cats."
new_s = s.replace("cats", "dogs")
print(new_s) # Output: I like dogs.
```
#### 10. `.strip()`, `.lstrip()`, `.rstrip()`

Removes whitespace from the beginning and/or end of a string.
- `.strip()`: Removes from both ends.
- `.lstrip()`: Removes from the left side.
- `.rstrip()`: Removes from the right side.

```
s = "   some spaces   "
print(s.strip()) # Output: "some spaces"
```