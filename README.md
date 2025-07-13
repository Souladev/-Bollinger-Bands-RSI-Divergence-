# -Bollinger-Bands-RSI-Divergence-
# Bollinger Bands + RSI Divergence Strategy
This is a Bollinger Bands + RSI Divergence Strategy implemented in Pine Script (version 5) for TradingView, designed to identify trading opportunities by combining Bollinger Bands breakouts with RSI divergence signals, enhanced by an optional volume filter.

# Overview
The strategy, titled "Bollinger Bands + RSI Divergence", uses Bollinger Bands to detect price breakouts or reversals and RSI divergence to confirm potential trend reversals. It incorporates a volume spike filter to enhance signal reliability and visualizes entry signals, Bollinger Bands, and divergence zones on the chart.

# How It Works
1. **Bollinger Bands Analysis**: Calculates the Simple Moving Average (basis) and standard deviation bands (upper and lower) to identify overbought (price above upper band) or oversold (price below lower band) conditions.
2. **RSI Divergence Detection**: Identifies bullish divergence (price makes lower lows while RSI makes higher lows) and bearish divergence (price makes higher highs while RSI makes lower highs) over a specified lookback period.
3. **Volume Filter**: Optionally filters signals based on volume spikes (volume exceeding 1.5x the moving average) to confirm high-conviction trades.
4. **Trade Signals**:
   - **Long Entry**: Triggered when price is below the lower Bollinger Band with bullish RSI divergence or when price crosses above the lower band with bullish divergence.
   - **Short Entry**: Triggered when price is above the upper Bollinger Band with bearish RSI divergence or when price crosses below the upper band with bearish divergence.
5. **Visual Feedback**: Plots Bollinger Bands, entry signals (triangles), and highlights divergence zones with background colors.

# Trend Analysis
The strategy does not explicitly define trend direction but uses Bollinger Bands and RSI divergence to identify potential reversal points:
- **Bullish Reversal**: Indicated by price below the lower Bollinger Band with bullish RSI divergence, visualized with green background.
- **Bearish Reversal**: Indicated by price above the upper Bollinger Band with bearish RSI divergence, visualized with red background.
- **Neutral**: No divergence detected, no background color.

# Use Cases
- **Reversal Trading**: Ideal for capturing reversals in overbought or oversold markets using Bollinger Bands and RSI divergence.
- **Customizable Trading**: Users can adjust Bollinger Bands length, standard deviation multiplier, RSI length, divergence lookback period, and volume filter settings to suit their trading style or asset.
- **Visual Feedback**: Provides clear visual cues with triangle arrows for entry signals and background colors for divergence zones, making it user-friendly for traders.

# Limitations
- **Market Assumptions**: Assumes price reversals follow RSI divergences, which may not always occur in strong trending markets.
- **Parameter Sensitivity**: Performance depends on the choice of Bollinger Bands length, RSI length, divergence lookback period, and volume filter settings. Users should backtest and optimize these parameters.
- **False Signals**: Divergence signals can be noisy in choppy markets, leading to false entries.
- **Execution**: The script defines signals but does not execute trades automatically; users must act on signals manually or integrate with a trading platform.
- **Data Dependency**: Relies on accurate price and volume data, which may vary across exchanges or low-liquidity assets.

# How to Use
1. **Add to TradingView**: Copy the Pine Script code into TradingView’s Pine Editor and apply it to a chart (e.g., BTCUSD or any asset).
2. **Configure Inputs**:
   - **Bollinger Bands Length**: Set the lookback period for the SMA and standard deviation (default: 20).
   - **Bollinger Bands StdDev**: Set the standard deviation multiplier for the bands (default: 2.0).
   - **RSI Length**: Set the lookback period for RSI (default: 14).
   - **Divergence Lookback Period**: Set the period for detecting price and RSI highs/lows (default: 5).
   - **Use Volume Filter**: Enable/disable volume spike confirmation (default: true).
   - **Volume SMA Length**: Set the lookback period for the volume moving average (default: 20).
3. **Interpret Signals**:
   - **Buy Signal**: Green triangle below the bar when price is below the lower Bollinger Band with bullish RSI divergence or crosses above the lower band with divergence (and volume spike if enabled).
   - **Sell Signal**: Red triangle above the bar when price is above the upper Bollinger Band with bearish RSI divergence or crosses below the upper band with divergence (and volume spike if enabled).
   - Monitor background colors for divergence zones (green for bullish, red for bearish).
4. **Backtest and Optimize**: Use TradingView’s strategy tester to evaluate performance and fine-tune parameters.
5. **Alerts**: Set up alerts for buy and sell signals using the provided `alertcondition` for real-time notifications.

# Summary
This strategy combines Bollinger Bands with RSI divergence to identify high-probability reversal opportunities, with an optional volume filter to enhance signal reliability. It is ideal for traders seeking to capitalize on overbought/oversold conditions with confirmation from momentum divergences. Adjust input parameters (Bollinger Bands length, RSI length, divergence lookback, volume settings) to optimize for specific assets or market conditions. The clear visualization of bands, signals, and divergence zones makes it accessible for traders, while alerts enable real-time trade monitoring.
