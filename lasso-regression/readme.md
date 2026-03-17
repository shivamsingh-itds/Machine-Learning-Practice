# 🧠 Lasso Regression – Complete Notes

## 🔍 What is Lasso Regression?

Lasso Regression (Least Absolute Shrinkage and Selection Operator) is a **regularization technique** used in Linear Regression.

It adds a **penalty term (L1 penalty)** to the cost function, which can shrink some coefficients **exactly to zero**.

In simple words:

> Lasso Regression not only reduces overfitting but also performs **feature selection**.

---

# 🎯 Why Do We Need Lasso Regression?

In Linear Regression:

- Model may overfit
- Features may be irrelevant
- Too many features increase complexity

Lasso helps to:

- Reduce overfitting
- Remove unnecessary features
- Simplify the model
- Improve interpretability

---

# 📌 Lasso Regression Cost Function

\[
J(\theta) = \sum (y_i - \hat{y_i})^2 + \lambda \sum |\theta|
\]

Where:

- \(y_i\) → Actual value  
- \(\hat{y_i}\) → Predicted value  
- \(\theta\) → Model coefficients  
- \(\lambda\) → Regularization parameter  

---

# 📊 Understanding L1 Penalty

\[
\lambda \sum |\theta|
\]

Effects:

- Shrinks coefficients
- Some coefficients become exactly **0**
- Automatically removes less important features

---

# 📉 Role of Lambda (λ)

| Lambda Value | Effect |
|--------------|--------|
| λ = 0 | Same as Linear Regression |
| Small λ | Slight regularization |
| Large λ | More coefficients become zero |

If λ is too large:

- Model may underfit

---

# 📈 Feature Selection Property

Key advantage of Lasso:

✔ Automatically selects important features  
✔ Removes irrelevant features  
✔ Produces sparse models  
