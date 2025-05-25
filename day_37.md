# Date: 26 March 2025  
## Techniques and Tools of Exploratory Data Analysis (EDA)

---

### Common Techniques in EDA  

#### 1. Data Cleaning  
- Handling missing values (imputation, deletion)  
- Correcting inconsistencies and errors  
- Removing duplicates

#### 2. Data Transformation  
- Scaling and normalization  
- Encoding categorical variables (one-hot, label encoding)  
- Feature engineering (creating new features)

#### 3. Data Visualization  
- Histograms and density plots (distribution of variables)  
- Box plots (outlier detection)  
- Scatter plots and pair plots (relationships between variables)  
- Bar charts (categorical data visualization)  
- Heatmaps (correlation matrices)  

#### 4. Statistical Summaries  
- Central tendency: mean, median, mode  
- Dispersion: variance, standard deviation, range, IQR  
- Skewness and kurtosis (shape of distribution)

#### 5. Dimensionality Reduction (optional)  
- Principal Component Analysis (PCA) to visualize high-dimensional data

---

### Popular Tools and Libraries for EDA  

| Tool/Library       | Description                                  | Use Case                          |
|--------------------|----------------------------------------------|----------------------------------|
| **Pandas**         | Data manipulation and cleaning                | Data wrangling and summaries     |
| **NumPy**          | Numerical operations                           | Arrays and mathematical functions|
| **Matplotlib**     | Basic plotting library                         | Customizable charts and plots    |
| **Seaborn**        | Statistical data visualization built on Matplotlib | Advanced visualizations like pairplots and heatmaps |
| **Plotly**         | Interactive plotting                           | Dashboards and interactive plots |
| **Jupyter Notebook** | Interactive coding environment               | Exploratory programming and visualization |

---

### Example: Using Key EDA Tools in Python

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load dataset
df = sns.load_dataset('titanic')

# Data Cleaning: Check missing values
print(df.isnull().sum())

# Data Transformation: Fill missing age values with median
df['age'].fillna(df['age'].median(), inplace=True)

# Statistical Summary
print(df.describe())

# Visualization: Age distribution
sns.histplot(df['age'], kde=True)
plt.show()

# Visualization: Survival rate by sex
sns.barplot(x='sex', y='survived', data=df)
plt.show()

# Correlation heatmap (numerical features only)
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.show()
