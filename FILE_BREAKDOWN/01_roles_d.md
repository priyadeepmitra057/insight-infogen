*(Part 4 of 4 - split due to length)*


### `log_utils.py`

#### Dependencies
- **Direct internal**:
  - `logger_factory.py` → [get_logger]
- **Transitive internal**:
  - `config.py` (via `logger_factory.py`)
- **Direct external**:
  - `hmac` → [*]
  - `numpy` → [*]
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: UTILITY
- **Purpose**: Logging configuration and utilities.

#### Exports
- `__all__` (constant/variable)
- `_DEV_SECRET_FALLBACK` (constant/variable)
- `_reset_secret_cache` (function)
- `_get_secret` (function)
- `_hmac_hex` (function)
- `_is_safe_scalar` (function)
- `log_safe_merchant` (function)
- `log_safe_text` (function)
- `verify_merchant_token` (function)

#### Side Effects
network calls

---

### `logger_factory.py`

#### Dependencies
- **Direct internal**:
  - `config.py` → [*]
- **Transitive internal**:
  - none
- **Direct external**:
  - `contextvars` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: UTILITY
- **Purpose**: Logging configuration and utilities.

#### Exports
- `generate_new_run_id` (function)
- `JSONFormatter` (class)
- `get_logger` (function)

#### Side Effects
network calls

---

### `passion_utils.py`

#### Dependencies
- **Direct internal**:
  - `logger_factory.py` → [get_logger]
- **Transitive internal**:
  - `config.py` (via `logger_factory.py`)
- **Direct external**:
  - `pandas` → [*]
  - `numpy` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: UTILITY
- **Purpose**: Provides reusable helper functions or utilities.

#### Exports
- `__all__` (constant/variable)
- `assert_columns_exist` (function)
- `_safe_isna` (function)
- `to_bool_strict` (function)
- `coerce_bool_column` (function)
- `sanitize_mask` (function)
- `safe_last_nonnull` (function)
- `_ALLOWED_TEMPLATE_SCALAR_TYPES` (constant/variable)
- `validate_template_values` (function)
- `_CURRENCY_RE` (constant/variable)
- `_INR_RE` (constant/variable)
- `safe_numeric` (function)

#### Side Effects
none

---

### `refactor_pipeline.py`

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
- **Purpose**: Utility script to aid in refactoring the pipeline.

#### Exports
- `indent_code` (function)

#### Side Effects
file I/O (open/print), file I/O

---

### `summary_utils.py`

#### Dependencies
- **Direct internal**:
  - `schema.py` → [Col]
- **Transitive internal**:
  - `logger_factory.py` (via `schema.py`)
  - `config.py` (via `schema.py`)
- **Direct external**:
  - `pandas` → [*]
- **Runtime / injected deps**: none

#### Identity
- **Role**: UTILITY
- **Purpose**: Provides reusable helper functions or utilities.

#### Exports
- `print_summary` (function)

#### Side Effects
file I/O (open/print)

---
