Operators are used to perform operation on a variable and values. Python has following operators. Types: 
1. Arithmetic operator
2. Comparision operator
3. Logical operator
4. Bitwise operator
5. Assignment operator
6. identity operator
7. Membership operators

Most of the operators are intutive, but A couple of operators which are unique and easy to forget in python, I'll cover them here
# Arithmetic operators
Simple arithmetic operation.
### 1. Modulus operator (%)
It gives the **remainder** when you divide a value with another. This is very useful for checking if a number is even or odd.

**Example:**
```
# If a number is perfectly divisible, the remainder is 0
print(10 % 2)  # Output: 0 (10 is even)

# If not, it gives the leftover value
print(11 % 2)  # Output: 1 (11 is odd)

print(15 % 4)  # Output: 3 (15 divided by 4 is 3 with a remainder of 3)
```

### 2. Power of operator (**)
This operator, also known as the **exponentiation** operator, raises the number on the left to the power of the number on the right.
**Example:**

```
# 2 to the power of 3 (2 * 2 * 2)
print(2 ** 3)  # Output: 8

# 5 squared (5 * 5)
print(5 ** 2)  # Output: 25
```

### 3. Integer division (//)
This operator performs a division and then **discards the decimal part**, keeping only the whole number (integer). It's also known as floor division.
**Example:**
```
# Normal division would give 3.5
print(7 / 2)   # Output: 3.5

# Integer division removes the .5
print(7 // 2)  # Output: 3

# Another example
print(10 // 3) # Output: 3 (Normal division is 3.33...)
```
# Comparison operator
1. Equal to / Not equal to
```
x == y
x != y
```
# Logical operators
or, and, not
# Bitwise Operators (SKIP)
These operators work directly on the **binary** (0s and 1s) representation of numbers. They are often used for low-level programming, data compression, and encryption.
### Bitwise AND (&)
This operator compares each bit of two numbers and returns a new number. A bit in the new number is `1` only if the corresponding bits in **both** original numbers are `1`.
Example:

Let's take 10 & 6.
- Binary of 10 is `1010`
- Binary of 6 is `0110`
```
  1010  (10)
& 0110  (6)
-------
  0010  (2)  -> The result is 2
```

**In Python:**
```
print(10 & 6)  # Output: 2
```
### Bitwise OR (|)
This operator compares each bit of two numbers and returns a new number. A bit in the new number is `1` if the corresponding bit in **either** of the original numbers is `1`.
Example:
Let's take 10 | 6.
- Binary of 10 is `1010`
- Binary of 6 is `0110`
```
  1010  (10)
| 0110  (6)
-------
  1110  (14) -> The result is 14
```
**In Python:**

```
print(10 | 6)  # Output: 14
```

### Bitwise Left Shift (<<)
This operator takes the binary representation of a number and shifts all its bits to the left by a specified number of places. Vacant positions on the right are filled with zeros.

Each left shift by one position is equivalent to **multiplying the number by 2**.
Example:

Let's take 5 << 2, which means "shift the bits of 5 to the left by 2 places."
- Binary of 5 is `0101`

Shift left by 1 place: 1010 (which is 10)
Shift left by 2 places: 10100 (which is 20)

**In Python:**
```
# Shifting 5 left by 2 is the same as 5 * (2**2)
print(5 << 2)  # Output: 20
```
# Assignment operators
1. =
2. a+=3 in equivalent to a = a+3
Note these does not work in python
a++, ++a
# Identity operators ==IMP==
Is, is not
These operators check if two variables point to the exact **same object in memory**, not just if they have the same value. This is different from the equality operator (`==`), which only checks if the values are equal.

```
a = 10
b = 10
print(a is b)  # Output: True (Both point to the same integer object)

x = "hello"
y = "hello"
print(x is y)  # Output: True (Both point to the same string object)
```
However, for mutable objects like lists, Python creates separate objects even if their contents are identical.
```
list1 = [1, 2, 3]
list2 = [1, 2, 3]
print(list1 is list2)  # Output: False (They are two different list objects)
print(list1 == list2)  # Output: True (Their values are the same)
```
# Membership operator
Membership operators in Python are used to check if a value is present in a sequence, like a list, string, or tuple.
These are only available in python and are very useful, because in other languages you need to write a if function to carry out these operation

```
my_list = [10, 20, 30, 40]
my_string = "hello world"

# Check if 30 is in the list
print(30 in my_list)  # Output: True

# Check if 'hello' is a substring
print("hello" in my_string)  # Output: True
```