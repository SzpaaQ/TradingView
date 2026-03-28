# MTF Trend + EMA/MA + Volume Candle Overlay

## Overview
This TradingView Pine Script indicator combines:

- Multi-Timeframe Trend Analysis (MTF)
- Configurable Moving Averages (EMA / SMA)
- Volume-based Candle Overlay (transparency filter)

The goal of this script is to provide a **clean, readable market structure view** enhanced with **volume context**, without breaking native TradingView styling.

---

## Features

### 1. Multi-Timeframe Trend (MTF)
The script analyzes trend direction across multiple timeframes:

- 5M
- 15M
- 1H
- 4H
- 1D

Trend definition:
- Bullish → price above MA + MA rising
- Bearish → price below MA or MA falling

Displayed as a table in the top-right corner.

---

### 2. Moving Averages (EMA / SMA)

You can choose:
- EMA (default)
- SMA

Four independent moving averages:
- MA #1 (default: 21)
- MA #2 (default: 50)
- MA #3 (default: 99)
- MA #4 (default: 200)

These are plotted directly on the chart and **fully customizable via TradingView Style panel**.

---

### 3. Volume Candle Overlay

This is a visual layer applied on top of candles.

Instead of replacing candles, it **modifies their visibility based on volume**.

#### How it works:
- Volume is normalized over a lookback window
- Each candle gets a transparency value:
  - High volume → less transparent (more visible)
  - Low volume → more transparent (faded)

#### Result:
- Important candles stand out
- Low-volume noise fades out

---

## Settings

### Volume Candle

| Setting | Description |
|--------|------------|
| Enable Volume Candle Overlay | Turns overlay ON/OFF |
| Bullish Color | Color for bullish candles |
| Bearish Color | Color for bearish candles |
| Volume Lookback | Number of candles used to normalize volume |
| Min Transparency (High Volume) | Visibility of high-volume candles |
| Max Transparency (Low Volume) | Fade level for low-volume candles |

---

## How It Works (Technical)

### Volume Normalization
```text
volNorm = (volume - lowest(volume)) / (highest(volume) - lowest(volume))
