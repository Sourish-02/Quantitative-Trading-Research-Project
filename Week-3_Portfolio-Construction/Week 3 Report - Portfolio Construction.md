
## Objective
The objective of this week's project was to construct a market-neutral long-short equity portfolio using technical indicators and optimize its risk-adjusted performance while satisfying portfolio constraints.

---
## Strategy Overview
A cross-sectional alpha model was developed by combining multiple technical indicators using historical **Information Coefficient (IC)** weights.

The strategy consisted of:

- Cross-sectional factor ranking
- Global IC weighted factor aggregation
- EWMA feature smoothing
- Volatility-adjusted position sizing
- Dollar-neutral portfolio construction
- Position limits and gross exposure normalization

---
## Alpha Factors
The portfolio combined multiple categories of technical indicators:
- Trend indicators
- Momentum oscillators
- Volume-based indicators
- Volatility measures

Each factor was converted into a cross-sectional percentile rank before aggregation to produce the final alpha score.

---
## Portfolio Construction
The final portfolio was built using:

| Parameter             | Value                          |
| --------------------- | ------------------------------ |
| Factor Weighting      | Global Information Coefficient |
| Feature Smoothing     | 10-Day EWMA                    |
| Risk Adjustment       | 20 & 60 Day Volatility         |
| Portfolio Type        | Dollar Neutral                 |
| Gross Exposure        | 100%                           |
| Maximum Position Size | ±10%                           |

---
## Experimental Evaluation
Several adaptive weighting approaches were investigated to improve portfolio performance.

### Experiment 1 — Rolling Information Coefficient

**Hypothesis**
Recent factor performance should be more predictive than long-term historical averages.

**Result**
- Net Sharpe: **0.2474**

**Conclusion**
Rolling IC estimates introduced significant estimation noise and substantially degraded performance.

**Decision:** Rejected.

---
### Experiment 2 — Rolling IC + Global Sign

**Hypothesis**
Only the magnitude of factor importance should adapt over time while preserving the historical direction of each factor.

**Result**
- Net Sharpe: **0.8400**

**Conclusion**
Although more stable than pure Rolling IC weighting, the strategy still underperformed the baseline Global IC approach.

**Decision:** Rejected.

---
### Experiment 3 — Information Ratio Weighting

**Hypothesis**
Factors with more stable predictive power should receive larger portfolio weights.

**Result**
- Net Sharpe: **0.8778**

**Conclusion**
Information Ratio weighting improved factor stability but failed to outperform the baseline strategy.

**Decision:** Rejected.

---
## Final Results
The final strategy retained **Global Information Coefficient weighting** while incorporating **EWMA feature smoothing** and improved portfolio normalization.

|Metric|Value|
|---|--:|
|Gross Sharpe|1.1837|
|Net Sharpe|1.0135|
|Turnover|29.5753|
|Mean Book Value|0.9913|
Compared to the original baseline, the final implementation significantly reduced portfolio turnover while achieving a modest improvement in the Net Sharpe Ratio.

---

## Key Learnings

- Constructing market-neutral long-short portfolios.
- Combining multiple alpha factors using Information Coefficient weighting.
- Applying EWMA smoothing to reduce portfolio turnover.
- Evaluating adaptive factor weighting using Rolling IC and Information Ratio methods.
- Identifying and eliminating look-ahead bias during backtesting.
- Understanding the trade-off between adaptive weighting schemes and estimation noise.

---
## Acknowledgement
This project was developed using the starter code and evaluation framework provided by the competition organizers. The strategy design, implementation, experiments, and documentation are my own.