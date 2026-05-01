---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Standard Scaler (Standardization)

Standardizes features by **removing the mean** and **scaling to unit variance**. Transforms data to have **mean = 0** and **standard deviation = 1**.

## Formula

$$
X' = \frac{X - \mu}{\sigma}
$$

Where:
- $\mu$ = mean of the feature
- $\sigma$ = standard deviation of the feature

## Effect on Data

| Property | Before | After |
|----------|--------|-------|
| **Mean** | $\mu$ (any value) | $0$ |
| **Standard Deviation** | $\sigma$ (any value) | $1$ |
| **Variance** | $\sigma^2$ | $1$ |

## Example

```python
Original: [10, 20, 30, 40, 50]
Mean = 30, Std = 15.81

After StandardScaler:
Z-scores: [-1.26, -0.63, 0, 0.63, 1.26]
Mean = 0, Std = 1
```

## When to Use

| Use Case | Why |
|----------|-----|
| Data follows [[Gaussian distribution]] | Optimal for standardization |
| [[Linear Regression]] | Assumes normally distributed features |
| [[Logistic Regression]] | Benefits from standardized features |
| **SVM, PCA, KNN** | Sensitive to feature scales |
| **Neural Networks** | Helps with convergence |

## Standardization vs Normalization (Min-Max)

| Feature | Standardization | Min-Max Normalization |
|---------|-----------------|----------------------|
| **Formula** | $(X - \mu)/\sigma$ | $(X - X_{min})/(X_{max} - X_{min})$ |
| **Output range** | No fixed range (typically -3 to +3) | $[0, 1]$ |
| **Outlier sensitivity** | Less sensitive | Very sensitive |
| **Preserves shape** | Yes | Yes |
| **Assumes** | Gaussian distribution | Any distribution |
| **Use when** | Features have different units, outliers present | Need bounded range, no outliers |

## Important Note

> [!warning] Does NOT Bound Values
> Standardization does **not** produce values in a fixed range (like $[0, 1]$). Values can be any real number, typically between -3 and +3 for normally distributed data, but potentially larger with outliers.

## When NOT to Use

| Situation | Reason |
|-----------|--------|
| **Decision Trees / Random Forest** | Not scale-sensitive |
| **Sparse data** | Standardization destroys sparsity |
| **Binary features (0/1)** | No need to scale |

## One-Line Summary

> Standardization = $(X - \mu)/\sigma$ → mean=0, variance=1 — for Gaussian data and scale-sensitive algorithms.

## Related

- [[Min-Max Scaling]]
- [[Normalizer]]
- [[Gaussian Distribution]]
- [[Z-Score]]
- [[Feature Scaling]]
- [[Data Preprocessing]]
- [[Linear Regression]]
- [[Logistic Regression]]
