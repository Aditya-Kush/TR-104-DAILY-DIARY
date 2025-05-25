# Date: 5 March 2025  
## Basics of Probability in Data Science

---

### What is Probability?  
Probability measures the likelihood or chance that a particular event will occur. It is a value between 0 and 1, where:  
- 0 means the event will never happen.  
- 1 means the event will always happen.

---

### Key Concepts  
- **Experiment:** An action or process that leads to one or more outcomes (e.g., rolling a dice).  
- **Sample Space (S):** The set of all possible outcomes. For a dice roll, \( S = \{1, 2, 3, 4, 5, 6\} \).  
- **Event (E):** A subset of the sample space, e.g., rolling an even number \( E = \{2, 4, 6\} \).

---

### Probability Formula  
\[
P(E) = \frac{\text{Number of favorable outcomes}}{\text{Total number of outcomes in the sample space}}
\]

---

### Types of Probability  
- **Theoretical Probability:** Based on known possible outcomes (e.g., fair dice).  
- **Experimental Probability:** Based on actual experiments or trials.  
- **Conditional Probability:** Probability of an event given that another event has occurred.

---

### Example  
What is the probability of rolling a 4 on a fair six-sided dice?  
\[
P(4) = \frac{1}{6} \approx 0.167
\]

What is the probability of rolling an even number?  
\[
P(\text{even}) = \frac{3}{6} = 0.5
\]

---

### Probability in Python

```python
import random

# Simulate rolling a dice 1000 times and count number of 4s
rolls = [random.randint(1, 6) for _ in range(1000)]
count_4 = rolls.count(4)
prob_4 = count_4 / 1000
print(f"Experimental Probability of rolling a 4: {prob_4}")
