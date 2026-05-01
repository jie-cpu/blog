---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# DBSCAN

**Density-Based Spatial Clustering of Applications with Noise**

A clustering algorithm that groups together points that are closely packed together, marking points in low-density regions as outliers.

## Core Idea

Clusters are defined as **dense regions** separated by sparse regions.

## Key Parameters

| Parameter | Description |
|-----------|-------------|
| **ε (epsilon)** | Maximum distance between two points to be considered neighbors |
| **minPts** | Minimum number of points required to form a dense region |

## Point Types

| Type | Definition |
|------|------------|
| **Core point** | Has at least `minPts` points within ε distance (including itself) |
| **Border point** | Within ε of a core point but has fewer than `minPts` neighbors |
| **Noise point** | Neither core nor border (outlier) |

## Advantages

| Pro | Description |
|-----|-------------|
| ✅ | Finds **arbitrarily shaped** clusters (not just circles) |
| ✅ | Automatically detects **outliers** as noise |
| ✅ | No need to specify number of clusters (`k`) |

## Disadvantages

| Con | Description |
|-----|-------------|
| ❌ | Sensitive to ε and minPts parameters |
| ❌ | Struggles with varying density clusters |
| ❌ | Does not work well on high-dimensional data |

## One-Line Summary

> DBSCAN = density-based clustering that finds arbitrary shapes and marks outliers as noise.

## Related

- [[Clustering]]
- [[K-means]]
- [[HDBSCAN]]
- [[OPTICS]]
- [[Outlier Detection]]