# 02 – K-Means Clustering

K-Means is a centroid-based clustering algorithm that partitions data into K clusters by minimizing within-cluster variation.

It is one of the simplest and most widely used unsupervised learning methods.

However, its simplicity hides strong geometric assumptions.

---

# 1. Objective of K-Means

K-Means solves the following optimization problem:

Minimize the Within-Cluster Sum of Squares (WCSS):

\[
\sum_{k=1}^{K} \sum_{x_i \in C_k} ||x_i - \mu_k||^2
\]

Where:

- \( C_k \) = cluster k  
- \( \mu_k \) = centroid (mean) of cluster k  
- \( ||x_i - \mu_k||^2 \) = squared Euclidean distance  

This objective is also called:

- Inertia (in sklearn)
- Within-cluster variance
- Distortion measure

---

# 2. Interpretation of the Objective

The goal is to:

- Make points within each cluster as close as possible to their centroid.
- Minimize total squared deviation.

Important:

K-Means does not explicitly maximize separation between clusters.
It only minimizes compactness within clusters.

Cluster separation emerges indirectly.

---

# 3. Why Squared Euclidean Distance?

Squared distance is used because:

- It penalizes distant points heavily.
- It is differentiable.
- It leads to the mean being the optimal centroid.

The mean minimizes squared error.

This directly connects K-Means to least squares regression logic.

---

# 4. Why the Mean as Centroid?

Given fixed cluster assignments:

The value of \( \mu_k \) that minimizes:

\[
\sum ||x_i - \mu_k||^2
\]

is the arithmetic mean of the cluster.

Thus:

Centroid = Mean of assigned points.

This is a consequence of minimizing squared loss.

---

# 5. The Algorithm (Lloyd’s Algorithm)

K-Means proceeds iteratively:

1. Initialize K centroids (randomly or via k-means++).
2. Assign each point to nearest centroid.
3. Recompute centroids as cluster means.
4. Repeat until assignments stabilize.

This is a form of coordinate descent:

- Assignment step
- Update step

Each iteration reduces the objective function.

Convergence is guaranteed, but only to a local minimum.

---

# 6. Initialization Sensitivity

Because the objective is non-convex:

Different initial centroids can produce different solutions.

Poor initialization may result in:

- Suboptimal clustering
- Empty clusters
- Slow convergence

k-means++ improves initialization by:

- Spacing initial centroids apart
- Reducing poor local minima

---

# 7. Behavior as K Increases

As K increases:

- WCSS monotonically decreases.
- In extreme case (K = N), WCSS = 0.

Therefore:

Minimizing WCSS alone cannot determine optimal K.

Model selection methods are required.

---

# 8. Choosing K

Common approaches:

## Elbow Method

Plot WCSS vs K.

Look for a point where reduction in WCSS slows down.

This indicates diminishing returns.

Sharp elbow → strong natural clustering.
Smooth curve → weak or no clear structure.

Limitation:
Subjective and not always clear.

---

## Silhouette Score

For each point:

a = average distance to points in same cluster  
b = average distance to points in nearest other cluster  

Silhouette score:

\[
\frac{b - a}{\max(a, b)}
\]

Range:
- Close to 1 → well separated
- Close to 0 → overlapping clusters
- Negative → likely misclassified

Silhouette considers both compactness and separation.

---

# 9. Geometric Assumptions of K-Means

K-Means assumes:

- Euclidean geometry
- Spherical clusters
- Similar cluster sizes
- Similar cluster densities
- Convex cluster shapes

Why spherical?

Because equal-distance contours in Euclidean space are spheres.

Assignment regions are Voronoi cells defined by perpendicular bisectors.

Clusters are therefore convex and symmetric around centroids.

---

# 10. Limitations

K-Means struggles with:

- Elongated clusters
- Non-convex shapes (e.g., crescents)
- Varying densities
- Outliers
- High-dimensional noise

Outliers can heavily influence centroids due to squared loss.

---

# 11. Scaling Requirement

Because K-Means uses Euclidean distance:

Feature scaling is essential.

Unscaled features distort cluster assignments.

Standardization is typically applied before clustering.

---

# 12. K-Means and High Dimensions

In high dimensions:

- Distance concentration occurs.
- Noise features accumulate.
- Cluster separation may weaken.

Dimensionality reduction (e.g., PCA) may help,
but only if cluster structure aligns with high-variance directions.

---

# 13. K-Means as Vector Quantization

K-Means can also be interpreted as:

- Data compression
- Vector quantization
- Prototype learning

Each centroid represents a prototype for its cluster.

---

# Core Insight

K-Means minimizes within-cluster squared distance under Euclidean geometry.

It assumes spherical structure and equal importance of features.

Its success depends entirely on:

- Geometry
- Scaling
- Representation
- Appropriate choice of K

K-Means does not discover arbitrary structure.
It partitions space according to its objective function.
