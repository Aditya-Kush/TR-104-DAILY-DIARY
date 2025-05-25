# Date = 25 April 2025  
# DECISION TREE ALGORITHM

Today, I focused on learning the **Decision Tree** algorithm — a widely used supervised learning technique for both **classification and regression** tasks. The goal was to understand how decision trees make predictions by recursively splitting the dataset based on feature values. I studied its structure, working principles, advantages, and limitations, and practiced implementing the model in Python using `scikit-learn`.

---

## What is a Decision Tree?

A **Decision Tree** is a flowchart-like structure where:
- Each **internal node** represents a decision based on a feature,
- Each **branch** represents the outcome of that decision,
- Each **leaf node** represents a final output (class label or continuous value).

It is **non-parametric**, easy to interpret, and does not require feature scaling.

---

## Types of Problems Solved by Decision Trees:
- **Classification**: Predicting discrete class labels (e.g., email spam detection).
- **Regression**: Predicting continuous numeric values (e.g., house price prediction).

---

## How Does a Decision Tree Work?

1. **Recursive Partitioning**:  
   The algorithm splits the dataset based on features that result in the highest information gain (classification) or least variance (regression).

2. **Splitting Criteria**:
   - **Gini Impurity** or **Entropy** for classification
   - **Mean Squared Error (MSE)** for regression

3. **Stopping Criteria**:
   - Maximum depth of the tree
   - Minimum number of samples in a node
   - No further improvement in split

4. **Prediction**:
   The model traverses the tree based on feature values of a new data point until it reaches a leaf node, which provides the prediction.

---

## Advantages of Decision Trees:
- Easy to interpret and visualize
- Handles both numerical and categorical data
- Requires minimal data preprocessing
- Works well with non-linear relationships

---

## Disadvantages of Decision Trees:
- Prone to overfitting on small datasets
- Can be unstable due to small variations in data
- Biased towards features with more levels

---

## Python Implementation – Decision Tree Classifier

```python
from sklearn.datasets import load_iris
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import classification_report

# Load dataset
iris = load_iris()
X = iris.data
y = iris.target

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Initialize model
model = DecisionTreeClassifier(criterion='gini', max_depth=3, random_state=42)

# Train model
model.fit(X_train, y_train)

# Predict
y_pred = model.predict(X_test)

# Evaluate
print(classification_report(y_test, y_pred))
