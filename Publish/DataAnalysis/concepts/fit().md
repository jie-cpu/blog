---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# CountVectorizer - The fit() Method

The `fit()` method is the first step in converting text into numerical format for machine learning.

## What fit() Does

| Step | Action |
|------|--------|
| **1. Learns the Vocabulary** | Analyzes input text to find all unique words |
| **2. Stores the Vocabulary** | Saves vocabulary internally in `vectorizer` object |

## Input Format

`text` should be a **sequence of text documents** (list or array of strings):

```python
text = [
    "The cat sat on the mat.",
    "The dog chased the cat.",
    "A bird flew away."
]

vectorizer.fit(text)  # Learn vocabulary from 'text'
```

## Vocabulary Storage

After `fit()`, the vocabulary is accessible via `[[vocabulary_]]`:

```python
print(vectorizer.vocabulary_)
# Output example: {'the': 5, 'cat': 0, 'sat': 4, 'on': 3, 'mat': 2, 'dog': 1, ...}
```

## Workflow Overview

```
fit()  →  Learn vocabulary from training data
           ↓
transform() → Convert text to word count matrix
           ↓
         Numerical data ready for ML
```

## One-Line Summary

> `fit()` learns and stores the vocabulary — the crucial link between words and numbers.

## Related

- [[vocabulary_]]
- [[CountVectorizer]]
- [[fit_transform]]
- [[transform]]
- [[Document-Term Matrix]]

