XGBoost isn't just a machine learning algorithm; it's a highly optimized **library** that implements the Gradient Boosting algorithm. Its name, short for **eXtreme Gradient Boosting**, reflects its focus on speed, performance, and flexibility, which it achieves by combining the core algorithm with advanced software and hardware optimization concepts.

For understanding its need, we need to understand.
Q13 - Why do we have so many ML algorithms
Ans - To understand why XGBoost was so revolutionary, it's helpful to look at the evolution of machine learning algorithms:
- **1970s-80s**: Early algorithms like **Linear Regression** and **Naive Bayes** were effective but specialized. They performed well only on specific types of data (e.g., linear relationships for LR, text for NB).
- **1990s-2000s**: More versatile algorithms like **Random Forest**, **SVM**, and the original **Gradient Boosting** emerged. These models could handle a wider variety of data but were often slow to train and prone to overfitting.

This is where researcher **Tianqi Chen** saw an opportunity. He recognized the immense potential of the Gradient Boosting algorithm and set out to build a better implementation.
## Why Gradient Boosting?

Chen chose Gradient Boosting as his foundation for several key reasons:
1. **Flexibility**: It can use various loss functions, allowing it to tackle regression, classification, ranking, and even custom prediction problems.
2. **Performance**: The core algorithm was already known for its high accuracy.
3. **Robustness**: It naturally handles missing values and includes regularization techniques (like L1 and L2) to prevent overfitting.
4. **Popularity**: It was already a favorite among top competitors on platforms like Kaggle, proving its effectiveness.

## XGBoost Timeline
- **2014**: Tianqi Chen begins the project as a research endeavor.
- **2015**: XGBoost gains massive recognition after winning the prestigious **Kaggle Higgs Boson Machine Learning Challenge**, where it significantly outperformed other models.
- **2016**: Chen and his collaborators publish the official paper, and the project becomes a fully open-source community effort, leading to widespread adoption and continuous improvement.

# What were the improvements
Tianqi did the improvements in the following fronts:
1. Performance
2. Speed
3. Flexibility

My outlook: XGB is the most powerful powerful algorithm out there for Tabular data, even more powerful than ANN. Also it is somewhat interpretable with Shapely and LIME. So moving forward, I can always keep a XGB solution.
There are other Similar Algorithm created on the same foundation of XGB like:
1. Microsoft LightGBM
2. CatBoost






Source: CampusX Video : [link](https://www.youtube.com/watch?v=C6aDw4y8qJ0&t=1151s)


