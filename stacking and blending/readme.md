# 🧠 Stacking & Blending – Ensemble Learning Techniques

## 🔍 What are Stacking and Blending?

Stacking and Blending are **ensemble learning techniques** used to combine multiple models to improve performance.

In simple terms:

> Instead of relying on one model, combine multiple models to get better predictions.

---

# 🎯 Why Use Ensemble Methods?

Single models may:

- Overfit or underfit
- Miss patterns in data
- Have high variance or bias

Ensemble methods help to:

- Improve accuracy
- Reduce errors
- Combine strengths of different models

---

# 📌 What is Stacking?

Stacking (Stacked Generalization) is an ensemble technique where:

- Multiple base models are trained
- Their predictions are used as input to a **meta-model**
- The meta-model makes the final prediction

---

# ⚙️ How Stacking Works

## Step-by-Step:

1️⃣ Train multiple base models (Level-0 models)

Examples:
- Logistic Regression
- Decision Tree
- Random Forest

2️⃣ Make predictions using these models

3️⃣ Use these predictions as new features

4️⃣ Train a meta-model (Level-1 model)

5️⃣ Meta-model gives final prediction

---

# 📊 Stacking Architecture


Input Data
↓
Base Models (Level-0)
↓
Predictions
↓
Meta Model (Level-1)
↓
Final Output


---

# 📌 Example

Base Models:
- Model A → predicts 0.7  
- Model B → predicts 0.6  
- Model C → predicts 0.8  

Meta Model:
- Takes [0.7, 0.6, 0.8]
- Produces final prediction

---

# ⚙️ Stacking in Python

```python
from sklearn.ensemble import StackingClassifier
from sklearn.linear_model import LogisticRegression
from sklearn.tree import DecisionTreeClassifier

estimators = [
    ('dt', DecisionTreeClassifier()),
    ('lr', LogisticRegression())
]

model = StackingClassifier(
    estimators=estimators,
    final_estimator=LogisticRegression()
)

model.fit(X_train, y_train)# 🧠 Stacking & Blending – Ensemble Learning Techniques

## 🔍 What are Stacking and Blending?

Stacking and Blending are **ensemble learning techniques** used to combine multiple models to improve performance.

In simple terms:

> Instead of relying on one model, combine multiple models to get better predictions.

---

# 🎯 Why Use Ensemble Methods?

Single models may:

- Overfit or underfit
- Miss patterns in data
- Have high variance or bias

Ensemble methods help to:

- Improve accuracy
- Reduce errors
- Combine strengths of different models

---

# 📌 What is Stacking?

Stacking (Stacked Generalization) is an ensemble technique where:

- Multiple base models are trained
- Their predictions are used as input to a **meta-model**
- The meta-model makes the final prediction

---

# ⚙️ How Stacking Works

## Step-by-Step:

1️⃣ Train multiple base models (Level-0 models)

Examples:
- Logistic Regression
- Decision Tree
- Random Forest

2️⃣ Make predictions using these models

3️⃣ Use these predictions as new features

4️⃣ Train a meta-model (Level-1 model)

5️⃣ Meta-model gives final prediction

---

# 📊 Stacking Architecture


Input Data
↓
Base Models (Level-0)
↓
Predictions
↓
Meta Model (Level-1)
↓
Final Output


---

# 📌 Example

Base Models:
- Model A → predicts 0.7  
- Model B → predicts 0.6  
- Model C → predicts 0.8  

Meta Model:
- Takes [0.7, 0.6, 0.8]
- Produces final prediction

---

# ⚙️ Stacking in Python

```python
from sklearn.ensemble import StackingClassifier
from sklearn.linear_model import LogisticRegression
from sklearn.tree import DecisionTreeClassifier

estimators = [
    ('dt', DecisionTreeClassifier()),
    ('lr', LogisticRegression())
]

model = StackingClassifier(
    estimators=estimators,
    final_estimator=LogisticRegression()
)

model.fit(X_train, y_train)