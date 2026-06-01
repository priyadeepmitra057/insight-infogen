*(Part 3 of 4 - split due to length)*


### `tests/run_stress_legacy.py`

#### Dependencies
- **Direct internal**:
  - `pipeline.py` → [run_pipeline]
  - `schema.py` → [Col]
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
  - `seed_labeler.py` (via `pipeline.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
  - `psutil` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `generate_large_dataset` (function)
- `run_stress_test` (function)

#### Side Effects
file I/O (open/print), file I/O

---

### `tests/run_tests_legacy.py`

#### Dependencies
- **Direct internal**:
  - `tests/test_phase1.py` → [*]
  - `tests/test_phase2.py` → [test_spend_model_training_and_prediction, test_categorization_training_and_prediction]
- **Transitive internal**:
  - `categorization_model.py` (via `tests/test_phase2.py`) → [module/symbols used indirectly]
  - `config.py` (via `tests/test_phase2.py`) → [module/symbols used indirectly]
  - `expected_spend_model.py` (via `tests/test_phase2.py`) → [module/symbols used indirectly]
  - `feature_engineer.py` (via `tests/test_phase1.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `tests/test_phase2.py`) → [module/symbols used indirectly]
  - `preprocessor.py` (via `tests/test_phase1.py`) → [module/symbols used indirectly]
  - `schema.py` (via `tests/test_phase2.py`) → [module/symbols used indirectly]
  - `seed_labeler.py` (via `tests/test_phase1.py`) → [module/symbols used indirectly]
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
  - `config.py` → [INSIGHT_TYPES, TIP_CORPUS]
  - `training_data_generator.py` → [_find_best_tip, _generate_base_features, generate_insight_dataset, ALL_CATEGORIES]
- **Transitive internal**:
  - `contracts.py` (via `training_data_generator.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
  - `pytest` → [module]
  - `sklearn` → [Pipeline, StandardScaler, OneHotEncoder, LogisticRegression, ColumnTransformer]
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
network calls, file I/O

---

### `tests/test_e2e.py`

#### Dependencies
- **Direct internal**:
  - `anomaly_detector.py` → [detect_anomalies]
  - `categorization_model.py` → [predict_categories, train_categorization_model]
  - `expected_spend_model.py` → [predict_expected_spend, train_expected_spend_model]
  - `feature_engineer.py` → [engineer_features_inference, fill_rolling_nulls, engineer_features]
  - `insight_generator.py` → [generate_human_insights]
  - `model_state.py` → [InsightModelState]
  - `pipeline.py` → [run_pipeline, run_inference]
  - `preprocessor.py` → [preprocess]
  - `recurring_detector.py` → [find_recurring_transactions]
  - `schema.py` → [Col]
  - `seed_labeler.py` → [label_credits, label_debits]
- **Transitive internal**:
  - `banned_content.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `bootstrap.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `candidate.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `config.py` (via `preprocessor.py`) → [module/symbols used indirectly]
  - `config_passion.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `contracts.py` (via `insight_generator.py`) → [module/symbols used indirectly]
  - `insight_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `known_persons.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `log_utils.py` (via `recurring_detector.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `preprocessor.py`) → [module/symbols used indirectly]
  - `marketplace_subcategory.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_models.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_pipeline.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_utils.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `pipeline_result.py` (via `pipeline.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `test_run_e2e_test` (function)
- `test_run_inference_uses_history_features` (function)

#### Side Effects
file I/O (open/print), file I/O

---

### `tests/test_logging_safety.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [module]
  - `log_utils.py` → [log_safe_merchant]
  - `logger_factory.py` → [module]
  - `pipeline.py` → [run_pipeline, generate_new_run_id]
  - `recurring_detector.py` → [find_recurring_transactions]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `anomaly_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `banned_content.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `bootstrap.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `candidate.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `categorization_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `config_passion.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `contracts.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `expected_spend_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `feature_engineer.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `known_persons.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `marketplace_subcategory.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `model_state.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_models.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_pipeline.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_utils.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `pipeline_result.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `preprocessor.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `seed_labeler.py` (via `pipeline.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pandas` → [module]
  - `pytest` → [module]
- **Runtime / injected deps**: config

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
file I/O (open/print), network calls, file I/O

---

### `tests/test_ml_integration.py`

#### Dependencies
- **Direct internal**:
  - `insight_model.py` → [predict_insight_scores, load_insight_ranker]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `config.py` (via `insight_model.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `insight_model.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pandas` → [module]
  - `pytest` → [module]
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
file I/O

---

### `tests/test_model_security.py`

#### Dependencies
- **Direct internal**:
  - `insight_model.py` → [load_insight_ranker, module, _MODELS_DIR, ModelSecurityError, _verify_checksum, _validate_model_path, _compute_checksum]
- **Transitive internal**:
  - `config.py` (via `insight_model.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `insight_model.py`) → [module/symbols used indirectly]
  - `schema.py` (via `insight_model.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pytest` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: TEST
- **Purpose**: Test suite or testing script.

#### Exports
- `tmp_models_dir` (function)
- `TestChecksumComputation` (class)
- `TestChecksumVerification` (class)
- `TestPathValidation` (class)
- `TestLoadInsightRanker` (class)

#### Side Effects
file I/O (open/print)

---

### `tests/test_passion_engine.py`

#### Dependencies
- **Direct internal**:
  - `banned_content.py` → [module, contains_banned_content]
  - `bootstrap.py` → [validate_template_fields, _validate_schema_columns, _dry_render_templates, module, _validate_tip_corpus]
  - `candidate.py` → [module, Candidate]
  - `config.py` → [module]
  - `config_passion.py` → [GENERALIST_CANONICALS, module, PASSION_MERCHANT_ALIASES, validate_merchant_aliases]
  - `contracts.py` → [module, _freeze_tip_corpus, lookup_matching_tip_ids]
  - `hash_utils.py` → [stable_hash]
  - `log_utils.py` → [log_safe_text, verify_merchant_token, _reset_secret_cache, log_safe_merchant, module, _get_secret]
  - `marketplace_subcategory.py` → [module, enrich_subcategories, resolve_merchant_vectorized]
  - `passion_detector.py` → [_is_non_declining, module, detect_passions, _check_distress_gate, _check_anomaly_suppression]
  - `passion_insight_generator.py` → [module, generate_passion_insights]
  - `passion_models.py` → [module, PassionSignal]
  - `passion_pipeline.py` → [_neutral_passion_result, safe_assign_new_columns, process_pipeline, _normalize_ts, _StepBudgetGuard, module]
  - `passion_utils.py` → [validate_template_values, safe_last_nonnull, sanitize_mask, safe_numeric, _safe_isna, module, coerce_bool_column, to_bool_strict]
  - `pipeline.py` → [_write_crash_dumps, module, PipelineResult]
  - `pipeline_result.py` → [module, PassionResult]
  - `schema.py` → [module, Col]
- **Transitive internal**:
  - `anomaly_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `categorization_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `expected_spend_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `feature_engineer.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `known_persons.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `passion_pipeline.py`) → [module/symbols used indirectly]
  - `model_state.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `preprocessor.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `recurring_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `seed_labeler.py` (via `pipeline.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
  - `pytest` → [module]
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
file I/O (open/print), network calls, file I/O

---

### `tests/test_phase1.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [CREDIT_PRIORITY, CREDIT_KEYWORDS, CATEGORY_KEYWORDS, CATEGORY_PRIORITY, FALLBACK_DEBIT_LABEL, FALLBACK_CREDIT_LABEL]
  - `feature_engineer.py` → [add_rolling_features, engineer_features, fill_rolling_nulls, add_time_features, engineer_features_inference, add_amount_features]
  - `preprocessor.py` → [clean_remark, _compute_signed_amount, preprocess, _normalize_flag, _drop_zero_amount, _deduplicate, validate_schema]
  - `schema.py` → [Col]
  - `seed_labeler.py` → [label_credits, _match_remark, _compile_keywords, label_debits]
- **Transitive internal**:
  - `logger_factory.py` (via `schema.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
  - `pytest` → [module]
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
file I/O

---

### `tests/test_phase2.py`

#### Dependencies
- **Direct internal**:
  - `categorization_model.py` → [predict_categories, train_categorization_model]
  - `expected_spend_model.py` → [predict_expected_spend, train_expected_spend_model]
- **Transitive internal**:
  - `config.py` (via `categorization_model.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `categorization_model.py`) → [module/symbols used indirectly]
  - `schema.py` (via `categorization_model.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
  - `pytest` → [module]
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
file I/O

---

### `tests/test_phase3.py`

#### Dependencies
- **Direct internal**:
  - `anomaly_detector.py` → [detect_anomalies]
  - `insight_generator.py` → [_select_tip, generate_human_insights]
  - `pipeline.py` → [PipelineResult]
  - `recurring_detector.py` → [find_recurring_transactions]
- **Transitive internal**:
  - `banned_content.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `bootstrap.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `candidate.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `categorization_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `config.py` (via `anomaly_detector.py`) → [module/symbols used indirectly]
  - `config_passion.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `contracts.py` (via `insight_generator.py`) → [module/symbols used indirectly]
  - `expected_spend_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `feature_engineer.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `insight_model.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `known_persons.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `log_utils.py` (via `recurring_detector.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `anomaly_detector.py`) → [module/symbols used indirectly]
  - `marketplace_subcategory.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `model_state.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_detector.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_insight_generator.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_models.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_pipeline.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `passion_utils.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `pipeline_result.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `preprocessor.py` (via `pipeline.py`) → [module/symbols used indirectly]
  - `schema.py` (via `anomaly_detector.py`) → [module/symbols used indirectly]
  - `seed_labeler.py` (via `pipeline.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pandas` → [module]
  - `pytest` → [module]
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
file I/O

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
- **Purpose**: Provides reusable helper functions or utilities.

#### Exports
- `__all__` (constant)
- `stable_hash` (function)

#### Side Effects
none

---

### `log_utils.py`

#### Dependencies
- **Direct internal**:
  - `logger_factory.py` → [get_logger]
- **Transitive internal**:
  - `config.py` (via `logger_factory.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: UTILITY
- **Purpose**: Provides reusable helper functions or utilities.

#### Exports
- `__all__` (constant)
- `_DEV_SECRET_FALLBACK` (constant)
- `_reset_secret_cache` (function)
- `_get_secret` (function)
- `_hmac_hex` (function)
- `_is_safe_scalar` (function)
- `log_safe_merchant` (function)
- `log_safe_text` (function)
- `verify_merchant_token` (function)

#### Side Effects
network calls, file I/O

---

### `logger_factory.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [module]
- **Transitive internal**:
  - none
- **Direct external**:
  - none
- **Runtime / injected deps**: none

#### Identity
- **Role**: UTILITY
- **Purpose**: Provides reusable helper functions or utilities.

#### Exports
- `generate_new_run_id` (function)
- `JSONFormatter` (class)
- `get_logger` (function)

#### Side Effects
network calls

---
