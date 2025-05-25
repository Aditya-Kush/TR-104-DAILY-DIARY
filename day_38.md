# Date: 27 March 2025  
## Mini Project 2: Exploratory Data Analysis (EDA) + Statistical Analysis

---

### Project Overview  
This mini project involves performing EDA and basic statistical analysis on a real-world dataset to extract insights and understand the data better. The chosen dataset is the **Titanic dataset**, which contains information about passengers on the Titanic ship, including demographics and survival status.

---

### Objectives  
- Perform data cleaning and preprocessing.  
- Conduct exploratory data analysis using statistical summaries and visualizations.  
- Apply hypothesis testing to analyze relationships between variables.

---

### Step 1: Data Loading and Cleaning

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from scipy import stats

# Load Titanic dataset
df = sns.load_dataset('titanic')

# Check missing values
print("Missing values per column:")
print(df.isnull().sum())

# Fill missing 'age' values with median
df['age'].fillna(df['age'].median(), inplace=True)

# Drop rows with missing 'embarked'
df.dropna(subset=['embarked'], inplace=True)

# Verify changes
print("\nAfter cleaning:")
print(df.isnull().sum())

```

```python

print(df.describe())
print(df['sex'].value_counts())
print(df['class'].value_counts())

```
```python
# Age distribution
sns.histplot(df['age'], kde=True)
plt.title('Age Distribution')
plt.show()

# Survival count by sex
sns.countplot(x='survived', hue='sex', data=df)
plt.title('Survival Count by Sex')
plt.show()

# Boxplot: Age by survival status
sns.boxplot(x='survived', y='age', data=df)
plt.title('Age Distribution by Survival Status')
plt.show()

# Correlation heatmap
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.title('Correlation Heatmap')
plt.show()

```

```python
# Create contingency table
contingency_table = pd.crosstab(df['sex'], df['survived'])
print(contingency_table)

# Perform Chi-Square test
chi2, p, dof, expected = stats.chi2_contingency(contingency_table)
print(f"Chi-square statistic: {chi2:.3f}")
print(f"P-value: {p:.3f}")

alpha = 0.05
if p < alpha:
    print("Reject null hypothesis: Survival depends on sex.")
else:
    print("Fail to reject null hypothesis: No evidence survival depends on sex.")
