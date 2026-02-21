# 01 – Geometry Foundations of Unsupervised Learning

Unsupervised learning is fundamentally geometric.

Unlike supervised learning, where labels guide optimization,
unsupervised methods rely entirely on:

- Distance
- Similarity
- Representation
- Feature scaling
- Dimensional structure

Understanding geometry is essential before applying clustering algorithms.

---

# 1. What Is Unsupervised Learning?

Supervised learning:
Given input features X, predict target Y.

Unsupervised learning:
Given only X, discover structure within X.

Typical goals:

- Identify clusters
- Detect latent structure
- Reduce dimensionality
- Identify density patterns

There is no ground truth label to validate structure.
Therefore, geometry determines results.

---

# 2. Distance Defines Structure

Clustering depends on similarity.
Similarity is defined by a distance metric.

Common metrics:

- Euclidean distance
- Manhattan distance
- Cosine similarity
- Mahalanobis distance

Changing the distance metric changes clustering results.

Clusters are not absolute.
They are defined relative to the chosen metric.

---

# 3. Scale Sensitivity

Euclidean distance is scale-sensitive.

If one feature has a much larger numerical range than others,
it dominates distance computation.

Example:

Income: 0 – 1,000,000  
Age: 18 – 70  

Without scaling:

Income differences dominate squared distance terms.

Distance reflects units, not structure.

---

# 4. Standardization and Geometry

Standardization transforms each feature to:

Mean = 0  
Standard deviation = 1  

After scaling:

- All features contribute equally in variance terms.
- Distance reflects relative variation, not magnitude.
- Geometry becomes balanced.

However:

Equal variance does not imply equal importance.

Standardization fixes numerical distortion,
not semantic relevance.

---

# 5. Representation Determines Clusters

Clustering results depend heavily on:

- Feature engineering
- Scaling choices
- Distance metric
- Dimensionality

Unsupervised learning has no Y to correct errors.
Incorrect representation leads to arbitrary clusters.

Geometry encodes assumptions.

---

# 6. Curse of Dimensionality

As dimensionality increases:

- Pairwise distances increase.
- Differences between nearest and farthest distances shrink.
- Distance contrast disappears.

This phenomenon is called distance concentration.

In high dimensions:

Nearest distance ≈ Farthest distance.

Clustering becomes unreliable because distance no longer distinguishes structure effectively.

---

# 7. Noise Accumulation

Adding irrelevant features:

- Adds random variation.
- Increases overall distances.
- Reduces signal-to-noise ratio.
- Degrades clustering quality.

Even if true structure exists in low dimensions,
high-dimensional noise can overwhelm it.

Feature selection becomes critical.

---

# 8. Cosine Similarity vs Euclidean Distance

Euclidean distance measures magnitude differences.

Cosine similarity measures angle (direction).

In high-dimensional data (e.g., text):

- Magnitude often reflects length, not meaning.
- Direction reflects pattern similarity.

Cosine similarity is less affected by magnitude inflation.

This is why cosine is often preferred in sparse, high-dimensional settings.

---

# 9. PCA and Clustering

Principal Component Analysis (PCA):

- Finds directions of maximum variance.
- Projects data into lower-dimensional space.

PCA helps clustering when:

- Noise dominates low-variance directions.
- True structure aligns with high-variance directions.

However:

Variance maximization ≠ cluster separation.

If cluster separation lies in low-variance directions,
PCA may discard important structure.

PCA is not guaranteed to improve clustering.

---

# 10. Variance vs Separation

Variance measures spread.

Clustering depends on separation.

High variance does not imply meaningful grouping.
Low variance does not imply irrelevance.

This distinction is crucial.

---

# 11. Neighborhood Preservation

Since global distance may distort in high dimensions,
methods that preserve local neighborhoods
can better reveal cluster structure.

Examples (conceptually):

- t-SNE
- UMAP

These prioritize local relationships rather than global variance.

They are often useful for visualization.

---

# 12. Core Principles

Before applying clustering:

1. Scale features appropriately.
2. Remove irrelevant dimensions if possible.
3. Consider dimensionality reduction carefully.
4. Understand chosen distance metric.
5. Recognize that geometry encodes assumptions.

Unsupervised learning is assumption-heavy.
Results depend on representation choices.

---

# Key Insight

Unsupervised learning is not purely statistical.

It is geometric.

Clusters are not discovered absolutely.
They are discovered relative to:

- Metric
- Scaling
- Representation
- Dimensional structure

Understanding geometry precedes algorithm selection.
