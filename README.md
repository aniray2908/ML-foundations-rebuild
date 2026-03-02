# ML Foundations Rebuild

A structured 6-week rebuild of core machine learning foundations, covering linear algebra, supervised learning, unsupervised learning, and disciplined model reasoning.

This repository is not about certificate accumulation.

It is a deliberate rebuild of ML fundamentals through:
- Clear theory documentation
- Mathematical reasoning
- Structured experimentation
- Clean implementation

---

## Why This Repository Exists

The goal of this sprint is to:

- Strengthen linear algebra confidence
- Deepen statistical learning understanding
- Build disciplined model selection habits
- Transition from "fitting models" to "understanding generalization"
- Understand clustering assumptions structurally
- Develop evaluation maturity across paradigms
- Prepare for advanced ML, interpretability, and production systems

---

# Repository Structure

ML-foundations-rebuild/\
│\
├── linear_algebra/\
├── supervised_learning/\
├── unsupervised_learning/\
├── interpretability/\
├── mlops_pipeline/\
│\
├── requirements.txt\
└── README.md

---

## Week 1 – Linear Algebra Foundations

Topics covered:

- Matrix multiplication & transformations
- Eigenvalues and eigenvectors
- Singular Value Decomposition (SVD)
- Principal Component Analysis (PCA)

Focus:  
Understanding how matrix operations drive machine learning models.

---

## Week 2 – Supervised Learning

### Regression
- Bias–Variance Tradeoff
- OLS and Multicollinearity
- Ridge & Lasso Regularization
- Cross-Validation
- AIC & AICc

### Classification
- Logistic Regression (log-odds modeling)
- Cross-Entropy Loss
- Linear Decision Boundaries

### Nonlinear Models
- Decision Trees (Gini & Entropy intuition)
- Tree Instability & Overfitting

### Ensemble Learning
- Bagging
- Random Forest
- Variance reduction through decorrelation

### Margin-Based Classification
- Support Vector Machines (SVM)
- Maximum margin principle
- Hard vs Soft margin
- C parameter (regularization tradeoff)
- Kernel trick
- RBF kernel and gamma
- Bias–variance behavior in SVM

### Model Evaluation
- Confusion Matrix
- Precision, Recall, F1
- ROC vs Precision–Recall analysis
- Threshold tradeoffs
- Calibration and probability reliability

### Resampling & Diagnostics
- Cross-validation recap
- Bootstrap sampling
- Out-of-bag intuition
- Variance estimation
- Learning curve analysis
- Diagnosing bias vs variance
- Data vs model capacity tradeoff

Implementation notebooks include:

- Bias–Variance visualization
- Ridge vs Lasso coefficient comparison
- Cross-validation tuning
- OLS vs Ridge vs Lasso vs Random Forest comparison
- Logistic Regression demonstration
- Tree & ensemble visualizations
- ROC, PR, and calibration analysis
- Bootstrap variance estimation
- Learning curve demo
- SVM boundary visualization

**Outcome:**  
Structured understanding of model construction, regularization, evaluation, margin maximization, and generalization behavior.

---

## Week 3 – Unsupervised Learning

### Geometric Foundations
- Distance metrics and similarity
- Feature scaling and distortion
- Curse of dimensionality
- Distance concentration
- Noise accumulation in high dimensions
- Variance vs separation distinction

### Clustering Paradigms

**Centroid-Based (K-Means)**
- WCSS / inertia objective
- Lloyd’s algorithm
- Initialization sensitivity (k-means++)
- Spherical cluster assumption
- Elbow method
- Silhouette intuition

**Linkage-Based (Hierarchical)**
- Single, Complete, Average, Ward linkage
- Dendrogram interpretation
- Chaining effect
- Nested cluster structure

**Density-Based (DBSCAN)**
- Core, border, and noise points
- Density connectivity
- Epsilon and min_samples sensitivity
- Arbitrary shape detection
- Failure under varying densities

### Internal Cluster Validation
- Silhouette score (point-level compactness vs separation)
- Davies–Bouldin Index (cluster similarity ratio)
- Calinski–Harabasz Index (between vs within variance ratio)
- Metric bias toward compact clusters
- Elongated and non-spherical cluster behavior

### PCA and Clustering Interaction
- Total variance decomposition
- Within vs between cluster variance
- When PCA improves clustering (noise removal)
- When PCA harms clustering (low-variance separation)
- Variance maximization vs separability tradeoff

Implementation notebooks include:

- Geometry experiments
- Distance concentration visualization
- K-Means experiments
- Hierarchical clustering comparisons
- DBSCAN demonstrations
- Cluster validation comparison (Silhouette vs DBI vs CH)
- PCA–clustering interaction experiments

**Outcome:**  
Structured understanding of unsupervised learning as a geometry- and assumption-driven discipline.

Ability to reason about clustering in terms of:

- Distance  
- Density  
- Linkage  
- Variance  
- Shape assumptions  
- Parameter sensitivity  
- Evaluation bias  

---

# Installation

Clone the repository:
# ML Foundations Rebuild

A structured 6-week rebuild of core machine learning foundations, covering linear algebra, supervised learning, unsupervised learning, and disciplined model reasoning.

This repository is not about certificate accumulation.

It is a deliberate rebuild of ML fundamentals through:
- Clear theory documentation
- Mathematical reasoning
- Structured experimentation
- Clean implementation

---

## Why This Repository Exists

The goal of this sprint is to:

- Strengthen linear algebra confidence
- Deepen statistical learning understanding
- Build disciplined model selection habits
- Transition from "fitting models" to "understanding generalization"
- Understand clustering assumptions structurally
- Develop evaluation maturity across paradigms
- Prepare for advanced ML, interpretability, and production systems

---

# Repository Structure

ML-foundations-rebuild/\
│\
├── linear_algebra/\
├── supervised_learning/\
├── unsupervised_learning/\
├── interpretability/\
├── mlops_pipeline/\
│\
├── requirements.txt\
└── README.md

---

## Week 1 – Linear Algebra Foundations

Topics covered:

- Matrix multiplication & transformations
- Eigenvalues and eigenvectors
- Singular Value Decomposition (SVD)
- Principal Component Analysis (PCA)

Focus:  
Understanding how matrix operations drive machine learning models.

---

## Week 2 – Supervised Learning

### Regression
- Bias–Variance Tradeoff
- OLS and Multicollinearity
- Ridge & Lasso Regularization
- Cross-Validation
- AIC & AICc

### Classification
- Logistic Regression (log-odds modeling)
- Cross-Entropy Loss
- Linear Decision Boundaries

### Nonlinear Models
- Decision Trees (Gini & Entropy intuition)
- Tree Instability & Overfitting

### Ensemble Learning
- Bagging
- Random Forest
- Variance reduction through decorrelation

### Margin-Based Classification
- Support Vector Machines (SVM)
- Maximum margin principle
- Hard vs Soft margin
- C parameter (regularization tradeoff)
- Kernel trick
- RBF kernel and gamma
- Bias–variance behavior in SVM

### Model Evaluation
- Confusion Matrix
- Precision, Recall, F1
- ROC vs Precision–Recall analysis
- Threshold tradeoffs
- Calibration and probability reliability

### Resampling & Diagnostics
- Cross-validation recap
- Bootstrap sampling
- Out-of-bag intuition
- Variance estimation
- Learning curve analysis
- Diagnosing bias vs variance
- Data vs model capacity tradeoff

Implementation notebooks include:

- Bias–Variance visualization
- Ridge vs Lasso coefficient comparison
- Cross-validation tuning
- OLS vs Ridge vs Lasso vs Random Forest comparison
- Logistic Regression demonstration
- Tree & ensemble visualizations
- ROC, PR, and calibration analysis
- Bootstrap variance estimation
- Learning curve demo
- SVM boundary visualization

**Outcome:**  
Structured understanding of model construction, regularization, evaluation, margin maximization, and generalization behavior.

---

## Week 3 – Unsupervised Learning

### Geometric Foundations
- Distance metrics and similarity
- Feature scaling and distortion
- Curse of dimensionality
- Distance concentration
- Noise accumulation in high dimensions
- Variance vs separation distinction

### Clustering Paradigms

**Centroid-Based (K-Means)**
- WCSS / inertia objective
- Lloyd’s algorithm
- Initialization sensitivity (k-means++)
- Spherical cluster assumption
- Elbow method
- Silhouette intuition

**Linkage-Based (Hierarchical)**
- Single, Complete, Average, Ward linkage
- Dendrogram interpretation
- Chaining effect
- Nested cluster structure

**Density-Based (DBSCAN)**
- Core, border, and noise points
- Density connectivity
- Epsilon and min_samples sensitivity
- Arbitrary shape detection
- Failure under varying densities

### Internal Cluster Validation
- Silhouette score (point-level compactness vs separation)
- Davies–Bouldin Index (cluster similarity ratio)
- Calinski–Harabasz Index (between vs within variance ratio)
- Metric bias toward compact clusters
- Elongated and non-spherical cluster behavior

### PCA and Clustering Interaction
- Total variance decomposition
- Within vs between cluster variance
- When PCA improves clustering (noise removal)
- When PCA harms clustering (low-variance separation)
- Variance maximization vs separability tradeoff

Implementation notebooks include:

- Geometry experiments
- Distance concentration visualization
- K-Means experiments
- Hierarchical clustering comparisons
- DBSCAN demonstrations
- Cluster validation comparison (Silhouette vs DBI vs CH)
- PCA–clustering interaction experiments

**Outcome:**  
Structured understanding of unsupervised learning as a geometry- and assumption-driven discipline.

Ability to reason about clustering in terms of:

- Distance  
- Density  
- Linkage  
- Variance  
- Shape assumptions  
- Parameter sensitivity  
- Evaluation bias  

---

# Installation

Clone the repository:
git clone https://github.com/aniray2908/ML-foundations-rebuild.git
cd ML-foundations-rebuild

Install dependencies:
pip install -r requirements.txt

---

# Key Learning Philosophy

This repository follows three principles:

1. Theory before tooling  
2. Derivation before automation  
3. Evaluation before optimization  

Model performance is not just about accuracy.  
It is about understanding:

- Bias
- Variance
- Calibration
- Geometry
- Margin
- Density
- Separation
- Assumptions

Machine learning is treated as a structural discipline.

---

# Next Phase

The next module expands into:

- Model interpretability (global vs local explanation)
- Feature importance & permutation importance
- Partial dependence analysis
- SHAP intuition and additive explanations
- Transition into reproducible ML systems and MLOps foundations

---

# References

Primary sources used in this rebuild:

- James, Witten, Hastie, Tibshirani — *Introduction to Statistical Learning*
- Hastie, Tibshirani, Friedman — *The Elements of Statistical Learning*
- Stanford Statistical Learning Lectures
- Scikit-learn Documentation

---

# Author

Anisha Ray
