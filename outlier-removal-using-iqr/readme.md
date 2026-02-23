#### Outlier removal using IQR# 🧠 Outlier Removal Using IQR (Interquartile Range)

## 🔍 What is an Outlier?

An outlier is a data point that is **significantly higher or lower** than most of the data.

Outliers can:
- Distort statistical measures
- Affect model performance
- Reduce prediction accuracy

---

# 📌 What is IQR?

IQR stands for **Interquartile Range**.

It measures the range of the **middle 50% of the data**.

\[
IQR = Q3 - Q1
\]

Where:
- **Q1 (25th percentile)** → Lower quartile  
- **Q3 (75th percentile)** → Upper quartile  
- **IQR** → Spread of middle 50% values  

---

# 📊 Understanding Quartiles

If data is sorted:

- Q1 → Value below which 25% of data lies  
- Q2 → Median (50%)  
- Q3 → Value below which 75% of data lies  

IQR focuses only on central data and ignores extremes.

---

# 🎯 Outlier Detection Rule (IQR Rule)

Lower Limit:
\[
Q1 - 1.5 \times IQR
\]

Upper Limit:
\[
Q3 + 1.5 \times IQR
\]

If a value is:
- Less than lower limit → Outlier  
- Greater than upper limit → Outlier  

---

# ⚙️ Steps to Remove Outliers Using IQR

1. Calculate Q1 (25th percentile).
2. Calculate Q3 (75th percentile).
3. Compute IQR = Q3 − Q1.
4. Calculate lower and upper limits.
5. Remove values outside the limits.

---

# 🧾 Example in Python

```python
import pandas as pd

Q1 = df['salary'].quantile(0.25)
Q3 = df['salary'].quantile(0.75)

IQR = Q3 - Q1

lower_limit = Q1 - 1.5 * IQR
upper_limit = Q3 + 1.5 * IQR

df_clean = df[(df['salary'] >= lower_limit) & 
              (df['salary'] <= upper_limit)]