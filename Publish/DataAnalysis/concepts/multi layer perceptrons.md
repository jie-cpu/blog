---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Multi-Layer Perceptron (MLP)

A **Multi-Layer Perceptron** is a class of feedforward artificial neural network. It consists of at least three layers: an input layer, one or more hidden layers, and an output layer.

## MLP vs General Neural Network

| Aspect | General Neural Network | MLP |
|--------|------------------------|-----|
| **Layers** | Any architecture | At least 3 layers (input + hidden + output) |
| **Activation** | Various | Typically **non-linear** (sigmoid, tanh, ReLU) |
| **Learning** | Various | **Backpropagation** + Gradient Descent |

## Architecture

```
Input Layer      Hidden Layer(s)      Output Layer
    ○─────────────○─────────────○
    ○─────────────○─────────────○
    ○─────────────○─────────────○
       (fully connected / dense)
```

### Key Properties

| Property | Description |
|----------|-------------|
| **Fully Connected** | Every neuron connects to all neurons in next layer |
| **Feedforward** | Information moves only forward (no cycles) |
| **Non-linear** | Uses [[Activation Functions]] to learn complex patterns |

## Mathematical Formulation

For each layer $l$:

$$
\mathbf{z}^{(l)} = \mathbf{W}^{(l)} \mathbf{a}^{(l-1)} + \mathbf{b}^{(l)}
$$
$$
\mathbf{a}^{(l)} = f^{(l)}(\mathbf{z}^{(l)})
$$

Where:
- $\mathbf{W}$ = weight matrix
- $\mathbf{b}$ = bias vector
- $f$ = [[Activation Functions|activation function]]
- $\mathbf{a}$ = output of previous layer

## How MLP Learns

```
Forward Pass
    Input → Hidden Layer 1 → Hidden Layer 2 → Output → Loss
    
Backward Pass ([[Backpropagation]])
    Loss → Output Layer → Hidden Layer 2 → Hidden Layer 1 → Update Weights
```

## Common Configurations

| Problem Type | Output Layer Activation | Loss Function |
|--------------|------------------------|---------------|
| **Binary Classification** | Sigmoid | Binary Cross-Entropy |
| **Multi-class Classification** | Softmax | Categorical Cross-Entropy |
| **Regression** | Linear | MSE / MAE |

## MLP Limitations

| Limitation | Description |
|------------|-------------|
| ❌ **No spatial awareness** | Treats pixels as flat vector (unlike CNN) |
| ❌ **No sequence memory** | No temporal understanding (unlike RNN) |
| ❌ **Many parameters** | Fully connected → large models |
| ❌ **Prone to [[Overfitting]]** | Requires regularization |

## When to Use MLP

| Use Case | Why |
|----------|-----|
| Tabular data | Works well with structured features |
| Small/medium datasets | Before scaling to deep learning |
| Baseline model | Simple, interpretable, effective |

## One-Line Summary

> MLP = fully connected feedforward network with ≥3 layers, learning via backpropagation — the foundation of deep learning.

## Related

- [[Neural Networks]]
- [[Perceptron]]
- [[Feedforward Neural Network]]
- [[Backpropagation]]
- [[Activation Functions]]
- [[Deep Learning]]
- [[Fully Connected Layer]]
- [[Dense Layer]]
