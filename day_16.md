# Date = 13 February 2025  
# Python Lambda Functions and Modules  

Today, I explored Python lambda functions for creating small anonymous functions and learned about modules for organizing code.

---

## Key Concepts Covered:
1. Understanding lambda (anonymous) functions.
2. Syntax and use cases for lambda functions.
3. Using lambda functions with built-in functions like `map()`, `filter()`, and `sorted()`.
4. What are Python modules and how to import them.
5. Creating custom modules and using `import`.
6. The difference between standard library modules and third-party modules.

---

## Lambda Functions  
- Lambda functions are small, anonymous functions defined with the `lambda` keyword.
- Useful for short operations without formally defining a function.

---

## Modules  
- Modules help organize Python code into reusable files.
- Use `import` to include modules in your program.

---

## Simple Python Examples  

```python
# Lambda function example
square = lambda x: x ** 2
print(square(5))  # 25

# Using lambda with map()
numbers = [1, 2, 3, 4]
squared = list(map(lambda x: x**2, numbers))
print(squared)

# Importing a module
import math
print(math.sqrt(16))
