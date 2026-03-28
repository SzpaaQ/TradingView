# MTF Trend + EMA/MA + Volume Candle Overlay

## Overview
This TradingView Pine Script indicator combines:

- Multi-Timeframe Trend Analysis (MTF)
- Configurable Moving Averages (EMA / SMA)
- Volume-based Candle Overlay (transparency filter)

---

## Features

### 1. Multi-Timeframe Trend (MTF)
Analyzes trend across:
- 5M, 15M, 1H, 4H, 1D

Bullish → price above MA + MA rising  
Bearish → otherwise

---

### 2. Moving Averages
- EMA or SMA
- 4 independent lines (21, 50, 99, 200 default)
- Fully editable in TradingView **Style tab**

---

### 3. Volume Candle Overlay

Overlay modifies candle visibility based on volume.

### Volume Normalization
volNorm = (volume - lowest(volume)) / (highest(volume) - lowest(volume))

### Transparency Logic
- High volume → visible candle  
- Low volume → faded candle  

### Implementation
Uses:
barcolor()

This preserves native candles and Style settings.

---

## Settings

### Volume Candle
- Enable Volume Overlay
- Bullish Color
- Bearish Color
- Volume Lookback
- Min Transparency (High Volume)
- Max Transparency (Low Volume)

---

## EMA Color Settings

Default:
color.black

To change:
1. Open indicator settings
2. Go to Style tab
3. Modify MA colors

---

## If EMA Colors Don’t Work

Cause:
Using plotcandle()

Fix:
Use barcolor() only

---

## Recommended Setup

### Clean View
- Bull → white
- Bear → light gray
- Min transparency: 40–60
- Max transparency: 80–90

### Scalping
- Lower min transparency
- Lookback: 20–30

---

## Use Cases

- Trend confirmation
- Volume filtering
- Scalping setups
- Structure + volume analysis

---

## Limitations

- No separate wick coloring
- Volume depends on lookback
- Overlay affects full candle

---

## Installation

1. Open TradingView
2. Paste script into Pine Editor
3. Add to chart

---

## License

MIT
