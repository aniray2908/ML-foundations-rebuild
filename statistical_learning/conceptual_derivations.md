# Conceptual Derivations – Statistical Learning

This document captures reasoning, refinement, and final understanding.

---

# Zero Training Error

Why can zero training error still lead to poor performance?

Initial intuition:
Perfect training fit means good model.

Refinement:
Zero training error implies low bias but possibly high variance.

Final understanding:
The model may memorize noise, leading to poor generalization.

---

# Averaging High-Variance Models

Question:
Why does averaging reduce variance?

Reasoning:
Random fluctuations cancel out when averaged.

Final understanding:
Variance decreases approximately by factor 1/n (if models not perfectly correlated).

Bias remains roughly unchanged.

---

# Multicollinearity

Question:
Why does it increase coefficient variance?

Reasoning:
β̂ variance depends on (XᵀX)^(-1).
Small eigenvalues lead to large inversion values.

Final understanding:
Near-singularity causes instability in coefficient estimates.

---

# Ridge Stabilization

Question:
Why does adding λI help?

Reasoning:
Eigenvalues of XᵀX increase by λ.
Small eigenvalues move away from zero.

Final understanding:
Stabilizes inversion and reduces variance.

---

# Large λ Behavior

As λ becomes large:

(XᵀX + λI) ≈ λI

β̂ ≈ (1/λ)XᵀY → 0

Final:
Bias ↑, Variance ↓

---

# AIC vs CV

CV:
Direct estimate of predictive performance.

AIC:
Analytical estimate under likelihood assumptions.

Final:
For prediction → CV preferred.
For inference → AIC/AICc appropriate.
