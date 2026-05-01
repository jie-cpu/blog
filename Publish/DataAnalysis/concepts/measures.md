---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Measures vs Metrics

## Key Distinction

| Term | Focus | Question |
|------|-------|----------|
| **Measure** | Raw value | What is the value? |
| **Metric** | Evaluation | Is this good or bad? |

**Goal:** Characterize data by one number (aggregation).

---

## Core Principle

> [!warning] Using only one measure is misleading

Always combine multiple measures to get a complete picture.

---

## Types of Measures

### 1. Location Measures (Central Tendency)

Where is the data centered?

| Measure | Description |
|---------|-------------|
| **Mode** | Most frequent value |
| **Mean** | Arithmetic average |
| **Median** | Middle value (50th percentile) |

### 2. Variability Measures (Spread)

How spread out is the data?

| Measure | Description |
|---------|-------------|
| **Variance** | Average squared deviation from mean |
| **Standard Deviation** | Square root of variance (same units as data) |
| **Coefficient of Variation** | SD/mean (relative variability) |
| **Min, Max** | Extreme values |
| **Range** | Max - Min |

### 3. Higher Moments (Shape)

What does the distribution look like?

| Measure | Description | What It Tells You |
|---------|-------------|-------------------|
| **Skewness** | Asymmetry | Negative = left tail · Positive = right tail |
| **Kurtosis** | "Tailedness" / curvature | High = heavy tails (outliers) · Low = light tails |

---

## Why Multiple Measures Matter

**Example:** Two datasets with same mean but very different spreads

```
Dataset A: [49, 50, 51]        Mean = 50, SD = 1
Dataset B: [10, 50, 90]        Mean = 50, SD = 40

Same mean → completely different interpretation!
```

---

## One-Line Summary

> Measures give numbers; metrics judge them. Never rely on a single measure — combine location, variability, and shape.

---

## Related

- [[Descriptive Statistics]]
- [[Mean Median Mode]]
- [[Standard Deviation]]
- [[Skewness]]
- [[Kurtosis]]
- [[Central Tendency]]
- [[Statistical Dispersion]]
