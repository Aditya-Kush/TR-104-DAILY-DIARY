# Date = 5 May 2025  
# K-MEANS AND HIERARCHICAL CLUSTERING

Today, I focused on two popular clustering algorithms: **K-Means** and **Hierarchical Clustering**. Both are widely used to group unlabeled data into meaningful clusters, but they differ in approach and use cases.

---

## K-Means Clustering

K-Means is a partition-based clustering method that aims to divide data into *k* clusters by minimizing the variance within each cluster.

### How K-Means Works:
1. Choose the number of clusters *k*.
2. Initialize *k* centroids randomly.
3. Assign each data point to the nearest centroid based on a distance metric (usually Euclidean distance).
4. Recalculate the centroids as the mean of all points assigned to that cluster.
5. Repeat steps 3 and 4 until convergence (no change in cluster assignments or centroids).

### Advantages:
- Simple and fast.
- Works well with large datasets.
- Efficient for spherical clusters.

### Disadvantages:
- Requires specifying *k* beforehand.
- Sensitive to initial centroid placement.
- Assumes clusters are convex shaped.

---

## Hierarchical Clustering

Hierarchical clustering builds a tree (dendrogram) of clusters by either merging smaller clusters (agglomerative) or splitting larger clusters (divisive).

### Types:
- **Agglomerative (Bottom-Up):** Start with each data point as its own cluster and iteratively merge the closest clusters.
- **Divisive (Top-Down):** Start with all points in one cluster and recursively split into smaller clusters.

### How Agglomerative Clustering Works:
1. Treat each data point as a single cluster.
2. Find the two closest clusters based on a linkage criterion (e.g., single, complete, average).
3. Merge these two clusters.
4. Repeat steps 2 and 3 until all points are in one cluster or a stopping condition is met.

### Advantages:
- Does not require specifying the number of clusters upfront.
- Produces a dendrogram to visualize cluster hierarchy.
- Can capture nested clusters and different shapes.

### Disadvantages:
- Computationally expensive for large datasets.
- Hard to undo decisions once clusters are merged.

---

## Python Implementation of K-Means Clustering

```python
from sklearn.datasets import make_blobs
from sklearn.cluster import KMeans
import matplotlib.pyplot as plt

# Generate synthetic data
X, y_true = make_blobs(n_samples=300, centers=4, cluster_std=0.70, random_state=42)

# Initialize KMeans
kmeans = KMeans(n_clusters=4, random_state=42)

# Fit and predict clusters
y_kmeans = kmeans.fit_predict(X)

# Plot the clusters and centroids
plt.scatter(X[:, 0], X[:, 1], c=y_kmeans, s=50, cmap='viridis')
plt.scatter(kmeans.cluster_centers_[:, 0], kmeans.cluster_centers_[:, 1], s=250, c='red', marker='X')
plt.title("K-Means Clustering")
plt.show()
