# StockResearch Class Documentation

## Overview
The `StockResearch` class automates fetching, analyzing, and visualizing stock data using Yahoo Finance. It supports valuation metrics, growth, return correlations, diversification, momentum scoring, and risk analysis.

## Features
- Automatically loads tickers and configuration files.
- Downloads fundamental and OHLC data if not already present.
- Calculates **Price-to-Earnings Ratios** (TTM and Forward).
- Creates **Return Correlation Matrix**.
- Visualizes **Growth & Profitability**.
- Computes **Risk & Return Statistics** including Sharpe Ratio.
- Plots **Portfolio Performance**.
- Analyzes **Diversification by Sector**.
- Computes **Momentum Scores** over 1M, 3M, 6M.

## Usage

### Basic Execution
```bash
python stock_research.py
```

### Programmatic Usage
```python
from stock_research import StockResearch

obj = StockResearch('lists/wl.txt', 'configs/configs_short.json')
obj()  # Runs full pipeline
```

## File Structure Expectations
```
project/
│── lists/wl.txt                # One ticker per line
│── configs/configs_short.json  # {"interval": "1wk", "freq": "quarterly"}
│── data/                       # Auto-generated CSVs
```

## Outputs
| Method | Description |
|--------|-------------|
| `price_to_earnings()` | Returns list ranked by PE discount |
| `return_correlation()` | Heatmap of return correlations |
| `growth()` | Profit margins & revenue growth plots |
| `risk_and_return()` | Sharpe ratio, drawdown, performance curve |
| `diversification()` | Sector allocation donut chart |
| `momentum_score()` | Rank stocks by momentum |

## Requirements
```
pandas
numpy
yfinance
plotly
```

## Notes
- Avoid excessive API calls; Yahoo Finance may throttle.
- Ensure correct ticker symbols.
- Forward PE retrieval may occasionally return **null** depending on availability.
