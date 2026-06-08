# Binance Trading Bot

Automated cryptocurrency trading bot for the Binance exchange. Implements configurable trading strategies with real-time order book analysis, technical indicator calculations, and risk management controls.

## Features

- Real-time price streaming via Binance WebSocket API
- Configurable strategy engine (RSI, MACD, moving average crossover)
- Paper trading mode for strategy validation without live funds
- Position sizing and stop-loss enforcement
- Trade log with P&L tracking
- Telegram notification integration

## Tech Stack

| Component | Technology |
|---|---|
| Runtime | Node.js 18+ |
| Exchange API | Binance REST + WebSocket |
| Indicators | technicalindicators |
| Notifications | Telegram Bot API |

## Getting Started

```bash
npm install
cp .env.example .env
# Add your Binance API keys to .env
npm run paper-trade   # Safe — no real orders
```

## Configuration

Edit `config.js` to set trading pairs, strategy parameters, and risk limits:

```js
module.exports = {
  symbol: "BTCUSDT",
  strategy: "rsi",
  rsiPeriod: 14,
  rsiOversold: 30,
  rsiOverbought: 70,
  maxPositionSize: 0.01,  // BTC
};
```

> **Warning:** Live trading carries financial risk. Thoroughly backtest any strategy before enabling live mode.
