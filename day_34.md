# Date: 18 March 2025  
## Correlation and Covariance in Data Science

---

### What is Covariance?  
Covariance measures how two variables change together. It indicates the direction of the linear relationship between variables.

- **Positive covariance:** Variables increase or decrease together.  
- **Negative covariance:** One variable increases while the other decreases.  
- **Zero covariance:** No linear relationship.

---

### Covariance Formula

\[
\text{Cov}(X, Y) = \frac{1}{n-1} \sum_{i=1}^n (X_i - \bar{X})(Y_i - \bar{Y})
\]

where:  
- \(X_i, Y_i\) are individual data points  
- \(\bar{X}, \bar{Y}\) are means of \(X\) and \(Y\) respectively  
- \(n\) is the number of data points

---

### What is Correlation?  
Correlation quantifies both the strength and direction of the linear relationship between two variables. It is a standardized version of covariance, bounded between -1 and 1.

- **Correlation = +1:** Perfect positive linear relationship.  
- **Correlation = -1:** Perfect negative linear relationship.  
- **Correlation = 0:** No linear relationship.

---

### Correlation Coefficient (Pearson’s r) Formula

\[
r = \frac{\text{Cov}(X, Y)}{\sigma_X \sigma_Y}
\]

where \(\sigma_X, \sigma_Y\) are the standard deviations of \(X\) and \(Y\).

---

### Python Example: Calculating Covariance and Correlation

```python
import numpy as np

# Sample data
X = np.array([2, 4, 6, 8, 10])
Y = np.array([1, 3, 5, 7, 9])

# Covariance
cov_matrix = np.cov(X, Y)
cov_xy = cov_matrix[0, 1]
print(f"Covariance between X and Y: {cov_xy}")

# Correlation
corr_matrix = np.corrcoef(X, Y)
corr_xy = corr_matrix[0, 1]
print(f"Correlation between X and Y: {corr_xy}")
