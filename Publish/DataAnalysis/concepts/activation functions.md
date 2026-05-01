---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Neural Network Activation Functions: A Quick Guide

Activation functions decide whether a neuron should "fire" or not. Here are the four essential ones:

## The Four Key Functions

| Function | Range | Passes Through (0,0)? |
|----------|-------|----------------------|
| **Threshold** | {0,1} | No |
| **ReLU** | [0, ∞) | No (kink at 0) |
| **Sigmoid (Logistic)** | (0,1) | No — passes through (0,0.5) |
| **Tanh** | (-1,1) | Yes — passes through (0,0) |

## One-Line Summary

- **Threshold** — binary on/off (old school)
- **ReLU** — max(0,x), simple and fast (modern default)
- **Sigmoid** — smooth S-curve, output between 0 and 1
- **Tanh** — zero-centered version of sigmoid, output between -1 and 1

## Quick Pick Guide
