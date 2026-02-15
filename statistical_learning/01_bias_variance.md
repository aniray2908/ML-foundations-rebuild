# 01 – Bias–Variance Tradeoff

## Problem Setup

We assume:

Y = f(X) + ε

Where:
- f(X) is the true underlying function
- ε is irreducible noise (mean 0, variance σ²)

Our goal is not to minimize training error,
but to minimize expected prediction error on new data.

---

## Expected Prediction Error

For a new point x₀:

E[(Y − f̂(x₀))²]

Decomposes into:

Bias² + Variance + Irreducible Error

---

## Bias

Bias measures:

How far the average model prediction is from the true function.

High bias:
- Model too simple
- Underfitting
- Cannot capture structure

---

## Variance

Variance measures:

How much predictions change if we retrain on different datasets.

High variance:
- Model too flexible
- Overfitting
- Sensitive to noise

---

## Tradeoff

As model flexibility increases:

Bias ↓  
Variance ↑  
Training error ↓  
Test error ↓ then ↑  

Optimal complexity minimizes total test error.

---

## Effect of Dataset Size

As dataset size increases:

Variance ↓  
Bias remains roughly unchanged  

More data stabilizes parameter estimates.
