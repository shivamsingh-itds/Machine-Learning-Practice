# 🧠 K-Means Clustering – Complete Notes

## 🔍 What is K-Means?

K-Means is an **unsupervised machine learning algorithm** used for **clustering**.

It groups data points into **K clusters** based on similarity.

In simple terms:

> K-Means divides data into K groups such that similar points belong to the same cluster.

---

# 🎯 Why Do We Use K-Means?

Used when:

- No labels are available (unsupervised learning)
- Want to find hidden patterns
- Need to group similar data points

Examples:
- Customer segmentation
- Image compression
- Market analysis

---

# 📌 Key Idea

K-Means tries to:

- Minimize distance between points and cluster center
- Maximize similarity within a cluster

---

# ⚙️ How K-Means Works (Step-by-Step)

1️⃣ Choose number of clusters (K)

2️⃣ Initialize K centroids randomly

3️⃣ Assign each data point to nearest centroid

4️⃣ Update centroids (mean of assigned points)

5️⃣ Repeat steps 3 and 4 until convergence

---

# 📊 Distance Metric

Usually uses **Euclidean Distance**:

\[
d = \sqrt{(x_1 - x_2)^2 + (y_1 - y_2)^2}
\]

Points are assigned to the closest centroid.

---

# 📉 Objective Function (Inertia)

K-Means minimizes:

\[
\sum (distance\ between\ points\ and\ their\ centroid)^2
\]

This is called **Within Cluster Sum of Squares (WCSS)**.

---

# 📌 Choosing Optimal K

## 1️⃣ Elbow Method

- Plot K vs WCSS
- Choose point where curve bends (elbow)

---

## 2️⃣ Silhouette Score

- Measures cluster quality
- Value between -1 to 1

---

# ⚙️ K-Means in Python

```python
from sklearn.cluster import KMeans

# Create model
kmeans = KMeans(n_clusters=3)

# Fit model
kmeans.fit(X)

# Cluster labels
labels = kmeans.labels_

# Centroids
centroids = kmeans.cluster_centers_