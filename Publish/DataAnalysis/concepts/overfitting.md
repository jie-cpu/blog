---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Overfitting, Underfitting, and Right Fit

The three states of model performance on training vs test data.

## Visual Comparison

```
Underfit (High Bias)     Right Fit           Overfit (High Variance)
     ╭───╮                   ╭─╮                    ╭─╮
    ╱     ╲                 ╱   ╲                  ╱ ╲ ╱ ╲
   │   ●   │               │  ●  │                │ ●   ● │
   ╲     ╱                 ╲   ╱                  ╲     ╱
     ╰───╯                   ╰─╘                    ╰───╯
  Too simple              Just right            Too complex
```

## The Three States

| State | Training Performance | Test Performance | Problem |
|-------|---------------------|------------------|---------|
| **Underfitting** | Poor | Poor | Model too simple |
| **Right Fit** | Good | Good | Just right ✅ |
| **Overfitting** | Excellent | Poor | Model memorized noise |

## Characteristics

### Underfitting (High Bias)

| Sign | Description |
|------|-------------|
| Training error | High |
| Test error | High (similar to training) |
| Cause | Model too simple, not enough features |
| Fix | Increase complexity, add features |

### Right Fit

| Sign | Description |
|------|-------------|
| Training error | Low |
| Test error | Low (close to training) |
| Goal | What we want! |

### Overfitting (High Variance)

| Sign | Description |
|------|-------------|
| Training error | Very low (near zero) |
| Test error | High (much worse than training) |
| Cause | Model too complex, not enough data |
| Fix | More data, regularization, simplify |

## Analogy: Exam Studying

| State | Studying | Test Result |
|-------|----------|-------------|
| **Underfit** | Didn't study at all | Fails |
| **Right fit** | Studied concepts, understood material | Passes well |
| **Overfit** | Memorized exact answers to practice questions | Fails on new questions |

## The Trade-off

```
Error
  ↑
  │                    ╭── Test Error
  │                   ╱    ╲
  │    Train Error   ╱        ╲
  │   ╭─────────────╯          ╲
  │  ╱                          ╲
  │ ╱                            ╲
  └──────────────────────────────────→ Model Complexity
       Underfit      Right        Overfit
```

## One-Line Summary

> Underfit = too simple (high bias) · Overfit = too complex (high variance) · Right fit = sweet spot.

## Related

- [[Bias-Variance Tradeoff]]
- [[Preventing Overfitting]]
- [[Cross-Validation]]
- [[Regularization]]
- [[Training and Inference]]
- [[Learning Curves]]
```

---

This version is:

- **Obsidian-ready** — copy and paste
- **ASCII visualization** for all three states
- **Table comparing** training/test performance
- **Characteristics table** with signs, causes, fixes
- **Study exam analogy** for intuition
- **Bias-variance tradeoff ASCII curve**
- **Links ready** — `[[Bias-Variance Tradeoff]]`, `[[Preventing Overfitting]]`

Want me to add concrete examples (e.g., polynomial regression with degree 1 vs 5 vs 15) or learning curve interpretation?