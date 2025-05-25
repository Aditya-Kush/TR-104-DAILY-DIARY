# Date = 28 April 2025  
# RANDOM FOREST ALGORITHM

Today, I explored the **Random Forest Algorithm**, which is an advanced ensemble learning method used for both **classification** and **regression** tasks. It builds multiple decision trees during training and combines their outputs to improve model performance and reduce overfitting. I learned how Random Forest improves accuracy, handles large datasets, and is robust to noise.

---

## What is a Random Forest?

A **Random Forest** is an ensemble method that constructs a "forest" of decision trees by training each on a random subset of the data and features. The final prediction is made by:
- **Majority voting** (classification)
- **Averaging** (regression)

It combines the simplicity of decision trees with the power of ensemble learning.

---

## How Does Random Forest Work?

1. **Bootstrap Aggregation (Bagging)**:  
   - Randomly selects samples from the training set **with replacement** to train each decision tree.

2. **Feature Randomness**:  
   - At each split in the tree, only a **random subset of features** is considered, increasing diversity among trees.

3. **Aggregation of Predictions**:
   - **Classification**: Uses **majority vote** from all trees.
   - **Regression**: Uses the **mean prediction** from all trees.

---

## Advantages of Random Forest:

- Reduces overfitting (compared to individual decision trees)
- Works well on large datasets with high dimensionality
- Robust to noise and missing values
- Handles both classification and regression
- No need for feature scaling

---

## Disadvantages of Random Forest:

- More computationally intensive
- Less interpretable than a single decision tree
- Can become slow with many trees

---

## Python Implementation – Random Forest Classifier

```python
from sklearn.ensemble import RandomForestClassifier
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, classification_report

# Load data
iris = load_iris()
X = iris.data
y = iris.target

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create model
model = RandomForestClassifier(n_estimators=100, random_state=42)

# Train model
model.fit(X_train, y_train)

# Predict
y_pred = model.predict(X_test)

# Evaluate
print("Accuracy:", accuracy_score(y_test, y_pred))
print("Classification Report:\n", classification_report(y_test, y_pred))
