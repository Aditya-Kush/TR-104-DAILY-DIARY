# Date: 24 March 2025  
## Pearson and Spearman Correlation Coefficients

---

### Pearson Correlation Coefficient  
- Measures the **linear** relationship between two continuous variables.  
- Values range from -1 to 1.  
  - +1 indicates a perfect positive linear correlation.  
  - -1 indicates a perfect negative linear correlation.  
  - 0 indicates no linear correlation.  
- Assumes variables are normally distributed and have a linear relationship.

---

### Pearson Correlation Formula

\[
r = \frac{\sum (X_i - \bar{X})(Y_i - \bar{Y})}{\sqrt{\sum (X_i - \bar{X})^2 \sum (Y_i - \bar{Y})^2}}
\]

---

### Spearman Correlation Coefficient  
- Measures the **monotonic** relationship (whether linear or not) between two variables using their ranks.  
- Values range from -1 to 1, similar to Pearson.  
- Non-parametric and does **not** assume normal distribution.  
- Useful when data is ordinal or not normally distributed.


---

### Python Example: Calculating Pearson and Spearman Correlations

```python
import numpy as np
from scipy.stats import pearsonr, spearmanr

# Sample data
X = [10, 20, 30, 40, 50]
Y = [12, 24, 33, 48, 52]

# Pearson correlation
pearson_corr, pearson_p = pearsonr(X, Y)
print(f"Pearson correlation: {pearson_corr:.3f}, p-value: {pearson_p:.3f}")

# Spearman correlation
spearman_corr, spearman_p = spearmanr(X, Y)
print(f"Spearman correlation: {spearman_corr:.3f}, p-value: {spearman_p:.3f}")
