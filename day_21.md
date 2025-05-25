# Date = 24 February 2025  
# Mini Project Part 1: Data Collection & Preparation using Excel and Pandas

## Goal of the Day:
To import and inspect an Excel-based dataset and perform initial data cleaning using **Pandas**. Excel was used to review the dataset structure and spot any missing or inconsistent entries.

---

## Dataset Used:
- **Supermarket Sales Data** (in `.xlsx` format)
- Columns include: `Invoice ID`, `Branch`, `City`, `Customer Type`, `Gender`, `Product Line`, `Unit Price`, `Quantity`, `Tax`, `Total`, `Date`, `Time`, `Payment`, `Rating`

---

## Key Concepts Covered:
1. Reading Excel files with `pd.read_excel()`
2. Viewing data with `.head()`, `.tail()`, `.info()`, `.describe()`
3. Checking and handling missing/null values
4. Data type conversion (e.g., Date to `datetime`)
5. Using Excel for manual spotting of errors/inconsistencies

---

## Python Example:

```python
import pandas as pd

# Load the Excel file
df = pd.read_excel("supermarket_sales.xlsx")

# View structure
print(df.head())
print(df.info())

# Convert Date column to datetime
df['Date'] = pd.to_datetime(df['Date'])

# Check for missing values
print(df.isnull().sum())
