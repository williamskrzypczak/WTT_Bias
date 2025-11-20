# Pine Script VU Meter Table Prompt

Create a Pine Script table that displays a VU meter-style analog gauge for the current histogram bias value. The meter should resemble a professional audio mixing board VU meter with the following specifications:

## Visual Design Requirements

1. **Layout**: Vertical orientation (like a traditional VU meter), with segments stacked from top to bottom
2. **Scale Range**: Display bias from -1.0 (strongest shorts/bearish) at the top to +1.0 (strongest longs/bullish) at the bottom, with 0.0 (neutral) in the center
3. **Table Dimensions**: Use 3 columns × approximately 15-20 rows to create a tall, narrow meter appearance

## Segment Structure

1. **Top Section (Shorts/Bearish - Red)**:
   - Multiple segments representing negative bias values
   - Segments should light up progressively from center upward as bias becomes more negative
   - Use red color gradient (darker red for stronger bias, lighter for weaker)
   - Thresholds: -1.0 to -0.75 (very strong), -0.75 to -0.5 (strong), -0.5 to -0.25 (medium), -0.25 to -0.1 (weak)

2. **Center Section (Neutral - Yellow/White)**:
   - Single center segment at 0.0
   - Should be highlighted when bias is near neutral (within ±0.1)
   - Use yellow or white background when active
   - Display "0" or "NEUTRAL" label

3. **Bottom Section (Longs/Bullish - Green)**:
   - Multiple segments representing positive bias values
   - Segments should light up progressively from center downward as bias becomes more positive
   - Use green color gradient (darker green for stronger bias, lighter for weaker)
   - Thresholds: 0.1 to 0.25 (weak), 0.25 to 0.5 (medium), 0.5 to 0.75 (strong), 0.75 to 1.0 (very strong)

## Visual Behavior

1. **Active Segments**: Only segments up to the current bias value should be lit/active
   - For negative bias: All segments from center up to the current bias level should light up
   - For positive bias: All segments from center down to the current bias level should light up
   - For neutral bias: Only the center segment should be active

2. **Color Intensity**: Match the histogram color intensity logic
   - Stronger bias values = darker/more intense colors
   - Weaker bias values = lighter/more faded colors
   - Use the same RGB intensity calculation as the histogram bars

3. **Labels**:
   - Top of meter: Label showing "SHORT" or the current bias value when negative
   - Center: "0" or "NEUTRAL" 
   - Bottom of meter: Label showing "LONG" or the current bias value when positive
   - Labels should highlight (white text) when that direction is active, dimmed (red/green) when inactive

## Technical Requirements

1. **Data Source**: Use `smoothedBias` variable (normalized to -1.0 to +1.0 range)
2. **Position**: Place table at `position.top_right` or `position.middle_right` for visibility
3. **Update Frequency**: Update only on `barstate.islast` to show current bias
4. **Color Calculation**: Use the same intensity/transparency calculations as the histogram to ensure visual consistency
5. **Table Styling**: 
   - Black background for inactive segments
   - Colored segments (red/green) for active segments
   - Small text size for compact appearance
   - No borders for clean look

## Column Structure

- **Column 0**: Title/scale labels (optional scale markers like -1, -0.5, 0, 0.5, 1.0)
- **Column 1**: Direction labels (SHORT at top, 0 in center, LONG at bottom)
- **Column 2**: Visual meter segments (the colored bars that light up)

## Example Behavior

- If current bias is -0.6: Red segments from center up to the -0.6 level should be lit, center segment active, all green segments off
- If current bias is 0.3: All red segments off, center segment active, green segments from center down to 0.3 level should be lit
- If current bias is 0.0: Only center segment should be active (yellow/white), all other segments off

The meter should provide an immediate visual representation of the current bias strength and direction, similar to how a VU meter shows audio levels on a mixing board.

