# Cross Validation in Machine Learning – Theory and Methods

Cross-validation is a powerful technique in machine learning used to assess the performance and generalizability of predictive models. This repository explains the **theory**, **types**, **advantages**, **limitations**, and **practical examples** of cross-validation.

Cross-validation is a **resampling technique** used to evaluate machine learning models by training them on subsets of the available data and testing them on the complementary subset. It helps in estimating how the model will perform on unseen data and is essential for **model validation**, **hyperparameter tuning**, and **preventing overfitting**.

---

## 🔁 Why Use Cross Validation?

- To validate the model’s ability to generalize to unseen data.
- To avoid **overfitting** or **underfitting**.
- To obtain a more **robust estimate** of model performance.
- To compare different models and choose the best one.

---

## 📌 Types of Cross Validation

### 1. **Hold-Out Validation**
- Splits the dataset into a training set and a testing set (e.g., 80/20).
- Simple and fast, but performance depends on the data split.
![image](https://github.com/user-attachments/assets/d07b2ac1-2e0f-468f-a34c-e49d5b8f59a0)


### 2. **K-Fold Cross Validation**
- Divides the dataset into *k* equal parts.
- The model is trained on *k-1* folds and tested on the remaining fold.
- This is repeated *k* times and results are averaged.

> 🔢 Common choice: `k = 5 or 10`
![image](https://github.com/user-attachments/assets/792e799d-b590-4644-97d8-c2f8613cdc28)

### 3. **Stratified K-Fold Cross Validation**
- Similar to K-Fold, but maintains the class distribution in each fold.
- Useful in **imbalanced classification** problems.
![image](https://github.com/user-attachments/assets/a52ed7a5-4ce2-40d3-abd9-66a5084992e9)

### 4. **Leave-One-Out Cross Validation (LOOCV)**
- Uses `n-1` samples for training and 1 sample for testing.
- Repeats for all `n` samples.
- Very accurate but computationally expensive.
  ![image](https://github.com/user-attachments/assets/31f518bf-625f-41fc-815c-da0a1f67cfcf)


### 5. **Group K-Fold Cross Validation**
- Used when samples are grouped and should not be split across folds (e.g., patient data).
- Ensures that the same group does not appear in both train and test sets.
![image](https://github.com/user-attachments/assets/32f3b82c-d393-457c-a11f-28a6c6db268f)

### 6. **Time Series Cross Validation (Forward Chaining)**
- Used for **time-dependent data**.
- Maintains the temporal order while creating folds.

---

## ✅ Advantages

- Better estimate of model performance.
- Reduces variability caused by random train-test splits.
- Helps in model selection and hyperparameter tuning.

---

## ⚠️ Limitations

- Increases computational cost.
- May not be suitable for very large datasets.
- Requires careful design in time series or grouped data.

---

## 📊 Practical Demonstrations

We’ve included Jupyter Notebooks under the `notebooks/` folder with practical examples using:
- `KFold` and `StratifiedKFold` (classification)
- `TimeSeriesSplit` (forecasting tasks)

> 📁 Check the [notebooks](notebooks/) folder to get started.

---

## 🔍 References

* [Scikit-learn Documentation on Cross Validation](https://scikit-learn.org/stable/modules/cross_validation.html)
* Géron, A. (2019). *Hands-On Machine Learning with Scikit-Learn, Keras & TensorFlow*
* [ML Cheatsheet – Cross Validation](https://ml-cheatsheet.readthedocs.io/en/latest/cross_validation.html)
---
