# SHAP Intuition

SHAP (SHapley Additive exPlanations) is a framework for explaining individual predictions of machine learning models.

While earlier interpretability methods answer questions such as:

- Which features matter overall? (Feature Importance)
- How predictions change when a feature changes? (Partial Dependence)

SHAP addresses a different question:

> Why did the model produce this specific prediction?

SHAP provides **local explanations** by decomposing a model prediction into contributions from each feature.

---

# Why SHAP Exists

Many machine learning models are highly accurate but difficult to interpret.

Examples include:

- Random Forest
- Gradient Boosting
- Neural Networks
- Kernel SVM

These models may produce strong predictions, but their internal reasoning is often opaque.

This creates problems in real-world applications:

- Model debugging becomes difficult
- Bias detection becomes harder
- Regulatory compliance may require explanations
- Users may not trust automated decisions

SHAP addresses these challenges by providing **consistent and mathematically grounded explanations**.

---

# The Core Idea

SHAP explains a prediction by comparing it to a **baseline prediction**.

The baseline represents the model's expected prediction when no specific feature information is known.

A prediction can therefore be written as:

prediction = baseline + feature contributions

Each feature contributes either positively or negatively to the final prediction.

Example:

Baseline house price:  
300k

Model prediction:  
500k

SHAP explanation:

| Feature | Contribution |
|-------|--------|
| Size | +120k |
| Location | +60k |
| Renovation | +20k |

Total:

300k + 120k + 60k + 20k = 500k

This decomposition explains **how each feature pushed the prediction away from the baseline**.

---

# Connection to Game Theory

SHAP values are based on **Shapley values**, a concept from cooperative game theory.

In game theory, multiple players cooperate to produce a shared reward.

Example:

Players collaborate to generate profit.

The question becomes:

> How should the total reward be fairly divided among the players?

Each player's contribution depends on **how much value they add to the group**.

However, this contribution can change depending on **the order in which players join the coalition**.

Example:

If Player A joins first, their contribution might appear large.

If Player A joins later, the marginal contribution might be smaller.

To ensure fairness, the Shapley value calculates a player's contribution by averaging their **marginal impact across all possible player orderings**.

SHAP applies this same principle to machine learning features.

---

# SHAP in Machine Learning

In SHAP:

- Features act as "players"
- The prediction acts as the "game outcome"

The goal is to determine how much each feature contributed to the final prediction.

SHAP computes the **average marginal contribution of each feature across all possible feature orderings**.

This produces a fair allocation of credit among features.

---

# Additive Explanation Model

SHAP explanations follow an additive structure:

f(x) = base_value + Σ φ_i

Where:

- f(x) = model prediction
- base_value = baseline prediction
- φ_i = contribution of feature i

This additive property ensures that:

The sum of all feature contributions equals the prediction difference from the baseline.

This property is called **additivity**.

---

# Important SHAP Properties

SHAP explanations satisfy several desirable theoretical properties.

## Additivity

The explanation must exactly reconstruct the model prediction.

prediction = baseline + sum(feature contributions)

This ensures explanations are internally consistent.

---

## Consistency

If a model changes so that a feature contributes more strongly to predictions, its SHAP value cannot decrease.

This guarantees logical behavior of feature attributions.

---

## Fair Credit Allocation

Feature contributions are averaged across all possible feature orderings.

This prevents unfair attribution caused by feature ordering effects.

---

# Global vs Local SHAP

SHAP values are primarily designed for **local explanations**, but they can also provide global insights.

### Local Explanations

Local SHAP values explain individual predictions.

Example:

Why was this specific loan application rejected?

SHAP values show how each feature pushed the prediction toward approval or rejection.

---

### Global Interpretability

Aggregating SHAP values across many observations reveals:

- which features influence the model most
- how feature effects vary across the dataset

This allows SHAP to also serve as a **global interpretability tool**.

---

# SHAP Visualizations

Several visualization methods help interpret SHAP values.

## Waterfall Plot

Shows how each feature contribution moves the prediction from baseline to final prediction.

Useful for explaining **individual predictions**.

---

## Summary Plot

Displays feature importance across the dataset.

Each point represents a feature contribution for a specific observation.

This reveals:

- feature importance
- direction of influence
- distribution of effects

---

## Dependence Plot

Shows how SHAP values vary with feature values.

This is similar to a **partial dependence plot**, but incorporates interaction effects.

---

# Advantages of SHAP

SHAP provides several advantages over earlier interpretability methods.

- Theoretical foundation in game theory
- Consistent feature attribution
- Works with any machine learning model
- Supports both local and global explanations
- Compatible with modern ML pipelines

---

# Limitations of SHAP

Despite its strengths, SHAP has some limitations.

### Computational Cost

Exact Shapley value computation requires evaluating all feature permutations.

This becomes computationally expensive as feature count increases.

Approximation methods are often used in practice.

---

### Correlated Features

When features are highly correlated, SHAP may distribute credit among them in unintuitive ways.

This reflects the ambiguity in determining which feature truly caused the prediction.

---

### Interpretability vs Causality

SHAP explains **model behavior**, not real-world causality.

A feature with a large SHAP value does not necessarily cause the outcome.

---

# Relationship to Other Interpretability Methods

SHAP connects naturally to other techniques studied earlier.

| Method | Question Answered |
|------|------|
| Feature Importance | Which features matter most? |
| Partial Dependence | How predictions change with feature values? |
| SHAP | Why this specific prediction occurred? |

Together these techniques provide a comprehensive view of model behavior.

---

# Summary

SHAP provides a principled way to explain machine learning predictions.

By decomposing predictions into additive feature contributions, SHAP enables both local and global interpretability.

The method combines:

- cooperative game theory
- additive explanations
- fair feature attribution

As machine learning models become increasingly complex, interpretability tools like SHAP play a critical role in ensuring models remain transparent, debuggable, and trustworthy.
