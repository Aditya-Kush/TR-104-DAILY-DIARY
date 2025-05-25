# Date = 21 April 2025  
# LINEAR REGRESSION — THEORY & IMPLEMENTATION  

Today, I focused on understanding **Linear Regression**, one of the most fundamental algorithms in machine learning and statistics. I studied both the theoretical background and implemented basic linear regression model using Python and the `scikit-learn` library.

---

## What is Linear Regression?

Linear regression is a **supervised learning** algorithm used for **predicting a continuous dependent variable** based on one or more independent variables. It finds the best-fitting straight line (regression line) through the data points.

The general equation for a **simple linear regression** (with one feature) is:


Where:  
- `y` = dependent/target variable  
- `x` = independent/input variable  
- `β₀` = intercept  
- `β₁` = slope (coefficient)  
- `ε` = error term (residual)

---

## Types of Linear Regression:

1. **Simple Linear Regression**: One independent variable  
2. **Multiple Linear Regression**: More than one independent variable  
3. **Polynomial Regression**: Linear regression on higher-degree polynomial features  
4. **Ridge, Lasso Regression**: Variants with regularization to reduce overfitting

---

## Assumptions of Linear Regression:

1. **Linearity**: Relationship between X and y is linear  
2. **Independence**: Observations are independent of each other  
3. **Homoscedasticity**: Constant variance of error terms  
4. **Normality**: Errors are normally distributed  
5. **No multicollinearity** (for multiple linear regression)

---

## Advantages of Linear Regression

- Easy to understand and implement  
- Fast to train and interpret  
- Good baseline for regression problems  
- Works well for linearly correlated data

---

## Limitations

- Not suitable for non-linear data  
- Sensitive to outliers  
- Assumes constant variance and independence  
- Can overfit if the model is too complex without regularization

---

## Implementation in Python (Using scikit-learn)

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error, r2_score

# Sample synthetic data
np.random.seed(42)
X = 2 * np.random.rand(100, 1)
y = 4 + 3 * X + np.random.randn(100, 1)

# Split into training and testing data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create and train the model
model = LinearRegression()
model.fit(X_train, y_train)

# Predict
y_pred = model.predict(X_test)

# Model coefficients
print("Intercept:", model.intercept_)
print("Coefficient:", model.coef_)

# Evaluation
print("Mean Squared Error:", mean_squared_error(y_test, y_pred))
print("R-squared:", r2_score(y_test, y_pred))

# Plotting the regression line
plt.scatter(X_test, y_test, color='blue', label='Actual')
plt.plot(X_test, y_pred, color='red', linewidth=2, label='Predicted')
plt.xlabel('X')
plt.ylabel('y')
plt.title('Linear Regression Example')
plt.legend()
plt.grid(True)
plt.show()
