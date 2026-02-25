# 05 – Cluster Validation (Internal Metrics)

Clustering evaluation is fundamentally different from supervised evaluation.

In supervised learning:
There is a target variable Y.
Model quality can be measured against ground truth.

In unsupervised learning:
There is no Y.
Cluster quality must be evaluated indirectly.

Internal validation measures clustering quality using only:
- Data
- Cluster assignments

These metrics evaluate structure under assumptions — not objective truth.

---

# 1. Why Cluster Validation Is Difficult

Clustering does not discover absolute truth.

It discovers structure under a chosen similarity definition.

For the same dataset, multiple clusterings may be valid:
- Variance-based (K-Means)
- Linkage-based (Hierarchical)
- Density-based (DBSCAN)

Evaluation must therefore measure:
- Compactness
- Separation
- Stability

No internal metric guarantees correctness.

---

# 2. Silhouette Score

For each point i:

- a(i): average distance to its own cluster
- b(i): minimum average distance to another cluster

Silhouette score:

\[
s(i) = \frac{b(i) - a(i)}{\max(a(i), b(i))}
\]

Range:
- Close to 1 → well clustered
- Close to 0 → overlapping clusters
- Negative → misclassified

Interpretation:
Measures relative separation vs compactness at the point level.

Properties:
- Scale-invariant
- Bounded between -1 and 1
- Sensitive to cluster overlap

Bias:
Prefers compact, well-separated clusters.

---

# 3. Davies–Bouldin Index (DBI)

For clusters i and j:

\[
R_{ij} = \frac{S_i + S_j}{M_{ij}}
\]

Where:
- \( S_i \): cluster spread (within-cluster distance)
- \( M_{ij} \): distance between cluster centroids

For each cluster i:
Find the worst-case (maximum) \( R_{ij} \).

DBI = average of these worst-case similarities.

Lower is better.

Interpretation:
Measures how similar each cluster is to its most similar neighbor.

Properties:
- Cluster-level metric
- Penalizes close centroids
- Penalizes large internal spread

Bias:
Strong preference for compact spherical clusters.

---

# 4. Calinski–Harabasz Index (CH)

\[
CH = \frac{B_k / (k - 1)}{W_k / (n - k)}
\]

Where:
- \( B_k \): between-cluster variance
- \( W_k \): within-cluster variance
- \( k \): number of clusters
- \( n \): number of samples

Higher is better.

Interpretation:
Signal-to-noise ratio:
- Signal = between-cluster dispersion
- Noise = within-cluster dispersion

Properties:
- Aligned with K-Means objective
- Tends to peak near natural cluster count

Bias:
Rewards compact, separated clusters.
Penalizes elongated or irregular shapes.

---

# 5. Metric Behavior Patterns

| Scenario | Silhouette | DBI | CH |
|-----------|------------|------|------|
| Compact, well-separated clusters | High | Low | High |
| Overlapping clusters | Low | High | Low |
| Elongated clusters | Moderate/Low | High | Lower |
| Non-spherical (e.g., moons) | Moderate | Moderate/High | Moderate |

Internal metrics encode geometric assumptions.

They are not universally fair.

---

# 6. Structural Insight

All three metrics implicitly reward:

- Compactness
- Separation
- Convex cluster shapes

They align naturally with centroid-based clustering.

They may penalize:

- Density-based clustering results
- Elongated clusters
- Arbitrary-shaped clusters

Therefore:

Validation must be interpreted in context.

---

# 7. No Universal Metric

Clustering quality depends on:

- Representation
- Distance metric
- Algorithm assumptions
- Domain interpretation

Internal metrics evaluate structure under geometric bias.

They do not determine truth.

---

# Core Takeaway

Cluster validation measures structure consistency — not correctness.

Internal metrics encode assumptions about what “good” clusters look like.

Understanding those assumptions is essential for responsible clustering.
