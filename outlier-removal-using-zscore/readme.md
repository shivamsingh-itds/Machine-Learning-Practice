# 🧠 Outlier Removal Using Z-Score

## 🔍 What is an Outlier?

An outlier is a data point that is **very far away from most of the other data points**.

Example:
- Most salaries: 20,000 – 50,000  
- One salary: 5,00,000 → This is likely an outlier

Outliers can:
- Distort mean and standard deviation
- Affect model performance
- Reduce accuracy in some algorithms

---

# 📌 What is Z-Score?

Z-Score tells us:

> How many standard deviations a data point is away from the mean.

It standardizes values so we can compare them properly.

---

# 📐 Z-Score Formula

\[
Z = \frac{X - \mu}{\sigma}
\]

Where:
- X = Data point
- μ = Mean of the feature
- σ = Standard deviation
- Z = Z-score value

---

# 🧠 Interpretation of Z-Score

| Z-Score | Meaning |
|----------|----------|
| Z = 0 | Value is exactly at mean |
| Z = 1 | 1 standard deviation above mean |
| Z = -1 | 1 standard deviation below mean |
| Z > 3 or Z < -3 | Likely an outlier |

---

# 🎯 Rule for Outlier Detection

Common rule:

- If **|Z| > 3**, treat it as an outlier.
- Sometimes threshold 2.5 is also used.

This works well when data is **normally distributed**.

---

# ⚙️ Steps to Remove Outliers Using Z-Score

1. Calculate mean of the feature.
2. Calculate standard deviation.
3. Compute Z-score for each data point.
4. Remove rows where:
   - Z > 3
   - Z < -3

---

# 🧾 Example in Python

```python
import numpy as np
import pandas as pd

mean = df['salary'].mean()
std = df['salary'].std()

df['zscore'] = (df['salary'] - mean) / std

df_clean = df[(df['zscore'] < 3) & (df['zscore'] > -3)]