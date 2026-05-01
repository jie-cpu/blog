---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Preventing Overfitting

Techniques to reduce overfitting and improve model generalization.

## Overview

| Technique | Description |
|-----------|-------------|
| **More training data** | Increase dataset size |
| **Data augmentation** | Create variations of existing data |
| **Dropout** | Randomly disable neurons during training |
| **Early Stopping** | Stop training before overfitting begins |
| **Regularization** | Add penalty term to loss function |

---

## 1. Train on More Data

The simplest and most effective way to prevent overfitting.

| Source | Example |
|--------|---------|
| Collect more real data | More images, more samples |
| Generate synthetic data | Data augmentation |

---

## 2. Data Augmentation

Applying **transformations** to expand the dataset and improve generalization.

### Common Transformations

| Domain | Transformations |
|--------|-----------------|
| **Images** | Rotation, cropping, flipping, scaling, adding noise, brightness adjustment |
| **Text** | Synonym replacement, back-translation, random insertion/deletion |
| **Audio** | Time stretching, pitch shifting, background noise |

```
Original → Rotate → Flip → Crop → Add Noise
   ○         ○        ○       ○         ○
   |         |        |       |         |
   └─────────┴────────┴───────┴─────────┘
                  Augmented Dataset
```

---

## 3. Dropout

Randomly **disable neurons** during training with probability $p$.

### How It Works

```
Full Network          Dropout (p=0.5)
    ○───○                 ○     ○
   ╱│╲ ╱│╲               ╱  ╲    
  ○ ○ ○ ○ ○             ○     ○  
   ╲│╱ ╲│╲               ╲     ╲
    ○───○                 ○     ○
```

| Parameter | Typical Value |
|-----------|---------------|
| Dropout rate ($p$) | 0.2 to 0.5 |
| **During training** | Randomly drop neurons |
| **During inference** | Use all neurons (scaled) |

> [!tip] Why it works
> Forces the network to not rely on any single neuron → learns redundant, robust features.

---

## 4. Early Stopping

Stop training **when validation performance stops improving**.

```
Performance
    ↑
    │  Train ↗↗↗
    │      ↗
    │    ↗    Validation ↗
    │  ↗           ↗↘
    │↗                ↘↘↘
    └──────────────────────→ Epochs
         ↑
    Stop here (best validation)
```

| What to Monitor | Description |
|-----------------|-------------|
| **Validation loss** | Stop when it stops decreasing |
| **Patience** | Wait N epochs before stopping |
| **Restore best weights** | Keep best model, not last |

---

## 5. Regularization

Add a **penalty term** to the loss function to constrain model parameters (especially weights) in terms of size or complexity.

### L1 vs L2 Regularization

| Type | Formula | Effect |
|------|---------|--------|
| **L1 (Lasso)** | $+\lambda \sum\|w_i\|$ | Produces sparse weights (some become 0) |
| **L2 (Ridge)** | $+\lambda \sum w_i^2$ | Shrinks weights toward 0 (none become exactly 0) |

### Combined Loss Function

$$
\mathcal{L}_{\text{total}} = \mathcal{L}_{\text{original}} + \lambda \cdot \text{penalty}(w)
$$

Where:
- $\lambda$ = regularization strength (hyperparameter)
- Larger $\lambda$ = stronger regularization

---

## Summary Table

| Technique | When to Use | Effectiveness |
|-----------|-------------|---------------|
| More data | Always (if possible) | ⭐⭐⭐⭐⭐ |
| Data augmentation | Limited data | ⭐⭐⭐⭐ |
| Dropout | Neural networks | ⭐⭐⭐⭐ |
| Early stopping | All models | ⭐⭐⭐ |
| Regularization | All models | ⭐⭐⭐⭐ |

## One-Line Summary

> Prevent overfitting by: more data + augmentation + dropout + early stopping + regularization.

## Related

- [[Overfitting]]
- [[Bias-Variance Tradeoff]]
- [[Regularization]]
- [[Dropout]]
- [[Early Stopping]]
- [[Data Augmentation]]
- [[Cross-Validation]]
- [[Generalization]]
```

---

This version is:

- **Obsidian-ready** — copy and paste
- **Five techniques** with clear sections
- **Data augmentation** with domain examples
- **Dropout diagram** and typical values
- **Early stopping visualization**
- **L1 vs L2 comparison**
- **Summary table** with effectiveness ratings
- **Links preserved** for all related concepts

Want me to add code examples (PyTorch/TensorFlow) for any of these techniques?