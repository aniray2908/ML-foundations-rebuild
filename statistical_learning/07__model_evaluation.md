# 08 – Model Evaluation for Classification

This module formalizes evaluation beyond accuracy.

It covers:

- Confusion matrix
- Precision & Recall
- F1 score
- ROC curve
- Precision–Recall curve
- Threshold tradeoffs
- Calibration

---

# 1. Confusion Matrix

Binary classification outcomes:

|                | Predicted Positive | Predicted Negative |
|---------------|-------------------|-------------------|
| Actual Positive | True Positive (TP) | False Negative (FN) |
| Actual Negative | False Positive (FP) | True Negative (TN) |

All evaluation metrics derive from these four quantities.

---

# 2. Accuracy

Accuracy = (TP + TN) / Total

Limitation:
Accuracy is misleading in imbalanced datasets.

Example:
If 99% of cases are negative,
predicting all negative yields 99% accuracy but zero usefulness.

---

# 3. Precision

Precision = TP / (TP + FP)

Measures:
Of all predicted positives, how many were correct?

High precision:
Few false positives.

Use when:
False positives are costly.

---

# 4. Recall (Sensitivity)

Recall = TP / (TP + FN)

Measures:
Of all actual positives, how many were detected?

High recall:
Few false negatives.

Use when:
Missing positives is costly.

---

# 5. Precision–Recall Tradeoff

Increasing threshold:

- Precision ↑
- Recall ↓

Decreasing threshold:

- Precision ↓
- Recall ↑

Threshold selection should reflect business cost.

---

# 6. F1 Score

F1 = 2 * (Precision * Recall) / (Precision + Recall)

Harmonic mean of precision and recall.

Useful when:
Precision and recall are equally important.

Limitation:
Ignores cost asymmetry.

---

# 7. ROC Curve

Plots:

True Positive Rate (Recall)
vs
False Positive Rate

FPR = FP / (FP + TN)

AUC measures ranking ability.

Limitation:
Can appear optimistic in imbalanced datasets.

---

# 8. Precision–Recall Curve

Plots:

Precision
vs
Recall

More informative than ROC when:
Positive class is rare.

Focuses directly on minority class performance.

---

# 9. Calibration

Calibration evaluates probability reliability.

A model is well-calibrated if:

Among all predictions of probability p,
approximately p fraction are actually positive.

Overconfident:
Predicted probabilities are too extreme.

Underconfident:
Predicted probabilities are too conservative.

Calibration matters when:
Probabilities drive decisions (risk scoring, pricing, resource allocation).

---

# 10. Discrimination vs Calibration

Discrimination:
Ability to rank positives above negatives (AUC).

Calibration:
Accuracy of predicted probability values.

A model can have:
High AUC but poor calibration.

These properties are independent.

---

# Core Insight

Evaluation should reflect:

- Class imbalance
- Cost asymmetry
- Operational objectives
- Probability reliability

Metric selection is a business decision, not just a mathematical one.
