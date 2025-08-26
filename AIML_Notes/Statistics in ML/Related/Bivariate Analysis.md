Bivariate analysis is the process of analyzing **two variables** simultaneously to understand the relationship between them. My strategy of comparing each feature against the **target variable**.

It's standard practice to place the independent variable (the feature you are testing) on the x-axis and the dependent variable (your target variable) on the y-axis.

## Choosing the Right Plot
The best type of plot to use depends on the data types of the two variables you are comparing.

### 1. Continuous vs. Continuous
When both your feature and your target variable are continuous (e.g., "Years of Experience" vs. "Salary"), the ideal plot is a **scatter plot**.
- **What to look for**: A scatter plot helps you visualize the **direction** (positive or negative), **strength** (strong, weak, or no relationship), and **form** (linear or non-linear) of the relationship between the two variables.
### 2. Continuous vs. Categorical
When you are comparing a continuous variable (e.g., "Salary") with a categorical variable (e.g., "Highest Degree"), you can use several plots to see how the continuous variable's distribution changes across the different categories.

- Bar Chart/Histogram/KDE: Shows the mean or median of the continuous variable for each category. It's great for a quick comparison of average values.
- **Box Plot**: This is more informative as it shows the median, quartiles, and potential outliers for each category, giving you a better sense of the distribution's spread and skewness.
### 3. Categorical vs. Categorical

When both your feature and your target variable are categorical (e.g., "City" vs. "Customer Churn"), you typically use tables  more specifically Pivot tables to see the split
- **Contingency Table (Crosstab)**: A table that shows the frequency of each combination of categories. It is like a pivot table where you take sum of count keeping one variable in x-axis and one on y-axis