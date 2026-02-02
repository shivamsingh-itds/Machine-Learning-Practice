# Normalization in Machine Learning

## What is Normalization?
Normalization is a **data preprocessing technique** used in Machine Learning to **scale feature values** into a fixed range, usually between:

- **0 and 1**
- or **-1 and 1**

In simple words 👇  
Normalization shrinks all values so they **fit within a small range**.

---

## Why do we need Normalization?
Different features can have very different ranges.

Example:
- Distance → 1 to 1000  
- Rating → 1 to 5  

Models that use **distance or magnitude** can get confused by large values.

Normalization helps to:
- Keep values in a **fixed range**
- Improve **distance calculations**
- Make model behavior more **stable**

---

## Normalization Formula (Min–Max Scaling)

\[
X_{norm} = \frac{X - X_{min}}{X_{max} - X_{min}}
\]

Where:
- **X** = original value  
- **X<sub>min</sub>** = minimum value of the feature  
- **X<sub>max</sub>** = maximum value of the feature  
- **X<sub>norm</sub>** = normalized value  

---

## Simple Explanation of the Formula
- Subtract the **minimum value** → shifts data to start from 0  
- Divide by **range (max − min)** → scales data between 0 and 1  

Result:  
All values now lie **between 0 and 1**

---

## Example
Original values: `10, 20, 30`  
Minimum = `10`  
Maximum = `30`

For X = 20:

\[
X_{norm} = \frac{20 - 10}{30 - 10} = \frac{10}{20} = 0.5
\]

---

## Types of Normalization
1. **Min–Max Normalization** (most common)
2. **Max Absolute Scaling**
3. **Mean Normalization**
4. **Unit Vector Scaling**

---

## When to Use Normalization?
Use normalization when:
- Data has **known bounds**
- Using **distance-based algorithms**

Common models that need it:
- KNN
- K-Means Clustering
- Neural Networks
- Gradient Descent–based models

---

## When NOT to Use Normalization?
- Tree-based models (Decision Tree, Random Forest)
- When outliers are extreme (Min–Max is sensitive to outliers)

---

## Key Takeaway
> Normalization scales data into a **fixed range**, usually 0 to 1, making it easier for models to compare values fairly.
