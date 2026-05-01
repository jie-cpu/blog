---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Clustering

Grouping similar data objects into clusters. Depends on **distance** measurements between data points.

## Applications

| Application | Description |
|-------------|-------------|
| Data distribution | Understanding how data is organized |
| Outlier detection | Often used as a preprocessing step |

## Types of Clustering

### 1. Partitioning Methods

- [[K-means Algorithm]]

### 2. Hierarchical Clustering

Depends on distance with different linkage methods:

| Linkage Type | Description |
|--------------|-------------|
| **Single linkage** | Minimum distance between clusters |
| **Complete linkage** | Maximum distance between clusters |
| **Average linkage** | Mean distance between clusters |

#### Specific Algorithms

- **[[AGNES]]** (Agglomerative Nesting)
    - Bottom-up approach (each point starts as its own cluster)
    - Uses single-link method
    - Based on dissimilarity matrix
    - Merges clusters with least dissimilarity

- **[[DIANA]]** (Divisive Analysis)
    - Top-down approach (starts with one cluster, splits recursively)

### 3. Density-Based Methods

- **[[DBSCAN]]**
    - Forms clusters based on dense regions
    - Can find arbitrarily shaped clusters
    - Handles noise/outliers naturally

## Cluster Assessment

Evaluating the quality of clustering results (internal and external validation metrics).

## One-Line Summary

> Clustering = grouping similar data points using distance — choose method based on data shape and needs.

## Related

- [[Distance Metrics]] (Euclidean, Manhattan, etc.)
- [[Silhouette Score]]
- [[Elbow Method]]
- [[Dendrogram]]