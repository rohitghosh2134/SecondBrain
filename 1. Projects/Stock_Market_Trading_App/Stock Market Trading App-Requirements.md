---
creation_date: 2025-08-30
tags:
  - "#Requirements"
  - "#Documentation"
---

## **Project:** [[Stock Market Trading App]]

### 1. Functional Requirements

#### 1.1 Data Ingestion & Storage
- **1.1.1** The system must be able to get **OHLC (Open, High, Low, Close)** data for **all stocks** on the **National Stock Exchange (NSE)**.
- **1.1.2** The system must sort and categorize all acquired stock data by its respective **sector**.
- **1.1.3** The system must be able to update and maintain this data on a regular basis (e.g., daily).

#### 1.2 Prediction & Analysis
- **1.2.1** The system must calculate and predict the **weekly profit** for each stock based on a pre-trained model.
- **1.2.2** The profit calculation must include **brokerage fees** to determine the final profit amount.
- **1.2.3** The system must identify and highlight the **single stock with the highest predicted profit**.
- **1.2.4** The system must provide a detailed analysis of **market lag**, explaining how price changes in one stock or sector affect others.

#### 1.3 Trading & Execution
- **1.3.1** The system must be able to place a trade for the highest-profit-predicted stock using the **FYERS API**.
- **1.3.2** The system must automatically execute a buy order based on the prediction and a sell order based on a predefined strategy.

#### 1.4 Book Maintenance & Visualization
- **1.4.1** The system must maintain a complete **trade book** or ledger. This book must log every trade, including buy/sell price, date, brokerage, and net profit/loss.
- **1.4.2** The trade book data must be accessible for display on the public-facing website.

---

### 2. User Stories
- **As a user, I want to view a ranked list of stocks by their predicted weekly profit so that I can quickly identify the best trading opportunities.**
- **As a user, I want to see a full history of all trades made by the app, including profit and loss, so that I can verify its performance.**

---

### 3. Non-Functional Requirements
- **Performance:** The prediction model must run and provide a result within a reasonable timeframe (e.g., under 1 minute) to enable timely trading decisions.
- **Security:** API keys for FYERS and MongoDB must be stored securely and not be exposed in the frontend.
- **Maintainability:** The data ingestion pipeline and prediction model should be easily retrainable.

---

### Backlog
- [ ] Add support for international stock exchanges (e.g., NYSE).
- [ ] Incorporate sentiment analysis from news articles into the prediction model.