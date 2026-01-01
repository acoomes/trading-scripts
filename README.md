# Trading Scripts Library

A collection of Pine Script trading strategies and indicators for TradingView. These scripts are designed for drop-in compatibility—simply copy and paste into TradingView's Pine Editor.

## Repository Structure

```
trading-scripts/
├── strategies/     # Complete trading strategies with entry/exit logic
├── indicators/     # Standalone technical indicators
├── utilities/      # Helper functions and libraries
└── prompts/        # LLM prompt templates for generating new scripts
```

## Usage

1. Navigate to the desired script in this repository
2. Copy the entire Pine Script code
3. Open [TradingView](https://www.tradingview.com/)
4. Go to **Pine Editor** (bottom panel)
5. Paste the script and click **Add to Chart**

## Available Scripts

### Strategies

| Script | Description | Timeframe |
|--------|-------------|-----------|
| [EMA Crossover](strategies/ema_crossover.pine) | Dual EMA crossover with trend filter | Any |
| [RSI Mean Reversion](strategies/rsi_mean_reversion.pine) | Oversold/overbought reversals with confirmation | 1H+ |
| [Bollinger Breakout](strategies/bollinger_breakout.pine) | Volatility breakout with volume confirmation | 15m+ |

### Indicators

*Coming soon*

### Utilities

*Coming soon*

## Script Conventions

All scripts in this library follow these conventions:

- **Pine Script v6** (latest version)
- **Clear input parameters** with sensible defaults
- **Visual feedback** via plotted signals and background colors
- **Alert conditions** for automated notifications
- **Modular design** for easy customization

## Creating New Scripts

See [`prompts/new_script_template.md`](prompts/new_script_template.md) for a template you can use with LLMs (ChatGPT, Claude, Gemini) to generate new Pine Script strategies.

## Risk Disclaimer

**These scripts are for educational and research purposes only.**

- Past performance does not guarantee future results
- Always backtest thoroughly before live trading
- Never risk more than you can afford to lose
- The authors are not responsible for any financial losses

## Contributing

Contributions are welcome! Please ensure your scripts:

1. Follow the conventions listed above
2. Include clear documentation in the script header
3. Have been tested on TradingView before submission

## License

MIT License - See [LICENSE](LICENSE) for details.
