# Date = 8 May 2025  
# CROSS VALIDATION AND GRID SEARCH CV

Today, I focused on understanding **cross-validation**, a robust technique for model evaluation, and **Grid Search CV**, a powerful method for hyperparameter tuning combined with cross-validation.

---

## What is Cross-Validation?

Cross-validation is a technique used to assess how a machine learning model will generalize to an independent dataset. It helps prevent overfitting and gives a more reliable estimate of model performance than a simple train-test split.

---

## Common Types of Cross-Validation:

1. **K-Fold Cross-Validation:**  
   The dataset is divided into *k* subsets (folds). The model is trained on *k-1* folds and validated on the remaining fold. This process is repeated *k* times, and the average score is reported.

2. **Stratified K-Fold:**  
   Similar to k-fold but ensures that each fold preserves the percentage of samples for each class, useful for classification tasks with imbalanced data.

3. **Leave-One-Out Cross-Validation (LOOCV):**  
   Each sample is used once as a test while the rest form the training set. It is computationally expensive but very thorough.

---

## Why Use Cross-Validation?

- Provides a more accurate estimate of model performance on unseen data.
- Helps detect overfitting or underfitting.
- Makes efficient use of limited data by using all samples for training and testing.

---

## What is Grid Search CV?

Grid Search CV combines grid search and cross-validation to systematically explore combinations of hyperparameters and evaluate model performance using cross-validation.

---

## How Grid Search CV Works:

1. Define a set of hyperparameters and their possible values (a grid).  
2. For each combination of hyperparameters, perform cross-validation to evaluate model performance.  
3. Select the combination with the best average cross-validation score.  

This approach balances model tuning and validation to select the best model configuration.

---

## Python Example: Using GridSearchCV with K-Fold Cross-Validation on SVM

```python
from sklearn import datasets
from sklearn.svm import SVC
from sklearn.model_selection import GridSearchCV, StratifiedKFold
from sklearn.metrics import accuracy_score
from sklearn.model_selection import train_test_split

# Load dataset
iris = datasets.load_iris()
X, y = iris.data, iris.target

# Split data into train and test
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Define model
svm = SVC()

# Define hyperparameter grid
param_grid = {
    'C': [0.1, 1, 10],
    'kernel': ['linear', 'rbf'],
    'gamma': ['scale', 'auto']
}

# Define Stratified K-Fold cross-validator
cv = StratifiedKFold(n_splits=5, shuffle=True, random_state=42)

# Initialize GridSearchCV
grid_search = GridSearchCV(estimator=svm, param_grid=param_grid, cv=cv, scoring='accuracy', n_jobs=-1)

# Fit GridSearchCV
grid_search.fit(X_train, y_train)

# Print best parameters and best score
print("Best Hyperparameters:", grid_search.best_params_)
print("Best Cross-validation Accuracy:", grid_search.best_score_)

# Test set prediction and evaluation
y_pred = grid_search.predict(X_test)
print("Test Set Accuracy:", accuracy_score(y_test, y_pred))
