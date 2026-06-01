# External Package Map

## Manifest vs Reality

### Declared and Used

| Package | Declared In | Imported By Files | Scope |
|---------|------------|------------------|-------|
| `catboost` | requirements/pyproject | 1 files (model_benchmark.py...) | single file |
| `joblib` | requirements/pyproject | 1 files (model_state.py...) | single file |
| `lightgbm` | requirements/pyproject | 2 files (model_benchmark.py, train_and_save_models.py...) | core only |
| `numpy` | requirements/pyproject | 23 files (marketplace_subcategory.py, pipeline.py, recurring...) | widespread |
| `pandas` | requirements/pyproject | 35 files (marketplace_subcategory.py, tutorial_real_data.py,...) | widespread |
| `psutil` | requirements/pyproject | 1 files (tests/run_stress_legacy.py...) | single file |
| `pytest` | requirements/pyproject | 10 files (tests/test_phase3.py, tests/test_ml_integration.py...) | widespread |
| `scikit-learn` | requirements/pyproject | 10 files (pipeline.py, model_benchmark.py, train_and_save_mo...) | widespread |
| `xgboost` | requirements/pyproject | 1 files (model_benchmark.py...) | single file |

### Declared but Never Imported

| Package | Declared In | Notes |
|---------|------------|-------|
| `fastparquet` | requirements/pyproject | **UNUSED** |
| `openpyxl` | requirements/pyproject | **UNUSED** |
| `pyarrow` | requirements/pyproject | **UNUSED** |
| `scipy` | requirements/pyproject | **UNUSED** |

### Imported but Not Declared

| Package | Imported By | Notes |
|---------|------------|-------|

## Package Concentration Risk

- **`pandas`**: Imported by 35 files. If this breaks or is upgraded with breaking changes, the blast radius is wide.
- **`numpy`**: Imported by 23 files. If this breaks or is upgraded with breaking changes, the blast radius is wide.
- **`scikit-learn`**:  Imported by 10 files. If this breaks or is upgraded with breaking changes, the blast radius is wide.
- **`pytest`**: Imported by 10 files. If this breaks or is upgraded with breaking changes, the blast radius is wide.

## Package → File Reverse Map

| Package | Files That Import It | Symbols Used |
|---------|---------------------|-------------|
| `__future__` | `passion_models.py` | [annotations] |
| `__future__` | `candidate.py` | [annotations] |
| `__future__` | `pipeline_result.py` | [annotations] |
| `catboost` | `model_benchmark.py` | [CatBoostClassifier] |
| `contextvars` | `logger_factory.py` | [*] |
| `gc` | `tests/run_stress_legacy.py` | [*] |
| `glob` | `analyzer.py` | [*] |
| `hmac` | `log_utils.py` | [*] |
| `inspect` | `tests/test_passion_engine.py` | [*] |
| `joblib` | `model_state.py` | [*] |
| `lightgbm` | `model_benchmark.py` | [LGBMClassifier] |
| `lightgbm` | `train_and_save_models.py` | [LGBMClassifier] |
| `numbers` | `passion_pipeline.py` | [Real, Integral] |
| `numpy` | `marketplace_subcategory.py` | [*] |
| `numpy` | `pipeline.py` | [*] |
| `numpy` | `recurring_detector.py` | [*] |
| `numpy` | `model_benchmark.py` | [*] |
| `numpy` | `training_data_generator.py` | [*] |
| `numpy` | `model_state.py` | [*] |
| `numpy` | `preprocessor.py` | [*] |
| `numpy` | `log_utils.py` | [*] |
| `numpy` | `feature_engineer.py` | [*] |
| `numpy` | `passion_models.py` | [*] |
| `numpy` | `passion_utils.py` | [*] |
| `numpy` | `candidate.py` | [*] |
| `numpy` | `expected_spend_model.py` | [*] |
| `numpy` | `passion_pipeline.py` | [*] |
| `numpy` | `passion_detector.py` | [*] |
| `numpy` | `tests/run_stress_heavy.py` | [*] |
| `numpy` | `tests/test_known_persons.py` | [*] |
| `numpy` | `tests/test_phase2.py` | [*] |
| `numpy` | `tests/test_passion_engine.py` | [*] |
| `numpy` | `tests/test_benchmark.py` | [*] |
| `numpy` | `tests/test_phase1.py` | [*] |
| `numpy` | `tests/test_e2e.py` | [*] |
| `numpy` | `tests/run_stress_legacy.py` | [*] |
| `pandas` | `marketplace_subcategory.py` | [*] |
| `pandas` | `tutorial_real_data.py` | [*] |
| `pandas` | `pipeline.py` | [*] |
| `pandas` | `recurring_detector.py` | [*] |
| `pandas` | `anomaly_detector.py` | [*] |
| `pandas` | `known_persons.py` | [*] |
| `pandas` | `summary_utils.py` | [*] |
| `pandas` | `demo.py` | [*] |
| `pandas` | `schema.py` | [*] |
| `pandas` | `seed_labeler.py` | [*] |
| `pandas` | `model_benchmark.py` | [*] |
| `pandas` | `insight_generator.py` | [*] |
| `pandas` | `categorization_model.py` | [*] |
| `pandas` | `training_data_generator.py` | [*] |
| `pandas` | `insight_model.py` | [*] |
| `pandas` | `preprocessor.py` | [*] |
| `pandas` | `log_utils.py` | [*] |
| `pandas` | `feature_engineer.py` | [*] |
| `pandas` | `passion_utils.py` | [*] |
| `pandas` | `pipeline_result.py` | [*] |
| `pandas` | `expected_spend_model.py` | [*] |
| `pandas` | `passion_pipeline.py` | [*] |
| `pandas` | `passion_detector.py` | [*] |
| `pandas` | `tests/run_stress_heavy.py` | [*] |
| `pandas` | `tests/test_phase3.py` | [*] |
| `pandas` | `tests/test_ml_integration.py` | [*] |
| `pandas` | `tests/test_known_persons.py` | [*] |
| `pandas` | `tests/test_phase2.py` | [*] |
| `pandas` | `tests/test_passion_engine.py` | [*] |
| `pandas` | `tests/test_benchmark.py` | [*] |
| `pandas` | `tests/test_logging_safety.py` | [*] |
| `pandas` | `tests/test_phase1.py` | [*] |
| `pandas` | `tests/test_e2e.py` | [*] |
| `pandas` | `tests/run_smoke.py` | [*] |
| `pandas` | `tests/run_stress_legacy.py` | [*] |
| `psutil` | `tests/run_stress_legacy.py` | [*] |
| `pytest` | `tests/test_phase3.py` | [*] |
| `pytest` | `tests/test_ml_integration.py` | [*] |
| `pytest` | `tests/test_known_persons.py` | [*] |
| `pytest` | `tests/conftest.py` | [*] |
| `pytest` | `tests/test_phase2.py` | [*] |
| `pytest` | `tests/test_passion_engine.py` | [*] |
| `pytest` | `tests/test_benchmark.py` | [*] |
| `pytest` | `tests/test_model_security.py` | [*] |
| `pytest` | `tests/test_logging_safety.py` | [*] |
| `pytest` | `tests/test_phase1.py` | [*] |
| `scikit-learn` | `pipeline.py` | [Pipeline] |
| `scikit-learn` | `model_benchmark.py` | [MLPClassifier, accuracy_score, DecisionTreeClassifier, AdaBoostClassifier, precision_score, Pipeline, CalibratedClassifierCV, KNeighborsClassifier, recall_score, LogisticRegression, GradientBoostingClassifier, LabelEncoder, StandardScaler, classification_report, confusion_matrix, f1_score, RandomForestClassifier, ColumnTransformer, OneHotEncoder, LinearSVC, StratifiedKFold, ExtraTreesClassifier, cross_validate] |
| `scikit-learn` | `train_and_save_models.py` | [ColumnTransformer, OneHotEncoder, StandardScaler, Pipeline] |
| `scikit-learn` | `categorization_model.py` | [Pipeline, LogisticRegression, TfidfVectorizer, ColumnTransformer, StandardScaler] |
| `scikit-learn` | `training_data_generator.py` | [train_test_split] |
| `scikit-learn` | `insight_model.py` | [Pipeline] |
| `scikit-learn` | `model_state.py` | [Pipeline] |
| `scikit-learn` | `expected_spend_model.py` | [RidgeCV, Pipeline, ColumnTransformer, OneHotEncoder, StandardScaler] |
| `scikit-learn` | `tests/test_ml_integration.py` | [Pipeline] |
| `scikit-learn` | `tests/test_benchmark.py` | [Pipeline, LogisticRegression, ColumnTransformer, OneHotEncoder, StandardScaler] |
| `traceback` | `tests/run_smoke.py` | [*] |
| `types` | `marketplace_subcategory.py` | [MappingProxyType] |
| `types` | `bootstrap.py` | [MappingProxyType] |
| `types` | `contracts.py` | [MappingProxyType] |
| `types` | `config_passion.py` | [MappingProxyType] |
| `types` | `tests/test_passion_engine.py` | [MappingProxyType] |
| `unicodedata` | `banned_content.py` | [*] |
| `xgboost` | `model_benchmark.py` | [XGBClassifier] |