# Date: 11 March 2025  
## Hypothesis Testing in Data Science

---

### What is Hypothesis Testing?  
Hypothesis testing is a statistical method used to make decisions or inferences about population parameters based on sample data. It tests an assumption (hypothesis) to determine whether there is enough evidence to reject it.

---

### Key Terms  
- **Null Hypothesis (\(H_0\))**: The default assumption that there is no effect or difference.  
- **Alternative Hypothesis (\(H_a\))**: The hypothesis that there is an effect or difference.  
- **Significance Level (\(\alpha\))**: The threshold probability for rejecting \(H_0\), commonly set at 0.05.  
- **p-value**: The probability of observing the test statistic or something more extreme if \(H_0\) is true.  
- **Test Statistic**: A standardized value calculated from sample data used to decide whether to reject \(H_0\).

---

### Steps in Hypothesis Testing  
1. Formulate \(H_0\) and \(H_a\).  
2. Choose significance level \(\alpha\).  
3. Calculate the test statistic from sample data.  
4. Find the p-value corresponding to the test statistic.  
5. Compare p-value to \(\alpha\):  
   - If \( p \leq \alpha \), reject \(H_0\).  
   - If \( p > \alpha \), fail to reject \(H_0\).

---

### Types of Tests  
- **Z-test:** For large samples or known population variance.  
- **T-test:** For small samples with unknown population variance.  
- **Chi-square test:** For categorical data.  
- **ANOVA:** For comparing means of three or more groups.

---

### Example: One-sample t-test in Python

```python
import numpy as np
from scipy import stats

# Sample data
data = [12, 14, 15, 16, 14, 13, 15, 16, 14, 13]
population_mean = 14

# Perform one-sample t-test
t_stat, p_value = stats.ttest_1samp(data, population_mean)

print(f"T-statistic: {t_stat:.3f}")
print(f"P-value: {p_value:.3f}")

alpha = 0.05
if p_value < alpha:
    print("Reject the null hypothesis.")
else:
    print("Fail to reject the null hypothesis.")
