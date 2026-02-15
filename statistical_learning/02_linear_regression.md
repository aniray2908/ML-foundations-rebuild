# 02 – Linear Regression (Statistical View)

## Model

Y = Xβ + ε

Where:
- X is design matrix
- β are coefficients
- ε ~ N(0, σ²)

---

## Ordinary Least Squares (OLS)

Minimize:

||Y − Xβ||²

Solution:

β̂ = (XᵀX)^(-1) XᵀY

---

## Interpretation

β_j represents:

Expected change in Y per unit change in X_j,
holding other predictors constant.

---

## Multicollinearity

Occurs when predictors are highly correlated.

Then:

- XᵀX becomes nearly singular
- Small eigenvalues appear
- Inversion becomes unstable

Coefficient variance:

Var(β̂) = σ² (XᵀX)^(-1)

Small eigenvalues → large variance.

---

## Geometric Interpretation

OLS projects Y onto the column space of X.

If columns are nearly linearly dependent,
projection becomes unstable.
