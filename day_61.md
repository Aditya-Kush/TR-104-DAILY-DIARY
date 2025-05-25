# Date = 1 May 2025  
# CLUSTERING

Today, I focused on understanding **Clustering**, an important technique in unsupervised learning. Unlike supervised learning, clustering does not use labeled data. Instead, it aims to group similar data points into clusters based on their inherent characteristics or features.

---

## What is Clustering?

Clustering is the task of dividing a dataset into groups (clusters) so that data points within the same cluster are more similar to each other than to those in other clusters. It helps in discovering natural groupings or patterns in data without prior knowledge of labels.

---

## Key Concepts:

- **Cluster**: A group of data points that are similar to each other based on certain distance or similarity measures.  
- **Centroid**: The center point of a cluster (often used in algorithms like K-Means).  
- **Distance Metrics**: Methods to measure similarity or dissimilarity, such as Euclidean distance, Manhattan distance, or cosine similarity.  
- **Number of Clusters (k)**: The user-defined or algorithm-determined number of groups to form.

---

## Popular Clustering Algorithms:

1. **K-Means Clustering**  
   - Partitions data into *k* clusters.  
   - Iteratively assigns points to nearest centroid and recalculates centroids until convergence.  
   - Simple and efficient but requires predefining *k*.  

2. **Hierarchical Clustering**  
   - Builds a tree (dendrogram) of clusters either by agglomerative (bottom-up) or divisive (top-down) approaches.  
   - Does not require specifying the number of clusters upfront.  

3. **DBSCAN (Density-Based Spatial Clustering of Applications with Noise)**  
   - Groups together points that are closely packed and marks points in low-density regions as noise/outliers.  
   - Effective for arbitrary-shaped clusters and handling noise.

---

## Applications of Clustering:

- Customer segmentation in marketing  
- Image segmentation in computer vision  
- Document grouping in text mining  
- Anomaly detection in fraud detection  

---

## Python Implementation of K-Means Clustering

```python
from sklearn.datasets import make_blobs
from sklearn.cluster import KMeans
import matplotlib.pyplot as plt

# Generate synthetic dataset with 3 clusters
X, y_true = make_blobs(n_samples=300, centers=3, cluster_std=0.60, random_state=0)

# Initialize KMeans with 3 clusters
kmeans = KMeans(n_clusters=3)

# Fit the model
kmeans.fit(X)

# Get cluster labels
y_kmeans = kmeans.predict(X)

# Plot the clusters
plt.scatter(X[:, 0], X[:, 1], c=y_kmeans, s=50, cmap='viridis')
plt.scatter(kmeans.cluster_centers_[:, 0], kmeans.cluster_centers_[:, 1], s=200, c='red', marker='X')
plt.title("K-Means Clustering")
plt.show()
