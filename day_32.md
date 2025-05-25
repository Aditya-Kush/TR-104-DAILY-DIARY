# Date: 12 March 2025  
## T-Test and Z-Test in Data Science

---

### Overview  
Both t-tests and z-tests are statistical methods used to compare sample data against a population or between two samples to determine if there is a significant difference.

---

### When to Use Z-Test  
- Population variance (\( \sigma^2 \)) is known.  
- Sample size is large (usually \( n > 30 \)).  
- Data is approximately normally distributed.

---

### When to Use T-Test  
- Population variance is unknown.  
- Sample size is small (usually \( n \leq 30 \)).  
- Data is approximately normally distributed or sample size is small.

---

### Formulae  

- **Z-test statistic:**  
\[
Z = \frac{\bar{x} - \mu}{\sigma / \sqrt{n}}
\]  
where \( \bar{x} \) = sample mean, \( \mu \) = population mean, \( \sigma \) = population standard deviation, \( n \) = sample size.

- **T-test statistic:**  
\[
t = \frac{\bar{x} - \mu}{s / \sqrt{n}}
\]  
where \( s \) = sample standard deviation (used instead of population std).

---

### Types of T-Tests  
- **One-sample t-test:** Compare sample mean to known value.  
- **Independent two-sample t-test:** Compare means of two independent groups.  
- **Paired sample t-test:** Compare means of related groups (e.g., before and after treatment).

---

### Python Examples

```python
import numpy as np
from scipy import stats

# Sample data
sample_data = [12, 15, 14, 16, 13, 14, 15, 16, 14, 13]
population_mean = 14

# One-sample t-test
t_stat, p_val = stats.ttest_1samp(sample_data, population_mean)
print(f"T-test statistic: {t_stat:.3f}, p-value: {p_val:.3f}")

# Z-test (manual calculation)
sample_mean = np.mean(sample_data)
population_std = 2  # assumed known
n = len(sample_data)

z_stat = (sample_mean - population_mean) / (population_std / np.sqrt(n))
p_val_z = 2 * (1 - stats.norm.cdf(abs(z_stat)))  # two-tailed test
print(f"Z-test statistic: {z_stat:.3f}, p-value: {p_val_z:.3f}")
