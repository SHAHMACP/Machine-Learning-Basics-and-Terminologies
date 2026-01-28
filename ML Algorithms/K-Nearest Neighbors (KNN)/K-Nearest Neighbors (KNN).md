# K-Nearest Neighbors (KNN)

K-Nearest Neighbors (KNN) is a supervised machine learning algorithm. 
Generally used for classification, but can also be used for regression tasks. 
It works by finding the "k" closest data points (neighbors) to a given input and makes a prediction based on the majority class (for classification) or the average value (for regression).
KNN operates on the principle that similar data points are close to each other in the feature space, using "nearest neighbors" to determine the output.

It is an instance-based learning method, meaning it does not build an explicit model during training but instead stores the entire training dataset and makes predictions based on similarity to new data points.
KNN is lazy—it performs computations only at prediction time, making it straightforward but computationally intensive for large datasets.
Since there's no model fitting, hyperparameters (e.g., K) are tuned via cross-validation.
Example: Classifying a new fruit as an apple or an orange based on weight and color by looking at the K most similar fruits in the training data.

## How KNN Works
Store Training Data: Memorize all labeled examples.
Compute Distances: For a new data point, calculate distance to all training points using a metric (detailed below).
Select Neighbors: Identify the K closest points (nearest neighbors).
Make a Prediction:
Classification: Majority vote (e.g., if 3 out of 5 neighbors are class A, predict A).
Regression: Average (or weighted average) of neighbors' values.
Output: The predicted class or value.
<img width="644" height="300" alt="image" src="https://github.com/user-attachments/assets/411645bf-e9da-464d-918c-a662bc2a2f31" />

When k=3 then two belong to a purple class, and one belongs to the yellow class majority vote of purple, so here the purple class is considered 
When k=6, then four belong to a yellow class,s and two belong to a purple class, so the majority votes are yellow, so consider the yellow class. 
<img width="386" height="321" alt="image" src="https://github.com/user-attachments/assets/273fc5a6-4b46-42d6-a0ce-71b129816011" />

<img width="569" height="290" alt="image" src="https://github.com/user-attachments/assets/7b8e1fc3-a7bb-4d2e-ad74-a45353dedc56" />

## Assumptions of KNN
Similarity Metric: Data points that are close in feature space are similar (relies on a meaningful distance measure).
No Noise or Outliers: The algorithm is sensitive to noisy data, as outliers can skew the selection of neighbors.
Balanced Classes: For classification, classes should be balanced; imbalanced data may bias majority voting.
Feature Scaling: Features should be on similar scales, as distance metrics are affected by varying units.
Local Structure: The data has local patterns that neighbors can capture; global structures may not be well-represented.


