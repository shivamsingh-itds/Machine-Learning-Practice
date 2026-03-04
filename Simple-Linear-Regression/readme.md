# 🧠 Linear Regression – Complete Notes

## 🔍 What is Linear Regression?

Linear Regression is a **supervised machine learning algorithm** used to predict **continuous numerical values**.

It finds the **best linear relationship between input features (X) and the target variable (Y)**.

In simple terms:

> Linear Regression fits a straight line that best represents the relationship between input and output.

Example:
- Predicting house price based on size
- Predicting salary based on experience
- Predicting sales based on advertising budget

---

# 📈 Linear Regression Equation

The basic equation of linear regression is:

\[
Y = \beta_0 + \beta_1X + \epsilon
\]

Where:

- **Y** → Dependent variable (target)
- **X** → Independent variable (feature)
- **β₀** → Intercept (value of Y when X = 0)
- **β₁** → Slope (change in Y for unit change in X)
- **ε** → Error term

---

# 📊 Simple Linear Regression

When there is **only one independent variable**, it is called **Simple Linear Regression**.

Example:

Predicting salary using experience.

```
Salary = β₀ + β₁(Experience)
```

Graphically:
- Straight line representing relationship between X and Y.

---

# 📊 Multiple Linear Regression

When there are **multiple input features**, it is called **Multiple Linear Regression**.

Equation:

\[
Y = \beta_0 + \beta_1X_1 + \beta_2X_2 + ... + \beta_nX_n
\]

Example:
Predict house price using:

- Area
- Number of rooms
- Location
- Age of house

---

# 🎯 Objective of Linear Regression

The goal is to find the **best fitting line** that minimizes prediction errors.

This is done using:

> **Ordinary Least Squares (OLS)**

OLS minimizes the **sum of squared residuals (errors)**.

---

# 📉 Residual (Error)

Residual is the difference between:

```
Actual Value - Predicted Value
```

\[
Residual = Y_{actual} - Y_{predicted}
\]

The regression line tries to **minimize these residuals**.

---

# 📐 Cost Function

Linear regression minimizes the **Mean Squared Error (MSE)**.

\[
MSE = \frac{1}{n} \sum (Y_i - \hat{Y_i})^2
\]

Where:

- \(Y_i\) → Actual value
- \(\hat{Y_i}\) → Predicted value
- n → Number of observations

---

# ⚙️ Training Linear Regression Model

Steps:

1. Collect dataset
2. Split into training and testing sets
3. Train the model
4. Make predictions
5. Evaluate performance

---

# 🧾 Linear Regression in Python

```python
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split

# split dataset
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# create model
model = LinearRegression()

# train model
model.fit(X_train, y_train)

# prediction
y_pred = model.predict(X_test)
```

---

# 📊 Evaluation Metrics

Common metrics used:

### Mean Absolute Error (MAE)

\[
MAE = \frac{1}{n} \sum |Y - \hat{Y}|
\]

### Mean Squared Error (MSE)

\[
MSE = \frac{1}{n} \sum (Y - \hat{Y})^2
\]

### Root Mean Squared Error (RMSE)

\[
RMSE = \sqrt{MSE}
\]

### R² Score (Coefficient of Determination)

Measures how well model explains variance.

```
R² = 0 → Poor model
R² = 1 → Perfect model
```

---

# 📌 Assumptions of Linear Regression

Linear regression works best when these assumptions hold:

1️⃣ **Linearity**  
Relationship between X and Y should be linear.

2️⃣ **No Multicollinearity**  
Independent variables should not be highly correlated.

3️⃣ **Homoscedasticity**  
Constant variance of residuals.

4️⃣ **Normal Distribution of Errors**

5️⃣ **Independence of Errors**

---

# 📈 When to Use Linear Regression?

Use when:

- Target variable is continuous
- Relationship between variables is linear
- Dataset size is moderate
- Interpretability is important

---

# ❌ When NOT to Use Linear Regression?

Avoid when:

- Relationship is non-linear
- Too many outliers
- Features are highly correlated
- Target variable is categorical

---

# ⭐ Advantages

- Simple and easy to understand
- Fast training
- Highly interpretable
- Works well with small datasets

---

# ⚠ Disadvantages

- Sensitive to outliers
- Assumes linear relationship
- Not suitable for complex patterns
- Performance decreases with multicollinearity

---

# 🔥 Key Takeaway

> Linear Regression predicts continuous values by fitting the best straight line that minimizes the difference between actual and predicted values.