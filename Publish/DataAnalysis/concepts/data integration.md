---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Data Integration

Combining data from **multiple sources** that may be redundant, heterogeneous, or inconsistent.

## Why Need Data Integration?

| Problem | Description |
|---------|-------------|
| **Multiple sources** | Data comes from different databases/files |
| **Redundant** | Same information repeated |
| **Heterogeneous** | Different formats or structures |
| **Inconsistent** | Conflicting values or definitions |

## How to Integrate

### 1. Redundancy Detection

Expressing the same information with less data.

**Example:**
- `Age = Current Year – Year of birth`
- `Adult = Age > 17`

> [!tip] Correlation analysis
> Can detect redundant attributes (e.g., high correlation between `Age` and `Adult`)

### 2. Schema Integration

Combining different table structures and attribute names into a unified schema.

### 3. Inconsistency Detection

Identifying and resolving conflicting values across sources.

## Heterogeneity

Different data types, units, or representations across sources.

![[heterogeneity.jpg]]

## One-Line Summary

> Data integration = combining multi-source data by resolving redundancy, heterogeneity, and inconsistency.

## Related

- [[Data Cleaning]]
- [[Schema Matching]]
- [[ETL]]
- [[Data Warehousing]]
- [[Redundancy Detection]]