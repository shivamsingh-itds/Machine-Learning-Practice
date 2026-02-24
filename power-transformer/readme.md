# 🧠 PowerTransformer in Machine Learning

## 🔍 What is PowerTransformer?

`PowerTransformer` is a preprocessing technique in scikit-learn used to:

- Make data **more normally distributed**
- Reduce **skewness**
- Stabilize variance

It applies a mathematical transformation to improve model performance.

---

# 🎯 Why Do We Need Power Transformation?

Many ML algorithms assume:
- Data is normally distributed
- Variance is constant

But real-world data is often:
- Right skewed (income, salary, population)
- Left skewed
- Heteroscedastic (unequal variance)

PowerTransformer helps to:
- Reduce skewness
- Improve symmetry
- Improve model accuracy

---

# 📌 Types of Power Transformation

There are two types in scikit-learn:

## 1️⃣ Yeo-Johnson (Default)
- Works with both positive and negative values.
- Most commonly used.

## 2️⃣ Box-Cox
- Works only with positive values.
- Cannot handle zero or negative values.

---

# ⚙️ How PowerTransformer Works

It applies a mathematical power function:

- Adjusts shape of distribution.
- Tries to make data closer to normal distribution.
- Learns transformation parameter (lambda).

The transformation is automatically optimized during fitting.

---

# 🧾 Basic Usage in scikit-learn

```python
from sklearn.preprocessing import PowerTransformer

pt = PowerTransformer(method='yeo-johnson')

X_transformed = pt.fit_transform(X)
