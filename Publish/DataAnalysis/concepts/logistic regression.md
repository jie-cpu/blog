---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Logistic Regression

A **regression model used for classification tasks** — same input as linear regression, but output is binary (0 or 1).

## Key Difference

| Aspect | Linear Regression | Logistic Regression |
|--------|-------------------|---------------------|
| **Purpose** | Predict continuous values | Classify into categories |
| **Output** | Any real number | 0 or 1 (probability then threshold) |
| **Input** | Features | Same features |

## Advantages

| Advantage | Description |
|-----------|-------------|
| ✅ Easy to implement | Simple algorithm |
| ✅ Easy to interpret | Coefficients show feature importance |
| ✅ Same model reduction | Same process as linear regression |

## Disadvantages

| Disadvantage | Description |
|--------------|-------------|
| ❌ Dependency assumption | Works well only if assumption holds (like linear regression) |
| ❌ Unbalanced data | Performs poorly when one class dominates |

## The Unbalanced Data Problem

> [!warning] Critical Issue for All Classification Methods

**Example:** $n_1 = 95$, $n_0 = 5$

- Model may simply ignore the 5 minority samples
- Those 5 could be the **most important**:
  - 🚨 Fraud detection
  - 🩺 Cancer diagnosis  
  - ⚠️ Error detection

### Why It's a Problem

```
Training set: 95% class A, 5% class B
           ↓
Model learns: "Always predict A"
           ↓
Accuracy = 95% (looks good!)
           ↓
But: Detects ZERO critical B cases
```

## One-Line Summary

> Logistic regression = linear regression for binary classification — easy to use but breaks on imbalanced data.

## Related

- [[Linear Regression]]
- [[Binary Classification]]
- [[Imbalanced Data]]
- [[Sigmoid Function (Classification Output)]]
- [[Confusion Matrix]]
- [[Precision and Recall]]
- [[SMOTE]]
```

---

This version is:

- **Obsidian-ready** — copy and paste
- **Comparison table** with linear regression
- **Pros/Cons tables**
- **Warning callout** for unbalanced data
- **Concrete example** (95/5 split)
- **Critical use cases** (fraud, cancer, errors)
- **Visual flow** showing the problem
- **Links ready** — `[[Imbalanced Data]]`, `[[SMOTE]]`, `[[Precision and Recall]]`

Want me to add the sigmoid function formula, odds ratio interpretation, or techniques for handling imbalanced data?