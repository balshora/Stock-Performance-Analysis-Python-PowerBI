# 📈 Strategic Equity Analysis: Saudi Aramco vs. ExxonMobil (5-Year Performance)

## 🎯 Project Overview
This project is an end-to-end **Data Engineering and Business Intelligence** pipeline. It compares the 5-year historical stock performance of two global energy titans: **Saudi Aramco (2222.SR)** and **ExxonMobil (XOM)**. 

The goal of this project is to move beyond simple price tracking and extract actionable financial insights regarding asset growth, market volatility, and portfolio diversification strategies using **Python** and **Power BI**.

---

## 🛠️ Tech Stack & Tools
* **Language:** Python 3.x
* **Libraries:** `yfinance`, `pandas`, `numpy`, `matplotlib`, `seaborn`
* **BI Tool:** Microsoft Power BI
* **Techniques:** Data Extraction, Feature Engineering, DAX Modeling, Interactive Dashboarding, Statistical Correlation.

---

## 🐍 Phase 1: Data Engineering & Python Analysis
Instead of relying on static Excel sheets, real-time market data was programmatically extracted and engineered using Python.

* **Data Extraction & Cleaning:**
  * Pulled 5 years of historical stock data using the `yfinance` API.
  * Flattened MultiIndex columns to resolve Pandas structural complexities.
  * Handled missing values (NaN) resulting from different international stock market holidays.
* **Feature Engineering (Financial Indicators):**
  * **Moving Averages (MA20 & MA100):** Calculated to identify long-term and short-term market trends (Golden/Death Crosses).
  * **Daily Returns:** Computed the daily percentage change to measure day-to-day stock volatility.
  * **Normalized Growth:** Standardized both stocks to a base value of `1` at the start date. This allowed for an "apples-to-apples" comparison of growth trajectories, completely bypassing the USD/SAR currency differences.
* **Statistical Analysis:**
  * Calculated the **Pearson Correlation Matrix** between the daily returns of both assets to evaluate their relationship.
* **Data Exporting:**
  * Generated clean, structured `.csv` files ready for seamless integration into Power BI.

---

## 📊 Phase 2: Business Intelligence & Power BI
The exported datasets were modeled and visualized in Power BI to create an interactive, investor-centric dashboard.

* **Data Modeling & DAX:**
  * Built a centralized master `DateTable` (`CALENDARAUTO()`) and established a One-to-Many relational model connecting both company datasets.
  * Created dynamic **DAX Measures** for:
    * `Latest Close Price` & `Daily Change %`
    * `Return on Investment (ROI)`
    * `Stock Volatility` (Using `STDEV.P` on daily returns)
  * Implemented **What-If Parameters** to create an "Investment Simulator," allowing users to input an initial capital (e.g., $10,000) and dynamically calculate the `Final Investment Value`.
* **Interactive Visualizations:**
  * **Candlestick Charts:** Displaying Open, High, Low, Close (OHLC) with overlaid Moving Averages.
  * **Risk Assessment Gauge:** Visually representing the calculated standard deviation (volatility risk) of each stock.
  * **Normalized Growth Race (Line Chart):** A master comparative chart showing the exact cumulative growth of both assets from a unified starting point.
  * **Risk vs. Return (Scatter Plot):** Mapping ROI against Volatility to instantly classify asset behavior.
 
<img width="1179" height="604" alt="Screenshot 2026-05-12 at 12 08 58 AM" src="https://github.com/user-attachments/assets/617c7119-3c52-4b92-b5b2-5fd819ad9bcc" />

<img width="1177" height="616" alt="Screenshot 2026-05-12 at 12 09 11 AM" src="https://github.com/user-attachments/assets/1729c2c1-eba2-46f6-8c33-03fd8e03292b" />

<img width="1170" height="600" alt="Screenshot 2026-05-12 at 12 09 25 AM" src="https://github.com/user-attachments/assets/6c7a6bd2-07b4-439e-8536-8217963168ce" />


---

## 💡 Key Business Insights & Results

1. **The Growth Engine vs. The Defensive Anchor:**
   * **ExxonMobil** demonstrated aggressive bullish momentum, yielding a massive ROI (e.g., >170%) over 5 years, acting as a powerful growth engine, albeit with slightly higher volatility.
   * **Saudi Aramco** exhibited remarkably low volatility and resilient sideways-to-positive price action, acting as a defensive anchor for capital preservation.
2. **Portfolio Diversification (The Correlation Factor):**
   * The Python correlation analysis revealed a coefficient of **`-0.12`**. 
   * **Insight:** Despite operating in the same macro-sector (Oil/Energy), the two stocks have a statistically insignificant, slightly negative correlation. This proves that investing in both entities does *not* double the systemic risk, but rather provides excellent portfolio diversification.

---

## 🔗 Companies Analyzed

<div align="center">
  
  <a href="https://www.aramco.com/" target="_blank">
    <img src="https://upload.wikimedia.org/wikipedia/en/thumb/4/43/Saudi_Aramco_logo.svg/800px-Saudi_Aramco_logo.svg.png" alt="Saudi Aramco Logo" width="200" style="margin-right: 50px;">
  </a>
  
  <a href="https://corporate.exxonmobil.com/" target="_blank">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/73/ExxonMobil_Logo.svg/800px-ExxonMobil_Logo.svg.png" alt="ExxonMobil Logo" width="200">
  </a>

  <p><i>Click the logos to visit the official corporate websites.</i></p>
</div>
