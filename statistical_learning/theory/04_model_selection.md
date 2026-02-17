# 04 – Model Selection & Evaluation Theory

## Cross-Validation

Purpose:
Estimate out-of-sample error.

### K-Fold CV

1. Split data into K folds
2. Train on K−1
3. Test on remaining fold
4. Average error

Reduces variance of error estimate compared to single split.

---

### LOOCV

K = n

Low bias  
High variance  

Highly sensitive to individual observations.

---

## AIC

AIC = 2k − 2 log(L)

Balances:
- Goodness of fit
- Model complexity

Lower is better.

Assumes correct likelihood specification.

---

## AICc (Small Sample Correction)

AICc = AIC + [2k(k+1)] / (n − k − 1)

Used when:
n is small relative to k.

Penalizes complexity more aggressively.

---

## CV vs AIC

Cross-validation:
- Data-driven
- Assumption-light
- Preferred for prediction

AIC/AICc:
- Model-based
- Preferred for inference under correct assumptions
