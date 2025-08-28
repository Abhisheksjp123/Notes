A **dictionary** in Python is an unordered collection of items. Unlike lists, which are indexed by a range of numbers, dictionaries are indexed by **keys**. Each key is associated with a **value**, creating what are known as **key-value pairs**.
Dictionaries are mutable, optimized for fast lookups, and are defined using curly braces `{}`

## 1. Creating a Dictionary
You can create a dictionary in several ways.
### Using Curly Braces `{}`
- Empty Dictionary
```
d = {}
```

- **Dictionary with Items**: Keys must be unique and are typically strings or numbers. Values can be of any data type.

```
# A simple dictionary
d = {'name': 'Ravi', 'age': 30, 'city': 'Delhi'}

# Dictionary with mixed key and value types
d = {'name': 'Alice', 1: [1, 2, 3]}
```

- Using the `dict()` Constructor
```
# From Key-Value Tuples:
d = dict([('name', 'Ravi'), ('age', 30)])
# Output: {'name': 'Ravi', 'age': 30}

# Using Keyword Arguments:
d = dict(name='Ravi', age=30)
# Output: {'name': 'Ravi', 'age': 30}
```

## 2. Accessing Items
You access the value associated with a key, not an index.
### Using Square Brackets `[]`
This is the most direct way. If the key does not exist, it will raise a `KeyError`.
```
d = {'name': 'Ravi', 'age': 30}
print(d['name'])
# Output: Ravi
```
### Using the `.get()` Method
This method is safer because it returns `None` (or a specified default value) if the key doesn't exist, instead of raising an error.
```
d = {'name': 'Ravi', 'age': 30}
print(d.get('age'))       # Output: 30
print(d.get('city'))      # Output: None
print(d.get('city', 'N/A')) # Output: N/A
```

## 3. Editing a Dictionary
Dictionaries are mutable, so you can easily add, update, or remove key-value pairs.
### Adding or Updating an Item
If the key exists, its value is updated. If the key does not exist, a new key-value pair is added.
```
d = {'name': 'Ravi', 'age': 30}

# Update an existing key
d['age'] = 31
print(d) # Output: {'name': 'Ravi', 'age': 31}

# Add a new key-value pair
d['city'] = 'Mumbai'
print(d) # Output: {'name': 'Ravi', 'age': 31, 'city': 'Mumbai'}
```

## 4. Deleting from a Dictionary
`del` Keyword
Removes the key-value pair for a specified key. Raises a `KeyError` if the key is not found.
```
d = {'name': 'Ravi', 'age': 30, 'city': 'Delhi'}
del d['age']
print(d) # Output: {'name': 'Ravi', 'city': 'Delhi'}
```
