---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Recurrent Neural Networks (RNNs)

**RNNs** are neural networks designed for **sequences of variable length**. They update the hidden state $H$ based on input $X_t$ and **previous hidden state** $H_{t-1}$ using the same update rule repeatedly.

## Core RNN Formula

$$
H_t = f(W_{xh}X_t + W_{hh}H_{t-1} + b_h)
$$

- $H_t$ = hidden state at time $t$
- $X_t$ = input at time $t$  
- $H_{t-1}$ = previous hidden state (memory)
- Same weights applied at **every time step**

## Why RNNs?

| Property | Benefit |
|----------|---------|
| **Variable length sequences** | Handle different input/output lengths |
| **Parameter sharing** | Same weights across time steps |
| **Memory** | Hidden state preserves information from past |

## RNN Architectures

```
One to One          One to Many            Many to One           
(Standard NN)       (Image Captioning)     (Action Recognition)
    X                   X                       X
    ↓                   ↓                       ↓
    H                   H → H → H ...          H → H → H ...
    ↓                   ↓                       ↓
    Y                   Y   Y   Y               Y
```

```
Many to Many           Many to Many (sync)
(Translation)          (Object Tracking)
X → X → X ...          X → X → X ...
↓   ↓   ↓              ↓   ↓   ↓
H → H → H ...          H → H → H ...
↓   ↓   ↓              ↓   ↓   ↓
Y   Y   Y              Y   Y   Y (per frame)
```

## Architecture Summary

| Architecture | Input | Output | Example |
|--------------|-------|--------|---------|
| **One to Many** | Single | Sequence | Image captioning, Music generation |
| **Many to One** | Sequence | Single | Action recognition, Sentiment analysis |
| **Many to Many** (sync) | Sequence | Sequence (per step) | Object tracking, Video segmentation |
| **Many to Many** (async) | Sequence | Sequence (different length) | Machine translation |

## Applications by Domain

### Computer Vision
| Task | Type | Description |
|------|------|-------------|
| Multiple object recognition | Many to Many | Recognize multiple objects |
| Image segmentation | Many to Many | Pixel-wise classification |
| Object tracking | Many to Many (sync) | Track object per frame |
| Image generation | One to Many | Generate image from description |
| Image annotation | One to Many | Describe image content |
| Image captioning | One to Many | Generate sentence from image |

### Natural Language Processing
| Task | Type | Description |
|------|------|-------------|
| Machine translation | Many to Many (async) | Sentence → Sentence |
| Text generation | One to Many | Generate text from prompt |

## Hidden State as Memory

```
Time:    t=0      t=1      t=2      t=3
         ↓        ↓        ↓        ↓
Input:   X₁  →    X₂  →    X₃  →    X₄
         ↓        ↓        ↓        ↓
Hidden:  H₁  →    H₂  →    H₃  →    H₄
         ↓        ↓        ↓        ↓
         (H₁ remembers X₁)
         (H₂ remembers X₁,X₂)
         (H₃ remembers X₁,X₂,X₃)
```

## Advantages & Challenges

| Advantages | Challenges |
|------------|------------|
| ✅ Handles variable length sequences | ❌ Vanishing/exploding gradients |
| ✅ Parameter sharing | ❌ Difficult to learn long-range dependencies |
| ✅ Maintains memory | ❌ Sequential (cannot parallelize fully) |

## Extensions

| Variant | Improvement |
|---------|-------------|
| **LSTM** | Long Short-Term Memory — solves vanishing gradient |
| **GRU** | Gated Recurrent Unit — simpler than LSTM |
| **Bidirectional RNN** | Looks forward and backward in sequence |

## One-Line Summary

> RNN = neural network with memory — same weights applied to each time step, handles variable length sequences.

## Related

- [[LSTM]]
- [[GRU]]
- [[Sequence Modeling]]
- [[Vanishing Gradient]]
- [[Bidirectional RNN]]
- [[Encoder-Decoder]]
- [[Attention Mechanism]]