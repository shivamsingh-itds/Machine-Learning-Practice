# 🧠 Logistic Regression – Complete Notes

## 🔍 What is Logistic Regression?

Logistic Regression is a **supervised machine learning algorithm** used for **classification problems**.

It predicts the **probability that a data point belongs to a class** (usually 0 or 1).

In simple terms:

> Logistic Regression predicts probability and converts it into a class label.

---

# 🎯 Why Not Linear Regression for Classification?

Linear Regression:
- Outputs values from (-∞ to +∞)
- Not suitable for probability

Logistic Regression:
- Uses a function that outputs values between **0 and 1**
- Suitable for classification

---

# 📌 Sigmoid Function

Logistic Regression uses the **Sigmoid (Logistic) Function**:

\[
\sigma(z) = \frac{1}{1 + e^{-z}}
\]

Where:

\[
z = \beta_0 + \beta_1X
\]

Output:
- Always between 0 and 1
- Represents probability

---

# 📊 Prediction Process

1. Compute linear equation:
\[
z = \beta_0 + \beta_1X
\]

2. Apply sigmoid:
\[
p = \frac{1}{1 + e^{-z}}
\]

3. Convert probability to class:

| Probability | Output |
|------------|--------|
| ≥ 0.5 | Class 1 |
| < 0.5 | Class 0 |

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

This converts a non-linear problem into a linear one.

---

# 📐 Cost Function (Log Loss)

Logistic Regression uses **Log Loss (Cross-Entropy Loss)**:

\[
Loss = -\frac{1}{n} \sum [y \log(p) + (1-y)\log(1-p)]
\]

Goal:
- Minimize loss

---

# 🔁 Optimization

- Uses **Gradient Descent** to update parameters
- Minimizes loss function

---

# 📊 Types of Logistic Regression

## 1️⃣ Binary Logistic Regression
- Two classes (0 or 1)

## 2️⃣ Multiclass Logistic Regression
- More than two classes

## 3️⃣ Multinomial Logistic Regression
- Uses softmax for multiple classes

---

# ⚙️ Logistic Regression in Python

```python
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Create model
model = LogisticRegression()

# Train
model.fit(X_train, y_train)

# Predict
y_pred = model.predict(X_test)

# Probability
y_prob = model.predict_proba(X_test)