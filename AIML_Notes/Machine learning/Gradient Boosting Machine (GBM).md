Gradient Boosting is an ensemble technique that builds models sequentially, where each new model corrects the errors of its predecessor. Here's a step-by-step walkthrough using a regression example to predict salary.

| ID  | Experience (Years) | Highest Degree | Salary (LPA) |
| :-- | :----------------- | :------------- | :----------- |
| 1   | 2                  | Bachelors      | 6.5          |
| 2   | 5                  | Bachelors      | 11.0         |
| 3   | 3                  | Masters        | 9.0          |
| 4   | 8                  | Bachelors      | 15.0         |
| 5   | 10                 | Masters        | 22.0         |
| 6   | 1                  | Bachelors      | 4.0          |
| 7   | 6                  | Masters        | 16.0         |
| 8   | 12                 | PhD            | 30.0         |

### Step 1:  The Base Model and Initial Residuals
The process starts with a simple **base model (F_0)** that makes an initial prediction. For regression, this is simply the **mean** of the target variable.
- **Initial Prediction (F_0)**: Mean of Salary = **14.1875**

Next, we calculate the **residuals**, which are the errors of this initial prediction.
- **Residual (r_1) = Actual Salary - Initial Prediction**

| ID  | Experience (Years) | Highest Degree | Salary (LPA) | Residuals R1 |
| :-- | :----------------- | :------------- | :----------- | :----------- |
| 1   | 2                  | Bachelors      | 6.5          | -7.6875      |
| 2   | 5                  | Bachelors      | 11.0         | -3.1875      |
| 3   | 3                  | Masters        | 9.0          | -5.1875      |
| 4   | 8                  | Bachelors      | 15.0         | 0.8125       |
| 5   | 10                 | Masters        | 22.0         | 7.8125       |
| 6   | 1                  | Bachelors      | 4.0          | -10.1875     |
| 7   | 6                  | Masters        | 16.0         | 1.8125       |
| 8   | 12                 | PhD            | 30.0         | 15.8125      |

### Step 2: The First Weak Learner and Learning Rate
Now, we train our first **weak learner**, which is a simple decision tree (h_1), to predict the **Residuals (r_1)** from Step 1. The output of this tree is a simplified, grouped prediction of the residuals.

Out final out put will be:
$$
F_1(x) = F_0(x) +  h_1(x)
$$
As DT tends to overfit this will give us pretty good result for our training data, but we want to generalize the model.

The key idea is to update our initial prediction by adding a small, controlled amount of the weak learner's prediction. This is controlled by the **learning rate (eta)**. The learning rate scales the contribution of each tree to prevent overfitting and help the model generalize better. Let's use a learning rate of **eta=0.1**.

The first **updated prediction (F_1)** is calculated as:

$$
F_1(x) = F_0(x) + \eta \cdot h_1(x)
$$

### Step 3: Iterate by Training on New Residuals
The process now repeats. First, we calculate the **new residuals (r_2)** based on our updated prediction from Step 2.
- **New Residual (r_2) = Actual Salary - Updated Prediction (F_1)**

Then, we train a second decision tree (h_2) to predict these new residuals (r_2).

The Final Model:
This iterative process continues for a specified number of trees. The final prediction is the sum of the initial base model prediction and the scaled contributions from all the individual trees.
$$
F_{final}(x) = F_0(x) + \eta \cdot h_1(x) + \eta \cdot h_2(x) + \dots
$$



