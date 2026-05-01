---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Learning Rate

The **learning rate** determines how big each step you take along the direction of gradient descent.

## Definition

| Aspect | Description |
|--------|-------------|
| **Symbol** | $\alpha$ (alpha) or $\eta$ (eta) |
| **Role** | Step size in gradient descent |
| **Effect** | Controls how much we adjust weights based on gradient |

## The Update Rule

$$
\theta_{\text{new}} = \theta_{\text{old}} - \alpha \cdot \nabla J(\theta)
$$

Where:
- $\theta$ = model parameters (weights)
- $\alpha$ = learning rate (step size)
- $\nabla J(\theta)$ = gradient (direction of steepest ascent)

## Learning Rate Impact

| Type | Step Size | Effect |
|------|-----------|--------|
| **Too large** | Too big | May overshoot and **diverge** |
| **Too small** | Too tiny | Very slow convergence |
| **Just right** | Balanced | Converges efficiently |

## Visual Analogy

```
Loss
 ↑
 │           ╲
 │            ╲  ← Too large: jumps past minimum
 │             ╲
 │        ●────→★  ← Just right: lands at minimum
 │       ╱
 │      ╱  ← Too small: many tiny steps
 │     ╱
 └──────────────────→ Steps
```

## Common Values

| Scenario | Typical Learning Rate |
|----------|----------------------|
| Starting point | 0.01 to 0.001 |
| Fine-tuning | 0.0001 or smaller |
| Adaptive methods (Adam) | 0.001 (default) |

## One-Line Summary

> Learning rate = step size in gradient descent — too big diverges, too small crawls.

## Related

- [[Gradient Descent]]
- [[Optimizer]]
- [[Learning Rate Scheduler]]
- [[Convergence]]
- [[Adam]]
- [[Stochastic Gradient Descent]]
```

---

This version is:

- **Obsidian-ready** — copy and paste
- **Definition table** with symbol and role
- **Update formula** in proper LaTeX
- **Impact table** — too large vs too small vs just right
- **ASCII visual** showing step size effects
- **Typical values** for practical reference
- **Links ready** — `[[Gradient Descent]]`, `[[Optimizer]]`, etc.

Want me to add learning rate scheduling strategies (step decay, exponential decay, cosine annealing) or adaptive methods like Adam?