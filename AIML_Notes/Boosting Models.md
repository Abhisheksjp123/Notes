Boosting is a powerful **ensemble learning technique** that combines multiple simple models, known as **weak learners**, to create a single, highly accurate model, or **strong learner**.

### Core Concept

Like bagging, boosting is an ensemble method. However, the core difference lies in their approach:
- **Bagging (e.g., Random Forest):** Trains many models in **parallel**, each on a different random subset of the data. The final prediction is an average or a vote from all models.
- **Boosting:** Trains models **sequentially**. Each new model is built to correct the errors made by the previous ones.

### How Boosting Works
The process is iterative, with each step focusing on the shortcomings of the previous one.
1. **Initial Model:** A simple base model (a weak learner) is trained on the dataset.
2. **Identify Errors:** The model's predictions are compared to the actual outcomes. The data points that were misclassified are identified.
3. **Increase Weights:** The algorithm increases the importance (or weight) of the misclassified data points. This forces the next model in the sequence to pay more attention to these "difficult" examples.
4. **Train Next Model:** A new weak learner is trained on this modified, re-weighted dataset. It focuses on getting the previously incorrect predictions right.
5. **Repeat:** This process is repeated for a specified number of models, with each subsequent model building on its predecessors to reduce the overall error.

### Final Prediction
The final prediction is not a simple average. Instead, it's a **weighted sum** of the predictions from all the models. Each model is assigned a weight (α) based on its accuracy—better-performing models have more "say" in the final outcome.

The formula for the final prediction can be expressed as:
$$ 
H_{final}(x) = \sum_{t=1}^{T} \alpha_t h_t(x)
$$
Where:
- Hfinal​(x): The final prediction from the strong model.
- ht​(x): The prediction from the t-th weak learner.
- αt​: The weight assigned to the t-th model, reflecting its performance. More accurate models get a higher weight.
- T: The total number of weak learners.



# Popular Boosting Algorithms

1. [[AdaBoost (Adaptive Boosting)]]
2. [[Gradient Boosting Machine (GBM)]]
3. [[XGBoost (Extreme Gradient Boosting)]]