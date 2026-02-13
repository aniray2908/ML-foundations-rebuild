# Week 1 – Matrix Fundamentals Notes

## 1. What is a Matrix?

A matrix represents a linear transformation.

More specifically:
It transforms an input vector into a new vector by scaling, rotating, shearing, or projecting it in space.

In ML:
Weight matrices transform feature vectors between layers.

---

## 2. What is Matrix Multiplication?

Matrix multiplication composes linear transformations.

If:
A transforms space once
B transforms space again

Then:
AB represents applying B first, then A.

Each element in the result matrix is:
The dot product of a row of A with a column of B.

So multiplication is essentially:
Row–column dot product aggregation.

---

## 3. Why Does Order Matter?

Matrix multiplication is NOT commutative.

AB ≠ BA

Because:
Applying transformation A then B is different from applying B then A.

In neural networks:
Layer order changes the function being learned.

This is why architecture matters.

---

## 4. Geometric Interpretation

When a matrix multiplies a vector:
- It transforms the coordinate space.
- It changes the basis orientation.
- It scales along specific directions.

Example:
Scaling matrix stretches axes.
Rotation matrix rotates vectors around origin.

So matrices are not just numbers.
They are operations on space.

---

## 5. How This Connects to ML

In a neural network layer:

y = Wx + b

W is a matrix.
x is a vector.

So each layer:
Applies a linear transformation to input data.

Deep learning is essentially:
Stacked matrix multiplications + nonlinearities.

Understanding this removes mystery from ML models.


