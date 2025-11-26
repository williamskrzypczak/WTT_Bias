# WTT_Bias Recommended Settings Guide

Copyright (c) 2025 Bulldog Ventures Inc. All rights reserved.

## Overview

This guide provides optimized settings for the WTT_Bias indicator based on different trading styles, timeframes, and market conditions. The default settings are well-balanced for most scenarios, but these recommendations can help you fine-tune the indicator for your specific needs.

## Quick Reference: Best All-Around Settings

For most traders on 15-minute to 1-hour charts:

Detection Settings:
- Bias Mode: Volume (default)
- Source Mode: Auto (Realtime+History) (default)
- Lower Timeframe: 5 minutes (default)
- Neutral Deadband: 0.05 (default)
- Smoothing Length: 3 (default)
- Alert When Bias Intensity Weakens: true (default)

Visual Settings:
- Show Bias Histogram: true (default)
- Show Signal Line: true (default)
- Show Intensity Decrease Dots: true (default)
- Histogram Style: Columns (default)
- Show Bias Table: true (default)

Compression Settings:
- Doji Body Threshold: 0.15 (default)
- Require Close Breakout: false (default)
- Confirm Breakouts On Close: false (default)
- Minimum Breakout %: 0.2% (default)
- Show Breakout Markers: true (default)
- Enable Compression Alerts: true (default)

Alert Settings:
- Alerts on Bar Close: true (default)

## Settings by Trading Style

### Conservative (Fewer Signals, Higher Quality)

Best for: Swing traders, position traders, those who prefer fewer but more reliable signals

Detection Settings:
- Bias Mode: Volume
- Source Mode: Auto (Realtime+History)
- Lower Timeframe: 10-15 minutes (for 1H+ charts) or 5 minutes (for 15M-1H charts)
- Neutral Deadband: 0.10 (increased to filter noise)
- Smoothing Length: 5 (more smoothing for stability)
- Alert When Bias Intensity Weakens: true

Compression Settings:
- Doji Body Threshold: 0.12 (stricter doji definition)
- Require Close Breakout: true (wait for confirmed close)
- Confirm Breakouts On Close: true (most reliable)
- Minimum Breakout %: 0.5% (higher threshold, fewer false signals)
- Enable Compression Alerts: true

Alert Settings:
- Alerts on Bar Close: true (most reliable)

Rationale: Higher deadband and smoothing reduce false signals. Requiring close breakouts and higher percentage thresholds ensure more reliable compression signals.

### Moderate (Balanced - Default Settings)

Best for: Most day traders, active swing traders

These are the default settings - see Quick Reference section above.

Rationale: Default settings provide a good balance between signal frequency and reliability. Works well across most timeframes and market conditions.

### Aggressive (More Signals, Earlier Entry)

Best for: Scalpers, active day traders, those comfortable with more false signals

Detection Settings:
- Bias Mode: Volume
- Source Mode: Auto (Realtime+History)
- Lower Timeframe: 1-3 minutes (for 5M-15M charts) or 5 minutes (for 15M+ charts)
- Neutral Deadband: 0.02 (lower threshold, more sensitivity)
- Smoothing Length: 2 (less smoothing, faster response)
- Alert When Bias Intensity Weakens: true

Compression Settings:
- Doji Body Threshold: 0.20 (more lenient doji definition)
- Require Close Breakout: false (react to intrabar moves)
- Confirm Breakouts On Close: false (earliest signals)
- Minimum Breakout %: 0.1% (lower threshold, more signals)
- Enable Compression Alerts: true

Alert Settings:
- Alerts on Bar Close: false (intrabar alerts for faster response)

Rationale: Lower deadband and smoothing provide faster, more sensitive signals. Intrabar breakouts and lower thresholds catch moves earlier, but may produce more false signals.

## Settings by Chart Timeframe

### Scalping (1-5 minute charts)

Detection Settings:
- Bias Mode: Volume (or Ticks for faster response)
- Source Mode: Realtime only (for fastest response)
- Lower Timeframe: 1 minute
- Neutral Deadband: 0.02
- Smoothing Length: 2
- Alert When Bias Intensity Weakens: true

Compression Settings:
- Doji Body Threshold: 0.20
- Require Close Breakout: false
- Confirm Breakouts On Close: false
- Minimum Breakout %: 0.1%
- Enable Compression Alerts: true

Alert Settings:
- Alerts on Bar Close: false

Note: On very short timeframes, consider using "Ticks" mode instead of "Volume" for faster response to price changes.

### Day Trading (15 minute - 1 hour charts)

Use the default settings - see Quick Reference section above.

Note: These are the default settings, which work excellently for day trading timeframes.

### Swing Trading (4 hour - Daily charts)

Detection Settings:
- Bias Mode: Volume
- Source Mode: Auto (Realtime+History)
- Lower Timeframe: 15-30 minutes (for 4H charts) or 1 hour (for Daily charts)
- Neutral Deadband: 0.08
- Smoothing Length: 5
- Alert When Bias Intensity Weakens: true

Compression Settings:
- Doji Body Threshold: 0.12
- Require Close Breakout: true
- Confirm Breakouts On Close: true
- Minimum Breakout %: 0.3%
- Enable Compression Alerts: true

Alert Settings:
- Alerts on Bar Close: true

Note: Higher deadband and smoothing help filter noise on longer timeframes. Requiring close breakouts ensures more reliable signals.

## Settings by Market Condition

### Trending Markets

Detection Settings:
- Neutral Deadband: 0.03-0.05 (lower to catch trend changes earlier)
- Smoothing Length: 3-4 (moderate smoothing)

Compression Settings:
- Minimum Breakout %: 0.2-0.3% (standard threshold)

Rationale: In trending markets, you want to catch momentum shifts early while maintaining some filtering.

### Choppy/Ranging Markets

Detection Settings:
- Neutral Deadband: 0.08-0.10 (higher to filter whipsaws)
- Smoothing Length: 5-7 (more smoothing for stability)

Compression Settings:
- Minimum Breakout %: 0.4-0.5% (higher threshold to reduce false breakouts)
- Require Close Breakout: true (wait for confirmation)
- Confirm Breakouts On Close: true (most reliable)

Rationale: Higher deadband and smoothing reduce false signals in choppy conditions. Higher breakout thresholds ensure genuine breakouts.

### High Volatility Markets

Detection Settings:
- Neutral Deadband: 0.06-0.08 (moderate filtering)
- Smoothing Length: 4-5 (more smoothing to handle volatility)

Compression Settings:
- Minimum Breakout %: 0.3-0.4% (higher to account for normal volatility)
- Doji Body Threshold: 0.12-0.15 (standard)

Rationale: Increased smoothing and thresholds help distinguish genuine signals from normal volatility spikes.

### Low Volatility Markets

Detection Settings:
- Neutral Deadband: 0.03-0.05 (lower threshold for sensitivity)
- Smoothing Length: 2-3 (less smoothing for faster response)

Compression Settings:
- Minimum Breakout %: 0.1-0.2% (lower threshold, smaller moves matter)
- Doji Body Threshold: 0.15-0.18 (standard to slightly lenient)

Rationale: Lower thresholds and smoothing allow the indicator to respond to smaller moves in quiet markets.

## Bias Mode Selection Guide

### Volume Mode (Recommended Default)

Use when:
- Trading liquid instruments (forex majors, large-cap stocks, major indices)
- You want volume-weighted bias signals
- Trading on 15-minute charts or higher

Advantages:
- More accurate representation of actual buying/selling pressure
- Better filtering of noise
- More reliable for swing trading

### Ticks Mode

Use when:
- Trading on very short timeframes (1-5 minutes)
- You want faster response to price changes
- Volume data is unreliable or unavailable
- Trading low-volume instruments

Advantages:
- Faster response time
- Works without volume data
- More sensitive to price changes

## Source Mode Selection Guide

### Auto (Realtime+History) - Recommended

Best for: Most traders, most scenarios

How it works:
- Uses realtime proxy (uptick/downtick counting) on the live bar
- Uses lower timeframe aggregation on historical bars

Advantages:
- Best of both worlds
- Accurate realtime data on current bar
- Reliable historical data

### Realtime Only

Best for: Scalpers, very short timeframes

How it works:
- Uses realtime proxy on live bar
- Uses lower timeframe aggregation on historical bars (same as Auto)

Note: This is essentially the same as Auto mode for most use cases.

### Lower TF Only

Best for: Backtesting, when you want consistent methodology across all bars

How it works:
- Always uses lower timeframe aggregation, even on live bar

Advantages:
- Consistent methodology
- Better for backtesting
- No dependency on realtime data

Disadvantages:
- Less accurate on live bar (uses approximation instead of realtime data)

## Compression Settings Explained

### Doji Body Threshold

- 0.10-0.12: Very strict (fewer dojis, higher quality)
- 0.15 (default): Balanced
- 0.18-0.20: Lenient (more dojis, more signals)

Recommendation: Start with default (0.15), adjust based on signal frequency.

### Require Close Breakout

- false (default): Reacts to intrabar price moves (faster, but may reverse)
- true: Waits for bar to close beyond doji range (more reliable, slower)

Recommendation: Use false for day trading, true for swing trading.

### Confirm Breakouts On Close

- false (default): Allows intrabar alerts/markers (faster)
- true: Waits for bar close (most reliable, prevents disappearing signals)

Recommendation: Use false for active trading, true for conservative approach.

### Minimum Breakout %

- 0.1-0.2%: Aggressive (more signals, some false)
- 0.2% (default): Balanced
- 0.3-0.5%: Conservative (fewer signals, higher quality)

Recommendation: Adjust based on instrument volatility and your risk tolerance.

## Visual Settings Recommendations

### Minimal Setup (Clean Chart)

- Show Bias Histogram: true
- Show Signal Line: false
- Show Intensity Decrease Dots: false
- Histogram Style: Columns
- Show Bias Table: true

Best for: Traders who want essential information without clutter.

### Standard Setup (Recommended)

- Show Bias Histogram: true
- Show Signal Line: true
- Show Intensity Decrease Dots: true
- Histogram Style: Columns
- Show Bias Table: true

Best for: Most traders who want full information.

### Maximum Detail Setup

- Show Bias Histogram: true
- Show Signal Line: true
- Show Intensity Decrease Dots: true
- Histogram Style: Both (Columns + Area)
- Show Bias Table: true

Best for: Analysis, learning, detailed market study.

## Alert Configuration Recommendations

### Conservative Alert Setup

- Alerts on Bar Close: true
- Alert When Bias Intensity Weakens: true
- Enable Compression Alerts: true

Best for: Swing traders, position traders, those who want reliable signals.

### Active Trading Alert Setup

- Alerts on Bar Close: false
- Alert When Bias Intensity Weakens: true
- Enable Compression Alerts: true

Best for: Day traders, scalpers who need faster notifications.

## Performance Tips

1. Lower Timeframe Selection: Choose a lower timeframe that's 3-6x smaller than your chart timeframe for optimal historical bias calculation.

2. Deadband Tuning: If you're getting too many zero-crosses in choppy markets, increase the deadband. If signals are too late, decrease it.

3. Smoothing Balance: More smoothing = more stable but slower response. Less smoothing = faster but more noise.

4. Compression Breakouts: In volatile markets, increase the minimum breakout percentage to reduce false signals.

5. Visual Performance: If experiencing lag, disable "Both" histogram style and use "Columns" or "Area" only.

## Testing Your Settings

1. Start with defaults - They're well-balanced for most scenarios
2. Observe for 20-50 bars - See how signals behave
3. Adjust one parameter at a time - This helps you understand what each setting does
4. Document your changes - Note which settings work best for your trading style
5. Test in different market conditions - Settings that work in trends may not work in ranges

## Quick Settings Presets Summary

Conservative:
- Deadband: 0.10
- Smoothing: 5
- Breakout %: 0.5%
- Close Break: true
- Confirm Close: true

Moderate (Default):
- Deadband: 0.05
- Smoothing: 3
- Breakout %: 0.2%
- Close Break: false
- Confirm Close: false

Aggressive:
- Deadband: 0.02
- Smoothing: 2
- Breakout %: 0.1%
- Close Break: false
- Confirm Close: false

Trending Markets:
- Deadband: 0.03-0.05
- Smoothing: 3-4
- Breakout %: 0.2-0.3%
- Close Break: false
- Confirm Close: false

Choppy Markets:
- Deadband: 0.08-0.10
- Smoothing: 5-7
- Breakout %: 0.4-0.5%
- Close Break: true
- Confirm Close: true

High Volatility:
- Deadband: 0.06-0.08
- Smoothing: 4-5
- Breakout %: 0.3-0.4%
- Close Break: true
- Confirm Close: false

Low Volatility:
- Deadband: 0.03-0.05
- Smoothing: 2-3
- Breakout %: 0.1-0.2%
- Close Break: false
- Confirm Close: false

## Conclusion

The default settings are excellent for most traders. Use this guide to fine-tune based on:
- Your trading style (conservative, moderate, aggressive)
- Your chart timeframe
- Current market conditions
- Your risk tolerance

Remember: There's no "perfect" setting for everyone. The best settings are those that align with your trading style and help you make better trading decisions.

End of Recommended Settings Guide

Copyright (c) 2025 Bulldog Ventures Inc. All rights reserved.

