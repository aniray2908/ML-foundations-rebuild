# 02 – Feature Importance

Feature importance methods aim to quantify how strongly a machine learning model relies on each input feature when making predictions.

Understanding feature importance helps answer questions such as:

- Which variables influence the model most?
- What signals has the model learned from the data?
- Are there unexpected or suspicious predictors driving predictions?

Feature importance provides a **global explanation** of model behavior by measuring how strongly features influence predictions across the dataset.

However, importance must be interpreted carefully because it does not imply **causality**.

---

# 1. What Feature Importance Measures

Feature importance answers the question:

> How much does the model rely on a feature when making predictions?

This is fundamentally different from asking whether the feature **causes** the outcome.

Feature importance reflects **model dependence**, not real-world causal influence.

For example:

| Feature | Importance |
|-------|------------|
| Credit score | High |
| Income | Medium |
| Age | Low |

This means the model relies heavily on credit score when making predictions.

It does **not** necessarily mean that credit score is the true causal driver of the outcome.

A feature may appear important simply because it is correlated with other important variables.

---

# 2. Tree-Based Feature Importance

Many tree-based models compute feature importance using **impurity reduction**.

Examples include:

- Decision Trees
- Random Forests
- Gradient Boosting Trees

During training, the tree repeatedly splits the data using features that reduce prediction error.

Each split reduces impurity in the dataset.

Common impurity measures include:

- **Gini impurity** (classification)
- **Entropy** (classification)
- **Mean squared error (MSE)** (regression)

Feature importance is calculated by summing the **total impurity reduction** contributed by each feature across all splits.

Formally:

Feature Importance = Total impurity reduction contributed by the feature.

Features that frequently produce large reductions in impurity receive higher importance scores.

---

# 3. Bias in Tree-Based Importance

Tree-based feature importance has several known biases.

These biases arise because the importance score depends on how often a feature is selected for splits.

---

## 3.1 Bias Toward Continuous Features

Continuous variables often appear more important because they provide many possible split points.

Example:
income < 30k
income < 40k
income < 50k
income < 60k

Each threshold is a potential split candidate.

More candidate splits increase the chance of reducing impurity.

Binary variables provide only one possible split.

Example:
gender = male vs female

As a result, continuous features often receive artificially higher importance.

---

## 3.2 Bias Toward High-Cardinality Features

Features with many unique values may also appear artificially important.

Example:
ZIP code
customer ID
product ID

These variables allow many possible splits.

The model may overfit to such features, giving them inflated importance scores.

---

# 4. Permutation Importance

Permutation importance addresses many limitations of tree-based importance.

It measures feature importance using **model performance degradation**.

Instead of examining the internal structure of the model, permutation importance evaluates how predictions change when feature information is destroyed.

This makes permutation importance **model-agnostic**.

---

## 4.1 Algorithm

Permutation importance is computed using the following procedure:

1. Train a model on the dataset.
2. Measure baseline model performance.
3. Randomly shuffle the values of a single feature.
4. Recompute model performance using the shuffled dataset.
5. Measure the performance drop.

Feature importance is defined as:

Performance drop after shuffling the feature.

If shuffling a feature causes a large drop in performance, the model relies heavily on that feature.

---

## 4.2 Interpretation

| Feature | Accuracy Drop | Importance |
|------|------|------|
| Credit score | Large drop | High |
| Income | Moderate drop | Medium |
| Age | No change | Low |

If performance remains unchanged after shuffling a feature, the model likely does not rely on it.

---

# 5. Correlated Feature Pitfall

Permutation importance can behave unexpectedly when features are highly correlated.

Consider two features:
income
salary

These variables may contain nearly identical information.

If the model uses **income**, then **salary** becomes redundant.

If we shuffle **salary**, the model can still rely on **income**.

As a result:

Permutation importance for salary may appear near zero.

This does not mean salary has no predictive information.

It simply means the model can obtain the same signal from another variable.

This phenomenon is known as **importance dilution** under feature correlation.

---

# 6. Importance vs Causality

A critical limitation of feature importance is that it measures **correlation**, not causation.

A feature may appear important even if it does not cause the outcome.

Example:

A housing price model might assign high importance to:
Number of nearby coffee shops

However, coffee shops do not cause house prices to increase.

Instead, both may be driven by a third factor:
Neighborhood wealth

Coffee shops act as a **proxy variable**.

Interpretability methods reveal what the model has learned, but they do not identify the true causal mechanisms behind the data.

---

# 7. Proxy Variables and Hidden Bias

Some features may act as proxies for sensitive attributes.

For example:
ZIP code → neighborhood → socioeconomic status

If a model heavily relies on ZIP code, it may indirectly use demographic or socioeconomic information.

Interpretability methods help detect such behavior.

This allows practitioners to audit models for fairness and ethical concerns.

---

# 8. Practical Guidelines

When interpreting feature importance:

1. Examine whether important features make logical sense.
2. Check for high-cardinality or identifier variables.
3. Investigate correlations between important features.
4. Consider domain knowledge when interpreting results.
5. Use multiple interpretability techniques when possible.

Feature importance should be treated as a **diagnostic tool**, not a definitive explanation.

---

# Core Takeaway

Feature importance helps reveal how machine learning models use input features.

It provides a global explanation of model behavior.

However, importance measures:

- model reliance
- statistical association

—not real-world causality.

Careful interpretation is required to avoid misleading conclusions.
