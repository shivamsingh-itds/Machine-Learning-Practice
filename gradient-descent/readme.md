# 🧠 Gradient Descent – Complete Notes

## 🔍 What is Gradient Descent?

Gradient Descent is an **optimization algorithm** used in Machine Learning to **minimize the loss (cost) function**.

It helps the model find the **best parameters (weights and bias)** that reduce prediction error.

In simple words:

> Gradient Descent repeatedly adjusts model parameters to reduce the error between predicted and actual values.

---

# 🎯 Why Do We Need Gradient Descent?

When training a machine learning model, we need to:

- Find the best parameters
- Minimize the cost function
- Improve model predictions

Gradient Descent helps by **moving towards the lowest point of the cost function (minimum error).**

---

# 📉 Conceptual Idea

Imagine standing on a mountain and trying to reach the **lowest valley**.

Steps:

1. Check the slope of the mountain.
2. Move in the direction of the steepest downward slope.
3. Repeat until you reach the lowest point.

That lowest point is called the **global minimum**.

---

# 📌 Cost Function

Gradient Descent works by minimizing a **cost function**.

For Linear Regression:

\[
J(\theta) = \frac{1}{2m} \sum (h_\theta(x) - y)^2
\]

Where:

- \(J(\theta)\) → Cost function
- \(m\) → Number of training examples
- \(h_\theta(x)\) → Predicted value
- \(y\) → Actual value

Goal:
Minimize \(J(\theta)\).

---

# 📐 Gradient Descent Update Rule

Parameters are updated using:

\[
\theta = \theta - \alpha \frac{\partial J(\theta)}{\partial \theta}
\]

Where:

- \(\theta\) → Model parameter (weight)
- \(\alpha\) → Learning rate
- \(\frac{\partial J}{\partial \theta}\) → Gradient (slope)

This formula moves parameters **towards lower error**.

---

# ⚙️ Steps of Gradient Descent

1. Initialize parameters randomly.
2. Calculate predictions.
3. Compute cost function.
4. Calculate gradient (slope).
5. Update parameters using update rule.
6. Repeat until convergence.

---

# 📊 Learning Rate (α)

Learning rate controls **how big each step is during optimization**.

### Small Learning Rate

- Very slow learning
- Takes many iterations

### Large Learning Rate

- May overshoot minimum
- Can cause divergence

Choosing correct learning rate is important.

---

# 📉 Types of Gradient Descent

## 1️⃣ Batch Gradient Descent

- Uses **entire dataset** to update parameters.
- Stable but slow.

Characteristics:
- Accurate updates
- High computation cost

---

## 2️⃣ Stochastic Gradient Descent (SGD)

- Updates parameters using **one data point at a time**.

Characteristics:
- Faster updates
- Noisy updates
- Good for large datasets

---

## 3️⃣ Mini-Batch Gradient Descent

- Uses **small batches of data**.

Characteristics:
- Balance between batch and stochastic
- Most commonly used in deep learning

---

# 📊 Visualization Idea

Cost function graph:

```
Cost
  |
  |      *
  |     *
  |    *
  |   *
  |  *
  | *
  |*__________
        Parameters
```

Gradient descent moves **down the curve** toward minimum.

---

# ⚙️ Gradient Descent in Python (Conceptual)

```python
learning_rate = 0.01
iterations = 1000

for i in range(iterations):
    
    predictions = X.dot(theta)
    
    errors = predictions - y
    
    gradient = X.T.dot(errors) / len(y)
    
    theta = theta - learning_rate * gradient
```

---

# ⭐ Advantages

- Efficient for large datasets
- Works for many ML models
- Simple mathematical concept
- Scales well with data

---

# ⚠ Disadvantages

- Sensitive to learning rate
- Can get stuck in local minima
- Requires feature scaling
- May take many iterations

---

# 📌 When to Use Gradient Descent?

Used in many ML algorithms:

- Linear Regression
- Logistic Regression
- Neural Networks
- Deep Learning models

---

# 🔥 Key Takeaway

> Gradient Descent is an optimization algorithm that minimizes the cost function by iteratively adjusting model parameters in the direction of the steepest decrease in error.