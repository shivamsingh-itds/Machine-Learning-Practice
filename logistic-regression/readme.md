# 🧠 Logistic Regression – Complete Notes

## 🔍 What is Logistic Regression?

Logistic Regression is a **supervised machine learning algorithm** used for **classification problems**.

Instead of predicting continuous values, it predicts **probabilities of classes**.

In simple words:

> Logistic Regression predicts the probability that an input belongs to a particular class.

---

# 🎯 Why Do We Need Logistic Regression?

Linear Regression is not suitable for classification because:

- It can predict values outside [0,1]
- It does not model probabilities correctly

Logistic Regression solves this by:

- Using a **sigmoid function**
- Converting output into probabilities

---

# 📌 Sigmoid (Logistic) Function

The sigmoid function maps any value into the range (0,1):

\[
\sigma(z) = \frac{1}{1 + e^{-z}}
\]

Where:

- \(z = \beta_0 + \beta_1X\)

Output:
- Value between 0 and 1 → Probability

---

# 📊 How Prediction Works

Step 1: Compute linear combination  
\[
z = \beta_0 + \beta_1X
\]

Step 2: Apply sigmoid function  
\[
p = \sigma(z)
\]

Step 3: Convert probability to class  

| Probability | Class |
|-------------|-------|
| p ≥ 0.5 | Class 1 |
| p < 0.5 | Class 0 |

---

# 📈 Logistic Regression Equation

\[
p = \frac{1}{1 + e^{-(\beta_0 + \beta_1X)}}
\]

This gives probability of class = 1.

---

# 📉 Log-Odds (Logit Function)

Logistic Regression models **log-odds**:

\[
\log\left(\frac{p}{1-p}\right) = \beta_0 + \beta_1X
\]

This converts probability into a linear relationship.

---

# ⚙️ Cost Function (Log Loss)

Logistic Regression uses **log loss (cross-entropy loss)**:

\[
Loss = -\frac{1}{n} \sum [y \log(p) + (1-y)\log(1-p)]
\]

Where:

- \(y\) → Actual label  
- \(p\) → Predicted probability  

Goal:
- Minimize this loss

---

# 🔁 Optimization

Uses **Gradient Descent** to minimize the loss function.

---

# 📊 Types of Logistic Regression

## 1️⃣ Binary Logistic Regression
- Two classes (0 or 1)

## 2️⃣ Multiclass Logistic Regression
- More than two classes (uses softmax)

## 3️⃣ Multinomial Logistic Regression
- Predicts multiple categories

---

# ⚙️ Logistic Regression in Python

```python
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split

# Split dataset
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Create model
model = LogisticRegression()

# Train model
model.fit(X_train, y_train)

# Predictions
y_pred = model.predict(X_test)

# Probabilities
y_prob = model.predict_proba(X_test)