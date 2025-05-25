# Date = 2 May 2025  
# SUPPORT VECTOR MACHINE (SVM)

Today, I focused on the **Support Vector Machine (SVM)** algorithm, a powerful supervised learning technique used primarily for classification tasks but also applicable to regression. SVM aims to find the optimal boundary (hyperplane) that best separates classes in the feature space with the maximum margin.

---

## What is Support Vector Machine?

Support Vector Machine is a discriminative classifier formally defined by a separating hyperplane. Given labeled training data, the algorithm outputs an optimal hyperplane that categorizes new examples. Intuitively, SVM finds the decision boundary that maximizes the distance (margin) between the closest points (support vectors) of different classes.

---

## Key Concepts:

- **Hyperplane**: A decision boundary that separates different classes. In 2D, it’s a line; in higher dimensions, a plane or hyperplane.  
- **Margin**: The distance between the hyperplane and the nearest data points from each class. SVM maximizes this margin.  
- **Support Vectors**: Data points closest to the hyperplane which influence its position and orientation.  
- **Kernel Trick**: Technique to transform data into higher dimensions when data is not linearly separable, enabling SVM to find a separating hyperplane in that space. Common kernels include linear, polynomial, and radial basis function (RBF).

---

## How SVM Works:

1. For linearly separable data, SVM finds the hyperplane that maximizes the margin between two classes.  
2. For non-linearly separable data, SVM uses kernel functions to map input features into higher-dimensional space to find a linear separation.  
3. The optimization objective is to minimize classification error while maximizing the margin.

---

## Advantages of SVM:

- Effective in high dimensional spaces.  
- Works well with clear margin of separation.  
- Uses kernel trick to handle nonlinear data efficiently.  
- Robust against overfitting, especially in high-dimensional space.

---

## Disadvantages of SVM:

- Can be less effective on noisy data with overlapping classes.  
- Computationally intensive for large datasets.  
- Choosing the right kernel and tuning parameters (C, gamma) can be challenging.

---

## Python Implementation of SVM using scikit-learn

```python
from sklearn import datasets
from sklearn.model_selection import train_test_split
from sklearn.svm import SVC
from sklearn.metrics import accuracy_score, classification_report

# Load dataset
iris = datasets.load_iris()
X = iris.data
y = iris.target

# Split dataset
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Initialize SVM classifier with RBF kernel
model = SVC(kernel='rbf', gamma='scale')

# Train the model
model.fit(X_train, y_train)

# Predict on test data
y_pred = model.predict(X_test)

# Evaluate the model
print("Accuracy:", accuracy_score(y_test, y_pred))
print("Classification Report:\n", classification_report(y_test, y_pred))
