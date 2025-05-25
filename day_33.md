# Date: 17 March 2025  
## Understanding P-values and Additional Key Concepts in Data Science

---

### What is a P-value?  
The p-value is the probability of obtaining results at least as extreme as the observed results of a statistical test, assuming that the null hypothesis \( H_0 \) is true.

- **Low p-value (≤ α):** Strong evidence against \( H_0 \), so reject \( H_0 \).  
- **High p-value (> α):** Weak evidence against \( H_0 \), so fail to reject \( H_0 \).

---

### Importance of P-values  
- Helps quantify the strength of evidence against the null hypothesis.  
- Used to decide whether the observed data is statistically significant.  
- Should be interpreted alongside effect size and confidence intervals for full context.

---

### Common Misconceptions  
- A p-value is NOT the probability that the null hypothesis is true.  
- A p-value does NOT measure the size or importance of an effect.  
- Statistical significance does NOT imply practical significance.

---

### Additional Concepts to Know  

#### 1. **Type I and Type II Errors**  
- **Type I Error (\(\alpha\))**: Rejecting the null hypothesis when it is true (false positive).  
- **Type II Error (\(\beta\))**: Failing to reject the null hypothesis when it is false (false negative).  

---

#### 2. **Effect Size**  
- A quantitative measure of the magnitude of the experimental effect.  
- Complements p-values by showing practical significance.

---

#### 3. **Confidence Intervals (CI)**  
- A range of values within which the true population parameter is expected to lie, with a certain level of confidence (e.g., 95%).  
- Provides more information than a simple hypothesis test.

---

### P-value Example in Python

```python
from scipy import stats
import numpy as np

# Sample data
data = np.array([12, 14, 15, 16, 14, 13, 15, 16, 14, 13])
population_mean = 14

# Perform one-sample t-test
t_stat, p_val = stats.ttest_1samp(data, population_mean)

print(f"T-statistic: {t_stat:.3f}")
print(f"P-value: {p_val:.3f}")

alpha = 0.05
if p_val < alpha:
    print("Reject the null hypothesis (statistically significant).")
else:
    print("Fail to reject the null hypothesis (not statistically significant).")
