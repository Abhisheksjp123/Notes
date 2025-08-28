The **p-value** is a crucial part of hypothesis testing. It quantifies how likely it is to get your observed data just by random chance, assuming your null hypothesis is true.
### **How** **to Calculate P-values?**  
The calculation depends on whether you're performing a one-tailed test (rarely used, for testing a specific direction like "greater than") or a two-tailed test (commonly used, for testing any difference).
### Calculating Two-Tailed P-Values  
A two-tailed p-value considers results that are **as extreme as, or more extreme than,** your observation in _both directions_ (positive and negative).

The p-value is the sum of three probabilities:
1. The probability of the specific outcome you observed.
2. The probability of an equally rare outcome in the opposite direction.
3. The probability of all outcomes that are even rarer (more extreme).

The reason we include equally rare and rarer outcomes is that the p-value isn't just about our specific result, but about the likelihood of the _overall extremeness_ of our result. If many other "extreme" outcomes are also possible, our specific result seems less special.

Let Say You've a rarest flower in the world. But then you Come to know there are lot of similar equally rare flowers  
because a lot of equally rare things would make Something less rare

### Example 1: Two Coin Tosses
You toss a coin twice and get two heads (HH). Is the coin biased?

- **Null Hypothesis (H0​)**: The coin is fair (not special).
- **Observation**: Getting 2 heads (HH). The probability is 1/4=0.25.
- **Equally Extreme Outcome**: Getting 2 tails (TT). The probability is 1/4=0.25.
- **More Extreme Outcomes**: There are no outcomes rarer than getting all heads or all tails. So, this probability is 0.

**P-value** = P(HH) + P(TT) = 0.25+0.25=0.50
- **Conclusion**: Since the p-value (0.50) is much greater than the standard significance level of 0.05, we **fail to reject the null hypothesis**. We don't have enough evidence to say the coin is biased.
  
## Example 2: P-Values on a Statistical Distribution

When working with continuous data, like a normal distribution, the p-value is the area in the tails of the distribution.

### Example: Height of Brazilian Women
![[Pasted image 20250826135305.png]]You have a normal distribution of heights for Brazilian women. You measure one woman with a height of 142 cm, which falls in the bottom 2.5% of the distribution. Does this height plausibly come from this population?
Ans:
- **Null Hypothesis (H0​)**: The height of 142 cm is from the given distribution of Brazilian women.
- **Observation**: The height is in the bottom 2.5% tail (area = 0.025).
- **Equally Extreme Outcome**: A height that is equally far from the mean but in the top tail (area = 0.025).
**P-value** = (Area in the lower tail) + (Area in the upper tail) = 0.025+0.025=0.05
Conclusion: Since the p-value is **exactly 0.05**, it is not strictly _less than_ 0.05. By the most common convention, you would **fail to reject the null hypothesis**. You're on the borderline, but there isn't quite enough evidence to declare the height as statistically significant or coming from a different population.

May cover later
#one-tailed-test 
#Power_Analysis
#P_hacking-Adjusted_p_value