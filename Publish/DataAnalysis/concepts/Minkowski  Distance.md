---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Minkowski Distance

A generalized distance metric that defines distance between two points in $d$-dimensional space.

## General Formula

$$
\text{Dist}(\mathbf{x}, \mathbf{y}) = \left( \sum_{i=1}^{d} |x_i - y_i|^p \right)^{1/p}
$$

Where:
- $\mathbf{x}, \mathbf{y}$ = two points in $d$-dimensional space
- $d$ = number of dimensions
- $p$ = parameter that determines the type of distance

## Special Cases (by $p$ value)

| Parameter | Distance Name | Formula | Intuition |
|-----------|---------------|---------|------------|
| $p = 1$ | **Manhattan (L1)** | $\sum\|x_i - y_i\|$ | City block distance |
| $p = 2$ | **Euclidean (L2)** | $\sqrt{\sum(x_i - y_i)^2}$ | Straight line |
| $p = \infty$ | **Maximum (L∞)** | $\max\|x_i - y_i\|$ | Largest single dimension difference |

## Visual Comparison (2D)

```
Manhattan (L1)          Euclidean (L2)          Maximum (L∞)
    ┌─────┐                  ╱                         
    │     │                ╱                          
    │     │              ╱                           □
    └─────┘            ╱                            
    
Path follows grid     Straight line         Max of x or y diff
```

## When to Use Which

| Distance | Best For |
|----------|----------|
| **Manhattan (L1)** | High-dimensional data, sparse vectors, grid-like paths |
| **Euclidean (L2)** | Most common, continuous spaces, intuitive geometry |
| **Maximum (L∞)** | When only the largest deviation matters |

## One-Line Summary

> Minkowski distance = family of distances where $p=1$ is Manhattan, $p=2$ is Euclidean, $p=\infty$ is Maximum.

## Related

- [[Distance Metrics]]
- [[Euclidean Distance]]
- [[Manhattan Distance]]
- [[Chebyshev Distance]]
- [[Clustering]]
- [[KNN]]
