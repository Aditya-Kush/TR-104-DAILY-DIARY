# Date = 21 April 2025  
# LOGISTIC REGRESSION — THEORY & IMPLEMENTATION  

Today, I focused on understanding **Logistic Regression**, a fundamental classification algorithm in machine learning. Unlike linear regression, logistic regression is used for **predicting categorical outcomes**, especially binary classes such as "yes/no", "spam/ham", "pass/fail".

---

## What is Logistic Regression?

Logistic Regression is a **supervised learning algorithm** used to predict the probability of a target variable. The output is typically a value between 0 and 1, representing the probability of belonging to a particular class.

Instead of fitting a straight line, logistic regression uses the **logistic (sigmoid) function** to squeeze the output of a linear equation into a probability range:


---

## Key Characteristics:

- Predicts **probability** and maps it to a **binary output** using a threshold (commonly 0.5)
- Can be extended to **multiclass classification** using "one-vs-rest" or "softmax" (multinomial logistic regression)

---

## Applications of Logistic Regression:

- Email spam detection  
- Disease diagnosis (e.g., diabetes, heart disease)  
- Credit scoring (loan approval)  
- Predicting customer churn  
- Binary sentiment analysis

---

## Evaluation Metrics for Classification:

- **Accuracy**: (TP + TN) / (TP + TN + FP + FN)  
- **Precision**: TP / (TP + FP)  
- **Recall**: TP / (TP + FN)  
- **F1-score**: Harmonic mean of precision and recall  
- **Confusion Matrix**: Table to visualize classification performance  
- **ROC Curve & AUC**: Measure of model's ability to distinguish classes

---

## Implementation in Python (Using scikit-learn)

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import classification_report, confusion_matrix

# Load sample dataset
from sklearn.datasets import load_breast_cancer
data = load_breast_cancer()
X = pd.DataFrame(data.data, columns=data.feature_names)
y = pd.Series(data.target)

# Train-test split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Model
model = LogisticRegression(max_iter=10000)
model.fit(X_train, y_train)

# Predictions
y_pred = model.predict(X_test)

# Evaluation
print("Confusion Matrix:")
print(confusion_matrix(y_test, y_pred))

print("\nClassification Report:")
print(classification_report(y_test, y_pred))
