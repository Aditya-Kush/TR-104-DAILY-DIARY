# Date = 13 May 2025  
# GAGGLE / UCI DATASET: DATA IMPORTS AND CLEANING

Today, I focused on importing datasets from popular sources like the Gaggle and UCI Machine Learning Repository, and performing initial data cleaning steps. These datasets are widely used in research and provide a variety of real-world problems to work on.

---

## About Gaggle and UCI Datasets

- **Gaggle**: A platform that provides access to various biological and biomedical datasets for data analysis.
- **UCI Machine Learning Repository**: One of the oldest and most popular repositories of datasets used for machine learning benchmarking and experimentation.

These datasets are usually provided in formats such as CSV, ARFF, or Excel, and require some preprocessing before analysis.

---

## Steps for Data Import and Cleaning

### 1. Importing Data

Datasets can be imported using libraries like `pandas` for CSV/Excel, or `scipy.io` for ARFF files.

Example: Loading a CSV dataset from UCI repository URL.

```python
import pandas as pd

# URL of UCI dataset (example: Wine dataset)
url = "https://archive.ics.uci.edu/ml/machine-learning-databases/wine/wine.data"

# Assign column names based on dataset documentation
columns = ['Class', 'Alcohol', 'Malic acid', 'Ash', 'Alcalinity of ash', 'Magnesium',
           'Total phenols', 'Flavanoids', 'Nonflavanoid phenols', 'Proanthocyanins',
           'Color intensity', 'Hue', 'OD280/OD315 of diluted wines', 'Proline']

# Load dataset
df = pd.read_csv(url, names=columns)

# Display first 5 rows
print(df.head())
