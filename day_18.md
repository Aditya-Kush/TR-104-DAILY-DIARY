# Date = 17 February 2025  
# Python for Data Science: NumPy Basics  

Today, I explored the fundamentals of NumPy, a core library for numerical computing in Python. Understanding NumPy is crucial for data science, machine learning, and scientific computing tasks.

---

## Key Concepts Covered:
1. NumPy Arrays vs Python Lists.
2. Creating NumPy Arrays (`np.array`, `np.zeros`, `np.ones`, `np.arange`, `np.linspace`).
3. Array Attributes (`shape`, `dtype`, `ndim`, `size`).
4. Array Indexing and Slicing.
5. Array Operations (element-wise addition, multiplication, broadcasting).
6. Useful Functions (`np.mean`, `np.sum`, `np.max`, `np.min`, `np.dot`).

---

## What is NumPy?  
- NumPy (Numerical Python) is a powerful library for numerical operations on large, multi-dimensional arrays and matrices.
- It offers high-performance operations, mathematical functions, linear algebra tools, and random number capabilities.

---

## Simple Python Examples  

```python
import numpy as np

# Creating a 1D array
arr = np.array([1, 2, 3, 4])
print("1D Array:", arr)

# Creating a 2D array
matrix = np.array([[1, 2], [3, 4]])
print("2D Array:\n", matrix)

# Array operations
print("Array + 10:", arr + 10)
print("Array squared:", arr ** 2)

# Array attributes
print("Shape:", matrix.shape)
print("Data type:", matrix.dtype)

# Indexing
print("First element of arr:", arr[0])

# Useful functions
print("Sum of arr:", np.sum(arr))
print("Mean of matrix:", np.mean(matrix))

```

## Today's Learning Summary:
Today, I learned that NumPy is a powerful Python library designed for numerical computations particularly for handling large multi-dimensional arrays with the ndarray object. It enables efficient operations, supports a wide range of mathematical functions and integrates well with other libraries like Pandas and Matplotlib. I also explored how to install NumPy and create basic arrays which are crucial for data manipulation and analysis in data science.