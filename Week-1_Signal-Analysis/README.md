## Objective
The objective of this week's project was to investigate whether a simple trend-following strategy based on moving average crossovers could outperform a passive buy-and-hold investment while reducing portfolio risk.

---
## Dataset
Historical price data was analysed to compute returns and evaluate trading strategies over time.

---
## Exploratory Analysis

The financial time series was analysed using:
- Log Return Distribution
- Q-Q Plot
- Drawdown Curve

These analyses provided insights into return behaviour, tail risk, and deviations from normality.

---
## Strategy

A Moving Average Crossover strategy was implemented.

Signal:
- Short-term Moving Average: 15 Days
- Long-term Moving Average: 75 Days

Trading Rule:
- Buy when MA(15) > MA(75)
- Exit otherwise

---
## Performance Evaluation

The strategy was compared against a buy-and-hold benchmark using:

- Annualised Return
- Annualised Volatility
- Sharpe Ratio
- Maximum Drawdown
- Equity Curve

Bootstrap confidence intervals were also computed for the Sharpe ratio.

---
## Results

The moving-average strategy achieved a higher Sharpe ratio than the buy-and-hold benchmark while simultaneously reducing maximum drawdown.

Performance analysis showed that the strategy was particularly effective during sustained market trends but underperformed during sideways market conditions due to frequent signal reversals.

---
## Key Learnings

- Computing financial returns.
- Evaluating trading strategies using risk-adjusted metrics.
- Understanding drawdown and portfolio risk.
- Interpreting Sharpe ratio and confidence intervals.
    
- Analysing trend-following strategies under different market regimes.
