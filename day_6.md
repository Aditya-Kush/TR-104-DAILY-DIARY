# Date = 27 January 2025  
# Control Flow: Conditional Statements and Loops  

Today, I learned how to control the flow of programs using conditionals and loops. These allow programs to make decisions and repeat tasks, which are critical concepts in programming and data science.

---

## Key Concepts Covered:
1. Conditional statements: if, elif, else.
2. Comparison and logical operators in conditions.
3. For loops: iterating over sequences.
4. While loops: repeating as long as a condition is true.
5. Break and continue statements.

---

## Conditional Statements  
- Conditional statements allow the program to execute different code blocks based on certain conditions.
- The elif keyword allows multiple conditions to be checked sequentially.

---

## Loops in Python  
- For loops iterate over iterable objects like lists or ranges.
- While loops run until a condition becomes false.
- Break stops the loop, continue skips the current iteration.

---

## Simple Python Examples  

```python
# Conditional
age = 20
if age >= 18:
    print("You are an adult")
else:
    print("You are a minor")

# For loop
for i in range(5):
    print(i)

# While loop
count = 0
while count < 3:
    print("Count is", count)
    count += 1
