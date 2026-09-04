# Model Results

## Competition Progress

The model was improved through multiple iterations of feature engineering, modeling, and prediction optimization.

| Version  | Approach                             |       RMSLE |
| -------- | ------------------------------------ | ----------: |
| Baseline | Initial forecasting model            |     0.15433 |
| V1       | Lag-based CatBoost model             |     0.10842 |
| V2       | Direct CatBoost model                |     0.08832 |
| V5       | Enhanced temporal and hub statistics |     0.07946 |
| Blend    | Model ensemble                       |     0.07939 |
| Final    | Prediction calibration               | **0.07843** |

## Final Result

### Public Leaderboard Score

**0.07843 RMSLE**

### Leaderboard Rank

**35**

### Rank 1 Score

**0.06609 RMSLE**

## Final Model Strategy

The best-performing solution used a CatBoost-based forecasting model with:

* Calendar features
* Temporal demand patterns
* Hub-level statistical features
* Operational features
* Hub metadata
* Categorical feature handling
* RMSLE-oriented prediction optimization

The final improvement was achieved through prediction calibration.

### Calibration

A multiplicative calibration factor was applied to the final predictions:

```text
Calibration Factor: 0.982
```

This improved the leaderboard score from:

```text
0.07939 → 0.07843
```

## Key Observation

Feature engineering produced the largest performance gains during the competition.

The progression from the initial baseline to the final solution was:

```text
0.15433 → 0.10842 → 0.08832 → 0.07946 → 0.07843
```

The final model achieved approximately a 49% reduction in RMSLE compared with the initial baseline.
