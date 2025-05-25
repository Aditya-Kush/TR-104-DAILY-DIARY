# Date = 24 April 2025  
# EVALUATION METRICS: ACCURACY, PRECISION, RECALL, F1-SCORE & RMSE

Today, I focused on understanding five essential evaluation metrics used in both classification and regression problems: **Accuracy**, **Precision**, **Recall**, **F1-score**, and **RMSE**. These metrics help measure how well a machine learning model performs in making predictions.

---

## What Are Evaluation Metrics?

Evaluation metrics are used to **quantify the performance** of machine learning models. Depending on the problem type (classification or regression), different metrics are more suitable. A good understanding of these metrics helps in selecting and improving models.

---

## 1. Accuracy

**Accuracy** is the ratio of correct predictions to total predictions.


Where:
- TP: True Positives  
- TN: True Negatives  
- FP: False Positives  
- FN: False Negatives

> Best used when classes are **balanced**.

---

## 2. Precision

**Precision** tells us what proportion of predicted positives were actually correct.


> Useful when **false positives** are costly (e.g., spam detection).

---

## 3. Recall

**Recall** indicates how well the model identified all actual positives.


> Important when **false negatives** are dangerous (e.g., disease detection).

---

## 4. F1-Score

**F1-Score** is the harmonic mean of precision and recall.


> Useful when there's an **imbalance between classes** and you want a balance between precision and recall.

---

## 5. RMSE (Root Mean Squared Error)

**RMSE** is used in regression problems. It represents the square root of the average squared differences between predicted and actual values.


Where:
- yᵢ = actual value  
- ŷᵢ = predicted value  
- n = number of samples

> Lower RMSE indicates better model performance.

---

## Example in Python

```python
from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score, mean_squared_error
import numpy as np

# Classification example
y_true_cls = [1, 0, 1, 1, 0, 1, 0]
y_pred_cls = [1, 0, 1, 0, 0, 1, 1]

print("Accuracy:", accuracy_score(y_true_cls, y_pred_cls))
print("Precision:", precision_score(y_true_cls, y_pred_cls))
print("Recall:", recall_score(y_true_cls, y_pred_cls))
print("F1 Score:", f1_score(y_true_cls, y_pred_cls))

# Regression example
y_true
```

## Today, I learned about Accuracy, Precision, Recall, F1-Score, and RMSE — key metrics to evaluate classification and regression models. I explored when and why to use each, their formulas, and tested them with practical Python examples using scikit-learn. Understanding these metrics will help me better interpret and improve model performance.