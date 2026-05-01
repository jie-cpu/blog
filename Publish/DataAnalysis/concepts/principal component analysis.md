---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Principal Component Analysis (PCA)

**Dimension reduction** by selecting some Principal Components (PCs). Transforms data to lower dimension without losing much information using a **linear transformation** (empirical covariance matrix).

## Core Idea

$$
\text{Original Data} \xrightarrow{\text{Linear Transformation}} \text{Principal Components (PCs)}
$$

- **PC1** = direction of **largest** variance
- **PC2** = direction of **second largest** variance (orthogonal to PC1)
- ...

## Example: Grades

```
Original Features (p dimensions)
├── Math
├── Chemistry
├── Biology
├── English
├── History
└── Politics

        ↓ PCA

Reduced Features (q dimensions, q < p)
├── IQ_sci (scientific ability)
└── IQ_social (humanities ability)
```

## Eigenvalues and Eigenvectors

| Concept | Meaning in PCA | Property |
|---------|----------------|----------|
| **Eigenvector** ($\gamma$) | Direction of the data | Covariance matrix only changes **length**, not **direction** |
| **Eigenvalue** ($\lambda$) | Variance along that direction | PCA orders from **largest to smallest** |

```
Eigenvalue λ₁ ≥ λ₂ ≥ λ₃ ≥ ... ≥ λₚ

PC1 (largest λ) → Most important → Most variance explained
PC2 (second λ) → Second most important
...
```

## Algorithm Steps

```
1. Calculate empirical covariance matrix

2. Get eigenvalues λ = (λ₁, ..., λₚ) 
   and eigenvector matrix Γ = [γ₁| ... |γₚ]

3. Center the data: Y = X - mean(X)

4. Use scree plot to decide number of effective PCs (q)

5. Visualization:
   ├── Data
   ├── Scree plot
   ├── Principal Components
   └── Biplot (PCs + original variables)

6. Take ONLY first q PCs for further analysis
```

## Scree Plot

```
Eigenvalue (λ)
    ↑
 λ₁ │●
    │  ●
 λ₂ │    ●
 λ₃ │      ●
 λ₄ │        ●
    │          ● ← Elbow (choose q here)
 λ₅ │            ●
    └──────────────────→ PC Number
      1  2  3  4  5  6
```

> [!tip] Choosing q
> Look for the "**elbow**" — where eigenvalues start to flatten.

## Advantages & Disadvantages

| Advantages | Disadvantages |
|------------|---------------|
| ✅ Easy to implement (explicit formulas) | ❌ Suitable only for **linear** dependencies |
| ✅ Easy to interpret | ❌ **Non-linear version**: Kernel PCA |
| | ❌ Sensitive to [[outliers]] |
| | ❌ Only for **numerical** (cardinal) data |

## One-Line Summary

> PCA = linear dimension reduction using eigenvectors — keeps directions with largest variance (eigenvalues).

## Related

- [[Kernel PCA]]
- [[Singular Value Decomposition]]
- [[Dimension Reduction]]
- [[Eigenvalues and Eigenvectors]]
- [[Covariance Matrix]]
- [[Scree Plot]]
- [[Biplot]]
