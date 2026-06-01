# Subsystem: 07a Passion Engine (Core Orchestration)

## Files in Scope
- `passion_pipeline.py` (ENTRYPOINT / ORCHESTRATOR)
- `passion_utils.py` (UTILITY)
- `tests/test_passion_engine.py` (TEST)

## 1. Responsibility
- **Owns**:
    1. Directing the secondary pipeline focused purely on "Passion" (hobby/interest/discretionary) spending.
    2. Guarding the execution with strict row limits and crash boundaries (`strict_mode`).
    3. Normalizing data uniquely for this pipeline (e.g. parsing dates that the core pipeline might have skipped).
- **Does NOT own**: Finding core banking anomalies or categorizing broad spending.

## 2. Public Interface

### `process_pipeline(df_raw, strict_mode=True, rng=None, allow_yyyymmdd_dates=False) → PassionResult`
- **File**: `passion_pipeline.py`
- **Preconditions**: `df_raw` must have Date, Amount, Remarks columns.
- **Postconditions**: Returns a `PassionResult` dataclass containing insights, detected passion categories, and a summary.
- **Failure modes**:
    - In `strict_mode=True`, re-raises all errors (e.g., parsing failures, max row violations).
    - In `strict_mode=False`, catches all exceptions and returns a default `_neutral_passion_result()` to ensure the parent pipeline (Core Insight Engine) survives.
- **Side effects**: None (operates on copies).

## 3. Internal Design
- **Key algorithms**:
    - *Defense in Depth*: The passion engine is designed to be highly unstable but sandboxed. It re-parses dates, re-cleans amounts, and catches its own errors heavily.
    - *Sequential Substages*: Normalization -> Subcategory Enrichment -> Detection -> Insight Generation.
- **Owned data structures**: `PassionResult` (via schema).
- **State model**: Stateless.
- **Concurrency model**: None.
- **Non-obvious implementation decisions**:
    - The pipeline reads an environment variable `INSIGHT_ENGINE_PASSION_MAX_ROWS` to prevent execution on massive dataframes. This implies the passion algorithms are non-linear or computationally prohibitive on big data.

## 4. Data Contracts
| Field | Type | Required | Validation Applied | Notes |
|-------|------|----------|-------------------|-------|
| `df_raw` | pd.DataFrame | Yes | Minimum row count checks | Must be valid Pandas. |
| `PassionResult` | Dataclass | Output | None | The unified response object. |

## 5. Dependencies
### Internal
| Subsystem | Why Used | Could It Fail? | Failure Handled? |
|-----------|----------|---------------|-----------------|
| `marketplace_subcategory.py` | Enriching merchants | Yes | Caught if soft mode. |
| `passion_detector.py` | Finding passion spend | Yes | Caught if soft mode. |
| `passion_insight_generator.py`| Generating strings | Yes | Caught if soft mode. |

### External
| Library/Service | Why Used | Could It Fail? | Failure Handled? |
|----------------|----------|---------------|-----------------|
| `pandas` | Operations | High (Data issues) | Caught if soft mode. |

## 6. Test Coverage Assessment
- **Tested behaviors**: `tests/test_passion_engine.py` is huge (2.4K lines). It tests strict vs soft mode, empty inputs, max row violations, and exact data pass-throughs.
- **Untested behaviors**: Interactions between specific environment variable overrides and test mocks.
- **Missing edge cases**: Deeply nested exception types bubbling out of C-extensions inside Pandas might bypass standard Python `Exception` blocks.

## 7. Issues & Risks
- **SMELL**: Re-parsing Dates and Amounts.
    - *What it does*: `passion_pipeline.py` (lines 410-413) runs `_normalize_ts` and `safe_numeric` on the incoming dataframe.
    - *Why it is a problem*: The parent `pipeline.py` *already* parsed dates and amounts in `preprocessor.py` before passing it down. This is redundant computation and risks diverging data states (e.g., if passion parses a date differently than core).
    - *Suggested fix*: Assume the input from the Core Engine is already strongly typed, or pass the cleaned `spend_debits` dataframe into the Passion Engine instead of raw rows.

## 8. Improvement Candidates
1. Remove redundant date/amount parsing as described above.
2. The `process_pipeline` function is highly coupled to environment variables natively inside the function body (`os.getenv`). Inject these as default arguments via the `config_passion.py` layer instead.
