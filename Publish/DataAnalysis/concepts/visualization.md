---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Data Visualization Methods

Visualization methods depend on **parameters** and **scale of data**.

---

## 1. Frequency Distribution

**Question:** How many times does each category appear?

| Data Type | Applicability |
|-----------|---------------|
| [[Categorical Data]] | ✅ Yes |
| [[Ordinal Data]] | ✅ Yes |
| Cardinal (numeric) | ❌ Needs binning first |

**Visualization:** Bar chart, frequency table

---

## 2. Empirical Density

Estimate data shape from **observed data**.

### Histogram

| Aspect | Description |
|--------|-------------|
| **Shape** | Bars (can have jumps) |
| **Data Type** | Cardinal (numeric) |
| **Parameters** | Number of classes, class size (equal or variable) |

```
Histogram (bars)
   ↑
   │ █
   │ █ █
   │ █ █ █
   │ █ █ █ █
   └────────→
```

| Parameter | Impact |
|-----------|--------|
| **Number of classes** | Too few → oversmooth · Too many → overfit |
| **Class size** | Equal or variable width |

### Kernel Density Estimate (KDE)

| Aspect | Description |
|--------|-------------|
| **Shape** | Continuous, smooth curve |
| **Smoothing parameter** | Bandwidth |
| **Data Type** | Cardinal (numeric) |

```
KDE (smooth curve)
   ↑
   │    ╭───╮
   │   ╱     ╲
   │  ╱       ╲
   │ ╱         ╲
   └──────────────→
```

| Parameter | Description |
|-----------|-------------|
| **Bandwidth** | Smoothing parameter — controls curve smoothness |

---

## 3. Boxplot

| Data Type | Applicability |
|-----------|---------------|
| [[Ordinal Data]] | ✅ Yes |
| [[Cardinal Data]] | ✅ Yes |

### Parameters: Level of Quantiles

| Quantile | Value |
|----------|-------|
| **Minimum** | Smallest value (excluding outliers) |
| **25% (Q1)** | First quartile |
| **50% (Median)** | Middle value |
| **75% (Q3)** | Third quartile |
| **Maximum** | Largest value (excluding outliers) |

### Boxplot Structure

```
     Outliers (if any) →   ●
                           |
     Maximum (excluding outliers) → ┬───┐
                                      │   │
     75% (Q3) →                    ───┘   ├─ IQR (Interquartile Range)
                                     │   │
     Median (50%) →                  ●───┤
                                     │   │
     25% (Q1) →                    ───┐   │
                                      │   │
     Minimum (excluding outliers) → ─┴───┘
                           |
                           ●  ← Outliers
```

## Quick Selection Guide

| Goal | Method | Data Type |
|------|--------|-----------|
| Count per category | Frequency distribution | Categorical, Ordinal |
| Estimate shape (discrete) | Histogram | Cardinal |
| Estimate shape (smooth) | KDE | Cardinal |
| Show summary + outliers | Boxplot | Ordinal, Cardinal |

## One-Line Summary

> Choose visualization by data type: categorical → frequency, cardinal → histogram/KDE/boxplot with appropriate parameters.

## Related

- [[Histogram]]
- [[Kernel Density Estimation]]
- [[Boxplot]]
- [[Frequency Distribution]]
- [[Quantile]]
- [[IQR]]
- [[Bandwidth]]
- [[Data Types]]
