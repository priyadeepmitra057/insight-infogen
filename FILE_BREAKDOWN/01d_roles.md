*(Part 4 of 4 - split due to length)*


### `passion_utils.py`

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
- `assert_columns_exist` (function)
- `_safe_isna` (function)
- `to_bool_strict` (function)
- `coerce_bool_column` (function)
- `sanitize_mask` (function)
- `safe_last_nonnull` (function)
- `_ALLOWED_TEMPLATE_SCALAR_TYPES` (constant)
- `validate_template_values` (function)
- `_CURRENCY_RE` (constant)
- `_INR_RE` (constant)
- `safe_numeric` (function)

#### Side Effects
file I/O

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
- **Purpose**: Provides reusable helper functions or utilities.

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
  - `config.py` (via `schema.py`) → [module/symbols used indirectly]
  - `logger_factory.py` (via `schema.py`) → [module/symbols used indirectly]
- **Direct external**:
  - `pandas` → [module]
- **Runtime / injected deps**: none

#### Identity
- **Role**: UTILITY
- **Purpose**: Provides reusable helper functions or utilities.

#### Exports
- `print_summary` (function)

#### Side Effects
file I/O (open/print), file I/O

---
