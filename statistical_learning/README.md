# Statistical Learning

This section focuses on understanding model behavior, regularization, and structured model selection.

The goal is to move from:

“Fitting models”

to

“Understanding generalization and model complexity.”

---

## 📚 Theory Modules

- 01_bias_variance.md  
- 02_linear_regression.md  
- 03_regularization.md  
- 04_model_selection.md
- 05_logistic_regression.md
- 06_trees_and_ensembles.md
- conceptual_derivations.md  

## These documents cover:

Regression:
- Bias–variance tradeoff
- OLS and multicollinearity
- Ridge & Lasso mechanics

Model Selection:
- Cross-validation
- AIC & AICc
- Model selection philosophy

Classification:
- Logistic regression and log-odds modeling
- Cross-entropy loss

Nonlinear Models:
- Decision trees (Gini & Entropy intuition)
- Tree instability and overfitting

Ensemble Learning:
- Bagging
- Random Forest
- Variance reduction through decorrelation

---

## 📓 Implementation Notebooks

- 01_bias_variance_demo.ipynb  
- 02_ridge_vs_lasso.ipynb  
- 03_cross_validation_and_hyperparameter_tuning.ipynb  
- 04_model_comparison.ipynb
- 05_logistic_regression_demo.ipynb
- 06_tree_vs_random_forest_demo.ipynb


These notebooks demonstrate:

- Visual bias–variance behavior
- Coefficient shrinkage and sparsity
- Hyperparameter tuning using K-fold CV
- Structured model comparison

---

## Key Learning Outcome

- Bias–variance governs model behavior.
- Regularization controls variance.
- Cross-validation estimates generalization error.
- Model choice depends on signal structure.

---
## References

- [Introduction to Statistical Learning (ISLR)](https://www.statlearning.com/)
- [Scikit-learn Documentation](https://scikit-learn.org/stable/supervised_learning.html)
