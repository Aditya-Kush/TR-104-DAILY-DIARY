# Date = 14 May 2025  
# ADVANCED DATA CLEANING TECHNIQUES

Today, I focused on advanced data cleaning techniques that go beyond basic missing value handling and duplicate removal. Proper cleaning ensures data quality, which directly affects model performance and insights.

---

## Why Advanced Data Cleaning?

Real-world datasets often contain complex issues like outliers, inconsistent data formats, noisy data, and incorrect entries. Addressing these requires more sophisticated techniques than simple imputation or dropping rows.

---

## Key Advanced Data Cleaning Techniques

### 1. Handling Outliers

Outliers can skew analysis and model predictions. Techniques include:

- **Z-score Method:** Identify points where the z-score is beyond a threshold (e.g., ±3).
- **IQR Method:** Use interquartile range to detect outliers outside 1.5 * IQR above Q3 or below Q1.

```python
import numpy as np

# Using IQR to detect outliers in a column
Q1 = df['column_name'].quantile(0.25)
Q3 = df['column_name'].quantile(0.75)
IQR = Q3 - Q1

outliers = df[(df['column_name'] < (Q1 - 1.5 * IQR)) | (df['column_name'] > (Q3 + 1.5 * IQR))]
print(outliers)
