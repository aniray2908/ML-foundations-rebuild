# ML Foundations Rebuild

A structured 6-week rebuild of core machine learning foundations, covering linear algebra, statistical learning, and disciplined model evaluation.

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
- Prepare for advanced ML, MLOps, and production systems

---

# Repository Structure

ML-foundations-rebuild/\  
│\  
├── linear_algebra/\  
├── statistical_learning/\
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

## Week 2 – Statistical Learning

Topics Covered:

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

### Model Evaluation
- Confusion Matrix
- Precision, Recall, F1
- ROC vs Precision–Recall analysis
- Threshold tradeoffs
- Calibration and probability reliability

Implementation notebooks include:

- Bias–Variance visualization
- Ridge vs Lasso coefficient comparison
- Cross-validation tuning of Ridge
- OLS vs Ridge vs Lasso vs Random Forest comparison
- Logistic Regression demonstration
- Decision Tree vs Random Forest visualization
- ROC, PR, and calibration analysis

Outcome:

Completed supervised learning foundations covering:

- Regression and regularization
- Classification modeling
- Ensemble learning
- Bias–variance reasoning
- Model evaluation under class imbalance
- Calibration and cost-aware decision thinking

Result:  
Structured understanding of both model construction and disciplined model evaluation.

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
It is about understanding bias, variance, calibration, and generalization behavior.

---

# References

Primary sources used in this rebuild:

- James, Witten, Hastie, Tibshirani — *Introduction to Statistical Learning*
- Hastie, Tibshirani, Friedman — *The Elements of Statistical Learning*
- Stanford Statistical Learning Lectures
- Scikit-learn Documentation

---

# Next Steps

Upcoming sections will expand into:

- Engineered ML pipelines
- Reproducible experimentation
- Model versioning and tracking
- MLOps foundations

---

# Author

Anisha Ray
