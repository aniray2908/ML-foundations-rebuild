# Linear Algebra Foundations – Notes

This document captures conceptual understanding from the 6-week ML foundations rebuild.

---

# Week 1 – Matrix Fundamentals

## 1. What is a Matrix?

A matrix represents a linear transformation.

It transforms an input vector into a new vector by:
- Scaling
- Rotating
- Shearing
- Projecting

In ML:
Weight matrices transform feature vectors between layers.

---

## 2. What is Matrix Multiplication?

Matrix multiplication composes transformations.

If:
A transforms space once
B transforms space again

Then:
AB represents applying B first, then A.

Each element of AB is:
Row of A ⋅ Column of B

So multiplication is dot-product aggregation.

---

## 3. Why Order Matters

Matrix multiplication is NOT commutative.

AB ≠ BA

Because transformations are sequential.

In neural networks:
Layer order changes the function being learned.

---

## 4. Geometric Interpretation

When a matrix multiplies a vector:
- It transforms coordinate space.
- It changes direction and magnitude.
- It acts as an operator, not just numbers.

---

## 5. ML Connection

In a neural network:

y = Wx + b

Each layer is a matrix multiplication followed by non-linearity.

Deep learning = stacked matrix transformations.

---

# Week 1 – Eigenvalues & Eigenvectors

## 1. Definition

A vector v is an eigenvector of matrix A if:

Av = λv

Where:
- v = eigenvector
- λ = eigenvalue

---

## 2. Intuition

Most vectors change direction under transformation.

Eigenvectors are special:
They do NOT change direction.
They only scale.

---

## 3. Meaning of Eigenvalues

Eigenvalue tells us:
How much the eigenvector is stretched or compressed.

Large λ → strong stretching  
Small λ → weak stretching  
Negative λ → direction flips  
Complex λ → rotation behavior  

---

## 4. Geometric Significance

Eigenvectors represent intrinsic directions of a transformation.

They reveal:
- Dominant axes
- Structural behavior
- Stability properties

---

## 5. Why Eigenvalues Matter in ML

1. PCA:
   Principal components are eigenvectors of covariance matrix.
   Largest eigenvalues = directions of maximum variance.

2. Optimization:
   Eigenvalues relate to curvature of loss functions.

3. System stability:
   Spectral radius affects convergence.

---

# Week 1 – Singular Value Decomposition (SVD)

## Definition

A = U Σ Vᵀ

Where:
U and V are orthogonal matrices.
Σ contains singular values.

---

## Interpretation

Every matrix transformation =
rotation → scaling → rotation.

Singular values measure scaling strength.

---

## Why SVD Matters in ML

- PCA implementation
- Dimensionality reduction
- Latent factor models
- Numerical stability

## References

- [Mathematics for Machine Learning – Imperial](https://www.coursera.org/specializations/mathematics-machine-learning)
- [3Blue1Brown – Essence of Linear Algebra](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi)
- [NumPy Linear Algebra Docs](https://numpy.org/doc/stable/reference/routines.linalg.html)
