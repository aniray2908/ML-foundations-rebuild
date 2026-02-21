# 07 – Decision Trees & Ensemble Methods

This module covers:

- Decision Trees
- Tree instability
- Bagging
- Random Forest
- Bias–variance behavior in ensembles

---

# 1. Decision Trees

Decision trees are non-parametric models that split the feature space into rectangular regions.

Each internal node asks a question:

Is feature_j ≤ threshold?

Each split partitions the data into two regions.

Leaves contain predictions.

For classification:
Leaf predicts majority class.

For regression:
Leaf predicts average value.

---

# 2. Geometric Interpretation

Each split creates:

- A vertical or horizontal boundary.
- Axis-aligned rectangular regions.

Unlike logistic regression, trees do not produce a single global boundary.

They create piecewise constant regions.

With enough splits, trees approximate nonlinear boundaries.

---

# 3. Splitting Criteria

For classification, common criteria:

## Gini Impurity

Measures how often a randomly chosen element would be incorrectly classified.

Gini = 1 − ∑ p_k²

Lower Gini → purer node.

## Entropy

Measures disorder in a node.

Entropy = − ∑ p_k log(p_k)

Lower entropy → purer node.

Both aim to maximize information gain.

---

# 4. Tree Depth and Overfitting

Shallow tree:
- High bias
- Low variance
- Underfits

Deep tree:
- Low bias
- High variance
- Overfits

Trees are high-variance models.

Small data changes → different splits → different tree.

This instability makes single trees unreliable.

---

# 5. Bagging (Bootstrap Aggregation)

Idea:

1. Sample data with replacement.
2. Train many deep trees.
3. Average predictions.

Why it works:

- Deep trees have low bias but high variance.
- Averaging reduces variance.
- Bias remains roughly unchanged.

Bagging reduces overfitting by stabilizing predictions.

---

# 6. Random Forest

Random Forest extends bagging.

In addition to bootstrap sampling:

At each split:
- Only a random subset of features is considered.

Why?

To reduce correlation between trees.

Less correlation → better variance reduction.

---

# 7. Bias–Variance Comparison

Logistic Regression:
- Linear boundary
- Low variance
- Higher bias if boundary is nonlinear

Single Decision Tree:
- Very flexible
- Low bias
- High variance

Random Forest:
- Flexible
- Low bias
- Lower variance than single tree

---

# 8. Strengths and Limitations

Decision Trees:
+ Interpretable
+ Capture nonlinear interactions
− Unstable
− High variance

Random Forest:
+ Strong generalization
+ Handles nonlinear patterns
+ Robust
− Less interpretable
− Larger computational cost

---

# Core Insight

Trees create nonlinear boundaries via recursive partitioning.

Random Forest reduces tree variance by averaging decorrelated trees.

Ensemble learning is fundamentally about variance reduction.
