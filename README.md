# Bitcoin Trading Strategy Analysis

## Project Overview

This project implements a technical analysis-based trading strategy for Bitcoin (BTCUSDT) using multiple timeframes. The strategy combines Exponential Moving Averages (EMA), Relative Strength Index (RSI), and Bollinger Bands to generate buy signals with predefined stop-loss and take-profit levels.

## Strategy Description

### Technical Indicators
- **EMA Fast**: 20-period Exponential Moving Average
- **EMA Slow**: 50-period Exponential Moving Average  
- **RSI**: 14-period Relative Strength Index
- **Bollinger Bands**: 20-period with standard deviation

### Entry Conditions
A buy signal is generated when:
- Fast EMA > Slow EMA (uptrend)
- RSI > 30 (not oversold)
- Price < Lower Bollinger Band (potential bounce)

### Risk Management
- **Stop Loss**: 7% below entry price
- **Take Profit**: 5% above entry price
- **Trade Size**: $1,000 per trade
- **Initial Capital**: $100,000
- **Trading Fee**: 0.11% per trade

## Results Analysis

### 1-Hour Timeframe Performance
- **Total Trades**: 35
- **Win Rate**: 57.14% (20 winning trades, 15 losing trades)
- **Average Return**: -0.63% per trade
- **Maximum Profit per Trade**: $48.90 (5% - 0.11% fee)
- **Maximum Loss per Trade**: -$71.10 (-7% - 0.11% fee)
- **Final Equity**: $100,320.40 (net profit: $320.40)

### Key Performance Metrics
- **Maximum Profit Potential**: $48.90 per winning trade
- **Maximum Loss Potential**: -$71.10 per losing trade
- **Risk-Reward Ratio**: 1:1.45 (favorable)
- **Total Return**: 0.32% over the testing period
- **Maximum Drawdown**: Approximately $928.60

## Files Structure

```
├── strategy.py              # Main strategy implementation
├── data/
│   ├── BTCUSDT_1h.csv      # 1-hour timeframe data
│   └── BTCUSDT_30m.csv     # 30-minute timeframe data
├── results_1h.csv          # Trading results for 1h timeframe
├── results_30m.csv         # Trading results for 30m timeframe
├── report_1h.png          # Performance visualization (1h)
├── report_30m.png         # Performance visualization (30m)
├── notebook.ipynb         # Jupyter notebook analysis
├── logic_notes.md         # Strategy logic documentation
└── 検証パラメータ.md       # Parameter verification notes
```

## Installation & Usage

### Prerequisites
```bash
pip install pandas numpy matplotlib ta
```

### Running the Strategy
```bash
python strategy.py
```

This will:
1. Load historical data from both timeframes
2. Calculate technical indicators
3. Generate trading signals
4. Execute backtest with risk management
5. Generate performance reports and visualizations
6. Save results to CSV files

## Strategy Parameters

| Parameter | Value | Description |
|-----------|-------|-------------|
| EMA_FAST | 20 | Fast EMA period |
| EMA_SLOW | 50 | Slow EMA period |
| RSI_LOW | 30 | RSI oversold threshold |
| RSI_HIGH | 70 | RSI overbought threshold |
| BB_WINDOW | 20 | Bollinger Bands period |
| STOP_LOSS | 0.07 | 7% stop loss |
| TAKE_PROFIT | 0.05 | 5% take profit |
| FEE_RATE | 0.0011 | 0.11% trading fee |
| CAPITAL | 100000 | Initial capital |
| TRADE_SIZE | 1000 | Position size per trade |

## Performance Insights

### Strengths
- **Positive Risk-Reward Ratio**: 1:1.45 ratio favors profitable trades
- **Consistent Trade Size**: Fixed $1,000 position size reduces risk
- **Clear Exit Rules**: Predefined stop-loss and take-profit levels
- **Multiple Timeframe Analysis**: Provides comprehensive market view

### Areas for Improvement
- **Low Win Rate**: 57.14% win rate could be improved
- **Small Net Profit**: 0.32% return over the period is modest
- **High Drawdown**: Maximum drawdown of ~$928 suggests risk management could be enhanced

### Risk Analysis
- **Maximum Single Trade Loss**: -$71.10 (7% + fees)
- **Maximum Single Trade Profit**: +$48.90 (5% - fees)
- **Worst Case Scenario**: Continuous losing trades could result in significant drawdown
- **Best Case Scenario**: Consistent winning trades could generate steady profits

## Recommendations

1. **Parameter Optimization**: Test different EMA periods, RSI thresholds, and stop-loss/take-profit levels
2. **Position Sizing**: Consider variable position sizing based on volatility
3. **Additional Filters**: Add volume analysis or market regime detection
4. **Risk Management**: Implement maximum daily loss limits
5. **Market Conditions**: Test strategy performance across different market conditions

## Disclaimer

This is a backtesting analysis and should not be considered as financial advice. Past performance does not guarantee future results. Always conduct thorough research and consider consulting with financial professionals before implementing any trading strategy.

## License

This project is for educational and research purposes only. 
