# Subsystem: 09b Model Benchmarking

## Files in Scope
- `model_benchmark.py` (CORE_LOGIC)

## 1. Responsibility
- **Owns**: Running an exhaustive comparison of scikit-learn and gradient boosting classifiers against the synthetic insight dataset to validate the choice of `LGBMClassifier` as the production standard.
- **Does NOT own**: Saving models for production.

## 2. Public Interface

### `run_benchmark() → pd.DataFrame`
- **File**: `model_benchmark.py`
- **Preconditions**: Needs `training_data_generator.py`.
- **Postconditions**: Returns a dataframe of metrics (Accuracy, Precision, Recall, F1, Train Time).
- **Side effects**: Heavy CPU usage. Prints to standard out.

## 3. Internal Design
- **Key algorithms**:
    - Defines a massive dictionary of candidate models (Logistic Regression, Random Forest, XGBoost, CatBoost, LightGBM, MLP, etc).
    - Runs 5-fold cross-validation on each using StratifiedKFold.
    - Extracts feature importances for tree-based models to explain *why* the model makes decisions.

## 4. Issues & Risks
- **SMELL**: Heavy dependencies.
    - *What it does*: Imports `xgboost` and `catboost` imports (lines 26-27).
    - *Why it is a problem*: These are massive C++ bound libraries. If they are in `requirements.txt` instead of a separate dev/benchmarking file, they bloat the production docker image by hundreds of megabytes for a script that is never run in production.
    - *Suggested fix*: Ensure `model_benchmark.py` dependencies are strictly in `requirements-dev.txt` or a separate `requirements-benchmark.txt`, and conditionally import them.
