# Polycool Polymarket copy Trading Bot 

Polycool lets you follow the smart money on 
@Polymarket

– browse markets
– copy trading
– smart wallet feed
– 24/7 market activity

good to see this layer of tooling being built around prediction markets

the ecosystem needs it.


## Setup

1. **Clone and install**

   Ubuntu
   ```bash
   git clone https://github.com/AtlasAlperen/polycool-bot
   cd polycool-bot
   npm install
   ```

2. **Environment**

   Create a `.env` in the project root (see `.gitignore`; do not commit secrets):

   - `POLYMARKET_PRIVATE_KEY` – EOA private key that signs for the proxy wallet.
   - `PROXY_WALLET_ADDRESS` – Proxy wallet address used with Polymarket CLOB.


## Scripts

| Command   | Description                          |
|----------|--------------------------------------|
| `npm run dev`   | Run bot: `tsx src/index.ts`          |
| `npm run log`   | Run and log stdout/stderr to `log.txt` |
| `npm run check` | Run inspector: `tsx src/inspect.ts`  |
| `npm run build` | Compile: `tsc`                       |
| `npm start`     | Run compiled: `node dist/index.js`   |

## Project layout

- `src/index.ts` – Entry: load config, create CLOB client, resolve market slug, connect WebSockets, instantiate `Trade`, main loop.
- `src/config/` – Env, TOML config, market/slug helpers.
- `src/services/` – CLOB client, Gamma API, WebSockets (CLOB + RTDS).
- `src/trade/` – `Trade` class: decision logic, prices/trending, order placement (buy/sell UP/DOWN).
- `trade.toml` – Strategy and market configuration.

 <img width="392" height="176" alt="image" src="https://github.com/user-attachments/assets/15068e3f-c845-42d9-8a85-aab5dc95150d" />
   

## Disclaimer

This bot is for education and experimentation. Trading on Polymarket involves financial risk. Only use funds you can afford to lose and ensure you comply with Polymarket’s terms and applicable laws.
