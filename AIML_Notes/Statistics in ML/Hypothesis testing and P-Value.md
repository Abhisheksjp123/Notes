# Hypothesis Testing
**Hypothesis testing** is a formal statistical method used to test a claim or assumption about a population. It's a structured way to determine if there's enough evidence in a sample of data to infer that a particular condition is true for the entire population.

The core idea is to start with a default assumption and then use evidence from your data to decide whether to stick with that assumption or reject it in favor of an alternative.

## The Two Competing Hypotheses
Every hypothesis test involves two competing statements: the null hypothesis and the alternative hypothesis.
### **NULL** **Hypothesis** (H0​) : 
The **null hypothesis** is the default assumption, or the "status quo." It always states that there is **no effect**, **no difference**, or **no relationship** between the variables you are studying.

Think of it as the "innocent until proven guilty" principle in a courtroom. You assume the null hypothesis is true unless you have strong evidence to prove otherwise.
- **Examples**:
	- A new drug has **no effect** on recovery time.
	- There is **no difference** in test scores between two teaching methods.

### Alternative hypothesis (Ha​ or H1​) :
The **alternative hypothesis** is the claim that the researcher is actually trying to prove. It is the direct opposite of the null hypothesis and states that there **is an effect**, a **difference**, or a **relationship**.
- **Examples**:
	- The new drug **reduces** recovery time.
	- There **is a difference** in test scores between the two teaching methods.

The goal of hypothesis testing is to collect enough statistical evidence to either **reject the null hypothesis** in favor of the alternative, or **fail to reject the null hypothesis** due to a lack of evidence.

Example: Do men and women have different average Salaries after graduating Universities?


## Example: University Graduate Salaries
Let's apply this to your example question: "Do men and women have different average salaries after graduating?"
1. **Formulate the Hypotheses**:
       - **Null Hypothesis (H0​)**: The average salary for men is **equal** to the average salary for women. (There is no difference.)
       - **Alternative Hypothesis (Ha​)**: The average salary for men is **not equal** to the average salary for women. (There is a difference.)
2. **Collect Data**: You would gather salary data from a representative sample of male and female graduates.
3. **Analyze and Conclude**: You would then perform a statistical test (like a t-test) to see how likely it is that you'd observe the difference in your sample if the null hypothesis were true.
    - If the difference is statistically significant (meaning it's unlikely to be due to random chance), you would **reject the null hypothesis** and conclude that there is a difference in average salaries.
    - If the difference is not significant, you would **fail to reject the null hypothesis**, concluding that you don't have enough evidence to say that a difference exists.

# [[P-Value]]
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