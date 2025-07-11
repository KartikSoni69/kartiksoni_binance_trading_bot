# 🪙 Binance Futures Trading CLI Bot

A Python command-line bot for placing **market and advanced orders** (e.g. Stop, Stop-Limit, Take-Profit) on **Binance Futures Testnet** using the Binance API.

Supports both:
- Traditional CLI with `argparse`
- Interactive terminal interface via `questionary`

---

## 🚀 Features

- Place **Market**, **Stop**, **Stop-Market**, **Take-Profit**, and **Stop-Limit** orders
- Connects to **Binance Futures Testnet** (no real money used)
- Logs all activity to `logs/bot.log`
- Interactive CLI mode for beginners
- Secure `.env` support for API keys

---

## 📦 Requirements

- Python 3.7+
- `python-binance`
- `questionary`
- `python-dotenv`

Install dependencies:

```bash
pip install -r requirements.txt
```

## 🔐 Setup: Environment Variables
Create a .env file in the root of your project:
```
BINANCE_API_KEY=your_testnet_api_key
BINANCE_API_SECRET=your_testnet_api_secret
```

You can get testnet keys from:
👉 https://testnet.binancefuture.com


🧪 Run the Bot
Option 1: Standard CLI
```
python main.py --symbol BTCUSDT --side BUY --quantity 0.01
```
Advanced Orders:

```
python main.py \
  --symbol BTCUSDT \
  --side SELL \
  --quantity 0.01 \
  --order_type STOP \
  --stop_price 28000 \
  --price 27950
```

## Order Types Supported:
* MARKET
* STOP_MARKET
* STOP (Stop-Limit)
* TAKE_PROFIT
* TAKE_PROFIT_LIMIT


Option 2: Interactive CLI (User-Friendly)
```
python cli_user_friendly.py
Answer prompts for symbol, side, order type, stop/limit prices, etc.
```
📁 Project Structure

```
binance_bot/
│
├── main.py                  # Argparse CLI
├── cli_user_friendly.py     # Questionary-based UI
├── trading_logic.py         # Handles order creation
├── api_client.py            # Initializes Binance client
├── config.py                # Loads .env API keys
├── logger.py                # Logs to logs/bot.log
├── .env                     # Your private API keys (not tracked)
├── logs/
│   └── bot.log
└── requirements.txt
```
📒 Logs
All activity (successful and failed orders) are saved to:
```
logs/bot.log
```

⚠️ Disclaimer
This project is for educational purposes on the Binance Futures Testnet only.
It does not use real money and should not be connected to the main Binance environment without careful review.

📧 Contact
Built by Kartik Soni
Feel free to fork, customize, and extend!
