# 03 – Partial Dependence

Partial Dependence Plots (PDPs) are a model interpretability technique used to understand how changes in a feature affect model predictions.

While feature importance identifies **which features matter**, partial dependence reveals **how those features influence predictions**.

PDPs provide a global view of the relationship between a feature and the model output.

---

# 1. Motivation

Machine learning models often learn complex nonlinear relationships between features and predictions.

However, examining model coefficients or feature importance alone does not reveal how a feature affects predictions.

For example, a feature may be important, but the model might learn:

- a linear relationship
- a nonlinear relationship
- a threshold effect
- diminishing returns

Partial dependence plots allow us to visualize these learned relationships.

---

# 2. Conceptual Idea

Partial dependence answers the question:

> If we vary a single feature while keeping other features constant, how does the model prediction change?

For a feature \( X_j \), partial dependence computes:

\[
PD(X_j) = E_{X_{-j}}[f(X_j, X_{-j})]
\]

Where:

- \( f(\cdot) \) is the model prediction
- \( X_j \) is the feature of interest
- \( X_{-j} \) represents all other features
- The expectation averages predictions across the dataset

In practice, this means:

1. Select a value for the feature of interest
2. Replace that feature value across all samples
3. Compute predictions
4. Average the predictions

This process is repeated for many values of the feature.

---

# 3. Interpreting Partial Dependence Plots

The resulting curve shows how predicted outcomes change as the feature varies.

---

## 3.1 Positive Relationship

If the PDP increases as the feature increases:
prediction
![Positive Partial Dependence](ML-foundations-rebuild/assets/interpretability_plots/pdp_positive_relationship.png)

The model predicts higher outcomes as the feature increases.

Example:

house size ↑ → predicted price ↑

---

## 3.2 Negative Relationship

If the curve decreases:
prediction
![Negative Partial Dependence](ML-foundations-rebuild/assets/interpretability_plots/pdp_negative_relationship.png)

The model predicts lower outcomes as the feature increases.

Example:

interest rate ↑ → loan approval probability ↓

---

## 3.3 Nonlinear Relationship

Many models learn nonlinear relationships.

Example:
prediction
![Nonlinear Partial Dependence](ML-foundations-rebuild/assets/interpretability_plots/pdp_nonlinear_relationship.png)

This may represent:

- lifecycle effects
- saturation effects
- optimal ranges

Example:
age → predicted income

Income may rise during early career years and decline later.

---

## 3.4 Diminishing Returns

A curve that rises and then flattens suggests diminishing marginal effects.
prediction
![Diminishing Returns PDP](ML-foundations-rebuild/assets/interpretability_plots/pdp_diminishing_returns.png)

Increasing the feature initially increases predictions, but the effect levels off.

Example:

house size vs predicted price

---

## 3.5 Flat Curve

A flat PDP indicates that the feature has little influence on predictions.
prediction
![Flat Partial Dependence](ML-foundations-rebuild/assets/interpretability_plots/pdp_flat_relationship.png)

This suggests the model does not rely strongly on that feature.

---

# 4. Overfitting Signals in PDP

Sometimes PDP curves exhibit strong oscillations or zig-zag patterns.

Example:
![Overfitting PDP Pattern](ML-foundations-rebuild/assets/interpretability_plots/pdp_overfit_pattern.png)

This can indicate:

- overfitting
- model instability
- sensitivity to noise

Such patterns often arise in very complex models such as deep decision trees.

---

# 5. Interaction Effects

PDP assumes that the effect of a feature can be examined independently.

However, features may interact with one another.

Example:
income effect on loan approval

may depend on:
credit score

In such cases, the PDP curve may represent an **average effect across different contexts**.

This can obscure feature interactions.

---

# 6. Limitations of Partial Dependence

Partial dependence has several important limitations.

---

## 6.1 Unrealistic Feature Combinations

When a feature is varied artificially, the resulting data points may not represent realistic combinations of features.

Example:
age = 18
years of experience = 30

Such combinations may not occur in real data.

Predictions for these unrealistic combinations can distort PDP interpretation.

---

## 6.2 Correlated Features

If the feature of interest is highly correlated with other features, varying it independently may break real-world relationships.

Example:
income ↔ years_of_experience

Changing income independently may produce unrealistic model inputs.

---

## 6.3 Averaging Effects

PDP averages predictions across the dataset.

This means it may hide different behaviors across subgroups.

Different segments of the population may exhibit different patterns.

---

# 7. PDP vs Other Interpretability Methods

| Method | Purpose |
|------|------|
| Feature Importance | Which features matter |
| Partial Dependence | How features influence predictions |
| SHAP Values | Why a specific prediction occurred |

These methods complement one another.

Together they provide a more complete understanding of model behavior.

---

# Core Takeaway

Partial dependence plots reveal how machine learning models translate feature values into predictions.

They help visualize nonlinear relationships, threshold effects, and diminishing returns.

However, PDPs must be interpreted carefully because:

- unrealistic feature combinations may occur
- correlated features can distort interpretation
- interaction effects may be hidden

PDPs should be used alongside other interpretability techniques to understand model behavior more fully.
