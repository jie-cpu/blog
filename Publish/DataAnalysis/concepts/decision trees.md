---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Decision Tree - Information Gain

A **top-down** approach to building decision trees by selecting the best feature to split on.

## Core Concepts

### Entropy

A measure of **impurity** or **uncertainty** in a dataset.

- High entropy = mixed classes (more uncertainty)
- Low entropy = pure classes (less uncertainty)

### Information Gain

The reduction in entropy after splitting on a feature.

> [!important] **Selection criterion**
> Choose the feature with the **largest** information gain — the bigger, the better.

## Formula

$$
\text{InfoGain} = \text{Entropy}(Parent) - \sum \frac{|Child|}{|Parent|} \times \text{Entropy}(Child)
$$

## Workflow (Top-Down)

1. Calculate entropy of root node (parent)
2. For each feature:
   - Split data by feature values
   - Calculate weighted average entropy of children
   - Compute information gain = parent entropy - weighted child entropy
3. Select feature with HIGHEST information gain
4. Split and repeat recursively

## Process Summary

| Step | Action |
|------|--------|
| 1 | Start with full dataset |
| 2 | Compute entropy of current node |
| 3 | Evaluate all features |
| 4 | Pick feature with **max information gain** |
| 5 | Split dataset |
| 6 | Repeat for each child node |

## One-Line Summary

> Decision trees = top-down greedy algorithm choosing splits that maximize information gain (minimize entropy).

## Related

- [[Entropy]]
- [[Information Gain]]
- [[Decision Tree]]
- [[ID3 Algorithm]]
- [[Gini Impurity]]

> [!example] Calculation Example
> See slide P25 for detailed calculation example.
