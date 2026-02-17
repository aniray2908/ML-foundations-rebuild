# 03 – Regularization (Ridge & Lasso)

Regularization controls model complexity to reduce variance.

---

# Ridge Regression (L2)

Minimize:

RSS + λ ∑ β²

Solution:

β̂_ridge = (XᵀX + λI)^(-1) XᵀY

## Effect

- Increases eigenvalues of XᵀX
- Stabilizes inversion
- Shrinks coefficients smoothly
- Reduces variance
- Slightly increases bias

As λ → ∞:
- β̂ → 0
- Bias ↑
- Variance ↓

Best for:
- Multicollinearity
- Dense signal (many small effects)

---

# Lasso Regression (L1)

Minimize:

RSS + λ ∑ |β|

## Effect

- Shrinks coefficients
- Can set some coefficients exactly to zero
- Performs feature selection

Best for:
- Sparse signal
- High-dimensional settings

---

# Ridge vs Lasso

Sparse true signal → Lasso  
Dense signal → Ridge  
Correlated predictors → Ridge often more stable  

Elastic Net combines both penalties.
