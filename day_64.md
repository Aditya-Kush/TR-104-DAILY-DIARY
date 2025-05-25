# Date = 6 May 2025  
# PRINCIPAL COMPONENT ANALYSIS (PCA)

Today, I focused on understanding **Principal Component Analysis (PCA)**, a powerful dimensionality reduction technique widely used in data analysis and machine learning to simplify datasets with many features while retaining most of the variance.

---

## What is PCA?

PCA is an unsupervised linear transformation technique that converts a set of correlated variables into a smaller set of uncorrelated variables called **principal components**. These components capture the maximum variance in the data in descending order.

The goal of PCA is to reduce the dimensionality of data while preserving as much information (variance) as possible, which helps in visualization, noise reduction, and improving algorithm performance.

---

## Key Concepts:

- **Principal Components:** New axes that are linear combinations of original features.
- **Variance:** PCA seeks directions (components) that maximize the variance of the projected data.
- **Eigenvectors & Eigenvalues:** PCA finds eigenvectors (principal components) and eigenvalues (amount of variance explained) from the covariance matrix of the data.
- **Dimensionality Reduction:** By selecting the top *k* principal components, PCA reduces features from *n* to *k* while retaining most variance.

---

## Steps Involved in PCA:

1. **Standardize the Data:** Mean-center and scale features to have unit variance.
2. **Compute Covariance Matrix:** Calculate covariance matrix of standardized data.
3. **Calculate Eigenvalues and Eigenvectors:** Determine eigenvalues and eigenvectors of the covariance matrix.
4. **Sort Eigenvalues:** Sort eigenvalues in descending order and choose top *k* eigenvectors.
5. **Project Data:** Transform the original data onto the selected principal components.

---

## Why Use PCA?

- To reduce computational cost by lowering the number of features.
- To remove noise and redundant features.
- To visualize high-dimensional data in 2D or 3D.
- To improve performance of machine learning models by reducing overfitting.

---

## Python Implementation of PCA

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.decomposition import PCA
from sklearn.datasets import load_iris
from sklearn.preprocessing import StandardScaler

# Load dataset
iris = load_iris()
X = iris.data
y = iris.target

# Standardize the data
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# Initialize PCA to reduce to 2 components
pca = PCA(n_components=2)

# Fit and transform the data
X_pca = pca.fit_transform(X_scaled)

# Explained variance ratio
print("Explained variance ratio of each component:", pca.explained_variance_ratio_)

# Plot the PCA result
plt.figure(figsize=(8,6))
scatter = plt.scatter(X_pca[:, 0], X_pca[:, 1], c=y, cmap='viridis', edgecolor='k', s=50)
plt.xlabel('Principal Component 1')
plt.ylabel('Principal Component 2')
plt.title('PCA of Iris Dataset')
plt.legend(handles=scatter.legend_elements()[0], labels=iris.target_names)
plt.show()
