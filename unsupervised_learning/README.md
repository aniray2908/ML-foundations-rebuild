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

This module begins with geometric foundations before introducing algorithms.

---

## 📚 Structure

### Theory

All conceptual documentation is located in:

- unsupervised_learning/theory/

Current topics:

- 01_geometry_foundations.md

Upcoming topics:

- K-Means: objective function and optimization
- Choosing K (elbow, inertia behavior)
- Hierarchical clustering (linkage and dendrograms)
- Principal Component Analysis (statistical interpretation)
- Dimensionality reduction and clustering interaction

---

### Demonstrations

Implementation notebooks are located in:

- unsupervised_learning/demos/

These will include:

- Scaling and distance sensitivity experiments
- High-dimensional noise simulations
- K-Means behavior visualization
- PCA + clustering interaction experiments

---

## Key Learning Outcome

After completing this module:

- Distance metrics are understood geometrically.
- Feature scaling implications are internalized.
- High-dimensional behavior is understood conceptually.
- PCA tradeoffs for clustering are recognized.
- Clustering assumptions are explicitly acknowledged.

Unsupervised learning is treated as a geometric problem,
not just an algorithmic one.
