# 🚀 Gradient Boosting – Complete Notes

## 🔍 What is Gradient Boosting?

Gradient Boosting is an **ensemble machine learning technique** that builds models **sequentially**, where each new model tries to **correct the errors of the previous one**.

It is mainly based on:
- **Decision Trees (weak learners)**
- **Boosting technique**

In simple terms:

> Gradient Boosting builds models one after another, each focusing on reducing the mistakes of the previous model.

---

# 🎯 Why Do We Need Gradient Boosting?

Single models may:
- Underfit data
- Miss complex patterns

Gradient Boosting helps to:
- Improve accuracy
- Reduce bias and variance
- Capture complex relationships

---

# 📌 Core Idea

Instead of building trees independently (like Random Forest), Gradient Boosting builds trees **sequentially**.

Each new tree:
- Learns from previous errors
- Focuses on difficult data points

---

# ⚙️ How Gradient Boosting Works

## Step-by-Step:

1️⃣ Start with a simple model (initial prediction, usually mean)

2️⃣ Calculate errors (residuals):

Error = Actual - Predicted


3️⃣ Train a new model on these errors

4️⃣ Add this new model to the previous one

5️⃣ Repeat steps multiple times

---

# 📊 Final Prediction

Final output is the **sum of all models**:

\[
Final Prediction = Model_1 + Model_2 + Model_3 + ...
\]

Each model improves the previous one.

---

# 📉 Why "Gradient"?

- Uses **Gradient Descent** to minimize the loss function
- Each step moves in direction of **minimum error**

---

# 📌 Key Concepts

## 1️⃣ Weak Learners

- Usually shallow decision trees
- Individually weak but powerful when combined

---

## 2️⃣ Residual Learning

- Models are trained on **errors of previous models**

---

## 3️⃣ Learning Rate (η)

- Controls contribution of each tree

| Learning Rate | Effect |
|--------------|--------|
| Small | Slow but accurate |
| Large | Fast but may overfit |

---

# ⚙️ Gradient Boosting in Python

```python
from sklearn.ensemble import GradientBoostingClassifier
from sklearn.model_selection import train_test_split

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Create model
model = GradientBoostingClassifier(n_estimators=100, learning_rate=0.1)

# Train model
model.fit(X_train, y_train)

# Predict
y_pred = model.predict(X_test)