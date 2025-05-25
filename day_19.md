# Date = 18 February 2025  
# Python for Data Science: Pandas Basics  

Today, I learned the basics of **Pandas**, a powerful data analysis and manipulation library in Python. Pandas is essential for working with structured data like CSV files, Excel sheets, and SQL tables.

---

## Key Concepts Covered:
1. Series and DataFrame.
2. Creating DataFrames manually and from CSV.
3. Reading and writing CSV files.
4. Data inspection (`head()`, `info()`, `describe()`).
5. Indexing and selecting data (`loc`, `iloc`).
6. Basic operations and filtering.
7. Handling missing values (`isnull()`, `dropna()`, `fillna()`).

---

## What is Pandas?  
- Pandas is a high-level data manipulation tool built on NumPy.
- It provides fast, flexible data structures like Series (1D) and DataFrame (2D) for data analysis and modeling.

---

## Simple Python Examples  

```python
import pandas as pd

# Creating a DataFrame from a dictionary
data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'City': ['New York', 'Paris', 'London']
}
df = pd.DataFrame(data)

# Display the DataFrame
print(df)

# Inspecting the data
print(df.head())        # First 5 rows
print(df.info())        # Data types and nulls
print(df.describe())    # Summary statistics

# Accessing columns and rows
print(df['Name'])       # Accessing a column
print(df.loc[0])        # Accessing first row by label
print(df.iloc[1])       # Accessing second row by index

# Filtering data
print(df[df['Age'] > 28])

# Handling missing data
df2 = pd.DataFrame({
    'A': [1, 2, None],
    'B': [None, 5, 6]
})
print(df2.isnull())
print(df2.dropna())
print(df2.fillna(0))
