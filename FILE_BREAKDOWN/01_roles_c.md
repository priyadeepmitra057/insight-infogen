*(Part 3 of 4 - split due to length)*


### `tests/run_stress_heavy.py`

#### Dependencies
- **Direct internal**:
  - `pipeline.py` → [run_pipeline]
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
  - `pandas` → [*]
  - `numpy` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `generate_stress_data` (function)

#### Side Effects
file I/O (open/print)

---

### `tests/run_stress_legacy.py`

#### Dependencies
- **Direct internal**:
  - `pipeline.py` → [run_pipeline]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `logger_factory.py` (via `pipeline.py`)
  - `config.py` (via `pipeline.py`)
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
  - `psutil` → [*]
  - `gc` → [*]
  - `numpy` → [*]
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `generate_large_dataset` (function)
- `run_stress_test` (function)

#### Side Effects
file I/O (open/print)

---

### `tests/run_tests_legacy.py`

#### Dependencies
- **Direct internal**:
  - `tests/test_phase2.py` → [test_spend_model_training_and_prediction, test_categorization_training_and_prediction]
  - `tests/test_phase1.py` → [*]
- **Transitive internal**:
  - `categorization_model.py` (via `tests/test_phase2.py`)
  - `config.py` (via `tests/test_phase2.py`)
  - `schema.py` (via `tests/test_phase2.py`)
  - `logger_factory.py` (via `tests/test_phase2.py`)
  - `expected_spend_model.py` (via `tests/test_phase2.py`)
  - `preprocessor.py` (via `tests/test_phase1.py`)
  - `feature_engineer.py` (via `tests/test_phase1.py`)
  - `seed_labeler.py` (via `tests/test_phase1.py`)
- **Direct external**:
  - none
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- none

#### Side Effects
file I/O (open/print)

---

### `tests/test_benchmark.py`

#### Dependencies
- **Direct internal**:
  - `training_data_generator.py` → [_find_best_tip, _generate_base_features, generate_insight_dataset, ALL_CATEGORIES]
  - `config.py` → [TIP_CORPUS, INSIGHT_TYPES]
- **Transitive internal**:
  - `contracts.py` (via `training_data_generator.py`)
- **Direct external**:
  - `numpy` → [*]
  - `pandas` → [*]
  - `pytest` → [*]
  - `sklearn` → [Pipeline, LogisticRegression, ColumnTransformer, OneHotEncoder, StandardScaler]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `dataset` (function)
- `test_data_generator_shape` (function)
- `test_no_nan_in_features` (function)
- `test_no_nan_in_labels` (function)
- `test_data_generator_distribution` (function)
- `test_all_insight_types_present` (function)
- `test_categories_are_valid` (function)
- `test_spikes_have_high_zscore` (function)
- `test_subscriptions_have_recurring_flag` (function)
- `test_no_action_has_benign_features` (function)
- `test_no_action_has_no_tip` (function)
- `test_actionable_insights_have_tips` (function)
- `test_tip_ids_are_valid` (function)
- `test_find_best_tip_category_specific` (function)
- `test_find_best_tip_generic_fallback` (function)
- `test_find_best_tip_no_match` (function)
- `test_amounts_are_positive` (function)
- `test_rolling_std_no_zero` (function)
- `test_model_can_train_and_predict` (function)

#### Side Effects
network calls

---

### `tests/test_e2e.py`

#### Dependencies
- **Direct internal**:
  - `preprocessor.py` → [preprocess]
  - `feature_engineer.py` → [engineer_features_inference, fill_rolling_nulls, engineer_features]
  - `seed_labeler.py` → [label_credits, label_debits]
  - `categorization_model.py` → [predict_categories, train_categorization_model]
  - `expected_spend_model.py` → [predict_expected_spend, train_expected_spend_model]
  - `anomaly_detector.py` → [detect_anomalies]
  - `recurring_detector.py` → [find_recurring_transactions]
  - `insight_generator.py` → [generate_human_insights]
  - `pipeline.py` → [run_pipeline, run_inference]
  - `schema.py` → [Col]
  - `model_state.py` → [InsightModelState]
- **Transitive internal**:
  - `config.py` (via `preprocessor.py`)
  - `logger_factory.py` (via `preprocessor.py`)
  - `log_utils.py` (via `recurring_detector.py`)
  - `contracts.py` (via `insight_generator.py`)
  - `insight_model.py` (via `pipeline.py`)
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
  - `numpy` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `test_run_e2e_test` (function)
- `test_run_inference_uses_history_features` (function)

#### Side Effects
file I/O (open/print)

---

### `tests/test_logging_safety.py`

#### Dependencies
- **Direct internal**:
  - `pipeline.py` → [run_pipeline, generate_new_run_id]
  - `recurring_detector.py` → [find_recurring_transactions]
  - `config.py` → [*]
  - `logger_factory.py` → [*]
  - `log_utils.py` → [log_safe_merchant]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `model_state.py` (via `pipeline.py`)
  - `preprocessor.py` (via `pipeline.py`)
  - `feature_engineer.py` (via `pipeline.py`)
  - `seed_labeler.py` (via `pipeline.py`)
  - `categorization_model.py` (via `pipeline.py`)
  - `expected_spend_model.py` (via `pipeline.py`)
  - `anomaly_detector.py` (via `pipeline.py`)
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
  - `pytest` → [*]
  - `pandas` → [*]
- **Runtime / injected deps**: internal: config.py

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `valid_debits_df` (function)
- `valid_credits_df` (function)
- `raw_df` (function)
- `test_crash_dump_created` (function)
- `test_crash_exception_identity_matching` (function)
- `test_crash_dump_failure_safety` (function)
- `test_invalid_log_level` (function)
- `test_pii_redaction_coverage` (function)

#### Side Effects
file I/O (open/print), network calls

---

### `tests/test_ml_integration.py`

#### Dependencies
- **Direct internal**:
  - `insight_model.py` → [load_insight_ranker, predict_insight_scores]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `logger_factory.py` (via `insight_model.py`)
  - `config.py` (via `insight_model.py`)
- **Direct external**:
  - `pandas` → [*]
  - `pytest` → [*]
  - `sklearn` → [Pipeline]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `mock_df` (function)
- `test_load_insight_ranker` (function)
- `test_predict_insight_scores` (function)
- `test_predict_insight_scores_graceful_fallback` (function)

#### Side Effects
none

---

### `tests/test_passion_engine.py`

#### Dependencies
- **Direct internal**:
  - `passion_pipeline.py` → [*, _StepBudgetGuard, _neutral_passion_result, process_pipeline, _normalize_ts, safe_assign_new_columns]
  - `passion_utils.py` → [sanitize_mask, _safe_isna, *, safe_numeric, to_bool_strict, coerce_bool_column, safe_last_nonnull, validate_template_values]
  - `pipeline_result.py` → [PassionResult, *]
  - `log_utils.py` → [verify_merchant_token, *, log_safe_merchant, _reset_secret_cache, _get_secret, log_safe_text]
  - `passion_detector.py` → [_check_anomaly_suppression, *, _check_distress_gate, _is_non_declining, detect_passions]
  - `config_passion.py` → [*, PASSION_MERCHANT_ALIASES, validate_merchant_aliases, GENERALIST_CANONICALS]
  - `passion_insight_generator.py` → [*, generate_passion_insights]
  - `marketplace_subcategory.py` → [*, resolve_merchant_vectorized, enrich_subcategories]
  - `banned_content.py` → [*, contains_banned_content]
  - `pipeline.py` → [*, _write_crash_dumps, PipelineResult]
  - `schema.py` → [*, Col]
  - `passion_models.py` → [*, PassionSignal]
  - `bootstrap.py` → [*, _validate_tip_corpus, validate_template_fields, _dry_render_templates, _validate_schema_columns]
  - `contracts.py` → [_freeze_tip_corpus, *, lookup_matching_tip_ids]
  - `candidate.py` → [*, Candidate]
  - `config.py` → [*]
  - `hash_utils.py` → [stable_hash]
- **Transitive internal**:
  - `logger_factory.py` (via `passion_pipeline.py`)
  - `model_state.py` (via `pipeline.py`)
  - `preprocessor.py` (via `pipeline.py`)
  - `feature_engineer.py` (via `pipeline.py`)
  - `seed_labeler.py` (via `pipeline.py`)
  - `categorization_model.py` (via `pipeline.py`)
  - `expected_spend_model.py` (via `pipeline.py`)
  - `anomaly_detector.py` (via `pipeline.py`)
  - `recurring_detector.py` (via `pipeline.py`)
  - `insight_model.py` (via `pipeline.py`)
  - `insight_generator.py` (via `pipeline.py`)
  - `known_persons.py` (via `pipeline.py`)
- **Direct external**:
  - `pytest` → [*]
  - `pandas` → [*]
  - `numpy` → [*]
  - `inspect` → [*]
  - `types` → [MappingProxyType]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `make_pipeline_result` (function)
- `TestBoolCoercion` (class)
- `TestSanitizeMask` (class)
- `TestNormalizeTs` (class)
- `TestStepBudgetGuard` (class)
- `TestConfigPassion` (class)
- `TestLogUtils` (class)
- `TestBannedContent` (class)
- `TestDistressGate` (class)
- `TestMerchantVectorizer` (class)
- `TestMarketplaceSubcategory` (class)
- `TestIsNonDeclining` (class)
- `TestEnrichSubcategories` (class)
- `TestAnomalySuppression` (class)
- `TestDetectPassions` (class)
- `TestSuppressedSignals` (class)
- `TestNarrowIndexException` (class)
- `TestPipeline` (class)
- `TestBootstrap` (class)
- `TestUtils` (class)
- `TestPassionSignalValidation` (class)
- `TestCandidateValidation` (class)
- `TestPassionResultRejection` (class)
- `TestThreadSafeInit` (class)
- `TestModuleImports` (class)
- `TestA2TipCorpusImportIsolation` (class)
- `TestA3StableHashProductionBan` (class)
- `TestNeutralPassionResult` (class)
- `TestE3PassionEngineE2EIntegration` (class)
- `TestE4DefensiveCopyIntegrity` (class)
- `TestF1CowSafeResolve` (class)
- `TestF2AliasBoundaryHardening` (class)
- `TestF3SecretCachingBehavior` (class)
- `TestF4MemoryPerformanceBenchmark` (class)
- `TestF5CrashDumpWithPassion` (class)
- `TestF6UnexpectedColumnsStrictMode` (class)
- `TestConfigPassionCanonicals` (class)

#### Side Effects
file I/O (open/print), network calls

---

### `tests/test_phase1.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col]
  - `preprocessor.py` → [_drop_zero_amount, clean_remark, _compute_signed_amount, preprocess, validate_schema, _deduplicate, _normalize_flag]
  - `feature_engineer.py` → [add_rolling_features, engineer_features_inference, add_time_features, add_amount_features, fill_rolling_nulls, engineer_features]
  - `seed_labeler.py` → [label_credits, _compile_keywords, _match_remark, label_debits]
  - `config.py` → [CATEGORY_KEYWORDS, CATEGORY_PRIORITY, CREDIT_KEYWORDS, FALLBACK_CREDIT_LABEL, CREDIT_PRIORITY, FALLBACK_DEBIT_LABEL]
- **Transitive internal**:
  - `logger_factory.py` (via `schema.py`)
- **Direct external**:
  - `numpy` → [*]
  - `pandas` → [*]
  - `pytest` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `_make_df` (function)
- `_make_debit_df_with_remarks` (function)
- `TestValidateSchema` (class)
- `TestNormalizeFlag` (class)
- `TestComputeSignedAmount` (class)
- `TestCleanRemark` (class)
- `TestDropZeroAmount` (class)
- `TestDeduplicate` (class)
- `TestPreprocess` (class)
- `_base_fe_df` (function)
- `TestTimeFeatures` (class)
- `TestRollingFeatures` (class)
- `TestFillRollingNulls` (class)
- `TestAmountFeatures` (class)
- `TestEngineerFeaturesFull` (class)
- `TestMatchRemark` (class)
- `TestLabelDebits` (class)
- `TestLabelCredits` (class)
- `TestInferenceFeatures` (class)

#### Side Effects
none

---

### `tests/test_phase2.py`

#### Dependencies
- **Direct internal**:
  - `categorization_model.py` → [predict_categories, train_categorization_model]
  - `expected_spend_model.py` → [predict_expected_spend, train_expected_spend_model]
- **Transitive internal**:
  - `config.py` (via `categorization_model.py`)
  - `schema.py` (via `categorization_model.py`)
  - `logger_factory.py` (via `categorization_model.py`)
- **Direct external**:
  - `pandas` → [*]
  - `pytest` → [*]
  - `numpy` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `test_categorization_training_and_prediction` (function)
- `test_spend_model_training_and_prediction` (function)
- `test_expected_spend_model_extrapolates` (function)
- `test_percent_deviation_no_inf` (function)
- `test_percent_deviation_negative_expected_amount` (function)
- `test_percent_deviation_zero_expected_amount` (function)
- `test_percent_deviation_normal_case` (function)

#### Side Effects
none

---

### `tests/test_phase3.py`

#### Dependencies
- **Direct internal**:
  - `anomaly_detector.py` → [detect_anomalies]
  - `recurring_detector.py` → [find_recurring_transactions]
  - `insight_generator.py` → [_select_tip, generate_human_insights]
  - `pipeline.py` → [PipelineResult]
- **Transitive internal**:
  - `schema.py` (via `anomaly_detector.py`)
  - `logger_factory.py` (via `anomaly_detector.py`)
  - `config.py` (via `anomaly_detector.py`)
  - `log_utils.py` (via `recurring_detector.py`)
  - `contracts.py` (via `insight_generator.py`)
  - `model_state.py` (via `pipeline.py`)
  - `preprocessor.py` (via `pipeline.py`)
  - `feature_engineer.py` (via `pipeline.py`)
  - `seed_labeler.py` (via `pipeline.py`)
  - `categorization_model.py` (via `pipeline.py`)
  - `expected_spend_model.py` (via `pipeline.py`)
  - `insight_model.py` (via `pipeline.py`)
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
  - `pytest` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `test_recurring_detector` (function)
- `test_recurring_frequency_none_for_non_recurring` (function)
- `test_recurring_requires_minimum_3_occurrences` (function)
- `test_biweekly_detection_and_variance_penalty` (function)
- `test_anomaly_composite_threshold` (function)
- `test_missing_anomaly_columns_raises` (function)
- `test_insight_generator_creates_strings` (function)
- `test_insight_generator_deterministic` (function)
- `test_insight_generator_different_seeds` (function)
- `test_select_tip_deterministic` (function)
- `test_pipeline_result_is_frozen` (function)
- `test_pipeline_result_replace` (function)

#### Side Effects
none

---

## UNKNOWN

### `analyzer.py`

#### Dependencies
- **Direct internal**:
  - none
- **Transitive internal**:
  - none
- **Direct external**:
  - `glob` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: UNKNOWN
- **Purpose**: Need to infer purpose.

#### Exports
- `get_all_py_files` (function)
- `AstVisitor` (class)
- `analyze_repo` (function)

#### Side Effects
file I/O (open/print), file I/O

---

## UTILITY

### `hash_utils.py`

#### Dependencies
- **Direct internal**:
  - none
- **Transitive internal**:
  - none
- **Direct external**:
  - none
- **Runtime / injected deps**: none

#### Identity
- **Role**: UTILITY
- **Purpose**: Hashing utilities.

#### Exports
- `__all__` (constant/variable)
- `stable_hash` (function)

#### Side Effects
none

---
