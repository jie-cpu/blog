---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Backpropagation

Adjust weights to minimize **loss** (difference between prediction and true value).

## Core Idea

Forward: predict → calculate loss  
Backward: propagate error → update weights

## Problem It Solved

Before backpropagation: single-layer networks couldn't effectively learn weights.

After backpropagation: deep networks became trainable.

## Simple Workflow

- Forward pass: input → hidden → output → loss
- Backward pass: loss → output layer → hidden layer → update weights

## One Line

> Backpropagation = how neural networks learn from mistakes.

## Related

- [[Gradient Descent]]
- [[Loss Function]]
- [[Chain Rule]]
- [[Neural Network]]