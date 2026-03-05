# 📊 Regression Metrics – Complete Notes

## 🔍 What are Regression Metrics?

Regression metrics are used to **evaluate the performance of regression models**.

Since regression predicts **continuous numerical values**, we measure **how close the predicted values are to the actual values**.

These metrics quantify the **prediction error** of the model.

---

# 🎯 Why Do We Need Regression Metrics?

Regression metrics help to:

- Measure model accuracy
- Compare different models
- Understand prediction errors
- Improve model performance

---

# 📌 Common Regression Metrics

The most commonly used regression metrics are:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score (Coefficient of Determination)
- Adjusted R²

---

# 1️⃣ Mean Absolute Error (MAE)

### Definition

MAE calculates the **average absolute difference between actual and predicted values**.

### Formula

\[
MAE = \frac{1}{n} \sum |Y_i - \hat{Y_i}|
\]

Where:

- \(Y_i\) → Actual value  
- \(\hat{Y_i}\) → Predicted value  
- n → Number of observations  

### Characteristics

- Easy to understand
- All errors are treated equally
- Less sensitive to outliers

---

# 2️⃣ Mean Squared Error (MSE)

### Definition

MSE calculates the **average of squared differences between actual and predicted values**.

### Formula

\[
MSE = \frac{1}{n} \sum (Y_i - \hat{Y_i})^2
\]

### Characteristics

- Penalizes large errors more
- Sensitive to outliers
- Used in many optimization algorithms

---

# 3️⃣ Root Mean Squared Error (RMSE)

### Definition

RMSE is the **square root of MSE**.

### Formula

\[
RMSE = \sqrt{\frac{1}{n} \sum (Y_i - \hat{Y_i})^2}
\]

### Characteristics

- Same unit as target variable
- More interpretable than MSE
- Penalizes large errors heavily

---

# 4️⃣ R² Score (Coefficient of Determination)

### Definition

R² measures how much variance in the target variable is explained by the model.

### Formula

\[
R^2 = 1 - \frac{SS_{res}}{SS_{tot}}
\]

Where:

- \(SS_{res}\) → Sum of squared residuals  
- \(SS_{tot}\) → Total sum of squares  

### Interpretation

| R² Value | Meaning |
|--------|---------|
| 1 | Perfect prediction |
| 0 | Model performs like mean prediction |
| < 0 | Model performs worse than baseline |

---

# 5️⃣ Adjusted R²

### Definition

Adjusted R² adjusts the R² score by considering the **number of features in the model**.

It prevents **artificial increase of R² when adding irrelevant variables**.

### Formula

\[
Adjusted\ R^2 = 1 - \left(\frac{(1-R^2)(n-1)}{n-p-1}\right)
\]

Where:

- n → Number of observations  
- p → Number of predictors  

---

# 📊 Example

Actual values:
```
[10, 20, 30]
```

Predicted values:
```
[12, 18, 33]
```

Errors:
```
[2, 2, 3]
```

MAE = average error  
MSE = average squared error  
RMSE = square root of MSE  

---

# ⚙️ Regression Metrics in Python

```python
from sklearn.metrics import mean_absolute_error
from sklearn.metrics import mean_squared_error
from sklearn.metrics import r2_score
import numpy as np

mae = mean_absolute_error(y_true, y_pred)

mse = mean_squared_error(y_true, y_pred)

rmse = np.sqrt(mse)

r2 = r2_score(y_true, y_pred)
```

---

# 📌 Comparison of Regression Metrics

| Metric | Sensitive to Outliers | Unit |
|------|----------------------|------|
| MAE | No | Same as target |
| MSE | Yes | Squared unit |
| RMSE | Yes | Same as target |
| R² | No | No unit |

---

# 🎯 When to Use Which Metric?

Use **MAE**:
- When equal importance to all errors

Use **RMSE**:
- When large errors are very bad

Use **R²**:
- To measure model explanatory power

Use **Adjusted R²**:
- When comparing models with different numbers of features

---

# 🔥 Key Takeaway

> Regression metrics measure how close predicted values are to actual values.  
> MAE, MSE, RMSE measure error magnitude, while R² explains how well the model fits the data.