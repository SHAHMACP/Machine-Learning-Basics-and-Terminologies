## 🧠 **Model Performance Metrics**

- Metrics used to assess the performance of a machine learning model.
- Helps in selecting the best model for a given problem.

---

### 🔶 **Classification Metrics**
#### 📊 Confusion Matrix
A confusion matrix is a table that is used to evaluate the performance of a classification algorithm. It compares the predicted class labels with the actual class labels.
|                     | Predicted Positive  | Predicted Negative  |
| ------------------- | ------------------- | ------------------- |
| **Actual Positive** | True Positive (TP)  | False Negative (FN) |
| **Actual Negative** | False Positive (FP) | True Negative (TN)  |

![image](https://github.com/user-attachments/assets/2504c3ed-ee81-4e19-b52f-bd39a84c96e7)

1. ### ✅ **Accuracy**

   * **Definition**: Proportion of total correct predictions.
   * **Formula**: $\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}$
   * **Use Case**: Works well when the dataset is balanced.
   * **Limitation**: Misleading in imbalanced datasets.

2. ### 🎯 **Precision**

   * **Definition**: Out of all predicted positives, how many are actually positive.
   * **Formula**: $\text{Precision} = \frac{TP}{TP + FP}$
   * **Use Case**: Important in spam detection, where false positives are costly.

3. ### 📢 **Recall (Sensitivity or True Positive Rate)**

   * **Definition**: Out of all actual positives, how many were predicted as positive.
   * **Formula**: $\text{Recall} = \frac{TP}{TP + FN}$
   * **Use Case**: Important in disease detection where false negatives are risky.

4. ### 🔁 **F1-Score**

   * **Definition**: Harmonic mean of precision and recall.
   * **Formula**: $\text{F1} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}$
   * **Use Case**: Useful when there's an uneven class distribution.

5. ### 📈 **ROC-AUC (Receiver Operating Characteristic - Area Under Curve)**

   * **Definition**: Measures the model’s ability to distinguish between classes.
   * **ROC Curve**: Plots True Positive Rate vs False Positive Rate.
   * **AUC**:

     * 1.0 = Perfect model
     * 0.5 = Random guess
   * **Use Case**: Great for evaluating classifiers across thresholds.

---

### 🔷 **Regression Metrics**
![image](https://github.com/user-attachments/assets/991de93f-5aa9-4f25-9efb-923d3aa773f8)

1. ### 📏 **Mean Absolute Error (MAE)**

   * **Definition**: Average of absolute differences between predicted and actual values.
   * **Formula**: $MAE = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i|$
   * **Use Case**: Easy to understand. All errors are weighted equally.

2. ### 📐 **Mean Squared Error (MSE)**

   * **Definition**: Average of squared differences between predicted and actual values.
   * **Formula**:
     $MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2$
     
   * **Use Case**: Penalizes large errors more than MAE.

3. ### 🧮 **Root Mean Squared Error (RMSE)**

   * **Definition**: Square root of MSE.
   * **Formula**: $RMSE = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2}$
     
   * **Use Case**: Has the same units as the target variable. Easy to interpret.

4. ### 📊 **R² Score (Coefficient of Determination)**

   * **Definition**: Indicates how well the model explains the variability of the target.
   * **Formula**: $ R^2 = 1-\frac{\text{SS}_{res}}{\text{SS}_{tot}} $
     
     where $SS_{res}$: Residual sum of squares and 
     $SS_{tot}$: Total sum of squares
   * **Interpretation**:

     * 1 = Perfect model
     * 0 = Model predicts average
     * <0 = Worse than average

---
