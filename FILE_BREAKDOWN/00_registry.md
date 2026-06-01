# File Registry

## Annotated Directory Tree

- `analyzer.py` - UNKNOWN
- `anomaly_detector.py` - CORE_LOGIC
- `banned_content.py` - CONFIG
- `bootstrap.py` - ENTRYPOINT
- `candidate.py` - SCHEMA
- `categorization_model.py` - CORE_LOGIC
- `config.py` - CONFIG
- `config_passion.py` - CONFIG
- `contracts.py` - SCHEMA
- `demo.py` - ENTRYPOINT
- `expected_spend_model.py` - CORE_LOGIC
- `feature_engineer.py` - CORE_LOGIC
- `hash_utils.py` - UTILITY
- `insight_generator.py` - CORE_LOGIC
- `insight_model.py` - CORE_LOGIC
- `known_persons.py` - DATA_LAYER
- `log_utils.py` - UTILITY
- `logger_factory.py` - UTILITY
- `marketplace_subcategory.py` - DATA_LAYER
- `model_benchmark.py` - CORE_LOGIC
- `model_state.py` - SCHEMA
- `passion_detector.py` - CORE_LOGIC
- `passion_insight_generator.py` - CORE_LOGIC
- `passion_models.py` - CORE_LOGIC
- `passion_pipeline.py` - ENTRYPOINT
- `passion_utils.py` - UTILITY
- `pipeline.py` - ENTRYPOINT
- `pipeline_result.py` - SCHEMA
- `preprocessor.py` - CORE_LOGIC
- `recurring_detector.py` - CORE_LOGIC
- `refactor_pipeline.py` - UTILITY
- `schema.py` - SCHEMA
- `seed_labeler.py` - DATA_LAYER
- `summary_utils.py` - UTILITY
- `tests/conftest.py` - TEST
- `tests/run_smoke.py` - TEST
- `tests/run_stress_heavy.py` - TEST
- `tests/run_stress_legacy.py` - TEST
- `tests/run_tests_legacy.py` - TEST
- `tests/test_benchmark.py` - TEST
- `tests/test_e2e.py` - TEST
- `tests/test_known_persons.py` - DATA_LAYER
- `tests/test_logging_safety.py` - TEST
- `tests/test_ml_integration.py` - TEST
- `tests/test_model_security.py` - CORE_LOGIC
- `tests/test_passion_engine.py` - TEST
- `tests/test_phase1.py` - TEST
- `tests/test_phase2.py` - TEST
- `tests/test_phase3.py` - TEST
- `train_and_save_models.py` - ENTRYPOINT
- `training_data_generator.py` - CORE_LOGIC
- `tutorial_real_data.py` - ENTRYPOINT

## Master File Table

| File | Role | Purpose | Direct Deps (internal) | Direct Deps (external) | Side Effects |
|------|------|---------|----------------------|----------------------|--------------|
| `analyzer.py` | UNKNOWN | Need to infer purpose. | none | glob | file I/O (open/print), file I/O |
| `anomaly_detector.py` | CORE_LOGIC | Composite statistical anomaly flagging. | schema.py | pandas | none |
| `banned_content.py` | CONFIG | Defines lists of banned words or content rules. | none | unicodedata | none |
| `bootstrap.py` | ENTRYPOINT | Initializes and bootstraps application environments or models. | contracts.py, logger_factory.py, schema.py, config_passion.py, log_utils.py | types | network calls |
| `candidate.py` | SCHEMA | Defines data schemas, types, classes, or domain models. | passion_models.py | __future__, numpy | network calls |
| `categorization_model.py` | CORE_LOGIC | Contains core business logic, statistical methods, or ML inference. | config.py, schema.py | pandas, sklearn | none |
| `config.py` | CONFIG | Stores configuration values, thresholds, and static lists. | none | none | none |
| `config_passion.py` | CONFIG | Stores configuration values, thresholds, and static lists. | config.py | types | none |
| `contracts.py` | SCHEMA | Defines data schemas, types, classes, or domain models. | config.py | types | network calls |
| `demo.py` | ENTRYPOINT | Runs a demo of the pipeline. | schema.py, pipeline.py, summary_utils.py | pandas | file I/O (open/print), network calls |
| `expected_spend_model.py` | CORE_LOGIC | Contains core business logic, statistical methods, or ML inference. | schema.py | pandas, numpy, sklearn | none |
| `feature_engineer.py` | CORE_LOGIC | Generates machine learning features. | schema.py | numpy, pandas | none |
| `hash_utils.py` | UTILITY | Hashing utilities. | none | none | none |
| `insight_generator.py` | CORE_LOGIC | Generates insights from categorized transactions. | contracts.py, schema.py | pandas | network calls |
| `insight_model.py` | CORE_LOGIC | Generates insights from categorized transactions. | schema.py | pandas, sklearn | file I/O (open/print), file I/O |
| `known_persons.py` | DATA_LAYER | Manages data for known persons or entities. | logger_factory.py, schema.py, config.py | pandas | network calls |
| `log_utils.py` | UTILITY | Logging configuration and utilities. | logger_factory.py | hmac, numpy, pandas | network calls |
| `logger_factory.py` | UTILITY | Logging configuration and utilities. | config.py | contextvars | network calls |
| `marketplace_subcategory.py` | DATA_LAYER | Manages data retrieval, labeling, or enrichment. | schema.py, config_passion.py, passion_utils.py, logger_factory.py | pandas, numpy, types | network calls |
| `model_benchmark.py` | CORE_LOGIC | Contains core business logic, statistical methods, or ML inference. | training_data_generator.py | numpy, pandas, sklearn, xgboost, lightgbm, catboost | file I/O (open/print), network calls |
| `model_state.py` | SCHEMA | Defines data schemas, types, classes, or domain models. | none | joblib, numpy, sklearn | network calls |
| `passion_detector.py` | CORE_LOGIC | Detects passion or specialized categories. | schema.py, config_passion.py, passion_utils.py, marketplace_subcategory.py, passion_models.py, logger_factory.py | numpy, pandas | network calls |
| `passion_insight_generator.py` | CORE_LOGIC | Generates insights from categorized transactions. | schema.py, contracts.py, config_passion.py, passion_models.py, passion_utils.py, banned_content.py, logger_factory.py | none | network calls |
| `passion_models.py` | CORE_LOGIC | Contains core business logic, statistical methods, or ML inference. | none | __future__, numpy | none |
| `passion_pipeline.py` | ENTRYPOINT | Orchestrator for the passion insights feature. | schema.py, config_passion.py, passion_utils.py, candidate.py, banned_content.py, logger_factory.py, pipeline_result.py, bootstrap.py, marketplace_subcategory.py, passion_detector.py, passion_insight_generator.py | pandas, numpy, numbers | network calls |
| `passion_utils.py` | UTILITY | Provides reusable helper functions or utilities. | logger_factory.py | pandas, numpy | none |
| `pipeline.py` | ENTRYPOINT | Central Orchestrator, defines complete Insight Engine pipeline. | logger_factory.py, model_state.py, config.py, schema.py, preprocessor.py, feature_engineer.py, seed_labeler.py, categorization_model.py, expected_spend_model.py, anomaly_detector.py, recurring_detector.py, insight_model.py, insight_generator.py, known_persons.py, log_utils.py, passion_pipeline.py | pandas, sklearn, numpy | file I/O (open/print), network calls |
| `pipeline_result.py` | SCHEMA | Defines data schemas, types, classes, or domain models. | candidate.py, passion_models.py | __future__, pandas | none |
| `preprocessor.py` | CORE_LOGIC | Contains core business logic, statistical methods, or ML inference. | config.py, schema.py, logger_factory.py | pandas, numpy | none |
| `recurring_detector.py` | CORE_LOGIC | Rule-based recurring transaction identifier. | config.py, schema.py, log_utils.py, logger_factory.py | pandas, numpy | none |
| `refactor_pipeline.py` | UTILITY | Utility script to aid in refactoring the pipeline. | none | none | file I/O (open/print), file I/O |
| `schema.py` | SCHEMA | Defines data schemas, types, classes, or domain models. | logger_factory.py | pandas | none |
| `seed_labeler.py` | DATA_LAYER | Labels seed data for training. | config.py, preprocessor.py, schema.py | pandas | none |
| `summary_utils.py` | UTILITY | Provides reusable helper functions or utilities. | schema.py | pandas | file I/O (open/print) |
| `tests/conftest.py` | TEST | Test suite or testing script. | passion_pipeline.py, log_utils.py | pytest | network calls |
| `tests/run_smoke.py` | TEST | Test suite or testing script. | pipeline.py | traceback, pandas | file I/O (open/print) |
| `tests/run_stress_heavy.py` | TEST | Test suite or testing script. | pipeline.py | pandas, numpy | file I/O (open/print) |
| `tests/run_stress_legacy.py` | TEST | Test suite or testing script. | pipeline.py, schema.py | psutil, gc, numpy, pandas | file I/O (open/print) |
| `tests/run_tests_legacy.py` | TEST | Test suite or testing script. | tests/test_phase2.py, tests/test_phase1.py | none | file I/O (open/print) |
| `tests/test_benchmark.py` | TEST | Test suite or testing script. | training_data_generator.py, config.py | numpy, pandas, pytest, sklearn | network calls |
| `tests/test_e2e.py` | TEST | Test suite or testing script. | preprocessor.py, feature_engineer.py, seed_labeler.py, categorization_model.py, expected_spend_model.py, anomaly_detector.py, recurring_detector.py, insight_generator.py, pipeline.py, schema.py, model_state.py | pandas, numpy | file I/O (open/print) |
| `tests/test_known_persons.py` | DATA_LAYER | Manages data for known persons or entities. | known_persons.py, pipeline.py, model_state.py, schema.py | pytest, pandas, numpy | none |
| `tests/test_logging_safety.py` | TEST | Test suite or testing script. | pipeline.py, recurring_detector.py, config.py, logger_factory.py, log_utils.py, schema.py | pytest, pandas | file I/O (open/print), network calls |
| `tests/test_ml_integration.py` | TEST | Test suite or testing script. | insight_model.py, schema.py | pandas, pytest, sklearn | none |
| `tests/test_model_security.py` | CORE_LOGIC | Contains core business logic, statistical methods, or ML inference. | insight_model.py | pytest | file I/O (open/print) |
| `tests/test_passion_engine.py` | TEST | Test suite or testing script. | passion_pipeline.py, passion_utils.py, pipeline_result.py, log_utils.py, passion_detector.py, config_passion.py, passion_insight_generator.py, marketplace_subcategory.py, banned_content.py, pipeline.py, schema.py, passion_models.py, bootstrap.py, contracts.py, candidate.py, config.py, hash_utils.py | pytest, pandas, numpy, inspect, types | file I/O (open/print), network calls |
| `tests/test_phase1.py` | TEST | Test suite or testing script. | schema.py, preprocessor.py, feature_engineer.py, seed_labeler.py, config.py | numpy, pandas, pytest | none |
| `tests/test_phase2.py` | TEST | Test suite or testing script. | categorization_model.py, expected_spend_model.py | pandas, pytest, numpy | none |
| `tests/test_phase3.py` | TEST | Test suite or testing script. | anomaly_detector.py, recurring_detector.py, insight_generator.py, pipeline.py | pandas, pytest | none |
| `train_and_save_models.py` | ENTRYPOINT | Script to train and save machine learning models. | training_data_generator.py, insight_model.py, schema.py | lightgbm, sklearn | file I/O (open/print), file I/O |
| `training_data_generator.py` | CORE_LOGIC | Contains core business logic, statistical methods, or ML inference. | config.py, contracts.py | numpy, pandas, sklearn | network calls |
| `tutorial_real_data.py` | ENTRYPOINT | Demonstrates ingesting real bank statements. | logger_factory.py, schema.py, pipeline.py | pandas | file I/O (open/print) |

## Hub Files

| File | Imported-By Count | Dependents |
|------|------------------|------------|
| `schema.py` | 27 | marketplace_subcategory.py, tutorial_real_data.py, pipeline.py, recurring_detector.py, anomaly_detector.py, known_persons.py, summary_utils.py, demo.py, bootstrap.py, seed_labeler.py, train_and_save_models.py, insight_generator.py, categorization_model.py, insight_model.py, passion_insight_generator.py, preprocessor.py, feature_engineer.py, expected_spend_model.py, passion_pipeline.py, passion_detector.py, tests/test_ml_integration.py, tests/test_known_persons.py, tests/test_passion_engine.py, tests/test_logging_safety.py, tests/test_phase1.py, tests/test_e2e.py, tests/run_stress_legacy.py |
| `config_passion.py` | 6 | marketplace_subcategory.py, bootstrap.py, passion_insight_generator.py, passion_pipeline.py, passion_detector.py, tests/test_passion_engine.py |
| `passion_utils.py` | 5 | marketplace_subcategory.py, passion_insight_generator.py, passion_pipeline.py, passion_detector.py, tests/test_passion_engine.py |
| `logger_factory.py` | 14 | marketplace_subcategory.py, tutorial_real_data.py, pipeline.py, recurring_detector.py, known_persons.py, bootstrap.py, schema.py, passion_insight_generator.py, preprocessor.py, log_utils.py, passion_utils.py, passion_pipeline.py, passion_detector.py, tests/test_logging_safety.py |
| `pipeline.py` | 10 | tutorial_real_data.py, demo.py, tests/run_stress_heavy.py, tests/test_phase3.py, tests/test_known_persons.py, tests/test_passion_engine.py, tests/test_logging_safety.py, tests/test_e2e.py, tests/run_smoke.py, tests/run_stress_legacy.py |
| `config.py` | 14 | pipeline.py, recurring_detector.py, known_persons.py, seed_labeler.py, contracts.py, logger_factory.py, categorization_model.py, training_data_generator.py, preprocessor.py, config_passion.py, tests/test_passion_engine.py, tests/test_benchmark.py, tests/test_logging_safety.py, tests/test_phase1.py |
| `log_utils.py` | 6 | pipeline.py, recurring_detector.py, bootstrap.py, tests/conftest.py, tests/test_passion_engine.py, tests/test_logging_safety.py |
| `contracts.py` | 5 | bootstrap.py, insight_generator.py, training_data_generator.py, passion_insight_generator.py, tests/test_passion_engine.py |
| `passion_models.py` | 5 | passion_insight_generator.py, candidate.py, pipeline_result.py, passion_detector.py, tests/test_passion_engine.py |

## Warnings

- **UNKNOWN Role**: `analyzer.py`
- **RUNTIME_DEP**: `tests/test_logging_safety.py` uses dynamic imports.
