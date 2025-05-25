# Date = 11 April 2025
# 1.1 TYPES OF SUPERVISED LEARNING (CLASSIFICATION)
Today I focused on First type of Supervised Learning which is "Classification".
The goal of Day 10 was to delve into Supervised Learning, A type of machine learning where models are trained on labeled data to make predictions or classifications. In this type of learning, the algorithm learns the relationship between input features and the correct output labels by minimizing prediction errors during the training process. By the end of this session I was be able to understand how supervised learning algorithms like Logistic regression, Decision trees, K-nearest Neighbor and Neural networks work to make accurate predictions based on historical data.

---

## Types of Supervised Learning

In supervised learning, The problems are primarily categorized into two main types based on the nature of the target variable (output). 
These are *Classification* and *Regression* Problems. Each type involves a different type of prediction task and the choice of algorithm depends on the problem you're solving.

---

## 1. Classification Problems:
Classification is a type of supervised learning where the goal is to assign inputs (features) to one of several predefined categories or classes. The output variable in a classification problem is categorical meaning it represents a discrete label. The model learns to distinguish between different classes based on the features provided.

---

## Key Characteristics of Classification Problems:

### Output: 
A discrete label (e.g.email spam or not spam, disease or no disease etc.).

### Goal: 
Predict which class or category the input belongs to.

### Example Applications:

1. Email Spam Detection: Classify an email as "spam" or "not spam".
2. Image Classification: Classify an image as containing a dog, cat or bird.
3. Medical Diagnosis: Classify a patient’s medical condition as "healthy" or "sick" based on symptoms and medical tests.
4. Sentiment Analysis: Classify a review as "positive" or "negative".

---

# Popular Classification Algorithms:

## 1. Logistic Regression:
Logistic Regression is a linear model for binary classification problems. It predicts the probability that a given input belongs to one of two classes (0 or 1). The output is passed through the sigmoid function which squashes the result into a range between 0 and 1.

### Key Steps:
1. Model Training: Use gradient descent or other optimization algorithms to minimize the loss function (cross-entropy or log loss).

2. Prediction: After training, use the learned weights to make predictions. If the predicted probability is greater than 0.5, classify as 1, otherwise as 0.

---

### Program of Logistic Regresssion in Python using scikit-learn:

```python

# Import necessary libraries
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.datasets import make_classification
from sklearn.metrics import accuracy_score

# Create a synthetic dataset for binary classification
X, y = make_classification(n_samples=1000, n_features=5, n_classes=2, random_state=42)

# Split the dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Initialize the Logistic Regression model
model = LogisticRegression()

# Train the model on the training data
model.fit(X_train, y_train)

# Make predictions on the test set
y_pred = model.predict(X_test)

# Calculate accuracy
accuracy = accuracy_score(y_test, y_pred)

# Output the accuracy
print(f"Accuracy of Logistic Regression model: {accuracy * 100:.2f}%")


```

---


## 2. K-Nearest Neighbors (KNN): 
K-Nearest Neighbors Classifies data based on the majority class of its neighbors.
K-Nearest Neighbors (KNN) is a simple, non-parametricsupervised learning algorithm used for classification. In KNN, The class of a given data point is determined by the majority class among its K nearest neighbors. The distance between points is typically measured using Euclidean distance though other distance metrics can be used.

---

### Working of K-Nearest Neighbors:

1. Choose a value for K (the number of nearest neighbors).
2. Calculate the distance between the input point and all the training data points.
3. Identify the K closest neighbors to the input point.
4. The output is the most frequent class among those K neighbors (for classification problems).

---

## 3. Decision Trees: 
A Decision Tree is a supervised learning algorithm used for both classification and regression tasks. It works by breaking down a dataset into smaller subsets, while at the same time an associated decision tree is incrementally developed.
The final model is a tree-like structure where:
- Each internal node represents a "test" or "decision" on a feature (e.g., "Is Age > 30?").
- Each branch represents the outcome of that decision (e.g., "Yes" or "No").
- Each leaf node represents a final class label (in classification) or a continuous value (in regression).

---

### Working of Decision Tree:

1. Feature Selection: The algorithm selects the feature that best splits the data at each node. The criterion for selecting features often involves measures like Gini impurity (for classification) or Mean Squared Error (MSE) (for regression).

2. Recursive Splitting: The process of selecting the best feature to split the data is recursively applied to each resulting subset. This continues until the data is perfectly split or a stopping criterion (e.g. maximum depth of the tree, minimum samples at a node) is met.

3. Prediction: For classification, the majority class in the leaf node becomes the predicted class for new data points falling into that leaf. For regression, the predicted value is the average of the target values in the leaf node.

---

## Today's Learning Summary:
Today, I learned about Classification, a type of Supervised Learning where the algorithm is trained on labeled data to predict discrete categories or classes. The model learns from the features (input data) and labels (target categories) to predict the class of new and unseen data.