# 09 – Resampling Methods: Cross-Validation & Bootstrap

Resampling methods help estimate:

- Model performance
- Prediction error
- Variability of estimates

They allow us to evaluate models when new data is limited.

---

# 1. Why Resampling?

In practice, we do not know the true test error.

We only observe:

Training error

But training error underestimates true generalization error.

Resampling provides an empirical way to estimate out-of-sample performance.

---

# 2. Cross-Validation (Recap)

K-fold cross-validation:

1. Split data into K folds.
2. Train on K-1 folds.
3. Test on remaining fold.
4. Repeat K times.
5. Average the error.

Purpose:
Estimate test error.

Common choices:
- 5-fold
- 10-fold
- Leave-One-Out CV (LOOCV)

Bias–Variance Tradeoff:
- LOOCV → low bias, high variance
- 5/10-fold → balanced

---

# 3. Bootstrap

Bootstrap is another resampling technique.

Instead of splitting data into folds,
we sample **with replacement**.

Procedure:

1. Randomly sample n observations from dataset of size n (with replacement).
2. Some observations will repeat.
3. Some observations will not be selected.
4. Train model on this bootstrap sample.
5. Repeat many times.

---

# 4. Key Property of Bootstrap

On average:

About 63% of original observations appear in a bootstrap sample.

Reason:

Probability an observation is NOT selected in one draw = (1 - 1/n)

After n draws:

(1 - 1/n)^n ≈ e^{-1} ≈ 0.37

So about:

- 63% included
- 37% left out

Those left out are called:

Out-of-Bag (OOB) samples.

---

# 5. What Bootstrap Estimates

Bootstrap can estimate:

- Variance of an estimator
- Confidence intervals
- Prediction uncertainty

Example:
Estimate variability of model coefficient.

Procedure:
- Fit model on many bootstrap samples.
- Observe distribution of coefficient values.
- Estimate variance from distribution.

---

# 6. Bootstrap vs Cross-Validation

Cross-Validation:
- Estimates test error directly.
- Used for model selection.

Bootstrap:
- Estimates variability of estimates.
- Useful for confidence intervals.
- Forms basis of bagging.

They serve different purposes.

---

# 7. Connection to Bagging

Bagging (Bootstrap Aggregation):

1. Create many bootstrap samples.
2. Train a high-variance model (e.g., deep tree) on each.
3. Average predictions.

Bootstrap introduces randomness.
Averaging reduces variance.

Thus:

Bootstrap → Bagging → Random Forest

---

# 8. Strengths and Limitations

Strengths:
- Simple
- Flexible
- Works for many estimators

Limitations:
- Can be computationally expensive
- Assumes data is representative
- Less reliable for very small datasets

---

# Core Insight

Cross-validation estimates performance.

Bootstrap estimates variability.

Bagging leverages bootstrap to reduce variance.

Resampling methods are central to statistical learning.
