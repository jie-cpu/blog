---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Supervised Learning Tasks

Predicting the future (output $y$) from input data ($X$).

## Core Tasks

| Task | Description |
|------|-------------|
| **Forecasting** | Predict future values (time series) |
| **Scoring** | Assign numerical score (e.g., credit risk) |
| **[[Classification]]** | Predict category |
| **Spam Filtering** | Classify email as spam or not |

## Labeled Data → Prediction

The output $y$ determines the task type:

| Data Type | Task | Output $y$ |
|-----------|------|-------------|
| **Discrete** (categories) | [[Classification]] | Category (e.g., "spam", "not spam") |
| **Continuous** (real numbers) | [[Regression]] | Real number (e.g., price, temperature) |

## Visual Decision Tree

```
Has labeled data?
       ↓
      YES
       ↓
What type is y?
       ↓
   ┌───┴───┐
   ↓       ↓
Discrete  Continuous
   ↓       ↓
Classification Regression
   ↓       ↓
Examples:  Examples:
- Spam?   - House price
- Cat/Dog - Temperature
- Digit   - Stock price
```

## Examples

| Problem | Input ($X$) | Output ($y$) | Type |
|---------|-------------|--------------|------|
| Spam filter | Email text | "spam" / "not spam" | Classification |
| Digit recognition | Image pixels | 0,1,2,...,9 | Classification |
| House price prediction | Size, rooms, location | $250,000 | Regression |
| Temperature forecast | Date, location | 72.5°F | Regression |

## One-Line Summary

> Supervised learning = predict $y$ from $X$ — discrete $y$ → classification, continuous $y$ → regression.

## Related

- [[Classification]]
- [[Regression]]
- [[Supervised Learning]]
- [[Labeled Data]]
- [[Training and Inference]]
- [[Spam Filtering]]
- [[Forecasting]]
