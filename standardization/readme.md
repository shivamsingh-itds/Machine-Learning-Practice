# Standardization in Machine Learning

## What is Standardization?
Standardization is a **data preprocessing technique** used in Machine Learning to **rescale features** so that they have:

- **Mean = 0**
- **Standard Deviation = 1**

In simple words 👇  
Standardization brings all numbers to a **common scale** without changing their relative meaning.

---

## Why do we need Standardization?
Different features can have very different ranges.

Example:
- Age → 18 to 60  
- Salary → 20,000 to 1,00,000  

Machine Learning models may **give more importance to larger values**, which is wrong.

Standardization helps to:
- Treat all features **equally**
- Improve **model performance**
- Speed up **training**

---

## Standardization Formula

\[
Z = \frac{X - \mu}{\sigma}
\]

Where:
- **X** = original value  
- **μ (mu)** = mean of the feature  
- **σ (sigma)** = standard deviation of the feature  
- **Z** = standardized value  

---

## Simple Explanation of the Formula
- Subtract the **mean** from the value → centers data around 0  
- Divide by **standard deviation** → scales the data  

Result:  
All values are now measured in terms of **how far they are from the mean**

---

## Example
Original values: `50, 60, 70`  
Mean (μ) = `60`  
Standard Deviation (σ) = `10`

For X = 70:

\[
Z = \frac{70 - 60}{10} = 1
\]

This means **70 is 1 standard deviation above the mean**

---

## When to Use Standardization?
Use standardization when:
- Features have **different units**
- Using distance-based or gradient-based models

Common models that need it:
- Linear Regression
- Logistic Regression
- KNN
- SVM
- PCA
- Neural Networks

---

## When NOT to Use Standardization?
- Tree-based models (Decision Tree, Random Forest)
- When data is already on the same scale

---

## Key Takeaway
> Standardization makes data **fair, balanced, and model-friendly** by converting it to a common scale with mean 0 and standard deviation 1.
