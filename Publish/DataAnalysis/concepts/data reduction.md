---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
Here's a clean, Obsidian-ready markdown note based on your summary:

---

# Data Reduction

**Goal:** Smaller data size allows applying sophisticated and computationally expensive algorithms.

Two main approaches:
- Reduce # records
- Reduce # dimensions

## How to Reduce Data

### 1. Data Sampling

| Type | Description |
|------|-------------|
| **Unbiased** | Each record has equal chance of selection |
| **Biased** | Some records have higher selection probability |
| **Stratified** | Preserve proportion of categories/groups |

### 2. Feature Selection (≠ Feature Extraction)

Select a subset of original features.

| Approach | Method |
|----------|--------|
| Unsupervised | Clustering |
| Supervised | Classification, Regression |

### 3. Data Reduction with Axis Rotation

| Method | Application |
|--------|-------------|
| **PCA** (Principal Component Analysis) | Remove weaker components to reduce data |
| **[[Singular Value Decomposition]] (SVD)** | Noise reduction, data imputation |

### 4. Data Reduction with Type Transformation

Transform data from **more complex type** to **less complex type**.

## Visual Flow

```
Original Data
    ├── Reduce # records → Sampling
    └── Reduce # dimensions
            ├── Feature Selection
            ├── Axis Rotation (PCA, SVD)
            └── Type Transformation
```

## One-Line Summary

> Data reduction = smaller dataset → faster + more complex algorithms possible.

## Related

- [[PCA]]
- [[Singular Value Decomposition]]
- [[Feature Selection vs Feature Extraction]]
- [[Dimensionality Reduction]]
- [[Sampling Methods]]
