# 📊 Classification Metrics – Complete Notes

## 🔍 What are Classification Metrics?

Classification metrics are used to **evaluate the performance of classification models**.

Since classification predicts **categories (classes)**, we measure how well the model correctly classifies data points.

---

# 🎯 Why Do We Need Classification Metrics?

- Accuracy alone is not enough (especially for imbalanced data)
- Helps understand model performance in detail
- Evaluates different types of errors
- Helps choose the best model

---

# 📌 Confusion Matrix (Foundation)

A confusion matrix shows the performance of a classification model.

|                | Predicted Positive | Predicted Negative |
|----------------|--------------------|--------------------|
| Actual Positive | TP (True Positive) | FN (False Negative) |
| Actual Negative | FP (False Positive) | TN (True Negative) |

### Definitions:

- **TP** → Correctly predicted positive  
- **TN** → Correctly predicted negative  
- **FP** → Incorrectly predicted positive  
- **FN** → Incorrectly predicted negative  

---

# 1️⃣ Accuracy

### Definition

Accuracy measures the **overall correctness of the model**.

### Formula

\[
Accuracy = \frac{TP + TN}{TP + TN + FP + FN}
\]

### Characteristics

- Simple and intuitive
- Not reliable for imbalanced datasets

---

# 2️⃣ Precision

### Definition

Precision measures **how many predicted positives are actually correct**.

### Formula

\[
Precision = \frac{TP}{TP + FP}
\]

### Use Case

- Important when **false positives are costly**

Example:
- Spam detection
- Fraud detection

---

# 3️⃣ Recall (Sensitivity / True Positive Rate)

### Definition

Recall measures **how many actual positives are correctly identified**.

### Formula

\[
Recall = \frac{TP}{TP + FN}
\]

### Use Case

- Important when **false negatives are costly**

Example:
- Disease detection
- Fraud detection

---

# 4️⃣ F1 Score

### Definition

F1 Score is the **harmonic mean of Precision and Recall**.

### Formula

\[
F1 = 2 \times \frac{Precision \times Recall}{Precision + Recall}
\]

### Characteristics

- Balances precision and recall
- Useful for imbalanced datasets

---

# 5️⃣ Specificity (True Negative Rate)

### Definition

Specificity measures how well the model identifies negatives.

### Formula

\[
Specificity = \frac{TN}{TN + FP}
\]

---

# 6️⃣ ROC Curve (Receiver Operating Characteristic)

- Graph of:
  - True Positive Rate (Recall)
  - vs False Positive Rate

\[
FPR = \frac{FP}{FP + TN}
\]

---

# 7️⃣ AUC (Area Under Curve)

- Measures performance of classification model across all thresholds

| AUC Value | Meaning |
|----------|--------|
| 1 | Perfect model |
| 0.5 | Random model |
| < 0.5 | Worse than random |

---

# 📊 Example

Suppose:

- TP = 50  
- TN = 40  
- FP = 10  
- FN = 5  

Then:

- Accuracy = (50+40)/105  
- Precision = 50/(50+10)  
- Recall = 50/(50+5)  

---

# 📌 When to Use Which Metric?

Use **Accuracy**:
- Balanced dataset

Use **Precision**:
- False positives are costly

Use **Recall**:
- False negatives are costly

Use **F1 Score**:
- Imbalanced dataset

Use **ROC-AUC**:
- Compare models

---

# ⭐ Advantages

- Gives detailed evaluation
- Helps understand model behavior
- Useful for model comparison

---

# ⚠ Disadvantages

- Can be confusing with many metrics
- Accuracy can be misleading
- Requires understanding of context

---

# 🔥 Key Takeaway

> Classification metrics evaluate how well a model predicts categories using measures like accuracy, precision, recall, F1 score, and ROC-AUC, each highlighting different aspects of model performance.