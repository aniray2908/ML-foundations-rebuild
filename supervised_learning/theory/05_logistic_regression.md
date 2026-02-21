# 05 – Logistic Regression

Logistic regression is a foundational binary classification model.

It predicts probabilities using a linear decision boundary transformed by a nonlinear function.

---

# 1. Motivation

In binary classification:

Y ∈ {0,1}

We want:

P(Y=1 | X)

Linear regression is unsuitable because:
- Predictions are unbounded.
- Errors are not normally distributed.
- Mean squared error is not aligned with probability modeling.

We need a function that:
- Maps ℝ → (0,1)
- Is smooth and differentiable
- Supports probabilistic interpretation

---

# 2. The Logistic (Sigmoid) Function

The sigmoid function:

σ(z) = 1 / (1 + e^{-z})

Where:

z = Xβ

Properties:
- Maps any real number to (0,1)
- Smooth and monotonic
- Differentiable everywhere

Predicted probability:

P(Y=1 | X) = σ(Xβ)

---

# 3. Linear Model in Log-Odds Space

Instead of modeling probability directly, logistic regression models:

log( p / (1 - p) ) = Xβ

Where:
p = P(Y=1 | X)

This transformation is called the log-odds or logit.

Why log-odds?

- Probability is bounded between 0 and 1.
- Log-odds lie in (-∞, +∞).
- This allows a linear model to operate without constraint.

---

# 4. Interpretation of Coefficients

If β_j > 0:
- Increasing X_j increases the probability of class 1.

If β_j < 0:
- Increasing X_j decreases the probability of class 1.

Exponentiating coefficients:

exp(β_j) = odds ratio

Interpretation:
A 1-unit increase in X_j multiplies the odds by exp(β_j).

Example:
If β_j = 0.7,
exp(0.7) ≈ 2
Odds roughly double.

---

# 5. Decision Boundary

Classification rule:

If P(Y=1 | X) ≥ 0.5 → Class 1  
Else → Class 0  

The decision boundary occurs when:

Xβ = 0

Thus, logistic regression produces a linear boundary in feature space.

Even though probability output is nonlinear.

---

# 6. Loss Function: Cross-Entropy

Logistic regression is estimated using maximum likelihood.

Likelihood for binary outcome:

L(β) = ∏ p_i^{y_i} (1 - p_i)^{1 - y_i}

Taking log:

Log-likelihood becomes cross-entropy loss.

Why cross-entropy instead of MSE?

- It strongly penalizes confident wrong predictions.
- It aligns with Bernoulli distribution assumptions.
- It directly optimizes probability estimation.

---

# 7. Regularized Logistic Regression

Just like linear regression, penalties can be added:

L2 (Ridge):
Loss + λ ∑ β²

L1 (Lasso):
Loss + λ ∑ |β|

Purpose:
- Control variance
- Prevent overfitting
- Enable feature selection (L1)

---

# 8. Strengths

- Interpretable
- Probabilistic
- Stable
- Convex optimization (global optimum)
- Works well for linearly separable data

---

# 9. Limitations

- Linear decision boundary
- Cannot model complex nonlinear patterns without feature engineering
- Performance may degrade with highly complex interactions

---

# Core Insight

Logistic regression is a linear classifier in feature space that outputs calibrated probabilities.

It is often the first baseline model in classification problems.
