# Subsystem: 07b Passion Engine (Detection)

## Files in Scope
- `passion_detector.py` (CORE_LOGIC)
- `passion_insight_generator.py` (CORE_LOGIC)
- `marketplace_subcategory.py` (DATA_LAYER)
- `passion_models.py` (SCHEMA)
- `candidate.py` (SCHEMA)
- `banned_content.py` (RULES)

## 1. Responsibility
- **Owns**: Identifying specific merchants (like marketplaces), grouping them into discretionary subcategories (e.g. Gaming, Cycling), evaluating if the spend crosses the threshold into a "Passion", and safely generating insights.
- **Does NOT own**: Core orchestration, exception handling, or pipeline I/O.

## 2. Public Interface

### `enrich_subcategories(df) → pd.DataFrame`
- **File**: `marketplace_subcategory.py`
- **Preconditions**: Needs clean `remarks` and `amount`.
- **Postconditions**: Appends `SUBCATEGORY`, `SUBCATEGORY_CONFIDENCE`, and `IS_PASSION_ELIGIBLE`.
- **Failure modes**: Swallows regex compilation errors (silently ignores).

### `detect_passions(df) → List[PassionSignal]`
- **File**: `passion_detector.py`
- **Preconditions**: Needs enriched subcategories and amounts.
- **Postconditions**: Identifies true passions based on thresholds (duration, frequency, spend).
- **Failure modes**: Fails if time-series calculations error on NaNs.

### `generate_passion_insights(candidates) → List[str]`
- **File**: `passion_insight_generator.py`
- **Preconditions**: Needs `Candidate` models wrapped around `PassionSignal`.
- **Postconditions**: Yields text insights.
- **Failure modes**: Handled gracefully. Filters banned words.

## 3. Internal Design
- **Key algorithms**:
    - *Vectorized Merchant Resolution*: Uses numpy `select` and pandas `str.contains` to rapidly assign hundreds of subcategories without iterating rows.
    - *Distress & Anomaly Suppression*: A passion is rejected if it represents > 80% of total spend (implies distress/error) or if it triggers too many anomaly flags (implies fraud).
    - *Banned Content Checking*: Prevents generating insights for sensitive categories (adult, gambling, etc.) via a fast substring match in `banned_content.py`.
- **Owned data structures**: `PassionSignal` (stores metrics about a specific passion), `Candidate` (DTO for the text generator).
- **State model**: Stateless.
- **Concurrency model**: Vectorized where possible (`enrich_subcategories`), otherwise sequential.
- **Non-obvious implementation decisions**:
    - The threshold for a passion requires `PASSION_MIN_MONTHS` of sustained spending. A single massive purchase does not trigger a passion, only repeated behavior.

## 4. Data Contracts
| Field | Type | Required | Validation Applied | Notes |
|-------|------|----------|-------------------|-------|
| `SUBCATEGORY` | str | Output | Categorical | Granular hobby labels. |
| `IS_PASSION_ELIGIBLE` | bool | Output | None | Mask for detector phase. |

## 5. Dependencies
### Internal
| Subsystem | Why Used | Could It Fail? | Failure Handled? |
|-----------|----------|---------------|-----------------|
| `config_passion.py` | Constants & mappings | No | N/A |

### External
| Library/Service | Why Used | Could It Fail? | Failure Handled? |
|----------------|----------|---------------|-----------------|
| `pandas` / `numpy` | Vectorized math | Low | Yes, via Orchestrator. |

## 6. Test Coverage Assessment
- **Tested behaviors**: Banned word filtering, thresholding limits, date bounding logic.
- **Untested behaviors**: Subcategory collision (what if a merchant matches two patterns simultaneously in `enrich_subcategories`).
- **Missing edge cases**: Leap years/days in the month calculation for `PASSION_MIN_MONTHS`.

## 7. Issues & Risks
- **RISK**: `passion_detector.py` (lines 235-236) date math.
    - *What it does*: Calculates months active using naive `(max_date - min_date).days / 30`.
    - *Why it is a problem*: Highly imprecise. If a user buys on Jan 31 and Feb 1 (2 days apart), they bought in 2 distinct months, but the math evaluates to `2/30 = 0.06` months. This undercounts frequency.
    - *Suggested fix*: Use Pandas `to_period('M')` and count unique months.
- **SMELL**: `banned_content.py` (lines 35-37) substring matching.
    - *What it does*: Matches substrings directly (e.g., if `sex` is banned).
    - *Why it is a problem*: The classic Scunthorpe problem. If `sex` is banned, a user buying from `Sussex Books` gets flagged as banned content.
    - *Suggested fix*: Enforce regex word boundaries (`\b`) on the banned content list.

## 8. Improvement Candidates
1. Fix the Scunthorpe problem in `banned_content.py` via word boundaries.
2. Refactor `detect_passions` month counting logic to use distinct calendar months rather than a raw division by 30 days.
