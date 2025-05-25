# Date = 19 February 2025
# PYTHON LIBRARIES
The goal of day was to familiarize with the "Pandas" library which is widely used for data analysis and manipulation. I focused on learning how to load, clean and manipulate datasets as well as basic statistics.

---

## Key Concepts Covered:
1. DataFrames and Series: The core data structures of pandas. DataFrames store tabular data (rows and columns), while Series represent single columns.
2. Loading Data: pd.read_csv() for loading datasets into a DataFrame.
3. Data Exploration: Methods like .head(), .tail(), .describe() to get an overview of the data.
4. Data Cleaning: Handling missing values with dropna() and fillna().

---

# Introduction to Pandas
Pandas is an open-source library that is built on top of NumPy library. It is a Python package that offers various data structures and operations for manipulating numerical data and time series. It is mainly popular for importing and analyzing data much easier. Pandas is fast and it has high-performance & productivity for users.
Pandas is a powerful and open-source Python library. The Pandas library is used for data manipulation and analysis. Pandas consist of data structures and functions to perform efficient operations on data.

---

## What is Pandas?
•⁠  ⁠The name "Pandas" has a reference to both "Panel Data" and "Python Data Analysis" and was created by Wes McKinney in 2008.
- Pandas is a powerful and versatile library that simplifies the tasks of data manipulation in Python. Pandas is well-suited for working with tabular data, such as spreadsheets or SQL tables.
- The Pandas library is an essential tool for data analysts, scientists and engineers working with structured data in Python.
•⁠  ⁠Pandas is a Python library used for working with data sets.
•⁠  ⁠It has functions for analyzing, cleaning, exploring and manipulating data.

---

## Why We Use Pandas:

1. Data Handling and Analysis: Pandas provides powerful, flexible data structures (e.g., `DataFrame` and `Series`) that make it easy to handle, manipulate, and analyze large datasets with different types of data (numeric, categorical, time series, etc.).

2. Easy Data Cleaning: It offers efficient methods for cleaning and transforming data, including handling missing values, filtering data, merging datasets, and reshaping tables, which are essential for real-world data processing.

3. Time Series Data: Pandas is particularly strong in handling time series data, providing robust tools for date/time manipulation, resampling, and time-based indexing, making it a go-to library for financial and temporal data analysis.

4. Integration with Other Libraries: Pandas integrates well with libraries like **NumPy**, **Matplotlib**, and **SciPy**, allowing for seamless workflows across data manipulation, analysis, and visualization.

5. Efficient Data Storage and Retrieval: With its efficient data structures, Pandas can read from and write to various file formats such as CSV, Excel, SQL, and HDF5, making data storage and retrieval straightforward.

---

## What Pandas Does:

1. DataFrame and Series: Pandas provides two key data structures: `DataFrame` (a table of rows and columns) and `Series` (a one-dimensional array), which allow you to organize and manipulate data efficiently.

2. Data Cleaning and Preprocessing: It simplifies tasks like handling missing data, filtering rows and columns, transforming data (e.g., applying functions), and detecting and removing duplicates.

3. Data Aggregation and Grouping: Pandas enables you to group data based on certain criteria and apply aggregation functions (e.g., sum, mean, count) to the groups, which is useful for summarizing large datasets.

4. Merging and Joining: It provides powerful tools to merge, join, and concatenate datasets, allowing for easy combining of multiple tables based on common columns or indexes, similar to SQL-style operations.

5. Data Visualization: While Pandas isn't a full-fledged plotting library, it has built-in integration with **Matplotlib** for simple visualizations such as line plots, bar charts, and histograms, directly from `DataFrame` and `Series` objects.

---

## Installing Pandas
The first step in working with Pandas is to ensure whether it is installed in the system or not.  If not, then we need to install it on our system using the pip command.

## Installation of Pandas

### Step 1: 
Type ‘cmd’ in the search box and open it.
### Step 2:
Locate the folder using the cd command where the python-pip file has been installed.

### Step 3:
After locating it, type the command 'pip install pandas'.

## Importing Pandas
After the Pandas have been installed in the system, you need to import the library. This module is generally imported by command 'import pandas as pd'

## One Simple Program for Creating a series using Pandas Library

```python

import pandas as pd 
import numpy as np

# Creating empty series 
ser = pd.Series() 
print("Pandas Series: ", ser) 

# simple array 
data = np.array(['g', 'e', 'e', 'k', 's']) 
  
ser = pd.Series(data) 
print("Pandas Series:\n", ser)

```

## Today's Learning Summary:
Today, I learned about Pandas, A powerful Python library for data manipulation and analysis. Pandas provides two primary data structures: DataFrame (for tabular data) and Series (for single columns). These structures make it easier to clean, explore and manipulate data. I explored key functionalities like loading data with read_csv(), handling missing values and using methods like .head(), .tail() and .describe() for data exploration. Pandas is well-suited for working with structured data and integrates seamlessly with other libraries like NumPy and Matplotlib. I also learned how to install Pandas using pip and create basic Series using NumPy arrays.