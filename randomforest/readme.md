# 🌲 Random Forest – Complete Notes

## 🔍 What is Random Forest?

Random Forest is an **ensemble machine learning algorithm** that builds **multiple decision trees** and combines their results.

It is used for both:
- **Classification**
- **Regression**

In simple terms:

> Random Forest = Many Decision Trees + Majority Voting / Averaging

---

# 🎯 Why Do We Need Random Forest?

Problems with a single Decision Tree:

- Overfitting
- High variance
- Sensitive to data changes

Random Forest solves this by:

- Combining multiple trees
- Reducing overfitting
- Improving accuracy and stability

---

# 🌳 How Random Forest Works

## Step-by-Step Process:

1️⃣ Create multiple random subsets of the dataset (Bootstrap Sampling)

2️⃣ For each subset:
- Build a Decision Tree

3️⃣ At each split:
- Select a **random subset of features**

4️⃣ Train multiple trees independently

5️⃣ Final Prediction:

- **Classification** → Majority Voting  
- **Regression** → Average of outputs  

---

# 📊 Key Concepts

## 1️⃣ Bootstrap Sampling

- Random sampling with replacement
- Each tree gets different data

---

## 2️⃣ Feature Randomness

- At each split, only a subset of features is considered
- Makes trees different from each other

---

## 3️⃣ Ensemble Learning

- Combines predictions from multiple models
- Improves overall performance

---

# 📌 Random Forest vs Decision Tree

| Feature | Decision Tree | Random Forest |
|--------|--------------|--------------|
| Overfitting | High | Low |
| Accuracy | Moderate | High |
| Stability | Low | High |
| Complexity | Simple | Complex |

---

# ⚙️ Random Forest in Python

```python
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Create model
model = RandomForestClassifier(n_estimators=100)

# Train model
model.fit(X_train, y_train)

# Predict
y_pred = model.predict(X_test)