---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Model Evaluation and Selection

## Data Split: TrainingData = {L, V, T}

| Set | Symbol | Purpose |
|-----|--------|---------|
| **Learning Set** | $L = (X_L, Y_L)$ | Train the model |
| **Validation Set** | $V = (X_V, Y_V)$ | Tune hyperparameters, early stopping |
| **Test Set** | $T = (X_T, Y_T)$ | Final evaluation (after training) |

## Visual Split

```
Original Data
     ↓
┌────┴────┬────────┐
│         │        │
 L        V        T
(Learn)  (Val)   (Test)
~60-70%  ~10-20%  ~10-20%
```

## Process: Cross-Validation (e.g., 10-fold)

![[10_folds.jpg]]

## Errors

| Error Type | Description | Indicates |
|------------|-------------|-----------|
| **Train error** | Error on learning set | Underfitting (if high) |
| **Validation error** | Error on validation set | Overfitting (if much higher than train) |
| **Test error** | Error on test set | Final generalization performance |

## Training vs Inference Phases

### Validation (during training)

| Aspect | Description |
|--------|-------------|
| Data | **Unseen** to model, **known** label (to human) |
| When | **During** training |
| Purpose | Tune hyperparameters, early stopping |
| Output | Return the **best model** |

### Test (after training)

| Aspect | Description |
|--------|-------------|
| Data | **Unseen** to model, **known** label (to human) |
| When | **After** training |
| Purpose | Final evaluation |
| Output | Unbiased estimate of generalization |

## Golden Rule

> [!danger] Never test your model on the same data it was trained on!

```
Train on L → Validate on V → Final evaluation on T
     ↑                            ↑
  Uses labels                Uses labels
  (to learn)                 (only to evaluate)
```

## One-Line Summary

> Split data into L (learn), V (validate), T (test) — use V for tuning, T only for final evaluation.

## Related

- [[Cross-Validation]]
- [[Overfitting]]
- [[Underfitting]]
- [[Train-Test Split]]
- [[Hyperparameter Tuning]]
- [[Early Stopping]]
- [[Generalization]]
