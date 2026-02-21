# 11 – Support Vector Machines (SVM)

Support Vector Machines are margin-based classifiers that seek the most robust separating boundary between classes.

They are defined by:

- Maximum margin principle
- Support vectors
- Soft margin regularization (C parameter)
- Kernel trick for nonlinear separation

---

# 1. Maximum Margin Principle

If data is linearly separable, there are infinitely many separating lines.

SVM selects the one that maximizes the margin.

Margin:
The distance between the decision boundary and the closest data points.

Why maximize margin?

- Larger margin → more robust
- Less sensitivity to small data shifts
- Better generalization

---

# 2. Support Vectors

Only the points closest to the boundary determine the margin.

These points are called:

Support Vectors.

Removing non-support-vector points does not change the boundary.

SVM solutions are sparse in this sense.

---

# 3. Hard Margin vs Soft Margin

Hard Margin SVM:
- No misclassification allowed
- Only works if data is perfectly separable

Soft Margin SVM:
- Allows some misclassification
- Introduces tradeoff between margin size and classification error

This tradeoff is controlled by the parameter C.

---

# 4. The C Parameter

C controls how strongly we penalize misclassification.

Large C:
- Strict about classification errors
- Smaller margin
- Lower bias
- Higher variance
- Risk of overfitting

Small C:
- Allows some misclassification
- Larger margin
- Higher bias
- Lower variance
- More generalization

C is analogous to inverse regularization strength.

---

# 5. The Kernel Trick

If data is not linearly separable in original space:

SVM maps data to a higher-dimensional space
where it becomes linearly separable.

Instead of explicitly transforming features,
SVM uses a kernel function to compute inner products in that higher-dimensional space.

This allows nonlinear decision boundaries
without explicitly constructing new features.

---

# 6. Common Kernels

Linear Kernel:
- Standard linear SVM

Polynomial Kernel:
- Curved boundaries of polynomial form

RBF (Gaussian) Kernel:
- Most commonly used
- Creates smooth, flexible boundaries

---

# 7. The Gamma Parameter (RBF Kernel)

Gamma controls how far the influence of a single training point reaches.

Large gamma:
- Influence is local
- Boundary becomes very wiggly
- Low bias
- High variance
- Overfitting risk

Small gamma:
- Influence is broad
- Boundary becomes smoother
- Higher bias
- Lower variance

Gamma controls boundary complexity.

---

# 8. C vs Gamma

C controls:
How much we punish classification errors.

Gamma controls:
How locally complex the boundary can be.

They are independent hyperparameters,
but interact in shaping model flexibility.

High C + High Gamma → very flexible, high overfitting risk  
Low C + Low Gamma → smooth, potentially underfit  

---

# 9. Bias–Variance in SVM

High Bias:
- Small C
- Small gamma

High Variance:
- Large C
- Large gamma

Balanced model:
- Moderately tuned C and gamma via cross-validation

---

# Core Insight

SVM is a margin-maximizing classifier
that balances model complexity and classification error.

It generalizes well because:

- It focuses on boundary-defining points
- It maximizes robustness via margin
- It controls complexity via C and gamma
- It enables nonlinear separation through kernels
