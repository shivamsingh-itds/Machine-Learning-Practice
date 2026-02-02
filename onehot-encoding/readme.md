# One-Hot Encoding in Machine Learning

## What is One-Hot Encoding?
One-Hot Encoding is a **categorical data encoding technique** used in Machine Learning to **convert text categories into numerical form**.

In simple words 👇  
One-Hot Encoding changes **categories into binary columns (0 and 1)** so that ML models can understand them.

---

## Why do we need One-Hot Encoding?
Machine Learning models **cannot work with text data directly**.

Example (raw data):
- Color = Red, Blue, Green  

ML models need numbers, not words.

One-Hot Encoding helps to:
- Convert categories into **machine-readable format**
- Avoid giving **false priority or order**
- Improve **model accuracy**

---

## How One-Hot Encoding Works

Original data:

| Color |
|------|
| Red |
| Blue |
| Green |

After One-Hot Encoding:

| Color_Red | Color_Blue | Color_Green |
|----------|------------|-------------|
| 1 | 0 | 0 |
| 0 | 1 | 0 |
| 0 | 0 | 1 |

---

## One-Hot Encoding Rule
- Each **unique category** gets its own column  
- Value is **1** if the category is present  
- Value is **0** if the category is absent  

---

## Simple Explanation
- Create a new column for each category  
- Mark **1** where the category matches  
- Mark **0** everywhere else  

Result:  
Categories are represented **clearly and fairly**

---

## Example
Original feature: `City`

Values: `Mumbai, Delhi, Pune`

Encoded output:

| City_Mumbai | City_Delhi | City_Pune |
|------------|-----------|-----------|
| 1 | 0 | 0 |
| 0 | 1 | 0 |
| 0 | 0 | 1 |

---

## Dummy Variable Trap
If there are **N categories**, using all N columns can cause **multicollinearity** in some models.

Solution:
- Drop **one column**
- Keep **N − 1 columns**

Example (drop City_Pune):

| City_Mumbai | City_Delhi |
|------------|-----------|
| 1 | 0 |
| 0 | 1 |
| 0 | 0 |

---

## When to Use One-Hot Encoding?
Use it when:
- Data is **categorical**
- Categories have **no order**

Common use cases:
- Gender
- City
- Product type
- Payment method

---

## When NOT to Use One-Hot Encoding?
- For **ordinal data** (Low, Medium, High)
- When categories are **too many** (high cardinality)

---

## Key Takeaway
> One-Hot Encoding converts categorical text data into **binary numerical columns**, allowing machine learning models to process categories without bias.
