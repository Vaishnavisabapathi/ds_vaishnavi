# 📊 Trader Behaviour vs Market Sentiment  
### Data Analysis Report  

---

## 🎯 Objective  
The purpose of this analysis is to explore how **trader performance** (profit/loss, trading volume, and behavior) varies with the **Bitcoin Fear & Greed Index** — a key measure of overall market sentiment.  

The goal is to identify **patterns that reveal when traders perform best**, and how fear or greed influences decision-making.  

---

## 🧠 Data Overview  

### 1. Historical Trader Data (from Hyperliquid)
- **Rows:** ~211,000 trades  
- **Key Columns:**  
  - `Account` – Trader’s unique ID  
  - `Coin` – Traded cryptocurrency (e.g., Bitcoin)  
  - `Execution Price` – Trade execution price  
  - `Size USD` – Trade value in USD  
  - `Side` – BUY or SELL  
  - `Closed PnL` – Profit or loss after closing  
  - `Timestamp IST` – Trade execution time  

📌 *This dataset provides insights into individual trade actions and performance.*

---

### 2. Fear & Greed Index Data
- **Rows:** ~2,600 daily entries  
- **Columns:**  
  - `Date` – Calendar date  
  - `Value` – Sentiment score (0–100; lower = Fear, higher = Greed)  
  - `Classification` – Sentiment category (Extreme Fear → Extreme Greed)  

📌 *This dataset reflects collective market psychology and emotional sentiment.*

---

## ⚙️ Methodology  

1. **Data Cleaning**
   - Converted timestamps to datetime.  
   - Extracted daily date from trade timestamps.  
   - Filled missing sentiment values using forward fill (ffill).  

2. **Merging**
   - Merged both datasets on `date`.  
   - Each trade was matched with its market sentiment on that day.  

3. **Feature Engineering**
   - Calculated **PnL per USD** (profit efficiency per dollar).  
   - Created **Net Position** (+ for BUY, − for SELL).  
   - Aggregated daily metrics:  
     - Total daily PnL  
     - BUY vs SELL volume  
     - Active traders per sentiment  

4. **Exploratory Data Analysis (EDA)**
   - Compared **BUY vs SELL profit** across sentiments.  
   - Visualized **daily trading volume & profit trends**.  
   - Analyzed **sentiment distribution** over time.  

---

## 🔍 Key Insights  

- **Most Profitable Periods:**  
  Traders made higher profits during *Fear* and *Extreme Fear* phases — supporting contrarian strategies.  

- **Greed Phases:**  
  Profitability declined and volatility spiked due to overconfidence and late entries.  

- **BUY vs SELL Trends:**  
  - BUY volume rose during *Fear* (buy-the-dip behavior).  
  - SELL volume peaked during *Greed* (profit-taking).  

- **Sentiment Stability:**  
  Neutral periods showed balanced but lower returns.  

- **Trader Activity:**  
  Activity surged during Fear phases, showing emotional influence on trading decisions.  

---

## 🚀 Strategic Plan  

Based on the findings, the trading team will:  

1. **Focus Trades During Fear Phases**  
   - Historical data shows higher profitability when sentiment < 30.  
   - Example: Buy Bitcoin during *Extreme Fear* and exit when sentiment > 50.  

2. **Reduce Leverage During Greed**  
   - Maintain leverage < 2x when sentiment indicates optimism to avoid sharp drawdowns.  

3. **Integrate Sentiment Tracking**  
   - Use the Fear & Greed Index as a live signal to time entries and exits.  

4. **Diversify During Neutral Sentiment**  
   - Employ smaller range-bound trades to maintain stability.  

---

## 🏁 Conclusion  

This analysis confirms that **trading success improves during Fear-driven markets**.  
By focusing on disciplined, sentiment-aware strategies, the team can trade smarter —  
**buy when others panic, sell when others are greedy**, and stay consistent with data, not emotion.  

---

## 📁 Files Included
- `historical_data.csv` – Trader data  
- `fear_greed_index.csv` – Market sentiment data  
- `notebook_1.ipynb` – Notebook containing data merge, EDA, and visualizations  
- `README.md` – Project summary  

---

## 👩‍💻 Author
**Vaishnavi N**  
Data Science Intern   
