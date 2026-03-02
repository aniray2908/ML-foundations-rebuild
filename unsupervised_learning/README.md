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
- Variance structure

This module approaches unsupervised learning from a geometry-first perspective before introducing clustering algorithms and validation theory.

---

## 📚 Structure

### Theory

All conceptual documentation is located in:

- unsupervised_learning/theory/

Completed theory modules:

- 01_geometry_foundations.md  
- 02_kmeans_clustering.md  
- 03_hierarchical_clustering.md  
- 04_dbscan.md  
- 05_cluster_validation.md  
- 06_pca_for_clustering.md  

---

## Theory Coverage

### 1️⃣ Geometric Foundations
- Distance metrics and similarity
- Feature scaling and distortion
- Curse of dimensionality
- Distance concentration
- Noise accumulation
- Variance vs separation distinction

---

### 2️⃣ Clustering Paradigms

#### Centroid-Based Clustering
- K-Means objective (WCSS / inertia)
- Lloyd’s algorithm
- Initialization sensitivity (k-means++)
- Spherical cluster assumption
- Elbow method
- Silhouette intuition

#### Linkage-Based Clustering
- Agglomerative clustering
- Single, Complete, Average, Ward linkage
- Dendrogram interpretation
- Chaining effect
- Nested cluster structure

#### Density-Based Clustering
- Core, border, and noise points
- Density connectivity
- Epsilon and min_samples sensitivity
- Arbitrary shape detection
- Failure under varying densities

---

### 3️⃣ Cluster Validation (Internal Metrics)

- Silhouette score (point-level compactness vs separation)
- Davies–Bouldin Index (cluster similarity ratio)
- Calinski–Harabasz Index (between vs within variance ratio)
- Metric bias toward compact clusters
- Elongated and non-spherical cluster behavior
- Assumption-driven evaluation

---

### 4️⃣ PCA and Clustering Interaction

- Total variance decomposition
- Within vs between cluster variance
- When PCA helps clustering (noise removal)
- When PCA harms clustering (low-variance separation)
- Distance concentration reduction
- Variance maximization vs separability

---

## 📓 Demonstrations

Implementation notebooks are located in:

- unsupervised_learning/demos/

Completed demonstrations include:

- Geometry intuition experiments
- Distance concentration visualization
- K-Means behavior (elbow + silhouette + scaling effects)
- Hierarchical clustering (dendrogram + linkage comparison)
- DBSCAN (non-spherical success + noise detection + density sensitivity)
- Cluster validation comparison (Silhouette vs DBI vs CH)
- PCA–clustering interaction experiments (help vs harm cases)

Each notebook reinforces the structural assumptions behind the algorithm.

---

## Structural Progression

This module intentionally builds in layers:

1. Geometry before algorithms  
2. Clustering definitions before evaluation  
3. Evaluation before dimensionality reduction  
4. PCA analyzed through variance–separation interaction  

Unsupervised learning is treated as:

A geometric problem  
An assumption-driven modeling problem  
A variance decomposition problem  

—not merely an algorithm selection task.

---

## Core Learning Outcome

After completing this module:

- Clustering is understood as assumption-driven, not universal.
- Distance metrics are internalized geometrically.
- Feature scaling effects are fully understood.
- High-dimensional behavior and noise accumulation are recognized.
- Centroid, linkage, and density-based paradigms are contrasted clearly.
- Internal validation metrics are understood structurally, not mechanically.
- PCA is understood as a variance filter, not a cluster optimizer.
- Dimensionality reduction tradeoffs are reasoned explicitly.

Unsupervised learning is treated as a structural discipline,
not just an implementation exercise.
