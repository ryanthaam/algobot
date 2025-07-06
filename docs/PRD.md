# 🤖 AlgoBot

An automated trading bot designed to execute high-probability liquidity sweep setups with disciplined risk management enhanced with ML-based trade filtering using Random Forest.

---

## 📌 Overview

AlgoBot combines:
- 🧠 Liquidity sweep detection (fakeouts above/below key levels)
- ⚙️ Rule-based entry + risk-reward engine
- 🧪 ML filtering using Random Forest to boost decision quality
- 📈 Real-time trade execution via Bybit
- 📊 (WIP) Backtesting + performance monitoring

---

## 🧠 Strategy Summary

- **Market**: Nasdaq, S&P500 (1m / 5m)
- **Entry Conditions**:
  - Price sweeps above/below a key high/low
  - Structure shift confirmation
  - R:R ≥ 2.0
  - **Random Forest predicts win probability > 70%**
- **Exit Conditions**:
  - Stop-loss at invalidation zone
  - Take-profit at predefined RR target

---

## 🧩 Core Features

| Feature                  | Description                                                      |
|--------------------------|------------------------------------------------------------------|
|  Liquidity Sweep Logic | Detect fakeouts using candle/volume/structure                    |
|  Risk Engine           | Configurable RR model with SL/TP + capital exposure rules         |
|  ML Trade Filter       | Uses Random Forest classifier trained on past setups              |
|  Bybit Integration     | REST + WebSocket APIs for live trading and market data            |
|  Backtester Module     | Run offline simulations on historical OHLCV data                  |
|  Trade Log Dashboard   | Visual logs (Streamlit) with win-rate, RR distribution, equity curve |
|  Alerts (Telegram)     | Optional trade alerts + daily summary                             |

---

## 🔬 ML Integration: Random Forest Classifier

AlgoBot uses a trained Random Forest model to evaluate setup quality before execution.

### Feature Inputs:
- Candle body/volume ratios
- RSI, volatility (ATR)
- Distance from liquidity zone
- Structure shift boolean
- Risk-reward profile

Only trades with high predicted success probability (e.g., >70%) are executed.

---

## 🧠 Tech Stack

| Layer        | Tool/Library                       |
|--------------|------------------------------------|
| Bot Logic    | Python                             |
| ML Models    | `scikit-learn`, `joblib`           |
| Backtest     | `pandas`, `ccxt`, `bt` (WIP)       |
| Frontend     | Streamlit (for dashboard, WIP)     |
| API          | Bybit REST + WebSocket             |
| Deployment   | Docker, Railway / Render / VPS     |

---

## 📁 Project Structure

