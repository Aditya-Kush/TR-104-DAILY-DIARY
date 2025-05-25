# Date = 30 Apr 2025  
# NAIVE BAYES ALGORITHM

Today, I focused on the **Naive Bayes** algorithm, which is a probabilistic classifier based on **Bayes’ Theorem** with the **naive assumption** of conditional independence between features. Naive Bayes is particularly effective for text classification problems such as spam detection, sentiment analysis, and document categorization. I also implemented the algorithm using Python’s scikit-learn library.

---

## What is Naive Bayes?

**Naive Bayes** is a family of simple probabilistic algorithms that apply **Bayes’ Theorem** for classification tasks. The “naive” part refers to the assumption that features are **independent** given the class label — which rarely holds true in real-world data, but still often leads to good performance.

---

## Bayes’ Theorem:

\[
P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}
\]

Where:
- \( P(A|B) \): Posterior probability of class A given predictor B  
- \( P(B|A) \): Likelihood of predictor B given class A  
- \( P(A) \): Prior probability of class A  
- \( P(B) \): Prior probability of predictor B

---

## Types of Naive Bayes Classifiers:

1. **Gaussian Naive Bayes** – assumes features follow a normal distribution  
2. **Multinomial Naive Bayes** – typically used for text classification with word counts  
3. **Bernoulli Naive Bayes** – used with binary/boolean features

---

## Advantages of Naive Bayes:

- Simple and fast  
- Works well with high-dimensional data  
- Requires a small amount of training data  
- Performs well for text classification problems  
- Not prone to overfitting

---

## Disadvantages of Naive Bayes:

- Assumes feature independence (rare in real data)  
- Not suitable when features are highly correlated  
- Less flexible compared to more complex models

---

## Python Implementation – Gaussian Naive Bayes

```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.naive_bayes import GaussianNB
from sklearn.metrics import accuracy_score, classification_report

# Load dataset
iris = load_iris()
X = iris.data
y = iris.target

# Split dataset
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Initialize the model
model = GaussianNB()

# Train the model
model.fit(X_train, y_train)

# Predict
y_pred = model.predict(X_test)

# Evaluate
print("Accuracy:", accuracy_score(y_test, y_pred))
print("Classification Report:\n", classification_report(y_test, y_pred))
