---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Similarity & Distance Metrics

## Core Terms

| Term | Description |
|------|-------------|
| **Distance Function** | Measures how **different** two objects are (dissimilarity) |
| **Similarity Function** | Measures how **alike** two objects are |

> [!note] Relationship
> Often: $\text{Similarity} = \frac{1}{1 + \text{Distance}}$ or $\text{Similarity} = 1 - \text{Normalized Distance}$

---

## By Data Type

### 1. Multidimensional Data

| Data Subtype | Metrics |
|--------------|---------|
| **Quantitative** (numeric) | [[Minkowski Distance]] (Euclidean, Manhattan, Chebyshev) |
| **Categorical** (nominal) | Hamming distance, Jaccard similarity |

### 2. Text Data

| Metric | Formula | Use Case |
|--------|---------|----------|
| **Cosine Similarity** | $\cos(\theta) = \frac{A \cdot B}{\|A\|\|B\|}$ | Document similarity, TF-IDF vectors |

### 3. Discrete Sequences

| Metric | Description |
|--------|-------------|
| **Longest Common Subsequence (LCS)** | Longest sequence appearing in both strings |

**Example:**
```
Sequence A: "ABCDEF"
Sequence B: "ACBEF"
LCS: "ABEF" (length 4)
```

### 4. Graphs

| Metric | Algorithm | Description |
|--------|-----------|-------------|
| **Shortest paths** | [[Dijkstra's Algorithm]] | Distance between nodes |
| **Many paths** | [[PageRank]] | Node importance based on link structure |
| | [[SimRank]] | Similarity between nodes based on neighbors |

### 5. Time Series

| Metric | Description |
|--------|-------------|
| Euclidean distance | Point-wise difference |
| Dynamic Time Warping (DTW) | Aligns sequences that vary in speed |
| Cross-correlation | Measures lagged similarity |

### 6. High-Dimensional Data

| Challenge | Solution |
|-----------|----------|
| Curse of dimensionality | Distance concentration |
| Mitigation | Dimensionality reduction (PCA, t-SNE) before distance calculation |
| Alternative | Cosine similarity (less affected than Euclidean) |

---

## Quick Selection Guide

| Data Type | Recommended Metric |
|-----------|---------------------|
| Numeric vectors (low-dim) | Euclidean (L2) |
| Numeric vectors (high-dim) | Cosine similarity |
| Sparse data (bag-of-words) | Cosine, Jaccard |
| Binary vectors | Jaccard, Hamming |
| Categorical | Hamming, Matching coefficient |
| Sequences (same length) | Euclidean, DTW |
| Sequences (different lengths) | LCS, DTW |
| Graphs (node similarity) | SimRank |
| Graphs (node importance) | PageRank |

---

## One-Line Summary

> Choose distance/similarity based on data type: numeric → Minkowski, text → Cosine, sequences → LCS, graphs → shortest paths or PageRank/SimRank.

---

## Related

- [[Minkowski Distance]]
- [[Cosine Similarity]]
- [[Jaccard Index]]
- [[Dynamic Time Warping]]
- [[Dijkstra's Algorithm]]
- [[PageRank]]
- [[SimRank]]
- [[Curse of Dimensionality]]
- [[Longest Common Subsequence]]
