# 🤖 Types of Machine Learning

This repository introduces the four main types of Machine Learning (ML):

* Supervised Learning
* Unsupervised Learning
* Semi-Supervised Learning
* Reinforcement Learning

Each type includes theoretical explanation, real-world examples, and Python code examples using Scikit-learn, PyTorch, and OpenAI Gym.

---

## 📁 Folder Structure

```
Types-of-Machine-Learning/
│
├── supervised_learning/
│   ├── regression_example.ipynb            # House Price Prediction
│   └── classification_example.ipynb        # Iris Flower Classification
│
├── unsupervised_learning/
│   ├── clustering_example.ipynb            # Customer Segmentation with K-Means
│   └── pca_example.ipynb                   # Dimensionality Reduction using PCA
│
├── semi_supervised_learning/
│   └── label_propagation_example.ipynb     # Digit Recognition with Few Labels
│
├── reinforcement_learning/
│   └── q_learning_gridworld.ipynb          # Agent Navigating a Grid World
│
├── datasets/
│   └── (used datasets)
│
├── images/
│   └── ml_types_diagram.png
│
└── README.md
```

---

## 1️⃣ Supervised Learning

**Definition:**
The model learns from labeled data (features + target).

**📌 Real-World Examples:**

* Spam email detection (Spam or Not)
* House price prediction based on size, location, etc.

**🧪 Included Notebook Examples:**

* `regression_example.ipynb`: Predicting house prices using Linear Regression on the Boston Housing dataset.
* `classification_example.ipynb`: Classifying Iris flowers using K-Nearest Neighbors (KNN).

---

## 2️⃣ Unsupervised Learning

**Definition:**
The model works on **unlabeled** data to discover patterns or groupings.

**📌 Real-World Examples:**

* Market segmentation of customers
* Social network analysis

**🧪 Included Notebook Examples:**

* `clustering_example.ipynb`: Using K-Means to segment customers based on annual income and spending score.
* `pca_example.ipynb`: Applying PCA for visualizing high-dimensional handwritten digits data.

---

## 3️⃣ Semi-Supervised Learning

**Definition:**
Uses a small set of labeled data along with a large set of unlabeled data.

**📌 Real-World Examples:**

* Image classification with few annotated images
* Webpage classification with partial tags

**🧪 Included Notebook Example:**

* `label_propagation_example.ipynb`: Using Scikit-learn’s `LabelPropagation` to classify MNIST digits with limited labeled samples.

---

## 4️⃣ Reinforcement Learning

**Definition:**
An agent learns to make decisions by interacting with an environment and receiving rewards.

**📌 Real-World Examples:**

* Game-playing AI (Chess, Go, Atari games)
* Self-driving cars and robotics

**🧪 Included Notebook Example:**

* `q_learning_gridworld.ipynb`: Agent learns the optimal path in a 5x5 grid world using Q-Learning.

---

## 🛠️ Technologies Used

* Python 3
* Scikit-learn
* Matplotlib, Seaborn
* NumPy, Pandas
* OpenAI Gym (for RL)

---

## 📚 References

* Géron, Aurélien. *Hands-On Machine Learning*
* OpenAI Gym
* Scikit-learn Documentation

---

## 🙌 Contributions Welcome

Open an issue or pull request to add more examples, improve documentation, or suggest corrections.
---
