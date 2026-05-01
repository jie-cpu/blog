---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Binarizer

A preprocessing technique that converts continuous or numerical data into binary values (0s and 1s) based on a specified threshold.

## When to Use

When the **presence or absence** of a feature is more important than its actual value.

## The Rule

| Condition | Output |
|-----------|--------|
| Value ≥ threshold | 1 |
| Value < threshold | 0 |

## Formula

$$
X' = \begin{cases} 
1 & \text{if } X \geq \text{threshold} \\ 
0 & \text{if } X < \text{threshold} 
\end{cases}
$$

## Common Applications

| Domain | Example |
|--------|---------|
| [[Text Classification]] | Term frequency → presence/absence of words |
| [[Image Processing]] | Grayscale → black-and-white |
| [[Feature Selection]] | Simplifying features for ML algorithms |

## Why Use Binarizer?

- ✅ Simplifies data
- ✅ Helps algorithms sensitive to feature scale
- ✅ Focuses on existence rather than magnitude

## One-Line Summary

> Binarizer = threshold-based conversion of numbers to 0/1.

## Related

- [[StandardScaler]]
- [[MinMaxScaler]]
- [[Normalization]]
- [[Preprocessing]]