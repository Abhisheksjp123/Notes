An **unordered** collection of **unique** elements. Duplicates are automatically removed.
Rules:
1. Sets do not allow duplicates
2. Sets do not allow indexing
3. Sets do not allow mutable datatypes 
4. Sets itself is a mutable datatype -> hence 2D sets are not possible

# 1. Creation

1. Empty SET
S = set()
Because though sets can be created with curly braces, for a empty set pyhton has given curly braces to dictionary
2. Homogenous set
S = {1,2,3}
3. Heterogenous set
S = {'ravi',1,4}
4. Duplicates removal
S = {1,1,2,3}
print(S) # will return {1,2,3}

# 2. Retrieval
Indexing is not possible in sets hence no retrieval

# 3. Update
Even though sets are mutable as you cannot access them, you cannot update them.

# 4. Add/Remove
let S = {1,2,3}
1. S.add(4) - will add 4 to set
2. S.remove(4) - will remove 4

# 5. Set Operations
Let
```
s1 = {1, 2, 3, 4, 5}
s2 = {4, 5, 6, 7, 8}
```
### 1. Union
The **union** of two sets contains all the unique items that are in _either_ set.
- **Operator**: `|`
- **Method**: `.union()`
```
# Using the operator
print(s1 | s2)
# Output: {1, 2, 3, 4, 5, 6, 7, 8}

# Using the method
print(s1.union(s2))
# Output: {1, 2, 3, 4, 5, 6, 7, 8}
```
### 2. Intersection
The **intersection** of two sets contains only the items that are present in _both_ sets.
- **Operator**: `&`
- **Method**: `.intersection()`

```
print(s1 & s2)
# Output: {4, 5}

print(s1.intersection(s2))
# Output: {4, 5}
```
### 3. Difference
The **difference** between two sets contains items that are in the first set but **not** in the second set.
- **Operator**: `-`
- **Method**: `.difference()`

```
# Items in s1 but not in s2
print(s1 - s2)
# Output: {1, 2, 3}

# Items in s2 but not in s1
print(s2.difference(s1))
# Output: {6, 7, 8}
```
### 4. Symmetric Difference
The **symmetric difference** contains all items that are in _either_ set, but **not** in both.
- **Operator**: `^`
- **Method**: `.symmetric_difference()`

```
print(s1 ^ s2)
# Output: {1, 2, 3, 6, 7, 8}

print(s1.symmetric_difference(s2))
# Output: {1, 2, 3, 6, 7, 8}
```
## Set Relationship Methods
These methods return a Boolean value (`True` or `False`).
### 5. `isdisjoint()`
Returns `True` if the two sets have **no items in common**.

```
s1 = {1, 2, 3}
s2 = {4, 5, 6}
print(s1.isdisjoint(s2))
# Output: True
```
### 6. `issubset()`
Returns `True` if **all items** of one set are contained within another set.
```
s1 = {1, 2}
s2 = {1, 2, 3, 4}
print(s1.issubset(s2))
# Output: True
```
### 7. `issuperset()`
Returns `True` if a set contains **all the items** of another set. It's the opposite of `issubset()`.
```
s1 = {1, 2, 3, 4}
s2 = {1, 2}
print(s1.issuperset(s2))
# Output: True
```