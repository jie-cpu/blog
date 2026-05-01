---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Min-Max Scaling

A **normalization technique** that transforms features to a fixed range, typically $[0, 1]$.

## Formula

$$X' = \frac{X - X_{\text{min}}}{X_{\text{max}} - X_{\text{min}}}$$

## How It Works

| Step | Operation |
|------|-----------|
| 1 | Subtract minimum value |
| 2 | Divide by range ($\text{max} - \text{min}$) |
| 3 | Result falls in $[0, 1]$ |

## When to Use

| Scenario | Suitability |
|----------|-------------|
| Non-Gaussian distribution | ✅ Good |
| Different units or scales | ✅ Good |
| Features with outliers | ❌ **Sensitive** |

## Example

```python
# Original values: [10, 20, 30, 40, 50]
# Min = 10, Max = 50, Range = 40

# After Min-Max scaling:
# 10 → (10-10)/40 = 0.00
# 20 → (20-10)/40 = 0.25
# 30 → (30-10)/40 = 0.50
# 40 → (40-10)/40 = 0.75
# 50 → (50-10)/40 = 1.00
```

## Limitation: Outlier Sensitivity

> [!warning] 
> Min-Max scaling is **sensitive to [[outliers]]**. A single extreme value can compress the rest of the data.

**Example with outlier:**
```
Values: [10, 20, 30, 40, 1000]
Min = 10, Max = 1000
Most data gets squeezed near 0 (10→0, 20→0.01, 30→0.02, 40→0.03)
```

## Comparison with Standardization

| Feature | Min-Max Scaling | [[Standardization]] |
|---------|----------------|---------------------|
| Output range | $[0, 1]$ (fixed) | No fixed range |
| Outlier sensitive | ✅ Yes | ❌ Less |
| Preserves shape | ✅ Yes | ✅ Yes |
| Use when | Known bounds | Unknown distribution |

## One-Line Summary

> Min-Max = scale to $[0, 1]$ using min and max — simple but outlier-sensitive.

## Related

- [[Standardization]]
- [[Normalization]]
- [[Feature Scaling]]
- [[Outlier]]
- [[Data Preprocessing]]
