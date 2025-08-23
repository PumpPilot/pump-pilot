# PumpPilot Pro (GitHub Pages)

Single-file, client-only Pump.fun sniper with:
- Token gate (holder of your mint)
- TP/SL auto-sell
- Per-wallet PnL (local storage)
- Filters: renounced, liquidity (Birdeye), bad words, require migration
- Configurable RPC
- Optional Jito bundle sending

## Quick Deploy
1) Create a repo and upload `index.html`, `404.html` (copy of index), and `logo.png` to the repo root.
2) (Launch time) Edit **index.html** and replace `YOUR_PUMPFUN_MINT` in **two** places. Also set `MARKET_URL`.
   - Or set these in **config.json** and leave the HTML untouched.
3) Enable **GitHub Pages**: Settings → Pages → Deploy from a branch → `main` / `/` (root).
4) Visit your Pages URL. Click **Connect**, verify **Holder** state, and **Start Bot**.

## Self-Test
- Preview button works without Phantom (UI only).
- DevTools → Network:
  - WS to `wss://pumpportal.fun/api/data`.
  - `POST https://pumpportal.fun/api/trade-local` on buy/sell (binary tx).
  - If Jito enabled, a `sendBundle` POST to the block engine URL.

## Notes
- Keep the tab open while the bot runs.
- Trades are non-custodial (you sign in wallet).
- PnL is best-effort. For exact fills, integrate historical fills later.
