#references #probability
A binomial distribution models the probability of achieving a specific number of successes in a fixed number of independent trials, where each trial has only two possible outcomes (success or failure) and the probability of success remains constant. It's a discrete probability distribution, meaning it deals with countable outcomes.

### **Key Characteristics:**
1. **Fixed number of trials ($n$):** The experiment is repeated a fixed number of times.
2. **Independent trials:** Each trial is independent of the others.
3. **Two outcomes:** Each trial has only two possible outcomes:  
   - Success (with probability $p$)
   - Failure (with probability $q = 1 - p$)
4. **Constant probability:** The probability of success $p$ remains the same for each trial.

### **Probability Mass Function (PMF):**
The probability of getting exactly $k$ successes in $n$ trials is given by:
$$
P(X = k) = \binom{n}{k} p^k (1 - p)^{n - k}
$$

where:
- $\binom{n}{k} = \frac{n!}{k!(n - k)!}$ is the binomial coefficient (number of ways to choose $k$ successes out of $n$ trials).
- $p$ = probability of success in a single trial.
- $k$ = number of successes ($0 \leq k \leq n$).

### **Mean (Expected Value) and Variance:**
- **Mean (Expected Value):**  
  $$
  \mu = n \cdot p
  $$
- **Variance:**  
  $$
  \sigma^2 = n \cdot p \cdot (1 - p)
  $$
- **Standard Deviation:**  
 $$ 
  \sigma = \sqrt{n \cdot p \cdot (1 - p)}
$$

### **Example:**
Suppose you flip a fair coin ($p = 0.5$) 10 times. The probability of getting exactly 6 heads is:

$$
P(X = 6) = \binom{10}{6} (0.5)^6 (0.5)^4 = 210 \times 0.015625 = 0.2051 \ (20.51\%)
$$
