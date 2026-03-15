# Model Versioning

Machine learning models evolve over time.

As new data becomes available and better training methods are developed, models are retrained and updated.

Model versioning ensures that each trained model is stored, tracked, and managed in a structured way.

Without model versioning, it becomes difficult to:

- track model improvements
- reproduce past results
- rollback to a previous model
- audit deployed systems

Model versioning is therefore a fundamental component of reliable machine learning systems.

---

# Why Model Versioning Matters

In traditional software systems, code changes are tracked using version control systems.

Machine learning systems require a similar approach for models.

Each trained model represents a unique combination of:

- dataset
- feature pipeline
- model architecture
- hyperparameters
- training environment

If any of these components change, the resulting model becomes a new version.

Tracking these versions ensures that model evolution remains transparent and reproducible.

---

# Model Artifacts

A trained model is stored as a **model artifact**.

A model artifact typically contains:

- the trained model parameters
- model configuration
- metadata about the training process

Common model artifact formats include:

- `.pkl`
- `.joblib`
- `.onnx`
- `.pt` (PyTorch)
- `.h5` (TensorFlow / Keras)

Example artifact:

```
housing_model_v1.pkl
```

---

# Model Version Identifiers

Each trained model should receive a version identifier.

Example:

```
model_v1
model_v2
model_v3
```

Version identifiers allow engineers to track how models improve over time.

Example model history:

| Version | Model Type | RMSE |
|------|------|------|
| v1 | Linear Regression | 0.74 |
| v2 | Random Forest | 0.61 |
| v3 | Random Forest (tuned) | 0.52 |

---

# Model Registry

A **model registry** stores trained models and their associated metadata.

The registry records information such as:

- model version
- training dataset
- feature pipeline
- hyperparameters
- evaluation metrics
- training timestamp

This allows teams to manage multiple models simultaneously.

Typical model lifecycle states include:

- **development**
- **staging**
- **production**
- **archived**

These states help organize models during deployment workflows.

---

# Model Rollback

Production systems sometimes require **model rollback**.

If a newly deployed model performs poorly, engineers may need to restore a previous model version.

Example:

```
current production model: v3
performance degradation detected
rollback to model v2
```

Versioned models make rollback straightforward and safe.

---

# Model Lineage

Model lineage describes the history of a model.

This includes:

- the dataset used
- the training pipeline
- experiment configurations
- previous model versions

Tracking lineage allows engineers to understand how models evolved.

Example lineage:

```
dataset_v1 → model_v1
dataset_v2 → model_v2
dataset_v3 → model_v3
```

---

# Model Versioning in ML Pipelines

In production ML pipelines, model versioning is integrated into the training workflow.

Typical pipeline:

```
data ingestion
↓
feature engineering
↓
model training
↓
evaluation
↓
model artifact saved
↓
model registered
```

Each successful training run produces a **new model version**.

---

# Relationship to Previous Concepts

Model versioning builds upon earlier MLOps principles.

- **Reproducibility** ensures models can be recreated.
- **Experiment tracking** records how models were trained.
- **Model versioning** stores trained models and manages their lifecycle.

Together, these practices create a structured workflow for machine learning development.

---

# Summary

Model versioning ensures that trained models are tracked, stored, and managed throughout their lifecycle.

By assigning version identifiers, storing model artifacts, and maintaining a model registry, teams can:

- track model evolution
- compare model performance
- safely deploy updates
- rollback problematic models

Model versioning is therefore an essential component of reliable and maintainable machine learning systems.
