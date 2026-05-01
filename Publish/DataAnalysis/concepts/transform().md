---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Vectorizer - transform() Method

The `transform()` method takes text data and converts it into a **[[document-term matrix]]** using the vocabulary learned by `fit()`.

## Function Overview

```
fit() learns vocabulary → transform() converts text to numbers
```

## Input

| Parameter | Description |
|-----------|-------------|
| `text` | Text to convert (same format as used in [[fit()]]) |

## Output

| Output Type | Description |
|-------------|-------------|
| **[[Sparse Matrix]]** | Efficient storage for data with mostly zeros |

## Important Rule

> [!warning] Must call `fit()` first!
> `transform()` relies on the vocabulary created by `fit()`. You cannot call `transform()` before `fit()`.

```python
# Correct order
vectorizer.fit(train_text)      # Learn vocabulary
X_train = vectorizer.transform(train_text)  # Convert training data
X_test = vectorizer.transform(test_text)    # Convert test data

# Wrong order ❌
X = vectorizer.transform(text)  # Error! No vocabulary yet
```

## Why Sparse Matrix?

| Fact | Implication |
|------|-------------|
| Most documents contain only a **small fraction** of all vocabulary words | Document-term matrix has mostly **zeros** |
| Sparse matrix stores **only non-zero values** | Saves memory and computation |

### Sparse Matrix Example

```
Vocabulary: ["apple", "banana", "cat", "dog", "elephant"] (5 words)

Document 1: "apple cat"        → [1, 0, 1, 0, 0]  (3 non-zero)
Document 2: "banana dog"       → [0, 1, 0, 1, 0]  (2 non-zero)
Document 3: "elephant"         → [0, 0, 0, 0, 1]  (1 non-zero)

Dense storage:  3×5 = 15 values
Sparse storage: stores only 3+2+1 = 6 values + indices
```

## Workflow Summary

```
Step 1: fit(train_data)     → Learn vocabulary
Step 2: transform(train_data) → Convert train to matrix
Step 3: transform(test_data)  → Convert test using SAME vocabulary
```

## One-Line Summary

> `transform()` = convert text to sparse document-term matrix using vocabulary from `fit()` — must call `fit()` first.

## Related

- [[fit()]]
- [[fit_transform]]
- [[Document-Term Matrix]]
- [[Sparse Matrix]]
- [[CountVectorizer]]
- [[Text Vectorization]]
