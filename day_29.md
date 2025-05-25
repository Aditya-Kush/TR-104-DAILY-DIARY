# Date: 7 March 2025  
## Poisson Distribution in Data Science

---

### What is Poisson Distribution?  
The Poisson distribution is a discrete probability distribution that expresses the probability of a given number of events occurring in a fixed interval of time or space, assuming these events occur with a known constant mean rate and independently of the time since the last event.

---

### When to Use Poisson Distribution?  
- Modeling count data (number of occurrences) over a fixed period or region.  
- Examples:  
  - Number of emails received in an hour.  
  - Number of customer arrivals at a store per day.  
  - Number of accidents at a traffic intersection per month.

---

### Poisson Probability Mass Function (PMF)

\[
P(X = k) = \frac{\lambda^k e^{-\lambda}}{k!}
\]

where:  
- \( k \) = number of events (0, 1, 2, ...)  
- \( \lambda \) = average number of events in the interval (mean)  
- \( e \) = Euler’s number (~2.71828)

---

### Key Properties  
- Mean and variance are both equal to \( \lambda \).  
- Suitable for rare events occurring independently.

---

### Example in Python

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import poisson

lambda_ = 3  # average number of events
k = np.arange(0, 10)

# Poisson PMF values
pmf = poisson.pmf(k, lambda_)

plt.bar(k, pmf)
plt.title('Poisson Distribution (λ=3)')
plt.xlabel('Number of Events (k)')
plt.ylabel('Probability')
plt.show()
