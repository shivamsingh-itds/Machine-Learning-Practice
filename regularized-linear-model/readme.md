# 🧠 Ridge Regression – Complete Notes

## 🔍 What is Ridge Regression?

Ridge Regression is a **regularization technique used with Linear Regression** to reduce **overfitting**.

It modifies the linear regression model by adding a **penalty term to the cost function**, which shrinks the model coefficients.

In simple terms:

> Ridge Regression keeps the model simple by penalizing large coefficient values.

---

# 🎯 Why Do We Need Ridge Regression?

In normal Linear Regression:

- The model may **overfit the training data**.
- Features may be **highly correlated (multicollinearity)**.
- Model coefficients may become **very large and unstable**.

Ridge Regression helps to:

- Reduce overfitting
- Handle multicollinearity
- Improve generalization of the model

---

# 📌 Ridge Regression Cost Function

### Linear Regression Cost Function

\[
J(\theta) = \sum (y_i - \hat{y_i})^2
\]

### Ridge Regression Cost Function

\[
J(\theta) = \sum (y_i - \hat{y_i})^2 + \lambda \sum \theta^2
\]

Where:

- \(y_i\) → Actual value  
- \(\hat{y_i}\) → Predicted value  
- \(\theta\) → Model coefficients  
- \(\lambda\) → Regularization parameter  

---

# 📊 Understanding the Penalty Term

\[
\lambda \sum \theta^2
\]

This term penalizes **large coefficient values**.

Effects:

- Coefficients shrink toward zero
- Model becomes simpler
- Overfitting reduces

---

# 📉 Role of Lambda (λ)

Lambda controls the **strength of regularization**.

| Lambda Value | Effect |
|---------------|--------|
| λ = 0 | Same as Linear Regression |
| Small λ | Slight regularization |
| Large λ | Strong regularization |

If λ becomes too large:

- Model may **underfit**.

---

# 📈 Bias–Variance Tradeoff

Ridge Regression introduces:

- Slight **increase in bias**
- Large **reduction in variance**

This improves model stability.

---

# 📌 Ridge vs Linear Regression

| Feature | Linear Regression | Ridge Regression |
|--------|------------------|----------------|
| Regularization | No | Yes |
| Overfitting | High risk | Reduced |
| Multicollinearity | Problematic | Handles well |
| Coefficients | Can become large | Shrinks coefficients |

---

# ⚙️ Ridge Regression in Python

```python
from sklearn.linear_model import Ridge
from sklearn.model_selection import train_test_split

# Split dataset
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Create model
ridge = Ridge(alpha=1.0)

# Train model
ridge.fit(X_train, y_train)

# Predictions
y_pred = ridge.predict(X_test)