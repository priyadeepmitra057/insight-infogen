*(Part 1 of 3 - split due to length)*

# Internal Dependency Graph

## Full Direct Import Map
`anomaly_detector.py` → `schema.py` [Col, require_columns]
`bootstrap.py` → `config_passion.py` [validate_config, PASSION_INSIGHT_TEMPLATES, validate_merchant_aliases]
`bootstrap.py` → `contracts.py` [INSIGHT_TEMPLATES, TIP_CORPUS]
`bootstrap.py` → `log_utils.py` [_get_secret]
`bootstrap.py` → `logger_factory.py` [get_logger]
`bootstrap.py` → `schema.py` [Col]
`candidate.py` → `passion_models.py` [PassionSignal]
`categorization_model.py` → `config.py` [FALLBACK_DEBIT_LABEL, FALLBACK_CREDIT_LABEL]
`categorization_model.py` → `schema.py` [Col, require_columns]
`config_passion.py` → `config.py` [SPECIFIC_MERCHANT_ALIASES, CATEGORY_KEYWORDS, CATEGORY_PRIORITY]
`contracts.py` → `config.py` [INSIGHT_TEMPLATES, TIP_CORPUS]
`demo.py` → `pipeline.py` [run_pipeline]
`demo.py` → `schema.py` [Col]
`demo.py` → `summary_utils.py` [print_summary]
`expected_spend_model.py` → `schema.py` [Col, require_columns]
`feature_engineer.py` → `schema.py` [Col, require_columns]
`insight_generator.py` → `contracts.py` [lookup_matching_tip_ids, INSIGHT_TEMPLATES, TIP_CORPUS]
`insight_generator.py` → `schema.py` [Col, require_columns]
`insight_model.py` → `schema.py` [Col, require_columns]
`known_persons.py` → `config.py` [module]
`known_persons.py` → `logger_factory.py` [get_logger]
`known_persons.py` → `schema.py` [Col]
`log_utils.py` → `logger_factory.py` [get_logger]
`logger_factory.py` → `config.py` [module]
`marketplace_subcategory.py` → `config_passion.py` [MARKETPLACE_HIGH_CONFIDENCE, PASSION_MERCHANT_ALIASES, ELECTRONICS_ALLOWED_CATEGORIES, MARKETPLACE_HIGH_AMOUNT_THRESHOLD, MARKETPLACE_LOW_CONFIDENCE, GENERALIST_CANONICALS]
`marketplace_subcategory.py` → `logger_factory.py` [get_logger]
`marketplace_subcategory.py` → `passion_utils.py` [safe_numeric, coerce_bool_column, assert_columns_exist]
`marketplace_subcategory.py` → `schema.py` [Col]
`model_benchmark.py` → `training_data_generator.py` [generate_insight_dataset]
`passion_detector.py` → `config_passion.py` [PASSION_ANOMALY_SUPPRESSION_THRESHOLD, DISTRESS_FEES_THRESHOLD, PASSION_SPEND_SHARE_THRESHOLD, PASSION_MIN_MONTHS, PASSION_MERCHANT_COUNT_MIN]
`passion_detector.py` → `logger_factory.py` [get_logger]
`passion_detector.py` → `marketplace_subcategory.py` [resolve_merchant_vectorized]
`passion_detector.py` → `passion_models.py` [PassionSignal]
`passion_detector.py` → `passion_utils.py` [assert_columns_exist, sanitize_mask, safe_numeric, _safe_isna, coerce_bool_column]
`passion_detector.py` → `schema.py` [Col]
`passion_insight_generator.py` → `banned_content.py` [contains_banned_content]
`passion_insight_generator.py` → `config_passion.py` [PASSION_INSIGHT_TEMPLATES]
`passion_insight_generator.py` → `contracts.py` [lookup_matching_tip_ids, INSIGHT_TEMPLATES, TIP_CORPUS]
`passion_insight_generator.py` → `logger_factory.py` [get_logger]
`passion_insight_generator.py` → `passion_models.py` [PassionSignal]
`passion_insight_generator.py` → `passion_utils.py` [validate_template_values]
`passion_insight_generator.py` → `schema.py` [Col]
`passion_pipeline.py` → `banned_content.py` [contains_banned_content]
`passion_pipeline.py` → `bootstrap.py` [run_startup_checks]
`passion_pipeline.py` → `candidate.py` [Candidate]
`passion_pipeline.py` → `config_passion.py` [PIPELINE_BUDGET_MS, PASSION_MIN_DEBIT_ROWS, PIPELINE_TOP_N, MAX_SPIKE_CANDIDATES, PIPELINE_HARD_TIMEOUT_MS]
`passion_pipeline.py` → `logger_factory.py` [get_logger]
`passion_pipeline.py` → `marketplace_subcategory.py` [enrich_subcategories, resolve_merchant_vectorized]
`passion_pipeline.py` → `passion_detector.py` [detect_passions]
`passion_pipeline.py` → `passion_insight_generator.py` [generate_passion_insights]
`passion_pipeline.py` → `passion_utils.py` [_safe_isna, coerce_bool_column, assert_columns_exist, safe_numeric]
`passion_pipeline.py` → `pipeline_result.py` [PassionResult]
`passion_pipeline.py` → `schema.py` [Col]
`passion_utils.py` → `logger_factory.py` [get_logger]
`pipeline.py` → `anomaly_detector.py` [detect_anomalies]
`pipeline.py` → `categorization_model.py` [predict_categories, train_categorization_model]
`pipeline.py` → `config.py` [module]
`pipeline.py` → `expected_spend_model.py` [predict_expected_spend, train_expected_spend_model]
`pipeline.py` → `feature_engineer.py` [engineer_features_inference, engineer_features]
`pipeline.py` → `insight_generator.py` [generate_human_insights]
`pipeline.py` → `insight_model.py` [predict_insight_scores, load_insight_ranker]
`pipeline.py` → `known_persons.py` [log_unmatched_recurring_transfers, detect_personal_patterns, _enforce_known_person_schema, tag_known_persons]
`pipeline.py` → `log_utils.py` [log_safe_text, log_safe_merchant]
`pipeline.py` → `logger_factory.py` [generate_new_run_id, get_logger, pipeline_run_id_ctx]
`pipeline.py` → `model_state.py` [InsightModelState]
`pipeline.py` → `passion_pipeline.py` [process_pipeline]
`pipeline.py` → `preprocessor.py` [preprocess]
`pipeline.py` → `recurring_detector.py` [find_recurring_transactions]
`pipeline.py` → `schema.py` [Col]
`pipeline.py` → `seed_labeler.py` [label_credits, label_debits]
`pipeline_result.py` → `candidate.py` [Candidate]
`pipeline_result.py` → `passion_models.py` [PassionSignal]
`preprocessor.py` → `config.py` [SPECIFIC_MERCHANT_ALIASES, NOISE_TOKENS, GENERIC_ROUTER_ALIASES]
`preprocessor.py` → `logger_factory.py` [get_logger]
`preprocessor.py` → `schema.py` [Col, coerce_and_validate_types, require_columns]
`recurring_detector.py` → `config.py` [module, RECURRING_CONFIG]
`recurring_detector.py` → `log_utils.py` [log_safe_merchant]
`recurring_detector.py` → `logger_factory.py` [get_logger]
`recurring_detector.py` → `schema.py` [Col, require_columns]
`schema.py` → `logger_factory.py` [get_logger]
`seed_labeler.py` → `config.py` [TIER_MAPPING, CREDIT_PRIORITY, CREDIT_KEYWORDS, CATEGORY_KEYWORDS, CATEGORY_PRIORITY, FALLBACK_DEBIT_LABEL, MIN_COVERAGE_THRESHOLD, FALLBACK_CREDIT_LABEL]
`seed_labeler.py` → `preprocessor.py` [normalize]
`seed_labeler.py` → `schema.py` [Col, require_columns]
`summary_utils.py` → `schema.py` [Col]
`tests/conftest.py` → `log_utils.py` [_reset_secret_cache]
`tests/conftest.py` → `passion_pipeline.py` [module]
`tests/run_smoke.py` → `pipeline.py` [run_pipeline, PipelineResult]
`tests/run_stress_heavy.py` → `pipeline.py` [run_pipeline]
`tests/run_stress_legacy.py` → `pipeline.py` [run_pipeline]
`tests/run_stress_legacy.py` → `schema.py` [Col]
`tests/run_tests_legacy.py` → `tests/test_phase1.py` [*]
`tests/run_tests_legacy.py` → `tests/test_phase2.py` [test_spend_model_training_and_prediction, test_categorization_training_and_prediction]
`tests/test_benchmark.py` → `config.py` [INSIGHT_TYPES, TIP_CORPUS]
`tests/test_benchmark.py` → `training_data_generator.py` [_find_best_tip, _generate_base_features, generate_insight_dataset, ALL_CATEGORIES]
`tests/test_e2e.py` → `anomaly_detector.py` [detect_anomalies]
`tests/test_e2e.py` → `categorization_model.py` [predict_categories, train_categorization_model]
`tests/test_e2e.py` → `expected_spend_model.py` [predict_expected_spend, train_expected_spend_model]
`tests/test_e2e.py` → `feature_engineer.py` [engineer_features_inference, fill_rolling_nulls, engineer_features]
`tests/test_e2e.py` → `insight_generator.py` [generate_human_insights]
`tests/test_e2e.py` → `model_state.py` [InsightModelState]
`tests/test_e2e.py` → `pipeline.py` [run_pipeline, run_inference]
`tests/test_e2e.py` → `preprocessor.py` [preprocess]
`tests/test_e2e.py` → `recurring_detector.py` [find_recurring_transactions]
`tests/test_e2e.py` → `schema.py` [Col]
`tests/test_e2e.py` → `seed_labeler.py` [label_credits, label_debits]
`tests/test_known_persons.py` → `known_persons.py` [_suggestion_key, _enforce_known_person_schema, tag_known_persons, _extract_signals]
`tests/test_known_persons.py` → `model_state.py` [InsightModelState]
`tests/test_known_persons.py` → `pipeline.py` [_compute_config_hash, run_pipeline, PipelineResult, run_inference]
`tests/test_known_persons.py` → `schema.py` [Col]
`tests/test_logging_safety.py` → `config.py` [module]
`tests/test_logging_safety.py` → `log_utils.py` [log_safe_merchant]
`tests/test_logging_safety.py` → `logger_factory.py` [module]
`tests/test_logging_safety.py` → `pipeline.py` [run_pipeline, generate_new_run_id]
`tests/test_logging_safety.py` → `recurring_detector.py` [find_recurring_transactions]
`tests/test_logging_safety.py` → `schema.py` [Col]
`tests/test_ml_integration.py` → `insight_model.py` [predict_insight_scores, load_insight_ranker]
`tests/test_ml_integration.py` → `schema.py` [Col]
`tests/test_model_security.py` → `insight_model.py` [load_insight_ranker, module, _MODELS_DIR, ModelSecurityError, _verify_checksum, _validate_model_path, _compute_checksum]
`tests/test_passion_engine.py` → `banned_content.py` [module, contains_banned_content]
`tests/test_passion_engine.py` → `bootstrap.py` [validate_template_fields, _validate_schema_columns, _dry_render_templates, module, _validate_tip_corpus]
`tests/test_passion_engine.py` → `candidate.py` [module, Candidate]
`tests/test_passion_engine.py` → `config.py` [module]
`tests/test_passion_engine.py` → `config_passion.py` [GENERALIST_CANONICALS, module, PASSION_MERCHANT_ALIASES, validate_merchant_aliases]
`tests/test_passion_engine.py` → `contracts.py` [module, _freeze_tip_corpus, lookup_matching_tip_ids]
`tests/test_passion_engine.py` → `hash_utils.py` [stable_hash]
`tests/test_passion_engine.py` → `log_utils.py` [log_safe_text, verify_merchant_token, _reset_secret_cache, log_safe_merchant, module, _get_secret]
`tests/test_passion_engine.py` → `marketplace_subcategory.py` [module, enrich_subcategories, resolve_merchant_vectorized]
`tests/test_passion_engine.py` → `passion_detector.py` [_is_non_declining, module, detect_passions, _check_distress_gate, _check_anomaly_suppression]
`tests/test_passion_engine.py` → `passion_insight_generator.py` [module, generate_passion_insights]
`tests/test_passion_engine.py` → `passion_models.py` [module, PassionSignal]
`tests/test_passion_engine.py` → `passion_pipeline.py` [_neutral_passion_result, safe_assign_new_columns, process_pipeline, _normalize_ts, _StepBudgetGuard, module]
`tests/test_passion_engine.py` → `passion_utils.py` [validate_template_values, safe_last_nonnull, sanitize_mask, safe_numeric, _safe_isna, module, coerce_bool_column, to_bool_strict]
`tests/test_passion_engine.py` → `pipeline.py` [_write_crash_dumps, module, PipelineResult]
`tests/test_passion_engine.py` → `pipeline_result.py` [module, PassionResult]
`tests/test_passion_engine.py` → `schema.py` [module, Col]
`tests/test_phase1.py` → `config.py` [CREDIT_PRIORITY, CREDIT_KEYWORDS, CATEGORY_KEYWORDS, CATEGORY_PRIORITY, FALLBACK_DEBIT_LABEL, FALLBACK_CREDIT_LABEL]
`tests/test_phase1.py` → `feature_engineer.py` [add_rolling_features, engineer_features, fill_rolling_nulls, add_time_features, engineer_features_inference, add_amount_features]
`tests/test_phase1.py` → `preprocessor.py` [clean_remark, _compute_signed_amount, preprocess, _normalize_flag, _drop_zero_amount, _deduplicate, validate_schema]
`tests/test_phase1.py` → `schema.py` [Col]
`tests/test_phase1.py` → `seed_labeler.py` [label_credits, _match_remark, _compile_keywords, label_debits]
`tests/test_phase2.py` → `categorization_model.py` [predict_categories, train_categorization_model]
`tests/test_phase2.py` → `expected_spend_model.py` [predict_expected_spend, train_expected_spend_model]
`tests/test_phase3.py` → `anomaly_detector.py` [detect_anomalies]
`tests/test_phase3.py` → `insight_generator.py` [_select_tip, generate_human_insights]
`tests/test_phase3.py` → `pipeline.py` [PipelineResult]
`tests/test_phase3.py` → `recurring_detector.py` [find_recurring_transactions]
`train_and_save_models.py` → `insight_model.py` [_compute_checksum]
`train_and_save_models.py` → `schema.py` [Col]
`train_and_save_models.py` → `training_data_generator.py` [generate_insight_dataset]
`training_data_generator.py` → `config.py` [lookup_matching_tip_ids, INSIGHT_TYPES, CATEGORY_PRIORITY]
`training_data_generator.py` → `contracts.py` [TIP_CORPUS]
`tutorial_real_data.py` → `logger_factory.py` [get_logger]
`tutorial_real_data.py` → `pipeline.py` [run_pipeline]
`tutorial_real_data.py` → `schema.py` [Col]

## Transitive Dependency Chains
**[HIGH RISK]** `anomaly_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
`bootstrap.py` → `contracts.py` → `config.py`
`bootstrap.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `bootstrap.py` → `schema.py` → `logger_factory.py` → `config.py`
`bootstrap.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `bootstrap.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `categorization_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `logger_factory.py` → `config.py`
`demo.py` → `pipeline.py` → `model_state.py`
`demo.py` → `pipeline.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `feature_engineer.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `seed_labeler.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `seed_labeler.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `categorization_model.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `categorization_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `expected_spend_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `anomaly_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `recurring_detector.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `recurring_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `recurring_detector.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `recurring_detector.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `insight_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `insight_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `known_persons.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `known_persons.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `known_persons.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `candidate.py` → `passion_models.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `banned_content.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `pipeline_result.py` → `candidate.py` → `passion_models.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `pipeline_result.py` → `passion_models.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `passion_models.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `passion_models.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `banned_content.py`
**[HIGH RISK]** `demo.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `demo.py` → `summary_utils.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `expected_spend_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `feature_engineer.py` → `schema.py` → `logger_factory.py` → `config.py`
`insight_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `insight_model.py` → `schema.py` → `logger_factory.py` → `config.py`
`known_persons.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `known_persons.py` → `schema.py` → `logger_factory.py` → `config.py`
`log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `marketplace_subcategory.py` → `schema.py` → `logger_factory.py` → `config.py`
`marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `marketplace_subcategory.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
`marketplace_subcategory.py` → `logger_factory.py` → `config.py`
`model_benchmark.py` → `training_data_generator.py` → `config.py`
**[HIGH RISK]** `model_benchmark.py` → `training_data_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `passion_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
`passion_detector.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `passion_detector.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_detector.py` → `marketplace_subcategory.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_detector.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `passion_detector.py` → `marketplace_subcategory.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_detector.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
`passion_detector.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
`passion_insight_generator.py` → `contracts.py` → `config.py`
`passion_insight_generator.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `passion_insight_generator.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
`passion_insight_generator.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `schema.py` → `logger_factory.py` → `config.py`
`passion_pipeline.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
`passion_pipeline.py` → `candidate.py` → `passion_models.py`
`passion_pipeline.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `pipeline_result.py` → `candidate.py` → `passion_models.py`
`passion_pipeline.py` → `pipeline_result.py` → `passion_models.py`
**[HIGH RISK]** `passion_pipeline.py` → `bootstrap.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `bootstrap.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `bootstrap.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `bootstrap.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `bootstrap.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `marketplace_subcategory.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `marketplace_subcategory.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_detector.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_detector.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
`passion_pipeline.py` → `passion_detector.py` → `passion_models.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_detector.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_insight_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_insight_generator.py` → `config_passion.py` → `config.py`
`passion_pipeline.py` → `passion_insight_generator.py` → `passion_models.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_insight_generator.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
`passion_pipeline.py` → `passion_insight_generator.py` → `banned_content.py`
**[HIGH RISK]** `passion_pipeline.py` → `passion_insight_generator.py` → `logger_factory.py` → `config.py`
`passion_utils.py` → `logger_factory.py` → `config.py`
`pipeline.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `schema.py` → `logger_factory.py` → `config.py`
`pipeline.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `feature_engineer.py` → `schema.py` → `logger_factory.py` → `config.py`
`pipeline.py` → `seed_labeler.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `seed_labeler.py` → `schema.py` → `logger_factory.py` → `config.py`
`pipeline.py` → `categorization_model.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `categorization_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `expected_spend_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `anomaly_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
`pipeline.py` → `recurring_detector.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `recurring_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `recurring_detector.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `recurring_detector.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `insight_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `insight_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `known_persons.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `known_persons.py` → `schema.py` → `logger_factory.py` → `config.py`
`pipeline.py` → `known_persons.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `candidate.py` → `passion_models.py`
`pipeline.py` → `passion_pipeline.py` → `banned_content.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `pipeline_result.py` → `candidate.py` → `passion_models.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `pipeline_result.py` → `passion_models.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `passion_models.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `passion_models.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `banned_content.py`
**[HIGH RISK]** `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `logger_factory.py` → `config.py`
`pipeline_result.py` → `candidate.py` → `passion_models.py`
**[HIGH RISK]** `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
`preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `recurring_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `recurring_detector.py` → `log_utils.py` → `logger_factory.py` → `config.py`
`recurring_detector.py` → `logger_factory.py` → `config.py`
`schema.py` → `logger_factory.py` → `config.py`
`seed_labeler.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `seed_labeler.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `seed_labeler.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `seed_labeler.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `summary_utils.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `candidate.py` → `passion_models.py`
`tests/conftest.py` → `passion_pipeline.py` → `banned_content.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `pipeline_result.py` → `candidate.py` → `passion_models.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `pipeline_result.py` → `passion_models.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `bootstrap.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `bootstrap.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `bootstrap.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `bootstrap.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `bootstrap.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_detector.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_detector.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_detector.py` → `passion_models.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_detector.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `passion_models.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `banned_content.py`
**[HIGH RISK]** `tests/conftest.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/conftest.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `logger_factory.py` → `config.py`
`tests/run_smoke.py` → `pipeline.py` → `model_state.py`
`tests/run_smoke.py` → `pipeline.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `feature_engineer.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `seed_labeler.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `seed_labeler.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `categorization_model.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `categorization_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `expected_spend_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `anomaly_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `recurring_detector.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `recurring_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `recurring_detector.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `recurring_detector.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `insight_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `insight_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `known_persons.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `known_persons.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `known_persons.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `candidate.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `banned_content.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `pipeline_result.py` → `candidate.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `pipeline_result.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `banned_content.py`
**[HIGH RISK]** `tests/run_smoke.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `logger_factory.py` → `config.py`
`tests/run_stress_heavy.py` → `pipeline.py` → `model_state.py`
`tests/run_stress_heavy.py` → `pipeline.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `feature_engineer.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `seed_labeler.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `seed_labeler.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `categorization_model.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `categorization_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `expected_spend_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `anomaly_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `recurring_detector.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `recurring_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `recurring_detector.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `recurring_detector.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `insight_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `insight_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `known_persons.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `known_persons.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `known_persons.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `candidate.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `banned_content.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `pipeline_result.py` → `candidate.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `pipeline_result.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `banned_content.py`
**[HIGH RISK]** `tests/run_stress_heavy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `logger_factory.py` → `config.py`
`tests/run_stress_legacy.py` → `pipeline.py` → `model_state.py`
`tests/run_stress_legacy.py` → `pipeline.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `feature_engineer.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `seed_labeler.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `seed_labeler.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `seed_labeler.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `categorization_model.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `categorization_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `expected_spend_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `anomaly_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `recurring_detector.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `recurring_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `recurring_detector.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `recurring_detector.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `insight_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `insight_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `known_persons.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `known_persons.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `known_persons.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `candidate.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `banned_content.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `pipeline_result.py` → `candidate.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `pipeline_result.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `bootstrap.py` → `log_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `marketplace_subcategory.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_detector.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `contracts.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `config_passion.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `passion_models.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `passion_utils.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `banned_content.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `pipeline.py` → `passion_pipeline.py` → `passion_insight_generator.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_stress_legacy.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_tests_legacy.py` → `tests/test_phase2.py` → `categorization_model.py` → `config.py`
**[HIGH RISK]** `tests/run_tests_legacy.py` → `tests/test_phase2.py` → `categorization_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_tests_legacy.py` → `tests/test_phase2.py` → `expected_spend_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_tests_legacy.py` → `tests/test_phase1.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_tests_legacy.py` → `tests/test_phase1.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `tests/run_tests_legacy.py` → `tests/test_phase1.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_tests_legacy.py` → `tests/test_phase1.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_tests_legacy.py` → `tests/test_phase1.py` → `feature_engineer.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_tests_legacy.py` → `tests/test_phase1.py` → `seed_labeler.py` → `config.py`
**[HIGH RISK]** `tests/run_tests_legacy.py` → `tests/test_phase1.py` → `seed_labeler.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `tests/run_tests_legacy.py` → `tests/test_phase1.py` → `seed_labeler.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_tests_legacy.py` → `tests/test_phase1.py` → `seed_labeler.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/run_tests_legacy.py` → `tests/test_phase1.py` → `seed_labeler.py` → `schema.py` → `logger_factory.py` → `config.py`
`tests/run_tests_legacy.py` → `tests/test_phase1.py` → `config.py`
`tests/test_benchmark.py` → `training_data_generator.py` → `config.py`
**[HIGH RISK]** `tests/test_benchmark.py` → `training_data_generator.py` → `contracts.py` → `config.py`
`tests/test_e2e.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `tests/test_e2e.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/test_e2e.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/test_e2e.py` → `feature_engineer.py` → `schema.py` → `logger_factory.py` → `config.py`
`tests/test_e2e.py` → `seed_labeler.py` → `config.py`
**[HIGH RISK]** `tests/test_e2e.py` → `seed_labeler.py` → `preprocessor.py` → `config.py`
**[HIGH RISK]** `tests/test_e2e.py` → `seed_labeler.py` → `preprocessor.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/test_e2e.py` → `seed_labeler.py` → `preprocessor.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/test_e2e.py` → `seed_labeler.py` → `schema.py` → `logger_factory.py` → `config.py`
`tests/test_e2e.py` → `categorization_model.py` → `config.py`
**[HIGH RISK]** `tests/test_e2e.py` → `categorization_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/test_e2e.py` → `expected_spend_model.py` → `schema.py` → `logger_factory.py` → `config.py`
**[HIGH RISK]** `tests/test_e2e.py` → `anomaly_detector.py` → `schema.py` → `logger_factory.py` → `config.py`
`tests/test_e2e.py` → `recurring_detector.py` → `config.py`
