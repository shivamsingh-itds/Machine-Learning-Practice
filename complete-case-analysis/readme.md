# 🧠 Complete Case Analysis (CCA) – Handling Missing Data

## 📌 Overview

This notebook demonstrates how to handle missing values using **Complete Case Analysis (CCA)** on the `data_science_job.csv` dataset and evaluates its impact on data distribution.

Complete Case Analysis means:

> Remove all rows that contain missing values in selected columns.

---

# 🔍 Step 1: Load and Explore the Dataset

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv('data_science_job.csv')
```

Initial checks performed:

```python
df.head()
df.shape
df.isnull().mean() * 100
```

Purpose:
- Understand dataset structure
- Identify missing value percentages
- Decide whether CCA is suitable

---

# 📊 Step 2: Select Columns with Low Missing Values

Columns selected where:
- Missing percentage < 5%
- Missing percentage > 0%

```python
cols = [var for var in df.columns 
        if df[var].isnull().mean() < 0.05 
        and df[var].isnull().mean() > 0]
```

Why?
- CCA is generally safe when missing data is small.

---

# 🧹 Step 3: Apply Complete Case Analysis

```python
new_df = df[cols].dropna()
```

This removes all rows that contain missing values in the selected columns.

Compare dataset size:

```python
df.shape, new_df.shape
```

Purpose:
- Measure how much data was lost.

---

# 📈 Step 4: Compare Numerical Distributions (Before vs After CCA)

Variables analyzed:
- training_hours
- city_development_index
- experience

Histogram comparison:

```python
df['training_hours'].hist(bins=50, density=True, color='red')
new_df['training_hours'].hist(bins=50, density=True, color='green')
```

Density plot comparison:

```python
df['training_hours'].plot.density(color='red')
new_df['training_hours'].plot.density(color='green')
```

Goal:
- Check whether CCA changes the distribution.
- Ensure no major distortion or bias is introduced.

---

# 📊 Step 5: Compare Categorical Variables

Variables analyzed:
- enrolled_university
- education_level

Proportion comparison:

```python
temp = pd.concat([
    df['education_level'].value_counts() / len(df),
    new_df['education_level'].value_counts() / len(new_df)
], axis=1)

temp.columns = ['original', 'cca']
```

Purpose:
- Compare percentage of each category.
- Detect any shift after removing missing rows.

---

# 📌 Key Concepts

## What is Complete Case Analysis (CCA)?

CCA removes all observations that contain missing values.

Only complete rows are kept for analysis.

---

# 🎯 When to Use CCA?

Use CCA when:

- Missing values are very small (< 5%)
- Missing data is random (MCAR)
- Dataset is large enough
- Distribution remains similar after removal

---

# ❌ When NOT to Use CCA?

Avoid CCA when:

- High percentage of missing values
- Data is not missing at random
- Dataset is small
- Removing rows changes distributions significantly

---

# ⭐ Advantages of CCA

- Simple to implement
- No artificial data added
- Easy to explain
- Fast computation

---

# ⚠ Disadvantages of CCA

- Data loss
- Reduced statistical power
- Risk of bias
- May remove important information

---

# 🔥 Final Takeaway

> Complete Case Analysis removes rows with missing values and is safe only when missing data is small and randomly distributed.  
> Always compare distributions before and after applying CCA to ensure no significant bias is introduced.