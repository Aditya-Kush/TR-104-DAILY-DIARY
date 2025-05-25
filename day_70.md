# Date = 15 May 2025  
# FEATURE ENGINEERING

Today, I focused on Feature Engineering, a crucial step in the machine learning pipeline that involves creating new features or transforming existing ones to improve model performance and accuracy.

---

## What is Feature Engineering?  
Feature Engineering is the process of using domain knowledge to extract, create, or transform variables (features) from raw data to make machine learning algorithms work better.

---

## Importance of Feature Engineering:  
- Helps models understand data patterns better.  
- Can improve accuracy and reduce overfitting.  
- Allows incorporation of domain knowledge.  
- Often more impactful than tuning model parameters.

---

## Common Feature Engineering Techniques:

### 1. Feature Creation  
- Deriving new features from existing data (e.g., extracting ‘Year’ from a ‘Date’ column).  
- Combining features (e.g., total price = quantity × unit price).

### 2. Feature Transformation  
- Scaling: Normalize or standardize features to a common scale.  
- Logarithmic transformation: Useful for skewed data.  
- Polynomial features: Creating interaction or higher-degree terms.

### 3. Encoding Categorical Variables  
- Label Encoding: Assigning integers to categories.  
- One-Hot Encoding: Creating binary columns for each category.

### 4. Handling Date and Time Features  
- Extracting components like day, month, year, weekday, hour.  
- Calculating time differences or durations.

### 5. Binning or Discretization  
- Converting continuous variables into categorical bins (e.g., age groups).

---

## Example Feature Engineering in Python:

```python
import pandas as pd
from sklearn.preprocessing import StandardScaler, OneHotEncoder

# Sample data
data = {
    'Date': ['2024-01-01', '2024-02-15', '2024-03-10'],
    'Sales': [250, 450, 300],
    'Category': ['A', 'B', 'A']
}

df = pd.DataFrame(data)

# Convert Date column to datetime
df['Date'] = pd.to_datetime(df['Date'])

# Extract Year and Month from Date
df['Year'] = df['Date'].dt.year
df['Month'] = df['Date'].dt.month

# One-hot encode Category
df = pd.get_dummies(df, columns=['Category'])

# Scale Sales
scaler = StandardScaler()
df['Sales_scaled'] = scaler.fit_transform(df[['Sales']])

print(df)
