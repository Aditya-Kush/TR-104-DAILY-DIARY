# Date = 3 February 2025  
# Dictionaries and Sets in Python  

Today, I explored dictionaries and sets, two powerful Python data structures for storing data with key-value pairs and unique elements, respectively.

---

## Key Concepts Covered:
1. Creating dictionaries and sets.
2. Accessing, adding, and removing dictionary items.
3. Set operations: union, intersection, difference.
4. When to use dictionaries vs sets.
5. Iterating through dictionaries and sets.

---

## Dictionaries  
- Dictionaries store data in key-value pairs.
- Keys must be unique and immutable.
- Values can be any data type.

---

## Sets  
- Sets are unordered collections of unique elements.
- Useful for membership testing and eliminating duplicates.

---

## Simple Python Examples  

```python
# Dictionary example
person = {'name': 'Alice', 'age': 25, 'city': 'New York'}
print(person['name'])  # Alice
person['age'] = 26

# Set example
unique_numbers = {1, 2, 3, 2, 1}
print(unique_numbers)  # {1, 2, 3}

# Set operations
a = {1, 2, 3}
b = {3, 4, 5}
print(a.union(b))        # {1, 2, 3, 4, 5}
print(a.intersection(b)) # {3}
