# 03 – Hierarchical Clustering

Hierarchical clustering builds a nested structure of clusters rather than directly partitioning data into K groups.

Instead of asking:

> "What are the K clusters?"

It asks:

> "How does structure emerge as we progressively merge (or split) data?"

The result is a hierarchy represented by a dendrogram.

---

# 1. Two Types of Hierarchical Clustering

## Agglomerative (Bottom-Up)

- Start with each point as its own cluster.
- Iteratively merge the two closest clusters.
- Continue until all points are merged into one cluster.

This is the most commonly used form.

## Divisive (Top-Down)

- Start with all points in one cluster.
- Recursively split clusters.

Less common due to computational complexity.

This module focuses on agglomerative clustering.

---

# 2. Core Idea: Linkage Criterion

When merging clusters, we must define:

> What does “closest clusters” mean?

Distance between clusters is determined by a linkage rule.

Different linkage rules produce fundamentally different geometries.

---

# 3. Linkage Methods

## 3.1 Single Linkage

Distance between clusters =
Minimum distance between any pair of points (one from each cluster).

Effect:
- Produces chain-like clusters.
- Can capture non-convex shapes.
- Sensitive to noise bridges.

This can lead to the “chaining effect,” where clusters grow through thin connections.

---

## 3.2 Complete Linkage

Distance between clusters =
Maximum distance between any pair of points.

Effect:
- Prefers compact, tight clusters.
- Avoids chaining.
- Produces roughly spherical groupings.

More conservative than single linkage.

---

## 3.3 Average Linkage

Distance between clusters =
Average pairwise distance between points in the two clusters.

Effect:
- Balanced behavior.
- Less sensitive to extreme pairs.
- Intermediate between single and complete.

---

## 3.4 Ward’s Linkage

Clusters are merged if the increase in within-cluster variance is minimal.

This is equivalent to minimizing:

Within-Cluster Sum of Squares (WCSS).

Effect:
- Produces compact clusters.
- Similar behavior to K-Means.
- Strongly variance-oriented.

Ward linkage is conceptually closest to K-Means.

---

# 4. Dendrogram

The output of hierarchical clustering is a tree.

The dendrogram shows:

- Which clusters merged
- At what distance they merged
- The hierarchical nesting structure

Choosing number of clusters becomes:

Cutting the dendrogram at a chosen height.

Large vertical jumps suggest natural separation.

---

# 5. Comparison to K-Means

| Aspect | K-Means | Hierarchical |
|--------|----------|--------------|
| Structure | Flat | Nested |
| Choose K upfront? | Yes | No |
| Geometry | Spherical | Depends on linkage |
| Optimization | Direct WCSS | Greedy merging |
| Initialization sensitive | Yes | No |

Hierarchical clustering provides structural insight before deciding K.

---

# 6. Geometric Behavior

Linkage determines geometry:

- Single → Flexible, chain-like
- Complete → Compact clusters
- Average → Balanced
- Ward → Variance-minimizing (K-Means-like)

Thus hierarchical clustering is not one algorithm,
but a family of geometric choices.

---

# 7. Strengths

- Does not require pre-specifying K.
- Reveals nested structure.
- Captures non-spherical shapes (with appropriate linkage).
- No random initialization sensitivity.

---

# 8. Limitations

- Computationally expensive for large datasets.
- Sensitive to distance metric.
- Once clusters merge, they cannot be undone.
- Linkage choice strongly affects outcome.

---

# 9. Core Insight

Hierarchical clustering does not optimize a single global objective.

It builds structure greedily.

Different linkage rules impose different geometric assumptions.

Clustering is not universal.

It is defined by:

- Metric
- Linkage
- Representation
- Dimensionality
