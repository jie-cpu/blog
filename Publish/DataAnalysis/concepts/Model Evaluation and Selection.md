---
title: My Post Title
date: 2026-04-20
updated: 2026-04-28
description: Optional short description
---
----
# Model Evaluation & Selection

Use **validation** and **test** sets to evaluate model performance.

## Classifier Evaluation Metrics

### Confusion Matrix

```
                Predicted
              Positive   Negative
Actual Positive    TP        FN
      Negative     FP        TN
```

### Common Metrics

| Metric | Formula | Interpretation |
|--------|---------|----------------|
| **Accuracy** | (TP+TN)/(TP+TN+FP+FN) | Overall correctness |
| **Error Rate** | (FP+FN)/(TP+TN+FP+FN) | 1 - Accuracy |
| **Sensitivity (Recall)** | TP/(TP+FN) | True positive rate |
| **Specificity** | TN/(TN+FP) | True negative rate |
| **Precision** | TP/(TP+FP) | Positive predictive value |
| **F-Measure** | 2×(Precision×Recall)/(Precision+Recall) | Harmonic mean |

### Example: Spam Filter

| Term | Meaning in Spam Detection |
|------|---------------------------|
| TP | Spam correctly marked as spam |
| TN | Legit email correctly kept |
| FP | Legit email marked as spam (bad!) |
| FN | Spam that got through (bad!) |

---

## Evaluate Classifier Accuracy

### Methods

| Method | Description |
|--------|-------------|
| **Holdout** | Split data into training + test (e.g., 70/30) |
| **Cross-Validation** | Multiple splits, average results |
| **Stratified Cross-Validation** | Maintains class proportions in each fold |
| **Bootstrap** | Sampling with replacement |

### Cross-Validation (k-fold)

```
Data → Split into k folds
      ↓
Train on k-1 folds, test on 1 fold
      ↓
Repeat k times (each fold serves as test once)
      ↓
Average k results
```

---

## Model Selection

| Tool | Purpose |
|------|---------|
| **Statistical Tests** | Compare if models are significantly different |
| **ROC Curves** | Visualize trade-off between TPR and FPR |

### ROC Curve

- **X-axis**: False Positive Rate (1 - Specificity)
- **Y-axis**: True Positive Rate (Sensitivity)
- **AUC** (Area Under Curve): Higher = Better model

---

## One-Line Summary

> Evaluate models using metrics (confusion matrix, precision/recall, F1), cross-validation, and ROC curves.

---

## Related

- [[Confusion Matrix]]
- [[Precision and Recall]]
- [[F1 Score]]
- [[Cross-Validation]]
- [[ROC Curve]]
- [[AUC]]
- [[Overfitting]]
- [[Bias-Variance Tradeoff]]
