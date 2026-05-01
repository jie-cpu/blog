---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Singular Value Decomposition (SVD)

A mathematical technique for **[[data reduction]]** and **[[dimensionality reduction]]**. Decomposes a matrix $A$ into three matrices:

$$
A = U \Sigma V^T
$$

## The Three Matrices

| Matrix | Name | Properties |
|--------|------|------------|
| $U$ | Left singular vectors | Orthogonal (columns are orthonormal) |
| $\Sigma$ | Singular values | Diagonal, sorted in **descending order** |
| $V^T$ | Right singular vectors | Orthogonal (rows are orthonormal) |

## Visual Representation

```
A        =     U     ×    Σ    ×    V^T
┌─────┐     ┌─────┐   ┌─────┐   ┌─────┐
│     │     │     │   │σ1   │   │     │
│ m×n │  =  │ m×m │ × │  σ2 │ × │ n×n │
│     │     │     │   │   ╱│   │     │
└─────┘     └─────┘   └─────┘   └─────┘
```

## SVD for Dimensionality Reduction

Keep only **top $k$ singular values**:

```
A ≈ U_k × Σ_k × V_k^T

Where:
- k = number of components to keep
- Σ_k = largest k singular values
```

### Why Keep Top k?

| Position | Singular Value | Importance |
|----------|----------------|------------|
| σ₁ | Largest | Most variance |
| σ₂ | Second largest | ... |
| ... | ... | ... |
| σₖ | k-th largest | Cutoff point |
| σ_{k+1} ... | Small | Noise (discard) |

## Applications

| Application | How SVD Helps |
|-------------|----------------|
| **[[Principal Component Analysis (PCA)]]** | SVD is the numerical method behind PCA |
| **[[Image Compression]]** | Keep top k singular values → approximate image |
| **[[Latent Semantic Analysis]] (LSA)** | Find hidden topics in text |
| **[[Noise Reduction]]** | Small singular values often = noise |
| **[[Data Imputation]]** | Predict missing values |

## Image Compression Example

```
Original: 1000×1000 pixels (1,000,000 values)
                    ↓ SVD with k=50
Compressed: Store U(1000×50) + Σ(50) + V^T(50×1000)
         ≈ 100,000 values (10x compression)
```

## Advantages & Disadvantages

| Advantages | Disadvantages |
|------------|---------------|
| ✅ Optimal low-rank approximation | ❌ Computationally expensive for large matrices |
| ✅ Preserves most variance | ❌ Requires dense matrix |
| ✅ Works with any matrix (not just square) | ❌ Less interpretable than original features |
| ✅ Numerical stability | |

## Relationship to PCA

| Aspect | PCA | SVD |
|--------|-----|-----|
| **Input** | Covariance matrix | Any data matrix |
| **Output** | Principal components | U, Σ, V^T |
| **Relationship** | Principal components come from **SVD** of centered data | Computing method for PCA |

## One-Line Summary

> SVD = $A = U\Sigma V^T$ — keep top k singular values for optimal low-rank approximation and dimensionality reduction.

## Related

- [[Data Reduction]]
- [[Dimensionality Reduction]]
- [[Principal Component Analysis (PCA)]]
- [[Eigenvalues and Eigenvectors]]
- [[Low-Rank Approximation]]
- [[Image Compression]]
- [[Latent Semantic Analysis]]
- [[Noise Reduction]]
