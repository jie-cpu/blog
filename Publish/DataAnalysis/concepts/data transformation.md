---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
Here's a clean, Obsidian-ready markdown note based on your summary:

---
# Data Transformation

**Goal:** Make data usable for analysis and machine learning.

> [!warning] Trade-off
> Potential **information loss** — overlaps with [[Data Reduction]]

## Types of Transformation

### 1. Scaling and Normalization

| Method | Description |
|--------|-------------|
| **[[Standardization]]** | Mean = 0, variance = 1 |
| **[[Min-Max Scaling]]** | Range = [0, 1] or [-1, 1] |

### 2. Text → Numeric Data

Convert categorical/text data into numerical format (e.g., [[CountVectorizer]], [[TF-IDF]], [[One-Hot Encoding]])

### 3. Time Series → Discrete Sequence Data

**Symbolic Aggregate Approximation (SAX)**

Two main approaches:

| Approach | Description |
|----------|-------------|
| **Window-based averaging** | Smooth time series into segments |
| **Value-based discretization** | Map numerical values to symbols (e.g., low/medium/high) |

### 4. Discrete Sequence → Binary Data

Convert sequence data into binary format (e.g., presence/absence matrix)

## Visual Flow

```
Original Data
    ├── Scaling/Normalization → Standardized data
    ├── Text → Numeric vectors
    ├── Time Series → Discrete symbols (SAX)
    └── Discrete Sequence → Binary matrix
```

## One-Line Summary

> Data transformation = making data usable, often with dimension reduction and potential info loss.

## Related

- [[Data Preprocessing]]
- [[Normalization]]
- [[Feature Scaling]]
- [[SAX]]
- [[Discretization]]
- [[One-Hot Encoding]]
