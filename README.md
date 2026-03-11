# 📈 CryptoTrack — Crypto Portfolio Tracker

A lightweight, single-file crypto portfolio tracker built with vanilla HTML, CSS, and JavaScript. Track your holdings, monitor real-time prices, and visualize your allocation — no backend required.

> Live prices powered by the [CoinGecko API](https://www.coingecko.com/en/api) · No sign-up · No server · No dependencies to install

---

## ✨ Features

- **Live prices** for the Top 20 cryptocurrencies via CoinGecko API
- **Portfolio tracker** — add coins with quantity and buy price
- **Profit / Loss** calculated automatically per coin and overall
- **Allocation chart** — interactive doughnut chart via Chart.js
- **Summary cards** — Total Invested, Portfolio Value, Total P&L
- **Auto-refresh** every 30 seconds with live countdown
- **Persistent storage** — portfolio saves to `localStorage` across sessions
- **Quick-add** — click any market row to pre-fill the coin selector

---

## 🚀 Getting Started

No build tools, no npm install, no server needed.

```bash
# 1. Clone the repo
git clone https://github.com/your-username/crypto-portfolio-tracker.git

# 2. Open in browser
cd crypto-portfolio-tracker
open index.html
```

Or just download `index.html` and open it directly in any modern browser.

---

## 🗂️ Project Structure

```
crypto-portfolio-tracker/
└── index.html      # Everything — HTML, CSS, JS in one file
```

---

## 🧑‍💻 How to Use

1. **Browse the market** — The bottom table shows live prices for the Top 20 coins with 24h change
2. **Add a coin** — Click a market row to select it (or use the dropdown), enter your quantity and average buy price, then click **+ Add Coin**
3. **Track P&L** — Your portfolio table updates instantly with current value and profit/loss per coin
4. **View allocation** — The doughnut chart shows how your portfolio is distributed
5. **Auto-save** — Everything is saved to your browser's localStorage automatically

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 (custom properties, grid, flexbox) |
| Logic | Vanilla JavaScript (ES2020+) |
| Charts | [Chart.js 4.4](https://www.chartjs.org/) via CDN |
| Prices | [CoinGecko Public API](https://docs.coingecko.com/) |
| Storage | Browser `localStorage` |

---

## 📡 API Reference

This project uses two CoinGecko public endpoints (no API key required):

```
# Simple prices with 24h change
GET https://api.coingecko.com/api/v3/simple/price
  ?ids=bitcoin,ethereum,...
  &vs_currencies=usd
  &include_24hr_change=true

# Market data (logos, rankings, etc.)
GET https://api.coingecko.com/api/v3/coins/markets
  ?vs_currency=usd
  &ids=bitcoin,ethereum,...
  &order=market_cap_desc
```

---

## 💰 Supported Coins

| # | Coin | Symbol |
|---|---|---|
| 1 | Bitcoin | BTC |
| 2 | Ethereum | ETH |
| 3 | Tether | USDT |
| 4 | BNB | BNB |
| 5 | Solana | SOL |
| 6 | XRP | XRP |
| 7 | Cardano | ADA |
| 8 | Dogecoin | DOGE |
| 9 | TRON | TRX |
| 10 | Polkadot | DOT |
| 11 | Polygon | MATIC |
| 12 | Litecoin | LTC |
| 13 | Avalanche | AVAX |
| 14 | Chainlink | LINK |
| 15 | Uniswap | UNI |
| 16 | Stellar | XLM |
| 17 | Cosmos | ATOM |
| 18 | Filecoin | FIL |
| 19 | Aptos | APT |
| 20 | NEAR Protocol | NEAR |

---

## 📐 Portfolio Calculations

```
Value        = quantity × current price
Invested     = quantity × buy price
Profit/Loss  = value − invested
P&L %        = (profit / invested) × 100

Total P&L    = Σ(value) − Σ(invested)
```

When you add the same coin twice, the position is averaged:

```
avg buy price = (old_qty × old_buy + new_qty × new_buy) / total_qty
```

---

## 🔒 Privacy

All data stays in your browser. Nothing is sent to any server other than CoinGecko's public price API. No tracking, no analytics, no accounts.

---

## 📄 License

MIT — free to use, fork, and modify.
