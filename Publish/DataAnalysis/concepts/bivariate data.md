---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Correlation and Related Concepts

**Correlation** refers to a **linear** relationship between variables. It characterizes the interplay between two or more variables.

## Types of Correlation

### Bravais-Pearson Correlation

- Measures **only linear correlation**
- Standard Pearson correlation coefficient

### Spearman Rank Correlation

- Measures **monotonic relationships** (both linear and nonlinear)
- Works with ranked data

> [!note] Important
> $y = x^2$ is **neither linear nor monotonic** — not suitable for Spearman.

## Coefficient of Determination ($R^2$)

| Property | Value |
|----------|-------|
| Range | $[0, 1]$ |
| Meaning | How well the model fits the data |

- $R^2 = 0$ → model explains nothing
- $R^2 = 1$ → perfect fit

## Interpolation vs Extrapolation

| Term | Meaning | Risk |
|------|---------|------|
| **Interpolation** | Predict within known data range | Lower risk |
| **Extrapolation** | Predict outside known data range | Higher uncertainty |

## One-Line Summary

> Pearson = linear only · Spearman = monotonic · $R^2$ = fit quality · Interpolation = safe · Extrapolation = risky.

## Related

- [[Pearson Correlation]]
- [[Spearman Rank Correlation]]
- [[R Squared]]
- [[Linear Regression]]
- [[Monotonic Function]]