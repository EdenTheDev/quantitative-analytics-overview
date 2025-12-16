
ELH Terminal - Quantitative Portfolio Management System (Preview)

--------------------------------------------------------------------------------
PROJECT CONTEXT
--------------------------------------------------------------------------------
This repository serves as a technical preview for a BSc Dissertation project and 
SaaS startup prototype focused on bridging digital asset markets with traditional 
macroeconomic indicators. The application is a full-stack financial analytics 
dashboard designed to provide retail investors with institutional-grade insights.

Note: This is a development snapshot intended for code review and portfolio 
demonstration.

--------------------------------------------------------------------------------
TECHNICAL ARCHITECTURE
--------------------------------------------------------------------------------

1. Backend (Python 3.10+ / FastAPI)
The server acts as a centralized API Gateway and WebSocket Proxy. It handles:
- Data Normalization: Unifies disparate data formats from Binance (Crypto), 
  Finnhub (Equities), and FRED (Macro) into a standardized internal schema.
- Security: Implements a Split-Proxy pattern where API keys and secrets remain 
  server-side. The frontend authenticates via JWT (JSON Web Tokens).
- Quantitative Engine: Uses NumPy and Pandas to calculate rolling volatility, 
  correlation coefficients, and Z-scores for market regime detection.

2. Frontend (React 19 / TypeScript)
A responsive Single Page Application (SPA) optimized for data density.
- Visualization: Integrates Lightweight Charts (TradingView) for canvas-based 
  rendering of financial data.
- State Management: Uses localized React state for high-frequency updates, 
  minimizing re-renders during WebSocket stream events.

--------------------------------------------------------------------------------
CORE FEATURES IMPLEMENTED
--------------------------------------------------------------------------------

1. Real-Time Market Data
   - Direct WebSocket integration with Binance for sub-second crypto price updates.
   - Server-proxied WebSocket tunnel for Finnhub stock data.

2. Macroeconomic Intelligence
   - Automated ingestion of Federal Reserve Economic Data (GDP, CPI).
   - Custom "Macro Score" algorithm weighting liquidity and sentiment.

3. Portfolio Analytics
   - Transaction-based accounting with cost-basis calculation.
   - Real-time PnL tracking and risk metrics (Sharpe Ratio, Max Drawdown).

4. Predictive Modeling
   - Linear regression forecasting for price targets.
   - Seasonality analysis using historical monthly return distributions.

5. AI Assistant
   - Context-aware chatbot (Google Gemini 2.5) that ingests live portfolio state.

--------------------------------------------------------------------------------
SETUP INSTRUCTIONS
--------------------------------------------------------------------------------

Prerequisites:
- Node.js v18+
- Python 3.10+

Backend:
1. cd backend
2. python -m venv venv
3. source venv/bin/activate
4. pip install -r requirements.txt
5. uvicorn main:app --reload

Frontend:
1. cd frontend
2. npm install
3. npm run dev

--------------------------------------------------------------------------------
DEVELOPMENT STATUS
--------------------------------------------------------------------------------
[x] WebSocket stability and reconnection logic.
[x] Basic quantitative risk modeling.
[ ] Advanced on-chain analysis.
[ ] Electron wrapper packaging.

