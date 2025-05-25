# Date = 1 April 2025
# PYTHON LIBRARIES
The goal of Day was on understanding how to use "Scikit-learn", A popular library for machine learning in Python. Scikit-learn provides efficient tools for classification, regression, clustering and more. In this session, I covered how to use the library for regression tasks like predicting stock prices (which is going to be my project at th end of this Training).

---

# Introduction to Scikit-Learn
Scikit-learn(often abbreviated as sklearn) is a powerful Python library for machine learning. It provides simple and efficient tools for data mining and data analysis, built on top of NumPy, SciPy and Matplotlib. Scikit-learn offers a wide range of machine learning algorithms for classification, regression, clustering, and dimensionality reduction. It also includes tools for model evaluation, feature selection, data preprocessing, and model validation, making it a comprehensive library for machine learning tasks. Scikit-learn is known for its ease of use, excellent documentation, and a strong community, making it a popular choice for both beginners and experts in machine learning.

---

## What is Scikit-Learn
Scikit-learn is a popular open-source Python library for machine learning, built on top of NumPy, SciPy, and matplotlib. It provides easy-to-use tools for building and evaluating machine learning models, including both supervised (e.g., regression, classification) and unsupervised (e.g., clustering, dimensionality reduction) algorithms. With features for data preprocessing, model selection, and hyperparameter tuning, Scikit-learn is widely used for data analysis, machine learning, and predictive modeling. Its simple API, extensive documentation, and integration with other Python libraries make it a go-to tool for both beginners and experts in machine learning.

---

## Why We Use Scikit-learn?

1. Wide Range of Algorithms: Scikit-learn provides a rich set of machine learning algorithms, including classification (e.g., SVM, Random Forest), regression (e.g. Linear Regression), clustering (e.g., K-Means) and dimensionality reduction (e.g., PCA), all in one library.

2. Ease of Use: Its API is user-friendly and consistent, with most functions following the same pattern, making it easy to learn and use, even for beginners in machine learning.

3. Preprocessing and Feature Engineering: Scikit-learn includes numerous tools for preprocessing data, such as scaling, normalization, encoding, and imputation, which are essential for preparing data for machine learning models.

4. Model Evaluation and Selection: It offers comprehensive methods for evaluating model performance, including cross-validation, grid search for hyperparameter tuning, and various metrics (e.g., accuracy, precision, recall, F1-score).

5. Integration with Other Libraries: Scikit-learn integrates seamlessly with other Python libraries like Pandas, NumPy and Matplotlib making it a central part of the Python data science and machine learning ecosystem.

---

### What Scikit-learn Does?

1. Supervised Learning: It provides implementations for supervised learning tasks such as classification (e.g., K-Nearest Neighbors, Logistic Regression) and regression (e.g., Decision Trees, Linear Regression) to predict outcomes from labeled data.

2. Unsupervised Learning: Scikit-learn also supports unsupervised learning tasks like clustering (e.g., K-Means) and dimensionality reduction (e.g. PCA) for finding patterns or reducing the complexity of the data.

3. Data Preprocessing: It offers tools for data cleaning and transformation, such as scaling, encoding categorical variables, handling missing values, and splitting datasets into training and testing sets.

4. Model Tuning: It allows for hyperparameter tuning using GridSearchCV and RandomizedSearchCV, helping you optimize model performance by testing multiple combinations of parameters.

5. Model Evaluation: Scikit-learn provides a wide range of evaluation metrics like accuracy, confusion matrix, ROC-AUC, and more, as well as cross-validation to ensure that your model generalizes well to new, unseen data.

---


## Installation of Scikit-Learn 
For most users the best approach is to install the binary version of scikit-learn using an official release from pypi.org the Python Package Index. You can do so with the following steps:

1. Scikit-learn requires Python 3.6+. To check which version of Python you have installed, run the following command:   
    python3 --version
The output should be similar to:
Python 3.8.2

2. If you have a valid Python version you can run the following command to download and install a pre-built binary of scikit-learn:
    pip install scikit-learn

The following dependencies will be automatically installed along with scikit-learn:
NumPy 1.13.3+
SciPy 0.19.1+
Joblib 0.11+
threadpoolctl 2.0.0+

3. Alternatively, if you already have scikit-learn and/or any of its dependencies are already installed, they can be updated as part of the installation by running the following command:
pip install -U scikit-learn

4. You can verify your Scikit-learn installation with the following command:
python -m pip show scikit-learn


## One Simple program for Scikit Learn Loading Dataset

```python

from sklearn import datasets
# Load data
iris= datasets.load_iris()
# Print shape of data to confirm data is loaded
print(iris.data.shape)

```

## One program for Scikit-Learn SVM - learning and Predciting

```python

from sklearn import svm
from sklearn import datasets
# Load dataset
iris = datasets.load_iris()
clf = svm.LinearSVC()
# learn from the data
clf.fit(iris.data, iris.target)
# predict for unseen data
clf.predict([[ 5.0,  3.6,  1.3,  0.25]])
# Parameters of model can be changed by using the attributes ending with an underscore
print(clf.coef_ )

```

## Today's Learning Summary:
Today, I learned about Scikit-learn, A Python library for machine learning that provides easy-to-use tools for Classification, Regression, Clustering and dimensionality reduction. It simplifies data preprocessing, model evaluation and hyperparameter tuning. It integrates well with libraries like NumPy and Pandas. I also learned how to install Scikit-learn and implement basic tasks like loading datasets and running a Support Vector Machine (SVM) model for classification.