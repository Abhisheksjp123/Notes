A **list** in Python is an ordered and mutable collection of items, meaning you can change its contents. Lists are incredibly versatile and can hold items of different data types.

# 1. Creating list
```
# Empty list
L = []
# List with multiple data types
L = [1,2,"ravi",[1,2]]
# Multi dimention list
L = [[1,2],[3,4]] -> 2D list, list inside a list
# List can be created by typecasting with list()
L = list("Ravi")
```

[[Python List vs numpy Array]]
# 2. Accessing a list
Accessing items in a list is very similar to accessing characters in a string. You can retrieve a single item using its index or a sub-section of the list using slicing.
## Concept of Indexing(Accessing a Single item)
**Indexing** is used to get a single item from a list by referring to its position. Python uses **zero-based indexing**, meaning the first item is at index 0.
- **Positive Indexing**: Starts from 0 for the first item and goes up.
- **Negative Indexing**: Starts from -1 for the last item and goes backward.
```
L = ['p', 'r', 'o', 'b', 'e']
# Positive indexing
print(L[0])   # Output: 'p'
print(L[2])   # Output: 'o'
# Negative indexing
print(L[-1])  # Output: 'e'
print(L[-3])  # Output: 'o'
```

## Slicing a string - Accessing a Sub list
**Slicing** is used to get a range of items from a list, which creates a new list. The syntax is `list[start:stop:step]`.
- **`start`**: The index of the first item to include (default is 0).
- **`stop`**: The index of the first item _not_ to include.
- **`step`**: The interval between items (default is 1).
```
my_list = ['p', 'r', 'o', 'g', 'r', 'a', 'm', 'i', 'z']

# Items from index 2 to index 4
# Includes items at index 2, 3, 4
print(my_list[2:5])
# Output: ['o', 'g', 'r']

# Items from the beginning to index 3
# Includes items at index 0, 1, 2, 3
print(my_list[:4])
# Output: ['p', 'r', 'o', 'g']

# Items from index 5 to the end
print(my_list[5:])
# Output: ['a', 'm', 'i', 'z']

# Get every second item
print(my_list[::2])
# Output: ['p', 'o', 'r', 'm', 'z']

# Reverse the list
print(my_list[::-1])
# Output: ['z', 'i', 'm', 'a', 'r', 'g', 'o', 'r', 'p']
```

# 3. Editing a list
Unlike strings, lists are **mutable**, which means you can change their content after they are created. You can edit a single item using indexing or modify multiple items at once using slicing.

```
# Example 1: Indexing
my_list = [1, 2, 3, 4, 5]

# Change the item at index 2 (the third item)
my_list[2] = 99

print(my_list)
# Output: [1, 2, 99, 4, 5]

# Example 2: Slicing
my_list = [1, 2, 3, 4, 5]

# Replace the items from index 1 up to (but not including) index 4
my_list[1:4] = [22, 33]

print(my_list)
# Output: [1, 22, 33, 5]
# Note: The new list doesn't have to be the same size as the slice it's replacing.
```

# 5. Adding to List

1. append()
The **`append()`** method adds a **single element** to the very end of the list.
If you append another list, it gets added as a single, nested item.
```
my_list = [1, 2, 3]

# Append a single integer
my_list.append(4)
print(my_list)
# Output: [1, 2, 3, 4]

# Append a list
my_list.append([5, 6])
print(my_list)
# Output: [1, 2, 3, 4, [5, 6]]
```
2. extend()
The **`extend()`** method adds all the items from an sequence (like another list, a tuple, or a string) to the end of the list, one by one.
It's used to merge a list with another sequence, effectively increasing the length of the list by the number of items in the sequence.

```
my_list = [1, 2, 3]
another_list = [4, 5, 6]

# Extend the list with another list
my_list.extend(another_list)
print(my_list)
# Output: [1, 2, 3, 4, 5, 6]

# Extend the list with a string
my_list.extend("abc")
print(my_list)
# Output: [1, 2, 3, 4, 5, 6, 'a', 'b', 'c']
```

3. insert(index to insert, value to insert)
The **`insert()`** method adds a single element at a **specific index** that you choose. All the items at and after that index are shifted one position to the right.
The syntax is `list.insert(index, element)`.

# 4. Delete
1. `del` Keyword
The **`del`** keyword removes an item or a slice of items at a **specific index**. It's a general Python keyword, not a list method.
```
my_list = [10, 20, 30, 40, 50]

# Delete the item at index 2
del my_list[2]
print(my_list)
# Output: [10, 20, 40, 50]

# Delete a slice of items from index 1 to 3
del my_list[1:3]
print(my_list)
# Output: [10, 50]
```

1. remove() method
The **`remove()`** method searches for and deletes the **first occurrence** of a specified **value**. If the value is not found, it raises a `ValueError`.
```
my_list = ['a', 'b', 'c', 'a', 'd']

# Remove the first 'a' it finds
my_list.remove('a')
print(my_list)
# Output: ['b', 'c', 'a', 'd']
```
1. pop()
The **`pop()`** method removes and **returns** the item at a specified **index**. If you don't specify an index, it removes and returns the **last item** in the list. This is useful when you need to use the removed item immediately.
```
my_list = [10, 20, 30, 40, 50]

# Pop the last item
last_item = my_list.pop()
print("Popped item:", last_item) # Output: Popped item: 50
print("List now:", my_list)      # Output: List now: [10, 20, 30, 40]

# Pop the item at index 1
item_at_index_1 = my_list.pop(1)
print("Popped item:", item_at_index_1) # Output: Popped item: 20
print("List now:", my_list)           # Output: List now: [10, 30, 40]
```

2. clear()
The **`clear()`** method removes **all items** from the list, leaving it empty.

# 5. Operations on list
Operations in list works similar to strings
- ==Arithmetic operation==
You can use two arithmetic-style operators on list: `+` for concatenation and `*` for repetition.
```
l1 = [1,2,3]
l2 = [4,5,6]
print(l1+l2) #[1,2,3,4,5,6]

print(l1*2) = [1,2,3,1,2,3]
```

- ==Loops in list==
Since list are sequences, you can iterate over them directly using a `for` loop to process one character at a time.
- ==Membership operations==
You can check if a sub list exists within a larger .list  using the `in` and `not in` operators. The result is always a Boolean (`True` or `False`).

# 6. List functions and methods
A quick note on the difference:
- **Functions** like `len()` take the list as an argument: `len(L1)`.
- **Methods** are called on the list object itself using dot notation: L1.pop()`

### Common Functions
1. len()
2. max/ min()
3. sorted()
Not an in-place operation, Returns a sorted list.
takes reverse attribute as well
4. sort()
### Common methods (specific to lists)
let l = \[1,2,3,4]

1. l.sort()
same as sorted function, but works in-place.
2. l.index()
returns index of first occurrence of the item 
l.index(3) will return 2


