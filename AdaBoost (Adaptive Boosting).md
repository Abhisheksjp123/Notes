How AdaBoost works:

Consider this dataset where we're trying to predict loan approval
We start with a dataset where each sample is assigned an equal initial weight. For this dataset with 8 samples (N=8), each sample has a weight of 1/8.

| ID  | Salary | Credit Score | Loan Approved (Output) | ==W1==  |
| :-- | :----- | :----------- | :--------------------- | ------- |
| 1   | >50k   | Good         | Yes                    | 1/8 |
| 2   | <50k   | Good         | Yes                    | 1/8 |
| 3   | >50k   | Bad          | No                     | 1/8 |
| 4   | <50k   | Bad          | No                     | 1/8 |
| 5   | >50k   | Neutral      | Yes                    | 1/8 |
| 6   | <50k   | Neutral      | No                     | 1/8 |
| 7   | <50k   | Good         | Yes                    | 1/8 |
| 8   | >50k   | Bad          | No                     | 1/8 |

### Step 1: Train the First Weak Learner (Stump) 
The first step is to train a **weak learner**. In AdaBoost, this is typically a **decision stump**, which is a decision tree with only one split.

Instead of using Gini Impurity or Entropy, the primary goal is to find the stump that **minimizes the total weighted error**. The error is the sum of the weights of the misclassified samples.
For our dataset, the best initial stump was found to be:
### Calculating Error and Performance
Based on this first stump, we can calculate its effectiveness.

- **Total Error (ϵ)** 
	The total error is the sum of the weights of all misclassified samples. Since only sample ID 5 was misclassified, the error is: 
	ϵ=Weight(ID 5)=1/8=0.125
- **Performance / Amount of Say (α)** 
	This value determines how much influence the stump will have in the final vote. It's calculated based on the total error.
$$
\alpha = \frac{1}{2} \ln \left( \frac{1 - \epsilon}{\epsilon} \right)
$$
Plugging in our error:
$$
\alpha = \frac{1}{2} \ln \left( \frac{1 - 0.125}{0.125} \right) = \frac{1}{2} \ln(7) \approx 0.973
$$

### Step 2: Update the Sample Weights 
Based on the performance (alpha) of the first stump, the weights for each sample are updated. This process increases the importance of misclassified samples and decreases the importance of correctly classified ones.
- **For correctly classified samples:** The weight is decreased.

$$
w_{\text{new}} = w_{\text{old}} \times e^{-\alpha}
$$

- **For incorrectly classified samples:** The weight is increased.

$$
w_{\text{new}} = w_{\text{old}} \times e^{\alpha}
$$


After updating, the weights are **normalized** by dividing each new weight by the sum of all new weights. This ensures the new weights sum to 1, creating a new probability distribution for training the next model.

| ID  | Initial Weight ($w_1$) | Classification | Updated Weight (Unnormalized) | New Weight ($w_2$) |
| :-- | :--------------------- | :------------- | :---------------------------- | :----------------- |
| 1   | 0.125                  | Correct        | 0.047                         | 0.0714             |
| 2   | 0.125                  | Correct        | 0.047                         | 0.0714             |
| 3   | 0.125                  | Correct        | 0.047                         | 0.0714             |
| 4   | 0.125                  | Correct        | 0.047                         | 0.0714             |
| 5   | 0.125                  | **Incorrect**  | **0.331**                     | **0.5000**         |
| 6   | 0.125                  | Correct        | 0.047                         | 0.0714             |
| 7   | 0.125                  | Correct        | 0.047                         | 0.0714             |
| 8   | 0.125                  | Correct        | 0.047                         | 0.0714             |
|     | **Total:**             |                | **~0.662**                    | **1.0**            |

### Step 3: Create the New Dataset (Resampling) 
The next step is to create a new dataset that the second weak learner will be trained on. This is done using a technique called **resampling with replacement**, guided by the new sample weights.

The process works like this:
1. The new dataset will have the same number of samples as the original (in this case, 8).
2. We generate 8 random numbers between 0 and 1.
3. For each random number, we see which sample's "bin range" it falls into and add that sample to our new dataset.

| ID | Loan Approved | Classification | New Weight ($w_2$) | Cumulative Bin Range |
|:---|:---|:---|:---|:---|
| 1 | Yes | Correct | 0.0714 | 0.0000 - 0.0714 |
| 2 | Yes | Correct | 0.0714 | 0.0714 - 0.1428 |
| 3 | No | Correct | 0.0714 | 0.1428 - 0.2142 |
| 4 | No | Correct | 0.0714 | 0.2142 - 0.2856 |
| 5 | Yes | **Incorrect** | **0.5000** | **0.2856 - 0.7856** |
| 6 | No | Correct | 0.0714 | 0.7856 - 0.8570 |
| 7 | Yes | Correct | 0.0714 | 0.8570 - 0.9284 |
| 8 | No | Correct | 0.0714 | 0.9284 - 1.0000 |
### Step 4
The process of training a stump, calculating its performance, and resampling the data is **repeated** for a specified number of iterations (controlled by the `n_estimators` hyperparameter). In each round, a new stump (ht​) is trained on the latest weighted data, and its performance score (αt​) is calculated.

Final prediction:
Once all the stumps are trained, AdaBoost combines them into a single strong classifier. The final prediction is not a simple sum but a **weighted majority vote**. Each stump "votes" on the classification, and its vote is weighted by its performance score (α). The class with the most weighted votes wins.

$$
H_{\text{final}}(x) =  \alpha_1 h_1(x) + \alpha_2 h_2(x) + \alpha_3 h_3(x) + \dots
$$

