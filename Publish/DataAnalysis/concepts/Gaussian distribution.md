---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Gaussian Distribution (Normal Distribution)

A continuous probability distribution characterized by its **bell-shaped curve**.

## Parameters

| Parameter | Symbol | Description |
|-----------|--------|-------------|
| **Mean** | $\mu$ | Center of the distribution |
| **Standard Deviation** | $\sigma$ | Spread or width of the curve |

## Probability Density Function (PDF)

$$
f(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{(x - \mu)^2}{2\sigma^2}}
$$

## Key Property: The 68-95-99.7 Rule

| Range | % of Data |
|-------|-----------|
| $\mu \pm 1\sigma$ | ≈ 68% |
| $\mu \pm 2\sigma$ | ≈ 95% |
| $\mu \pm 3\sigma$ | ≈ 99.7% |

## Visual Shape

```
                 ↑
                 │        ╭─────╮
                 │      ╱         ╲
                 │    ╱             ╲
                 │  ╱                 ╲
                 │ ╱                   ╲
                 └────────────────────────→
                   μ-3σ μ-2σ μ-σ  μ μ+σ μ+2σ μ+3σ
```

## One-Line Summary

> Gaussian = bell-shaped distribution defined by mean (center) and standard deviation (spread).

## Related

- [[Standard Normal Distribution]]
- [[Central Limit Theorem]]
- [[Probability Distribution]]
- [[Z-Score]]
- [[Bell Curve]]
