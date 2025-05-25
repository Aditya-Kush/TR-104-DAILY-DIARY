# Date = 11 February 2025  
# Advanced Python: Object-Oriented Programming (OOP) Basics  

Today, I delved into the basics of advanced OOP concepts in Python. Understanding OOP is essential for writing modular and reusable code, especially in complex projects.

---

## Key Concepts Covered:
1. Classes and Objects.
2. Attributes and Methods.
3. The `__init__` constructor method.
4. Encapsulation and Access Modifiers (public, private).
5. Inheritance and method overriding (basic introduction).
6. The `self` keyword.

---

## What is OOP?  
- Object-Oriented Programming organizes code into objects that contain both data and behavior.
- It promotes code reuse, scalability, and easier maintenance.

---

## Simple Python Examples  

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        print(f"Hello, my name is {self.name} and I am {self.age} years old.")

p1 = Person("Alice", 30)
p1.greet()
