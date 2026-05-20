# Primetrade.ai Data Science Intern Assignment
**Trader Performance vs Market Sentiment**

Here is my submission for the Data Science Intern assignment at Primetrade.ai. I looked into how market sentiment (using the Bitcoin Fear/Greed Index) affects trader behavior and performance on Hyperliquid.

## Setup & How to Run
1. Make sure you have Python 3.8+ installed.
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Ensure the two data files are in the `data/` directory:
   - `data/fear_greed_index.csv`
   - `data/historical_data.csv`
4. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
5. Open `notebook/main.ipynb` to see the analysis. You can also run all the cells to replicate the results.

## Methodology
- **Data Prep & Alignment:** First, I checked for missing values and duplicates. The sentiment dataset had some duplicate dates which I dropped. Then, I aligned both datasets by converting the millisecond timestamps in the historical data to daily dates.
- **Metrics:** I rolled up the trade-level data to get daily metrics per account. This includes Daily PnL, Win Rate (profitable trades / total trades), Average Trade Size, Daily Trade Count, and a Long/Short ratio.
- **Analysis:** I grouped the sentiment into broad categories (Fear, Greed, Neutral) to make comparisons easier. I also segmented traders based on how often they trade and whether they are overall profitable or not.
- **Bonus:** I built a simple Random Forest model to predict if a trader would be profitable the next day, based on their current day's stats and market sentiment.

## Key Insights
1. **Higher Win Rates in Greed, Higher Risk in Fear:** On average, traders have a better win rate during "Greed" days. However, daily PnL swings are much wilder during "Fear" periods, meaning the biggest gains and losses happen when the market is fearful.
2. **Trade Sizing Differences:** Frequent traders usually take smaller positions but increase their size a bit during Greed phases. Infrequent traders tend to take large, lumpy positions regardless of the sentiment.
3. **The Bull Trap:** The biggest difference between profitable and unprofitable traders is how they handle Fear days. Profitable traders quickly adapt and balance their exposure (L/S ratio drops close to 1), while unprofitable traders stubbornly stay long (L/S ratio spikes) even in a bear market.

## Strategy Recommendations
Based on the analysis, here are two strategy ideas:
1. **Dynamic Risk Control for Struggling Traders:** When the daily sentiment drops to "Fear," the platform could cap the Long/Short ratio or require higher margin for long positions for accounts in the unprofitable segment. The data shows they tend to bleed money by fighting the trend.
2. **Leverage Scaling for Top Traders:** Since consistent winners see their win rates peak during "Greed" days, we could temporarily increase their buying power or capital allocation when the sentiment index crosses 60 to maximize the upside.
