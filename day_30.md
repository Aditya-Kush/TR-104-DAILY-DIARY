# Date: 10 March 2025  
## Sampling and the Central Limit Theorem (CLT)

---

### What is Sampling?  
Sampling is the process of selecting a subset of individuals, items, or data points from a larger population to make statistical inferences about the population.

---

### Types of Sampling Methods  
- **Simple Random Sampling:** Every member of the population has an equal chance of being selected.  
- **Stratified Sampling:** Population divided into strata (groups) and samples taken from each stratum.  
- **Systematic Sampling:** Selecting every \( k^{th} \) individual from a list.  
- **Cluster Sampling:** Dividing population into clusters and randomly selecting entire clusters.

---

### Importance of Sampling  
- Enables analysis without surveying the entire population.  
- Reduces cost and time.  
- Provides representative data for inference.

---

### Central Limit Theorem (CLT)  
The CLT states that, given a sufficiently large sample size, the distribution of the sample mean will approximate a normal distribution regardless of the original population's distribution, provided the samples are independent and identically distributed (i.i.d.).

---

### Why is CLT Important?  
- Justifies using the normal distribution in inferential statistics even when the population distribution is unknown.  
- Allows estimation of population parameters and construction of confidence intervals.  
- Supports hypothesis testing based on sample means.

---

### Illustration of CLT  
- If you take many samples of size \( n \) from any population, the distribution of their means tends to be normal as \( n \) increases.  
- The mean of the sampling distribution equals the population mean \( \mu \).  
- The standard deviation of the sampling distribution (standard error) is:  
\[
\sigma_{\bar{x}} = \frac{\sigma}{\sqrt{n}}
\]

---

### Example in Python

```python
import numpy as np
import matplotlib.pyplot as plt

# Population with a non-normal distribution (e.g., exponential)
population = np.random.exponential(scale=2, size=10000)

sample_means = []
sample_size = 50

# Take 1000 samples of size 50 and compute their means
for _ in range(1000):
    sample = np.random.choice(population, sample_size, replace=True)
    sample_means.append(np.mean(sample))

plt.hist(sample_means, bins=30, density=True, alpha=0.7, color='blue')
plt.title('Sampling Distribution of Sample Means (CLT)')
plt.xlabel('Sample Mean')
plt.ylabel('Frequency')
plt.show()
