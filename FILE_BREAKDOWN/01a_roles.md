*(Part 1 of 4 - split due to length)*

# Files by Role

## CONFIG

### `banned_content.py`

#### Dependencies
- **Direct internal**:
  - none
- **Transitive internal**:
  - none
- **Direct external**:
  - none
- **Runtime / injected deps**: none

#### Identity
- **Role**: CONFIG
- **Purpose**: Stores configuration values, thresholds, and static lists.

#### Exports
- `BANNED_PATTERN` (constant)
- `_CONFUSABLES` (constant)
- `_normalize_display_text` (function)
- `_COMPACT_SAFE_TERMS` (constant)
- `_SEP` (constant)
- `_obfuscated_word_pattern` (function)
- `_OBFUSCATED_SAFE_PATTERN` (constant)
- `contains_banned_content` (function)
- `__all__` (constant)

#### Side Effects
none

---

### `config.py`

#### Dependencies
- **Direct internal**:
  - none
- **Transitive internal**:
  - none
- **Direct external**:
  - none
- **Runtime / injected deps**: none

#### Identity
- **Role**: CONFIG
- **Purpose**: Stores configuration values, thresholds, and static lists.

#### Exports
- `LOG_LEVEL` (constant)
- `VALID_LOG_LEVELS` (constant)
- `ENABLE_CRASH_DUMPS` (constant)
- `CRASH_DUMP_DIR` (constant)
- `ENABLE_PII_DEBUG_LOGS` (constant)
- `HIGH_PRIORITY` (constant)
- `MEDIUM_PRIORITY` (constant)
- `LOW_PRIORITY` (constant)
- `CATEGORY_PRIORITY` (constant)
- `TIER_MAPPING` (constant)
- `CREDIT_PRIORITY` (constant)
- `FALLBACK_DEBIT_LABEL` (constant)
- `FALLBACK_CREDIT_LABEL` (constant)
- `MIN_COVERAGE_THRESHOLD` (constant)
- `RECURRING_CONFIG` (constant)
- `lookup_matching_tip_ids` (function)
- `KNOWN_PERSON_MATCH_THRESHOLD` (constant)
- `CONCAT_MIN_LENGTH` (constant)
- `CONCAT_PARTIAL_MIN_LENGTH` (constant)
- `MIN_SPEND_TRANSACTIONS_FOR_ML` (constant)

#### Side Effects
none

---

### `config_passion.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [SPECIFIC_MERCHANT_ALIASES, CATEGORY_KEYWORDS, CATEGORY_PRIORITY]
- **Transitive internal**:
  - none
- **Direct external**:
  - none
- **Runtime / injected deps**: none

#### Identity
- **Role**: CONFIG
- **Purpose**: Stores configuration values, thresholds, and static lists.

#### Exports
- `_CORE_ALIASES` (constant)
- `_PASSION_EXTRAS` (constant)
- `_NORMALIZED_EXTRAS` (constant)
- `_ALIAS_CONFLICTS` (constant)
- `validate_merchant_aliases` (function)
- `validate_config` (function)
- `__all__` (constant)

#### Side Effects
none

---

## CORE_LOGIC

### `anomaly_detector.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `config.py` (via `schema.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `schema.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Composite statistical anomaly flagging.

#### Exports
- `detect_anomalies` (function)

#### Side Effects
file I/O

---

### `categorization_model.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [FALLBACK_DEBIT_LABEL, FALLBACK_CREDIT_LABEL]
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `logger_factory.py` (via `schema.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pandas` → [module]
  - `sklearn` → [Pipeline, StandardScaler, LogisticRegression, ColumnTransformer, TfidfVectorizer]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Contains core business logic, statistical methods, or ML inference.

#### Exports
- `build_categorization_pipeline` (function)
- `train_categorization_model` (function)
- `predict_categories` (function)

#### Side Effects
file I/O

---

### `expected_spend_model.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `config.py` (via `schema.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `schema.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
  - `sklearn` → [RidgeCV, Pipeline, StandardScaler, OneHotEncoder, ColumnTransformer]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Contains core business logic, statistical methods, or ML inference.

#### Exports
- `build_spend_pipeline` (function)
- `train_expected_spend_model` (function)
- `predict_expected_spend` (function)

#### Side Effects
file I/O

---

### `feature_engineer.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `config.py` (via `schema.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `schema.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Generates machine learning features.

#### Exports
- `ZSCORE_CLIP` (constant)
- `add_time_features` (function)
- `add_rolling_features` (function)
- `fill_rolling_nulls` (function)
- `add_amount_features` (function)
- `engineer_features` (function)
- `engineer_features_inference` (function)

#### Side Effects
file I/O

---

### `insight_generator.py`

#### Dependencies
- **Direct internal**:
  - `contracts.py` → [lookup_matching_tip_ids, INSIGHT_TEMPLATES, TIP_CORPUS]
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `config.py` (via `contracts.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `schema.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Generates insights from categorized transactions.

#### Exports
- `_select_tip` (function)
- `generate_human_insights` (function)

#### Side Effects
network calls, file I/O

---

### `insight_model.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `config.py` (via `schema.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `schema.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pandas` → [module]
  - `sklearn` → [Pipeline]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Generates insights from categorized transactions.

#### Exports
- `NUMERIC_FEATURES` (constant)
- `CATEGORICAL_FEATURES` (constant)
- `_MODELS_DIR` (constant)
- `ModelSecurityError` (class)
- `_compute_checksum` (function)
- `_verify_checksum` (function)
- `_validate_model_path` (function)
- `load_insight_ranker` (function)
- `predict_insight_scores` (function)

#### Side Effects
file I/O (open/print), file I/O

---

### `model_benchmark.py`

#### Dependencies
- **Direct internal**:
  - `training_data_generator.py` → [generate_insight_dataset]
- **Transitive internal**:
  - `config.py` (via `training_data_generator.py`) → [module/symbols used indirectly]
  - `contracts.py` (via `training_data_generator.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `catboost` → [CatBoostClassifier]
  - `lightgbm` → [LGBMClassifier]
  - `numpy` → [module]
  - `pandas` → [module]
  - `sklearn` → [recall_score, StandardScaler, classification_report, precision_score, accuracy_score, AdaBoostClassifier, OneHotEncoder, LogisticRegression, ColumnTransformer, f1_score, KNeighborsClassifier, DecisionTreeClassifier, CalibratedClassifierCV, RandomForestClassifier, ExtraTreesClassifier, StratifiedKFold, MLPClassifier, LabelEncoder, LinearSVC, GradientBoostingClassifier, Pipeline, cross_validate, confusion_matrix]
  - `xgboost` → [XGBClassifier]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Contains core business logic, statistical methods, or ML inference.

#### Exports
- `get_candidate_models` (function)
- `build_pipeline` (function)
- `evaluate_model` (function)
- `run_benchmark` (function)
- `format_results_table` (function)
- `print_confusion_matrix` (function)
- `print_classification_report_top` (function)
- `generate_feature_importance` (function)
- `main` (function)

#### Side Effects
file I/O (open/print), network calls, file I/O

---

### `passion_detector.py`

#### Dependencies
- **Direct internal**:
  - `config_passion.py` → [PASSION_ANOMALY_SUPPRESSION_THRESHOLD, DISTRESS_FEES_THRESHOLD, PASSION_SPEND_SHARE_THRESHOLD, PASSION_MIN_MONTHS, PASSION_MERCHANT_COUNT_MIN]
  - `logger_factory.py` → [get_logger]
  - `marketplace_subcategory.py` → [resolve_merchant_vectorized]
  - `passion_models.py` → [PassionSignal]
  - `passion_utils.py` → [assert_columns_exist, sanitize_mask, safe_numeric, _safe_isna, coerce_bool_column]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `config.py` (via `schema.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Detects passion or specialized categories.

#### Exports
- `__all__` (constant)
- `_FEE_KEYWORDS` (constant)
- `_FEE_PATTERN` (constant)
- `_safe_coerce_anomaly` (function)
- `_check_distress_gate` (function)
- `_check_anomaly_suppression` (function)
- `_parse_dates_safe` (function)
- `_is_non_declining` (function)
- `detect_passions` (function)

#### Side Effects
network calls, file I/O

---

### `passion_insight_generator.py`

#### Dependencies
- **Direct internal**:
  - `banned_content.py` → [contains_banned_content]
  - `config_passion.py` → [PASSION_INSIGHT_TEMPLATES]
  - `contracts.py` → [lookup_matching_tip_ids, INSIGHT_TEMPLATES, TIP_CORPUS]
  - `logger_factory.py` → [get_logger]
  - `passion_models.py` → [PassionSignal]
  - `passion_utils.py` → [validate_template_values]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `config.py` (via `schema.py`) → [module/symbols used indirectly]
- **Direct external**:
  - none
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Generates insights from categorized transactions.

#### Exports
- `__all__` (constant)
- `_select_tip` (function)
- `_render_candidate` (function)
- `generate_passion_insights` (function)

#### Side Effects
network calls

---

### `passion_models.py`

#### Dependencies
- **Direct internal**:
  - none
- **Transitive internal**:
  - none
- **Direct external**:
  - `numpy` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Contains core business logic, statistical methods, or ML inference.

#### Exports
- `__all__` (constant)
- `_EPS` (constant)
- `PassionSignal` (class)

#### Side Effects
none

---

### `preprocessor.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [SPECIFIC_MERCHANT_ALIASES, NOISE_TOKENS, GENERIC_ROUTER_ALIASES]
  - `logger_factory.py` → [get_logger]
  - `schema.py` → [Col, coerce_and_validate_types, require_columns]
- **Transitive internal**:
  - none
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Contains core business logic, statistical methods, or ML inference.

#### Exports
- `_LONG_DIGIT_PATTERN` (constant)
- `_EMAIL_PATTERN` (constant)
- `_SPECIAL_CHAR_PATTERN` (constant)
- `_MULTI_SPACE_PATTERN` (constant)
- `validate_schema` (function)
- `_parse_and_sort_dates` (function)
- `_normalize_flag` (function)
- `_compute_signed_amount` (function)
- `normalize` (function)
- `clean_remark` (function)
- `_drop_zero_amount` (function)
- `_deduplicate` (function)
- `_split_debit_credit` (function)
- `preprocess` (function)

#### Side Effects
file I/O

---

### `recurring_detector.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [module, RECURRING_CONFIG]
  - `log_utils.py` → [log_safe_merchant]
  - `logger_factory.py` → [get_logger]
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - none
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Rule-based recurring transaction identifier.

#### Exports
- `find_recurring_transactions` (function)

#### Side Effects
file I/O

---

### `training_data_generator.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [lookup_matching_tip_ids, INSIGHT_TYPES, CATEGORY_PRIORITY]
  - `contracts.py` → [TIP_CORPUS]
- **Transitive internal**:
  - none
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
  - `sklearn` → [train_test_split]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Contains core business logic, statistical methods, or ML inference.

#### Exports
- `_find_best_tip` (function)
- `_generate_base_features` (function)
- `_apply_labels` (function)
- `_add_edge_cases` (function)
- `generate_insight_dataset` (function)

#### Side Effects
network calls, file I/O

---

## DATA_LAYER

### `known_persons.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [module]
  - `logger_factory.py` → [get_logger]
  - `schema.py` → [Col]
- **Transitive internal**:
  - none
- **Direct external**:
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: DATA_LAYER
- **Purpose**: Manages data retrieval, labeling, or enrichment.

#### Exports
- `_NAME_NOISE_TOKENS` (constant)
- `_MERCHANT_INDICATOR_TOKENS` (constant)
- `_MERCHANT_SUFFIXES` (constant)
- `_TRANSFER_CONTEXT_TOKENS` (constant)
- `_SEPARATOR_PATTERN` (constant)
- `SignalBundle` (class)
- `_extract_signals` (function)
- `_is_contiguous_subsequence` (function)
- `_find_concat_partial_match` (function)
- `_find_account_fragment_match` (function)
- `_compile_matchers` (function)
- `_score_remark` (function)
- `tag_known_persons` (function)
- `_enforce_known_person_schema` (function)
- `_suggestion_key` (function)
- `log_unmatched_recurring_transfers` (function)
- `_analyze_person_group` (function)
- `detect_personal_patterns` (function)

#### Side Effects
network calls, file I/O

---

### `marketplace_subcategory.py`

#### Dependencies
- **Direct internal**:
  - `config_passion.py` → [MARKETPLACE_HIGH_CONFIDENCE, PASSION_MERCHANT_ALIASES, ELECTRONICS_ALLOWED_CATEGORIES, MARKETPLACE_HIGH_AMOUNT_THRESHOLD, MARKETPLACE_LOW_CONFIDENCE, GENERALIST_CANONICALS]
  - `logger_factory.py` → [get_logger]
  - `passion_utils.py` → [safe_numeric, coerce_bool_column, assert_columns_exist]
  - `schema.py` → [Col]
- **Transitive internal**:
  - `config.py` (via `schema.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `numpy` → [module]
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: DATA_LAYER
- **Purpose**: Manages data retrieval, labeling, or enrichment.

#### Exports
- `__all__` (constant)
- `_ALIAS_PATTERN` (constant)
- `resolve_merchant_vectorized` (function)
- `enrich_subcategories` (function)

#### Side Effects
network calls, file I/O

---

### `seed_labeler.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [TIER_MAPPING, CREDIT_PRIORITY, CREDIT_KEYWORDS, CATEGORY_KEYWORDS, CATEGORY_PRIORITY, FALLBACK_DEBIT_LABEL, MIN_COVERAGE_THRESHOLD, FALLBACK_CREDIT_LABEL]
  - `preprocessor.py` → [normalize]
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `logger_factory.py` (via `preprocessor.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: DATA_LAYER
- **Purpose**: Manages data retrieval, labeling, or enrichment.

#### Exports
- `CompiledKeyword` (class)
- `_compile_keywords` (function)
- `_match_remark` (function)
- `_DEFAULT_DEBIT_KWS` (constant)
- `_DEFAULT_CREDIT_KWS` (constant)
- `_log_coverage` (function)
- `label_debits` (function)
- `label_credits` (function)

#### Side Effects
file I/O

---
