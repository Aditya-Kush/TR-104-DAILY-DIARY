# Date = 23 April 2025  
# EVALUATION METRICS IN MACHINE LEARNING  

I focused on understanding the core **evaluation metrics** used in machine learning. These metrics are essential to assess how well a model performs and to compare different models for a given task. I explored metrics for both classification and regression tasks with definitions, uses, and examples.

---

## Key Concepts Covered:

1. **Accuracy** – Measures the overall correctness of a classification model.
2. **Precision** – Tells how many predicted positives are actually correct.
3. **Recall** – Indicates how well the model captures all actual positives.
4. **F1-Score** – Harmonic mean of precision and recall useful for imbalanced datasets.
5. **Confusion Matrix** – A matrix to visualize model performance for classification.
6. **MAE, MSE, RMSE** – Error-based metrics for regression tasks.
7. **R² Score** – Measures how well predictions approximate actual outcomes.

---

## What Are Evaluation Metrics?

Evaluation metrics are **quantitative measures** used to assess the performance of a machine learning model. They help answer the question:  
**"How well is my model doing?"**

Different types of problems require different metrics. For example, classification uses accuracy, precision, recall, while regression uses MAE, MSE, and R².

---

## Why Are Evaluation Metrics Important?

- They **quantify** a model's performance.
- Help in **comparing models** and choosing the best one.
- Crucial for **avoiding overfitting or underfitting**.
- Guide decisions like feature selection, tuning hyperparameters, and model choice.

---

## Types of Evaluation Metrics

### For Classification:

- **Accuracy**: Correct predictions out of total predictions.
- **Precision**: Relevant when false positives are costly (e.g. email spam).
- **Recall**: Important when false negatives are dangerous (e.g. medical diagnosis).
- **F1-Score**: Balances precision and recall.
- **Confusion Matrix**: Visual representation of prediction outcomes.

### For Regression:

- **MAE (Mean Absolute Error)**: Average of absolute differences between actual and predicted values.
- **MSE (Mean Squared Error)**: Average of squared differences.
- **RMSE (Root Mean Squared Error)**: Square root of MSE, interpretable in the same units.
- **R² Score (Coefficient of Determination)**: Represents explained variance by the model.

---

## Simple Example: Classification Metrics in Python

```python
from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score, confusion_matrix

y_true = [1, 0, 1, 1, 0, 1, 0]
y_pred = [1, 0, 1, 0, 0, 1, 1]

print("Accuracy:", accuracy_score(y_true, y_pred))
print("Precision:", precision_score(y_true, y_pred))
print("Recall:", recall_score(y_true, y_pred))
print("F1 Score:", f1_score(y_true, y_pred))
print("Confusion Matrix:\n", confusion_matrix(y_true, y_pred))
```

## Today, I learned that evaluation metrics are key to understanding a model's success in real-world scenarios. For classification, I explored accuracy, precision, recall, F1-score, and the confusion matrix. For regression, I studied MAE, MSE, RMSE, and R². These metrics will help me assess models more accurately in upcoming projects.
