
## 1. Mean

### Population Mean
$$
\mu = \frac{\sum_{i=1}^{N} x_i}{N}
$$
Where:
**μ**: Population mean.
**N**: Population size.
### Sample Mean
$$
\bar{x} = \frac{\sum_{i=1}^{n} x_i}{n}
$$
n: Sample size.
## 2. Variance

### Population Variance
This measures the spread of the **entire population**.
$$
\sigma^2 = \frac{\sum_{i=1}^{N} (x_i - \mu)^2}{N}
$$
σ2 : Population Variance
N: Population size
### Sample Variance
This measures the spread of your **sample** and is used to estimate the population variance (σ2). Notice the denominator is **n-1**, not n.
$$
s^2 = \frac{\sum_{i=1}^{n} (x_i - \bar{x})^2}{n-1}
$$
s2 : Population Variance
n: Population size

>Why "n-1"? (Bessel's Correction)
Using **n-1** in the denominator for the sample variance is known as **Bessel's correction**. It's done because the sample mean (xˉ) is always at the center of the sample data, which tends to make the spread of the sample slightly smaller than the true spread of the population.
>
>Dividing by a smaller number (n-1 instead of n) inflates the result slightly, giving us a more accurate and **unbiased estimate** of the true population variance.