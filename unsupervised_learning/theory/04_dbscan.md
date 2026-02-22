# 04 – DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

DBSCAN is a density-based clustering algorithm.

Unlike centroid-based or linkage-based methods, DBSCAN defines clusters as:

Regions of high density separated by regions of low density.

It does not assume spherical clusters.
It does not require pre-specifying the number of clusters.
It explicitly identifies noise.

---

# 1. Core Idea

DBSCAN groups together points that are:

Density-connected.

Two key parameters define density:

- ε (epsilon): Neighborhood radius
- min_samples: Minimum number of points required to form a dense region

Clusters are formed by expanding from dense core points.

---

# 2. Definitions

## Core Point

A point is a core point if:

It has at least min_samples points within distance ε (including itself).

Core points lie inside dense regions.

---

## Border Point

A point that:

- Is within ε of a core point
- But does not itself have enough neighbors to be a core point

Border points belong to clusters but do not expand them.

---

## Noise Point

A point that:

- Is not a core point
- Is not within ε of any core point

Noise points are labeled as outliers.

DBSCAN explicitly detects outliers.

---

# 3. Density Connectivity

Two points are density-connected if:

- There exists a chain of core points linking them
- Each step in the chain lies within ε

Clusters grow by recursively expanding from core points.

---

# 4. Algorithm Overview

1. Pick an unvisited point.
2. If it is a core point, create a new cluster.
3. Recursively add all density-connected points.
4. Mark visited points.
5. Continue until all points are processed.

No centroid is computed.
No global objective is minimized.

Clustering emerges from local density structure.

---

# 5. Geometric Assumption

DBSCAN assumes:

Clusters = Dense regions separated by sparse regions.

It does not assume:

- Spherical shape
- Equal size
- Equal variance
- Convexity

This allows it to capture non-linear shapes such as crescents.

---

# 6. Parameter Sensitivity

## ε Too Small

- Few core points.
- Many noise points.
- Fragmented clusters.

## ε Too Large

- Dense regions merge.
- Sparse gaps disappear.
- Too few clusters (often one large cluster).

## min_samples Too Small

- Noise may form artificial clusters.

## min_samples Too Large

- True clusters may be labeled as noise.

Parameter tuning is critical.

---

# 7. Strengths

- Captures arbitrary cluster shapes.
- Does not require choosing K.
- Explicitly detects outliers.
- Works well for spatial data.

---

# 8. Limitations

- Struggles when clusters have varying densities.
- Sensitive to ε choice.
- Distance-based (still suffers in high dimensions).
- Performance degrades in high-dimensional spaces.

Distance concentration affects DBSCAN as well.

---

# 9. Comparison with Other Methods

| Method | Assumption | Requires K | Handles Non-Spherical | Detects Noise |
|---------|------------|------------|------------------------|---------------|
| K-Means | Spherical clusters | Yes | No | No |
| Hierarchical | Linkage-defined | No (cut later) | Depends on linkage | No |
| DBSCAN | Density-separated | No | Yes | Yes |

Each method defines "cluster" differently.

---

# 10. Core Insight

DBSCAN does not optimize a global function.

It defines clusters through local density structure.

Clustering is not universal.

It depends on:

- Geometry
- Distance metric
- Density assumptions
- Parameter choice
