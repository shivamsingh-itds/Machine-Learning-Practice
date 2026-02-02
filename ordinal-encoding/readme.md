# Ordinal Encoding in Machine Learning

## What is Ordinal Encoding?
Ordinal Encoding is a **categorical data encoding technique** used in Machine Learning to **convert ordered categories into numerical values**.

In simple words 👇  
Ordinal Encoding assigns **numbers based on order or rank** of the categories.

---

## Why do we need Ordinal Encoding?
Some categorical data has a **natural order**, but ML models still need numbers.

Example:
- Education: School < College < University  
- Size: Small < Medium < Large  

Ordinal Encoding helps to:
- Preserve the **order of categories**
- Convert text data into **numeric form**
- Improve model understanding for ranked data

---

## How Ordinal Encoding Works

Original data:

| Size |
|------|
| Small |
| Medium |
| Large |

After Ordinal Encoding:

| Size | Encoded Value |
|-----|--------------|
| Small | 1 |
| Medium | 2 |
| Large | 3 |

---

## Ordinal Encoding Rule
- Categories are encoded **according to their rank**
- Higher rank → **higher number**
- Order must be **defined manually or logically**

---

## Simple Explanation
- Identify categories with a **clear order**
- Assign numbers based on that order
- Models can now understand **which category is higher or lower**

---

## Example
Original feature: `Rating`

Values:
- Poor
- Average
- Good
- Excellent

Encoded values:

| Rating | Encoded |
|-------|--------|
| Poor | 1 |
| Average | 2 |
| Good | 3 |
| Excellent | 4 |

---

## When to Use Ordinal Encoding?
Use it when:
- Data is **categorical and ordered**
- Order matters in prediction

Common use cases:
- Education level
- Customer satisfaction
- Product quality
- Experience level

---

## When NOT to Use Ordinal Encoding?
- When categories have **no natural order**
- When numeric difference is **not meaningful**

Example ❌:
- City names
- Colors
- Product IDs

---

## Risk of Ordinal Encoding
Models may assume:
- Distance between categories is **equal**, which may not be true

Example:
- Difference between Poor → Average may not equal Average → Good

---

## Key Takeaway
> Ordinal Encoding converts ordered categorical data into numbers **while preserving their ranking**, making it suitable only when category order truly matters.
