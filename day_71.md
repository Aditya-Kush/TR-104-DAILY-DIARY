# Date = 16 May 2025  
# CREATING NEW FEATURES, ENCODING, AND SCALING

Today, I focused on practical techniques for creating new features, encoding categorical variables, and scaling numerical features to prepare data effectively for machine learning models.

---

## 1. Creating New Features  
Creating new features involves deriving meaningful variables from existing data to provide more insights to the model.

### Examples:  
- Extracting date components: year, month, day, weekday from a datetime column.  
- Combining features: creating ratios or differences (e.g., profit = revenue - cost).  
- Aggregation: summarizing data using group-wise statistics like mean or count.

---

## 2. Encoding Categorical Variables  
Machine learning models require numerical input, so categorical features must be converted.

### Encoding Techniques:  

- **Label Encoding:**  
  Assigns each category an integer label. Useful for ordinal data but can introduce unintended order for nominal data.

- **One-Hot Encoding:**  
  Converts each category into a new binary column. Prevents ordering issues but increases dimensionality.

- **Target Encoding (Briefly):**  
  Maps categories to target variable statistics (like mean target value).

---

## 3. Scaling Numerical Features  
Scaling adjusts the range of features to help algorithms converge faster and perform better.

### Common Methods:

- **Min-Max Scaling:**  
  Scales data to a fixed range [0,1].

- **Standardization (Z-score Scaling):**  
  Centers data to mean 0 with standard deviation 1.

---

## Python Code Example:

```python
import pandas as pd
from sklearn.preprocessing import LabelEncoder, OneHotEncoder, StandardScaler

# Sample data
data = {
    'Date': ['2023-05-01', '2023-06-15', '2023-07-20'],
    'Category': ['Low', 'Medium', 'High'],
    'Sales': [100, 200, 150]
}

df = pd.DataFrame(data)

# 1. Creating new features from Date
df['Date'] = pd.to_datetime(df['Date'])
df['Year'] = df['Date'].dt.year
df['Month'] = df['Date'].dt.month
df['Day'] = df['Date'].dt.day
df['Weekday'] = df['Date'].dt.weekday

# 2. Encoding categorical variable 'Category' using Label Encoding
le = LabelEncoder()
df['Category_Label'] = le.fit_transform(df['Category'])

# Or One-Hot Encoding
df_onehot = pd.get_dummies(df['Category'], prefix='Category')

# Merge one-hot encoded columns back to original df
df = pd.concat([df, df_onehot], axis=1)

# 3. Scaling numerical feature 'Sales'
scaler = StandardScaler()
df['Sales_Scaled'] = scaler.fit_transform(df[['Sales']])

print(df)
