# Random Forest Algorithm

Random Forest is an ensemble learning method that builds multiple decision trees
and combines their outputs to improve accuracy and prevent overfitting.

## **Working:**

1. **Bootstrap Sampling(Bagging)**:
    * The dataset is randomly sampled with replacement to create multiple subsets (bootstrap samples).
    * Each subset is of the same size as the original dataset but may contain duplicate data points due to replacement.
2. **Independent Decision Trees**:
    * A separate Decision Tree is trained on each bootstrap sample.
3. **Feature Randomization**:
    * At each node of a tree, only a random subset of features is considered for splitting (instead of all features).
    * This further introduces diversity among trees.
4. **Aggregation (Voting or Averaging)**:
    * For classification: Each tree votes for a class, and the majority class is chosen (majority voting).
    * For regression: The predictions from all trees are averaged (mean prediction).

## **Important Parameters**  
- **n_estimators**: Number of decision trees in the forest.  
- **max_depth**: Maximum depth of individual trees (controls complexity).  
- **min_samples_split**: Minimum samples required to split a node.  
- **min_samples_leaf**: Minimum samples required in a leaf node.  
- **max_features**: Number of features considered for the best split.  
- **bootstrap**: Whether to use bootstrap sampling (default: True).  
- **criterion**: Function to measure split quality (example : **gini** for classification, **mse** for regression).  

## **Why it is called ‘Random’?**  
- **Random Sampling (Bagging)** – Each tree is trained on a randomly selected subset of data.  
- **Random Feature Selection** – At each split, a random subset of features is chosen instead of all features.  


## **Loss Functions**  

### Classification Loss Function  
#### **Gini Impurity**  
$$
G = 1 - \sum_{i=1}^{C} p_i^2
$$
where \( p_i \) is the probability of class \( i \).  

#### **Entropy (Cross-Entropy / Log Loss)**  
$$
H = -\sum_{i=1}^{C} p_i \log_2 p_i
$$

### Regression Loss Function  
#### **Mean Squared Error (MSE)**  
$$
MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y_i})^2
$$

#### **Mean Absolute Error (MAE)**  
$$
MAE = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y_i}|
$$

## **Advantages**  
- Reduces overfitting compared to individual decision trees.  
- Can handle high-dimensional data well.  
- Works well with missing values and noisy data.  
- Can be used for both classification and regression.  
- Handles non-linearity effectively.  

## **Disadvantages**  
- Computationally expensive for large datasets.  
- Requires more memory and processing time.  
- Less interpretable compared to single decision trees.  

## **Applications**  
- Credit risk prediction in banking.  
- Medical diagnosis (e.g., disease detection).  
- Image classification.  
- Fraud detection in financial systems.  

## **When to Use**  
- When accuracy is more important than interpretability.  
- When handling large datasets with high-dimensional features.  
- When there’s a risk of overfitting with a single decision tree.  
