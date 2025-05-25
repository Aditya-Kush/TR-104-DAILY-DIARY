# Date: 25 March 2025  
## Exploratory Data Analysis (EDA) in Data Science

---

### What is Exploratory Data Analysis?  
EDA is the process of analyzing and summarizing datasets to understand their main characteristics, often using visual methods. It helps uncover patterns, spot anomalies, test hypotheses, and check assumptions before modeling.

---

### Objectives of EDA  
- Understand data distribution and variability  
- Detect outliers and missing values  
- Identify relationships between variables  
- Prepare data for modeling

---

### Key EDA Techniques

#### 1. Summary Statistics  
- **Measures of Central Tendency:** Mean, median, mode  
- **Measures of Dispersion:** Variance, standard deviation, range, interquartile range (IQR)

#### 2. Data Visualization  
- **Histograms:** Show distribution of single variables  
- **Box Plots:** Identify outliers and visualize spread  
- **Scatter Plots:** Explore relationships between two variables  
- **Bar Charts:** Compare categorical data  
- **Correlation Matrix Heatmaps:** Visualize correlations between variables

#### 3. Handling Missing Data  
- Detect missing values  
- Decide on imputation or removal

---

### Python Libraries for EDA  
- `pandas` for data manipulation and summary statistics  
- `matplotlib` and `seaborn` for visualization  
- `numpy` for numerical operations

---

### Sample EDA Workflow in Python

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load dataset
df = sns.load_dataset('iris')

# Summary statistics
print(df.describe())

# Check for missing values
print(df.isnull().sum())

# Visualize distributions
sns.histplot(df['sepal_length'], kde=True)
plt.show()

# Boxplot for outliers
sns.boxplot(x='species', y='sepal_length', data=df)
plt.show()

# Scatter plot between two variables
sns.scatterplot(x='sepal_length', y='petal_length', hue='species', data=df)
plt.show()

# Correlation heatmap
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.show()
