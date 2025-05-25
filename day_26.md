# Date: 4 March 2025  
## Understanding Standard Deviation in Data Science

---

### What is Standard Deviation?  
Standard deviation is a measure of the amount of variation or dispersion in a set of values. It tells us how spread out the data points are around the mean.

- A low standard deviation means data points tend to be close to the mean.  
- A high standard deviation indicates that data points are spread out over a wider range.

---

### Relationship Between Variance and Standard Deviation  
- Standard deviation is the **square root** of the variance.  
- While variance is expressed in squared units, standard deviation is in the same units as the original data, making it easier to interpret.

\[
\sigma = \sqrt{\sigma^2}
\]

where \( \sigma \) is the population standard deviation and \( \sigma^2 \) is the population variance.

---

### Formula for Standard Deviation  
For a dataset \( x_1, x_2, ..., x_n \) with mean \( \bar{x} \):

- **Population standard deviation:**  
\[
\sigma = \sqrt{\frac{1}{n} \sum_{i=1}^n (x_i - \mu)^2}
\]

- **Sample standard deviation:**  
\[
s = \sqrt{\frac{1}{n-1} \sum_{i=1}^n (x_i - \bar{x})^2}
\]

---

### Example  
Consider the dataset: `10, 12, 14, 16, 18`

1. Mean = 14  
2. Variance = 8 (from previous calculation)  
3. Standard Deviation = \( \sqrt{8} \approx 2.83 \)

---

### Standard Deviation in Python

```python
import numpy as np

data = [10, 12, 14, 16, 18]
std_dev = np.std(data)  # population standard deviation by default
print("Standard Deviation:", std_dev)
