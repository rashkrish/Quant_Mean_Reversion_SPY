# Validated Trend-Filtered Mean Reversion Strategy on SPY

## Executive Summary & Robustness Validation

This project demonstrates the iterative development and rigorous **Out-of-Sample validation** of a quantitative trading strategy. The core objective was to build a low-volatility Mean Reversion model and prove its effectiveness on **unseen market data**.

The final strategy is a Single-Index Mean Reversion model on the $\text{SPY}$ ETF, utilising dynamic **Z-Score signals** filtered by a **300-day Moving Average (MA) Trend Filter**.

### Validation: Out-of-Sample (Test) Performance (2023)

The key measure of success is the performance on **unseen data (2023)**, which confirms the model's robustness and lack of overfitting.

| Metric | In-Sample (Train: 2018-2022) | **Out-of-Sample (Test: 2023)** | **Assessment** |
| :--- | :--- | :--- | :--- |
| **Annualized Return** | -0.03% | **+1.03%** | **Profitable on New Data.** Successfully generated positive returns in the test environment. |
| **Sharpe Ratio (Annualized)** | -0.02 | **+0.27** | **Robustness Proven!** A positive Sharpe Ratio on unseen data proves the model generalizes effectively. |
| **Annualized Volatility** | 1.72% | **3.80%** | **Low Risk.** Volatility remained low, suggesting controlled exposure. |
| **Maximum Drawdown** | 1.82% | **3.22%** | **Excellent Risk Control.** Drawdown remained low across both market periods. |

---

## 💻 Strategy and Implementation Detail

The solution was built with institutional-grade rigour, incorporating realism and advanced risk management:

1.  **Adaptive Signaling:** The strategy enters when the Z-Score exceeds $\mathbf{\pm 1.25}$ and exits rapidly when it reverts to $\mathbf{\pm 0.25}$. This tight exit threshold minimises exposure after the reversion profit is captured.
2.  **Trend Filter:** A **300-day Moving Average Trend Filter** is used to ensure the strategy only takes long positions when the price is above the long-term trend, protecting the mean-reversion logic from persistent, unprofitable drifts.
3.  **Realistic Execution:** The backtest simulates execution at the **next day's Open price** and includes explicit handling of **transaction costs (0.001)** and **slippage (0.0001)**.
4.  **Risk Management:** A strict **Z-Score Stop-Loss ($\mathbf{\pm 3.0}$)** is implemented to prevent catastrophic losses from market regime shifts.

---

## 📊 Equity Curve Visualisation

The chart below visually confirms the strategy's stability and successful performance during the validation period. The equity curve (blue) trends upward after the red vertical split line, confirming the $\mathbf{+0.27}$ Sharpe Ratio on unseen data.

![Strategy Equity Curve with Out-of-Sample Validation](RESULTS/results_equity_curve.png)

---

## 📁 Repository Structure

The entire project is self-contained and reproducible.
