# 🧠 Principal Component Analysis (PCA) – Complete Notes

## 🔍 What is PCA?

Principal Component Analysis (PCA) is a **dimensionality reduction technique** used in Machine Learning.

It transforms large sets of correlated features into a smaller set of uncorrelated variables called:

> Principal Components

These components retain most of the important information (variance) from the original data.

---

# 🎯 Why Do We Need PCA?

In real-world datasets:
- There may be too many features.
- Features may be highly correlated.
- High dimensional data increases computation cost.
- Models may suffer from overfitting.

PCA helps to:

- Reduce number of features
- Remove multicollinearity
- Improve model performance
- Reduce noise
- Speed up training

---

# 📌 What Are Principal Components?

Principal Components are:

- New features created from original features.
- Linear combinations of original variables.
- Ordered by importance (variance explained).

Important properties:
- PC1 captures maximum variance.
- PC2 captures second highest variance.
- PCs are orthogonal (uncorrelated).

---

# 📐 Mathematical Idea (Simple Understanding)

Steps PCA follows:

1️⃣ Standardize the data  
2️⃣ Compute covariance matrix  
3️⃣ Calculate eigenvalues & eigenvectors  
4️⃣ Select top k eigenvectors  
5️⃣ Transform original data onto new feature space  

Eigenvectors → Direction of maximum variance  
Eigenvalues → Amount of variance captured  

---

# ⚙️ Steps to Perform PCA

1. Scale the data (important step)
2. Apply PCA
3. Choose number of components
4. Transform the dataset

---

# 🧾 PCA in Python (scikit-learn)

```python
from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA

# Step 1: Standardize
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# Step 2: Apply PCA
pca = PCA(n_components=2)
X_pca = pca.fit_transform(X_scaled)
```

---

# 📊 Explained Variance

To check how much information is retained:

```python
pca.explained_variance_ratio_
```

Example output:
```
[0.75, 0.20]
```

Meaning:
- PC1 explains 75% variance
- PC2 explains 20% variance
- Total = 95% retained

---

# 📌 Choosing Number of Components

Common methods:

- Explained variance threshold (e.g., 95%)
- Scree plot
- Elbow method

Example:

```python
pca = PCA(n_components=0.95)
```

This keeps enough components to explain 95% variance.

---

# 📈 When to Use PCA?

Use PCA when:

- High dimensional dataset
- Features are correlated
- Want to reduce overfitting
- Need visualization (2D or 3D projection)
- Speed up model training

---

# ❌ When NOT to Use PCA?

Avoid PCA when:

- Interpretability is very important
- Dataset is small
- Using tree-based models (Decision Trees, Random Forest)
- Features are already independent

---

# ⭐ Advantages of PCA

- Reduces dimensionality
- Removes multicollinearity
- Improves performance
- Speeds up training
- Helps in visualization
- Reduces noise

---

# ⚠ Disadvantages of PCA

- Loss of interpretability
- Information loss (if too many components removed)
- Assumes linear relationships
- Requires scaling

---

# 🔄 PCA vs Feature Selection

| PCA | Feature Selection |
|------|------------------|
| Creates new features | Selects existing features |
| Reduces dimension mathematically | Removes irrelevant features |
| Hard to interpret | Easy to interpret |

---

# 🔥 Key Takeaway

> PCA reduces dimensionality by transforming correlated features into a smaller set of uncorrelated principal components while preserving maximum variance in the data.