# Clustering in Machine Learning

Clustering is a powerful **unsupervised machine learning** technique used to discover **groups of similar items** in unlabelled datasets. This repository explains key clustering algorithms — their **concepts, working, parameters, examples**, and **Python code**.

---

## What is Clustering?

Clustering is the task of **grouping a set of objects** in such a way that objects in the same group (**cluster**) are **more similar** to each other than to those in other groups.

> Clustering = Finding structure in unlabelled data

---

## Why Clustering?

- Customer segmentation
- Market research
- Social network analysis
- Image segmentation
- Disease grouping
- Anomaly/fraud detection
- Document classification

---

## Types of Clustering Algorithms

| Algorithm Type         | Description                                | Example Algorithms                  |
|------------------------|--------------------------------------------|-------------------------------------|
| **Partitioning**       | Divides data into non-overlapping subsets  | K-Means, K-Medoids                  |
| **Hierarchical**       | Builds a tree-like structure of clusters   | Agglomerative, Divisive             |
| **Density-based**      | Groups based on dense regions               | DBSCAN, OPTICS                      |
| **Model-based**        | Uses probabilistic models                   | Gaussian Mixture Models (GMM)       |


![image](https://github.com/user-attachments/assets/734fcf6d-2e33-43ff-917a-1d4f93d7bff3)

---

## K-Means Clustering
K-Means Clustering is an unsupervised learning algorithm that groups similar data points into K clusters. 
It’s centroid-based, meaning each cluster is represented by the mean position (center) of the data points within it.
To partition the data into K distinct clusters so that:
Points within a cluster are as similar as possible.
Points in different clusters are as different as possible.


### How k means works??
- Choose K (number of clusters)
- Randomly initialize K centroids
- Assign each data point to the nearest centroid (using distance measure, usually Euclidean)
- Update centroids by calculating the mean position of all points assigned to that cluster
- Repeat steps 3 and 4 until:
            Centroids don’t change significantly
            OR a max number of iterations is reached

![image](https://github.com/user-attachments/assets/aa3a4661-d2a5-4a73-aaf3-ee2713171983)

### Loss function (Inertia)
![image](https://github.com/user-attachments/assets/1e5eda9d-5978-4159-8e5f-3b6c01fa9e26)

### Dunn Index
Dunn index is the ratio of the minimum of inter-cluster distances and maximum of intracluster distances. 
The more the value of the Dunn index, the better the clusters will be.
![image](https://github.com/user-attachments/assets/c25f5868-6cd0-446a-beec-5ba8242e142d)


### Parameters
- `n_clusters`: Number of clusters (K)
- `init`: Method to initialize centroids (`k-means++`)
- `max_iter`: Max iterations
- `random_state`: Reproducibility

### Limitations
- Needs predefined K
- Sensitive to outliers and initialization
- Only finds spherical clusters

### Example
```python
from sklearn.cluster import KMeans
kmeans = KMeans(n_clusters=3, random_state=0)
kmeans.fit(X)
labels = kmeans.labels_
````

### Elbow Method for Optimal Cluster Number in K-Means!
The elbow method is a graphical representation of finding the optimal ‘K’ in a K-means clustering.
When we analyze the graph, we can see that the graph will rapidly change at a point and thus creating an elbow shape. From this point, the graph moves almost parallel to the X-axis. The K value corresponding to this point is the optimal value of K or an optimal number of clusters.
![image](https://github.com/user-attachments/assets/799c1b7a-48ba-4563-a5a2-d959976871b3)



---

## Hierarchical Clustering
Hierarchical Clustering is an unsupervised machine learning algorithm that builds a hierarchy of clusters in a tree-like structure.
![image](https://github.com/user-attachments/assets/3d63b955-40a4-4040-96d6-f7a755ee3a2a)
![image](https://github.com/user-attachments/assets/f15d6e17-fe05-4ce6-983f-22173adf20f2)


### Idea

* **Agglomerative**: Bottom-up merging of closest clusters
* **Divisive**: Top-down splitting of large clusters
* Represented using a **dendrogram**
A dendrogram is like a family tree for clusters. It shows how individual data points or groups of data merge together.
![image](https://github.com/user-attachments/assets/0d73c23b-9ca3-4a49-9f78-de0c57e38e00)


### Parameters

* `linkage`: 'ward', 'single', 'complete', 'average'
* `affinity`: Distance metric (`euclidean`, `manhattan`)
![image](https://github.com/user-attachments/assets/a3f77b15-c862-4ee9-ad5e-e9d9e767f5b1)

### Limitations

* Computationally expensive
* Hard to scale with large data

### Example

```python
from sklearn.cluster import AgglomerativeClustering
agg = AgglomerativeClustering(n_clusters=3, linkage='ward')
labels = agg.fit_predict(X)
```

---

## DBSCAN (Density-Based Spatial Clustering)

* 'Density-Based Spatial Clustering of Applications with Noise'.
* DBSCAN is a powerful density-based clustering algorithm that groups together points that are close in space and marks as outliers the points that lie alone in low-density regions.
* It identifies clusters as dense regions in the data space separated by areas of lower density.
* Clusters can take any shape not just circular or convex.
* Identifies noise/outliers
* No need to specify the number of clusters

### Parameters

* ε (epsilon) : Radius of neighborhood around a point
* minPts : Minimum number of points required to form a dense region
* Core Point : Has ≥ minPts points within ε
* Border Point :	Not a core point, but is within ε of a core point
* Noise Point : Neither core nor border (an outlier)
  ![image](https://github.com/user-attachments/assets/70538c45-c719-49ee-96b2-5e101ecb4206)

### How DBSCAN Works!
* For each point Count how many other points fall within its ε-radius.
* If count ≥ minPts → mark as a core point.
* Form a cluster from each core point and all reachable points.
* Border points are attached to their nearby core clusters.
* Noise points are ignored or marked as -1 (outliers).
![1_WunYbbKjzdXvw73a4Hd2ig](https://github.com/user-attachments/assets/46779132-d2dd-4098-820b-f2d152f3a2a7)

### Limitations

* Sensitive to eps value
* Poor performance in varying density

### Example

```python
from sklearn.cluster import DBSCAN
db = DBSCAN(eps=0.5, min_samples=5)
labels = db.fit_predict(X)
```

---

## Evaluating Clustering (No Labels)

| Metric               | Use                                                      |
| -------------------- | -------------------------------------------------------- |
| **Silhouette Score** | Measures separation distance between clusters            |
| **Davies-Bouldin**   | Lower is better — how similar clusters are to each other |
| **Inertia**          | Only for K-Means — total within-cluster distance         |

#### Silhouette Score
 
The silhouette score measures the similarity of each point to its own cluster compared to other clusters, and the silhouette plot visualizes these scores for each sample. 
A high silhouette score indicates that the clusters are well separated, and each sample is more similar to the samples in its own cluster than to samples in other clusters. 
A silhouette score close to 0 suggests overlapping clusters, and a negative score suggests poor clustering solutions.


```python
from sklearn.metrics import silhouette_score
score = silhouette_score(X, labels)
```

---

## Example Dataset

```python
import pandas as pd
df = pd.read_csv("Mall_Customers.csv")
X = df[["Annual Income (k$)", "Spending Score (1-100)"]]
```

---

## Choosing the Right Clustering Algorithm

| Criteria                     | Best Option          |
| ---------------------------- | -------------------- |
| Fast, simple                 | K-Means              |
| Nested/group structure       | Hierarchical         |
| Arbitrary shapes or outliers | DBSCAN               |
| High dimensionality          | GMM or PCA + K-Means |

We prefer to use DBSCAN when the data is not spherical in shape or the number of classes is not known beforehand. K-Means on the other hand is better suited for data with well-defined, spherical clusters and is less effective with noise or complex cluster structures.
![image](https://github.com/user-attachments/assets/67aa2084-eb9a-4cd1-b2fa-1a73bab21270)


---

## Tools & Libraries

* `scikit-learn` – KMeans, DBSCAN, Agglomerative
* `scipy` – Dendrogram for hierarchical
* `seaborn`, `matplotlib` – Visualization
* `yellowbrick` – Visual tools like elbow, silhouette plots

---

## Real-World Examples

* Segmenting retail customers based on behavior
* Grouping genes based on expression
* Brain scan pattern discovery
* Identifying similar photos (e.g., face groups)

---
```

