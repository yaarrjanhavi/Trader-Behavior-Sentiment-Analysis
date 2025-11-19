# 📈 Junior Data Scientist – Trader Behavior Insights

## Project Overview
This project was completed as part of the application process for the Junior Data Scientist role at [Company Name, e.g., Bajarangs/PrimeTrade.ai].

**Objective:** To explore and quantify the relationship between **Bitcoin market sentiment** (Fear/Greed Index) and **trader performance** on the Hyperliquid derivatives exchange. The goal is to uncover behavioral patterns that distinguish profitable traders during extreme market conditions.

## 💾 Data Sources
Two primary datasets were utilized for this analysis:
1.  **Historical Trader Data (Hyperliquid):** Granular, trade-level data including `Closed PnL`, `Side` (Buy/Sell), `Execution Price`, and `Timestamp`.
2.  **Bitcoin Market Sentiment (Fear/Greed Index):** Daily sentiment readings (`value` and `classification: Fear/Greed`).

*Note: Due to data privacy/size constraints, the full raw datasets are not included in this repository. Links to the original datasets were provided in the assignment description.*

## ⚙️ Methodology and Analysis

### 1. Data Cleaning & Integration
* **Time Synchronization:** Trader timestamps (IST/UTC) were standardized and aggregated to the daily level to align with the daily Fear/Greed Index.
* **Merging:** Trade data was joined with sentiment data on the `Date` key, ensuring every trade was mapped to the corresponding day's market sentiment.

### 2. Feature Engineering
Key performance metrics were calculated, grouped by the `classification` (Fear vs. Greed):
* **Performance Metrics:** Mean Closed PnL, Total PnL, and Win Rate (for trades where PnL > 0).
* **Behavioral Metrics:** Average position size (`Size USD`) and **Trade Direction** (`Side`) split for the top N% of profitable accounts.

### 3. Key Findings & Insights
*(Replace these bullet points with your actual results. Be precise and bold the actionable insights.)*

* **Sentiment Impact:** The mean Closed PnL for all traders was statistically **X% lower** during periods classified as 'Greed' compared to 'Fear' days (p-value = [Your P-Value]).
* **Contrarian Signal:** **Top 10% of successful traders** demonstrated a distinctly **contrarian behavior**. During periods of **Extreme Fear (Index < 25)**, their ratio of **BUY/LONG** trades was **Y% higher** than their baseline, suggesting they buy into panic.
* **Retail Behavior:** Unsuccessful traders were found to disproportionately increase their **average trade size** by Z% during 'Extreme Greed' days, indicating over-leveraging and FOMO-driven losses.

## 📊 Results and Visualizations

*Include your best visualizations here. Use image links to your files in the `reports/figures` folder.*

**Figure 1: Closed PnL Distribution by Sentiment**
![Box plot comparing Closed PnL distribution between Fear and Greed days](reports/figures/pnl_distribution_boxplot.png)

**Figure 2: Successful Trader Direction During Extreme Fear**
![Bar chart showing the ratio of Buy vs. Sell trades for top traders during Fear days](reports/figures/successful_trader_behavior.png)

## 🛠️ How to Run the Project Locally

To reproduce this analysis, please follow these steps:

### 1. Requirements
* Python 3.8+
* The required libraries are listed in `requirements.txt`.

### 2. Environment Setup
```bash
# Clone the repository
git clone [YOUR-GITHUB-REPO-URL]
cd Trader-Behavior-Sentiment-Analysis

# Create and activate a virtual environment (optional, but recommended)
python -m venv venv
source venv/bin/activate  # On Linux/macOS
# .\venv\Scripts\activate # On Windows

# Install dependencies
pip install -r requirements.txt
