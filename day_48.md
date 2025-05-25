# Date = 14 April 2025
# 1.2 TYPES OF SUPERVISED LEARNING (REGRESSION)
Today I focused on Second type of Supervised Learning i.e Regresssion with its some popular Algorithms.
The goal of Day was to delve into Regression, a type of supervised learning where the model is trained to predict continuous numerical values based on input features. In regression tasks, The algorithm learns the relationship between the independent variables (features) and a continuous dependent variable (output) by minimizing the error between predicted and actual values. By the end of this session, I was able to understand how regression algorithms such as Linear Regression and Decision Tree work to make accurate numerical predictions. I also gain insights into how to evaluate the performance of regression models using metrics like Mean Squared Error (MSE) and R² Score and how to interpret the relationships between variables.



## Types of Supervised Learning

In supervised learning, The problems are primarily categorized into two main types based on the nature of the target variable (output). 
These are *Classification* and *Regression* Problems. Each type involves a different type of prediction task and the choice of algorithm depends on the problem you're solving.

---


## 2. Regression Problems:
While classification deals with predicting categorical outputs (like "spam" or "not spam"), regression focuses on predicting continuous numeric values based on the input features.
A regression problem in supervised learning involves predicting a numeric outcome (a continuous value) from one or more input features. The goal is to model the relationship between the independent variables (features) and the dependent variable (target) so that the model can predict future or unseen values accurately.

---

## Key Characteristics of Regression Problems:

### Output: 
A continuous value (e.g., predicting house prices, stock prices etc.).

### Goal:
Predict the numeric value of the target variable based on the input features. Unlike classification, which predicts categories, regression predicts quantities.


### Example Applications:

1. House Price Prediction: Predict the price of a house based on its features like size, number of bedrooms, location, etc.
2. Stock Price Forecasting: Predict the future price of a stock based on historical data.
3. alary Prediction: Predict a person's salary based on factors like experience, education, job role, etc.
4. Temperature Forecasting: Predict the future temperature in a city based on historical weather data.

---

# Popular Regression Algorithms:

## 1. Linear Regression:
Linear Regression is the simplest and most commonly used regression algorithm. It models the relationship between the input variables (independent variables) and the target variable (dependent variable) as a linear equation. The idea is to find the best-fitting line that minimizes the error between the predicted and actual values.

### Key Steps:

1. Hypothesis: First it tests for the hypothesis. 
2. Objective: The objective of Linear Regression is to minimize the error (usually measured by Mean Squared Error) between the predicted and actual target values.
3. Training: The model is trained using a method called Ordinary Least Squares (OLS) to find the optimal weights for the features.
4. Prediction: After training, new data points can be fed into the model to predict the continuous target variable.

---

### Program of Linear Regresssion in Python using scikit-learn:

```python

# Import necessary libraries
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.datasets import make_regression
from sklearn.metrics import mean_squared_error

# Generate a synthetic dataset for regression
X, y = make_regression(n_samples=1000, n_features=3, noise=10, random_state=42)

# Split the dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Initialize the Linear Regression model
model = LinearRegression()

# Train the model on the training data
model.fit(X_train, y_train)

# Make predictions on the test set
y_pred = model.predict(X_test)

# Calculate the Mean Squared Error (MSE)
mse = mean_squared_error(y_test, y_pred)

# Output the MSE
print(f"Mean Squared Error of Linear Regression model: {mse:.2f}")


```

---

## 3. Decision Trees for Regression:
A Decision Tree can also be used for regression tasks. In this case, The algorithm builds a tree-like model to predict continuous values. Each internal node represents a decision based on one feature, and the leaves represent the predicted target values.

### Working of Decision Trees for Regression:
1. Feature Splitting: The algorithm selects features that minimize the variance within each group. The best feature is chosen at each node to split the data.

2. Stopping Criteria: The splitting process continues until a stopping criterion is met such as reaching the maximum depth of the tree or the minimum number of samples in a node.

3. Prediction: Once the tree is built, predictions are made by traversing the tree from the root to the leaves, and returning the average of the target values in the leaf node.

---

## Python Implementation of Decision Tree Regression Using scikit-learn:

```python

# Import necessary libraries
from sklearn.tree import DecisionTreeRegressor
from sklearn.metrics import mean_squared_error

# Generate synthetic dataset for Decision Tree Regression
X, y = make_regression(n_samples=1000, n_features=1, noise=10, random_state=42)

# Split the dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Initialize the Decision Tree Regressor model
model = DecisionTreeRegressor(random_state=42)

# Train the model on the training data
model.fit(X_train, y_train)

# Make predictions on the test set
y_pred = model.predict(X_test)

# Calculate the Mean Squared Error (MSE)
mse = mean_squared_error(y_test, y_pred)

# Output the MSE
print(f"Mean Squared Error of Decision Tree Regression model: {mse:.2f}")


```

---

## Today’s Learning Summary:
Today, I learned about Regression problems in supervised learning. Unlike Classification, where the output is categorical, Regression problems involve predicting continuous values. The most popular regression algorithms include Linear Regression and Decision Trees for Regression. Each algorithm has its strengths and weaknesses and choosing the right one depends on the specific characteristics of the dataset and the problem you're solving.
This concludes my learning for today. I am now more confident in understanding how to apply regression algorithms to real-world datasets and make continuous predictions.