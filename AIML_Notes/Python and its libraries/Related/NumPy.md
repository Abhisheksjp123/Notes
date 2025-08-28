NumPy (Numerical Python) is a fundamental library for scientific computing in Python. It's a low-level library written primarily in **C and Fortran**, providing powerful tools for high-performance mathematical and logical operations on large, multi-dimensional arrays.

### Why NumPy? The Problem of Speed

Python is an easy-to-learn, high-level language because of its many layers of abstraction over C. While this makes it user-friendly, it also makes it significantly slower for complex numerical computations, which was a major hurdle for its adoption in machine learning.

NumPy solves this problem by providing a powerful N-dimensional array object (ndarray) and a collection of functions that operate on these arrays. Because the core operations are performed in compiled C code, they are orders of magnitude faster than their equivalents in pure Python.

In fact, NumPy is the foundational building block for many other data science libraries. For example, nearly all data in a pandas DataFrame is built on top of NumPy arrays.


Properties of ndarray
ndarray are similar to C arrays, they are homogeneous(can carry only same types of items). Can only carry integer, floats and complex. and their size is fixed, cannot be changed once created.

[[Python List vs numpy Array]]

Notebook to discuss CRUD operations of Numpy array is : [Numpy Notebook on Colab](https://colab.research.google.com/drive/18ydwUBJewEHNzdQz1P4_UpeEX93fPDg6)
NB sitting in 10abhishek10 drive

==In the Colab notes there is a option mentioned in numpy about Broadcasting array operation==
It can also be understood with this image (as colabcannot contain image)
![[Pasted image 20250827135018.png]]