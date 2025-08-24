1. print()
2. input()
3. type()
4. int() #typecasting
	also
	1. float()
	2. str()
	3. list()
	4. tuple()
5. abs()
6. min()/max()
7. round()
8. pow()
	pow(2,3) = 2^3 = 8
9. id ==imp==
	If returns address of the variable in memory
10. len()
11. sum()
12. help()
	Provides the documentation of a function
13. dir()
	The `dir()` function returns a simple list of all the attributes and methods

Difference b/w help() and dir()
The main difference is that `dir()` gives you a **list of what's available** in an object, while `help()` gives you the **documentation on how to use it**.

Think of `dir()` as the table of contents of a book, and `help()` as the actual chapter text.
==dir() use==
```
my_list = [1, 2, 3]

# What can I do with a list?
print(dir(my_list))
```

**Output (partial):**

```
['__add__', '__class__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
```

This shows you that methods like `append`, `sort`, and `pop` exist, but it doesn't tell you how to use them.
==help() use==
```
# I see 'append' from dir(). How do I use it?
help(list.append)
```

**Output:**

```
Help on method_descriptor in module builtins:

append(self, object, /)
    Append object to the end of the list.
```

This tells you exactly what `append` does and that it takes one argument (`object`).