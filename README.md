# Bitcoin Market Sentiment Analysis: Fear vs Greed Impact on Trader Behavior

## Overview

This data science project analyzes how Bitcoin market sentiment (measured by the Fear and Greed Index) affects trader behavior and performance on Hyperliquid, a decentralized perpetual futures exchange.

## Project Objective

The goal of this analysis is to understand:
- How market sentiment correlates with trader profitability
- How trading behavior adapts under different sentiment regimes
- Whether different trader segments perform better under specific market conditions
- Actionable trading strategies based on empirical findings

## Dataset Description

### Trading Data (historical_data.csv)
- **Source:** Hyperliquid trading platform
- **Records:** ~211,000+ trades
- **Key Fields:**
  - Account (trader address)
  - Coin (trading pair)
  - Execution Price
  - Size Tokens / Size USD
  - Side (BUY/SELL)
  - Closed PnL (profit/loss)
  - Fee
  - Timestamp

### Sentiment Data (fear_greed_index.csv)
- **Source:** Alternative.me Crypto Fear & Greed Index
- **Key Fields:**
  - Date
  - Value (0-100 scale)
  - Classification (Extreme Fear, Fear, Neutral, Greed, Extreme Greed)

## Methodology

1. **Data Cleaning:** Checked for missing values, standardized column names, parsed datetime fields
2. **Feature Engineering:** Created trader segments (by trade size and activity level), win indicators
3. **Merged Analysis:** Combined trading data with sentiment data by date
4. **Statistical Analysis:** Examined PnL distributions, win rates, trade frequencies
5. **Segmentation Analysis:** Compared performance across trader types

## Key Insights

### 1. Sentiment Drives Risk-Taking
Traders take significantly larger positions during Fear periods (avg $7,816) compared to Extreme Greed ($3,112). PnL variance is highest during Greed, showing increased risk-taking when sentiment is positive.

### 2. Win Rates Peak During Extreme Greed
The highest win rate (46.5%) occurs during Extreme Greed, while the lowest (37.1%) happens during Extreme Fear. However, Extreme Greed also shows the widest PnL distribution, indicating bimodal outcomes.

### 3. Contrarian Trading is Prevalent
During Extreme Fear, more traders buy (51.1%) than sell, and during Extreme Greed, more sell (55.1%). This confirms significant contrarian trading behavior in the market.

### 4. Quality Over Quantity
Infrequent traders ($96.94 avg PnL) significantly outperform frequent traders ($42.49 avg PnL). High-size traders ($93.12 avg PnL) outperform low-size traders ($4.38).

### 5. Trade Frequency Responds to Sentiment
Trading activity is highest during Neutral and Greed periods, while Fear periods see reduced activity.

## Strategy Recommendations

### Strategy 1: Contrarian Position Sizing
- **When:** During Extreme Fear periods
- **Action:** Increase position size (2-3x normal) while others reduce exposure
- **Rationale:** Contrarian positions during excessive Fear can capture rebounds

### Strategy 2: Selective Trading During Greed
- **When:** During Extreme Greed periods
- **Action:** Reduce position size, be prepared to take profits or shorts
- **Rationale:** High variance during Greed makes smaller positions safer

### Strategy 3: Quality Over Quantity
- Limit daily trades to high-conviction setups
- Avoid overtrading through strict entry criteria

## Tools Used

- **Python 3.13** - Programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Matplotlib** - Static visualization
- **Seaborn** - Statistical visualization
- **Jupyter Notebook** - Interactive development environment

## Project Structure

```
bitcoin_sentiment_analysis/
│
├── analysis.ipynb          # Main analysis notebook
├── README.md               # This file
├── requirements.txt        # Python dependencies
└── data/
    ├── historical_data.csv  # Hyperliquid trading data
    └── fear_greed_index.csv # Fear & Greed Index data
```

## Instructions to Run

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd bitcoin_sentiment_analysis
   ```

2. **Create virtual environment (recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook analysis.ipynb
   ```

5. **Run the notebook:**
   - Open `notebook.ipynb` in Jupyter
   - Run cells sequentially from the beginning
   - All charts and insights will be generated automatically

## License

This project is for educational purposes as part of a data science internship assignment.

## Author

Data Science Intern | 2024
