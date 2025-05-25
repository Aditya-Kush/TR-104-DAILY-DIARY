# Date = 29 January 2025  
# Working with Lists and Tuples in Python  

Today, I learned about two important Python data structures: lists and tuples. These are used to store collections of items and are fundamental when working with data.

---

## Key Concepts Covered:
1. Creating lists and tuples.
2. Accessing elements using indexing and slicing.
3. Common list methods: append, insert, remove, pop, sort.
4. Differences between lists and tuples.
5. Iterating through lists and tuples.

---

## Lists  
- Lists are mutable, meaning you can change their contents after creation.
- They are ordered collections of items and can contain mixed data types.

---

## Tuples  
- Tuples are immutable, meaning once created, their contents cannot be changed.
- Useful when you want to ensure data integrity.

---

## Simple Python Examples  

```python
# List example
fruits = ['apple', 'banana', 'cherry']
fruits.append('orange')
print(fruits[1])  # banana

# Tuple example
coordinates = (10.0, 20.0)
print(coordinates[0])  # 10.0

# Iteration
for fruit in fruits:
    print(fruit)
