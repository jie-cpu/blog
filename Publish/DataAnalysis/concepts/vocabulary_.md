---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# vocabulary_ Attribute (CountVectorizer)

The `vocabulary_` attribute (note the **trailing underscore**) is a **dictionary** that stores the mapping between each unique word and its index in the vocabulary.

## After fit()

Once you've called `fit()`, the vocabulary is available:

```python
print(vectorizer.vocabulary_)
```

## Output Example

```python
# Output (order may vary):
{
    'the': 7,
    'cat': 1,
    'sat': 5,
    'on': 4,
    'mat': 3,
    'dog': 2,
    'chased': 0,
    'bird': 0,      # Note: multiple words can map to same index?
    'flew': 3,
    'away': 0
}
```

> [!warning] Note on the Example
> The example above shows potential duplicate indices (e.g., `'chased'`, `'bird'`, `'away'` all at index 0). In a real `CountVectorizer`, each unique word gets a **unique index**. The example likely has a typo — indices should be distinct.

## Correct Interpretation

| Word | Index |
|------|-------|
| `'the'` | 7 |
| `'cat'` | 1 |
| `'sat'` | 5 |
| `'on'` | 4 |
| `'mat'` | 3 |
| `'dog'` | 2 |

## Important Notes

| Note | Description |
|------|-------------|
| **Trailing underscore** | Convention in scikit-learn for attributes learned from data |
| **Dictionary mapping** | `word → index` |
| **Index order** | Determined by order words are **encountered** during `fit()` |
| **Used by transform()** | Indices tell where to put counts in the document-term matrix |

## Vocabulary Flow

```
Text: "The cat sat on the mat"
           ↓ fit()
Vocabulary: {'the': 0, 'cat': 1, 'sat': 2, 'on': 3, 'mat': 4}
           ↓ transform()
Document-term matrix column positions match these indices
```

## Complete Workflow

```python
from sklearn.feature_extraction.text import CountVectorizer

text = ["The cat sat on the mat"]
vectorizer = CountVectorizer()
vectorizer.fit(text)

# Print the vocabulary mapping
print(vectorizer.vocabulary_)
# {'the': 0, 'cat': 1, 'sat': 2, 'on': 3, 'mat': 4}

# Transform text to matrix
X = vectorizer.transform(text)

# X's columns correspond to vocabulary indices
```

## One-Line Summary

> `vocabulary_` = dictionary mapping `{word: index}` learned during `fit()` — indices determine column positions in document-term matrix.

## Related

- [[fit()]]
- [[transform()]]
- [[CountVectorizer]]
- [[Document-Term Matrix]]
- [[vocabulary_ (scikit-learn convention)]]
