# Hypothesis Testing
**Hypothesis testing** is a formal statistical method used to test a claim or assumption about a population. It's a structured way to determine if there's enough evidence in a sample of data to infer that a particular condition is true for the entire population.

The core idea is to start with a default assumption and then use evidence from your data to decide whether to stick with that assumption or reject it in favor of an alternative.

## The Two Competing Hypotheses
Every hypothesis test involves two competing statements: the null hypothesis and the alternative hypothesis.
Hypothesis  can be One tailed or Two tailed:
example : Let's use the example of a new drug's effect on recovery time compared to an old drug.

1. For a Two-Tailed Test
Here, you're testing for _any_ difference. The "no effect" is that the recovery times are equal.
- **Null Hypothesis (H0​)**: The average recovery time for the new drug is **equal to** the old drug's time.    
	- μnew​ = μold​
- **Alternative Hypothesis (Ha​)**: The average recovery time is **not equal**.
	- μnew !=μold​
1. For a One-Tailed Test (Right-Tailed)
Here, you're specifically testing if the new drug _reduces_ recovery time. The "status quo" you're trying to disprove is that the new drug is either the same _or worse_ than the old one.

- **Null Hypothesis (H0​)**: The average recovery time for the new drug is **greater than or equal to** the old drug's time.
	- μnew​≥μold​
- **Alternative Hypothesis (Ha​)**: The average recovery time is **less than** the old drug's time.
	- μnew​<μold​


The goal of hypothesis testing is to collect enough statistical evidence to either **reject the null hypothesis** in favor of the alternative, or **fail to reject the null hypothesis** due to a lack of evidence.


Steps for Hypothesis testing
1. **Formulate the Hypotheses**:
2. **Collect Data**: 
3. **Analyze and Conclude**: This is the most important part, it goes like

Once you have your hypotheses and data, you use a **statistical test** to analyze the evidence. The test produces a **p-value**, which helps you decide whether to reject or fail to reject the null hypothesis. The choice of test depends on the type of data you have and the question you're asking.

"In statistical theory, this step involves calculating a **test statistic** from your sample data. This statistic measures how far your sample result deviates from the result expected under the null hypothesis. The test statistic is then used to determine the p-value by comparing it to the known probability distribution for that test (e.g., the t-distribution or the normal distribution). If the p-value is below a predetermined significance level (alpha, typically 0.05), the result is deemed statistically significant."

#### 1. **T-Tests**
T-tests are used to compare the means of one or two groups. They are a go-to tool for A/B testing in machine learning.
- **When to use**: When you have a small sample size (typically n < 30) and the population standard deviation is unknown.
- **Types**:
	- **One-Sample T-Test**: Compares the mean of a single group to a known value. Example: You want to know if the average IQ score of students in a particular class is significantly different from the national average IQ of 100
	
	- **Two-Sample T-Test (Independent T-Test)**: Compares the means of two independent groups. This is the most common type for A/B testing (e.g., comparing the click-through rates of two different website designs).
	
	- **Paired T-Test**: Compares the means of the same group at two different times (e.g., before and after a treatment). Example accuracy of students before and after lunch.

#### 2. **Z-Tests**
Z-tests are also used to compare means, but they have stricter requirements than t-tests.
- **When to use**: When you have a large sample size (n ≥ 30) and you know the population standard deviation. In practice, t-tests are often preferred because the population standard deviation is rarely known.

#### 3. **ANOVA (Analysis of Variance)**
ANOVA is used when you want to compare the means of **three or more** groups.
- **When to use**: Instead of running multiple t-tests (which increases the chance of error), ANOVA checks if there's a significant difference between any of the group means.
- **Example**: Comparing the effectiveness of three different machine learning models on a specific metric.

#### 4. **Chi-Squared Test (χ2)**

The Chi-Squared test is used for **categorical data**.
- **When to use**: To determine if there is a significant association between two categorical variables.
- **Example in ML**: In feature selection, you might use a Chi-Squared test to see if a categorical feature (e.g., "City") is independent of the categorical target variable (e.g., "Customer Churn"). If they are not independent, the feature is likely useful for the model.


