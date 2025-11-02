🎯 Project Overview

A comprehensive cryptocurrency portfolio management and analytics platform integrating real-time market data, macroeconomic indicators, and AI-driven forecasting.
The system will provide long-term investment insights using data visualisation, algorithmic macro scoring, and predictive modelling.
All features will be accessible through a standalone executable (AIO) with a simple user interface.

✅ Core Requirements (Must Have)
1. Real-Time Market Data
Live price feeds for major crypto assets (BTC, ETH, SOL, BNB, HYPE) via WebSockets.
Live trading volume updates for the same assets.
Efficient asynchronous handling using asyncio and threading to prevent UI blocking.

2. Historical Market Data
Fetch OHLCV (Open, High, Low, Close, Volume) data for all tracked assets using REST APIs.
Maintain historical datasets for analysis and backtesting.

3. Data Visualisation
Display price action in candlestick format using matplotlib or mplfinance.

Include:
Live price line
Volume bars
Moving averages (MA20 / MA50)
Auto-scrolling chart view with right offset for improved readability.

5. Macroeconomic Data Integration
Retrieve macroeconomic indicators such as:
Interest rates
Inflation
M2 money supply
GDP growth
Employment data

Data fetched via public APIs (e.g. FRED) or asynchronous web scraping.
Plot this data in matplotlib for comparative analysis alongside crypto metrics.

5. Macro Score Algorithm
Develop a macro score (0–100) to quantify global economic strength.
Weighted composite index based on:
GDP growth
Inflation
Interest rates
Unemployment

Risk sentiment indicators (e.g., DXY, VIX, ADR)
Visualise the score as a dynamic indicator (similar to the Fear & Greed Index).

6. Long-Term ROI Forecasting Algorithm
Estimate expected return on investment (ROI) over a defined horizon (e.g. 6–12 months).
Inputs include:
Moving averages
Macro score
Seasonality trends
Market cycles

Output: target price and optimal selling month.

7. Seasonality and Cycle Analysis
Integrate statistical seasonality:
Historical monthly/quarterly performance
4-year Bitcoin halving cycle analysis
Identify bullish/bearish biases (e.g. Q4 outperformance).

8. Asynchronous Data Scraping
Use asynchronous techniques (aiohttp, asyncio) to gather obscure or delayed data not provided by APIs.
Examples:
Central bank speeches
FOMC minutes summaries
Macroeconomic forecasts

9. LLM Chatbot Integration
Integrate a lightweight Local/Hosted LLM chatbot trained or fine-tuned on:
The project’s own macro and ROI algorithms

Historical data and economic indicators
Users can ask:
“What is the current macro score trend?”
“How might BTC perform next quarter based on historical seasonality?”

Acts as an intelligent assistant for interpreting model results.

10. Unified Executable Application
All functionality combined into a standalone .exe file built with PyInstaller.
GUI-based navigation to:
View portfolio data
Inspect live charts
Check macro dashboard
Interact with AI assistant

🟡 Important (Should Have) Features
Feature	Description
Chrome Extension Integration:	Optional API bridge to portfolio tracking sites (CoinMarketCap, CoinStats). Enables quick import of holdings.

Advanced TA Indicators:	Add support/resistance, RSI, MACD, and basic liquidity analysis.

Improved UI Framework	Transition from CLI to a full GUI (e.g., using Tkinter, PyQt, or Dash).

Cloud Data Syncing:	Save user preferences and last known data to cloud for portability.

🟢 Optional (Could Have) Features
Feature	Description
Sentiment Analysis Engine	Perform NLP on Twitter, Reddit, and news data using transformers or nltk. Quantify market sentiment.

Whale Wallet Tracking	Track large on-chain movements to infer institutional sentiment.

Cross-Asset Comparison	Compare crypto performance against Gold, NASDAQ, and S&P500 indices.

Alert System	Notifications for sudden macro score drops, volatility spikes, or target ROI reached.

❌ Out of Scope (Won’t Have for Now)
Feature	Reason for Exclusion
Automated Trading / Execution	Requires exchange API keys, trading permissions, and compliance — beyond FYP ethical scope.

Full DeFi Wallet Integration	Blockchain APIs are inconsistent and often require paid endpoints (Etherscan, Glassnode).

Black Swan Event Prediction	Would require extensive NLP models, global risk datasets, and advanced ML pipelines.

Full Mobile App Development	Out of time scope; instead, responsive desktop executable will be delivered.

Real-Time Sentiment Data via Paid APIs	Premium APIs like LunarCrush, Santiment, or Glassnode are subscription-based.

Reinforcement Learning Auto-Portfolio	Advanced ML topic suitable for postgraduate research, not BSc time frame.

Continuous Cloud Deployment	Hosting cost and maintenance requirements exceed single-student project feasibility.

Multi-User Web Platform	Will focus on a local executable version instead of multi-tenant architecture.

