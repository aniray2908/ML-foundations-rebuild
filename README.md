# ML Foundations Rebuild

A structured 6-week rebuild of core machine learning foundations, covering linear algebra, supervised learning, unsupervised learning, interpretability, and disciplined model reasoning.

This repository is not about certificate accumulation.

It is a deliberate rebuild of ML fundamentals through:

- Clear theory documentation  
- Mathematical reasoning  
- Structured experimentation  
- Clean implementation  

---

# Why This Repository Exists

The goal of this sprint is to:

- Strengthen linear algebra confidence  
- Deepen statistical learning understanding  
- Build disciplined model selection habits  
- Transition from “fitting models” to “understanding generalization”  
- Understand clustering assumptions structurally  
- Develop evaluation maturity across paradigms  
- Learn interpretability techniques for real-world ML systems  
- Prepare for advanced ML engineering and MLOps  

---

# Repository Structure
ML-foundations-rebuild/\
│\
├── linear_algebra/\
├── supervised_learning/\
├── unsupervised_learning/\
├── interpretability/\
├── mlops_pipeline/\
├── assets/\
│\
├── requirements.txt\
└── README.md

---

# Week 1 – Linear Algebra Foundations

Topics covered:

- Matrix multiplication & transformations  
- Eigenvalues and eigenvectors  
- Singular Value Decomposition (SVD)  
- Principal Component Analysis (PCA)  

**Focus**

Understanding how matrix operations drive machine learning models.

---

# Week 2 – Supervised Learning

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

**Outcome**

Structured understanding of model construction, regularization, evaluation, margin maximization, and generalization behavior.

---

# Week 3 – Unsupervised Learning

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

- Silhouette score  
- Davies–Bouldin Index  
- Calinski–Harabasz Index  
- Metric bias toward compact clusters  
- Behavior on elongated and non-spherical clusters  

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

**Outcome**

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

# Week 4 – Model Interpretability

This module focuses on understanding **why models make predictions**.

### Interpretability Foundations

- Interpretability vs explainability  
- Transparent vs black-box models  
- Global vs local explanations  
- Accuracy vs interpretability tradeoff  

### Feature Attribution

- Linear model coefficient interpretation  
- Tree-based feature importance  
- Permutation importance  
- Correlation pitfalls in importance analysis  

### Model Behavior Analysis

- Partial dependence plots  
- Feature response visualization  
- Interaction analysis  

### Local Explanations

- SHAP intuition  
- Additive feature attribution  
- Instance-level explanation techniques  

Implementation notebooks demonstrate:

- Feature importance comparisons  
- Permutation importance experiments  
- Correlated feature pitfalls  
- Partial dependence visualization  

**Outcome**

Ability to analyze, explain, and communicate machine learning model behavior responsibly.

---

# Week 5 – MLOps Foundations

This module focuses on the **engineering discipline required to operationalize machine learning systems**.

While earlier modules focused on model behavior and statistical reasoning, this stage addresses the **systems architecture required for reliable ML workflows**.

Modern ML systems require structured pipelines, reproducible experimentation, model lifecycle management, and data governance.

---

### ML Pipeline Architecture

- Data ingestion  
- Data validation  
- Feature engineering  
- Model training  
- Model evaluation  
- Model artifact generation  

Understanding pipeline structure helps transform ad-hoc experimentation into **structured and repeatable workflows**.

---

### Reproducibility

Machine learning experiments often contain multiple sources of randomness.

This section covers:

- Random seeds  
- Deterministic data splits  
- Dependency management  
- Dataset versioning  

Reproducibility ensures experiments can be **repeated and verified reliably**.

---

### Experiment Tracking

ML development typically involves running many experiments.

Experiment tracking records:

- Model architectures  
- Hyperparameters  
- Dataset versions  
- Evaluation metrics  

This enables systematic **comparison of models and training strategies**.

---

### Model Versioning

Models evolve as datasets and training strategies improve.

Model versioning provides structured mechanisms to:

- Store trained model artifacts  
- Track model evolution  
- Manage deployment stages  
- Enable safe rollback of models  

---

### Data Validation

Machine learning systems depend on stable and reliable input data.

This module covers validation mechanisms including:

- Schema validation  
- Missing value detection  
- Range checks  
- Data drift monitoring  
- Feature distribution monitoring  

Data validation protects pipelines from **silent model failures caused by unexpected data changes**.

---

### Implementation Notebooks

This module includes demonstration notebooks covering:

- Structured ML pipeline implementation  
- Reproducible experiment design  
- Experiment tracking workflows  
- Hyperparameter experiment comparison  

These demonstrations illustrate how **engineering practices support reliable machine learning systems**.

---

**Outcome**

Understanding how machine learning systems transition from experimentation to **production-grade engineering workflows**.

Key capabilities developed include:

- Designing structured ML pipelines  
- Building reproducible experiments  
- Tracking model development  
- Managing model lifecycle and versioning  
- Validating production data pipelines
