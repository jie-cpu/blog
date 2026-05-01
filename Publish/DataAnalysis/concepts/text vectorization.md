---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Text Vectorization

Machine learning models work with **numbers**, not words. To use text data (sentences, documents, tweets) for training, you must first convert it into a **numerical representation**.

## The Core Problem

```
Text Data                    Numerical Data
    ↓                             ↓
"Hello world"    →    [0.5, 0.2, 0.8, ..., 0.1]
"I love ML"      →    [0.1, 0.9, 0.3, ..., 0.4]
"Spam email"     →    [0.0, 0.7, 0.2, ..., 0.6]
```

## Why?

| Fact | Implication |
|------|-------------|
| ML models are **mathematical** | They require numerical input |
| Text is **symbolic** | Words have no inherent numeric value |
| Solution: **[[text vectorization]]** | Convert text → numbers |

## Common Vectorization Methods

| Method | Description |
|--------|-------------|
| [[CountVectorizer]] | Word counts |
| [[TF-IDF]] | Term frequency-inverse document frequency |
| [[Word Embeddings]] | Dense vectors (Word2Vec, GloVe) |

## One-Line Summary

> Text vectorization = converting text into numbers so ML models can process it.

## Related

- [[Text Vectorization]]
- [[CountVectorizer]]
- [[TF-IDF]]
- [[Word Embeddings]]
- [[Bag of Words]]
- [[NLP]]
- [[Preprocessing]]

