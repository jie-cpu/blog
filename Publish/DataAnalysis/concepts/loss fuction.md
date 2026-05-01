---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Regression Error Metrics

**MAE** and **MSE** are common metrics for evaluating regression models. **The smaller, the better.**

## MAE (Mean Absolute Error)

Measures the average magnitude of errors without considering direction.

$$
\text{MAE} = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i|
$$

## MSE (Mean Squared Error)

Measures the average squared difference between predicted and actual values. Penalizes large errors more heavily.

$$
\text{MSE} = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
$$

## Comparison

| Metric | Formula | Sensitivity to Outliers |
|--------|---------|------------------------|
| **MAE** | $\frac{1}{n}\sum\|y - \hat{y}\|$ | Less sensitive |
| **MSE** | $\frac{1}{n}\sum(y - \hat{y})^2$ | **More sensitive** (squares errors) |

## Key Insight

> [!important] The smaller, the better for both metrics.

| Value | Meaning |
|-------|---------|
| 0 | Perfect predictions |
| Small | Good model fit |
| Large | Poor model fit |

## When to Use Which

| Metric | Best For |
|--------|----------|
| **MAE** | When outliers are not critical, interpretable in original units |
| **MSE** | When large errors must be heavily penalized |

## Related

- [[RMSE]] (Root Mean Squared Error)
- [[R Squared]]
- [[Regression Metrics]]
- [[Loss Function]]