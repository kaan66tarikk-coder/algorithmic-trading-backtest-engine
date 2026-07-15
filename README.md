# Long-Short Algorithmic Trading Backtester

A Python-based backtesting engine that simulates a dual-direction (Long/Short) trading strategy using Simple Moving Average (SMA) crossovers and the Relative Strength Index (RSI). It compares the active strategy's performance against a passive Buy and Hold benchmark.

## Strategy Logic
* **Long (1):** Triggered when the 5-day SMA is above the 20-day SMA AND the RSI is below 70.
* **Short (-1):** Triggered when the conditions above are not met.
* **Execution:** Signals are shifted by 1 day (`shift(1)`) to avoid look-ahead bias, ensuring trades are executed on the next day's open/close.

## Backtest Results (Gold Futures - GC=F)
The simulation was run using historical data starting from January 1, 2026.

* **Starting Capital:** $10,000.00
* **Strategy (Long/Short) Ending Capital:** $10,836.38 (+8.36%)
* **Buy & Hold Ending Capital:** $8,579.52 (-14.20%)

During a major market downtrend where a passive investor lost 14.2%, the algorithm managed to preserve capital and generate an 8.36% absolute return, yielding a +22.56% alpha.

## Dependencies
* pandas
* numpy
* yfinance
* matplotlib

## Installation & Usage

1. Clone the repository:
```bash
git clone https://github.com/kaan66tarikk-coder/algorithmic-trading-backtest-engine.git
```

2. Install dependencies:
```bash
pip install pandas numpy yfinance matplotlib
```

3. Run the backtest:
```bash
python trading_bot.py
```

## Disclaimer
This project is for educational purposes only. The backtesting results do not guarantee future performance. This is not financial advice.
