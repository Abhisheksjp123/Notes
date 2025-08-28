# Distribution/ Probability Distribution functions:
A **probability distribution** describes how the values of a variable are spread out. It tells us which values are most likely to occur, which are less likely, and what the overall shape of the data is. We often visualize distributions using a **histogram** or a **Kernel Density Estimate (KDE)** plot.

While there are many types of distributions, a few are particularly common in statistics and data science.
1. Normal Distribution (Gaussian Distribution)
The **Normal Distribution** is arguably the most important distribution in statistics. It's characterized by its symmetric, bell-shaped curve.
![[licensed-image.jpeg|300]]
2. Poisson distribution :

![[Untitled.jpeg]]
The **Poisson Distribution** is used to model the number of times an event occurs within a specific interval of time or space. It deals with discrete count data.
- **Key Characteristics**: It describes the probability of a given number of events happening when the average rate of occurrence is known.
- **Examples**:
	- The number of emails you receive in an hour.
	- The number of customers arriving at a store in a day.
	- The number of typos on a page.
3. Exponential Distribution
The **Exponential Distribution** is related to the Poisson distribution. While Poisson models the _number_ of events, the exponential distribution models the _time between_ those events.

- **Key Characteristics**: It describes processes where events happen continuously and independently at a constant average rate.
- **Examples**:
	- The time until the next customer arrives at a store.
	- The lifespan of an electronic component.
	- The time until an earthquake occurs.

# Normal Distribution
The **Normal Distribution** is arguably the most important distribution in statistics. It's characterized by its symmetric, bell-shaped curve.
- **Key Characteristics**: The data is centered around the mean, with values becoming progressively less frequent the further they are from the mean. The mean, median, and mode are all equal.
- **Examples**: Heights of people, blood pressure, test scores, and measurement errors often follow a normal distribution.

![[licensed-image.jpeg|400]]

- 95 % of values lies +/- 2 Standard deviation around the mean i.e  
-  68 % of values lies +/- 1 Standard deviation around the mean i.e  
Conclusion : Standard deviation gives the width of normal distribution  
So we need 2 things to draw a normed distribution : -  
1. Mean  
2. Standard deviation , to determine its width
## Central Limit Theorem
While many real-world phenomena like height, weight, and salary naturally follow a normal distribution, the **Central Limit Theorem (CLT)** reveals something even more profound and useful.

The CLT states that if you take **sufficiently large samples** from any population, regardless of the population's original distribution, the **distribution of the sample means** will approximate a normal distribution.

This is a cornerstone of statistics. As a rule of thumb, a sample size of **n ≥ 30** is often considered sufficiently large for the CLT to apply.

### A Simple Analogy
Imagine rolling a single six-sided die many times. The distribution of the outcomes is **uniform**, not normal—each number (1 through 6) has an equal chance of appearing.

Now, instead of rolling one die, you roll five dice and calculate their average. If you repeat this process thousands of times and plot a histogram of all those averages, you'll see a beautiful **bell-shaped, normal distribution** begin to form. The original distribution (uniform) doesn't matter; the distribution of the sample means will still be normal.

### Why the CLT is So Important
The Central Limit Theorem is the bedrock of inferential statistics for two main reasons:
1. **It allows for inference without knowing the population distribution**: The CLT enables statisticians to use methods based on the normal distribution to make inferences about a population's parameters (like the mean), even if the population's actual distribution is skewed, uniform, or completely unknown.
2. **It justifies many statistical methods**: It is the theoretical foundation that makes widely used techniques like ==confidence intervals== and ==hypothesis testing== valid and reliable. These methods rely on the assumption that the sample statistic (like the sample mean) follows a normal distribution.