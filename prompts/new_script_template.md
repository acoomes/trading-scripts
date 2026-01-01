# Pine Script Generation Prompt Template

Use this template when asking an LLM (ChatGPT, Claude, Gemini, etc.) to generate new Pine Script trading strategies or indicators.

---

## The Prompt

Copy and customize the following prompt:

```
Create a Pine Script v6 trading strategy with the following specifications:

## Strategy Overview
- **Name**: [Your strategy name]
- **Type**: [Strategy (with backtesting) / Indicator (signals only)]
- **Trading Style**: [Trend following / Mean reversion / Breakout / Scalping / Swing]
- **Recommended Timeframe**: [1m / 5m / 15m / 1H / 4H / Daily]
- **Assets**: [Stocks / Crypto / Forex / Futures / All]

## Entry Conditions
Long Entry:
- [Condition 1, e.g., "RSI crosses above 30"]
- [Condition 2, e.g., "Price is above 200 EMA"]
- [Condition 3, e.g., "Volume is 1.5x average"]

Short Entry (if applicable):
- [Condition 1]
- [Condition 2]

## Exit Conditions
Long Exit:
- [Condition 1, e.g., "RSI reaches 70"]
- [Condition 2, e.g., "Price crosses below 20 EMA"]

Short Exit (if applicable):
- [Condition 1]
- [Condition 2]

## Risk Management
- Stop Loss: [Fixed % / ATR-based / Swing low / None]
- Take Profit: [Fixed % / Risk:Reward ratio / Indicator-based / None]
- Trailing Stop: [Yes (specify %) / No]
- Position Sizing: [% of equity / Fixed amount]

## Indicators to Use
- [Indicator 1 with parameters, e.g., "EMA(9) and EMA(21)"]
- [Indicator 2, e.g., "RSI(14)"]
- [Indicator 3, e.g., "Bollinger Bands(20, 2)"]

## Additional Requirements
- [ ] Include input parameters for all key values
- [ ] Add visual signals (arrows/shapes) on chart
- [ ] Include alert conditions for entries/exits
- [ ] Add info table showing current indicator values
- [ ] Color-code background for market conditions
- [ ] Include detailed comments explaining logic

## Code Style Requirements
- Use Pine Script v6 syntax
- Group related inputs together
- Use clear section separators with comments
- Follow TradingView best practices
- Make the script drop-in ready (copy-paste compatible)
```

---

## Example: Filled-In Prompt

```
Create a Pine Script v6 trading strategy with the following specifications:

## Strategy Overview
- **Name**: MACD + RSI Momentum Strategy
- **Type**: Strategy (with backtesting)
- **Trading Style**: Trend following with momentum confirmation
- **Recommended Timeframe**: 1H and 4H
- **Assets**: Crypto and Forex

## Entry Conditions
Long Entry:
- MACD line crosses above signal line
- MACD histogram is positive
- RSI is between 40 and 70 (not overbought, showing strength)
- Price is above 50 EMA

Short Entry:
- MACD line crosses below signal line
- MACD histogram is negative
- RSI is between 30 and 60 (not oversold, showing weakness)
- Price is below 50 EMA

## Exit Conditions
Long Exit:
- MACD line crosses below signal line
- OR RSI reaches 80 (overbought)
- OR Stop loss / Take profit hit

Short Exit:
- MACD line crosses above signal line
- OR RSI reaches 20 (oversold)
- OR Stop loss / Take profit hit

## Risk Management
- Stop Loss: 1.5x ATR(14) from entry
- Take Profit: 2:1 reward:risk ratio
- Trailing Stop: Yes, activate at 1:1, trail at 1x ATR
- Position Sizing: 100% of equity per trade

## Indicators to Use
- MACD (12, 26, 9) - standard settings
- RSI (14)
- EMA (50) for trend filter
- ATR (14) for stop loss calculation

## Additional Requirements
- [x] Include input parameters for all key values
- [x] Add visual signals (arrows/shapes) on chart
- [x] Include alert conditions for entries/exits
- [x] Add info table showing MACD, RSI, and position status
- [x] Color-code background green for bullish, red for bearish bias
- [x] Include detailed comments explaining logic
```

---

## Tips for Better Results

1. **Be Specific**: The more detail you provide, the better the output
2. **Include Edge Cases**: Mention what should happen in unusual situations
3. **Request Validation**: Ask the LLM to explain its logic after generating
4. **Iterate**: Start simple, then add complexity in follow-up prompts
5. **Test First**: Always backtest generated strategies before live trading

---

## Follow-Up Prompts

After receiving the initial script, you might ask:

- "Add a time filter so it only trades during London and New York sessions"
- "Add a maximum daily loss limit that stops trading after 3% drawdown"
- "Convert this strategy into an indicator-only version with alerts"
- "Add pyramiding support with a maximum of 3 entries"
- "Optimize the default parameters for Bitcoin on the 4H timeframe"

---

## Quality Checklist

Before adding a generated script to your library, verify:

- [ ] Script compiles without errors in TradingView
- [ ] All inputs are properly grouped and labeled
- [ ] Entry/exit signals appear correctly on the chart
- [ ] Alerts fire at the expected moments
- [ ] Backtest results are reasonable (no impossible returns)
- [ ] Risk management works as expected
- [ ] Script performs reasonably across different assets/timeframes
