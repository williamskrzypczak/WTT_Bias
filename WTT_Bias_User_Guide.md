# WTT_Bias Indicator User Guide

© 2025 Bulldog Ventures Inc. All rights reserved.

---

## Overview

WTT_Bias estimates intrabar directional pressure by comparing upticks to downticks and allocating volume into bullish or bearish buckets. The oscillator normalizes the result to a -1.0 to +1.0 scale, applies a configurable neutral deadband, then smooths the output to highlight sustained bias shifts. Visual components—histogram, signal line, analog bias meter, and zero-cross markers—help you judge trend direction, strength, and momentum changes at a glance.

---

## Quick Start

1. Add `WTT_Bias R1.26` to your chart on TradingView.
2. Keep the default `Detection Settings` unless you already have a lower timeframe preference.
3. Enable or disable `Visual Settings` elements (histogram, signal line, bias meter, zero-cross markers) based on how much on-chart detail you want.
4. Configure alerts by selecting the built-in alert conditions after adding the script; set a frequency (close or intrabar) that matches your workflow.
5. Watch for:
   - Histogram bars transitioning above/below zero (`Bias` plot).
   - Analog bias meter shifting toward `SHORT` or `LONG`.
   - Zero-cross triangles on the histogram or center cell.
   - Intensity dots on the signal line showing weakening momentum.

---

## Input Reference

### Detection Settings
- `Bias Mode`: Choose **Volume** (default) to weigh buy/sell volume changes or **Ticks** to count upticks vs downticks.
- `Source Mode`: Set how the indicator sources data:
  - **Auto (Realtime+History)** (default) uses realtime proxy for the live bar and lower timeframe aggregation historically.
  - **Realtime only** keeps realtime proxy on the live bar and lower timeframe aggregation for history.
  - **Lower TF only** always uses the specified lower timeframe aggregation.
- `Lower Timeframe (for history)`: Pick a timeframe below your chart TF (default `10` minutes) to approximate intrabar bias on historical bars.
- `Neutral Deadband`: Suppresses small oscillations around zero by treating values within ±deadband as neutral (default `0.05`).
- `Smoothing Length`: Simple moving average length applied after deadbanding (default `3`).
- `Alert Threshold`: Triggers alert conditions when smoothed bias crosses ±threshold (default `0.20`).
- `Alert When Bias Intensity Weakens`: Optional alert when bullish or bearish momentum eases and the signal line dot appears.

### Visual Settings
- `Show Bias Histogram`: Displays bias as columns from -1 to +1 (default on).
- `Show Signal Line`: Overlays the smoothed bias line with lime (bullish) and reddish-pink (bearish) coloring (default off).
- `Show Bias Meter`: Renders the analog bias meter table in the bottom-right corner (default on).
- `Show Zero-Cross Markers`: Adds triangle markers at histogram level when bias crosses zero (default on).
- `Show Intensity Decrease Dots`: Places dots on the signal line when bias intensity weakens (default on when signal line is enabled).

### Alert Settings
- `Alerts on Bar Close (More Reliable)`: If enabled (default), alerts evaluate on confirmed bar closes; when disabled, alerts may trigger intrabar.

### Colors
- Customize bullish, bearish, neutral, zero-line, zero-cross marker colors, plus transparency for histogram and line. Align these with your chart theme for clarity.

---

## Visual Components

- **Bias Histogram**: Colored columns show the smoothed bias. Color intensity adapts to strength—darker for strong bias, lighter for weak bias. Zero bars use the `Zero Color`.
- **Signal Line**: Optional line matching histogram values. Lime points to bullish bias, reddish-pink indicates bearish, gray marks neutral.
- **Intensity Decrease Dots**: Circle markers on the signal line flag when momentum softens from strong to weak.
- **Zero-Cross Markers**: Triangle up/down markers at the zero line indicate bias flips; colors follow `Zero-Cross Marker Color`.
- **Analog Bias Meter**:
  - Title row reminds you the display reflects directional bias.
  - Middle row labels `SHORT`, `0`, and `LONG`, highlighting the active side.
  - Bottom row uses a red-to-green gradient (with neutral center cell) to represent current and prior bar intensity.
  - Center cell shows arrows or “NEUTRAL”; dots plus reversed arrows denote easing intensity; ▲/▼ replace text when a zero-cross occurs.

---

## Alerts

The indicator emits at most one alert per bar. Priority order:
1. Bias flips above or below zero.
2. Bias crosses the positive or negative alert threshold.
3. Optional intensity decrease events (when enabled).

To use alerts:
- Add the script to your chart and open TradingView’s `Alerts` dialog.
- Choose `WTT_Bias R1.25` as the condition and select the desired event.
- Set frequency consistent with the `Alerts on Bar Close` option.
- Customize the message if needed (default includes the symbol and event).

---

## Workflow Tips

- Pair the oscillator with higher timeframe trend analysis; strong positive bias during an uptrend highlights favorable pullbacks.
- Adjust `Lower Timeframe (for history)` if your chart timeframe changes. Aim for 3–6× smaller than the chart timeframe for smoother historical bias.
- Increase `Neutral Deadband` in choppy markets to reduce false flips; lower it when you want earlier signals.
- Enable the signal line and intensity dots when monitoring momentum transitions; disable them for a minimal chart footprint.
- Use alerts alongside the analog meter—alerts notify you instantly, while the meter helps you gauge strength and direction visually.

---

## Troubleshooting

- **No bias values on historical bars**: Confirm `Lower Timeframe (for history)` is lower than the chart timeframe and that the symbol has sufficient history.
- **Frequent zero-cross alerts in sideways markets**: Raise `Neutral Deadband` or `Alert Threshold` to filter minor oscillations.
- **Table not visible**: Ensure `Show Bias Meter` is enabled and your chart has space in the bottom-right corner. Zoom out or move other drawings if necessary.
- **Alerts firing twice per bar**: Enable `Alerts on Bar Close` to lock evaluation to confirmed closes.

---

## Version Notes

This guide covers features in `WTT_Bias R1.26`. Review the in-script revision history for detailed change notes when new releases ship.

---

## Support

For feature requests, bug reports, or licensing inquiries, contact WaveRider Trading Technologies via your usual Bulldog Ventures Inc. channel.

