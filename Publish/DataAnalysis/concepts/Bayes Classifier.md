---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Naïve Bayes Classifier

A probabilistic classifier based on **Bayes' Theorem** with the "naïve" assumption that features are independent.

## Bayes' Theorem

$$
P(\text{Class}|\text{Features}) = \frac{P(\text{Features}|\text{Class}) \times P(\text{Class})}{P(\text{Features})}
$$

## The Naïve Bayes Formula

$$
P = P(X|C_i) \times P(C_i)
$$

Where:
- $P(C_i)$ = prior probability of class $i$
- $P(X|C_i)$ = likelihood of features $X$ given class $C_i$

## Step-by-Step Example (P41)

### Step 1: Classes
- $C_1$, $C_2$
- $P(C_1)$, $P(C_2)$

### Step 2: Data to classify
- $X = (X_1, X_2, X_3, ...)$

### Step 3: Compute conditional probabilities
For each feature and each class:
- $P(X_1|C_1)$, $P(X_1|C_2)$
- $P(X_2|C_1)$, $P(X_2|C_2)$
- $P(X_3|C_1)$, $P(X_3|C_2)$

### Step 4: Calculate likelihood for each class
$$
P(X|C_1) = P(X_1|C_1) \times P(X_2|C_1) \times P(X_3|C_1)
$$
$$
P(X|C_2) = P(X_1|C_2) \times P(X_2|C_2) \times P(X_3|C_2)
$$

### Step 5: Multiply by prior
$$
P(C_1|X) \propto P(X|C_1) \times P(C_1)
$$
$$
P(C_2|X) \propto P(X|C_2) \times P(C_2)
$$

Choose class with higher value.

## Problems

| Problem | Description |
|---------|-------------|
| **Independence assumption** | Features are assumed independent — often false in real data |
| **Zero probability** | If any $P(X_k|C_i) = 0$, entire product becomes zero |

## Solution: Laplace Correction (Laplacian Estimator)

Add a small count (usually 1) to every feature count to avoid zero probabilities.

$$
P(X_k|C_i) = \frac{\text{count}(X_k|C_i) + 1}{\text{total count}(C_i) + \text{number of possible values}}
$$

## One-Line Summary

> Naïve Bayes = Bayes' theorem + feature independence assumption + Laplace correction for zero probabilities.

## Related

- [[Bayes' Theorem]]
- [[Conditional Probability]]
- [[Laplace Smoothing]]
- [[Classification]]