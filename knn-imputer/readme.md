# KNN Imputer 

## 🔍 What is KNN Imputer?

`KNNImputer` is a missing value handling technique in scikit-learn that uses the **K-Nearest Neighbors algorithm** to fill missing values.

Instead of using mean or median, it:
> Finds similar rows (neighbors) and fills missing values using their values.

---

# 🎯 Why Use KNN Imputer?

Simple imputation:
- Uses only column statistics (mean/median).
- Ignores relationships between rows.

KNN Imputer:
- Uses similarity between data points.
- Produces more realistic imputations.
- Works well when similar samples have similar values.

---

# ⚙️ How KNN Imputer Works (Step-by-Step)

1. Choose the number of neighbors (k).

2. For a row with a missing value:
   - Find the k nearest rows using distance (usually Euclidean distance).
   - Distance is calculated using available (non-missing) features.

3. Take the average (or weighted average) of the neighbors.

4. Replace the missing value with that average.

---

# 📌 Example

Suppose we have:

| Age | Salary |
|-----|--------|
| 25  | 30000  |
| 30  | 40000  |
| 28  | ?      |

If k = 2:

- Find 2 nearest neighbors based on Age.
- Their Salary values: 30000 and 40000.
- Imputed Salary = (30000 + 40000) / 2 = 35000.

---

# 🧾 Basic Usage in scikit-learn

```python
from sklearn.impute import KNNImputer

imputer = KNNImputer(n_neighbors=5)
imputed_data = imputer.fit_transform(data)