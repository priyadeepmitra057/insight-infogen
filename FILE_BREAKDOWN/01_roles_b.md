*(Part 2 of 4 - split due to length)*


### `seed_labeler.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [CATEGORY_KEYWORDS, CATEGORY_PRIORITY, CREDIT_KEYWORDS, TIER_MAPPING, MIN_COVERAGE_THRESHOLD, FALLBACK_CREDIT_LABEL, CREDIT_PRIORITY, FALLBACK_DEBIT_LABEL]
  - `preprocessor.py` → [normalize]
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `logger_factory.py` (via `preprocessor.py`)
- **Direct external**:
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: DATA_LAYER
- **Purpose**: Labels seed data for training.

#### Exports
- `CompiledKeyword` (class)
- `_compile_keywords` (function)
- `_match_remark` (function)
- `_DEFAULT_DEBIT_KWS` (constant/variable)
- `_DEFAULT_CREDIT_KWS` (constant/variable)
- `_log_coverage` (function)
- `label_debits` (function)
- `label_credits` (function)

#### Side Effects
none

---

### `tests/test_known_persons.py`

#### Dependencies
- **Direct internal**:
  - `known_persons.py` → [tag_known_persons, _extract_signals, _enforce_known_person_schema, _suggestion_key]
  - `pipeline.py` → [run_pipeline, _compute_config_hash, PipelineResult, run_inference]
  - `model_state.py` → [InsightModelState]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `logger_factory.py` (via `known_persons.py`)
  - `config.py` (via `known_persons.py`)
  - `preprocessor.py` (via `pipeline.py`)
  - `feature_engineer.py` (via `pipeline.py`)
  - `seed_labeler.py` (via `pipeline.py`)
  - `categorization_model.py` (via `pipeline.py`)
  - `expected_spend_model.py` (via `pipeline.py`)
  - `anomaly_detector.py` (via `pipeline.py`)
  - `recurring_detector.py` (via `pipeline.py`)
  - `log_utils.py` (via `pipeline.py`)
  - `insight_model.py` (via `pipeline.py`)
  - `insight_generator.py` (via `pipeline.py`)
  - `contracts.py` (via `pipeline.py`)
  - `passion_pipeline.py` (via `pipeline.py`)
  - `config_passion.py` (via `pipeline.py`)
  - `passion_utils.py` (via `pipeline.py`)
  - `candidate.py` (via `pipeline.py`)
  - `passion_models.py` (via `pipeline.py`)
  - `banned_content.py` (via `pipeline.py`)
  - `pipeline_result.py` (via `pipeline.py`)
  - `bootstrap.py` (via `pipeline.py`)
  - `marketplace_subcategory.py` (via `pipeline.py`)
  - `passion_detector.py` (via `pipeline.py`)
  - `passion_insight_generator.py` (via `pipeline.py`)
- **Direct external**:
  - `pytest` → [*]
  - `pandas` → [*]
  - `numpy` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: DATA_LAYER
- **Purpose**: Manages data for known persons or entities.

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
none

---

## ENTRYPOINT

### `bootstrap.py`

#### Dependencies
- **Direct internal**:
  - `contracts.py` → [TIP_CORPUS, INSIGHT_TEMPLATES]
  - `logger_factory.py` → [get_logger]
  - `schema.py` → [Col]
  - `config_passion.py` → [validate_config, PASSION_INSIGHT_TEMPLATES, validate_merchant_aliases]
  - `log_utils.py` → [_get_secret]
- **Transitive internal**:
  - `config.py` (via `contracts.py`)
- **Direct external**:
  - `types` → [MappingProxyType]
- **Runtime / injected deps**: none

#### Identity
- **Role**: ENTRYPOINT
- **Purpose**: Initializes and bootstraps application environments or models.

#### Exports
- `__all__` (constant/variable)
- `ALLOWED_FORMAT_SPECS` (constant/variable)
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
  - `schema.py` → [Col]
  - `pipeline.py` → [run_pipeline]
  - `summary_utils.py` → [print_summary]
- **Transitive internal**:
  - `logger_factory.py` (via `schema.py`)
  - `config.py` (via `schema.py`)
  - `model_state.py` (via `pipeline.py`)
  - `preprocessor.py` (via `pipeline.py`)
  - `feature_engineer.py` (via `pipeline.py`)
  - `seed_labeler.py` (via `pipeline.py`)
  - `categorization_model.py` (via `pipeline.py`)
  - `expected_spend_model.py` (via `pipeline.py`)
  - `anomaly_detector.py` (via `pipeline.py`)
  - `recurring_detector.py` (via `pipeline.py`)
  - `log_utils.py` (via `pipeline.py`)
  - `insight_model.py` (via `pipeline.py`)
  - `insight_generator.py` (via `pipeline.py`)
  - `contracts.py` (via `pipeline.py`)
  - `known_persons.py` (via `pipeline.py`)
  - `passion_pipeline.py` (via `pipeline.py`)
  - `config_passion.py` (via `pipeline.py`)
  - `passion_utils.py` (via `pipeline.py`)
  - `candidate.py` (via `pipeline.py`)
  - `passion_models.py` (via `pipeline.py`)
  - `banned_content.py` (via `pipeline.py`)
  - `pipeline_result.py` (via `pipeline.py`)
  - `bootstrap.py` (via `pipeline.py`)
  - `marketplace_subcategory.py` (via `pipeline.py`)
  - `passion_detector.py` (via `pipeline.py`)
  - `passion_insight_generator.py` (via `pipeline.py`)
- **Direct external**:
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: ENTRYPOINT
- **Purpose**: Runs a demo of the pipeline.

#### Exports
- none

#### Side Effects
file I/O (open/print), network calls

---

### `passion_pipeline.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col]
  - `config_passion.py` → [MAX_SPIKE_CANDIDATES, PIPELINE_TOP_N, PIPELINE_BUDGET_MS, PASSION_MIN_DEBIT_ROWS, PIPELINE_HARD_TIMEOUT_MS]
  - `passion_utils.py` → [assert_columns_exist, coerce_bool_column, safe_numeric, _safe_isna]
  - `candidate.py` → [Candidate]
  - `banned_content.py` → [contains_banned_content]
  - `logger_factory.py` → [get_logger]
  - `pipeline_result.py` → [PassionResult]
  - `bootstrap.py` → [run_startup_checks]
  - `marketplace_subcategory.py` → [resolve_merchant_vectorized, enrich_subcategories]
  - `passion_detector.py` → [detect_passions]
  - `passion_insight_generator.py` → [generate_passion_insights]
- **Transitive internal**:
  - `config.py` (via `schema.py`)
  - `passion_models.py` (via `candidate.py`)
  - `contracts.py` (via `bootstrap.py`)
  - `log_utils.py` (via `bootstrap.py`)
- **Direct external**:
  - `pandas` → [*]
  - `numpy` → [*]
  - `numbers` → [Real, Integral]
- **Runtime / injected deps**: none

#### Identity
- **Role**: ENTRYPOINT
- **Purpose**: Orchestrator for the passion insights feature.

#### Exports
- `__all__` (constant/variable)
- `_PERMANENT_STARTUP_ERRORS` (constant/variable)
- `_neutral_passion_result` (function)
- `_ensure_initialized` (function)
- `_FATAL_EXCEPTIONS` (constant/variable)
- `_should_reraise` (function)
- `PASSION_OWNED_OUTPUT_COLUMNS` (constant/variable)
- `safe_assign_new_columns` (function)
- `_looks_like_compact_yyyymmdd` (function)
- `_normalize_ts` (function)
- `_CURRENCY_RE_LOCAL` (constant/variable)
- `_INR_RE_LOCAL` (constant/variable)
- `_is_unparseable_amount` (function)
- `_StepBudgetGuard` (class)
- `process_pipeline` (function)

#### Side Effects
network calls

---

### `pipeline.py`

#### Dependencies
- **Direct internal**:
  - `logger_factory.py` → [pipeline_run_id_ctx, get_logger, generate_new_run_id]
  - `model_state.py` → [InsightModelState]
  - `config.py` → [*]
  - `schema.py` → [Col]
  - `preprocessor.py` → [preprocess]
  - `feature_engineer.py` → [engineer_features_inference, engineer_features]
  - `seed_labeler.py` → [label_credits, label_debits]
  - `categorization_model.py` → [predict_categories, train_categorization_model]
  - `expected_spend_model.py` → [predict_expected_spend, train_expected_spend_model]
  - `anomaly_detector.py` → [detect_anomalies]
  - `recurring_detector.py` → [find_recurring_transactions]
  - `insight_model.py` → [load_insight_ranker, predict_insight_scores]
  - `insight_generator.py` → [generate_human_insights]
  - `known_persons.py` → [tag_known_persons, detect_personal_patterns, _enforce_known_person_schema, log_unmatched_recurring_transfers]
  - `log_utils.py` → [log_safe_merchant, log_safe_text]
  - `passion_pipeline.py` → [process_pipeline]
- **Transitive internal**:
  - `contracts.py` (via `insight_generator.py`)
  - `config_passion.py` (via `passion_pipeline.py`)
  - `passion_utils.py` (via `passion_pipeline.py`)
  - `candidate.py` (via `passion_pipeline.py`)
  - `passion_models.py` (via `passion_pipeline.py`)
  - `banned_content.py` (via `passion_pipeline.py`)
  - `pipeline_result.py` (via `passion_pipeline.py`)
  - `bootstrap.py` (via `passion_pipeline.py`)
  - `marketplace_subcategory.py` (via `passion_pipeline.py`)
  - `passion_detector.py` (via `passion_pipeline.py`)
  - `passion_insight_generator.py` (via `passion_pipeline.py`)
- **Direct external**:
  - `pandas` → [*]
  - `sklearn` → [Pipeline]
  - `numpy` → [*]
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
file I/O (open/print), network calls

---

### `train_and_save_models.py`

#### Dependencies
- **Direct internal**:
  - `training_data_generator.py` → [generate_insight_dataset]
  - `insight_model.py` → [_compute_checksum]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `config.py` (via `training_data_generator.py`)
  - `contracts.py` (via `training_data_generator.py`)
  - `logger_factory.py` (via `insight_model.py`)
- **Direct external**:
  - `lightgbm` → [LGBMClassifier]
  - `sklearn` → [ColumnTransformer, OneHotEncoder, StandardScaler, Pipeline]
- **Runtime / injected deps**: none

#### Identity
- **Role**: ENTRYPOINT
- **Purpose**: Script to train and save machine learning models.

#### Exports
- `NUMERIC_FEATURES` (constant/variable)
- `CATEGORICAL_FEATURES` (constant/variable)
- `train_and_save` (function)

#### Side Effects
file I/O (open/print), file I/O

---

### `tutorial_real_data.py`

#### Dependencies
- **Direct internal**:
  - `logger_factory.py` → [get_logger]
  - `schema.py` → [Col]
  - `pipeline.py` → [run_pipeline]
- **Transitive internal**:
  - `config.py` (via `logger_factory.py`)
  - `model_state.py` (via `pipeline.py`)
  - `preprocessor.py` (via `pipeline.py`)
  - `feature_engineer.py` (via `pipeline.py`)
  - `seed_labeler.py` (via `pipeline.py`)
  - `categorization_model.py` (via `pipeline.py`)
  - `expected_spend_model.py` (via `pipeline.py`)
  - `anomaly_detector.py` (via `pipeline.py`)
  - `recurring_detector.py` (via `pipeline.py`)
  - `log_utils.py` (via `pipeline.py`)
  - `insight_model.py` (via `pipeline.py`)
  - `insight_generator.py` (via `pipeline.py`)
  - `contracts.py` (via `pipeline.py`)
  - `known_persons.py` (via `pipeline.py`)
  - `passion_pipeline.py` (via `pipeline.py`)
  - `config_passion.py` (via `pipeline.py`)
  - `passion_utils.py` (via `pipeline.py`)
  - `candidate.py` (via `pipeline.py`)
  - `passion_models.py` (via `pipeline.py`)
  - `banned_content.py` (via `pipeline.py`)
  - `pipeline_result.py` (via `pipeline.py`)
  - `bootstrap.py` (via `pipeline.py`)
  - `marketplace_subcategory.py` (via `pipeline.py`)
  - `passion_detector.py` (via `pipeline.py`)
  - `passion_insight_generator.py` (via `pipeline.py`)
- **Direct external**:
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: ENTRYPOINT
- **Purpose**: Demonstrates ingesting real bank statements.

#### Exports
- `run_real_data_tutorial` (function)

#### Side Effects
file I/O (open/print)

---

## SCHEMA

### `candidate.py`

#### Dependencies
- **Direct internal**:
  - `passion_models.py` → [PassionSignal]
- **Transitive internal**:
  - none
- **Direct external**:
  - `__future__` → [annotations]
  - `numpy` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: SCHEMA
- **Purpose**: Defines data schemas, types, classes, or domain models.

#### Exports
- `__all__` (constant/variable)
- `_coerce_finite_float` (function)
- `Candidate` (class)

#### Side Effects
network calls

---

### `contracts.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [TIP_CORPUS, INSIGHT_TEMPLATES]
- **Transitive internal**:
  - none
- **Direct external**:
  - `types` → [MappingProxyType]
- **Runtime / injected deps**: none

#### Identity
- **Role**: SCHEMA
- **Purpose**: Defines data schemas, types, classes, or domain models.

#### Exports
- `_GENERIC_TIP_PREFIX` (constant/variable)
- `_is_generic_tip_id` (function)
- `_freeze_insight_templates` (function)
- `_freeze_tip_corpus` (function)
- `INSIGHT_TEMPLATES` (constant/variable)
- `TIP_CORPUS` (constant/variable)
- `lookup_matching_tip_ids` (function)
- `__all__` (constant/variable)

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
  - `joblib` → [*]
  - `numpy` → [*]
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
  - `__future__` → [annotations]
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: SCHEMA
- **Purpose**: Defines data schemas, types, classes, or domain models.

#### Exports
- `__all__` (constant/variable)
- `PassionResult` (class)

#### Side Effects
none

---

### `schema.py`

#### Dependencies
- **Direct internal**:
  - `logger_factory.py` → [get_logger]
- **Transitive internal**:
  - `config.py` (via `logger_factory.py`)
- **Direct external**:
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: SCHEMA
- **Purpose**: Defines data schemas, types, classes, or domain models.

#### Exports
- `Col` (class)
- `require_columns` (function)
- `coerce_and_validate_types` (function)

#### Side Effects
none

---

## TEST

### `tests/conftest.py`

#### Dependencies
- **Direct internal**:
  - `passion_pipeline.py` → [*]
  - `log_utils.py` → [_reset_secret_cache]
- **Transitive internal**:
  - `schema.py` (via `passion_pipeline.py`)
  - `logger_factory.py` (via `passion_pipeline.py`)
  - `config.py` (via `passion_pipeline.py`)
  - `config_passion.py` (via `passion_pipeline.py`)
  - `passion_utils.py` (via `passion_pipeline.py`)
  - `candidate.py` (via `passion_pipeline.py`)
  - `passion_models.py` (via `passion_pipeline.py`)
  - `banned_content.py` (via `passion_pipeline.py`)
  - `pipeline_result.py` (via `passion_pipeline.py`)
  - `bootstrap.py` (via `passion_pipeline.py`)
  - `contracts.py` (via `passion_pipeline.py`)
  - `marketplace_subcategory.py` (via `passion_pipeline.py`)
  - `passion_detector.py` (via `passion_pipeline.py`)
  - `passion_insight_generator.py` (via `passion_pipeline.py`)
- **Direct external**:
  - `pytest` → [*]
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
  - `logger_factory.py` (via `pipeline.py`)
  - `config.py` (via `pipeline.py`)
  - `model_state.py` (via `pipeline.py`)
  - `schema.py` (via `pipeline.py`)
  - `preprocessor.py` (via `pipeline.py`)
  - `feature_engineer.py` (via `pipeline.py`)
  - `seed_labeler.py` (via `pipeline.py`)
  - `categorization_model.py` (via `pipeline.py`)
  - `expected_spend_model.py` (via `pipeline.py`)
  - `anomaly_detector.py` (via `pipeline.py`)
  - `recurring_detector.py` (via `pipeline.py`)
  - `log_utils.py` (via `pipeline.py`)
  - `insight_model.py` (via `pipeline.py`)
  - `insight_generator.py` (via `pipeline.py`)
  - `contracts.py` (via `pipeline.py`)
  - `known_persons.py` (via `pipeline.py`)
  - `passion_pipeline.py` (via `pipeline.py`)
  - `config_passion.py` (via `pipeline.py`)
  - `passion_utils.py` (via `pipeline.py`)
  - `candidate.py` (via `pipeline.py`)
  - `passion_models.py` (via `pipeline.py`)
  - `banned_content.py` (via `pipeline.py`)
  - `pipeline_result.py` (via `pipeline.py`)
  - `bootstrap.py` (via `pipeline.py`)
  - `marketplace_subcategory.py` (via `pipeline.py`)
  - `passion_detector.py` (via `pipeline.py`)
  - `passion_insight_generator.py` (via `pipeline.py`)
- **Direct external**:
  - `traceback` → [*]
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `CSV_PATH` (constant/variable)

#### Side Effects
file I/O (open/print)

---
