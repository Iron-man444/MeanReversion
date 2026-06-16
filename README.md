# MeanReversion
Meanreversoin fakout percantage system

# Universal Anti-Breakout RSI (MT5 Expert Advisor)

This repository contains the source code for the **Universal Anti-Breakout RSI**, an automated trading robot (Expert Advisor) developed for MetaTrader 5 (MQL5). 

The core philosophy of this EA is to capitalize on market reversals by fading false breakouts. Instead of chasing the trend, it places pending limit orders outside of recent support and resistance zones, utilizing a Relative Strength Index (RSI) filter to avoid "catching falling knives".

## 📈 Strategy Overview

The system operates strictly on **Buy Limit** and **Sell Limit** orders. 

1. **Extremum Identification:** The EA scans a defined number of recent bars to identify the local highest high and lowest low.
2. **RSI Filtering:** Before placing any orders, it checks the current RSI value:
   * **Sell Setup:** If the RSI is overbought (e.g., >= 60.0), it sets a Sell Limit order slightly *above* the highest high.
   * **Buy Setup:** If the RSI is oversold (e.g., <= 40.0), it sets a Buy Limit order slightly *below* the lowest low.
3. **Trade Management:** The EA uses percentage-based Take Profit and Stop Loss levels calculated directly from the entry price. 
4. **Order Cleanup:** To keep the trading environment clean, pending orders are assigned an expiration time, and any unexecuted orders are automatically deleted at the opening of a new bar.

## ⚙️ Key Features & Parameters

The EA is highly customizable through its input parameters, which are divided into logical groups:

### 1. Money Management
* **`FixLots` (0.1):** The fixed lot size to trade if dynamic risk is disabled.
* **`RiskPercent` (2.0):** Calculates position size based on the account balance and stop-loss distance. If set to `0`, the EA defaults to `FixLots`.

### 2. Anti-Breakout Strategy (Reversal Only)
* **`LimitDistPct` (0.05):** The distance (in percentage) beyond the recent high/low where the limit order will be placed.
* **`TpPercent` (0.8):** Take Profit distance (in percentage). Designed to catch the initial rejection/bounce.
* **`SlPercent` (0.4):** Stop Loss distance (in percentage). Keeps risk tight in case a genuine breakout trend begins.

### 3. RSI Filter
* **`RsiPeriod` (14):** The lookback period for the RSI indicator.
* **`RsiOverbought` (60.0):** The threshold above which the EA is permitted to look for Sell Limit opportunities.
* **`RsiOversold` (40.0):** The threshold below which the EA is permitted to look for Buy Limit opportunities.

### 4. Time & Strategy settings
* **`Timeframe` (PERIOD_H1):** The default chart timeframe the EA operates on.
* **`BarsN` (5):** The number of historical bars analyzed to determine the local high and low.
* **`ExpirationHours` (12):** The validity lifespan of the pending Limit orders in hours.


*Disclaimer: This Expert Advisor is provided for educational and experimental purposes. Always forward-test on a demo account before risking real capital.*


<img width="1900" height="556" alt="Screenshot 2026-05-07 025621" src="https://github.com/user-attachments/assets/c930d48f-56d6-4b94-aa18-5bcdfc10a16d" />



<img width="1000" height="500" alt="Screenshot 2026-05-07 030014" src="https://github.com/user-attachments/assets/9d6425ed-9094-4c5e-9ad2-8f9518e9def2" />

LIVE RESULTS OF mean.ex5  05-28 TO 06-16

<img width="1337" height="816" alt="image" src="https://github.com/user-attachments/assets/38c78d03-377e-4343-b6c5-30864fd9c6da" />
<img width="1898" height="857" alt="image" src="https://github.com/user-attachments/assets/e4dc3768-49f8-46de-939b-20420a3de03e" />

WITH THAT SETTINGS

<img width="902" height="551" alt="image" src="https://github.com/user-attachments/assets/cc7b3198-f0e9-46bd-9874-1bcc77cba31b" />





