# 🧠 Iterative Imputer – Important Notes

## 🔍 What is Iterative Imputer?

`IterativeImputer` is an advanced missing value handling technique in scikit-learn.

Instead of filling missing values using simple methods like:
- Mean
- Median
- Most frequent

It predicts missing values using other features in the dataset.

It is based on the idea:
> Use available columns to predict the missing values of another column.

It is conceptually similar to MICE (Multivariate Imputation by Chained Equations).

---

# 🎯 Why Use Iterative Imputer?

Basic imputation:
- Uses only one column to fill missing values.
- Ignores relationships between features.

Iterative Imputer:
- Uses relationships between multiple columns.
- Produces more realistic and accurate imputations.
- Works well when features are correlated.

---

# ⚙️ How Iterative Imputer Works (Step-by-Step)

1. First, fill all missing values using simple imputation (usually mean).  
   → This is called the initial imputation (0th iteration).

2. Select one column that has missing values.

3. Treat that column as the target variable (y).

4. Use remaining columns as input features (X).

5. Train a regression model to predict missing values.

6. Replace missing values with predicted values.

7. Repeat this process for each column with missing values.

8. One full cycle over all columns = 1 iteration.

9. Repeat iterations until:
   - Values converge (stabilize), or  
   - Maximum iterations (`max_iter`) are reached.

---

# 🔁 Important Concept: Round-Robin Method

- Columns are imputed one by one.
- After each full cycle, predictions improve.
- Process continues iteratively.

---

# 🧾 Basic Usage in scikit-learn

```python
from sklearn.experimental import enable_iterative_imputer
from sklearn.impute import IterativeImputer

imputer = IterativeImputer(random_state=42)
imputed_data = imputer.fit_transform(data)