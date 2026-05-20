# Trader Performance vs Market Sentiment Analysis

## About the Project

This project was done for the Data Science / Analytics Intern assignment at Primetrade.ai.

The main aim of this project is to understand how Bitcoin market sentiment affects trader behavior and performance on Hyperliquid.

I used two datasets:

1. Bitcoin Fear/Greed sentiment data
2. Historical trader data

The analysis checks how traders perform during different market conditions like Fear, Greed, Neutral, Extreme Fear, and Extreme Greed.

---

## Project Objective

The main questions answered in this project are:

- Does trader performance change during Fear and Greed days?
- Do traders change their trading behavior based on sentiment?
- Which trader groups perform better or take more risk?
- What simple trading rules can be suggested from the analysis?

---

## Project Structure

```text
PrimeTrade.ai/
│
├── data/
│   ├── fear_greed_index.csv
│   └── historical_data.csv
│
├── notebook/
│   └── main.ipynb
│
├── charts/
│   ├── avg_pnl_by_sentiment.png
│   ├── win_rate_by_sentiment.png
│   ├── trades_by_sentiment.png
│   ├── avg_trade_size_by_sentiment.png
│   ├── long_short_by_sentiment.png
│   └── drawdown_by_sentiment.png
│
├── summary_tables/
│   ├── sentiment_summary.csv
│   ├── drawdown_summary.csv
│   ├── frequency_segment_summary.csv
│   ├── size_segment_summary.csv
│   └── performance_segment_summary.csv
│
├── requirements.txt
└── README.md
```

---

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

## How to Run

### 1. Clone the repository

```bash
git clone https://github.com/vaibhavmangla07/PrimeTrade.ai.git
```

### 2. Go to the project folder

```bash
cd PrimeTrade.ai
```

### 3. Install required libraries

```bash
pip install -r requirements.txt
```

### 4. Open Jupyter Notebook

```bash
jupyter notebook
```

Then open:

```text
notebook/main.ipynb
```

Run all cells from top to bottom.

---

## Methodology

First, I loaded both datasets and checked their shape, missing values, and duplicate rows.

Then I converted the timestamp columns into proper date format. After that, I merged the trader data with the sentiment data using the date column.

After merging, I created important metrics such as:

- Total PnL
- Average PnL
- Win rate
- Total trades
- Average trade size
- Trading volume
- Fees
- Long/short trade count
- Drawdown proxy

These metrics were used to compare trader performance across different sentiment conditions.

---

## Key Insights

1. Trader performance was different across market sentiment conditions.
2. Extreme Greed days showed better average PnL and win rate.
3. Fear days had higher trading activity and higher average trade size.
4. Greed days showed higher drawdown risk, which means traders may take more risk during positive sentiment.
5. Frequent traders had higher average PnL, but they also had more exposure because they traded more.
6. Large size traders earned more on average, but their win rate was lower than small size traders.

---

## Strategy Recommendations

### 1. Reduce position size during Fear days

Fear days had high trading activity and larger average trade size.
So traders should avoid taking very large positions during Fear days.

This is useful for large size traders and high activity traders.

### 2. Avoid overtrading during Greed days

Greed days showed higher drawdown risk.
So traders should not increase trade frequency blindly during Greed days.

This is useful for frequent traders and high activity traders.

### 3. Use sentiment as a risk filter

Market sentiment should not be used as a direct buy or sell signal.
It should be used as an extra risk management signal along with win rate, trade size, trade frequency, and drawdown.

---

## Output

The project includes:

- Jupyter notebook
- Output charts
- Summary tables
- Short analysis and recommendations

Charts are saved in the `charts/` folder.
Summary tables are saved in the `summary_tables/` folder.

---

## Conclusion

This project shows that market sentiment has a relation with trader behavior and performance.

Traders were more active during Fear days and took larger positions. Greed days showed higher drawdown risk, which means positive sentiment can also lead to risky trading behavior.

Overall, sentiment is useful as a risk management filter, but it should not be used alone for trading decisions.

---

## Author

Vaibhav Mangla

GitHub: [https://github.com/vaibhavmangla07](https://github.com/vaibhavmangla07)   

LinkedIn: https://www.linkedin.com/in/vaibhav-mangla-097b92219/

G-Mail: vmangla0704@gmail.com
