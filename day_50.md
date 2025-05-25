# Date = 15 April 2025
# POPULAR UNSUPERVISED LEARNING ALGORITHMS
Today I focused on Popular Unsupervised Learning Algorithms (i.e Clustering and PCA).
The goal of today was to dive into Clustering and Principal Component Analysis (PCA), Two key techniques in Unsupervised Learning. In this approach, The algorithm works with unlabeled data to identify hidden patterns, groupings, or structures without predefined labels or categories.

---

## Introduction:
In this approach, The algorithm works with unlabeled data to identify hidden patterns, groupings or structures without predefined labels or categories.

1. Clustering: It focuses on grouping similar data points together with popular algorithms like K-Means and Hierarchical Clustering. These algorithms partition the data into clusters, where points in the same group are more similar to each other than to those in other groups.

2. Principal Component Analysis (PCA): It is used for dimensionality reduction means transforming high-dimensional data into a lower-dimensional space while retaining as much variance as possible. This technique helps in visualizing data, reducing computational complexity and highlighting the most important features of the data.


---


# Popular Unsupervised Learning Algorithms:

## 1. K-Means Clustering:
K-Means Clustering is one of the most widely used clustering algorithms in unsupervised learning. It aims to partition the dataset into a pre-defined number of clusters (K) where the data points within each cluster are as similar as possible and the data points in different clusters are as dissimilar as possible. The algorithm assigns each data point to the nearest cluster center (centroid) and then re-calculates the centroids iteratively.

### Key Steps:

1. Initialization: Randomly select K initial centroids from the data points.
2. Assignment: Assign each data point to the closest centroid.
3. Update Centroids: Calculate new centroids as the mean of the points assigned to each cluster.
4. Repeat: Continue the assignment and update steps until convergence (no further changes in centroids).

---


### Python Implementation of K-Means Clustering Using scikit-learn:

 ```python

# Import necessary libraries
import numpy as np
from sklearn.cluster import KMeans
from sklearn.datasets import make_blobs
import matplotlib.pyplot as plt

# Generate a synthetic dataset for clustering
X, y = make_blobs(n_samples=300, centers=4, cluster_std=0.60, random_state=42)

# Initialize the KMeans model with 4 clusters
kmeans = KMeans(n_clusters=4)

# Fit the model to the data
y_kmeans = kmeans.fit_predict(X)

# Plot the clusters and centroids
plt.scatter(X[:, 0], X[:, 1], c=y_kmeans, s=50, cmap='viridis')
centers = kmeans.cluster_centers_
plt.scatter(centers[:, 0], centers[:, 1], c='red', s=200, alpha=0.5)
plt.title("K-Means Clustering with 4 Clusters")
plt.show()

```

---

## 2. Hierarchical Clustering:
Hierarchical Clustering is another clustering technique that builds a tree-like structure (dendrogram) to represent the nested grouping of data points. The key difference from K-Means is that you don’t need to specify the number of clusters in advance. You can either use agglomerative (bottom-up) or divisive (top-down) methods for building the hierarchy.

---

### Working of Hierarchical Clustering:

1. Agglomerative Approach: Start with each data point as a single cluster and iteratively merge the closest clusters until there is only one cluster.

2. Divisive Approach: Start with one large cluster and iteratively split it into smaller clusters based on dissimilarity.
Dendrogram: The results can be represented in a tree-like structure (dendrogram) where the branches show the hierarchy of merging or splitting clusters.

---

### Python Implementation of Hierarchical Clustering Using scikit-learn:

```python

# Import necessary libraries
from sklearn.cluster import AgglomerativeClustering
import matplotlib.pyplot as plt
from sklearn.datasets import make_blobs

# Generate synthetic data for clustering
X, y = make_blobs(n_samples=300, centers=3, cluster_std=0.60, random_state=42)

# Initialize Agglomerative Clustering model
model = AgglomerativeClustering(n_clusters=3)

# Fit the model and predict the clusters
y_pred = model.fit_predict(X)

# Plot the clusters
plt.scatter(X[:, 0], X[:, 1], c=y_pred, s=50, cmap='viridis')
plt.title("Hierarchical Clustering with 3 Clusters")
plt.show()

```

## 3. Principal Component Analysis (PCA):
PCA is a dimensionality reduction technique often used to reduce the number of features in a dataset while retaining as much variance (information) as possible. PCA transforms the data into a new set of orthogonal axes called principal components that capture the most important patterns in the data.

---

### Key Steps:

1. Standardization: Normalize the features by centering the data around zero and scaling it.
2. Covariance Matrix: Calculate the covariance matrix to understand how features relate to each other.
3. Eigenvalue Decomposition: Compute the eigenvalues and eigenvectors of the covariance matrix to identify the principal components.
4. Projection: Project the data onto the principal components to reduce its dimensionality.

---

### Python Implementation of PCA Using scikit-learn:

```python

# Import necessary libraries
from sklearn.decomposition import PCA
from sklearn.datasets import make_blobs
import matplotlib.pyplot as plt

# Generate synthetic data for PCA
X, y = make_blobs(n_samples=300, centers=2, random_state=42)

# Initialize PCA with 2 components (reduce to 2D)
pca = PCA(n_components=2)

# Fit and transform the data to reduce its dimensionality
X_pca = pca.fit_transform(X)

# Plot the reduced data
plt.scatter(X_pca[:, 0], X_pca[:, 1], c=y, cmap='viridis', s=50)
plt.title("PCA for Dimensionality Reduction")
plt.xlabel("Principal Component 1")
plt.ylabel("Principal Component 2")
plt.show()

```

---

## Today’s Learning Summary:
So today, I learned that Unsupervised Learning is a powerful machine learning paradigm that enables algorithms to discover hidden patterns, relationships and structures in data without the need for labeled examples. This approach is particularly useful when working with large and unlabeled datasets as it can uncover insights and groupings that may not be immediately apparent.