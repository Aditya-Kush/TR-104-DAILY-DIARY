# Date = 9 May 2025  
# WORKING WITH REAL DATASET

Today, I focused on practical aspects of working with real-world datasets in machine learning projects. Handling real data involves multiple steps like loading, cleaning, exploring, preprocessing, and preparing the data for modeling.

---

## Key Steps in Working with Real Datasets:

### 1. Data Loading  
Real datasets can come in various formats such as CSV, Excel, JSON, databases, or online sources. Libraries like **pandas** make it easy to load and manipulate these datasets.

### 2. Data Exploration  
Initial exploration helps understand the dataset’s structure, types of variables, missing values, and distribution. Common techniques include:
- Viewing the first few rows (`head()`)
- Checking data types and summary statistics (`info()`, `describe()`)
- Visualizing distributions and relationships

### 3. Data Cleaning  
Real data often has:
- Missing values
- Duplicate entries
- Outliers
- Inconsistent formatting  
Cleaning is essential to ensure data quality and improve model performance.

### 4. Data Preprocessing  
Preprocessing may include:
- Encoding categorical variables
- Feature scaling (normalization/standardization)
- Handling imbalanced data
- Creating new features

### 5. Splitting Data  
Dividing data into training and testing sets to evaluate model generalization on unseen data.

---

## Example: Loading and Exploring the Titanic Dataset Using Pandas

```python
import pandas as pd

# Load dataset from URL
url = "https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv"
data = pd.read_csv(url)

# View first 5 rows
print(data.head())

# Check data info and missing values
print(data.info())
print(data.isnull().sum())

# Summary statistics
print(data.describe())

# Handling missing values (Example: Fill missing 'Age' with median)
data['Age'].fillna(data['Age'].median(), inplace=True)

# Drop irrelevant columns
data.drop(columns=['PassengerId', 'Name', 'Ticket', 'Cabin'], inplace=True)

# Encode categorical variables (Example: Sex and Embarked)
data['Sex'] = data['Sex'].map({'male': 0, 'female': 1})
data['Embarked'].fillna('S', inplace=True)
data = pd.get_dummies(data, columns=['Embarked'], drop_first=True)

print(data.head())
