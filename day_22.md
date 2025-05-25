# Date = 25 February 2025  
# Mini Project Part 1: Data Collection & Preparation using Excel and Pandas

## Goal of the Day:
To import and inspect an Excel-based dataset and perform initial data cleaning using **Pandas**. Excel was used to review the dataset structure and spot any missing or inconsistent entries.

---

## Python Example:

```python

import matplotlib.pyplot as plt

# Total sales by product line
sales_by_product = df.groupby("Product line")["Total"].sum().sort_values(ascending=False)
print(sales_by_product)

# Average rating by city
avg_rating = df.groupby("City")["Rating"].mean()
print(avg_rating)

# Add Hour column for time-based analysis
df["Hour"] = pd.to_datetime(df["Time"]).dt.hour

# Plot sales by hour
df.groupby("Hour")["Total"].sum().plot(kind='line', title='Sales by Hour')
plt.xlabel("Hour of Day")
plt.ylabel("Total Sales")
plt.grid(True)
plt.show()
