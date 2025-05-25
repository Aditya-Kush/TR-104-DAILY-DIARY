# Date = 29 April 2025  
# K-NEAREST NEIGHBORS (KNN) ALGORITHM

Today, I studied the **K-Nearest Neighbors (KNN)** algorithm, a simple yet effective supervised learning method used for **classification** and **regression**. KNN is an instance-based learning technique that classifies data based on the majority vote of its **k nearest neighbors**. It does not involve any explicit training phase, making it a **lazy learner**.

---

## What is K-Nearest Neighbors (KNN)?

**KNN** is a **non-parametric**, **lazy learning** algorithm. It makes predictions for a new instance by looking at the **‘k’ most similar training examples** (neighbors) and taking a **majority vote** (for classification) or **average** (for regression).

---

## How Does KNN Work?

1. **Choose the value of K** (e.g., 3, 5, 7).  
2. **Calculate the distance** between the test point and all training data points using a distance metric (commonly Euclidean distance).
3. **Select the K nearest data points** (neighbors).
4. **Vote or Average**:
   - **Classification**: The most common class among the K neighbors is selected.
   - **Regression**: The mean (or median) of the K neighbors is the predicted value.

---

## Distance Metrics:

- **Euclidean Distance** (default):
  \[
  d(p, q) = \sqrt{(p_1 - q_1)^2 + (p_2 - q_2)^2 + \ldots + (p_n - q_n)^2}
  \]

- **Manhattan Distance**  
- **Minkowski Distance**

---

## Advantages of KNN:

- Simple to understand and implement  
- No training phase (fast for small datasets)  
- Naturally handles multi-class problems  
- Works well with smaller datasets

---

## Disadvantages of KNN:

- Slow prediction time for large datasets  
- Sensitive to irrelevant features and feature scaling  
- Requires selection of optimal ‘K’  
- Affected by imbalanced data

---

## Python Implementation – KNN Classifier

```python
from sklearn.datasets import load_iris
from sklearn.neighbors import KNeighborsClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import classification_report, accuracy_score

# Load data
iris = load_iris()
X = iris.data
y = iris.target

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Initialize model
knn = KNeighborsClassifier(n_neighbors=5)

# Train model
knn.fit(X_train, y_train)

# Predict
y_pred = knn.predict(X_test)

# Evaluate
print("Accuracy:", accuracy_score(y_test, y_pred))
print("Classification Report:\n", classification_report(y_test, y_pred))
