---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Linear Regression

**Aim:** Model the relationship between the target (output) and input variables.

## Types

| Type | Input Variables | Output |
|------|----------------|--------|
| **Simple Linear Regression** | Single variable | Single output |
| **Multiple Linear Regression** | Multiple variables | Single output |

## Goodness of Fit

### Coefficient of Determination ($R^2$)

| Property | Value |
|----------|-------|
| Range | $[0, 1]$ |
| Close to 1 | Good model fit |
| Close to 0 | Poor model fit |

### Correlation ($r$)

| Property | Value |
|----------|-------|
| Range | $[-1, 1]$ |
| $r = 0$ | No linear relationship |
| $r = -1$ | Perfect negative correlation |
| $r = 1$ | Perfect positive correlation |

## Variable Transformation: Dummy Variables

Convert categorical variables to numeric format (0 and 1 only).

| Reason | Explanation |
|--------|-------------|
| **Machine understanding** | Algorithms need numbers |
| **Avoid incorrect ordering** | Prevents treating categories as 1<2<3 |
| **Measure individual effects** | Each category gets its own coefficient |

## Algorithm Steps

```
1. Preparation
   ├── Visualize data
   └── Decide about variable transformation

2. Estimation (Learn model parameters)

3. Interpretation
   ├── Interpret parameters
   └── Check goodness of fit ($R^2$)

4. Visualization
   ├── Prediction vs Y
   └── Residuals vs Y

5. Assumption Checking
   ├── Normality
   ├── Homogeneity
   └── Variable correlations

6. Model Reduction Decision
```

## Advantages & Disadvantages

| Advantages | Disadvantages |
|------------|---------------|
| ✅ Easy calculation, explicit formulas | ❌ Only for linear relationships |
| ✅ Easy to interpret | ❌ Sensitive to outliers |
| | ❌ Only continuous variables (or dummies) |

## One-Line Summary

> Linear regression = models linear relationships between inputs and output — simple, interpretable, but sensitive to outliers and linearity assumption.

## Related

- [[Multiple Linear Regression]]
- [[Simple Linear Regression]]
- [[R Squared]]
- [[Correlation]]
- [[Dummy Variable]]
- [[Ordinary Least Squares]]
- [[Residual Analysis]]
- [[Assumptions of Linear Regression]]
```

---

This version is:

- **Obsidian-ready** — copy and paste
- **Two clear sections** for regression types
- **Tables for $R^2$ and correlation**
- **Dummy variable explanation** with three reasons
- **Numbered workflow** for the 6-step algorithm
- **Pros/Cons table** for quick evaluation
- **Links ready** for related concepts

Want me to add the actual formulas (OLS, normal equation), or a concrete example with dummy variables?