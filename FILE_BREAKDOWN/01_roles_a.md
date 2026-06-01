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
  - `unicodedata` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CONFIG
- **Purpose**: Defines lists of banned words or content rules.

#### Exports
- `BANNED_PATTERN` (constant/variable)
- `_CONFUSABLES` (constant/variable)
- `_normalize_display_text` (function)
- `_COMPACT_SAFE_TERMS` (constant/variable)
- `_SEP` (constant/variable)
- `_obfuscated_word_pattern` (function)
- `_OBFUSCATED_SAFE_PATTERN` (constant/variable)
- `contains_banned_content` (function)
- `__all__` (constant/variable)

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
- `LOG_LEVEL` (constant/variable)
- `VALID_LOG_LEVELS` (constant/variable)
- `ENABLE_CRASH_DUMPS` (constant/variable)
- `CRASH_DUMP_DIR` (constant/variable)
- `ENABLE_PII_DEBUG_LOGS` (constant/variable)
- `HIGH_PRIORITY` (constant/variable)
- `MEDIUM_PRIORITY` (constant/variable)
- `LOW_PRIORITY` (constant/variable)
- `CATEGORY_PRIORITY` (constant/variable)
- `TIER_MAPPING` (constant/variable)
- `CREDIT_PRIORITY` (constant/variable)
- `FALLBACK_DEBIT_LABEL` (constant/variable)
- `FALLBACK_CREDIT_LABEL` (constant/variable)
- `MIN_COVERAGE_THRESHOLD` (constant/variable)
- `RECURRING_CONFIG` (constant/variable)
- `lookup_matching_tip_ids` (function)
- `KNOWN_PERSON_MATCH_THRESHOLD` (constant/variable)
- `CONCAT_MIN_LENGTH` (constant/variable)
- `CONCAT_PARTIAL_MIN_LENGTH` (constant/variable)
- `MIN_SPEND_TRANSACTIONS_FOR_ML` (constant/variable)

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
  - `types` → [MappingProxyType]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CONFIG
- **Purpose**: Stores configuration values, thresholds, and static lists.

#### Exports
- `_CORE_ALIASES` (constant/variable)
- `_PASSION_EXTRAS` (constant/variable)
- `_NORMALIZED_EXTRAS` (constant/variable)
- `_ALIAS_CONFLICTS` (constant/variable)
- `validate_merchant_aliases` (function)
- `validate_config` (function)
- `__all__` (constant/variable)

#### Side Effects
none

---

## CORE_LOGIC

### `anomaly_detector.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `logger_factory.py` (via `schema.py`)
  - `config.py` (via `schema.py`)
- **Direct external**:
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Composite statistical anomaly flagging.

#### Exports
- `detect_anomalies` (function)

#### Side Effects
none

---

### `categorization_model.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [FALLBACK_DEBIT_LABEL, FALLBACK_CREDIT_LABEL]
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `logger_factory.py` (via `schema.py`)
- **Direct external**:
  - `pandas` → [*]
  - `sklearn` → [Pipeline, LogisticRegression, TfidfVectorizer, ColumnTransformer, StandardScaler]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Contains core business logic, statistical methods, or ML inference.

#### Exports
- `build_categorization_pipeline` (function)
- `train_categorization_model` (function)
- `predict_categories` (function)

#### Side Effects
none

---

### `expected_spend_model.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `logger_factory.py` (via `schema.py`)
  - `config.py` (via `schema.py`)
- **Direct external**:
  - `pandas` → [*]
  - `numpy` → [*]
  - `sklearn` → [RidgeCV, Pipeline, ColumnTransformer, OneHotEncoder, StandardScaler]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Contains core business logic, statistical methods, or ML inference.

#### Exports
- `build_spend_pipeline` (function)
- `train_expected_spend_model` (function)
- `predict_expected_spend` (function)

#### Side Effects
none

---

### `feature_engineer.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `logger_factory.py` (via `schema.py`)
  - `config.py` (via `schema.py`)
- **Direct external**:
  - `numpy` → [*]
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Generates machine learning features.

#### Exports
- `ZSCORE_CLIP` (constant/variable)
- `add_time_features` (function)
- `add_rolling_features` (function)
- `fill_rolling_nulls` (function)
- `add_amount_features` (function)
- `engineer_features` (function)
- `engineer_features_inference` (function)

#### Side Effects
none

---

### `insight_generator.py`

#### Dependencies
- **Direct internal**:
  - `contracts.py` → [TIP_CORPUS, INSIGHT_TEMPLATES, lookup_matching_tip_ids]
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `config.py` (via `contracts.py`)
  - `logger_factory.py` (via `schema.py`)
- **Direct external**:
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Generates insights from categorized transactions.

#### Exports
- `_select_tip` (function)
- `generate_human_insights` (function)

#### Side Effects
network calls

---

### `insight_model.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col, require_columns]
- **Transitive internal**:
  - `logger_factory.py` (via `schema.py`)
  - `config.py` (via `schema.py`)
- **Direct external**:
  - `pandas` → [*]
  - `sklearn` → [Pipeline]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Generates insights from categorized transactions.

#### Exports
- `NUMERIC_FEATURES` (constant/variable)
- `CATEGORICAL_FEATURES` (constant/variable)
- `_MODELS_DIR` (constant/variable)
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
  - `config.py` (via `training_data_generator.py`)
  - `contracts.py` (via `training_data_generator.py`)
- **Direct external**:
  - `numpy` → [*]
  - `pandas` → [*]
  - `sklearn` → [MLPClassifier, accuracy_score, DecisionTreeClassifier, AdaBoostClassifier, precision_score, Pipeline, CalibratedClassifierCV, KNeighborsClassifier, recall_score, LogisticRegression, GradientBoostingClassifier, LabelEncoder, StandardScaler, classification_report, confusion_matrix, f1_score, RandomForestClassifier, ColumnTransformer, OneHotEncoder, LinearSVC, StratifiedKFold, ExtraTreesClassifier, cross_validate]
  - `xgboost` → [XGBClassifier]
  - `lightgbm` → [LGBMClassifier]
  - `catboost` → [CatBoostClassifier]
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
file I/O (open/print), network calls

---

### `passion_detector.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col]
  - `config_passion.py` → [PASSION_MIN_MONTHS, PASSION_ANOMALY_SUPPRESSION_THRESHOLD, DISTRESS_FEES_THRESHOLD, PASSION_MERCHANT_COUNT_MIN, PASSION_SPEND_SHARE_THRESHOLD]
  - `passion_utils.py` → [sanitize_mask, _safe_isna, safe_numeric, assert_columns_exist, coerce_bool_column]
  - `marketplace_subcategory.py` → [resolve_merchant_vectorized]
  - `passion_models.py` → [PassionSignal]
  - `logger_factory.py` → [get_logger]
- **Transitive internal**:
  - `config.py` (via `schema.py`)
- **Direct external**:
  - `numpy` → [*]
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Detects passion or specialized categories.

#### Exports
- `__all__` (constant/variable)
- `_FEE_KEYWORDS` (constant/variable)
- `_FEE_PATTERN` (constant/variable)
- `_safe_coerce_anomaly` (function)
- `_check_distress_gate` (function)
- `_check_anomaly_suppression` (function)
- `_parse_dates_safe` (function)
- `_is_non_declining` (function)
- `detect_passions` (function)

#### Side Effects
network calls

---

### `passion_insight_generator.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col]
  - `contracts.py` → [TIP_CORPUS, INSIGHT_TEMPLATES, lookup_matching_tip_ids]
  - `config_passion.py` → [PASSION_INSIGHT_TEMPLATES]
  - `passion_models.py` → [PassionSignal]
  - `passion_utils.py` → [validate_template_values]
  - `banned_content.py` → [contains_banned_content]
  - `logger_factory.py` → [get_logger]
- **Transitive internal**:
  - `config.py` (via `schema.py`)
- **Direct external**:
  - none
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Generates insights from categorized transactions.

#### Exports
- `__all__` (constant/variable)
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
  - `__future__` → [annotations]
  - `numpy` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Contains core business logic, statistical methods, or ML inference.

#### Exports
- `__all__` (constant/variable)
- `_EPS` (constant/variable)
- `PassionSignal` (class)

#### Side Effects
none

---

### `preprocessor.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [GENERIC_ROUTER_ALIASES, SPECIFIC_MERCHANT_ALIASES, NOISE_TOKENS]
  - `schema.py` → [Col, require_columns, coerce_and_validate_types]
  - `logger_factory.py` → [get_logger]
- **Transitive internal**:
  - none
- **Direct external**:
  - `pandas` → [*]
  - `numpy` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Contains core business logic, statistical methods, or ML inference.

#### Exports
- `_LONG_DIGIT_PATTERN` (constant/variable)
- `_EMAIL_PATTERN` (constant/variable)
- `_SPECIAL_CHAR_PATTERN` (constant/variable)
- `_MULTI_SPACE_PATTERN` (constant/variable)
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
none

---

### `recurring_detector.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [*, RECURRING_CONFIG]
  - `schema.py` → [Col, require_columns]
  - `log_utils.py` → [log_safe_merchant]
  - `logger_factory.py` → [get_logger]
- **Transitive internal**:
  - none
- **Direct external**:
  - `pandas` → [*]
  - `numpy` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Rule-based recurring transaction identifier.

#### Exports
- `find_recurring_transactions` (function)

#### Side Effects
none

---

### `tests/test_model_security.py`

#### Dependencies
- **Direct internal**:
  - `insight_model.py` → [load_insight_ranker, _verify_checksum, _compute_checksum, *, _MODELS_DIR, ModelSecurityError, _validate_model_path]
- **Transitive internal**:
  - `schema.py` (via `insight_model.py`)
  - `logger_factory.py` (via `insight_model.py`)
  - `config.py` (via `insight_model.py`)
- **Direct external**:
  - `pytest` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: CORE_LOGIC
- **Purpose**: Contains core business logic, statistical methods, or ML inference.

#### Exports
- `tmp_models_dir` (function)
- `TestChecksumComputation` (class)
- `TestChecksumVerification` (class)
- `TestPathValidation` (class)
- `TestLoadInsightRanker` (class)

#### Side Effects
file I/O (open/print)

---

### `training_data_generator.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [INSIGHT_TYPES, lookup_matching_tip_ids, CATEGORY_PRIORITY]
  - `contracts.py` → [TIP_CORPUS]
- **Transitive internal**:
  - none
- **Direct external**:
  - `numpy` → [*]
  - `pandas` → [*]
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
network calls

---

## DATA_LAYER

### `known_persons.py`

#### Dependencies
- **Direct internal**:
  - `logger_factory.py` → [get_logger]
  - `schema.py` → [Col]
  - `config.py` → [*]
- **Transitive internal**:
  - none
- **Direct external**:
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: DATA_LAYER
- **Purpose**: Manages data for known persons or entities.

#### Exports
- `_NAME_NOISE_TOKENS` (constant/variable)
- `_MERCHANT_INDICATOR_TOKENS` (constant/variable)
- `_MERCHANT_SUFFIXES` (constant/variable)
- `_TRANSFER_CONTEXT_TOKENS` (constant/variable)
- `_SEPARATOR_PATTERN` (constant/variable)
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
network calls

---

### `marketplace_subcategory.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col]
  - `config_passion.py` → [ELECTRONICS_ALLOWED_CATEGORIES, PASSION_MERCHANT_ALIASES, MARKETPLACE_LOW_CONFIDENCE, MARKETPLACE_HIGH_CONFIDENCE, MARKETPLACE_HIGH_AMOUNT_THRESHOLD, GENERALIST_CANONICALS]
  - `passion_utils.py` → [assert_columns_exist, coerce_bool_column, safe_numeric]
  - `logger_factory.py` → [get_logger]
- **Transitive internal**:
  - `config.py` (via `schema.py`)
- **Direct external**:
  - `pandas` → [*]
  - `numpy` → [*]
  - `types` → [MappingProxyType]
- **Runtime / injected deps**: none

#### Identity
- **Role**: DATA_LAYER
- **Purpose**: Manages data retrieval, labeling, or enrichment.

#### Exports
- `__all__` (constant/variable)
- `_ALIAS_PATTERN` (constant/variable)
- `resolve_merchant_vectorized` (function)
- `enrich_subcategories` (function)

#### Side Effects
network calls

---
