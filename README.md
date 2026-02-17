# Pine Strategy Indicators v6

## Overview

This repository contains a collection of custom Pine Script indicators designed for TradingView. These indicators cover momentum analysis, volume tracking, trend identification, and alternative market analysis approaches. Each indicator is production-ready and can be integrated directly into TradingView charts.

## Included Indicators

### Awesome Oscillator

**Purpose:** Measures market momentum by comparing short-term and long-term price movements.

**Core Logic:** Calculates the difference between a 5-period simple moving average and a 34-period simple moving average of the median price (hl2). The histogram changes color based on momentum direction: green when increasing, red when decreasing.

**Key Parameters:**
- **Periods:** Fixed at 5 and 34 (not configurable)

![Awesome Oscillator](images/Awesome-Oscillator.png)

**Typical Use Case:** Identifying momentum shifts and potential trend reversals. Green bars indicate strengthening bullish momentum, while red bars signal strengthening bearish momentum. Works best when combined with trend-following indicators.

### Cumulative Volume Index

**Purpose:** Tracks the cumulative flow of volume between advancing and declining days.

**Core Logic:** Continuously sums the difference between advancing volume and declining volume for a selected exchange. The indicator retrieves real-time volume data from major US exchanges (NYSE, NASDAQ, AMEX, ARCX) or aggregated market data (US Total, DJ).

**Key Parameters:**
- **Exchange:** NYSE, NASDAQ, AMEX, ARCX, US Total, DJ (default: NYSE)

![Cumulative Volume Index](images/Cumulative-Volume-Index.png)

**Typical Use Case:** Measuring institutional money flow and market breadth. Rising CVI suggests accumulation, while falling CVI indicates distribution. Divergences between CVI and price can signal potential trend changes.

### Hull Moving Average

**Purpose:** Provides a responsive trend indicator with reduced lag compared to traditional moving averages.

**Core Logic:** Uses weighted moving averages of different periods combined with a square root smoothing function. The calculation applies: WMA(2 × WMA(src, period/2) - WMA(src, period), sqrt(period)).

**Key Parameters:**
- **Length:** Averaging period (default: 9)
- **Source:** Price input (default: close)

![Hull Moving Average](images/Hull-Moving-Average.png)

**Typical Use Case:** Trend identification with minimal lag. Price crossing above HMA suggests bullish conditions, while crossing below indicates bearish conditions. The smoothness makes it suitable for dynamic support/resistance levels.

### Moon Phases

**Purpose:** Displays lunar cycle phases on price charts for alternative market analysis.

**Core Logic:** Calculates astronomical moon phases using Julian date conversions and lunar anomaly formulas. Plots new moon and full moon events directly on the chart with background color transitions between waxing (new to full) and waning (full to new) periods.

**Key Parameters:**
- **Waxing Moon Color:** Display color for waxing phase (default: blue)
- **Waning Moon Color:** Display color for waning phase (default: white)

![Moon Phases](images/Moon-Phases.png)

**Typical Use Case:** Exploring correlations between lunar cycles and market behavior. Some traders observe price patterns around new moon and full moon events. Note: Not supported on monthly timeframes.

### Visible Average Price

**Purpose:** Calculates the average price of all bars currently visible on the chart viewport.

**Core Logic:** Dynamically collects price values from all visible bars within the current chart view window and computes their arithmetic mean. The average updates automatically as the user scrolls or zooms the chart.

**Key Parameters:**
- **Source:** Price input (default: close)

![Visible Average Price](images/VisibleAverage-Price.png)

**Typical Use Case:** Quick reference for the mean price level within the visible timeframe. Useful for identifying whether current price is trading above or below the visible average, helping assess local market positioning.

## How to Use

1. Open the TradingView platform and navigate to the Pine Editor
2. Copy the Pine Script code from the desired indicator file in this repository
3. Paste the code into a new Pine Editor script
4. Save and add the indicator to your chart
5. Customize parameters through the indicator settings panel as needed

## Disclaimer

These indicators are provided for educational and informational purposes only. They are not financial advice and should not be used as the sole basis for trading decisions. Always conduct your own research and consider consulting with a financial professional before trading.
