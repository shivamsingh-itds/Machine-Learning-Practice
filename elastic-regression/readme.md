# 🧠 Elastic Net Regression – Complete Notes

## 🔍 What is Elastic Net Regression?

Elastic Net Regression is a **regularization technique** that combines both:

- **Ridge Regression (L2 penalty)**  
- **Lasso Regression (L1 penalty)**  

In simple words:

> Elastic Net is a hybrid model that performs **both coefficient shrinking and feature selection**.

---

# 🎯 Why Do We Need Elastic Net?

Problems with Ridge and Lasso:

- **Ridge** → Cannot remove features (no feature selection)  
- **Lasso** → Unstable when features are highly correlated  

Elastic Net solves both problems:

- Handles **multicollinearity**
- Performs **feature selection**
- More stable than Lasso

---

# 📌 Elastic Net Cost Function

\[
J(\theta) = \sum (y_i - \hat{y_i})^2 
+ \lambda_1 \sum |\theta| 
+ \lambda_2 \sum \theta^2
\]

Where:

- \(y_i\) → Actual value  
- \(\hat{y_i}\) → Predicted value  
- \(\theta\) → Model coefficients  
- \(\lambda_1\) → L1 penalty (Lasso)  
- \(\lambda_2\) → L2 penalty (Ridge)  

---

# 📊 Key Idea

Elastic Net combines:

- L1 → Feature selection  
- L2 → Coefficient shrinking  

So it:

✔ Removes irrelevant features  
✔ Keeps correlated features stable  
✔ Reduces overfitting  

---

# 📉 Alpha and L1 Ratio

In sklearn, Elastic Net uses:

- **alpha** → Overall regularization strength  
- **l1_ratio** → Balance between L1 and L2  

| l1_ratio | Meaning |
|----------|--------|
| 0 | Pure Ridge |
| 1 | Pure Lasso |
| 0.5 | Equal mix |

---

# ⚙️ Elastic Net in Python

```python
from sklearn.linear_model import ElasticNet
from sklearn.model_selection import train_test_split

# Split dataset
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Create model
model = ElasticNet(alpha=1.0, l1_ratio=0.5)

# Train model
model.fit(X_train, y_train)

# Predictions
y_pred = model.predict(X_test)