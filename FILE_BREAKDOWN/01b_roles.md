*(Part 2 of 4 - split due to length)*


### `tests/test_known_persons.py`

#### Dependencies
- **Direct internal**:
  - `known_persons.py` → [_suggestion_key, _enforce_known_person_schema, tag_known_persons, _extract_signals]
  - `model_state.py` → [InsightModelState]
  - `pipeline.py` → [_compute_config_hash, run_pipeline, PipelineResult, run_inference]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `anomaly_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `banned_content.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `bootstrap.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `candidate.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `categorization_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `config.py` (via `known_persons.py`) → [module/symbols used indirectly]
  - `config_passion.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `contracts.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `expected_spend_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `feature_engineer.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `log_utils.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `known_persons.py`) → [module/symbols used indirectly]
  - `marketplace_subcategory.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_models.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_pipeline.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_utils.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `pipeline_result.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `preprocessor.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `recurring_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `seed_labeler.py` (via `pipeline.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
  - `pytest` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: DATA_LAYER
- **Purpose**: Manages data retrieval, labeling, or enrichment.

#### Exports
- `test_known_persons_cfg` (function)
- `test_self_accounts_cfg` (function)
- `_create_minimal_test_df` (function)
- `test_extract_signals_upi_digits` (function)
- `test_tagging_exact_upi` (function)
- `test_tagging_self_account_fragment` (function)
- `test_merchant_suppression` (function)
- `test_concat_partial_with_bounds` (function)
- `test_enforce_schema_schema` (function)
- `test_suggestion_key_min_len` (function)
- `test_state_version_uses_di_params_not_globals` (function)

#### Side Effects
file I/O

---

## ENTRYPOINT

### `bootstrap.py`

#### Dependencies
- **Direct internal**:
  - `config_passion.py` → [validate_config, PASSION_INSIGHT_TEMPLATES, validate_merchant_aliases]
  - `contracts.py` → [INSIGHT_TEMPLATES, TIP_CORPUS]
  - `log_utils.py` → [_get_secret]
  - `logger_factory.py` → [get_logger]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `config.py` (via `contracts.py`) → [module/symbols used indirectly]
- **Direct external**:
  - none
- **Runtime / injected deps**: none

#### Identity
- **Role**: ENTRYPOINT
- **Purpose**: Initializes and bootstraps application environments or models.

#### Exports
- `__all__` (constant)
- `ALLOWED_FORMAT_SPECS` (constant)
- `validate_template_fields` (function)
- `_validate_python_version` (function)
- `_validate_schema_columns` (function)
- `_validate_insight_templates` (function)
- `_validate_passion_templates` (function)
- `_validate_tip_corpus` (function)
- `_validate_secret` (function)
- `_dry_render_templates` (function)
- `run_startup_checks` (function)

#### Side Effects
network calls

---

### `demo.py`

#### Dependencies
- **Direct internal**:
  - `pipeline.py` → [run_pipeline]
  - `schema.py` → [Col]
  - `summary_utils.py` → [print_summary]
- **Transitive internal**:
  - `anomaly_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `banned_content.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `bootstrap.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `candidate.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `categorization_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `config.py` (via `schema.py`) → [module/symbols used indirectly]
  - `config_passion.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `contracts.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `expected_spend_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `feature_engineer.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `known_persons.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `log_utils.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `schema.py`) → [module/symbols used indirectly]
  - `marketplace_subcategory.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `model_state.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_models.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_pipeline.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_utils.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `pipeline_result.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `preprocessor.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `recurring_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `seed_labeler.py` (via `pipeline.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: ENTRYPOINT
- **Purpose**: Runs a demo of the pipeline.

#### Exports
- none


#### Side Effects
file I/O (open/print), network calls, file I/O

---

### `passion_pipeline.py`

#### Dependencies
- **Direct internal**:
  - `banned_content.py` → [contains_banned_content]
  - `bootstrap.py` → [run_startup_checks]
  - `candidate.py` → [Candidate]
  - `config_passion.py` → [PIPELINE_BUDGET_MS, PASSION_MIN_DEBIT_ROWS, PIPELINE_TOP_N, MAX_SPIKE_CANDIDATES, PIPELINE_HARD_TIMEOUT_MS]
  - `logger_factory.py` → [get_logger]
  - `marketplace_subcategory.py` → [enrich_subcategories, resolve_merchant_vectorized]
  - `passion_detector.py` → [detect_passions]
  - `passion_insight_generator.py` → [generate_passion_insights]
  - `passion_utils.py` → [_safe_isna, coerce_bool_column, assert_columns_exist, safe_numeric]
  - `pipeline_result.py` → [PassionResult]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `config.py` (via `schema.py`) → [module/symbols used indirectly]
  - `contracts.py` (via `bootstrap.py`) → [module/symbols used indirectly]
  - `log_utils.py` (via `bootstrap.py`) → [module/symbols used indirectly]
  - `passion_models.py` (via `candidate.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: ENTRYPOINT
- **Purpose**: Orchestrator for the passion insights feature.

#### Exports
- `__all__` (constant)
- `_PERMANENT_STARTUP_ERRORS` (constant)
- `_neutral_passion_result` (function)
- `_ensure_initialized` (function)
- `_FATAL_EXCEPTIONS` (constant)
- `_should_reraise` (function)
- `PASSION_OWNED_OUTPUT_COLUMNS` (constant)
- `safe_assign_new_columns` (function)
- `_looks_like_compact_yyyymmdd` (function)
- `_normalize_ts` (function)
- `_CURRENCY_RE_LOCAL` (constant)
- `_INR_RE_LOCAL` (constant)
- `_is_unparseable_amount` (function)
- `_StepBudgetGuard` (class)
- `process_pipeline` (function)

#### Side Effects
network calls, file I/O

---

### `pipeline.py`

#### Dependencies
- **Direct internal**:
  - `anomaly_detector.py` → [detect_anomalies]
  - `categorization_model.py` → [predict_categories, train_categorization_model]
  - `config.py` → [module]
  - `expected_spend_model.py` → [predict_expected_spend, train_expected_spend_model]
  - `feature_engineer.py` → [engineer_features_inference, engineer_features]
  - `insight_generator.py` → [generate_human_insights]
  - `insight_model.py` → [predict_insight_scores, load_insight_ranker]
  - `known_persons.py` → [log_unmatched_recurring_transfers, detect_personal_patterns, _enforce_known_person_schema, tag_known_persons]
  - `log_utils.py` → [log_safe_text, log_safe_merchant]
  - `logger_factory.py` → [generate_new_run_id, get_logger, pipeline_run_id_ctx]
  - `model_state.py` → [InsightModelState]
  - `passion_pipeline.py` → [process_pipeline]
  - `preprocessor.py` → [preprocess]
  - `recurring_detector.py` → [find_recurring_transactions]
  - `schema.py` → [Col]
  - `seed_labeler.py` → [label_credits, label_debits]
- **Transitive internal**:
  - `banned_content.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `bootstrap.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `candidate.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `config_passion.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `contracts.py` (via `insight_generator.py`) → [module/symbols used indirectly]
  - `marketplace_subcategory.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `passion_detector.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `passion_insight_generator.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `passion_models.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `passion_utils.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `pipeline_result.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
  - `sklearn` → [Pipeline]
- **Runtime / injected deps**: none

#### Identity
- **Role**: ENTRYPOINT
- **Purpose**: Central Orchestrator, defines complete Insight Engine pipeline.

#### Exports
- `_compute_config_hash` (function)
- `_validate_state_version` (function)
- `PipelineResult` (class)
- `finalize_df` (function)
- `_optimize_memory_footprint` (function)
- `train_models` (function)
- `_pre_initialize_ml_columns` (function)
- `_write_crash_dumps` (function)
- `_resolve_passion_crash_fields` (function)
- `_attach_passion_results` (function)
- `run_pipeline` (function)
- `run_inference` (function)

#### Side Effects
file I/O (open/print), network calls, file I/O

---

### `train_and_save_models.py`

#### Dependencies
- **Direct internal**:
  - `insight_model.py` → [_compute_checksum]
  - `schema.py` → [Col]
  - `training_data_generator.py` → [generate_insight_dataset]
- **Transitive internal**:
  - `config.py` (via `training_data_generator.py`) → [module/symbols used indirectly]
  - `contracts.py` (via `training_data_generator.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `insight_model.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `lightgbm` → [LGBMClassifier]
  - `sklearn` → [ColumnTransformer, Pipeline, StandardScaler, OneHotEncoder]
- **Runtime / injected deps**: none

#### Identity
- **Role**: ENTRYPOINT
- **Purpose**: Script to train and save machine learning models.

#### Exports
- `NUMERIC_FEATURES` (constant)
- `CATEGORICAL_FEATURES` (constant)
- `train_and_save` (function)

#### Side Effects
file I/O (open/print), file I/O

---

### `tutorial_real_data.py`

#### Dependencies
- **Direct internal**:
  - `logger_factory.py` → [get_logger]
  - `pipeline.py` → [run_pipeline]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `anomaly_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `banned_content.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `bootstrap.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `candidate.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `categorization_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `config.py` (via `logger_factory.py`) → [module/symbols used indirectly]
  - `config_passion.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `contracts.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `expected_spend_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `feature_engineer.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `known_persons.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `log_utils.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `marketplace_subcategory.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `model_state.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_models.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_pipeline.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_utils.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `pipeline_result.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `preprocessor.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `recurring_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `seed_labeler.py` (via `pipeline.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: ENTRYPOINT
- **Purpose**: Demonstrates ingesting real bank statements.

#### Exports
- `run_real_data_tutorial` (function)

#### Side Effects
file I/O (open/print), file I/O

---

## SCHEMA

### `candidate.py`

#### Dependencies
- **Direct internal**:
  - `passion_models.py` → [PassionSignal]
- **Transitive internal**:
  - none
- **Direct external**:
  - `numpy` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: SCHEMA
- **Purpose**: Defines data schemas, types, classes, or domain models.

#### Exports
- `__all__` (constant)
- `_coerce_finite_float` (function)
- `Candidate` (class)

#### Side Effects
network calls

---

### `contracts.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [INSIGHT_TEMPLATES, TIP_CORPUS]
- **Transitive internal**:
  - none
- **Direct external**:
  - none
- **Runtime / injected deps**: none

#### Identity
- **Role**: SCHEMA
- **Purpose**: Defines data schemas, types, classes, or domain models.

#### Exports
- `_GENERIC_TIP_PREFIX` (constant)
- `_is_generic_tip_id` (function)
- `_freeze_insight_templates` (function)
- `_freeze_tip_corpus` (function)
- `INSIGHT_TEMPLATES` (constant)
- `TIP_CORPUS` (constant)
- `lookup_matching_tip_ids` (function)
- `__all__` (constant)

#### Side Effects
network calls

---

### `model_state.py`

#### Dependencies
- **Direct internal**:
  - none
- **Transitive internal**:
  - none
- **Direct external**:
  - `joblib` → [module]
  - `numpy` → [module]
  - `sklearn` → [Pipeline]
- **Runtime / injected deps**: none

#### Identity
- **Role**: SCHEMA
- **Purpose**: Defines data schemas, types, classes, or domain models.

#### Exports
- `InsightModelState` (class)
- `save_model_state` (function)
- `load_model_state` (function)

#### Side Effects
network calls

---

### `pipeline_result.py`

#### Dependencies
- **Direct internal**:
  - `candidate.py` → [Candidate]
  - `passion_models.py` → [PassionSignal]
- **Transitive internal**:
  - none
- **Direct external**:
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: SCHEMA
- **Purpose**: Defines data schemas, types, classes, or domain models.

#### Exports
- `__all__` (constant)
- `PassionResult` (class)

#### Side Effects
file I/O

---

### `schema.py`

#### Dependencies
- **Direct internal**:
  - `logger_factory.py` → [get_logger]
- **Transitive internal**:
  - `config.py` (via `logger_factory.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: SCHEMA
- **Purpose**: Defines data schemas, types, classes, or domain models.

#### Exports
- `Col` (class)
- `require_columns` (function)
- `coerce_and_validate_types` (function)

#### Side Effects
file I/O

---

## TEST

### `tests/conftest.py`

#### Dependencies
- **Direct internal**:
  - `log_utils.py` → [_reset_secret_cache]
  - `passion_pipeline.py` → [module]
- **Transitive internal**:
  - `banned_content.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `bootstrap.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `candidate.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `config.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `config_passion.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `contracts.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `marketplace_subcategory.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `passion_detector.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `passion_insight_generator.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `passion_models.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `passion_utils.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `pipeline_result.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `schema.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pytest` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `_set_test_env` (function)
- `_reset_pipeline_initialized` (function)
- `_reset_dev_secret` (function)
- `real_startup_env` (function)

#### Side Effects
network calls

---

### `tests/run_smoke.py`

#### Dependencies
- **Direct internal**:
  - `pipeline.py` → [run_pipeline, PipelineResult]
- **Transitive internal**:
  - `anomaly_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `banned_content.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `bootstrap.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `candidate.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `categorization_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `config.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `config_passion.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `contracts.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `expected_spend_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `feature_engineer.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `known_persons.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `log_utils.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `marketplace_subcategory.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `model_state.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_models.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_pipeline.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_utils.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `pipeline_result.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `preprocessor.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `recurring_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `schema.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `seed_labeler.py` (via `pipeline.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `CSV_PATH` (constant)

#### Side Effects
file I/O (open/print), file I/O

---

### `tests/run_stress_heavy.py`

#### Dependencies
- **Direct internal**:
  - `pipeline.py` → [run_pipeline]
- **Transitive internal**:
  - `anomaly_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `banned_content.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `bootstrap.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `candidate.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `categorization_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `config.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `config_passion.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `contracts.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `expected_spend_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `feature_engineer.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `known_persons.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `log_utils.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `marketplace_subcategory.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `model_state.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_models.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_pipeline.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_utils.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `pipeline_result.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `preprocessor.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `recurring_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `schema.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `seed_labeler.py` (via `pipeline.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `generate_stress_data` (function)

#### Side Effects
file I/O (open/print), file I/O

---
