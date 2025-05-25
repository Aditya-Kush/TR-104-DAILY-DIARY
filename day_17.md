# Date = 14 February 2025
# PYTHON LIBRARIES
The goal of Day 3 was to learn how to use "NumPy", A fundamental library for numerical computing in Python. NumPy provides efficient array operations, mathematical functions and tools for working with large datasets.

---


# Python Libraries
Python’s standard library is very extensive offering a wide range of facilities as indicated by the long table of contents listed below. The library contains built-in modules (written in C) that provide access to system functionality such as file I/O that would otherwise be inaccessible to Python programmers as well as modules written in Python that provide standardized solutions for many problems that occur in everyday programming. A Python library is a collection of pre-written code, functions, and modules that you can use to perform common tasks without having to write the code from scratch. These libraries help save time and effort by providing ready-made solutions for a wide range of programming problems. 
Python has a vast ecosystem of libraries for tasks such as data analysis (e.g., NumPy, Pandas), Machine learning (e.g., TensorFlow, scikit-learn) and more. To use a library in Python, you typically install it via pip (Python's package manager) and import it into your project.

---

# Introduction to NumPy

## What is NumPy?
- NumPy was created in 2005 by Travis Oliphant. It is an open source project and you can use it freely.
- NumPy stands for Numerical Python.
- NumPy is a Python library used for working with arrays.
- It also has functions for working in domain of linear algebra, fourier transform, and matrices.
 NumPy aims to provide an array object that is up to 50x faster than traditional Python lists.
- The array object in NumPy is called ndarray and it provides a lot of supporting functions that make working with ndarray very easy.
- Arrays are very frequently used in data science, where speed and resources are very important.

---

## Why Use NumPy?

1. Efficient Numerical Computation: NumPy provides fast and efficient operations on large arrays and matrices, making it ideal for scientific and mathematical computing tasks. Its vectorized operations are much faster than using Python's built-in lists.

2. Multidimensional Arrays: NumPy introduces the `ndarray` (N-dimensional array) object, which is capable of handling large multi-dimensional datasets, offering advanced indexing, slicing, and reshaping operations.

3. Mathematical Functions: It provides a vast collection of mathematical functions (e.g., linear algebra, statistical operations, Fourier transforms) that can be applied to arrays quickly and efficiently.

4. Compatibility with Other Libraries: NumPy integrates seamlessly with other libraries like Pandas, Matplotlib and SciPy forming the foundation of many scientific computing and data science workflows.

5. Memory Efficiency: NumPy arrays use less memory compared to Python lists, as it stores data more compactly and with a fixed data type, leading to faster processing and more efficient memory usage.

---

## What NumPy Does:

1. Array Creation: NumPy allows the creation of multi-dimensional arrays (`ndarray`), which are more efficient and flexible compared to Python lists.

2. Mathematical Operations: It supports element-wise operations, such as addition, subtraction, multiplication, and division, as well as more complex functions like trigonometric, exponential, and logarithmic functions.

3. Linear Algebra Operations: NumPy includes functions for matrix multiplication, eigenvalue computation, determinants, and other linear algebra operations, making it a powerful tool for mathematical calculations.

4. Random Number Generation: The library has a comprehensive set of random number generation functions, allowing you to create random data for simulations, statistical sampling, or testing purposes.

5. Array Manipulation: NumPy provides functions for reshaping, slicing, and indexing arrays, making it easier to manipulate large datasets and perform tasks like filtering, aggregating, and transforming data.

---

## Installation of NumPy
You can install NumPy Libray using command "pip install numpy" on your Terminal.


## One Simple Program for Creating a NumPy Array

```python

import numpy as np
arr = np.array([1, 2, 3, 4, 5])
print(arr)
print(type(arr))

```

## Today's Learning Summary:
Today, I learned that NumPy is a powerful Python library designed for numerical computations particularly for handling large multi-dimensional arrays with the ndarray object. It enables efficient operations, supports a wide range of mathematical functions and integrates well with other libraries like Pandas and Matplotlib. I also explored how to install NumPy and create basic arrays which are crucial for data manipulation and analysis in data science.