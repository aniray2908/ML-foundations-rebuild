# Unsupervised Learning

This module focuses on discovering structure in data without labeled targets.

Unsupervised learning answers:

> What patterns, structure, or geometry exist in X alone?

Unlike supervised learning, there is no target variable to guide optimization.
Results depend entirely on:

- Representation
- Scaling
- Distance metric
- Dimensional structure
- Density assumptions

This module approaches unsupervised learning from a geometry-first perspective before introducing clustering algorithms.

---

## 📚 Structure

### Theory

All conceptual documentation is located in:

- unsupervised_learning/theory/

Completed topics:

- 01_geometry_foundations.md  
- 02_kmeans_clustering.md  
- 03_hierarchical_clustering.md  
- 04_dbscan.md  

Theory coverage includes:

### Geometric Foundations
- Distance metrics and similarity
- Feature scaling and distortion
- Curse of dimensionality
- Distance concentration
- Noise accumulation
- PCA tradeoffs for clustering
- Variance vs separation distinction

### Centroid-Based Clustering
- K-Means objective (WCSS / inertia)
- Lloyd’s algorithm
- Initialization sensitivity (k-means++)
- Elbow method
- Silhouette score
- Spherical cluster assumption

### Linkage-Based Clustering
- Agglomerative clustering
- Single, Complete, Average, Ward linkage
- Dendrogram interpretation
- Chaining effect
- Nested cluster structure

### Density-Based Clustering
- Core, border, and noise points
- Density connectivity
- Epsilon and min_samples sensitivity
- Arbitrary shape detection
- Failure under varying densities

---

### Demonstrations

Implementation notebooks are located in:

- unsupervised_learning/demos/

Completed demonstrations include:

- Geometry intuition experiments
- Distance concentration visualization
- K-Means (elbow + silhouette + scaling effects)
- Hierarchical clustering (dendrogram + linkage comparison)
- DBSCAN (non-spherical success + noise detection + density failure)

Each notebook reinforces the geometric assumptions behind the algorithm.

---

## Core Learning Outcome

After completing this module:

- Clustering is understood as assumption-driven, not universal.
- Distance metrics are internalized geometrically.
- Feature scaling effects are fully understood.
- High-dimensional behavior and noise accumulation are recognized.
- Centroid, linkage, and density-based paradigms are contrasted clearly.
- Parameter sensitivity is reasoned structurally, not heuristically.

Unsupervised learning is treated as a geometric and structural discipline,
not just an algorithmic exercise.
