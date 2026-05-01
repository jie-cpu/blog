---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Chain Rule in Backpropagation

A core principle in neural network learning: gradients flow backward through the network, and **all incoming gradients must be summed up** at each node.

## The Key Rule

> [!important]
> When one node receives gradients from multiple paths, **sum them all** before continuing backward.

## Visual Example

```
        ┌───► Node B ───┐
        │               │
Node A ─┼               ├───► Output
        │               │
        └───► Node C ───┘

Gradient at Node A = grad from B + grad from C
```

## Why Summing?

| Scenario | Action |
|----------|--------|
| Single path | Pass gradient through |
| **Multiple paths** | **Sum all incoming gradients** |
| Shared weights | Accumulate updates from all uses |

## Common Application

In [[Backpropagation]]:
- A single weight may affect the loss through **multiple paths**
- All contributions must be **summed** to get the true gradient

## One-Line Summary

> Chain rule + gradient flow = sum all incoming gradients at every node.

## Related

- [[Backpropagation]]
- [[Gradient Descent]]
- [[Chain Rule]]
- [[Computational Graph]]
- [[Automatic Differentiation]]
