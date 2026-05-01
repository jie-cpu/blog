---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Normalizer (Sample-wise Normalization)

A technique that scales **individual samples (rows)** to have **unit norm** — unlike Min-Max or Standardization which scale features (columns).

## Formula

$$
X' = \frac{X}{||X||}
$$

Where $||X||$ is the **norm** of the vector (L1 or L2 norm).

## Key Distinction: Feature Scaling vs Sample Normalization

| Method | Scales | Output |
|--------|--------|--------|
| **Min-Max / Standardization** | Features (columns) | Varies |
| **Normalizer** | Samples (rows) | Unit norm |

## Common Norms

| Norm | Formula | Result |
|------|---------|--------|
| **L2 Normalization** | $X' = \frac{X}{\sqrt{\sum x_i^2}}$ | $\|X'\|_2 = 1$ (default) |
| **L1 Normalization** | $X' = \frac{X}{\sum \|x_i\|}$ | $\|X'\|_1 = 1$ |

## Example

```python
Sample: [3, 1, 0, 2]

# L2 norm = √(9+1+0+4) = √14 ≈ 3.74
After L2: [0.80, 0.27, 0, 0.53]  # ||X'||₂ = 1

# L1 norm = 3+1+0+2 = 6
After L1: [0.50, 0.17, 0, 0.33]  # ||X'||₁ = 1
```

## When to Use

| Use Case | Why |
|----------|-----|
| [[Text Classification]] | Direction over magnitude (word presence patterns) |
| [[Clustering]] (e.g., [[K-means]]) | Distance based on angle, not length |
| [[K-Nearest Neighbors]] | Prevents large-magnitude samples from dominating |

## Why It Works

> [!important] Direction > Magnitude
> Normalizer focuses on **angle between vectors** (cosine similarity) rather than their length.

```
Sample A: [100, 50]    → Normalized: [0.89, 0.45]
Sample B: [2, 1]        → Normalized: [0.89, 0.45]  (same direction!)

Original distance: large
Normalized distance: 0 (perfectly aligned)
```

## One-Line Summary

> Normalizer = row-wise scaling to unit norm — direction matters, magnitude doesn't.

## Related

- [[Min-Max Scaling]]
- [[Standardization]]
- [[Cosine Similarity]]
- [[K-means]]
- [[KNN]]
- [[Feature Scaling]]
- [[Vector Norm]]
```

---

This version is:

- **Obsidian-ready** — copy and paste
- **Clear distinction** from feature scaling methods
- **Formula** with both L1 and L2 norms
- **Concrete example** showing before/after
- **Use case table** (text, clustering, KNN)
- **Callout box** showing direction > magnitude
- **Links preserved** — `[[classification]]`, `[[clustering]]`, etc.

Want me to add a comparison table of Normalizer vs StandardScaler vs MinMaxScaler?