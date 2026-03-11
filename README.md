📈 CryptoTrack — Crypto Portfolio Tracker
A lightweight, single-file crypto portfolio tracker built with vanilla HTML, CSS, and JavaScript. Track your holdings, monitor real-time prices, and visualize your allocation — no backend required.

Live prices powered by the CoinGecko API · No sign-up · No server · No dependencies to install


✨ Features

Live prices for the Top 20 cryptocurrencies via CoinGecko API
Portfolio tracker — add coins with quantity and buy price
Profit / Loss calculated automatically per coin and overall
Allocation chart — interactive doughnut chart via Chart.js
Summary cards — Total Invested, Portfolio Value, Total P&L
Auto-refresh every 30 seconds with live countdown
Persistent storage — portfolio saves to localStorage across sessions
Quick-add — click any market row to pre-fill the coin selector


🚀 Getting Started
No build tools, no npm install, no server needed.
bash# 1. Clone the repo
git clone https://github.com/your-username/crypto-portfolio-tracker.git

# 2. Open in browser
cd crypto-portfolio-tracker
open index.html
Or just download index.html and open it directly in any modern browser.

🗂️ Project Structure
crypto-portfolio-tracker/
└── index.html      # Everything — HTML, CSS, JS in one file

🧑‍💻 How to Use

Browse the market — The bottom table shows live prices for the Top 20 coins with 24h change
Add a coin — Click a market row to select it (or use the dropdown), enter your quantity and average buy price, then click + Add Coin
Track P&L — Your portfolio table updates instantly with current value and profit/loss per coin
View allocation — The doughnut chart shows how your portfolio is distributed
Auto-save — Everything is saved to your browser's localStorage automatically


🛠️ Tech Stack
LayerTechnologyMarkupHTML5StylingCSS3 (custom properties, grid, flexbox)LogicVanilla JavaScript (ES2020+)ChartsChart.js 4.4 via CDNPricesCoinGecko Public APIStorageBrowser localStorage

📡 API Reference
This project uses two CoinGecko public endpoints (no API key required):
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

💰 Supported Coins
#CoinSymbol1BitcoinBTC2EthereumETH3TetherUSDT4BNBBNB5SolanaSOL6XRPXRP7CardanoADA8DogecoinDOGE9TRONTRX10PolkadotDOT11PolygonMATIC12LitecoinLTC13AvalancheAVAX14ChainlinkLINK15UniswapUNI16StellarXLM17CosmosATOM18FilecoinFIL19AptosAPT20NEAR ProtocolNEAR

📐 Portfolio Calculations
Value        = quantity × current price
Invested     = quantity × buy price
Profit/Loss  = value − invested
P&L %        = (profit / invested) × 100

Total P&L    = Σ(value) − Σ(invested)
When you add the same coin twice, the position is averaged:
avg buy price = (old_qty × old_buy + new_qty × new_buy) / total_qty

🔒 Privacy
All data stays in your browser. Nothing is sent to any server other than CoinGecko's public price API. No tracking, no analytics, no accounts.

📄 License
MIT — free to use, fork, and modify.
