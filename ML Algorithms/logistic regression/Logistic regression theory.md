# 📊 Logistic Regression

Logistic Regression is a **supervised machine learning algorithm** used for **binary classification problems**. Unlike linear regression, it predicts the **probability** of a categorical dependent variable.

It is used in applications such as:
- Spam detection
- Disease diagnosis (e.g., diabetes prediction)
- Customer churn prediction

---

## Mathematical Background

In Logistic Regression, we use the **sigmoid function** to map predicted values to probabilities between 0 and 1:

$$\
\sigma(z) = \frac{1}{1 + e^{-z}}
\$$

Where:
 $\ z = \beta_0 + \beta_1x_1 + \beta_2x_2 + \ldots + \beta_nx_n \$

---

## 📈 Sigmoid Function

The sigmoid function converts the linear regression output into a probability:

- Output close to 0 → Class 0
- Output close to 1 → Class 1

---

## 🔁 Loss Function

Logistic Regression uses **Binary Cross-Entropy Loss** (Log Loss):

$$\
\mathcal{L}(y, \hat{y}) = -[y \log(\hat{y}) + (1 - y) \log(1 - \hat{y})]
\$$

Where:
- $y$ is the actual label
- $\hat{y}$ is the predicted probability

---


```python
from sklearn.linear_model import LogisticRegression
model = LogisticRegression()
model.fit(X_train, y_train)
predictions = model.predict(X_test)
````

---



## Results and Accuracy

The model is evaluated using:

* Accuracy Score
* Confusion Matrix
* ROC Curve
* Precision, Recall, and F1 Score

---
