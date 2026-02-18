# 10 – Learning Curves

Learning curves visualize how model performance changes as the training dataset grows.

They help diagnose:

- Underfitting (High Bias)
- Overfitting (High Variance)
- Whether more data will help
- Whether model complexity is appropriate

---

# 1. What is a Learning Curve?

A learning curve plots:

- Training error vs training set size
- Test error vs training set size

As more data is added, both errors evolve.

The relationship between these curves reveals bias–variance behavior.

---

# 2. General Behavior

As training size increases:

- Training error increases slightly
- Test error decreases initially
- Both curves eventually stabilize

This happens because:

- Small datasets allow memorization
- Larger datasets reduce variance
- Stable convergence indicates model capacity is appropriate

---

# 3. High Bias (Underfitting)

Characteristics:

- Training error high
- Test error high
- Small gap between curves

Interpretation:

The model is too simple to capture structure.

Adding more data does not significantly reduce error.

Solution:

- Increase model flexibility
- Add nonlinear features
- Reduce regularization

---

# 4. High Variance (Overfitting)

Characteristics:

- Training error very low
- Test error high
- Large gap between curves

Interpretation:

The model memorizes training data but fails to generalize.

Adding more data reduces variance.

Solution:

- Add more data
- Increase regularization
- Reduce model complexity

---

# 5. Good Fit (Balanced Model)

Characteristics:

- Training error low
- Test error low
- Small gap

Interpretation:

Model capacity matches data complexity.

Bias and variance are balanced.

---

# 6. Strategic Value of Learning Curves

Learning curves answer:

- Should I collect more data?
- Should I change model complexity?
- Is my model fundamentally too simple?
- Is my model too flexible for current data size?

They guide engineering decisions rather than guesswork.

---

# 7. Key Insight

Model performance depends on:

Model capacity × Dataset size.

High-capacity models are not inherently bad.
They require sufficient data to control variance.

---

# Core Diagnostic Rules

High Bias:
Train high + Test high + Small gap.

High Variance:
Train low + Test high + Large gap.

Good Fit:
Train low + Test low + Small gap.

Learning curves convert bias–variance theory into visual diagnosis.
