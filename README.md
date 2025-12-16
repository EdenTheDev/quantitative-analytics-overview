
ELH Terminal - Quantitative Portfolio Management System

--------------------------------------------------------------------------------
PROJECT ABSTRACT
--------------------------------------------------------------------------------
ELH Terminal is a full-stack financial analytics platform designed to bridge 
digital asset markets with traditional macroeconomic indicators. The system 
provides a unified interface for portfolio tracking, risk analysis, and market 
scanning. Unlike standard portfolio trackers, this application emphasizes 
quantitative metrics (Beta, Sharpe Ratio, Volatility) and real-time data 
aggregation through a custom secure proxy architecture.

The application is built as a modular monolith to ensure low-latency data 
processing and simplified deployment.

--------------------------------------------------------------------------------
SYSTEM ARCHITECTURE
--------------------------------------------------------------------------------

1. Backend (Python/FastAPI)
The server acts as a centralized API Gateway and WebSocket Proxy. It handles:
- Data Normalization: Unifies disparate data formats from Binance (Crypto), 
  Finnhub (Equities), and FRED (Macro) into a standardized internal schema.
- Security: Implements a Split-Proxy pattern where API keys and secrets remain 
  server-side. The frontend authenticates via JWT (JSON Web Tokens).
- Quantitative Engine: Uses NumPy and Pandas to calculate rolling volatility, 
  correlation coefficients, and Z-scores for market regime detection.

2. Frontend (React/TypeScript)
A responsive Single Page Application (SPA) optimized for data density.
- State Management: Localized React state for high-frequency updates.
- Visualization: Integration of Lightweight Charts (TradingView) for canvas-based 
  rendering of OHLCV data.
- Modules: Component-based architecture separating Market Overview, Portfolio 
  Management, and Screener logic.

--------------------------------------------------------------------------------
CORE FEATURES IMPLEMENTED
--------------------------------------------------------------------------------

1. Real-Time Market Data
   - Direct WebSocket integration with Binance for sub-second crypto price updates.
   - Server-proxied WebSocket tunnel for Finnhub stock data to bypass CORS 
     restrictions while maintaining security.

2. Macroeconomic Intelligence
   - Automated ingestion of Federal Reserve Economic Data (GDP, CPI, Unemployment).
   - Custom "Macro Score" algorithm that weights economic indicators to determine 
     global liquidity conditions.

3. Portfolio Analytics
   - Transaction-based accounting (Buy/Sell logic with cost-basis calculation).
   - Real-time PnL (Profit and Loss) tracking.
   - Risk Metrics: Calculation of Portfolio Beta (relative to BTC), Annualized 
     Volatility, and Sharpe Ratio.

4. Asset Screener
   - Search functionality for traditional finance assets (Stocks, ETFs, Indices).
   - On-demand fetching of historical candle data with fallback simulation.

--------------------------------------------------------------------------------
TECHNICAL STACK
--------------------------------------------------------------------------------
- Server: Python 3.10+, FastAPI, Uvicorn, SQLite
- Client: React 19, TypeScript, Vite, Tailwind CSS
- Data Science: Pandas, NumPy, SciPy
- Protocols: REST, WebSockets, OAuth2 (JWT)

--------------------------------------------------------------------------------
SETUP AND INSTALLATION
--------------------------------------------------------------------------------

Prerequisites:
- Node.js v18 or higher
- Python 3.10 or higher

Backend Setup:
1. cd backend
2. python -m venv venv
3. source venv/bin/activate  (Windows: venv\Scripts\activate)
4. pip install -r requirements.txt
5. uvicorn main:app --reload

Frontend Setup:
1. cd frontend
2. npm install
3. npm run dev

--------------------------------------------------------------------------------
DEVELOPMENT NOTES
--------------------------------------------------------------------------------
- Database: Uses local SQLite (`portfolio.db`). Excluded from git.
- API Limits: Backend implements caching for Finnhub/Yahoo Finance.
- Auth: Default credentials seeded on init.
