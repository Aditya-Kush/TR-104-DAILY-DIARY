# Date = 28 January 2025  
# Functions in Python  

Today, I explored how to write reusable blocks of code using functions. Functions help organize code, make it reusable, and improve readability — all important for larger data science projects.

---

## Key Concepts Covered:
1. Defining functions using def keyword.
2. Function parameters and arguments.
3. Return statement.
4. Scope of variables inside and outside functions.
5. Calling functions with and without arguments.
6. Built-in functions vs user-defined functions.

---

## Why Use Functions?  
- Functions reduce repetition and improve code modularity.
- They help break complex tasks into smaller manageable pieces.
- Functions can take inputs, process them, and return outputs.

---

## Simple Python Examples  

```python
# Function with no arguments
def greet():
    print("Hello, Data Science!")

# Function with arguments and return
def add_numbers(a, b):
    return a + b

greet()
result = add_numbers(5, 7)
print("Sum is", result)
